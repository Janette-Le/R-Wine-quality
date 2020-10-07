# R - Wine quality

**:black_nib: [Codes file](https://github.com/Janette-Le/R-Wine-quality/blob/main/Codes.R)**<br>
**:page_with_curl: [Report](https://github.com/Janette-Le/R-Wine-quality/blob/main/Report.pdf)**

<p align="justify">Wine (from Latin vinum) is an alcoholic beverage made from grapes, fermented without the addition of sugars/acids/enzymes/water/other nutrients, with a history lasting for thousands of years and is closely related to the history of agriculture, cuisine, civilization, and humanity. 
After thousands of years of wine production, improvements in the winemaking process and exploration of various unique types of grapes as a raw ingredient, nowadays, there is significant diversity in wine industry with almost 200 types of wine by taste and style, classified into 5 main types: white, red, rosé, sparkling and fortified wine. For this project, I choose red version of Vinho Verde Wine to analyze, which has incredibly deep in color, a youthful, inky purple,  made principally from the late-ripening, red-fleshed Vinhão grape.<br>
The taste of wine depends on various elements, and is strongly related to 11 typical independent chemicals in red wine do affect its quality and to what extent. In another way, we use machine learning to determine which physicochemical properties make a wine “good”!</p>

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
![image1](/images/2.png)
<p align="justify">
   1. There is no blank entries (N/A) in our data set, but there is around 30% of  Zeros (0) are suitable for this data set because they refer to values of physicochemical test outcomes.<br>
   2. Using `<boxplot()>` to examine extreme values, assuming that all abnormal values falling out of upper and lower whiskers line are outliers. There are around 30% values of the dataset considered as outliers, but we couldn't get rid of them all.<br> 
   For 9 out of 11 independent variables, I apply some top and bottom limit to trim out the outliers and maintain the losing percentage to be around 2-3%, because their distributions tend to be normal. Especially for some variables that heavily positively skewed with long-tail extended for more than ¾ of the value scale, I use `<log10()>` to transform them.</p>
   
## Descriptive Statistics
<p align="justify">
   
</p>

# Correlation between Variables
![image1](/images/1.jpg)
<p align="justify">
   
</p> 
# Model Building: Multiple Linear Regression Model
<p align="justify">
   
</p>

# Model Optimization
  ## Model Optimization by Utilizing Stepwise Regression
  <p align="justify">
   
</p>
  ## Model Optimization by Comparing with LASSO
  <p align="justify">
   
</p>


# Statistical Findings after Comparing Different Models 
<p align="justify">
   
</p>

# Conclusion and insights
<p align="justify">
   
</p>
