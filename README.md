## SETUP:

Install PRAW api: pip install praw pandas<br>
Install Natural Language Toolkit: pip install nltk<br>
Install OpenAI api: pip install openai<br>

## Develop a script to scrape Reddit posts and comments from specific subreddits related to health conditions relevant to the clinical trial.

The subreddits considered for the dataset  : <br>
r/BodyDysmorphia : https://www.reddit.com/r/BodyDysmorphia/<br>
r/Fibromyalgia: https://www.reddit.com/r/Fibromyalgia/<br>
r/rarediseases: https://www.reddit.com/r/rarediseases/<br>
r/Celiac: https://www.reddit.com/r/Celiac/<br>
r/clinicaltrials: https://www.reddit.com/r/clinicaltrials/<br>
r/clinicalresearch: https://www.reddit.com/r/clinicalresearch/new/<br>
r/FindClinTrial: https://www.reddit.com/r/FindClinTrial/<br>
r/health: https://www.reddit.com/r/Health/<br>
r/ AskDocs: https://www.reddit.com/r/AskDocs/<br>

The dataset in dataset.csv consists of 6556 entries with the following columns:<br>
Text: Reddit post/ comment content<br>
Score: Number of upvotes for each post/ comment<br>
Cleaned_text: Preprocessed text<br>
Emotion detected: Sentiment analysis of the text<br>

## Perform sentiment analysis on the scraped data to determine the general attitude and interest levels regarding clinical trials.

Preprocess the text using the following:<br>
Remove URLs and user mentions<br>
Remove special characters, numbers, punctuations<br>
Convert text to lowercase<br>
Split comments into individual words<br>
Remove stopwords<br>
Convert words to their base form<br>

I’ve made use of transfer learning for the sentiment analysis part of the assignment. Google's T5 is an encoder-decoder model and converts all NLP problems into a text-to-text format. The model is finetuned to the dataset: https://huggingface.co/datasets/dair-ai/emotion where the model is trained on 16k entries and tested on around 2k entries that classifies the comment into one of the following emotions: anger, fear, joy, love, sadness, surprise. <br>
The bar chart shows the setiment vs the percentge of entries with the sentiment. The visualization shows a positive opinion and receptiveness towards clinical trials.

## Use the OpenAI API to generate personalized messages aimed at users who express interest in or could potentially benefit from participating in a clinical trial.

I tried to use the OpenAI API to generate personalized message based on the text and the sentiment associated with the comment but the API rate limit was exceeded. I couldn’t execute the third part of the assignment due to limit of system resources. 
