# Multi-Period Hospital Resource Optimization

This project formulates and solves a **large-scale linear optimization problem** for hospital resource allocation across multiple departments, shifts, and resource types.

---

## ✨ Overview

The notebook models a realistic **hospital operations planning** scenario in which limited human and operational resources must be allocated efficiently over a full week.

Using **Pyomo**, the project:

- Defines a **multi-period, multi-department** optimization problem
- Models **supply, demand, and capacity constraints**
- Solves both a **continuous (relaxed)** and an **integer (realistic)** version of the model
- Derives and analyzes the **dual problem**
- Compares objective values to study **integrality gaps**
- Interprets results using **operations research concepts** such as shadow prices

The focus is on **modeling clarity, mathematical structure, and interpretability**, not on ad-hoc heuristics.

---

## 🧠 Problem Description

### Context  
As Director of Operations Research, the task is to allocate hospital staff and support resources efficiently while:

- Meeting minimum patient demand
- Respecting limited resource availability
- Operating under budgetary and logistical constraints
- Handling different departments and time shifts

### Dimensions of the Model

- **Departments**: ER, ICU, Surgery, Hospital Floors, Outpatient Clinics  
- **Resources**: Doctors, Nurses, Maintenance, Administrative staff  
- **Shifts**: Morning and afternoon shifts across weekdays and weekends  

---

## 🎯 Objective

Maximize overall operational efficiency by optimizing the allocation of resources across departments and shifts, subject to:

- Supply limits  
- Minimum demand requirements  
- Department-specific needs  
- Non-negativity and integrality constraints  

---

## 🧮 Optimization Models

### 1. Primal (Continuous) Model
- Decision variables are **continuous**
- Provides an **upper bound** on achievable performance
- Useful for theoretical benchmarking

### 2. Integer Model
- Decision variables must be **whole units**
- Represents **realistic operational constraints**
- Produces implementable solutions

---

## 🔁 Dual Problem

The dual formulation is derived to:

- Verify **strong duality**
- Interpret **shadow prices**
- Measure the marginal value of:
  - Additional resources
  - Relaxed demand constraints
  - Increased capacity

This provides economic insight into **which constraints are most critical**.

---

## 📊 Key Results

- The **relaxed solution dominates** the integer solution, as expected
- The difference between them quantifies the **integrality loss**
- The gap reflects real-world limitations (e.g., you cannot hire 0.7 nurses)
- Dual variables offer clear operational interpretations for decision-makers

---

## 🧰 Technologies Used

- **Python 3**
- **Pyomo**
- **pandas**
- **NumPy**
- **Linear / Mixed-Integer Optimization Solvers**

---

