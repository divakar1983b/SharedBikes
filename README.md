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
    -   dummy variables for "weathersit" feature shall be created with first drop
    -   dummy variables for "season" feature shall be created with first drop
- Outlier Removal
    -   Outliers and Multicollinearity shall be understood from pair plots and Box plot of different features
    -   PairPlot of Continuous Variables:
*![Book logo](/PP_BS_YR.png)
    -   From the above pair plot we can see a good relation between "cnt" & "temp"/"atemp"
    -   Also the "temp" and "atemp" are highly correalated and dropping one of them would prevent multicollinearity in the model.
    -   Box plot of different features
    *![Book logo](/PP_BS_YR.png)


## Multicolinearity
- Provide general information about your project here.
- What is the background of your project?

## Model_Estimate
- Conclusion 1 from the analysis
- Conclusion 2 from the analysis
- Conclusion 3 from the analysis
- Conclusion 4 from the analysis

## Conclusion
- Provide general information about your project here.
- What is the background of your project?
<!-- You don't have to answer all the questions - just the ones relevant to your project. -->
