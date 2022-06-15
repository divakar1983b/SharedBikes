# BIKE SHARING MODEL - "BOOM BIKES" 
> BoomBikes aspires to understand the demand for shared bikes among the people. 
> The company wants to know: 
> Which variables are significant in predicting the demand for shared bikes.
> How well those variables describe the bike demands
> Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market > based on some factors.

*![Book logo](/BSS.jpg)

## Table of Contents
* [Objective](#Objective)
* [Data Exploration](#Data_Exploration)
* [MultiColinearity](#Multicolinearity)
* [Model Estimate](#Model_Estimate)
* [Conclusion](#Conclusion)

<!-- You can include any other section that is pertinent to your problem -->

## Objective
- Model the demand for shared bikes with the given independent variables
- Model shall be used by managament to understand the effect of different features on the demand
<!-- You don't have to answer all the questions - just the ones relevant to your project. -->

## Data_Exploration
-  Variables
    -   From the dataset "day.csv", we have the datas for "instant", "dteday", "season", "yr", "mnth", "holiday", "weekday", "workingday", "weathersit", "temp",    "atemp", "hum", "windspeed", "causual", "registered", "cnt". 
    -   "cnt" is our target variable for which the regression model needs to be built
    -   "temp", "atemp", "hum", "windspeed" are the continuous variables
    -   "holiday", "weekday", "workingday", "season", "weathersit", "mnth", "yr" are categorical variables
    -   "instant", "dteday" shall be dropped due to low relavance to the model 
    -   "casual", "registered", "weekday" shall be dropped due to presence of alternate variable "cnt", "workingday", "holiday"
    -   dummy variables for "weathersit" feature shall be created with drop first method
    -   dummy variables for "season" feature shall be created with drop first method
- Correlations and Outliers
    -   Correlations, Outliers and Multicollinearities can be understood from pair plots,Box plot and heat maps
    -   PairPlot of Continuous Variables:
*![Book logo](/PP_BS_YR.png)
        -   From the above pair plot we can see a good relation between "cnt" & "temp"/"atemp"
        -   Also the "temp" and "atemp" are highly correalated and dropping one of them would prevent multicollinearity in the model.
    -   Box plot of different features:
    
    *![Book logo](/seasons.PNG)*![Book logo](/weather.PNG)
    
    *![Book logo](/Holiday.PNG)*![Book logo](/workingday.PNG)
    
    *![Book logo](/cnt.PNG)*![Book logo](/atemp.PNG)
    
    *![Book logo](/hum.PNG)*![Book logo](/windspeed.PNG)
    
    *![Book logo](/month.PNG)
    
        -   From the above box plots we can see that in year 2019 the shared bikes demand was comparetively higher than the year 2018 in all the trends.
        -   But the pattersn followed by various features such as "seasons", "weathersit", "holiday", "workingday", "mnth" in affecting the "cnt" target variable seems to be similar
        -   Also the Outliers in "cnt", "atemp", "windspeed", "hum" were identified and removed


## Multicolinearity
- To understand the multicollinearity amoung the different features, we shall plot the heat map between the variables, as well as use the variance_inflation_factor from statsmodels

    *![Book logo](/heatmap1.PNG)
    
- From the heatmap we can see that "temp" & "atemp" are highly correlated features. "temp" feature shall be dropped
- Similarly "hum", "fall" were also correlated with "atemp", which were confirmed by VIF function and elimiated one by one.
    *![Book logo](/heatmap2.PNG)

## Model_Estimate
- From the correlation matrix and other plots plotted above, we can clearly see that in the year 2019 the demand was comparitively higher than year 2018.
- But the factor(feature) which caused the increase in demand in year 2019 compared to year 2018 is perhaps not captured in the available features.
- In the correlation matrix the gains between the "cnt" and different features are not the same for year 2019 and year 2018, which confirms some unknown factor.
- For estimating the linear regression model, to get better correlation the data needs to be split for year 2018 and 2019 and proceed with model building.
- Linear regression models for year 2018 and 2019 were estimated separately as follows
        - OLS models for year 2018 and year 2019 were estimated separately
        - To identify and remove possible multicollinearities amoung features P-factor, VIF, RFE were looked into. 
        - The model estimate were repeated for 4 runs and in each run a collinear feature with high P/VIF/RFE is removed to get the final model
        - The final model estimate is shown below
- OLS Model

     *![Book logo](/2018model.PNG)*![Book logo](/2019model.PNG)

- VIF & RFE analysis

    *![Book logo](/vifmodel.PNG)*![Book logo](/rfemodel.PNG)
    
- R2 Score & Residual plot
- 
    *![Book logo](/r2score.PNG)*![Book logo](/predresd.PNG)
    
- Test data Predictions
  *![Book logo](/pred2018.PNG)*![Book logo](/pred2019.PNG)
  
- - Conclusion 4 from the analysis
- - Conclusion 4 from the analysis
- - Conclusion 4 from the analysis

## Conclusion
- Provide general information about your project here.
- What is the background of your project?
<!-- You don't have to answer all the questions - just the ones relevant to your project. -->
