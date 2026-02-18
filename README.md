### Surgical Instrument Failure Analysis based on procedures performed using that instrument

**Author** Puneet Aggarwal

#### Executive summary

#### Rationale
Why should anyone care about this question?

This research is important because identifying factors that contribute to early surgical instrument failure can help organizations improve instrument design, usage guidelines, and maintenance strategies. Predicting potential failures in advance may reduce operational costs, improve utilization of instrument life, enhance surgeon experience, and ultimately contribute to improved patient safety.

#### Research Question

The objective of this project is to determine whether there is a relationship between the usable life of a surgical instrument, the types of surgeries it is used for, and the experience level of the surgeon, and whether these factors can help predict the likelihood of instrument failure before the end of its intended life.

#### Data Sources
What data will you use to answer you question?

Due to data privacy and organizational restrictions, proprietary production data cannot be used directly. For this project, the analysis will be conducted using anonymized datasets derived from real-world patterns that simulates surgical instrument usage, surgery types, surgeon experience levels, and reported instrument failures.

#### Methodology

The project will apply multiple machine learning and data analysis techniques learned during the course, including:

Exploratory Data Analysis (EDA) to understand data distributions, trends, and correlations
Data preprocessing techniques such as encoding categorical variables and feature scaling
Supervised learning models such as Logistic Regression, Decision Trees, and Support Vector Machines (SVM)
Model evaluation and comparison using appropriate performance metrics
Visualization techniques (e.g., charts and graphs) to communicate insights effectively

#### Results
What did your research find?

Final Summary of Exploratory Data Analysis
Data Overview and Cleaning:
•	The initial dataset contained 952 entries and 9 columns. Significant missing values were identified in 'Anonymized Lot', '4 digit Seq', 'Type of Procedures', and 'Experience of Surgeon who performed Last Surgery(in Years)'.
•	Initial cleaning involved filling missing values and then dropping incomplete records, resulting in a cleaned dataset of 730 entries.
•	A 'Customer Lot' column was successfully derived by concatenating 'Anonymized Lot' and '4 digit Seq'.

Procedure Type Analysis:
•	The 'Type of Procedures' column, containing pipe-separated values, was successfully split and individual procedures were counted.
•	The top 10 most frequent procedures were identified and visualized, with 'Prostatectomy - Radical w/ Lymphadenectomy' being the most common.

Surgeon Experience Analysis:
•	The 'Experience Level' column, categorized as 'L' (Low), 'M' (Medium), and 'H' (High), was analyzed. The distribution showed 'M' as the most common category (343 entries), followed by 'H' (313 entries), and 'L' (74 entries).

Remaining Uses Distribution:
•	'Remaining Uses' showed a right-skewed distribution, with a mean of approximately 6.37, a median of 5.0, and a maximum of 81.0. This indicates that most instruments fail with few remaining uses, but a few have significantly higher remaining uses, suggesting early defects.

Relationships Exploration:
•	Surgeon Experience vs. Remaining Uses: Box plots indicated that while there isn't a drastically different pattern in 'Remaining Uses' across different surgeon experience levels, all groups show outliers with very high 'Remaining Uses', suggesting factors beyond surgeon experience are at play in premature failures.
•	Procedure Type vs. Remaining Uses: Box plots for the top 5 most frequent procedures revealed variations in 'Remaining Uses' distribution across procedures, highlighting that some procedures might be more demanding on instruments.

Analysis of Early Defects:
•	The 75th percentile of 'Remaining Uses' was calculated as 8.0, serving as the threshold for 'high Remaining Uses' (indicating early defects).
•	175 records had 'Remaining Uses' greater than 8.0. The top 10 procedures associated with these early defects were identified and visualized, with 'Prostatectomy - Radical w/ Lymphadenectomy' and 'Hysterectomy - Malignant' appearing frequently, suggesting these procedures might be linked to instruments failing prematurely.

Correlation Analysis of Combined Factors:
•	Individual procedures, 'Experience Level', and 'Instrument' were successfully one-hot encoded.
•	Strongest Positive Correlation: 'Component Separation TAR' (0.351) showed the strongest positive correlation with 'Remaining Uses', implying instruments used in this procedure tend to have higher remaining uses at failure.
•	Strongest Negative Correlation: 'Prostatectomy - Radical w/ Lymphadenectomy' (-0.207) exhibited the strongest negative correlation, indicating instruments used here tend to have fewer remaining uses at failure.

Baseline Machine Learning Model:
•	A RandomForestRegressor model was built to predict 'Remaining Uses' using one-hot encoded procedures, experience levels, and instruments as features.
•	The model achieved a Mean Absolute Error (MAE) of 2.242, a Root Mean Squared Error (RMSE) of 4.630, and an R-squared (R2) of 0.636. This R2 value indicates that approximately 63.6% of the variance in 'Remaining Uses' can be explained by our features. The model shows a reasonable predictive capability, with room for improvement, especially for predicting higher 'Remaining Uses' values.


#### Next steps

Model Enhancement: For the ML model, future steps could include:
o	Hyperparameter Tuning: Optimizing the RandomForestRegressor's parameters.
o	Feature Engineering: Creating more sophisticated features 
o	Advanced Models: Experimenting with other regression models (e.g., Gradient Boosting, XGBoost).


#### Outline of project

- [Link to notebook 1]()
- [Link to notebook 2]()
- [Link to notebook 3]()


##### Contact and Further Information