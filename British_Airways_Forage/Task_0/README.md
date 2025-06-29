#  British Airways Customer Reviews Analysis

## 🔗 Project Overview

The goal of this task is to apply Natural Language Processing (NLP) techniques to understand customer sentiment, identify key themes in reviews, and surface areas of excellent performance and those requiring improvement.

## 🔍 Business & Data Science Goals

**Business Goals:**

* Understand what customers are praising or complaining about.
* Identify actionable areas to enhance customer experience and brand perception.

**Data Science Goals:**

* Apply NLP techniques such as sentiment analysis, TF-IDF, and topic modeling.
* Translate unstructured review text into structured insights for reporting.

## 📊 Tools and Technologies

* Python (Pandas, NLTK, spaCy, scikit-learn, Gensim, Matplotlib, Seaborn)
* VADER and TextBlob for sentiment analysis
* pyLDAvis for topic modeling visualization
* Jupyter Notebook, VSCode
* Git and GitHub

## 📂 Dataset & Collection

* Source: [AirlineQuality - British Airways](https://www.airlinequality.com/airline-reviews/british-airways)
* Method: Web scraping 50 pages using `requests` and `BeautifulSoup`
* Total reviews collected: **\~3628 verified reviews**

## 💚 Data Preparation & Cleaning

1. **Filtered for Verified Trips**: Removed reviews tagged with "Not Verified".
2. **Removed Tags**: Stripped tags like "✅ Trip Verified |" from review beginnings.
3. **Structured**: Stored in a clean DataFrame.

## 🔧 Text Preprocessing

* Lowercasing
* Removal of punctuation, digits, and stopwords (default + custom list)
* Lemmatization using spaCy
* Tokenization
* Extracted route mentions (origin/destination) where available

## 📊 Sentiment Analysis

### Tools Used:

* **TextBlob**: Polarity and Subjectivity
* **VADER**: Compound sentiment scores (more robust for short review texts)

### 📈 Summary:

**Polarity (TextBlob)**

* Mean: 0.12 → Slightly positive sentiment overall
* 25th percentile: -0.01 → At least 25% of reviews are neutral or slightly negative
* Full range: \[-1.0, 1.0] → Indicates a diverse spectrum of feedback

**Subjectivity (TextBlob)**

* Mean: 0.53 → Moderately subjective content
* Range: \[0.0, 1.0] → Mix of factual and opinionated reviews

**VADER Sentiment**

* Mean: 0.31 → Skewed slightly toward positive
* Median: 0.68 → Most reviews lean positive, but a long tail exists

## 🌐 Keyword Analysis

### WordClouds

* Revealed high-frequency words: `seat`, `service`, `crew`, `food`, `time`, `delay`, etc.

### TF-IDF Analysis by Sentiment

* **Negative Reviews**: `delay`, `hour`, `london`, `cancel`, `staff`
* **Neutral Reviews**: `seat`, `check`, `crew`, `cabin`, `service`
* **Positive Reviews**: `good`, `crew`, `club`, `lounge`, `excellent`

### Radar Chart Insight:

* `seat` dominates all categories
* `crew`, `good`, and `club` are strongly tied to positive sentiment
* `delay`, `heathrow`, and `hour` are highly negative-associated

## 🧬 Topic Modeling (LDA)

### Model:

* **LDA via Gensim**
* Optimal Number of Topics: **3** (determined by coherence score)

### Final Topics:

1. **Operational Issues** → Keywords: `hour`, `check`, `delay`, `tell`, `staff`
2. **Cabin & Flight Features** → Keywords: `class`, `business`, `airline`, `food`, `economy`
3. **Positive Experience** → Keywords: `good`, `crew`, `service`, `lounge`, `club`

### pyLDAvis Interpretation:

* All three topic bubbles were large and well-separated → high model quality
* Topic 3 (Positive Experience) was distinct from others, indicating clearly differentiated praise

## 🌍 Topic Distribution & Sentiment Mapping

| Topic Label             | Mean VADER Sentiment | Review Count |
| ----------------------- | -------------------- | ------------ |
| Positive Experience     | 0.74                 | 1527         |
| Cabin & Flight Features | 0.10                 | 1109         |
| Operational Issues      | -0.13                | 972          |

### Interpretation:

* Positive feedback is clearly associated with **crew**, **service**, and **lounge** mentions.
* Complaints are strongly linked with **delays**, **check-in**, and **airport experience**.

## 🌟 Final Insights

* **Strengths**: Crew professionalism, food, and premium experiences (e.g. lounges, club seating)
* **Weaknesses**: Operational inefficiencies like delays, check-in problems, and communication
* **Opportunities**:

  * Improve airport handling and delay communication
  * Promote positive experiences more visibly (highlight lounges, crew quality)

## 📅 Next Steps

* Integrate review metadata (e.g., date, route, customer type) for deeper segmentation
* Track sentiment trends over time
* Deploy insights into dashboards for continuous monitoring

---

*Prepared with 💙 by Kofoworola Egbinola*
