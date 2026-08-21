# Intelligent Load Forecasting

An LSTM-based time-series forecasting project for predicting resource allocation from historical system utilization, workload, and temporal patterns.

## 📌 Project Overview

Modern computing systems need to allocate resources efficiently according to changing workloads. Predicting future resource requirements can help systems make better resource allocation decisions and avoid unnecessary over-provisioning.

This project explores the use of **Long Short-Term Memory (LSTM)** neural networks to forecast future **Resource Allocation** using historical resource utilization and workload data.

The project focuses on:

- CPU utilization
- Memory usage
- Storage usage
- Workload
- Time-based features
- Historical resource allocation

The main objective is to investigate whether an LSTM model can learn temporal patterns from historical system resource data and improve forecasting compared with a simple statistical baseline.

---

## 🎯 Objectives

The project aims to:

1. Explore and understand resource utilization data.
2. Clean and preprocess missing and inconsistent values.
3. Extract useful temporal features from timestamps.
4. Build time-series sequences from historical observations.
5. Train an LSTM neural network for resource allocation forecasting.
6. Evaluate the model using standard regression metrics.
7. Compare the LSTM against a simple baseline.
8. Experiment with different historical sequence lengths.
9. Generate future resource allocation forecasts.

---

## 📊 Dataset

The dataset contains hourly observations of system resource utilization.

### Dataset Statistics

- **Observations:** 26,305
- **Time period:** January 2022 – January 2025
- **Frequency:** Hourly
- **Target variable:** `Resource Allocation`

### Features

| Feature | Description |
|---|---|
| `timestamp` | Date and time of the observation |
| `cpu_utilization` | CPU utilization level |
| `memory_usage` | Memory utilization level |
| `storage_usage` | Storage utilization level |
| `workload` | Workload level |
| `Resource Allocation` | Target variable to be forecast |

---

## 🔎 Data Exploration

The initial analysis included:

- Dataset shape and structure
- Data types
- Missing-value analysis
- Timestamp validation
- Duplicate timestamp detection
- Time-gap analysis
- Statistical summaries
- Temporal feature exploration
- Resource allocation distribution

The dataset contains hourly observations with a consistent one-hour time interval.

---

## 🧹 Data Preprocessing

The preprocessing pipeline includes:

1. Timestamp conversion
2. Chronological sorting
3. Missing-value identification
4. Missing-value handling
5. Temporal feature extraction
6. Feature preparation
7. Chronological train/validation/test splitting
8. Feature scaling

### Temporal Features

The timestamp was used to derive features such as:

- Hour of day
- Day of week
- Month
- Weekend/weekday information

These features allow the model to capture potential daily and weekly patterns.

---

## ⏱️ Time-Series Sequence Construction

Instead of treating each observation independently, historical observations are grouped into sequences.

Two sequence lengths were investigated:

### 168-hour sequence

```text
168 hours = 7 days