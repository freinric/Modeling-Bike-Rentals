# Modelling Bike Rentals

This is the repository for our UBC MDS DATA583 (Advanced Modelling) group project.

We analyzed Hadi Fanaee-T's [Bike Sharing Dataset](https://archive.ics.uci.edu/ml/datasets/Bike+Sharing+Dataset), from the Laboratory of Artificial Intelligence and Decision Support (LIAAD), University of Porto, accessed in the UCI Machine Learning Repository. This dataset combines the Trip History Data for the years of 2011 and 2012 of 'Capital Bikeshare', which is metro Washington DC's bikeshare service, with weather data and the holiday schedule. We are hypothesizing that we are able to predict the count of bikes rented in a given hour given the predictor variables (weather, calendar date and time, etc). We are also hypothesizing that results will be better if we model casual and registered user bike rentals separately, rather than aggregated together in total bike users.

The report is found [here](BikeReport.pdf).

We observed that the Poisson model is a better fit than linear model both in terms of having lower MSE and having predicted values that are positive. Even though Poisson model is less easily interpretable than linear model, minimal effort is required to interpret how the coefficients of Poisson model relate to/explain the response variables as was shown before. Furthermore, the Random Forests provide much less interpretability, but makes up for it via greater accuracy in predictions, as can be seen from its relative MSE. 

If we want to understand how the different variables contribute to explaining the response variables, the Poisson model should be picked. If we'd rather get good predictions, random forest model should be picked. We are expecting a non-parametric model with splines to fit even better, but were not able to run such a model with our limited computer power. 

We observed that the MSE for 'casual' variable is significantly lower than those of 'registered' and 'total'. In fact, in all models, the MSE of the total count models is greater than the sum of MSEs for the casual and registered mode. This means that the separated models are better able to capture and accurately predict the number of bike renters, as was hypothesized.

In the linear models and poisson models, all predictors came out as significant, and so variable importance was hard to discern. The random forest model gave us the insight that the predictors most important in predicting the counts of riders, whether casual or registered, were the hour of the day, the year, and the weekday. This suggests that time affects the ridership more than the weather conditions. 
