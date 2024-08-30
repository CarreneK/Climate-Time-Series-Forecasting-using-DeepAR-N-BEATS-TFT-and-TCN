# DeepAR, N-BEATS, TFT, and TCN

## Overview
This project implements and compares several state-of-the-art deep learning models for time series forecasting, specifically focusing on predicting daily climate metrics such as temperature. The project utilizes the DailyDelhiClimate dataset and explores the impact of different covariates on model accuracy. The models used include DeepAR, N-BEATS, Temporal Fusion Transformer (TFT), and Temporal Convolutional Network (TCN).

## Project Structure
The project is organized into three main files, each corresponding to different stages and models in the forecasting process:

### File 1: DeepAR and N-BEATS Implementation
- **Description**: This file contains the implementation of the DeepAR and N-BEATS models. It starts with basic data preprocessing, including scaling and splitting the data. The file then explores the impact of various covariates such as month, season, humidity, wind speed, and mean pressure on forecasting accuracy. Both models are optimized using grid search, and the results are compared using Mean Absolute Error (MAE) as the evaluation metric.
- **Key Functions**:
  - **DeepAR Model**: Implemented with and without covariates, evaluated using backtesting.
  - **N-BEATS Model**: Trained with varying covariate configurations and compared against the DeepAR model.
- **Output**: MAE scores for different covariate scenarios and a final comparison table.

### File 2: Temporal Fusion Transformer (TFT) Implementation
- **Description**: This file focuses on the Temporal Fusion Transformer (TFT) model, which is particularly well-suited for handling multiple covariates and capturing complex temporal dependencies. The file follows a similar structure to the first, but specifically tailors the model to utilize future covariates effectively. It includes detailed steps for data preparation, model training, and evaluation.
- **Key Functions**:
  - **TFT Model**: Implementation with basic and full covariates.
  - **Optimization**: Grid search for the best hyperparameters and evaluation of the model's performance.
- **Output**: MAE scores for different covariate scenarios, with a focus on how the TFT model handles these inputs.

### File 3: Temporal Convolutional Network (TCN) Implementation
- **Description**: This file contains the implementation of the Temporal Convolutional Network (TCN) model. The TCN model is designed to leverage past covariates for improved forecasting accuracy. The file includes steps for adding past climate data as covariates, training the TCN model, and evaluating its performance.
- **Key Functions**:
  - **TCN Model**: Built and optimized with a focus on using past covariates.
  - **Comparison**: The TCN model's performance is compared with that of the DeepAR, N-BEATS, and TFT models.
- **Output**: MAE scores for different covariate configurations and a final comparison table that includes the TCN model.

## Results
The project provides a detailed comparison of the four models across different covariate scenarios. Below is a summary of the key findings:

- **DeepAR**: Achieved the best performance with a full set of covariates, MAE = 0.0705.
- **N-BEATS**: Improved accuracy when using full covariates, MAE = 0.0688.
- **TFT**: Outperformed other models in handling complex covariates, MAE = 0.0615.
- **TCN**: Showed strong performance with past covariates, MAE = 0.1893.

## References
- [Darts Time Series Library Documentation](https://github.com/unit8co/darts)
- [DailyDelhiClimate Dataset on Kaggle](https://www.kaggle.com/datasets/sumanthvrao/daily-climate-time-series-data)

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
