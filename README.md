<H3>NAME - THAANESH V </H3>
<H3>REGISTER NO - 212223230228</H3>

<H1 Align="center">Project Based Experiment<H1>
<H3>Objective:<H3>
The objective of this project is to analyze Facebook post comments or feedback using sentiment analysis and filter only those entries that have positive sentiment. This helps in understanding user engagement and extracting constructive insights from social media data.
<H3>Program:</H3>
  
```
import pandas as pd
from textblob import TextBlob
import matplotlib.pyplot as plt
```
  
### Step 1: Load Facebook data (CSV format)
```
data = pd.read_csv("facebook_data.csv")
```
### Step 2: Sentiment analysis function
```
def get_sentiment(text):
    analysis = TextBlob(str(text))
    if analysis.sentiment.polarity > 0:
        return "Positive"
    elif analysis.sentiment.polarity < 0:
        return "Negative"
    else:
        return "Neutral"
```
### Step 3: Apply sentiment function to each comment
```
data['Sentiment'] = data['comment'].apply(get_sentiment)
```
### Step 4: Filter only Positive feedback
```
positive_feedback = data[data['Sentiment'] == "Positive"]
```
### Step 5: Save to a new CSV
```
positive_feedback.to_csv("positive_feedback.csv", index=False)
```
### Step 6: Visualization - Bar chart of sentiment distribution
```
sentiment_counts = data['Sentiment'].value_counts()
plt.bar(sentiment_counts.index, sentiment_counts.values)
plt.title("Facebook Comments Sentiment Distribution")
plt.xlabel("Sentiment")
plt.ylabel("Number of Comments")
plt.show()
```
### Step 7: Display some positive comments
```
print("Sample Positive Feedback:")
print(positive_feedback.head(5))
```
<H3>Output:</H3>
<img width="734" height="670" alt="image" src="https://github.com/user-attachments/assets/94e76bfd-5b4a-42f8-8740-ed9ec9094b48" />

<H3>Inference:</H3>
In this project, I learned how to use Python to perform basic sentiment analysis on text data. I was able to classify comments as positive, negative, or neutral and filter out the positive feedback. This helped me get hands-on practice with Python libraries like pandas and TextBlob and understand how sentiment analysis works on social media data.
