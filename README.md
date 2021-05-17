# Sentiment Analysis Project 
## Jacob Linao
Sentiment analysis is a vital technique in which we will be classifying the review text as either positive or negative by incorporating aspects of Natural Language Processing (NLP) and machine learning. Specifically, we will conduct logistic regression and determine the sentiment based upon the evaluation of a restaurant review. From the Yelp review data, consumers discuss their experiences and opinions through their reviews, thus natural language processing and sentiment analysis can be utilized. Ultimately, a review is what the opinion of the user is about the business in his or her own words and not a rating or mathematical predictive task, thus, it is essential to be able to predict what the user feels about a business from the review text (Channapragada & Shivaswamy, 2015, p. 1) [1]. In this project, we conduct data preprocessing, topic modeling, exploratory descriptive analytics, modeling, results and conclusions. Overall, sentiment analysis can help understand consumers as a whole; detecting business’ day-to-day successes and faults, and remedying them over time. 

```python
chunk_list = []
for chunk_review in reviews:
    # Renaming column name to avoid conflict with business overall star rating
    chunk_review = chunk_review.rename(columns={'stars': 'review_stars'})
    # Inner merge with edited business file so only reviews related to the business remain
    chunk_merged = pd.merge(df_b, chunk_review, on='business_id', how='inner')
    # Show progress
    print(f"{chunk_merged.shape[0]} out of {size:,} related reviews")
    chunk_list.append(chunk_merged)
# After trimming down the review file, concatenate all relevant data back to one dataframe
df_b = pd.concat(chunk_list, ignore_index=True, join='outer', axis=0)
```
