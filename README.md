# Stats_project
Initially from the imported dataset, the most important aspects were renaming feature names and exploring how they could be made more efficient when calling within Python. 

The feature names were all changed into something that was easily recognizable and something that did not have to be looked up with the included documentation on the data.gov website. 

After the renaming, the features were all standardized into a grammatical parameter where punctuation was all lowercase, all dashes/spaces turned into underscores.  

Using the head function, on the column names, I was able to see which columns were irrelevant and/or included too many nulltype, ‘nan’ values. If need be, for later, I could include these features as dummy-type variables for my linear/non-linear regression models, however they were not initially needed, so they were dropped and the new dataframe was saved using the inline argument within the drop function.

Within each feature, I had to make sure that the grouping of the subsets was not overly complicated and easy to understand.  For example, in the ‘drive’  feature, the observations included duplicate all wheel drive values that measured whether a vehicle had the capacity to turn of all time all wheel drive. Since having the option to turn off all wheel drive still includes the additional weight in having such a sophisticated drivetrain, it will still impact fuel economy in the same way as it would if it wasn’t an option. The other features were also explored and altered so that such duplicate ‘grouping’ was not an issue. 

From looking over the dataset, I realized that the only combined fuel economy given was in the form of adjusted values that included variables for weather, rolling resistance in tires, and having all electronic and luxury aids in the off position. However, this standard wasn’t used till the 21st century, meaning that the data would be skewed in a different diffection for anything pre-2000. Therefore I standardized the parameter by finding the mean of un-adjusted city  and unadjusted highway fuel efficiency data. From personal experience of driving many automobiles, the data seemed to be much more in-line with real world estimates.

For more visual exploratory analysis,  I decided to model the combined fuel economy and co2 emissions for groups of years. This made it easy to see that the world’s automakers still have much to do in terms of technological advancements for efficiency in motors. It is easy to see however that in the last five to ten years, automakers have took a turn in finally reducing these means. Whether it was to do with the mass movement of reducing climate temperature, is a question that needs to be answered by studying a greater number of datasets.

After identifying the dependent variables, via a matrix scatter plot, I was ready to move on to figuring linear regression from within multiple and pairs of variables. 

With this dataset, it was intuitively easy to see which variables would end of being dependent and independent. Any sort of fuel economy would be calculated the same way, and imagining the science behind burning gas and creating emissions in a linear aspect made the process even more streamlined. 

After setting  a dependent variable that most linearly fit the dataset, it was easy to set up a formula within the least squares function that achieved the highest R squared and adjusted R-Squared values. 

After running the linear regression model,  the only p-values that were above .05 ended up from within the ‘drive’ feature. However removing the ‘drive’ variable from the linear regression model would too negatively impact the adjusted R squared value, therefore it was left unchanged. 

Since this concluded my multiple regression model, I decided it would be interesting to model linear regression in terms of a pair of dependent and independent variables. 

After realizing that not all data is perfectly linear, I modeled a non-linear regression in the ‘co2_emissions’ and ‘combined_mpg” features with an order of three for the exponents. Initially I tried 2,  trying not to overfit the model, but the parabolic shape of this line did not reflect the lower extremes of the data. This non-liner curve applied to the data produced a high adjusted R-Squared value of 0.865.

For probabilities, I believed it would be interesting to see how manual and automatic vehicles impacted fuel economy. This included producing  data sets for manual, automatic, over 30mpg and less than 30mpg datasets. I decided to use a binomial distribution in the mindset that a success was figures over 30, and a failure involved figures less than 30. This produced an ideal Gaussian curve, that with albeit low probability, modeled the amount of success over a period of tests.

Continuing on the theme of climate change, I decided to see which country included automakers that produced the biggest change in mean over the past 30 years in terms of co2 emissions.  CO2 emission datasets were produced for each countries automakers, and their P-Values were compared on whether to reject or accept the Null Hypothesis for each scenario. 
