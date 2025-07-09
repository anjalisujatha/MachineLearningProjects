# 💬 Sentiment Analysis on Text Data using Machine Learning

This project focuses on performing sentiment analysis to classify text as **positive**, **negative**, or **neutral** using machine learning techniques. It combines data preprocessing, text vectorization, and model evaluation to find the most effective sentiment classifier.

## 📌 Objectives

- Preprocess and clean text data for analysis
- Explore and visualize sentiment distribution
- Train and evaluate multiple classification models
- Identify the best-performing model for sentiment prediction

## 📊 Dataset

- Combined training and test sets
- Key features:
  - `text`: The original text
  - `selected_text`: Substring expressing sentiment
  - `sentiment`: Target label (positive, negative, neutral)
  - Additional metadata (Time of Tweet, Age of User, Country, etc.)

## 🧹 Text Preprocessing

- HTML and punctuation removal
- Lowercasing and whitespace cleanup
- Tokenization using `nltk`
- Stopword removal
- Stemming and lemmatization
- Final column used for training: `selected_text`

## 📈 Exploratory Data Analysis (EDA)

- Sentiment distribution visualized using bar charts
- Frequency distribution of sentiment-related words
- Cleaned and normalized corpus created for analysis

## 🧠 Models Trained

- **Logistic Regression**
- **Decision Tree Classifier**
- **Random Forest Classifier**

## 🧪 Model Performance

| Model                  | Accuracy |
|------------------------|----------|
| Baseline (most common) | 0.40     |
| Logistic Regression    | **0.83** |
| Decision Tree          | 0.76     |
| Random Forest          | 0.81     |

- Logistic Regression performs the best in terms of precision, recall, and f1-score across sentiment classes.

## ✨ Manual Prediction

Sample code for making predictions on new text inputs:

```python
def manual_testing(news):
    testing_news = {"text": [news]}
    new_def_test = pd.DataFrame(testing_news)
    new_def_test["text"] = new_def_test["text"].apply(wp)
    new_xv_test = vectorization.transform(new_def_test["text"])
    prediction = lr.predict(new_xv_test)
    return prediction