### FindDefault-Prediction-of-Credit-Card-fraud-

### Problem Statement

A credit card is one of the most widely used financial products for online transactions, offering a convenient way to manage finances, but also posing risks. Credit card fraud occurs when someone unauthorized uses another person's card or card information to make purchases or withdraw cash. Therefore, it is essential for credit card companies to detect fraudulent transactions to prevent customers from being charged for items they didn’t purchase. The dataset used contains transactions made by European cardholders in September 2013. It includes 284,807 transactions over two days, with 492 of them being fraudulent. The dataset is highly imbalanced, as fraudulent transactions make up only 0.172% of the total transactions. The goal is to build a classification model to predict whether a transaction is fraudulent or not.

### Data Set Overview:
The dataset contains 284,807 rows and 31 columns, with most of the numerical features transformed into 28 principal components using Principal Component Analysis (PCA) to protect sensitive user information. The columns "Time," "Amount," and "Class" are left unchanged, with "Class" being the target variable for identifying fraudulent (1) and non-fraudulent (0) transactions.

### Data Cleaning:
During the data cleaning process, we discovered that the dataset contains no missing values but does include some duplicate records. 

### Exploratory Data Analysis (EDA):
We started by analyzing the distribution of fraudulent and non-fraudulent transactions, visualizing the relationship between the two. Additionally, we explored the "Time" and "Amount" columns to understand transaction patterns and identify any potential outliers in the "Amount" column. It was observed that fraudulent transactions make up just 0.17% of the dataset.

### Feature Engineering:
Since "Time" and "Amount" were not needed for the model, we removed them and created a new column for scaled values. For model training, we separated the data into two variables: X (feature matrix, which includes PCA components and the scaled amount) and Y (target variable, Class).

### Model Training:
We split the dataset into training (70%) and testing (30%) sets using `train_test_split()`. The features (X) and target variable (Y) were used for this purpose.

### Model Selection:
For the model, we chose Decision Tree and Random Forest algorithms. A Decision Tree is a supervised learning algorithm that partitions the data into subsets based on feature values, forming a tree-like structure. Random Forest, an ensemble learning method, combines multiple decision trees to enhance accuracy and reduce overfitting. We compared the performance of both algorithms to identify the best one for this dataset.

### Model Validation:
We evaluated the models using various metrics including accuracy, precision, recall, F1 score, and confusion matrix. We also visualized the confusion matrices as heatmaps for both models.

### Handling Imbalanced Data:
Given the severe class imbalance in the dataset, we applied the SMOTE (Synthetic Minority Over-sampling Technique) method to oversample the minority class and balance the dataset. After oversampling, we used the Random Forest algorithm on the resampled data and calculated the model’s performance using accuracy, precision, recall, F1 score, and confusion matrix. The results were also visualized using heatmaps of the confusion matrices.

### Model Deployment:
For future deployment, we plan to use the `pickle` library to save the trained model and the dataset, enabling easy access and use in production environments.
 
