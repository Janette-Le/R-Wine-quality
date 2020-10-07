# R - Wine quality

**:black_nib: [Codes file](https://github.com/Janette-Le/R-Wine-quality/blob/main/Codes.R)**<br>
**:page_with_curl: [Report](https://github.com/Janette-Le/R-Wine-quality/blob/main/Report.pdf)**

<p align="justify">Wine (from Latin vinum) is an alcoholic beverage made from grapes, fermented without the addition of sugars/acids/enzymes/water/other nutrients, with a history lasting for thousands of years and is closely related to the history of agriculture, cuisine, civilization, and humanity. 
After thousands of years of wine production, improvements in the winemaking process and exploration of various unique types of grapes as a raw ingredient, nowadays, there is significant diversity in wine industry with almost 200 types of wine by taste and style, classified into 5 main types: white, red, rosé, sparkling and fortified wine. For this project, I choose red version of Vinho Verde Wine to analyze, which has incredibly deep in color, a youthful, inky purple,  made principally from the late-ripening, red-fleshed Vinhão grape.<br>
The taste of wine depends on various elements, and is strongly related to 11 typical chemicals in it. In this project, I use machine learning to determine which physicochemical properties make a wine tastes “good”!</p>

## Project sections:
1. [Project topic](#R---wine-quality)
2. [Preliminary Exploratory Analysis](#prelimitary-exploration-analysis)
   - [Data cleansing]
   - [Descriptive Statistics]
3. [Correlation between Variables](#correlation-between-variables)
4. [Model Building: Multiple Linear Regression Model](#model-building-multiple-linear-legression-model)
5. [Model Optimization](#model-optimization)
   - Model Optimization by Utilizing Stepwise Regression
   - Model Optimization by Comparing with LASSO
6. [Statistical Findings after Comparing Different Models](#statistical-findings-after-comparing-different-models)
7. [Conclusion and insights](#conclusion-and-insights)

# Prelimitary Exploration Analysis
## Data cleansing
![image2](/images/2.png)
<p align="justify">
   1. There is no blank entries (N/A) in the data set, but there is around 30% of  Zeros (0) are suitable for this data set because they refer to values of physicochemical test outcomes.<br>
   2. Using <code>boxplot()</code> to examine extreme values, assuming that all abnormal values falling out of upper and lower whiskers line are outliers. There are around 30% values of the dataset considered as outliers, but it is impossible to get rid of them all.<br> 
   For 9 out of 11 independent variables, I apply some top and bottom limit to trim out the outliers and maintain the losing percentage to be around 2-3%, because their distributions tend to be normal. Especially for some variables that heavily positively skewed with long-tail extended for more than ¾ of the value scale, I use <code>log10()</code> to transform them.</p>
   
## Descriptive Statistics
<p align="justify">By summarizing the red wine dataset, it is not hard to find the descriptive statistics on the chart, which can help us to learn the details of each variable. For example, the mean of fixed acidity, volatile acidity, citric acid, residual sugar etc., is 8.27, 0.53, 0.26 and 2.36 respectively. Mentioning about dependent variable Quality score, although the quality scale range from 0 to 8, but as can be noticed clearly that most of wine sample received the score of 5 and 6 (nearly 80% of all observations).</p>

![image3](/images/3.PNG)

# Correlation between Variables
![image3](/images/1.jpg)
<p align="justify">As we can see, the six strongest features affect the quality of wine are volatile.acidity, citric.acid, total.sulfur.dioxide, density, sulphates, and alcohol.</p>

# Model Building: Multiple Linear Regression Model
<p align="justify">The F-statistics value is 78.58, p-value is 2.2e-16 while the R^2 is 0.37, indicating the performance of the model is relatively fitting well but some improvement is necessary needed</p>

![image4](/images/4.PNG)

# Model Optimization

## Model Optimization by Utilizing Stepwise Regression
  <p align="justify"> After establishing a multiple linear regression model with the critical variables: volatile.acidity, citric.acid, total.sulfur.dioxide, density, sulphates, and alcohol, it is better to perform the stepwise selection---Forward selection or Backward selection, which can be applied in the high-dimensional configuration, providing some additional insights. Firstly, performing the linear regression with all independent variables indicates that the volatile.acidity, total.sulfur.dioxide, pH, sulphates, and alcohol are the statistically significant roles in the regression that need to be adjusted. Then, running the backward selection to cut down the variables and leave the most important ones for the accuracy.</p>
  
## Model Optimization by Comparing with LASSO
  <p align="justify">In statistics and machine learning, least absolute shrinkage and selection operator (LASSO) is a regression analysis method that performs both variable selection and regularization in order to enhance the prediction accuracy and interpretability of the statistical model it produces. In other words, LASSO is a shrinkage and variable selection method for linear regression model. The advantage of the LASSO model is that LASSO regression works like a feature selector that picks out the most important coefficients(those are most predictive and have the lowest p-values), meanwhile, shrinks these irrelevant coefficients exactly toward zero in order to minimize prediction errors.</p>
  
# Statistical Findings after Comparing Different Models 
<p align="justify">I used the mean square error (MSE) to compare previous model and LASSO model. MSE is the average of the square of the errors. The larger the number, the larger the error. There is no correct value for MSE. In other words, the lower the value the better and 0 means the model is perfect. Since there is no correct answer, comparing the MSE value is a basic method of selecting one prediction model over another.</p>

| Model | MSE |
| ------|------ |
| Multiple linear regression | 0.4048 |
| Stepwise regression| 0.4103 |
| LASSO | 0.4118 |

# Conclusion and insights
<p align="justify">Although both multiple linear regression model and LASSO model generate the relatively same MSE, I prefer to use LASSO since the model is more accurate on variable selections. By utilizing LASSO model I covered all the significant independent variables which show up in the both multiple linear regression model and stepwise regression model with minimized prediction error.<br>
   Wine quality is a complex study, good wine is more than perfect combination of different chemical components. Under the regression techniques have been applied, I found out that alcohol, sulphates, chloride, and acidity play a major role in determining the quality scores.</p>
