This repo is implementing Random Forest Regressor on WHO epidemiological surveillance data (fluID dataset). The model achieved a Mean Absolute Percentage Error (MAPE) of 12.66%, meaning predictions deviated by about 13% on average from observed ILI counts.
The basis (Inputs) are past 4 weeks ILI cases (Lag_1 to Lag_4).
The below Time-Series plot shows the comparison of training data, actual data (test data), and Predictions over time made by the model. Random Forest captured the seasonal patterns and short-term trends but did not predict the peaks of the outbreak.

<img width="1190" height="630" alt="image" src="https://github.com/user-attachments/assets/49665f8d-7055-4678-bae5-73d94c79b3db" />

### Details about Dataset
Dataset is crucial part of machine learning training process. In fact, its the only way to get the preditions right. Even the most advanced model will perform poorly when trained on low-quality data. A less sophisticated model can outperform others when trained on high-quality data.

Here are some details about the dataset used:
1. Massive amount of missing values
**Significantly Missing (>90%):** PNEU_POP_COV (100% missing), GEOSPREAD_Comments, PNEU_INPIENTS, TREND, GEOSPREAD, etc.
**Moderately Missing (30-80%):** ILI_CASE, SARI_CASE, ARI_CASE

2. Inconsistent Categorical Data:
The AGEGROUP_CODE column is messy and inconsistent. It mixes different naming converntions and overlapping groups.
**For Example:**
ALL vs All (These should be merged).
Overlapping groups: 0TO4 vs 0TO1, 2TO4.
Specific vs General: 65TO vs 65TO74, 65TO79.

3. Data Types
**Date Columns:** ISO_WEEKSTARTDATE and MMWR_WEEKSTARTDATE are currently read as object (text).

4. Redundancy
**Duplicate/Similar Columns:** You have both ISO dates (ISO_WEEKSTARTDATE) and MMWR dates (MMWR_WEEKSTARTDATE). These often track closely but can differ slightly.
