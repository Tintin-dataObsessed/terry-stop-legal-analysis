# Terry Stop Legal Analysis and Prediction
Analysis of the landmark 1968 U.S. Supreme Court case Terry v. Ohio, which established the legal standard of "reasonable suspicion" and introduced the concept of Terry Stops.

The aim is to analyse the Police Department data to build a model that predicts whether an arrest happened after a Terry Stop, using details like whether a weapon was present and the time of the stop. This is a binary classification task, which means to arrest or not arrest.

# Background
The Fourth Amendment is meant to protect people from being searched or arrested without a good reason. It says that the government can’t do “unreasonable searches and seizures,” which means police need a solid reason—and often a warrant—before they can take you into custody. Reasonable suspicion is a concept that came out of the Terry v. Ohio case. It gives police the right to stop and briefly question someone if they think something suspicious is happening, even if they don’t have enough evidence to arrest them yet.

# Legal and Data Understanding
This project explores the 1968 U.S. Supreme Court case Terry v. Ohio, which introduced the legal concept of reasonable suspicion and established the framework for what are now known as Terry Stops. Using real police department data, this project builds a binary classification model to predict whether an arrest occurred after a Terry stop, based on details such as the presence of a weapon, time of stop, age, and gender of the subject.

This project aims to analyze and evaluate the use of Terry Stops by addressing the following goals:

- Examine whether factors like gender, age, and reason for the stop influence the likelihood of an arrest.
- Build a machine learning model that balances accuracy with fairness and justice.
- Identify potential patterns or biases in stop-and-arrest decisions.
- Investigate the presence of disparities in arrests based on demographic variables.

The dataset used is from the Seattle Police Department. This data represents records of police reported stops under Terry v. Ohio, 392 U.S. 1 (1968). Each row represents a unique stop.
https://data.seattle.gov/Public-Safety/Terry-Stops/28ny-9ts8/about_data

# Data Preparation and Preprocessing

- Checked for null values, duplicate rows, and corrected data types for consistency.
- cleaning of categorical variables (e.g., age groups, gender labels).
- Explored feature distributions:
- The most common age group was 26–35 years old.
  - The majority of stops involved males.
  - The most frequent origin of stops was 911 calls, followed by on-view observations by officers.

# Modeling and Evaluation
I used two classification models:

- Logistic Regression

- Decision Tree Classifier

These models were chosen because:
- Both are well-suited for binary classification problems.
- They offer interpretable results, important in legal and policy contexts.
- Features used: Call type (911 or on-view), Subject age group, Subject gender

Model Evaluation:
- Both models achieved an accuracy of approximately 0.48.
- The confusion matrices revealed: High precision for the "Not Arrested" class and High recall for the "Arrested" class.


# Recommendations
To help review and update policies, to detect bias patterns, and in Training and Awareness for the community.

# Conclusion

The data was highly imbalanced however, considering how this is based on arrests in the Chicago area and the nature of police work ,it is not considered abnormal to have a large number of Not Arrested in favour of Arrested.

Given the context of predictive policing and civil rights, precision and recall for the Arrested are our most important metrics. Recall must be maximized to understand all potential arrests, but also to improve precision to avoid falsely predicting arrests, which could lead to bias.

The evaluation metrics showed the model predicted "Not Arrested" cases well, with no false negatives and a high number of true negatives. However, it struggled to correctly identify actual arrests, resulting in a low number of true positives and a high number of false negatives. This means the model made both Type I errors (false positives) and Type II errors (false negatives), although Type II errors were more pronounced.

These findings highlight the difficulty of predicting arrests in an imbalanced dataset and suggest the need for further refinement, possibly through better feature selection, alternative models, or fairness-aware techniques.