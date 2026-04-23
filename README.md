#  EAF Energy Optimization Tool  

##  Overview  
This project presents a machine learning driven decision support tool for optimizing **Electric Arc Furnace (EAF)** operations. The objective is to minimize **specific energy consumption (kWh/t)** while maintaining realistic and balanced operating conditions.  

The model integrates **process knowledge, synthetic data generation, regression modeling, and penalty based optimization** to recommend practical operating strategies for steelmaking.

---

## ⚙️ Problem Statement  
EAF energy efficiency is influenced by multiple interacting variables such as:

- Scrap quality  
- Hot heel fraction  
- Oxygen injection  
- Carbon addition  
- Electrical operating level  

Traditional optimization approaches may push these variables to extreme values. This project addresses that limitation by introducing a **balanced optimization framework** that reflects real operational constraints.

---

##  Methodology  

### 1. Dataset Development  
A synthetic dataset was generated based on realistic EAF operating ranges and metallurgical relationships. Each row represents a single furnace heat scenario.

### 2. Machine Learning Models  
Three regression models were evaluated:

- Linear Regression  
- Random Forest Regressor  
- XGBoost Regressor  

**XGBoost** achieved the best performance and was selected for optimization.

### 3. Model Evaluation  
- RMSE (primary metric)  
- R² score (supporting metric)  

### 4. Optimization Approach  
A **penalty-based objective function** was introduced:

- Minimize predicted energy consumption  
- Penalize excessive use of oxygen, carbon, and power  

This ensures realistic and operationally feasible recommendations.

---

##  Optimization Objective  

The optimization balances:

- Low energy consumption  
- Moderate oxygen usage  
- Moderate carbon injection  
- Reasonable electrical operating levels  

---

##  Key Results  

- XGBoost achieved strong predictive performance (RMSE ≈ 7.21, R² ≈ 0.886)  
- Optimal operation occurs in a **balanced region**, not at extreme values  
- Typical optimized ranges:  
  - Carbon: ~11–13 kg/t  
  - Oxygen: ~28–34 Nm³/t  
  - Power level: ~400–450 kWh/t  
- Optimization shows that EAF efficiency depends on **coordinated control of multiple variables**  
- Scenario analysis confirms that optimal settings vary with furnace conditions  

---

##  Scenario Analysis  

Multiple operating scenarios were evaluated by fixing:

- Scrap quality  
- Hot heel fraction  and optimizing controllable variables.

This demonstrates:

- Condition dependent optimization  
- Practical decision-making support for operators  

---

##  Limitations  

- Dataset is synthetic and based on assumed relationships  
- Penalty weights are manually defined  
- Model does not capture dynamic furnace behavior  
- Power variable represents an operating proxy rather than true grid power   

---

##  Future Improvements  

- Integration of real industrial EAF data  
- Multi-objective optimization (energy, cost, emissions)  
- Dynamic process modeling (time-dependent behavior)  
- Data-driven tuning of penalty weights  
- Deployment as a real-time decision-support tool  

---

##  Engineering Insight  

> Effective EAF optimization is not achieved by maximizing inputs, but by balancing energy efficiency with controlled resource usage under realistic operating constraints.

