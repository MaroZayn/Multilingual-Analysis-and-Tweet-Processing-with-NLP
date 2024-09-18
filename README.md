# Multilingual-Analysis-and-Tweet-Processing-with-NLP

## Overview
This project focuses on cleaning, analyzing, and visualizing tweet data, followed by sentiment analysis and entity recognition. Additionally, it involves translating tweets from multiple languages to English and performing topic classification using a zero-shot classification model.

## Steps in the Project

### 1. Data Cleaning
- Imported a dataset of tweets (`data_tweet_sample_challenge.csv`).
- Filtered the data to retain specific columns like `id`, `created_at`, `text`, `author.id`, `author.name`, `like_count`, and `retweet_count`.
- Converted columns to appropriate data types and reset the `id` column.
- Created a `date` column to store the tweet creation date and a `daytime` column to categorize tweets by time of day (morning, afternoon, evening, night).
- Extracted hashtags from the `text` column and added them as a new column.
- Cleaned the text of tweets by removing links, emojis, hashtags, and special characters.

### 2. Data Visualization
- Created bar charts to visualize:
  - Number of tweets by period of the day.
  - Top 10 authors with the most tweets.
  - Authors with the highest number of retweets.
  - Top hashtags with the most likes and retweets.
- Used pie charts to visualize:
  - Hashtags with the most likes and retweets per country.
  - The most discussed hashtag by top 10 journals.

### 3. Sentiment Analysis
- Used Hugging Face’s `transformers` library and the `sentiment-analysis` pipeline to classify each tweet as positive or negative.
- Added `sentiment_label` and `sentiment_score` columns to store sentiment analysis results.

### 4. Named Entity Recognition (NER)
- Applied NER to each cleaned tweet using the `wikineural-multilingual-ner` model from Hugging Face.
- Extracted named entities and added them to a `ner_results` column.

### 5. Language-based Data Segmentation and Translation
- Segmented the dataset by language (English, French, Spanish, German, Dutch, Italian).
- Translated non-English tweets into English using the `HappyTextToText` translation model for each language.
- Stored the translated text in a new `translated_text` column.

### 6. Topic Classification
- Used the `deberta-v3-base-tasksource-nli` zero-shot classification model from Hugging Face to classify tweets into categories like `IA`, `programming`, `data`, `popular`, and `versatile`.
- Appended the classification results as new columns to the original dataset.

## Data Visualizations
- **Daytime Tweet Distribution**: Number of tweets based on the time of day (morning, afternoon, evening, night).
- **Top 10 Authors**: Bar chart of the authors with the most tweets.
- **Retweet Distribution**: Top authors based on the number of retweets received.
- **Hashtag Popularity**: Bar chart of the top 10 hashtags based on likes and retweets.
- **Journal Topic Analysis**: Pie chart of the top topics (hashtags) discussed by the top 10 journals.
- **Hashtags by Country**: Pie chart of the most popular hashtags in different countries.

## Libraries Used
- **Pandas**: For data manipulation and analysis.
- **Matplotlib**: For data visualization.
- **Re**: For regular expressions and text cleaning.
- **Transformers**: For sentiment analysis, NER, translation, and zero-shot classification.

## Instructions to Run the Project

1. Clone the repository:
   ```bash
   git clone https://github.com/MaroZayn/multilingual-analysis-and-tweet-processing-with-nlp.git
2. Installez les dépendances requises :
   ```bash
   pip install -r requirements.txt
3. Run the Jupyter Notebook to execute the analysis:
   ```bash
   jupyter notebook tweet_analysis.ipynb

## Conclusion

This project combines multiple stages of data analysis: cleaning, visualization, sentiment analysis, named entity recognition, text translation, and topic classification. It demonstrates how to handle tweet data, extract meaningful insights, and present the results through visualizations.
