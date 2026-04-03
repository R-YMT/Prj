# AEP Hourly Energy Load Forecasting with LSTM

Predicting hourly energy consumption using a Long Short-Term Memory (LSTM) 
neural network trained on 13 years of AEP (American Electric Power) data. 
This project demonstrates how deep learning can model complex temporal patterns 
in energy systems, with direct applications to AI-driven load management in 
data centers and power grids.

## Results

| Model | RMSE (MW) | MAE (MW) |
|-------|-----------|----------|
| Persistence Baseline | 525.58 | 407.64 |
| LSTM (this work) | 222.44 | 163.37 |

The LSTM reduces RMSE by 57% and MAE by 60% over the naive baseline, 
representing ~1.4% average error relative to mean consumption (~15,500 MW).

## Dataset

- **Source:** [AEP Hourly Energy Consumption](https://www.kaggle.com/datasets/robikscube/hourly-energy-consumption)
- 121,273 hourly readings from October 2004 to August 2018
- Single feature: energy consumption in megawatts (MW)
- No missing values

## Model Architecture

- 2-layer LSTM with 64 hidden units and 0.2 dropout
- Fully connected output layer
- Input: 24-hour sliding window
- Output: next hour's energy consumption
- Optimizer: Adam (lr=0.001)
- Loss: MSE
- Epochs: 30

## Project Structure
```
├── data/
│   └── AEP_hourly.csv
├── aep-energy-load-forecasting-lstm.ipynb
├── lstm_aep_model.pth
└── README.md
```
