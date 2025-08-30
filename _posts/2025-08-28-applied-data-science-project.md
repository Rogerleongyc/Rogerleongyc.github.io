layout: post
author: Leong Ying Cheu
title: "Applied Data Science Project Documentation"
categories: ITD214 PROJECT
---
## Project Background
Provide an overview of your team's project business goals and objectives and state the objective that you are working on. 

Team Project: Business Goals & Objectives

Business Goal
Maximize the commercial and critical success of upcoming film productions
— by leveraging historical movie data to generate actionable insights and increase overall revenue by 5%.

Team Objectives

Predict Box Office Revenue (By Kelvin)

Predict User Ratings (By Augustine)

Predicting sentiments for new movies (By Shir Min)

Predict Commercial Success Class (Blockbuster Classification) - (By Roger, myself)

Develop a predictive model to classify whether a movie will be a Blockbuster or Not, based on both textual features (like overview and tagline) and structured metadata (like director, genre, popularity).

My goal was to:
Extract meaningful signals from movie metadata and text descriptions.
Apply text analytics techniques (lemmatization, TF-IDF)
Engineer hybrid features and train classification models (Logistic Regression, Random Forest, SGB).
Evaluate models to determine the best performer for classifying Blockbuster vs Non-Blockbuster outcomes.
This classification helps stakeholders screen high-potential projects during early production stages — saving cost and maximizing returns.

## Work Accomplished
To fulfill my objective, I developed a machine learning pipeline that predicts whether a movie is likely to become a Blockbuster or Not Blockbuster. This involved:

Filtering and cleaning metadata for release month and genres.

Transforming textual features (overview + tagline) using NLP techniques.

Engineering a hybrid feature set combining structured data and cleaned text.

Training and comparing multiple classification models (Logistic Regression, Random Forest, SGB).

Evaluating models using accuracy, F1 score, and ROC AUC.

Selecting Random Forest as the final model for its balance between performance and overfitting resistance.

Implementing a real-time prediction interface using ipywidgets.

### Data Preparation
Data used originated from a merged IMDb + TMDB metadata dataset. Key steps included:

Filtering Genres: Removed rows where genres_list contained only ['Unknown'] to avoid noisy inputs.

Cleaning Release Dates: Extracted valid release_month values and excluded rows with nulls or unknowns.

Popularity Filtering: Limited popularity to a realistic range (5 to 1000), and created a popularity_level using percentile binning:

Top 25%: High (Blockbuster)

Bottom 25%: Low

Middle 50%: Normal

Text Preparation:

Combined overview and tagline into a single narrative.

Cleaned the text using lemmatization, stopword removal (NLTK), and spaCy’s language model.

Created clean_text for modeling and vectorization.

One-hot Encoding:

Applied LabelEncoder to Director, genres_list (first genre used), and release_month.

Ensured popularity_level was not leaked into training until target label encoding.

### Modelling

Three classifiers were trained on the final dataset using a hybrid feature set:

Text Features: TF-IDF vectorization of the clean_text (max 5000 tokens).

Categorical Features: One-hot encoding of Director, release_month, genres_list, and popularity_level.

Models used:

Logistic Regression

Random Forest Classifier

Gradient Boosting (SGB/XGBoost)

Each model was trained and validated using an 80/20 split.

### Evaluation

alt="Classifier Evaluation Chart" src="https://github.com/user-attachments/assets/4e0a1ace-9ee8-4e49-b2e7-f2618c460b02"

     


	
Although all models showed perfect scores, we recognized the risk of overfitting, particularly for complex models like SGB.

✅ Final Model Chosen: Random Forest

Chosen for its interpretability, robustness, and practical generalization.

Provides feature importance and handles mixed data types effectively.

Less sensitive to noise and performs well with imbalanced datasets.

## Recommendation and Analysis

Key Findings:

Textual features (overview + tagline), after preprocessing and TF-IDF vectorization, contributed significantly to classification performance.

Categorical metadata like Director, genre, and release month helped capture contextual patterns, especially for genres or creators historically linked to blockbuster success.

Combining structured metadata with textual insights gave the model a holistic view of each movie, improving its classification confidence.


Business Recommendations:

Use this model during the early production stage to flag promising movie scripts or ideas.

Prioritize projects predicted as blockbusters for larger budgets, wider releases, or higher marketing investment.

Monitor feature importance regularly to detect shifts in genre/director preferences over time.

Extend the model to newer data as more films are released — retraining every 6–12 months is recommended to stay relevant.


## AI Ethics

1. 🎯 Bias and Fairness
Imbalanced training data (e.g., genre or director dominance) can bias the model, underrepresenting niche films. Popularity thresholds may reflect marketing power more than quality. Sentiment features could carry genre-specific language bias.

Mitigation: Apply stratified sampling, evaluate fairness across subgroups, and examine misclassifications to detect underrepresented segments.

2. 🔍 Transparency
Random Forest and TF-IDF reduce interpretability. Stakeholders may not fully understand how predictions are made.

Mitigation: Provide feature importance charts, document preprocessing steps, and offer confidence scores alongside predictions.

3. 🔐 Data Privacy
Even with public data, proper licensing and ethical use are crucial. Avoid identifiable or sensitive data.

Mitigation: Cite all data sources, exclude private or unnecessary fields, and respect platform licenses (e.g., IMDb, TMDb).

4. ✅ Responsible Use
Overreliance on the model may marginalize unique, low-scoring creative ideas and promote formulaic films.

Mitigation: Use the model as decision support, not replacement. Flag uncertain predictions for human review and balance machine insights with human creativity.


## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 
