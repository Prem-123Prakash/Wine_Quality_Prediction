# Wine_Quality_Prediction

This project focuses on predicting the quality of white wine using a dataset from Kaggle. The dataset contains physicochemical properties (features) and quality scores (target variable) for 4,898 samples of white wine. The goal is to use machine learning techniques to classify wine quality.

Dataset Overview
Source: Kaggle
Shape: (4898, 12)
Columns:
       Features: fixed acidity, volatile acidity, citric acid, residual sugar, chlorides, free sulfur dioxide, total sulfur dioxide, density, pH, sulphates, alcohol
       Target: quality (integer score ranging from 3 to 9)
Class Distribution (Original):
       6: 2198 samples
       5: 1457 samples
       7: 880 samples
       Others: Fewer samples, with a skewed distribution.
       
**Step-by-Step Process**
1. Data Preprocessing
Standardized the features using StandardScaler for scaling all attributes to the same range to improve model performance.
Split the dataset into training (70%) and testing (30%) sets using train_test_split.

3. Initial Model Training
Model Used: Support Vector Classifier (SVC)
Target Variable: Original quality scores (3 to 9)

4. Results:
Accuracy: 58%
Challenges: Poor performance on underrepresented classes (e.g., quality 3, 9).

6. Addressing Imbalance
Revised Approach: Binary classification.
Class 0: Wines with quality 3, 4, 5.
Class 1: Wines with quality 6, 7, 8, 9.
Class Distribution (Revised):
Class 1: 3258 samples
Class 0: 1640 samples

8. Binary Classification Model
Model Used: SVC(Same as above model)
Results:
       Confusion Matrix:
                       [[289, 203],
                        [124, 854]]
       Metrics:

               Precision: 0.70 (Class 0), 0.81 (Class 1)
               Recall: 0.59 (Class 0), 0.87 (Class 1)
               F1-Score: 0.64 (Class 0), 0.84 (Class 1)
   
Overall Accuracy: 78%


**Observations**

The initial model struggled due to imbalanced data and misclassification of underrepresented classes.
Binary classification improved performance significantly, especially for wines of quality 6 and above.

**Next Steps**
. Feature Engineering: Investigate feature importance and remove less relevant features.
. Model Tuning: Optimize hyperparameters of SVC to further improve classification performance.
. Alternate Models: Experiment with ensemble methods (e.g., Random Forest, Gradient Boosting) to compare results.
. Data Augmentation: Address class imbalance using oversampling or synthetic data generation techniques.
