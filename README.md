# Airbnb Text Analytics & NLP Project

## Overview

This project analyses **Airbnb listing performance** using a combination of:

- Listing metadata
- Guest reviews
- Large Language Model (LLM) summaries
- Natural Language Processing (NLP) with spaCy

The goal is to understand **what drives high-performing listings**, identify **issues in low-performing listings**, and assess whether the analysed market represents a **good Airbnb investment opportunity**.

---

## Project Workflow

The workflow includes:

- Data cleaning and preprocessing  
- Selection of **Top 5 and Bottom 5 listings**  
- Balanced review usage (**maximum 30 reviews per listing**)  
- LLM-based review summarisation  
- spaCy NLP analysis  
- Comparison of top vs bottom listings  
- Generation of structured JSON insights

---

## Repository Structure


Airbnb_Project/
│
├── data/
│ ├── all_reviews_export.csv
│ ├── bottom_reviews_export.csv
│ ├── cleaned_listings_df.csv
│ ├── cleaned_reviews.csv
│ ├── listings.csv
│ ├── reviews.csv
│ ├── reviews_df_export.csv
│ └── top_reviews_export.csv
│
├── notebooks/
│ ├── EDA.ipynb
│ ├── Preprocess_workbook.ipynb
│ └── Spacy_eda.ipynb
│
├── results/
│ ├── bottom_5_listings.csv
│ ├── bottom_5_sampled_reviews.csv
│ ├── Top 5 Listings.csv
│ ├── top_5_sampled_reviews.csv
│ ├── top_5_with_reviews.csv
│ └── llm_outputs/
│ ├── listing_metadata_analysis.json
│ └── listing_review_analysis.json
│
├── Airbnb Presentation (2).pdf
└── README.md


---

## Project Objectives

- Evaluate whether the selected market is suitable for **Airbnb investment**
- Identify characteristics of **high-performing listings**
- Detect recurring issues in **lower-performing listings**
- Analyse **guest review sentiment**
- Generate structured **NLP outputs for each property**

---

## Data Pipeline

### Data Cleaning

- Loaded listing metadata and review text
- Standardised column formats
- Removed incomplete or invalid entries
- Ensured ID consistency between listings and reviews

---

### Selecting Top and Bottom Listings

**Top Listings**

- Selected using the **highest review scores**
- Ensured **unique hosts** to avoid bias

**Bottom Listings**

- Filtered using rating range **2.8 – 3.4**
- Ensured **unique hosts**
- Required **at least 5 recent reviews**

---

### Review Dataset Preparation

For each listing:

- Exported all reviews
- Applied a **maximum cap of 30 reviews per property**
- Created the following datasets:


all_reviews_export.csv
top_reviews_export.csv
bottom_reviews_export.csv


Sampled review datasets are stored in the `results/` directory.

---

## LLM Analysis

For each listing:

- Reviews were combined into a single text corpus
- An LLM generated structured insights including:

- Review summary
- Positive themes
- Negative themes
- Suggested improvements
- Metadata observations
- Investment signals

Outputs are stored in:


results/llm_outputs/


---

## spaCy NLP Analysis

NLP analysis was performed in:


notebooks/Spacy_eda.ipynb


Techniques used include:

- Tokenisation and lemmatisation
- Stopword removal
- Extraction of adjectives and descriptive language
- Keyword frequency comparison between top and bottom listings
- Theme identification across:

  - Cleanliness  
  - Noise  
  - Communication  
  - Accuracy  
  - Comfort  

---

## Key Insights

The combined **LLM and NLP analysis** highlights:

- Features that guests value most in highly rated listings
- Recurring problems in poorly performing listings
- Alignment (or mismatch) between **listing descriptions and guest experiences**
- Improvement opportunities for underperforming properties
- Signals indicating whether the market is suitable for Airbnb investment

  These insights could help investors evaluate whether a market presents a viable short-term rental opportunity.
---
## Business Impact

This analysis demonstrates how guest reviews and listing metadata can be used to:

- Identify characteristics of high-performing Airbnb listings
- Detect recurring problems in poorly rated properties
- Provide actionable improvement suggestions for hosts
- Support real estate investment decisions


---
## Key Skills Demonstrated

- Data Cleaning & Preprocessing (Pandas)
- Exploratory Data Analysis
- Natural Language Processing (spaCy)
- Large Language Model Integration
- Data Visualisation
- Text Analytics
- Python Workflow Development

---

## Running the Project

Install required libraries:

```bash
pip install pandas numpy spacy matplotlib openai

Launch Jupyter:

jupyter notebook

Example dataset loading:

data = pd.read_csv("../data/all_reviews_export.csv")
Future Improvements

Possible extensions include:

Topic modelling (BERTopic, LDA)

Large-scale sentiment scoring (VADER, TextBlob)

Pricing or occupancy prediction models

Host communication pattern analysis

Automation of LLM summarisation workflows

Authors

Anjali Rehal
Emmanuel Oloruntola

Rockborne Data Consultant Trainees
