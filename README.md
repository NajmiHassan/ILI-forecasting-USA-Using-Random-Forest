This repo is implementing Random Forest Regressor on WHO epidemiological surveillance data (fluID dataset). The model accuracy is 87.34% with Mean Absolute Percentage Error (MAPE) of 12.66%.
Input feature are past 4 weeks ILI cases (Lag_1 to Lag_4).
The below Time-Series plot shows the comparison of training data, actual data (test data), and Predictions over time made by the model. Random Forest captured the seasonal patterns and short-term trends but did not predict the peaks of the outbreak.
<img width="1190" height="630" alt="image" src="https://github.com/user-attachments/assets/49665f8d-7055-4678-bae5-73d94c79b3db" />
