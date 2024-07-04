# Introduction
The project performs approaches, give insights and make decisions with **sentiment analysis**. More specifically, we collect and analyze YouTube comments related to the TED Talk video: “[Elon Musk: The future we're building -- and boring](https://www.youtube.com/watch?v=zIwLWfaAg-8)”, then perform sentiment analysis visualizations. The primary objective is to gain a comprehensive understanding of audience reactions and discussions towards Elon Musk's discussion by analyzing user comments. The project involves the following steps: scraping comments from YouTube, preprocessing the text data, performing sentiment analysis (NRC, Vader and TextBlob), generating n-grams, and visualizing the results through network graphs and charts. 

# Steps
**1. Web-scrapping data on youtube**

We use Selenium to automate the navigation and extraction of comments from YouTube video pages. This task required handling dynamically loaded content and managing pop-ups like cookie consent to ensure smooth data extraction. By successfully scraping user comments, we obtained valuable textual data for further analysis.

**2. Data preparation**

We cleaned and preprocessed the scraped data to make it ready for analysis. This involved tokenizing the text data, breaking down comments into individual words or tokens. We generated bigrams to capture pairs of consecutive words, providing more context than single words. Additionally, we counted the frequency of these bigrams to identify common phrases or patterns in the comments. The data preparation phase ensured that our data was free from errors, inconsistencies, and irrelevant content, making it suitable for sentiment analysis.

**3. Sentiment analysis and visualization**

**3.1 NRC**

The NRC (National Research Council Canada) Emotion Lexicon was utilized to categorize words in YouTube comments into various emotions and sentiment categories. This lexicon-based approach assigns words to different emotional categories, such as joy, anger, sadness, and fear, as well as broader sentiment categories like positive and negative. By applying the NRC lexicon to each comment, we were able to quantify the emotional content and sentiment of the comments. For example, if a large proportion of comments were categorized under emotions like joy and anticipation, it indicated a positive and excited reaction to the video. Conversely, a higher frequency of emotions such as anger or sadness would point to negative feedback or dissatisfaction.
    
**3.2 Vader**

We analyze the sentiment of short texts from scrapped-clean data. It combines a lexicon of words with associated sentiment scores and a set of rules to evaluate the sentiment more accurately. For example, if the majority of comments had high positive scores and compound scores above 0.5, it indicated a generally positive reception to the video content. The visualization of sentiment scores allowed us to see the distribution and intensity of sentiments, showing not only the direction (positive or negative) but also how strongly the sentiments were expressed.

**3.3 TextBlob**

TextBlob provides two key metrics for sentiment analysis: polarity and subjectivity. Polarity measures the sentiment on a scale from -1 (most negative) to +1 (most positive), while subjectivity indicates how subjective or opinionated the text is, ranging from 0 (most objective) to 1 (most subjective). TextBlob was applied to each comment to calculate these scores, which were then analyzed and visualized to gain insights into the sentiment and subjectivity of the comments. For instance, if the average polarity score of the comments was significantly positive, it suggested that viewers generally had a favorable opinion of the video. The subjectivity scores helped us understand how personal or opinionated the comments were, with higher subjectivity indicating more personal and subjective comments. By visualizing the polarity and subjectivity scores, we were able to identify the overall sentiment trend and the degree of subjectivity in the comments.

**3.4 ML supported approach (Logistic Regression)**

The ML enhances the depth and accuracy of analysis, providing more meaningful insights into audience reactions to Elon Musk's TED Talk. This comprehensive approach ensures that our findings are robust and actionable, offering significant value to the analysis. The ML model demonstrated balanced performance (71%) across both positive and negative sentiment classes. This indicates that the model is equally effective at identifying positive and negative comments, which is crucial for a fair sentiment analysis.

# How to run the project
1. Go to root directory of the project
2. Install/upgrade required python **libraries**
    ```sh
    pip install -r requirements.txt
    ```
3. Run **data_scarpper.ipynb** to get web-scrapping data and create .csv dataset
    ```sh
    py data_scrapper.ipynb
    ```
4. Run **data_preparation.ipynb** to clean data and plot comments
    ```sh
    py data_preparation.ipynb 
    ```
5. Run **sentiment_analysis.ipynb** to perfom NRC, Vader and TextBlob analysis, and visualization, and Logistic Regression
    ```sh
    py sentiment_analysis.ipynb 
    ```

