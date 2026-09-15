# Sentiment Analysis of Amazon Fine Food Reviews

## Overview
An NLP project that classifies Amazon Fine Food reviews into **negative, neutral, and positive** sentiment using classic machine learning models. Star ratings are mapped to sentiment labels, and TF-IDF features are used to train and compare Naive Bayes and Logistic Regression classifiers.

## Dataset
- Source: Amazon Fine Food Reviews (`Reviews.csv`)
- Labels derived from `Score`: 1–2 → negative, 3 → neutral, 4–5 → positive
- Balanced sample of 7,000 reviews per class to avoid class imbalance

## Workflow
1. **Data Loading & Labeling** — map star ratings to sentiment classes, drop nulls/duplicates
2. **Text Preprocessing** — lowercasing, tokenization, stopword removal (negation words like "not", "never" retained), lemmatization
3. **Feature Extraction** — TF-IDF vectorization (unigrams + bigrams, 8,000 features)
4. **Modeling** — Multinomial Naive Bayes and Logistic Regression (class-balanced)
5. **Evaluation** — Accuracy, Precision, Recall, F1-score, confusion matrices
6. **Visualization** — class distribution plots, model comparison chart, word clouds per sentiment
7. **Error Analysis** — inspection of misclassified reviews and discussion of common failure patterns (mixed-sentiment reviews, neutral vs. positive/negative confusion)

## Key Findings
- Logistic Regression generally outperformed Naive Bayes, benefiting from `class_weight='balanced'` to better handle the harder neutral class
- Most misclassifications came from mixed-sentiment reviews and borderline neutral ratings

## Tech Stack
Python · pandas · NumPy · NLTK · scikit-learn · Matplotlib · Seaborn · WordCloud

## Files
- `Amazon_fine_food_SentimentAnalysis.ipynb` — full analysis notebook
