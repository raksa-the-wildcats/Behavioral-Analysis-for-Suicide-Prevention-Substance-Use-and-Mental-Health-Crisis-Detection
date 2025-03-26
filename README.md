This repository contains a 3-part pipeline to extract, classify, and geolocate mental health–related discussions from Twitter, using NLP, sentiment analysis, and interactive mapping.

## ✅ Project Objectives

- Extract and analyze crisis-related discussions from social media
- Detect high-risk content using sentiment and keyword-based classification
- Visualize geographic trends of mental health distress on an interactive map

---

## 🔧 Tasks Overview

### Task 1: Social Media Data Extraction & Preprocessing
- Extract tweets via **Twitter API v2** using mental health–related keywords
- Store `Post ID`, `Timestamp`, `Text`, and `Engagement metrics`
- Clean text by removing emojis, stopwords, special characters

📁 Output:
- `cleaned_tweets.csv`: Preprocessed tweet dataset for NLP

---

### Task 2: Sentiment & Crisis Risk Classification
- Apply **VADER** sentiment analyzer to label tweets: *Positive, Neutral, Negative*
- Classify tweets into **Risk Levels**:
  - **High Risk** – suicidal intent or crisis language
  - **Moderate Concern** – seeking help or emotional struggle
  - **Low Concern** – general mental health discussions
- Use **TF-IDF** to identify distinguishing words in each risk level

📁 Output:
- `task2_sentiment_risk.csv`: Tweets labeled with sentiment and risk
- Distribution plots of sentiment & risk level

---

### Task 3: Geolocation & Crisis Mapping
- Extract user profile locations and geocode to coordinates
- Generate a **heatmap** of crisis mentions using **Folium**
- Identify top 5 locations with the most mental health discussions

📁 Output:
- `tweets_geocoded.csv`: Tweets with lat/lon
- `twitter_crisis_heatmap.html`: Interactive map visualization

---

## 📦 Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

Or manually install:

```bash
pip install pandas requests nltk vaderSentiment folium geopy scikit-learn spacy
python -m nltk.downloader stopwords punkt
python -m spacy download en_core_web_sm
```

---

## 🚀 How to Run

1. **Set up Twitter API credentials** with Bearer Token
2. Run the notebook step-by-step (`AI-Powered Behavioral Analysis.ipynb`)
3. Open `twitter_crisis_heatmap.html` to explore geographic trends

---

## 📌 Notes

- Uses publicly available Twitter data (filtered for mental health keywords)
- Nominatim geocoder is rate-limited — allow a delay when geocoding
- No personal or identifiable data is collected

---

## 📚 Acknowledgments

This project was completed as part of the **GSoC HumanAI Candidate Assessment** challenge.
