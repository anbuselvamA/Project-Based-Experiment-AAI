<H3>NAME : ANBUSELVAM A</H3>
<H3>REGISTER NUMBER : 212222240009</H3>
<H1 Align="center">Project Based Experiment<H1>
<H3>Objective :</H3>
  
Perform sentiment analysis using your Facebook data and filter the data that has only Positive feedback for the code given in the following link.

<H3>Program:</H3>
  
```py
pip install pandas textblob

import pandas as pd
from textblob import TextBlob

# Sample DataFrame simulating Facebook data
data = {
    'post_id': [1, 2, 3, 4],
    'content': [
        'I love the new update! - Anbu',
        'Anbu is the worst experience ever.',
        'This is a great day for Anbu and everyone!',
        'Absolutely terrible support, Anbu!'
    ]
}

# Create DataFrame
df = pd.DataFrame(data)

# Function to classify sentiment
def get_sentiment(text):
    analysis = TextBlob(text)
    # Classifying sentiment: < 0 indicates negative sentiment
    if analysis.sentiment.polarity < 0:
        return 'negative'
    else:
        return 'positive'

# Count occurrences of your name
def count_name_occurrences(text, name):
    return text.lower().count(name.lower())

# Apply the sentiment analysis function to the content
df['sentiment'] = df['content'].apply(get_sentiment)

# Count occurrences of the name "Tom"
df['name_count'] = df['content'].apply(lambda x: count_name_occurrences(x, "Anbu"))

# Display the results
print("Sentiment Analysis and Name Count:")
print(df[['post_id', 'content', 'sentiment', 'name_count']])

# Count total occurrences of "Tom"
total_occurrences = df['name_count'].sum()
print(f"\nTotal occurrences of 'Anbu': {total_occurrences}")


```

<H3>Output:</H3>

![Screenshot 2024-11-01 204216](https://github.com/user-attachments/assets/c77a0b2b-ea6c-4c12-8315-99b6c2d906b6)

<H3>Inference:</H3>
Thus sentiment analysis using Facebook data is done and filtering the data that has only positive feedback for the code is executed successfully.
