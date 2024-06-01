SETUP:

Install PRAW api: pip install praw pandas
Install Natural Language Toolkit: pip install nltk
Install OpenAI api: pip install openai

Develop a script to scrape Reddit posts and comments from specific subreddits related to health conditions relevant to the clinical trial.

The subreddits considered for the dataset  :
r/BodyDysmorphia : https://www.reddit.com/r/BodyDysmorphia/
r/Fibromyalgia: https://www.reddit.com/r/Fibromyalgia/
r/rarediseases: https://www.reddit.com/r/rarediseases/
r/Celiac: https://www.reddit.com/r/Celiac/
r/clinicaltrials: https://www.reddit.com/r/clinicaltrials/
r/clinicalresearch: https://www.reddit.com/r/clinicalresearch/new/
r/FindClinTrial: https://www.reddit.com/r/FindClinTrial/
r/health: https://www.reddit.com/r/Health/
r/ AskDocs: https://www.reddit.com/r/AskDocs/

The dataset in dataset.csv consists of 6556 entries with the following columns:
Text: Reddit post/ comment content
Score: Number of upvotes for each post/ comment
Cleaned_text: Preprocessed text
Emotion detected: Sentiment analysis of the text

Perform sentiment analysis on the scraped data to determine the general attitude and interest levels regarding clinical trials.

Preprocess the text using the following:
Remove URLs and user mentions
Remove special characters, numbers, punctuations
Convert text to lowercase
Split comments into individual words
Remove stopwords
Convert words to their base form

I’ve made use of transfer learning for the sentiment analysis part of the assignment. Google's T5 is an encoder-decoder model and converts all NLP problems into a text-to-text format. The model is finetuned to the dataset: https://huggingface.co/datasets/dair-ai/emotion where the model is trained on 16k entries and tested on around 2k entries that classifies the comment into one of the following emotions: anger, fear, joy, love, sadness, surprise. 
The bar chart shows the setiment vs the percentge of entries with the sentiment. The visualization shows a positive opinion and receptiveness towards clinical trials.



Use the OpenAI API to generate personalized messages aimed at users who express interest in or could potentially benefit from participating in a clinical trial.

I tried to use the OpenAI API to generate personalized message based on the text and the sentiment associated with the comment but the API rate limit was exceeded. I couldn’t execute the third part of the assignment due to limit of system resources. 
