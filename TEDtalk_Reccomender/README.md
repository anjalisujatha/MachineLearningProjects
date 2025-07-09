#  Object-Oriented TED Talks Recommender System

This project implements a clean and modular TED Talks recommendation engine using object-oriented programming in Python. The system recommends TED talks based on user input by leveraging TF-IDF vectorization and cosine similarity.

##  Objectives

- Load and preprocess TED Talk data
- Clean and vectorize text using TF-IDF
- Compute cosine similarity for content-based recommendations
- Structure logic inside a reusable Python class
- Visualize topics with word clouds

##  Key Features

- Encapsulated in a `TEDTalkRecommender` class
- Automatically cleans and combines `title` + `details`
- Generates top-N recommendations based on cosine similarity
- Option to visualize most frequent words across talks

##  Dataset

- File: `tedx_dataset.csv`
- Key columns:
  - `main_speaker`
  - `title`
  - `details`
  - `posted`, `url`, `num_views` (optional)

##  Text Preprocessing

- Stopword removal using NLTK
- Punctuation removal and lowercase conversion
- Combination of `title` and `details` for rich context
- TF-IDF vectorization (with English stopwords)

##  How It Works

### Example:

```python
from ted_recommender import TEDTalkRecommender

recommender = TEDTalkRecommender('tedx_dataset.csv')
recommender.load_and_preprocess_data()

user_input = "Climate change and reducing carbon footprint"
recommendations = recommender.recommend(user_input)
print(recommendations)