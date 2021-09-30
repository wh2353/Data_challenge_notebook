# General description of the NFL play-calling 

National Football League (NFL) is a highly competitive and most profitable sports league in the USA. Every down in the game matters and key play calls in a close game are highly likely to determine a team's fate. Currently in the league, most play calls are made by experience and require quick judgement within 40 seconds or less, thus are often error-prone. Incidents that terrible play calls ruin a team's whole season's effects are frequently been reported. <br><br>
The NFLsavant.com provides play-to-play data of all NFL teams dated from 2013 to present. Those data provide useful information such as each team's favourite formation and playtype, as well as potential strength and weakness in offence and defence. However, those data were rarely be modelled and analysed.  Based on above, I propose a project that build a machine learning model from the play-to-play data to predict the best formation and playtype for each down in order to help NFL head coach make correct calls under time pressure and ultimately facilitate a team's success.

In specific, I propose a model that predict the most yards can be gained for a particular down and output the specific team formation and play type that can achieve this. To complete this goad, we need to first understand which features in the dataset have strong effects on yards gained on each play. Preliminary exploratory data analysis [Link to First Asset](https://github.com/wh2353/Data_challenge_notebook/blob/main/NFL%20play-to-play%20exploratory%20analysis.ipynb) showed that most numeric features are independent from the yards, while different choices in PlayType and formations may have significant effects on the outcome of gained yards per down.

The categorical features that are imperative to Yards were then numerized as one hot vectors, and 10K samples were random selected from in total 96713 data, split 70%-30% for train and test set respectively and fit with random forest regressor. WITH ONLY 10% of the data, I was able to identify the best model of a prediction cv score (R2 value) of 0.6405 through grid search. And the feature importance plot based on best model clearly demonstrated that SeriesFirstDown has the most dominant effect on number of yards per down, following by (Yards) toGo (to reach first down) as well as YardLine (the position of the line scrimmage) [Link to Second Asset](https://github.com/wh2353/Data_challenge_notebook/blob/main/NFL-Play-to-Play-random-forest-regression.ipynb).

In summary, both exploratory data analysis and random forest regression modeling indicate that number of yards gains are associated with a series sets of features in the dataset, which demonstrates the feasiblity of the project. Next steps will include obtaining team-specific data and add players and coaches information to current data for further refining the prediction model.
