# Classifying Political Spectrum through Opinions

---

This project focuses on using the classification method in machine learning to predict the political sides of participants based on stances on local issues and other important factors.
My interest in analyzing and exploring the issues of elections, socio-economics, and global politics has brought me to do this project.

## Dataset
The dataset can be found on Kaggle. The data's contents are in Turkish, and translation into other languages can be possible.

## Objectives
The following are the objectives for the project:
1. Determine the composition of the data (i.e., number and/or share of participants based on age, sex, residency, educational background, and the political views [represented as political parties] the participants are aligned)
2. Determine the percentage/share of participants' opinions on each political issue asked.
3. Compare different machine learning classification models and obtain their accuracies and other relevant metrics.
4. Classify the political views of participants of which the political views were listed as 'Others'

## Data Limitation
The dataset is hugely imbalanced; while removing the participants with views tagged as 'Others,' the participants having conservative views outnumber those with liberal/progressive ones (671 conservative and 400 liberal affiliations).

## Methodology
Exploratory data analysis was conducted to examine the composition of the variables and identify any discrepancies or indications that might affect model performance in the machine learning phase.

### Categorizing the affiliations
The political affiliations of participants are originally represented by the political parties they associate themselves with, and they were categorized according to the ideologies or leanings of the party (e.g. a party is leaning to the side of traditional/conservative or liberal/progressive).

### Model Development
Eight models were created for this project, combining various classification and ensemble methods, of which were configured into their optimal settings and tested on the original imbalanced dataset.

### Addressing Imbalance
Given the data imbalance, the SMOTE-ENN resampling technique was applied to test the accuracy and reliability of the models further. This aimed to ensure the models could generalize weel and were not biased toward the majority class.

### Evaluating the Models
The models were evaluated using metrics used for classification (accuracy, recall, precision, and f1-scores). In assessing potential overfitting, a comparison of training and testing accuracies was performed, both on the original and resampled datasets, as well as the general accuracy for both data. Learning curve and cross-validation was also used to see if the model performs consistently across different subsets of data.

### Prediction on Unlabeled Data
The data identified is the subset of the whole dataset but with political affiliations labeled as 'Others', which originally means other (non-major) political parties participants affiliate themselves with.

## Results

### Model Comparison
All models showed significant improvements in accuracy when tested on the resampled data compared to the original dataset. The Decision Tree had the lowest accuracy on the original data but improved dramatically with resampling, increasing by almost 18 percentage points. SVC had the least improvement and the lowest accuracy on the resampled data, with an 8 percentage point increase, reaching 77.7% accuracy.

Neural Networks achieved the highest accuracy on the original data and showed considerable improvement after resampling, matching the accuracy of the Gradient Boosting model. However, Neural Networks exhibited a higher risk of overfitting, as indicated by the learning curve and cross-validation results on the resampled data.

In terms of distinguishing classes, Gradient Boosting had a perfect AUC score of 1.00, indicating optimal class separation, while KNN achieved an AUC of 0.97. Although KNN had a higher average precision (AP) of 0.93 compared to Gradient Boosting's 0.91, the Gradient Boosting model demonstrated a narrower gap between training and cross-validation scores, suggesting better generalization and less overfitting.

Overall, despite KNN's higher AP, the Gradient Boosting model was chosen for its superior performance in class discrimination (perfect AUC score) and lower overfitting risk, making it the most reliable choice for this project.

### Prediction
For 290 participants with political affiliations labeled as 'Others,' the Gradient Boosting model predicted 111 with possible leanings towards liberal/progressive ideals and 179 with possible traditional/conservative leanings. This distribution is consistent with the original data, which includes 400 liberals and 671 conservatives.

The predictions were evaluated through learning curve and cross-validation, including the assessment of standard deviations, reflecting the model's reliability and consistency in categorizing participants. The similarity in the distribution of predicted affiliations to the original data indicates that the model is well-calibrated and generalizes effectively to unseen data.

The distribution of the participants' possible affiliations may be attributed to the imbalance in the original dataset, however, the similarity in distribution may also indicate that the model is well-calibrated and generalize well on unseen data.

---

Feel free to leave comments, feedback, and suggestions on what could be improved in the project.
