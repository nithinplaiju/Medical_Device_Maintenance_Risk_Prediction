# Medical Device Maintenance Risk Prediction

## Project Overview
This project predicts the maintenance risk level of medical devices (Low, Medium, or High) using machine learning, based on device usage and cost data.

## Objective
To help hospitals and medical facilities identify which devices are likely to need urgent or costly maintenance, so they can prioritize inspections and repairs before a device fails.

## Technologies Used
- Python
- Google Colab
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Seaborn

## Dataset
- Source: Kaggle - Medical Device Failure Dataset 
- 4,149 medical devices (X-Ray Machines, MRI Scanners, PET Scanners, Infusion Pumps, Defibrillators, CT Scanners)
- 13 columns including Age, Manufacturer, Maintenance Cost, Downtime, Maintenance Frequency, and Failure Event Count

## Project Workflow
1. Data Collection
2. Data Cleaning
   - Checked for missing values (none found)
   - Found and corrected 105 rows with negative Maintenance_Cost values (converted to absolute value, as negative maintenance cost is not realistic)
3. Data Analysis (Exploratory Data Analysis)
   - Used boxplots to check for outliers in Maintenance_Cost and Downtime
   - Compared Maintenance_Cost, Downtime, Maintenance_Frequency, and Device_Type across the three risk classes to identify which features are useful predictors
4. Model Training
   - Selected Age, Maintenance_Cost, and Downtime as features (Maintenance_Frequency and Device_Type were dropped after analysis showed minimal relationship with risk class)
   - Split data: 80% training, 20% testing
5. Prediction
6. Evaluation

## Files in this Repository
- notebooks -> Google Colab notebook
- data -> Dataset
- README.md -> Project documentation

## Key Insight
Maintenance_Cost and Downtime showed a clear, strong relationship with a device's risk class - devices with higher maintenance cost and longer downtime were much more likely to be classified as high risk. In contrast, Maintenance_Frequency and Device_Type showed little to no relationship with risk class, so they were excluded from the final model.

## Model Used
- Random Forest Classifier

## Model Performance
Accuracy: 73.86%

| Class | Precision | Recall | F1-score | Support |
|-------|-----------|--------|----------|---------|
| 1 (Low risk) | 0.74 | 0.82 | 0.77 | 282 |
| 2 (Medium risk) | 0.66 | 0.66 | 0.66 | 287 |
| 3 (High risk) | 0.84 | 0.74 | 0.78 | 261 |

## Future Improvements
- Try additional features and models to improve accuracy
- Apply hyperparameter tuning
- Test additional models (e.g. Decision Tree, KNN) for comparison

## Author
Nithin P Laiju