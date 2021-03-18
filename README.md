**Guiding question**: 

How accurately can I predict GDP of a country, without knowing the country name, based solely on political, environmental, financial, and health data? For the USA, how accurately can I forecast GDP by percent change and GDP in dollars?



**Data Cleaning and EDA**

I downloaded a 16,000 row dataset from the World Bank with metrics for every country on political, environmental, financial, and health data each year since 1960. This dataset was filled with an excessive amount of null values. I cleaned and organized the data into 4 new datasets, each for a specific modeling purpose. The 4 cleaned datasets were as follows:
1. Top 5 Ranked Countries By GDP and Their Yearly GDP in Dollars
2. Top 5 Ranked Countries By GDP and With Yearly Associated political, Environmental, Financial, and Health data
3. USA GDP and GDP Percent Change, Yearly Since 1961
4. USA GDP and GDP Percent Change, Yearly Since 1980 With Associated political, Environmental, Financial, and Health data
 

**Modeling**

GDP Prediction Modeling Notebook
***
"GDP Prediction Modeling Notebook" explores the following question: how accurately can I predict GDP of a country, without knowing the country name, based solely on political, environmental, financial, and health data? I used the cleaned data set that includes political, environmental, financial, and health data for the 5 countries with the highest GDP in 2018. I stripped away the country name and randomized the order of the training and testing data. I then created a generalized prediction model that can predict GDP in dollars for different countries solely based on metrics collected for the country in that given year. Furthermore, I used interpretability from my linear regression model to show the relative weight of each feature in my datset for predicting GDP in my generalized model.

● Models Used:

    ○ Basic Linear regression

    ○ Random Forest With Extra Trees

    ○ Neural Network
Time Series Forecasting Notebook (USA GDP)
***
"Time Series Forecasting Notebook (USA GDP)" explores the following question: for the USA, how accurately can I forecast GDP by percent change and GDP in dollars? I used the cleaned data set that includes information on USA GDP in dollars and GDP percent change, yearly since 1961. I also used the cleaned data set that includes information on USA GDP and GDP percent change, yearly since 1980 with associated political, environmental, financial, and health data. I displayed impact on GDP of each feature when forecasting with political, environmental, financial, and health metrics.

● Models Used:
    
    ○ Sarima out of sample predictions (predicting final 20% of GDP data)
    ○ Sarima out of sample predictions (predicting 1 year ahead at a time for                   final 20% of GDP data)
    ○ Sarima In Sample Forecast With Added Yearly Political, Environmental,
    Financial, and Health Metrics
    ○ FB Prophet Model (In Sample)
 
 

 

**Key results from modeling**: 

How accurately can I predict GDP of a country, without knowing the country name, based solely on political, environmental, financial, and health data? Note that this dataset is predicting on data for countries that had the highest 5 GDP's in 2018.
    
   ○ Top scoring generalized prediction model was a random forest with extra trees: 
    
    ■ Achieved an R2 score of 99.5% (strong predictive power)
    ■ Achieved an average error of 270 Billion Dollars (GDP from my dataset is             typically in the trillions)
   ○ Most important features to generalized GDP prediction according to my interpretable linear model:
    
    ■ Fertility Rate, total births per woman
    ■ CO2 emissions (metric tons per capita)
    ■ Prevalence of overweight (% of adults)
    ■ Mortality rate, under-5 (per 1,000 live births)
 ***
For the USA, how accurately can I forecast GDP in dollars? 

○ Out Of Sample  Sarima Predictions 1 Year Ahead At A Time:
    
    ■ Achieved an R2 score of 97% (strong predictive power)
    ■ Achieved an average Error Of 379 Billion Dollars
 
 ○ In Sample Sarima Forecast With Added Features: 
     
    ■ Achieved an R2 score of 99.3% (strong predictive power)
    ■ Achieved an average error of 104 Billion Dollars
    *Note that in sample forecasts are useful for understanding the                 predictive power of a model but in the real world you will never have full                    knowledge of future exogenous variables
        
    ● Most Important Features to GDP Prediction
        ■ Fertility Rate, total births per woman
        ■ Population density (people per sq. km of land area)
        ■ Prevalence of overweight (% of adults)
        ■ Date
        ■ CO2 emissions (metric tons per capita)
 
***
For the USA, how accurately can I forecast GDP by percent change?

○ In Sample Forecast With Added Features (USA GDP Percent Change)
    
    ■ Achieved an R2 score of 99.7% (strong predictive power)
    ■ Achieved an average error of average 8% off GDP percent change
    *Note that in sample forecasts are useful for understanding the                 predictive power of a model but in the real world you will never have full                    knowledge of future exogenous variables
        
    ● Most Important Features to GDP Prediction (Percent Change)
        ■ Population ages 65 and above (% of total population)
        ■ Hospital beds (per 1,000 people)
        ■ Mortality rate, under-5 (per 1,000 live births)
        ■ Fertility rate, total (births per woman)
        ■ Population density (people per sq. km of land area)
 
 
 
 

**Takeaways and Next Steps For Modeling**:

*Generalized Model Takeaways and Next Steps:*
***
My generalized model for predicting GDP of any country based on political, environmental, financial,and health data was created using the countries with the top 5 GDP’s in 2018. To best predict GDP with a generalizable model I recommend using a random forest with extra trees model. To improve this model and create a model that can truly generalize to many country types, I recommend including data from a myriad of countries with high, middle and low GDP’s. This would also give more robust information about what metrics a country can focus on in order to increase their overal GDP. 




*USA GDP Forecasting Takeaways and Next Steps:*
***

To best forecast future GDP for the USA I suggest predicting one year in advance at a time and including political, environmental, financial, and health data. Given that you cannot truly know political, environmental, financial, and health metrics for years in the future I suggest forecasting each of these features based on past data. Then I suggest feeding those predictions into your forecasting model for USA GDP. This next step would be somewhat intensive but I predict that it would provide better results than forecasting without exogenous variables.
 
