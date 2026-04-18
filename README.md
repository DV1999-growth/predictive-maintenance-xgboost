# Predictive Maintenance using XGBoost

This project predicts machine failure using sensor data such as temperature, torque, rotational speed, and tool wear.

## Dataset

This project uses the AI4I 2020 Predictive Maintenance Dataset.

Dataset is not included due to licensing restrictions.

Download it from:
https://www.kaggle.com/datasets/shivamb/ai4i2020-predictive-maintenance-dataset

After downloading, place the CSV file inside the `data/` folder.

## Model

- Model used: XGBoost
- Handled class imbalance using `scale_pos_weight`
- Tuned classification threshold to improve recall

## Results

Final model performance at threshold = 0.75:

- Precision: 0.63  
- Recall: 0.81  

Confusion Matrix:

[[1900   32]
 [  13   55]]