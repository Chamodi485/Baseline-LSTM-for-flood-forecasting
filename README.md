# Baseline-LSTM-for-flood-forecasting

# Kelani River Flood Forecasting

> 6-hour ahead discharge prediction for Glencource station using LSTM + Physics-Informed Neural Network (PINN)

![Status](https://img.shields.io/badge/status-active%20development-brightgreen) ![Python](https://img.shields.io/badge/python-3.10-blue)

---

## Problem

The Kelani River basin in Sri Lanka experiences frequent flash flooding, putting thousands of downstream residents at risk. This project builds a deep learning pipeline that predicts **discharge at Glencource 6 hours ahead** using real-time upstream station data from Kithulgala, Norwood, and Deraniyagala.

---

##  Model Architecture

### Input Features (6 variables)
| Station | Features |
|---|---|
| Kithulgala | Discharge (Q), Rainfall (RF) |
| Norwood | Discharge (Q), Rainfall (RF) |
| Deraniyagala | Discharge (Q), Rainfall (RF) |

- **Lookback window:** 504 hours (21 days) — selected via lag correlation analysis
- **Forecast horizon:** 6 hours ahead
- **Two models:** Baseline LSTM + Physics-Informed LSTM (PINN)

---

## Results (Walk-Forward Cross Validation)

| Model | NSE | r | FHV (%) |
|---|---|---|---|
| Baseline LSTM | 0.894 | 0.950 | -17.0 |
| PINN-LSTM | 0.894 | 0.949 | -16.9 |

Walk-forward CV across 3 folds (val years: 2022, 2023, 2024).
NSE > 0.85 is considered **very good** for operational flood forecasting.

