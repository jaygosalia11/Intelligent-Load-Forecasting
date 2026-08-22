# Intelligent Load Forecasting

An LSTM-based time-series forecasting project for predicting resource allocation from historical system utilization, workload, and temporal patterns.

## 📌 Project Overview

Modern computing systems need to allocate resources efficiently according to changing workloads. Predicting future resource requirements can help systems make better resource allocation decisions and reduce unnecessary over-provisioning.

This project uses a **Long Short-Term Memory (LSTM)** neural network to forecast **Resource Allocation** using historical system utilization, workload, and temporal information.

The project focuses on:

- CPU utilization
- Memory usage
- Storage usage
- Workload
- Hour of day
- Day of week
- Weekend/weekday information
- Historical resource allocation

The main objective is to investigate whether an LSTM model can learn temporal patterns from historical system resource data and improve forecasting compared with a simple statistical baseline.

---

## 🎯 Objectives

The project aims to:

1. Explore and understand system resource utilization data.
2. Clean and preprocess the dataset.
3. Extract useful temporal features from timestamps.
4. Construct time-series sequences from historical observations.
5. Train an LSTM neural network using a 168-hour historical window.
6. Evaluate the model using standard regression metrics.
7. Compare the LSTM against a simple mean-based baseline.
8. Visualize actual versus predicted resource allocation.
9. Analyze hourly and daily resource allocation patterns.
10. Generate a forecast for the next 24 hours.

---

## 📊 Dataset

The dataset contains hourly observations of system resource utilization.

### Dataset Statistics

- **Observations:** 26,305
- **Time Period:** January 2022 – January 2025
- **Frequency:** Hourly
- **Target Variable:** `Resource Allocation`

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

The initial exploratory analysis includes:

- Dataset shape and structure
- Data types
- Missing-value analysis
- Duplicate detection
- Timestamp validation
- Time-gap analysis
- Statistical summaries
- Feature distributions
- Outlier analysis
- Temporal pattern exploration
- Resource allocation analysis

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

The timestamp is used to derive:

- `hour` — hour of the day
- `day_of_week` — day of the week
- `is_weekend` — indicator for Saturday and Sunday

These features provide the model with information about daily and weekly temporal patterns.

---

## ⏱️ Time-Series Sequence Construction

The final LSTM model uses a **168-hour historical sequence**, representing seven days of previous observations.

```text
168 hours = 7 days




## 🛠️ Tech Stack

### Programming Language
- **Python**

### Data Processing & Analysis
- **Pandas** — data loading, cleaning, transformation, and analysis
- **NumPy** — numerical operations and array manipulation

### Data Visualization
- **Matplotlib** — time-series plots, distributions, and forecasting visualizations

### Machine Learning & Deep Learning
- **Scikit-learn** — data scaling and model evaluation metrics
- **TensorFlow / Keras** — LSTM model development, training, evaluation, and model loading

### Development Environment
- **Jupyter Notebook** — project development and experimentation
- **Python Virtual Environment (`.venv`)** — dependency isolation

### Version Control
- **Git** — source code version control
- **GitHub** — repository hosting and project management