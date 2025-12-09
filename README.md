<<<<<<< HEAD
Airbnb Text Analytics & NLP Project

Repository:
https://github.com/Emmandara/Airbnb_Text_Analytics_Project.git

Overview

This project analyses Airbnb listing performance using a combination of structured listing metadata, raw guest reviews, LLM-generated summaries, and spaCy-based NLP techniques.
The aim is to identify the drivers of high-performing listings, understand shortcomings in poorly performing listings, and assess whether the analysed market presents a good Airbnb investment opportunity.

The workflow includes:

Data cleaning and preprocessing

Selection of Top 5 and Bottom 5 listings

Balanced review usage (capped at 30 reviews per listing)

LLM summarisation and theme extraction

spaCy NLP analysis

Comparison between top and bottom performing listings

Generation of structured JSON outputs for each property

Folder Structure (Current)
Airbnb_Project/
│   .gitignore
│
├── data
│       all_reviews_export.csv
│       bottom_reviews_export.csv
│       cleaned_listings_df.csv
│       cleaned_reviews.csv
│       listings.csv
│       reviews.csv
│       reviews_df_export.csv
│       top_reviews_export.csv
│
├── notebooks
│       EDA.ipynb
│       Preprocess_workbook.ipynb
│       Spacy_eda.ipynb
│
└── results
    │   bottom_5_listings.csv
    │   bottom_5_sampled_reviews.csv
    │   Top 5 Listings.csv
    │   top_5_sampled_reviews.csv
    │   top_5_with_reviews.csv
    │
    └── llm_outputs
            listing_<id>_metadata_analysis.json
            listing_<id>_review_analysis.json


This README reflects the structure exactly as it currently exists.

Project Objectives

Evaluate whether the selected market is suitable for Airbnb investment.

Identify characteristics associated with the best-performing Airbnb listings.

Detect recurring issues in lower-performing listings.

Understand how guest review sentiment aligns with listing metadata.

Produce structured, repeatable NLP outputs for each listing.

Data Pipeline
1. Data Cleaning

Loaded and cleaned listing metadata and review text

Standardised column formats

Removed invalid or incomplete entries

Ensured ID consistency between listing and review datasets

2. Selecting Top and Bottom Listings

Top 5 listings selected using highest review scores and unique hosts

Bottom 5 listings filtered using a rating band (2.8–3.4), unique hosts, ≥5 recent reviews

3. Handling Review Data

Exported all reviews per listing

Applied a maximum cap of 30 reviews per property to avoid imbalance

Created datasets:

all_reviews_export.csv

top_reviews_export.csv

bottom_reviews_export.csv

Sampled versions stored in results/

4. LLM Summaries

For each listing:

Combined review text

Generated structured JSON containing:

Review summary

Positive themes

Negative themes

Suggested improvements

Metadata observations

Investment-related signals

Outputs are stored in results/llm_outputs/.

5. spaCy NLP Analysis

Performed in Spacy_eda.ipynb:

Tokenisation and lemmatisation

Removal of stopwords

Extraction of adjectives and sentiment-associated words

Keyword frequency comparison between top and bottom properties

Theme identification across cleanliness, noise, communication, accuracy and comfort

Insights

The combined LLM and NLP analysis helps reveal:

What guests appreciate most in well-performing listings

Repeated issues that occur in lower-rated listings

Whether host-provided metadata aligns with actual guest experiences

Improvement points for lower-performing listings

Indicators supporting or refuting the suitability of the market for investment

Running the Project

Install any required Python libraries as needed (optional):

pip install pandas numpy spacy matplotlib openai


Open the notebooks:

jupyter notebook


Use relative paths when loading data from notebooks:

data = pd.read_csv("../data/all_reviews_export.csv")

Future Improvements

Topic modelling (BERTopic, LDA)

Sentiment scoring at scale (e.g., VADER or TextBlob)

Pricing or occupancy prediction models

Host communication pattern analysis

Automation of LLM summarisation workflow

Authors

Anjali Rehal  & Emmanuel Oloruntola
Rockborne Data Consultant Trainees
=======
# Airbnb_Text_Analytics_Project
“Airbnb review analysis using LLM and spaCy NLP”
>>>>>>> ac641befd3f366baf7bc6b4538c0fa6ba71a53f2
