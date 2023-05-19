
# Student dropout rates or Academic Success
## Team Ignite

### Problem Statement
Develop a machine learning model that can predict student dropout rates or academic success based on a variety of factors, such as attendance, grades, and demographic data. The model should be able to identify students who are at risk of dropping out or falling behind and provide targeted interventions and support.

### Data Collection
Data was collected from UC Irvine Machine learning Repository- https://archive-beta.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success.

The data consists of 4424 rows and 37 features.
![image](https://github.com/ignite18/Student-dropout-rates-or-academic-success/assets/85385312/df9c8532-cc67-41d8-b439-e194078feff9)

The secondary data was found to be free of null values,duplicates or typos, so much of data cleaning wasen't required.

The Exploratory Data Analysis was done mainly using two libraries Matplotlib and Seaborn.

### Feature Selection
Feature selection is a process of selecting a subset of relevant features from a larger set of available features. Its purpose is to improve model performance, reduce overfitting, enhance interpretability, and reduce computational complexity. By selecting the most informative and discriminative features, we can focus on the most relevant aspects of the data and eliminate noise or redundant information.

We have done `Statisitcal variable selection` by using Statsmodel library and assigning the value of p < 0.005. By setting a threshold, such as p < 0.005, we filter out features that have p-values above this threshold, indicating that they are not statistically significant. These selected features can then be used for further analysis or model building.

The features selected for our model were:

'Previous qualification', 'Nacionality', 'Debtor', 'Tuition fees up to date', 'Gender', 'Scholarship holder', 'International', 'Curricular units 1st sem (credited)', 'Curricular units 1st sem (approved)', 'Curricular units 2nd sem (credited)', 'Curricular units 2nd sem (enrolled)', 'Curricular units 2nd sem (evaluations)', 'Curricular units 2nd sem (approved)', 'Curricular units 2nd sem (grade)'.

Before the modelling, we had to drop the students who were 'Enrolled' in the course, this was done because we have to predict the students who have graduated or dropped out.

### Model Building
Necessory libraries were imported first for modelling. The independent features and the target variables were choosen and the data was split into training and testing in the ratio of 8:2 respectively. 
'x' refers to the independent variables or input features of the model. These are the variables that you use to predict the target variable y. The input features are typically represented as a matrix or dataframe, where each row corresponds to an observation or data point, and each column represents a different feature or predictor.

'y' refers to the dependent variable or target variable that you want to predict using the logistic regression model. The target variable is a binary categorical variable, meaning it takes on one of two possible outcomes or classes.

#### Logistic Regression
Logistic regression is a type of regression analysis that is specifically designed for predicting binary outcomes. It is called "logistic" because it uses the logistic function (also known as the sigmoid function) to model the relationship between the independent variables and the probability of the binary outcome.

The training set contained 80% of the data and the remaining for testing. The model gave as an accuracy of 0.88705 which was good. Moreover, a confusion matrix was also plotted.

![image](https://github.com/ignite18/Student-dropout-rates-or-academic-success/assets/85385312/9f819582-6c56-40cf-bb3d-b996b9200d52)

#### Random Forest Classifier
Random Forest Classifier is a versatile and powerful algorithm that is widely used for both classification and regression tasks. It works by constructing an ensemble of decision trees, where each tree is trained on a randomly sampled subset of the training data and features.

With Random Forest, we obtained an accuracy of 0.9008 which was better than logistic regression.

The confusion matrix is also plotted for the same.

![image](https://github.com/ignite18/Student-dropout-rates-or-academic-success/assets/85385312/5a4a485f-3ce2-4361-a099-17fdede83354)

#### Gradient Boosting Classifier
Gradient Boosting Classifier, also known as Gradient Boosting Machine (GBM), is a boosting algorithm that combines the predictions of multiple weak learners (typically decision trees) in an iterative manner to create a strong predictive model. The main idea behind gradient boosting is to train new models that focus on correcting the mistakes made by previous models, gradually improving the overall predictive performance.

This model gave an accuracy of 0.89.

The confusion matrix has been plotted.

![image](https://github.com/ignite18/Student-dropout-rates-or-academic-success/assets/85385312/3bc70216-e90a-4d81-82ed-de5bfa29a7f6)

### Hyperparameter tuning for Random Forest Classifier using Grid Search
Hyperparameter tuning is an important step in optimizing the performance of machine learning models. It involves searching for the best combination of hyperparameters, which are parameters that are not learned from the data but are set before the training process. Grid search is a popular technique for hyperparameter tuning that exhaustively searches through a predefined grid of hyperparameter values to find the optimal combination.

When applying hyperparameter tuning using grid search to a Random Forest Classifier, the goal is to find the best values for hyperparameters such as the number of trees (n_estimators), maximum depth of the trees (max_depth), and minimum number of samples required to split an internal node (min_samples_split), among others.

After tuning the model, we improved the score to 0.904958.

### Model Deployment
To know how our model performs on unseen data is necessory. Therefore a unseen data was uploaded and the results were checked. Our model was perfoming well on the test data.


