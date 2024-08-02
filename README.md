**MODELING THE OUTCOMES OF THE MATCHES**

Welcome to my first-ever data science project!

**WHY THIS TOPIC?**

Before doing this project I did some research to find out how other people approached this topic. What made me think was the fact that many people base their ML models on the odds already offered by bookies. I wholeheartedly disagree with this approach. This is why in this project I want to explore the model's capabilities that solely rely on the team's stats from the past to make its predictions. Also, this project is an expansion of my bachelor's thesis work where I try to improve on my previous work.

**THE DATA**

The dataset that I'm going to work with is the Kaggle "League of Legends - 2024 Competitive Game dataset". I chose this dataset because it contains many interesting stats about the games that can make interesting predictors for my model. The link to the dataset - https://www.kaggle.com/datasets/barthetur/league-of-legends-2024-competitive-game-dataset/data From now on I'm going to refer to this dataset as the raw_data.csv file

**BUSINESS USE CASE**

Since the objective of this analysis is to answer the question: "Can you predict the future result of the match, if you know the past performance of the participants of the match?" this model could be employed by the betting companies in order to better value the bets they offer.

Additionally, to some extent, it can be used by the coaches to gain a better understanding of what makes a team successful in the long haul 

**ASSUMPTIONS**

This attempt at modeling the outcomes of the matches is based on the idea that in order to win a team needs to gain some kind of lead over their rivals. That's why instead of comparing raw values (which has been done many times) I'm going to subtract the scores of Team A from Team B to see what kind of advantage made them triumphant (or losers).

**LIBRARIES USED**

1. Pandas for data wrangling
2. Seaborn for visualizations
3. Sci-kit Learn for final preprocessing and model construction
