---
layout: post
author: Leong Ying Cheu
title: "Applied Data Science Project Documentation"
categories: ITD214
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

Encoding:

Applied LabelEncoder to Director, genres_list (first genre used), and release_month.

Ensured popularity_level was not leaked into training until target label encoding.
### Modelling
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

### Evaluation
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Recommendation and Analysis
Explain the analysis and recommendations

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## AI Ethics
Discuss the potential data science ethics issues (privacy, fairness, accuracy, accountability, transparency) in your project. 

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce bibendum neque eget nunc mattis eu sollicitudin enim tincidunt. Vestibulum lacus tortor, ultricies id dignissim ac, bibendum in velit. Proin convallis mi ac felis pharetra aliquam. Curabitur dignissim accumsan rutrum. In arcu magna, aliquet vel pretium et, molestie et arcu. Mauris lobortis nulla et felis ullamcorper bibendum. Phasellus et hendrerit mauris. Proin eget nibh a massa vestibulum pretium. Suspendisse eu nisl a ante aliquet bibendum quis a nunc. Praesent varius interdum vehicula. Aenean risus libero, placerat at vestibulum eget, ultricies eu enim. Praesent nulla tortor, malesuada adipiscing adipiscing sollicitudin, adipiscing eget est.

## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 
