# Data Generation using Modelling and Simulation for Machine Learning

## Overview
This project demonstrates how modelling and simulation can be used to generate synthetic data for machine learning.  
A **manufacturing production line queue system** was simulated using discrete-event simulation, and the generated data was used to train and compare multiple machine learning models.

The objective is to learn the relationship between system parameters and system performance (**average waiting time**) using simulated data.

---

## Simulation Domain
**Manufacturing Production Line Queue System**

A stochastic manufacturing system was simulated where:

- Jobs arrive randomly  
- Multiple machines process jobs  
- A finite buffer limits queue length  
- Waiting time depends on system configuration  

The simulation was implemented using the **SimPy** library in Python.

---

## Methodology

The workflow follows:

**Modelling → Simulation → Data Generation → Machine Learning → Evaluation**

---

### Step 1: Define Parameters and Bounds

| Parameter | Description | Range |
|----------|-------------|------|
| arrival_rate | Job arrival rate | 0.5 – 2 jobs/min |
| service_rate | Machine service rate | 1 – 3 jobs/min |
| num_machines | Number of machines | 1 – 5 |
| buffer_size | Queue capacity | 5 – 20 |
| sim_time | Simulation duration | 200 – 500 min |

**Target variable:** Average waiting time

---

### Step 2: Simulation-based Data Generation

For each simulation run:

1. Random parameters sampled within bounds  
2. Manufacturing system simulated using SimPy  
3. Average waiting time recorded  

Total simulations executed:

1000

Generated dataset saved as:

simulation_data.csv

---

### Step 3: Machine Learning Models

The simulated dataset was used to train and compare the following regression models:

- Linear Regression  
- Ridge Regression  
- Lasso Regression  
- Decision Tree Regressor  
- Random Forest Regressor  
- Gradient Boosting Regressor  
- Support Vector Regressor (SVR)  
- K-Nearest Neighbors (KNN)  

---

### Step 4: Evaluation Metrics

Models were evaluated using:

- RMSE (Root Mean Squared Error)  
- MAE (Mean Absolute Error)  
- R² Score  

Model comparison results saved as:

model_result.csv

---

## Results

Model comparison showed that **Random Forest Regressor achieved the lowest RMSE**, indicating the best prediction accuracy.

Tree-based ensemble models performed better because the manufacturing queue system exhibits nonlinear dynamics and parameter interactions.

The trained models successfully learned the relationship between:

System Parameters → Average Waiting Time

---

## Visualization

The RMSE comparison graph generated from the experiment shows that **Random Forest** achieved the lowest prediction error among all tested models.

---

## How to Run

1. Open manufacturing_simulation.ipynb in Google Colab  
2. Run all cells  
3. Generated outputs:
   - simulation_data.csv  
   - model_result.csv  

---

## Tools & Libraries

- Python  
- SimPy  
- NumPy  
- Pandas  
- Scikit-learn  
- Matplotlib  

---

