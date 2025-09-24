<<<<<<< HEAD
# ⚡ Practical Lab 1: Streaming Data for Predictive Maintenance with Linear Regression-Based Alerts

## 🧠 Context

This lab builds on the Data Streaming & Visualization Workshop, where we learned to stream, store, and visualize industrial current data. In this extension, we implement a regression-based anomaly detection system to proactively identify deviations in current readings — simulating a predictive maintenance scenario for manufacturing robots.

The goal is to detect early signs of torque tube failure by flagging abnormal current behavior before breakdowns occur, reducing costly downtime and improving equipment reliability.

---

## 👤 Author

**Vishnu Sivaraj**  

---

## 🚀 System Overview

The system architecture includes:

1. **Data Source**: Real and synthetic current readings from robot controllers
2. **Streaming Layer**: Simulated time-series data using pandas and NumPy
3. **Regression Engine**: Linear regression models trained per axis
4. **Anomaly Detection**: Residual-based alert/error logic using z-score thresholds
5. **Visualization Layer**: Matplotlib plots with alert/error overlays
6. **Logging Layer**: CSV-based event log for flagged anomalies

---

## 📋 Requirements

- Python 3.10 or 3.12
- Jupyter Notebook
- pandas 2.2.0
- matplotlib
- seaborn
- scikit-learn
- numpy
- (Optional) `os` and `datetime` for file handling and timestamping
- `psycopg2` or `psycopg2-binary` for PostgreSQL connection
- An active [Neon.tech](https://neon.tech) project and database connection string



---

##  🎯  How to Run

1. Clone this repo
2. Install Required Dependencies: "pip install -r requirements.txt"
3. Configure Database Access
      - Create a .env file in the project root directory
      - Add your Neon PostgreSQL connection string in the following format:
         DATABASE_URL=postgresql://your_neon_connection_string
4. Run the Jupyter notebook cells sequentially 
5. Review Outputs


## 📐 Regression & Alert Rules

This system uses linear regression to model expected current readings over time for each axis. The goal is to detect deviations that may signal early signs of equipment failure.

🔧 Regression Model
- A separate linear regression model is trained for each axis (Axis1 to Axis8) using standardized current readings vs elapsed time.
- Training data is cleaned, normalized (0–1), and standardized (z-score) to match the synthetic test data pipeline.

📊 Residual Calculation
- Residual = Actual Reading − Predicted Reading
- Residuals are calculated in z-score space, making them statistically interpretable.

🚨 Alert/Error Logic
- Alert: Triggered when residual exceeds 1.5 × std for ≥ 6 seconds
- Error: Triggered when residual exceeds 3.0 × std for ≥ 6 seconds
- Events are logged with:
- Axis name
- Start and end timestamps
- Type (Alert or Error)
- Duration


## 📊 Plots of Results

Axis1 with Alerts/Errors

This plot compares actual vs predicted readings for Axis1. A red vertical line marks the point where an error was detected based on residual thresholds.

![alt text](<plots/Axis1 error.png>)


## Licence


##  🤝 Contributing 
This lab was completed individually by Vishnu Sivaraj for CSNC8010. For questions or feedback, feel free to reach out directly.
=======
# Streaming-Data-for-Predictive-Maintenance-with-Linear-Regression
A regression-based anomaly detection system for predictive maintenance. Streams industrial current data from a Neon PostgreSQL database, applies linear regression per axis, and flags deviations as alerts or errors. Includes real-time visualization and event logging to simulate early fault detection in manufacturing robots.
>>>>>>> 6f64868cf1b290715b47de3dc457ffcd57f672f9
