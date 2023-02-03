# Baseball Playoff Predictions
## Modeling MLB team playoff chances based on team statistics and attributes
**Author:** Joshua Lensing
### Business Problem:
Major League Baseball data and analytics are becoming a very big component of how professional baseball teams operate. A lot of this dataset comes from the idea of "Moneyball," where Billy Beane, the GM of the Oakland Athletics, found statisitics relating to individual player performance that scouts and other front offices were not focused on at the time. He hoped to use those background statistics and develop a formula for success that didn't require spending a large amount of money to build a roster of players. Instead, he hoped to find players that scored well in these statistical categories that other teams would often overlook and pay them cheaply to play for the Athletics. The hope was to ultimately make the playoffs and compete for a championship.

The source for this dataset can be found [here](https://www.kaggle.com/datasets/wduckett/moneyball-mlb-stats-19622012).

The data dictionary for this dataset can be found below:

| Variable Name | Descrtiption |
|---------------|--------------|
Team | Team Name
League | AL or NL
Year | Baseball Season in a Calendar Year
RS | Runs Scored
RA | Runs Allowed
W | Wins
OBP | On-Base Percentage
SLG | Slugging Percentage
BA | Batting Average
Playoffs | 0 for no playoffs, 1 for playoffs
RankSeason | Seed number during the regular season
RankPlayoff | Seend number for playoffs
G | Games Played
OOBP | Opponent On-Base Percentage
OSLG | Opponent Slugging Percentage

## Methods
- There are 2 columns I dropped from dataset before creating the visualizations: 'SeasonRank' and 'PlayoffRank.' These columns contained a lot of missing values because they only ranked the teams in the dataset that made the playoffs. And the ranking had no use to making the prediction of whether or not they make the playoffs, so they were dropped.
-  For modeling, I also dropped 'OOBP' and 'OSLG' columns. About 66% of the values in those columns were also missing, as that stat had not been calculated prior to 1999. I did not want to calculate the mean for all missing values because it would introduce a lot of error into the dataset.
- I did some feature engineering on the best model to see if it could improve its ability to predict the target. I combined 'OBP' and 'SLG' into 'OPS', which is a widely regarded stat in professional baseball. I also created a run differential column as well to show how many more runs each team scored vs. how many they allowed.

##Results
