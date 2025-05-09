## nba_game_predictor
GitHub Link: https://github.com/tanmbillawala/nba_game_predictor

To see the results of our project, look at NBA_Game_Statistics_Predictor.ipynb and NBA_Game_Outcome_Predictor.ipynb.
Our project has the following files.

### Jupyter Notebooks
#### Import-Update_Data.ipynb
This file is used to get the NBA game logs. Once we get the data, we clean it as necessary (fixing dates, changing columns to usable formats, and dropping unnecessary columns) then we export to csv for use in the other notebooks. Use this file when new games have happened and the current logs need to be updated. However, it is not necessary to run this file because we already have the cleaned game logs as a csv file. 

#### EDA.ipynb
This file has comprehensive exploratory data analysis to better understand the data and direct our next steps for our approach when building the model. While the notebook provides interesting visuals, it is not necessary to run.

#### NBA_Game_Statistics_Predictor.ipynb
Our project build a game predictor with a two-step approach. First, we predict statistics indicated team performance (like Field-Goal Percentage) for the game we want to predict the outcome of. Then, we use these values to predict our outcome. This notebook handles predicting game statistics. We try two different ways: a basic rolling window and an XGBoost model which predicts the statistics when given the rolling averages. We perform hyperparameter tuning on the XGBoost Regression model, then compare performance between the two methods. This notebook is not necessary to run for training and testing of the model as we saved the csv files since predicting the statistics can take nearly 10 hours. However, for Playoff Prediction, this notebook needs to be run in tandem with NBA_Game_Outcome_Predictor since we are constantly going between predicting statistics and outcome.

#### NBA_Game_Outcome_Predictor.ipynb
This notebook handles the outcome prediction. We validate the model, perform feature selection and hyperparameter tuning, and finally test using the predicted statistics from before. Once this is complete, we perform playoff prediction at the end. 

### .CSV files
#### all_stats_cleaned.csv
Includes all the game log information, which contains team information (name, id, abbreviation), opponent, win/loss, game information (min, points, shooting statistics). This file is used primarily for statistics prediction.

#### df_model_tuned.csv
Has the predicted statistics from the XGBoost Regression Model for the seasons from 2014-2024. This can be used to avoid the lengthy prediction running and should be constantly updated with new games.

#### df_rolling.csv
Has the predicted statistics using a basic rolling window.
