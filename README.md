Methodology
Initially, a comprehensive dataset of climate information regarding Mendocino County was compiled. Utilizing NASA's MODIS (Moderate Resolution Imaging Spectroradiometer), an open-source repository of satellite data, essential climate variables known to influence wildfire ignition and spread were gathered. These variables included maximum temperature, minimum temperature, average temperature, dew point, humidity, precipitation, wind gust, and wind speed. Over a span of 3 years, daily climate data for Mendocino County was retrieved from both NASA MODIS and the local weather satellite maintained by Mendocino County.

Subsequently, this wealth of data was organized into an Excel spreadsheet format. Each row in the spreadsheet represented a distinct day, while each column corresponded to a specific climate parameter. To facilitate predictive modeling, an additional column titled "wildfire" was incorporated into the spreadsheet. This column served as the target variable for subsequent analyses, with binary values of 0 or 1 assigned to denote the presence or absence of wildfires on respective dates. Rigorous research efforts were undertaken to accurately identify dates marked by wildfire activity. Upon confirmation of wildfire occurrences, a value of 1 was assigned to the "wildfire" column for the corresponding dates. Following the completion of this data collection process, a finalized historical weather dataset of Mendocino County was constructed. The dataset was then converted into a CSV file in able for Jupyter Notebook to read the file and import it into the code.

Now that the dataset has been imported to the notebook, small data cleaning measures can take place before programming the machine learning classification model. First, columns that are unnecessary and useless in the prediction model was dropped for simplicity. The date and precipitation type are examples. 

To Train the prediction model, 80% of the dataset information was utilized and the remaining 20% of information was named as a Test set. For Example, if we had 10 years’ worth of data, 8 Years of information would prepare the calculations and 2 years of information would test the model. The accuracy of a classification model is evaluated on how accurately a model predicts the test set when given 80% of information. 
	
After that, Pearson Correlation was utilized to remove any highly correlated features. The Pearson correlation measures the strength of the linear relationship between two variables. It has a value between -1 to 1, with a value of -1 meaning a total negative linear correlation, 0 being no correlation, and + 1 meaning a total positive correlation. No features were removed since none had a correlation of above 0.75.

In addition to that, before testing the model, the x train is scaled. Feature scaling is the process of normalizing the range of features in a dataset. Real-world datasets often contain features that are varying in degrees of magnitude, range, and units. Therefore, for machine learning models to interpret these features on the same scale, preforming feature scaling is crucial.
	  
To test each of the five different classification machine learning models, a code was programed to run a prediction of the test dataset given only the training dataset. Each model ran the simulation. 
 
To evaluate the performance of each model, the R-squared (r2) score and mean absolute error (MAE) was calculated for each model’s performance on their predicted results of the test data set vs. the actual results of the test data set. R-squared is a statistical measure that indicates how much of the variation of a dependent variable is explained by an independent variable in a regression model. A r2 score is scaled from 0 – 1 and the higher the score, the more accurate the model is. MAE is defined as the average variance between the significant values in the dataset and the projected values in the same dataset. 

Results:
The Linear Regression model preformed with a R-squared score of 0.9670 and a MAE value of 0.7304.

The Lasso Regression model preformed with a R-squared score of 0.9073 and a MAE value of 1.3218.

The K-Neighbors Regressor model preformed with a R-squared score of 0.8671 and a MAE value of 1.4226.

The Random Forest Regressor preformed with a R-squared score of 0.9236 and a MAE value of 1.0331.

The Support Vector Regressor preformed with a R-squared score of 0.8180 and a MAE value of 1.4461.

Dissucsion/Conclusion
After running a prediction of the testing dataset with each machine learning model evaluation of the R-squared score and MAE were determined for each model. The Linear Regression model preformed with a R-squared score of 0.9670 and a MAE value of 0.7304 when predicting for wildfires for the testing dataset we created in phase 3 of the programming process. This evaluation was based on how accurate the model predicted for wildfires in the testing data set by comparing the predicted results created by the model to the actual results of the data. This was programmed in phase 4 of the programming process. Other prediction models like the Lasso Regression model preformed with a R-squared score of 0.9073 and a MAE value of 1.3218. The K-Neighbors Regressor model preformed with a R-squared score of 0.8671 and a MAE value of 1.4226. The Random Forest Regressor preformed with a R-squared score of 0.9236 and a MAE value of 1.0331. And the Support Vector Regressor preformed with a R-squared score of 0.8180 and a MAE value of 1.4461.

Based on the results of the model testing preformed, the Linear Regression model proves to be the best preforming model in predicting wildfires based on climate variables. It achieved the highest R-squared score and lowest MAE value of all models (0.9670, 0.7304). The next best preforming prediction model was the Random Forest Regressor model which achieved a R-squared score of 0.9236 and MAE value of 1.0331. The worst preforming model was the Support Vector Regressor. Considering the conclusions of the study preformed, a Linear Regression machine learning model is the most accurate in predicting wildfires based on climate data of a specific location. Utilizing a Linear Regression model and advanced data collection techniques can serve as a novel approach in wildfire prediction in targeted, wildfire prone areas.

