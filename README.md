# Game of Thrones Death Predictor
#### Exploring Use Cases for Machine Learning in Fiction

## Overview
This model predicts who is most likely to die next on Game of Thrones (GOT). It uses data sourced from the GOT wiki, and makes a prediction for a snapshot in time - the end of the 5th book. Several possible models are explored and contrasted including Logistic Regression, Naive Bayes, Decision Trees, and Random Forest.  

The primary objective for this project was to explore limitations of applying ML to use cases like storytelling. We know machines can write stories, but many algorithmically-generated stories are uninteresting and/or nonsensical. How close are are we really to machines writing stories that we'd actually *want* to read? 
         
## Approach
The steps I followed were: acquire data, look for insights and patterns with an exploratory data analysis, split data into training and test sets, apply machine learning models, score each model, and compare results across models. Below is more detail on the process.   

### Data Acquisition: 
Thankfully I didn’t need to take detailed notes on each book - there was an existing set of labeled data. Another curious fan had crawled the GOT wiki and exported several features into a CSV. This gave me a labeled data set with information relevant to answering my question.  

### Data Analysis:
Features in the data set included: “is alive”, “married”, “single”, “has dead brothers/sisters”, a made up popularity score (based on inbound links to the character’s wiki page), and the house each character belonged to. I did an exploratory analysis using python, pandas and matplotlib. 

The exploratory analysis resulted in some interesting insights. Certain houses are “winning” the staying alive game. Chances of survival are better for unmarried characters. My favorite insight is - despite what George R. R. Martin says about not keeping certain characters alive, I found characters in the top percentile of popularity had a significantly improved likelihood of being alive than those less popular. Intuitively this makes sense -  readers and viewers will be more engaged if they have familiar faces to root for. The story would be less compelling if all the main characters died off every chapter or episode and a whole new cast was introduced.   

## Modeling:
I chose supervised learning models since I had a labeled response for the feature I wanted to predict. If the character was alive by the end of the 5th book, they were counted as “alive”. I dropped that column from my training data, and used it as an answer key to compare how well each machine learning model predicted. I started with a simple model first (Logistic Regression) before trying more complex models like Naive Bayes, Decision Trees, and Random Forest.  

## Metrics 
To find who was most likely to die *next* I looked at characters who were alive, but the model predicted dead. The TV show was about to surpass the 5th book, which gave me a chance to see if *predicted deaths* (based on book data) matched who *actually died* in the new TV episodes. 

## Outcome
The best model (random forest) did correctly predict the surprising death of Tommen Baratheon.

## Limitations
There are several limitations to this kind of model. 
-  Generalizability: One of the most helpful features for predicting death was the popularity score, so if you wanted to use a model like this to win bets with friends about another fantasy series that doesn’t have an extensive online wiki dedicated to it that might not work so well. 
-  Books vs TV series: The model is trained on book data, and the TV series differs from the books. The model does not account for characters who have died in the TV series, but are still alive in the book series. For example, Stannis was among those predicted next to die, but in the TV show he had already died. 
-  Snapshot in Time: As the story progresses more characters will die. The model currently uses the snapshot of the end of the 5th book.
-  Resurrection: Since resurrection is an edge case, the model currently does not track how many times a character dies. Characters who come back from the dead by the end of the 5th book are counted as alive.    

## Future Work
- Iterate on the model: I used basic ML models here since I wanted a high level of explainability and insight into which features impacted predictions. There’s certainly more complex approaches that could be applied and feature engineering that could be done.
- Moving Window: The model could make predictions for different time periods of the story.
- Increase Generalizability: It’d be interesting to try building a generalized plot predictor that performed well across many different fantasy series. 
- What about the animals? The source data didn’t include direwolves, but if you add pet data let me know what you find. :)
- Push to Production: Right now the model lives on my laptop, but it could be turned into an interactive app. 
