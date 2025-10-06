# Multi-Date Remote Sensing Change Detection

## Overview
This project focuses on detecting changes in geographical areas using multi-date satellite imagery.  
The goal is to classify each area into one of six categories based on urban and geographical features, using machine learning techniques.

## Task
Classify each area into one of six classes:

| Class | Description    |
|-------|----------------|
| 0     | Demolition     |
| 1     | Road           |
| 2     | Residential    |
| 3     | Commercial     |
| 4     | Industrial     |
| 5     | Mega Projects  |

<img width="499" height="640" alt="image" src="https://github.com/user-attachments/assets/d12e00c4-0e9f-470e-9a4a-db6168da942c" />


## Data
Each instance represents an irregular polygon with associated features:  

- Categorical status over five dates (e.g., under construction, completed).  
- Neighborhood urban features (density, industrial areas, etc.).  
- Geographical features (proximity to rivers, hills, etc.).  

## Approach
The project follows a standard ML pipeline:

1. **Data Preprocessing**  
   Convert raw geo-data into usable formats.

2. **Feature Engineering**  
   - Generate features from polygon geometry (area, perimeter).  
   - Encode categorical variables (e.g., one-hot encoding).  
   - Compute temporal differences between dates.  
   - Optionally, apply dimensionality reduction or feature selection.

3. **Model Selection & Training**  
   - Tested multiple classifiers: k-NN, SVM, Random Forests, Neural Networks.  
   - Hyperparameter tuning and cross-validation were performed.  
   - Ensembles were explored to improve performance.

4. **Evaluation**  
   - Cross-validation on training data.  
   - Final assessment on Kaggle test set using **Mean F1-Score**.  

## Results
- Baseline k-NN model achieved ~40% F1-Score.  
- After feature engineering and model tuning, performance improved significantly.  
- Detailed experiments, feature combinations, and model comparisons are included in the code.

## Usage
1. Preprocess the dataset (`train.geojson`, `test.geojson`).  
2. Run the main script to train the model and generate predictions:

```bash
python main.py
