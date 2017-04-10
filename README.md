# data_science_class

# Background
After doing product for an iOS app with recommendations relying on machine learning, I wanted to learn more about the advantages and limitations of the various models. 

# Challenge
The data science evening class I took included a final project. The challenge I chose for the project was “Given historical data from the Game of Thrones books, can we predict who is likely to die next?”   

# Approach
I found a CSV on Kaggle.com of historical data of the fictional land (the books go into great detail).  Features included: “is alive”, “married”, “single”, “has dead brothers/sisters”, a made up popularity score (based on inbound links to the character’s wiki page), and the house each person belonged to. I did an exploratory data analysis using python and pandas, plotted charts in matplot lib, and applied a few machine learning models.

# Metrics 
I had a feature labeled “is alive”. If the character was alive (or resurrected) by the end of the 5th book, he or she was counted as “alive”. I dropped that column from my training data, and used it as an answer key to score how well each machine learning model predicted. 

To find who was most likely to die *next* I looked at characters who were alive, but the model predicted dead. The TV show was about to surpass the 5th book, which gave me a chance to see if *predicted deaths* (based on book data) matched who *actually died* in the new TV episodes.   

# Outcome
The best model (random forest) did correctly predict some surprising deaths! 

The exploratory analysis resulted in some interstesting insights, too. Check out the ipython notebook for which houses are “winning” the staying alive game, and whether chances of survival are better for are married or single characters. My favorite insight is - despite what George R. R. Martin says about not keeping certain characters alive, I found characters in the top 10% of popularity had a much greater chance of being alive than those less popular. Intuitively this makes sense -  readers and viewers have “skin in the game” and higher engagement if they have a few heros to follow through trials and triumph than if all the main characters died off every 3 chapters or episodes and we had to constantly adapt to new back stories.      



Below is a list of topics we covered in the night class.

TOPICS
Intro to Data Science
Introduction to Git
Pandas
APIs
Web Scraping 101
Intro to Machine Learning
KNN
Scikit-learn
Model Evaluation
Linear Regression
Logistic Regression
Time Series Data
Review (using SF Crime Data Lab)
Clustering
Natural Language Processing
Naive Bayes
Decision Trees
Ensembling Techniques
Dimension Reduction
Web Development with Flask
Recommendation Engines 
Support Vector Machines
Neural Networks
Projects

