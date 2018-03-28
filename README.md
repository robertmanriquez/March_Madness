# March_Madness

Machine Learning models and data manipulation for predicting a bracket for the 2018 NCAA March Madness tournament.

Every year, Kaggle hosts a competition to see who can make the most accurate predictions (graded on logloss) for every possible matchup of the 351 Men's College Basketball teams.  Only 68 make it to the finals, and only one team can be the champions!  The contest is available [here](https://www.kaggle.com/c/mens-machine-learning-competition-2018), which includes all of the data and documentation.

My strategy was to consider the average game stats for each team from only 2 years prior as features, including their team seeds, and scraping Basketball Power Index (BPI) rankings off of [ESPN's website](http://www.espn.com/mens-college-basketball/bpi)  Once my data was processed, I decided that my Random Forest Classifier model performed the best out after screening with LogReg, KNN, and DecTreeClassifier.  I also liked using Random Forest for it's "white box" approach that allows the user to see feature importances and an actual example decision tree using sklearn's graphviz functions.

Using a few handy packages for visualizations, I was able to make my own bracket to follow along the tournament. (see Acknowledgments)

# What's inside:

* [ESPN_BPI_Scraper.ipynb](https://github.com/robertmanriquez/March_Madness/blob/master/ESPN_BPI_Scraper.ipynb)

This file contains the web scraper I used to scroll through each page on ESPN's website for BPI rankings, download the table, then concat it to a single csv.

* [MM_StatGrabberMerge_Functions_and_Model.ipynb](https://github.com/robertmanriquez/March_Madness/blob/master/MM_StatGrabberMerge_Functions_and_Model.ipynb)

This notebook has all of the functions I made to automate the cleaning, preprocessing, and merging required to assemble my training set.  Makes use of the regular season games, tournament season games, team name/seeds lists, and the ESPN BPI list.  I trained my model to predict 2017 games, then adapted it to make predictions on the 2018 matchups.

* [March_Madness_RandomForest_Model.ipynb](https://github.com/robertmanriquez/March_Madness/blob/master/March_Madness_RandomForest_Model.ipynb)

Lastly, I summarized my work and the functions used for assembling my training data and building models.  This notebook contains my final Random Forest model and a quick evaluation of classification metrics (logloss, accuracy, ROC curve).  This model yielded 75.7% accuracy, logloss of ~ 0.488, and a ROC curve with 84% area under the curve (AUC).


I invite you to take a look, and thank you for visiting!

**Robert Manriquez**


## Acknowledgments

* Data used was supplied from Kaggle.
* Modeling built using SciKit-Learn libraries.
* Thanks to https://github.com/joowani/binarytree and https://github.com/cshaley/bracketeer for their convenient packages for making my bracket!
