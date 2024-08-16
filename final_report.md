# Predicting 2024 Paris Olympics Results Based on Historical Data

**Authors:**
- Kelvin Wang
- Tuna Akmehmet
- Ethan Baird
- Arnav Singh

**Date:** August 18, 2024  
**Course:** Prof. Schwarze, Mathematics and AI (MATH 76.01)

---

## Introduction

The Olympic Games represent one of the most prestigious and highly anticipated sporting events worldwide. Every four years, athletes from across the globe gather to compete at the highest level, showcasing their skills and vying for the coveted Olympic medals. Predicting outcomes in such a highly competitive environment has always been of interest to sports analysts, coaches, and fans. Understanding the factors that contribute to an athlete's success not only enhances the preparation for future competitions but also provides valuable insights into the dynamics of elite sports. This project leverages machine learning techniques to predict the results of the 2024 Paris Olympic Games by analyzing historical data from the past 120 years of Olympic events. Through this analysis, we aim to uncover patterns and trends that can help forecast which athletes are most likely to win medals.

## Motivation

The motivation behind this project stems from the importance of data-driven decision-making in sports. As the volume and variety of data in sports continue to grow, so does the potential to transform how we analyze and predict sports outcomes. In the context of the Olympics, where the stakes are incredibly high, predicting potential medalists can influence training strategies, athlete selection processes, and even sponsorship decisions. Furthermore, this project is important because it pushes the boundaries of what is possible with predictive analytics in sports, opening doors to new methods of performance enhancement and competition strategy.

## Methodology

### Data Preprocessing

The dataset utilized in this study (`athlete_events.csv`) includes various features related to athletes' performances across multiple Olympic Games. The initial steps of data preprocessing included:

- **Subsetting Relevant Features:** We selected variables likely to influence an athlete's performance, such as `Sex`, `Age`, `Height`, `Weight`, `NOC` (National Olympic Committee), `Year`, `Sport`, `Event`, and `Medal`.
- **Handling Missing Data:** The `Medal` column, which serves as the target variable, was filled with "No Medal" for missing entries to distinguish between medalists and non-medalists.
- **Encoding Categorical Variables:** We encoded categorical variables like `Sex` (0 for male, 1 for female) and `Medal` (0 for no medal, 1 for won a medal) to prepare them for model training.
- **Filtering the Dataset:** To ensure the model's relevance, we filtered the dataset to include only those events where a sufficient number of athletes had won medals (more than 50 medalists in each event).

### Feature Engineering

To further enhance the predictive power of our models, additional feature engineering was performed:

- **One-Hot Encoding:** Categorical features such as `NOC` were one-hot encoded to allow the machine learning models to interpret these variables effectively.
- **Balancing the Dataset:** The dataset was balanced by reducing the number of non-medalists to match the number of medalists, preventing the model from being biased towards predicting no medals.

### Model Selection and Training

We experimented with various machine learning models to predict whether an athlete would win a medal:

- **Decision Tree Classifier:** Used a Decision Tree model with a maximum of 20 leaf nodes to prevent overfitting. This model provides interpretable results by showing the decision-making process for classifying an athlete as a medalist or non-medalist.
- **Logistic Regression:** Employed to understand the linear relationships between the input features and the probability of winning a medal.
- **Linear Discriminant Analysis (LDA):** Used to model the relationships between the features and the target variable, assuming the data is normally distributed within each class.
- **Random Forest Classifier:** Trained to leverage the power of ensemble learning, combining the predictions of multiple decision trees to improve accuracy.
- **Bagging and Boosting Classifiers:** Explored Bagging (Bootstrap Aggregating) and Gradient Boosting techniques to further improve the model's performance by combining multiple weak learners.
- **Support Vector Classifier (SVC):** Used to classify the data by finding the optimal hyperplane that maximizes the margin between the classes.
- **k-Nearest Neighbors (kNN):** Implemented to predict the class of a given athlete based on the classes of their nearest neighbors in the feature space.

### Evaluation

Each model was trained and evaluated using the following metrics:

- **Training Accuracy:** Measures the accuracy of the model on the training set, indicating how well the model has learned the training data.
- **Testing Accuracy:** Measures the accuracy of the model on the testing set, providing an indication of the model's ability to generalize to new, unseen data.

The evaluation results were stored in a DataFrame to compare the performance of each model.

## Main Findings

Our analysis revealed that ensemble methods, such as Random Forest and Gradient Boosting, outperformed simpler models like Logistic Regression and Decision Trees in terms of both training and testing accuracy. These findings suggest that capturing the complex interactions between features is crucial for accurately predicting Olympic outcomes. The k-Nearest Neighbors model also showed competitive performance, particularly when the number of neighbors (k) was carefully chosen.

Despite these successes, the project also highlighted several challenges:
- **Data Imbalance:** Even after balancing the dataset, predicting medalists remains challenging due to the inherent unpredictability of sports outcomes.
- **Feature Importance:** Features such as `Height`, `Weight`, and `Age` were found to be important, but there may be other influential factors not captured in the dataset, such as training conditions, injuries, and psychological factors.

### Visual Aids

![Model Performance Comparison](model_performance.png)  
*Figure 1: Comparison of Model Performance in Terms of Training and Testing Accuracy.*

![Feature Importance in Random Forest](feature_importance.png)  
*Figure 2: Feature Importance as Determined by the Random Forest Model.*

## Learning Outcomes

This project provided valuable learning experiences in several areas:

- **Data Preprocessing:** Team members gained hands-on experience in cleaning and preparing data for analysis, a critical step in any data science project.
- **Modeling Techniques:** We explored a variety of machine learning models, gaining insights into how different algorithms work and when to apply them.
- **Evaluation and Interpretation:** The project emphasized the importance of model evaluation, teaching us how to assess model performance and interpret the results.
- **Collaboration and Workflow:** We learned how to collaborate effectively, manage a project workflow, and integrate different parts of a project into a cohesive whole.

## Author Contribution Statement

- **Kelvin Wang:** Led the data preprocessing and feature engineering efforts, ensuring the dataset was clean and ready for modeling.
- **Tuna Akmehmet:** Worked on the interpretation of results, generating insights from the model outputs and compiling the main findings.
- **Ethan Baird:** Focused on the implementation of machine learning models, including Decision Trees, Random Forest, and kNN, and evaluated their performance.
- **Arnav Singh:** Managed the project workflow, ensuring timely progress and integrating the various components into the final report.

## Conclusion

This project demonstrated the potential of machine learning models to predict Olympic outcomes based on historical data. While the models showed varying degrees of success, they also underscore the complexity of sports prediction. Future work could involve integrating more features, such as athletes' training regimes or recent performance metrics, to improve predictive accuracy.

As we move closer to the 2024 Olympics, these models could be further refined and used to generate insights and predictions that might be of interest to coaches, analysts, and sports enthusiasts. However, it's important to approach these predictions with caution, given the dynamic and unpredictable nature of sports competitions.
