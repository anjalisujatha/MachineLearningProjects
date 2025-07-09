#  TED Talks Recommendation System

This project builds a personalized TED Talks recommendation engine using Natural Language Processing and similarity measures. It suggests relevant talks based on a given input description or topic of interest.

##  Objectives

- Clean and preprocess TED talk metadata
- Generate meaningful embeddings using TF-IDF
- Compute similarity using Cosine and Pearson correlation
- Recommend TED talks most similar to a user's interest

##  Dataset

- `tedx_dataset.csv`
- Features:
  - `main_speaker`: Name of the TED speaker
  - `title`: Title of the TED talk
  - `details`: Talk description
  - `posted`: Date when the talk was published
  - `url`: URL to the talk
  - `num_views`: View count (mostly missing)

##  Preprocessing Steps

- Combined `title` and `details` for rich context
- Removed stopwords using NLTK
- Removed punctuation and converted text to lowercase
- Created a word cloud for visualization
- Extracted `year` and `month` from the `posted` field

##  Text Representation

- TF-IDF vectorizer used to convert text into numeric vectors
- Cosine Similarity and Pearson Correlation used to compute similarity between talks

##  Recommendation Logic

The function `recommend_talks()`:
- Takes a new talk/topic as input
- Compares it with all TED talks in the dataset
- Returns top 5 most similar TED talks based on cosine and Pearson similarity scores

