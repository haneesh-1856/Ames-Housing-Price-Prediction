COMP_SCI-5565 IML - Final Project Report
Haneesh Chowdary Sriram (16376630)

Executive Summary:

From the give datasets, “Ames Housing Price Dataset” for the project. The project main aim is to apply machine learning techniques to analyze housing data for house price prediction, predicting Sale price for the regression, classification, and market segmentation. Classification models are used to predict the “House Style” which is categorizing houses by type, Regression models are used to estimate the sale prices for the houses, and clustering models are used to group houses into affordable, comfortable, and high range houses using the appropriate metrics. These projects and different models will help in understanding the machine learning concepts and effectively support real estate decision-making and market analysis. 

Introduction:

The housing market is complex, with a rich and diverse set of 79 features that describe each property in various data types: numerical measurements of lot area and living area in square feet, ordinal ratings including overall quality scored from 1 to 10, and categorical attributes such as neighborhood, exterior materials, and heating type. All of these features put together capture almost every aspect of a house, including location, size, age, architectural style, pool, etc. Being able to analyze all of these features will provide a better understanding of buyers' and sellers' preferences, the value of the housing market, and trends, while estimating house prices more precisely. The major motivation for this project is the extraction of meaningful insights from housing data using machine learning methods, including regression models to predict numerical sale prices, classification algorithms to categorize houses based on structural properties, and clustering methods to segment houses into inexpensive, moderate, and expensive categories.

Overview of the dataset

This dataset is comprehensive house sales dataset from Ames, Iowa. The dataset contains 2937 rows and 82 columns. It has a wide range of features like Location details, House Lot details, Basement details, pool, exterior materials, heating types, Overall quality, time of building, utilities, condition ratings, garage details, sales price and conditions, etc recorded in the 82 columns. There are also quite a lot of missing values in the data, especially pool related data is almost 99% missing. There are also few details missing commonly for all the details with respect to that feature. For example, the garage and basement feature have variables with respect to it like Garage Type, Garage Year Built, Garage Finish, etc and Base Quality, Basement condition, exposure, all the variable w.r.t it are missing.


Main preprocessing task:

For a single feature, there are so many columns in the dataset related to that feature. For example for a basement feature the dataset have "Bsmt Qual", "Bsmt Cond", "Bsmt Exposure", "BsmtFin Type 1", "BsmtFin SF 1", "BsmtFin Type 2", "BsmtFin SF 2", "Bsmt Unf SF", "Total Bsmt SF", "Bsmt Full Bath", "Bsmt Half Bath". So All the sub-features(columns) related to a particular main feature are gathered and analyzed for their relationship with the target variable. The sub-features are sorted based on their relation strength. Then they are normalized and assigned weightage based on their importanse. this sub-feature weightage is used to calculate the overall feature score. This will help in reducing feature complexity by combining the correlated columns into a single one. Also it improves model efficiency by decreasing the dimensionality without losing key information.

 
Machine Learning Tasks and Models Used:

The project addressed classification, regression, and clustering-three core machine learning tasks-using an enhanced Ames Housing dataset with engineered composite features.
Classification:
The Classification task is used to predict the House Style, a multi-class and imbalanced categoraical values using features such as Overall Quality, condition, LivingArea, Basement, Garage, Bathroom, Lot, Year.
The next lines present the models that were implemented and compared:

•	Logistic Regression (Multinomial) as a linear baseline

•	k-Nearest Neighbors (kNN) as a distance-based non-parametric model

•	Random Forest Classifier can be considered an ensemble tree-based model, which has the capability to capture the nonlinearity of the relationship and interaction between features.

Regression:

The regression task is mainly focused on predicting the Sale Price, a continuous target variable representing house value. To predict the Sale Price, the features used for the regression model are Overall Quality, condition, LivingArea, Basement, Garage, Bathroom, Lot, Year details.
The following models were compared:

•	Linear Regression as a baseline model

•	Ridge Regression in addressing potential multicollinearity

•	Gradient Boosting Regressor-a non-linear ensemble model for better predictive accuracy.

Clustering:

This clustering task was employed for unsupervised segmentation of houses, considering structural and quality attributes such as Overall Quality, condition, LivingArea, Basement, Garage, Bathroom, Lot, Year.. And with these models, 
Following clustering algorithms were applied:

K-Means Clustering, DBSCAN, Agglomerative Hierarchy Clustering PCA was used strictly for dimensionality reduction purposes, visualization.

Final Performance Summaries

Classification (House Style Prediction)

Model	Test Accuracy	Key Observation
Logistic Regression	~62%	High recall for minority classes but low precision
k-Nearest Neighbors	~81%	Strong performance on dominant classes, poor minority coverage
Random Forest	~81%	Best balance between accuracy and minority-class performance
Best classification model: Random Forest, despite class imbalance, Random Forest achieved the strongest overall performance, especially in macro-averaged metrics.

Regression (Sale Price Prediction):

Model	R²	RMSE
Linear Regression	~0.82	~$35,200
Ridge Regression	~0.82	~$35,200
Gradient Boosting Regressor	~0.90	~$26,000
Best regression model: Gradient Boosting Regressor, this model significantly reduced prediction error and captured non-linear patterns not addressed by linear models.

Clustering:

Algorithm	Silhouette Score	Number of Clusters
K-Means	~0.20	3
DBSCAN	~0.14	Variable
Agglomerative	~0.17	3
Best clustering approach: K-Means, although cluster separation was moderate, K-Means produced the most interpretable and stable segmentation.
Key Insights and Observations:
Feature engineering played a great role in enhancing model performance for all tasks, especially in capturing meaningful relationships in the housing data. Ensemble models consistently gave the best results for all tasks due to their ability to model non-linear interactions among features effectively. Living area, overall quality, basement and garage attributes turned out to be the most influential factors in determining house prices. There was a marked impact of class imbalance in the classification results, yielding weaker performances for the rare house styles. Clustering methods identified broad housing segments, although clear and well-separated groupings were limited because of complexity and high dimensionality.

