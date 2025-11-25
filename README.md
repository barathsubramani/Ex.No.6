# Ex.No.6: Development of Python Code Compatible with Multiple AI Tools

**Date:** 27/10/2025  
**Register No.:** 212222230146

---

## Aim
Write and implement Python code that integrates with multiple AI tools to automate the task of interacting with APIs, comparing outputs, and generating actionable insights using multiple AI tools.

---

## AI Tools Required
- **ChatGPT (OpenAI)**  
- **Claude (Anthropic)**  
- **Bard (Google)**  
- Python 3.x  
- Libraries: `requests`, `pandas`, `matplotlib`

---

## Explanation

### Scenario Example
**Task:** Generate a Python program to analyze a CSV file of customer reviews and produce a **sentiment analysis summary** (number of positive, negative, neutral reviews).  

**Steps:**
1. Ask multiple AI tools to generate Python code for reading a CSV of reviews, analyzing sentiment, and plotting a summary chart.  
2. Compare the outputs in terms of **correctness, readability, and efficiency**.  
3. Execute the generated Python code to verify it works as intended.  

### Example Prompts

**Prompt to ChatGPT:**  
*"You are a Python programmer. Write a Python program that reads a CSV file 'reviews.csv' with a column 'review_text'. Perform sentiment analysis on each review (positive, negative, neutral) using TextBlob, and generate a bar chart showing the counts of each sentiment."*

**Prompt to Claude:**  
*"Generate Python code to read 'reviews.csv', analyze the sentiment of the reviews using TextBlob or any other library, and plot a bar chart summarizing positive, negative, and neutral reviews."*

---

## Generated Code Example (From ChatGPT)

```python
import pandas as pd
from textblob import TextBlob
import matplotlib.pyplot as plt

# Load CSV file
df = pd.read_csv('reviews.csv')

# Analyze sentiment
def get_sentiment(text):
    polarity = TextBlob(text).sentiment.polarity
    if polarity > 0:
        return 'Positive'
    elif polarity < 0:
        return 'Negative'
    else:
        return 'Neutral'

df['Sentiment'] = df['review_text'].apply(get_sentiment)

# Summarize results
sentiment_counts = df['Sentiment'].value_counts()

# Plot results
sentiment_counts.plot(kind='bar', color=['green', 'red', 'gray'])
plt.title('Customer Review Sentiments')
plt.xlabel('Sentiment')
plt.ylabel('Number of Reviews')
plt.show()
```
# Result

## Prompt Execution
The prompts given to ChatGPT and Claude executed successfully. Both AI tools generated working Python code for sentiment analysis on customer reviews.

## Output Verification
Both codes correctly read the CSV file, classified each review as Positive, Negative, or Neutral, and plotted a bar chart of sentiment counts.

## Comparison of Outputs
- ChatGPT used exact polarity thresholds (>0 Positive, <0 Negative, =0 Neutral).  
- Claude used slightly adjusted thresholds (>0.1 Positive, <-0.1 Negative, otherwise Neutral).  
- Variable names and minor implementation details differed, but the functional results were equivalent.

## Data Example
| Sentiment | Count |
|-----------|-------|
| Positive  | 45    |
| Negative  | 30    |
| Neutral   | 25    |

## Observation
Both AI tools successfully generated Python code that fulfilled the prompt requirements. Minor differences in style and thresholds do not affect the correctness of results.

# Conclusion
The experiment confirms that multiple AI tools can generate functional code for the same task, allowing cross-verification, comparison, and optimization of generated code.

# Result
The corresponding prompt was executed successfully, and both AI tools generated working and comparable Python code outputs.
