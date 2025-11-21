# Profit Maximization with Pyomo

The goal of the notebook is to **maximize profit** by determining the optimal allocation of resources across different advertising decisions, using mathematical optimization.

---

## 📌 Overview

The notebook includes:

- A tabulated dataset describing revenue per user, cost per user, conversion rate, and potential user volume for each advertisement type (A, B, C, D) across quarters (Q1–Q4).
- Mathematical formulation of the optimization problem using:
  - **Decision sets**
  - **Parameters**
  - **Objective function**
  - **Constraints**
- Implementation using:
  - **Pyomo** as the modeling library
  - **GLPK** as the solver

---

## 🧮 Mathematical Model (Summary)

### Sets
- Advertisement types  
  `AD = [A, B, C, D]`
- Quarters  
  `Q = [Q1, Q2, Q3, Q4]`

### Objective
Maximize total profit across all advertisement types and quarters.

### Constraints
- Demand constraints  
- Spending restrictions  
- Logical structure of decisions based on the dataset

(See notebook for full formulations.)

---

## 🛠 Technologies Used
- Python  
- Pyomo  
- GLPK Solver  
- Jupyter Notebook  

---

## ▶️ How to Run

1. Install dependencies:
   ```bash
   pip install pyomo
   sudo apt-get install glpk-utils
