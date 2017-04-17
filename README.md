# Exploring New Use Cases for Machine Learning

# Background
This repository contains a machine learning side project I did. From being a PM on a recommendations app relying on machine learning, I got curious about what was happening "under the hood" with the algorithms.

My primary objective for this project was to test limitations of ML models and metrics. Given my product background, I was curious what problems ML can and can not solve - both today, and in the future. Therefore, I chose a problem that seemed likely impossible, or at the least very challenging, to solve with machine learning. Storytelling is a highly creative process. We know machines can write stories, but many algorithmically-generated stories are uninteresting and/or nonsensical. How close are are we really to machines writing stories that we'd actually *want* to read? 

# Challenge
Given labeled data and the mental model of fans, I wanted to explore if a machine could predict the plot of a compelling story. The challenge I chose for this project was: “Given historical data from the Game of Thrones books, can we use machine learning to predict who is likely to die next?”. Here is the analytical approach I used.              

# Approach
The steps I followed were: acquire data, look for insights and patterns with an exploratory data analysis, split data into training and test sets, apply machine learning models, score each model, and compare results across models. Below is more detail on the process.   

Data Acquisition: 
To get data my options were: read each book (or watch each episode) and take detailed notes - or look for an existing set of labeled data. I found a wikipedia style website with detailed historical data. Another curious fan had crawled this wiki, made a CSV with various features for a different analysis, and posted the CSV on Kaggle.com. This gave me a labeled data set with information relevant to answering my question.  

Data Analysis:
Features in the data set included: “is alive”, “married”, “single”, “has dead brothers/sisters”, a made up popularity score (based on inbound links to the character’s wiki page), and the house each character belonged to. I did an exploratory data analysis using python and pandas and plotted charts in matplot lib. 

The exploratory analysis resulted in some interstesting insights. Certain houses are “winning” the staying alive game. Chances of survival are better for unmarried characters. My favorite insight is - despite what George R. R. Martin says about not keeping certain characters alive, I found characters in the top percentile of popularity had a significantly improved liklihood of being alive than those less popular. Intuitively this makes sense -  readers and viewers have “skin in the game” and higher engagement if they have a few heros to follow through trials and triumph. The story would be less compelling if all the main characters died off every chapter or episode and a whole new cast was introduced.   

Modeling:
Of the two primary types of machine learning models: supervised and unsupervised, I chose supervised learning models since I had a labeled response for the feature I wanted to predict. If the character was alive by the end of the 5th book, she was counted as “alive”. I dropped that column from my training data, and used it as an answer key to compare how well each machine learning model predicted. I started with a simple model first (Logistic Regression) before trying more complex models like Naive Bayes, Decision Trees, and Random Forest.  

# Metrics 
To find who was most likely to die *next* I looked at characters who were alive, but the model predicted dead. The TV show was about to surpass the 5th book, which gave me a chance to see if *predicted deaths* (based on book data) matched who *actually died* in the new TV episodes. 

# Outcome
The best model (random forest) did correctly predict the surprising death of Tommen Baratheon.

There are several limitations to the models. 
a. Books vs TV series: The model predictions are based off book data, so it does not account for characters who are alive in the books but have died in the TV series. For example, Stannis was among the predicted next to die, but in the TV show he had already died. 
b. Updating Predictions: As the story progresses more characters will die. The model currently uses the snapshot of the end of the 5th book, but could be modified to make more predictions as time goes on.
c. Resurrection: Since resurrection is an edge case, the model currently does not track how many times a character dies. Resurrected characters are counted as alive.    
