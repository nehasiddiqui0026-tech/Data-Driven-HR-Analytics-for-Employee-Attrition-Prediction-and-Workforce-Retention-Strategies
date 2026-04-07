# Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies
Analyses employee attrition using clustering and classification models to identify key drivers such as overtime, job satisfaction, and work-life balance. Applies logistic regression for predictive modelling to support HR decision-making and improve workforce retention strategies.
## Project Overview
This project explores employee attrition using data analytics and predictive modelling techniques to identify key factors influencing workforce turnover. Employee attrition presents significant financial and operational challenges, making it essential for organisations to understand and predict employee behaviour.

The analysis begins with data preprocessing, descriptive statistics, and visual exploration to understand distributions, trends, and relationships across variables such as age, job involvement, satisfaction, income, and overtime. Correlation and proximity analysis are conducted to assess relationships between categorical and numerical variables using Jaccard and Euclidean distance metrics.

Clustering techniques, including k-means and k-medoids, are applied to segment employees into distinct groups based on shared characteristics. Validation metrics such as Silhouette Score and Davies-Bouldin Index are used to determine the optimal number of clusters, with eight clusters providing the most meaningful segmentation.

For classification, multiple models including k-nearest neighbours, Naïve Bayes, and logistic regression are implemented and evaluated using precision, recall, and confusion matrices. Logistic regression demonstrates the strongest performance and is selected for predictive modelling.

The final model identifies overtime, job involvement, job satisfaction, and work-life balance as key predictors of attrition, while variables such as gender and income show limited significance. The findings provide actionable insights for organisations to design targeted HR strategies, reduce employee turnover, and improve long-term workforce stability.
## Project Objective
1. Identify key factors influencing employee attrition, including job satisfaction, overtime, and work-life balance
2. Segment employees into meaningful clusters to uncover behavioural patterns and risk groups
3. Evaluate and compare classification models to determine the most effective approach for predicting attrition
4. Develop a predictive model to support data-driven HR decision-making and retention strategies
5. Provide actionable insights to help organisations reduce turnover and improve workforce stability
## Data Source and ANalysis Framework
The pre-processed data had been extracted from Kaggle which was curated by IBM data scientists’ of 1470 employees to explore employee attrition and the variables it is dependent on [(dataset link)](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset). The cleaned data features 11 factors, including employee attrition as the main dependent variables. Age, Gender, Job involvement, Job role, Job satisfaction, Monthly income, Overtime, Work life balance, Years at company and Years since last promotion are the other listed variables. Variables such as Job satisfaction, Job involvement and Work life balance were ranked on a scale from 1 to 5, 1 signifying ‘good’ and 5 meaning ‘bad’. This was done to convert the data into numerical form for processing. All the variables are cross sectional and structured to facilitate accurate data analysis.

### Key Determinants of Employee Attrition
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/Key%20determinants%20of%20employee%20attrition.png)
### Employee Attrition Data Analysis Framework
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Employee%20attrition%20data%20analysis%20framework.png)

The framework follows the data analysis process. Problem/Business understanding is the initial step. Understanding employee attrition and the variables that contribute to it so mitigation strategies can be identified is the key problem definition. The second step involves understanding the data set by identification of variables of interest, data summary, distributions, missing values, and relationships between variables. Data pre-processing mainly covers data cleaning, data validation and data reduction. The initial employee attrition excel file contained 23 variables. The data was validated by being imported to SPSS. Descriptive statistics were run but no missing values were highlighted. Visualisation of the data using SPSS, Orange and python was done which preceded correlation analysis and proximity analysis. Proximity analysis involved Jaccard distance and Euclidean distance for the relevant group of variables. K-means clustering is followed by classification using three models, Logistic regression, k-Nearest neighbour and Naïve bayes.
## Data Preprocessing
### Descriptive Analysis
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/Descriptive%20analysis%20of%20variables.png)

The results for the descriptive analysis show the dataset of 1,470 employees. The attrition rate is skewed towards most employees staying with the company. Key factors that influence job attrition are job satisfaction, income and work-life balance. Over-time participation had been low, further contributing to the attrition rate, as the mean was closer to 2, which in binary coding had been encoded as ‘no’.
### Distribution Visual Analysis
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/Descriptive%3Adistribution%20visual%20analysis.png)
### Histograms of Independent Variables
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Histograms%20of%20independent%20variables.png)

The histograms visualise the distribution across independent variables, both numeric and categorical. Age appears to have a bell-shaped distribution which suggests a normal distribution with most respondents being 30-40 years of age. Job involvement is left skewed showing most employees were more involved in their job. Similarly, work-life balance, satisfaction and working overtime were also left skewed. Monthly income however, is rightly skewed, with majority of the individuals having a monthly income below $10,000.
### Boxplots of Variables Relative to Attrition
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Boxplots%20of%20variables%20relative%20to%20attrition.png)

The boxplots are plotted against employee attrition. Monthly income seems to have the most outliers for higher incomes, while there are no outliers for lower incomes. The highest range is seen for employees that did not work overtime and decided to stay with the company. Other variables also show no significant outliers, which deduces that the data is robust and without any values that could potentially skew it. 
### Pie Chart of Employee Attrition in Job Roles 
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Pie%20chart%20of%20employee%20attrition%20in%20Job%20roles%20.png)

Job roles consisted of 9 categories listed above. The pie chart displays employee attrition to be the highest in Laboratory technicians of 26.2 percent and the least in research directors of only 0.8 percent which might also directly tie in with high job satisfaction and income. 
### Correlation Analysis
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Heatmap%20of%20variable%20correlations.png)

To investiagte the relationship between variables, correlation analysis was used. The correlation coefficient ranges from -1 to 1, with -1 showing a strong negative correlation and 1 a strong positive correlation. Age and monthly income had the highest correlation among all the variables of 0.5 which suggests that older employees are getting paid relatively higher. Attrition had the highest correlation with working overtime- employees whi had to consistenly stay back after their working hours, were more likely to resign.
### Proximity Analysis
To understand the similarity and dissimilarity between variables and observations, a proximity analysis is conducted. The data set included variables that were mainly categorical binary data. To analyse this specific type of data, the Jaccard distance metric is used. For variables numeric in nature, Euclidean distance had been implemented. 
#### Jaccard Distance
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/Jaccard%20Similarity%20score%20matrix.png)

![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Jaccard%20Similarity%20heatmap.png)

Overtimes and Attrition displays the highest distance of 0.573. This suggests that employees who worked outside of their office houses, were significantly different than those employees who decided on staying in the company. The matrix also shows a high value for gender and attrition. This signifies those characteristics associated with women with high attrition is different from men with high attrition.
#### Euclidean Distance
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/Euclidean%20distance%20matrix.png)

Euclidean distance is the measurement of similarity or dissimilarity between numerical data. The two numerical variables, age and monthly income, have a distance of 863.04 which is relatively large. This implicates that they are distinct in their magnitude, which is reflected by the data, as monthly income has a larger scale than age.
## Data Preprocessing
The data consisted of numerical data along with ordinal categorical data. Potential outliers were identified while cleaning the data to prevent any extreme skewness. Descriptive statistics provided more insight on the nature of each variable which was followed by visual representations in the form of graphs and tables. Variables such as job involvement scaling from 1 to 5 added restrictions during proximity analysis due to their non-binary and non-numerical nature. 
## Data Analysis
### Clustering
Clustering analysis is used to group data into clusters based on similar attributes or characteristics. This allows for the identification of patterns in data. To determine the optimal number of clusters. Using Silhouette score, the metric visualised 10 clusters against the score. The highest scores were identified in Clusters 2 and 8. Another index which was used to elevate the credibility of the results was the Davies Bouldin Index. It evaluates the compactness and separation in the clusters. This translates to the fact that the lower score signifies a better cluster. The data was first normalized so that there was no domination of variables that have large ranges. 
#### Davies- Bouldin Analysis
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Davies-Bouldin%20analysis.png)
#### Silhouette Score Analysis
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Silhouette%20Score%20analysis.png)

Narrowing the optimal number of clusters to 2 and 8 using the previous methods allows for more rigorous research. The outcomes are then displayed for k-mean and k-medoids clusters for k=2 and k=8 highlighting the unique characteristics of each cluster. After validation using both methods 8 clusters were selected based on a high silhouette index (0.23) and a lower Davies-Bouldin index (0.4).
#### K-means Clustering Count
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/K-means%20clustering%20count.png)
#### K-medoids Clustering Count
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/K-medoids%20clustering%20count.png)
### Classification
The main objective of classification involves training the model on a specified data set to make future predictions or generalizations. The classification algorithms that were used include K-nearest neighbour, Naïve bayes and logistic regression. KNN is mainly distance based. Inclusion of categorical data prompted the usage of Naïve Bayes model and Logistic regression model was used instead of a linear one due to the multi-class nature of the data. Evaluation metrics for all three models is done using precision which determines how many positive instances were accurately so. The second metric is recall which identifies the count of all accurate positive instances. F1- score assists with imbalanced datasets and is the mean of the previous metrics. Lastly, support is the count of occurrences, which was the same in all models. Logistic regression displays the highest precision and recall of 0.86 and 0.88 that the two models which highlights better identification of positive instances and the minimizing of false positives. 
#### Evaluation Metrics for Models 
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/Evaluation%20metrics.png)

Understanding of the model performance called for visualisation of the classification results into confusion matrices. A confusion matrix compares the labels true positive, true negative, false positives and false negative to accurately assess which model has the highest count of accurate predictions of positive class and negative class. Similarly, it also measures how many instances where the model incorrectly predicted the positive class and negative class. The K-nearest neighbours matrix shows the model was able to accurately predict 116 instances of class 0 but was inaccurate for 19 of them. The model was able to predict 129 instances of class 1 but was incorrect for 36 cases. 

For the Naïve Bayed model, there were 120 accurate predictions of class 0 and 15 inaccurate ones, while class 1 saw 128 accurate predictions and 37 inaccurate ones. This model is comparatively slightly better than KNN based on these results. Lastly. The logistic model displays 118 true positives for class 0 and 17 false positives. Similarly, 29 predictions were inaccurate for class 1 and 136 were accurate, which is the highest amount among all the models.
#### K-nearest Confusion Matrix
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/K-nearest%20confusion%20matrix.png)
#### Naïve Bayes Confusion Matrix
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Naive%20bayes%20confusion%20matrix.png)
#### Logistic Regression Confusion Matrix
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Logistic%20regression%20confusion%20matrix.png)
### Predictive Modelling
#### Logistic Regression
After evaluation of the models and consideration of the nature of the data being binary and multi-class, logistic regression is used to develop a predictive model. The relationship between job attrition and job role and satisfaction can also be determined using the regression model to better assist companies to determine patterns in behaviour for planning and forecasting. The output for logistic regression of the data shows the coefficients of each independent variable, which has a direct impact on the dependent variable which is employee attrition. 
#### Regression Analysis
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/Regression%20analysis.png)

Overtime has the highest positive coefficient alongside job involvement. This indicates that employees who tend to work overtime and have less job involvement have a higher chance of leaving their company. Gender, having a p value greater than 0.05 does not have a significant impact on employee attrition. Due to it not being statistically significant, alongside monthly income, the regression model was run again, after disregarding these variables. 

#### Logistic Regression Feature Importance
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/visualisations/Logistic%20regression%20feature%20importance.png)
#### Revised Regression Analysis
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/Revised%20regression%20analysis.png)
#### Equation
**Y’= 0.84 + 0.01*Age + 0.07*Job Involvement + 0.02* Job role + 0.04* Job Satisfaction + 0.2* Overtime + 0.03* Work Life Balance**

This equation provides a logistic regression model for employee attrition based on the significant variables, which include age, job involvement, job role, job satisfaction, overtime and work life balance.
#### Evaluation Metrics
![T1](https://github.com/nehasiddiqui0026-tech/Data-Driven-HR-Analytics-for-Employee-Attrition-Prediction-and-Workforce-Retention-Strategies/blob/main/tables/Evaluation%20metrics.png)
## Conclusion
The study conducts a rigorous analysis of the variables and their relationship with employee attrition to determine a predictive model. data analysis algorithms provided substantial findings that can be important to organizations when implementing company policies. Variables such as Overtime, job satisfaction and work life balance were seen to have the most substantial effect on the decision of the employee to leave a company. This was similar to the research conducted by Fallucchi, et al. (2020) that used descriptive statistics to observe distribution of Overtime and stated that employees who worked over time more frequently displayed an attrition of over 30 percent, 

While employees who did not work overtime had a rate of 10.4 percent.  One contradiction that was highlighted was gender and monthly income. During secondary data research, both these variables were seen to have a moderate to low correlation with attrition. Women were more likely to leave a company and employees that were granted lower wages were also more likely to leave. However, the logistic regression model determined both these variables to be insignificant to employee attrition. Correlation heatmaps were also able to identify relationships between different variables, which showcased age and monthly income to have the highest correlation and for work life balance to have a high correlation with attrition. This directly reiterated a study by Mansor, et al. (2021).  Clustering of data was essential for data processing. After analysis, 8 number of clusters were determined to be optimal.

The classification and clustering analysis are generalized attrition patterns by grouping variations into subgroups. The predictive model provided further insights into future employee attrition behaviour based on factors such as their job satisfaction levels and job involvement.

The data gathering approach along with the processing step has certain limitations. The data being categorical restricted it from having a uninformative distance model. The data had to be grouped into numerical and categorical which using Euclidean distance and Jaccard distance models respectively. The dataset has limited variables, which also constricts the scope of the research. Voluntary attrition is specifically being focused on in the research, which would require further in-depth data to provide more understanding on human behaviour. The sample of employees did not specify which specific country they were based in. This limits the research from portraying results accurate to all regions. 

The main contributor to ‘The Great Attrition’ was the COVID-19 pandemic, thus it is also imperative to consider work-from-home models when assessing attrition. The key trends and implications show that younger employees that tend to work overtime more frequently and have low levels of job involvement tend to leave organizations. Furthermore, monthly income and gender does not have a direct correlation to employee attrition. Companies are thus, recommended to reduce overtime hours to prevent ‘burnouts. Furthermore, for a company to maintain competitive advantage over their competition, the must prevent their employees to move to their competitors, in a buoyant local labour market. 
