# Course Project


## Overview

By Megan O’Rorke
-----------
* Problem statement and hypothesis
I’m planning to find insights about deaths in the TV series Game of Thrones (GOT). 
- Which house has the most characters? 
- What's the ratio of alive vs dead per house?
- Which house has the highest proportion of deaths?
- Is there a relationship between survival and popularity? 
- Is there a relationship between survial and marriage? 
- Is there a relationship between survial and being noble? 
-----------
* Description of your data set and how it was obtained
Battles, character-deaths, character-predictions CSV files from Kaggle. 
-----------
* Description of any pre-processing steps you took
I took a subset of the character-predictions file and created character-predictions-9.csv. I removed the non-major houses and a few of the columns. 
-----------
* What you learned from exploring the data, including visualizations
Night's Watch has the most characters. 
Night's Watch and Targaryen have the most dead.
Targaryens have the highest proportion of deaths. 
A higher proportion of popular characters die
More of the dead characters were married than single. 
More of the dead characters were noble. 
-----------
* How you chose which features to use in your analysis
The original data set had 33 features. I took out whether spouse/father/heir/mother are alive, who the spouse/heir/father/mother is, date of birth/death, culture and title. There was previous analysis on culture and age, and I wanted to do my analysis on features that hadn’t been explored yet. I left ID#, house, books character appeared in, married, noble, dead relatives, dead spouse, whether they’re alive or dead, male or female and popularity.   
-----------
* Details of your modeling process, including how you selected your models and validated them
Next steps: 
Plot bar graphs
Linear regression - gender, house features. 
Decision tree
Random forrest
KandN - colors red if dead, green if alive.
-----------
* Your challenges and successes
Challenge: Programmatically cleaning the data. I’m new to that part. 
Successes: After I got the first chart, it was pretty simple fun to set up subsequent ones. 
-----------
* Possible extensions or business applications of your project
Not sure there’s a biz model here, but it’s a fun data set to explore! Should make for an entertaining presentation. 
-----------
* Conclusions and key learnings
If you’re a character in GOT, don’t be in the Night’s Watch or get married. :)
-----------
Initially tried out with model X, got this prediction. 
Can I make a better prediction? 
Dunno, not there yet. 