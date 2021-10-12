# Yelp Reviews Sentiment Analysis :stew:            
<img src="/images/logo.png" width="225" height="125">

### Use Case: Utilizing consumer reviews to develop data-driven insights for restaurants on how to improve their business during Covid-19

## Business Problem :thought_balloon:
Covid-19 challenged many people on a global scale, especially businesses and their operations. Business owners who have significantly struggled are restuarant owners. The new landscape has pushed restaurants to make changes to their businesses such as the new emphasis on takeout orders. Because it is vital to be adaptable, restaurants must understand new novel internal trends within their business in order to survive. 

Consumers discuss their experiences and opinions through their Yelp reviews, making it a valuable resource for identifying areas of strengths as well as critical pain points. **Ultimately, sentiment analysis through NLP modeling can help understand consumers as a whole by detecting business’ day-to-day successes and faults, and remedying them over time.**




## Data Challenges and Approach :mount_fuji:
1. How can we get the data we need?
  * **Web-scraped data from Yelp website using BeautifulSoup and Selenium to retrieve 10,000+ reviews.**
2. How can we model text data? 
* **Employ text preprocessing such as vectorization, tokenization, stopwords filtering, lemmatization, Count Vectorizer, and TFIDF. Evaluation for number of features and parameters (min/max df,n-grams).**
3. What machine learning model will best fit our use case: using textual features to predict customer sentiment?
* **Evaluated model performance for logistic regression and conducted grid-search for parameter optimization.**
4. What data insights can we present to stakeholders?
* **Conduct topic modeling to identify important topic focuses of business and develop sentiment prediction model to assign positive/negative labels and segment reviews to augment found topics.**

 
## Project Findings :mag_right:
### Latent Semantic Analysis (LSA)
We use TF-IDF and bi-grams to get the frequency of two terms with our max features at 12,500. Next, we incorporate SVD by decomposing the matrix into three constituent matrices setting the number of components to 5, iterating through it 100 times. In [Figure 1](#figure-1), we can visualize the singular values and their relative importance of each component and the amount of variation captured from each concept. 

### Feature Importance
We conduct feature importance for the purpose of gaining insights into the data and as well as the model. The implementation of feature importance assigns scores to input features based on how impactful they are at predicting a target variable. This is done by splitting the coefficients from the classifier into positive and negative features and plotting them to see their impacts on positive or negative sentiments. From the top positive and negative words, the most important features are labeled with scores on the y-axis. From [Figure 2](#figure-2), two of the most important features are “definite back” and “highly recommend”. These inform Japanese-style restaurant owners that when positive experiences are had, consumers are more likely to return or spread their positive experiences with their communities which can be a form of free advertising by word-of-mouth. 

From [Figure 3](#figure-3), the opposite can be informed. Words like “won’t back” and “never come” inform Japanese-style restaurant owners that consumers with negative experiences will not return and that they may spread those negative experiences with their communities which results in negative advertising by word-of-mouth. It can also be seen that “food poisoning” and “service horrible” are aspects that are highly correlated to negative sentiments. Japanese-style restaurant owners can adjust their business to steer away from these aspects.

### Model Evaluation
Accuracy answers the question: “Out of all the classes, how much did we predict correctly?”. Recall measures how much the model was able to predict correctly out of all the positive classes; a high value is desirable. Precision measures how much actual positive predictions were made from all the correct positive class predictions. The F1-measure allows the ability to measure both precision and recall simultaneously. These measures along with the classification report are provided in [Table 1](#table-1) and [Table 2](#table-2) respectively.

Another important performance indicator is known as the AUC-ROC curves, shown in [Figure 4](#figure-4). ROC is defined as a probability curve that plots the True Positive Rate (TPR) on the xaxis against the False Positive Rate (FPR) on the y-axis. The AUC conveys the model’s capability of classifying the distinction between classes. A higher AUC that's close to 1 represents a more effective model in predicting the sentiment between negative and positive. The model produced very good results with the overall accuracy of the model being 90%. The recall score is also very high at 96%, denoting that our model is able correctly identify positive classes. Finally, the F- 1 score at 93% conveys that the model is able to correctly predict positive classes very well. Looking at the classification report, we see that there are 22,304 occurrences of the positive class and only 7,341 of the negative class, even despite assigning the neutral star rating reviews to negative sentiment. We expected this imbalance of distribution of classes from exploratory analytics, as most of the reviews for these Las Vegas restaurants were positive. Ultimately, this is a concern as unbalanced support in the data may prove a weakness and could possibly necessitate resampling or further feature extraction. By acknowledging our AUC score of 0.949 and its closeness to 1, we interpret this as a very good measure of separability, meaning there is a 95% chance the model will be able to distinguish between the two classes.

### Business Recommendations
Throughout our analysis, we found that our sentiment words were more positive than negative of Yelp users' experiences at the designated restaurants. In relation to the positive sentiments of users, we can display a positive correlation between that of positive reviews with high ratings, and negative reviews with lower ratings. From segmenting the area to Las Vegas and categorizing off of Japanese restaurants, we gain insight on how they operate as a whole. Each of the individual users provide their opinions throughout their reviews; as the positive outweighs the negative, Japanese restaurants are providing great dining services and food to their customers, which increases the positivity disclosed in their review, as well as an input of a higher rating. Although, through this project, Japanese restaurant owners can also view aspects that drive more negative sentiments which they can take initiative on and remedy over time.


## Project Visualizations

### Figure 1

### Figure 2

### Figure 3

### Figure 4

### Table 1

### Table 2

