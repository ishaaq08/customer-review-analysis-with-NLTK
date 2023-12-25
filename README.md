# About the Project

- This project invovled scraping customer reviews from eBay and extracting the sentiment of the review which was provided by the customer rating - 'positive' or 'negative'.
- Python's Natural Language Tool Kit (NLTK) VADER model was then employed to analyse the text review and determine the sentiment.
- Finally, the positive/negative rating provided by the customer, outlining the sentiment of the review, was then compared to the sentiment determined by the VADER model.

# Methodology

 ### Web scrape using BeautifulSoup 
- The BeautifulSoup library was used to scrape the relevant data from the web page.
- There were multiple dynamically rendered pages containing the reviews, thus a library such as Selenium which can be used to interact with web pages would be required, however this was beyond the scope of this project.
- Instead only the reviews listed on the first page were extracted.
 
 ### Store data in a pandas DataFrame and clean it 
 - To enhance the data analysis process the data was transformed from lists to a DataFrame. This allowed for the adding of additional columns such as the VADER score.
 
 ### Analyse customer reviews using the VADER model
 - The customer reviews were then passed into the VADER model's Sentiment Intensity Analyser which outputs a dictionary containing 4 keys: positive, negative, neutral and compound score.
 - The compound score was of focus here as it's value determines whether a piece of text has a positive, negative or neutral sentiment.
 - A new column in the DataFrame was created to store the compound score.
 - An additional column was created that outputs the text 'positive', 'negative' or 'neutral' depending on the compound score.
 
 ### Visualize results through matplotlib
 - 2 sets of bar plots were created with the x axis displaying the rating and the y axis displaying the count. 1 bar plot for the actual ratings and the other for the NLTK results.
 - A pie chart was also created displaying how many of the VADER results matched with the actual customer ratings.

# Conclusions

- 76% of the NLTK results matched with the actual 'positive' or 'negative' rating provided by the customer.
- NLTK results - 18 positive, 7 neutral, 0 negative.
- Actual results - 24 positive, 1 neutral, 0 negative.
- Most of the discrepancies existed where the customer gave a positive rating but left a review of 'as described' or 'turned up as described' - it is valid for the model to classify these ratings as neutral. Also, in some instances the customer gave a positive rating but left a review of 'A++++', in this instance it is also fair for the model to classify the result as 'Neutral'

Ultimately, the VADER model proved to be accurate in capturing the general sentiment trend found within the customer reviews. 




