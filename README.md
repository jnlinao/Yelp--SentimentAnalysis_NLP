# Yelp Reviews Sentiment Analysis :stew:            
<img src="/images/logo.png" width="150" height="100">

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
We use TF-IDF and bi-grams to get the frequency of two terms with our max features at 12,500. Next, we incorporate SVD by decomposing the matrix into three constituent matrices setting the number of components to 5, iterating through it 100 times. In [Figure 1](#Figure-1) can visualize the singular values and their relative importance of each component and the amount of variation captured from each concept.

## Project Visualizations
[Figure 1](#Figure-1)
### Figure 1

