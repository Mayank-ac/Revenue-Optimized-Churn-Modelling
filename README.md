# Decision-Focused Churn Modeling for Retention Optimization

This project reframes traditional churn prediction as a **retention decision problem**.  
Instead of optimizing for AUC or accuracy alone, it focuses on **maximizing net revenue under a fixed incentive budget** by deciding *which customers to target* and *which strategy to use*.

## 🚀 Project Overview

Most churn models rank customers purely by churn probability. In practice, retention teams face real constraints:
- Limited incentive budgets
- Varying customer lifetime value (LTV)
- Uncertain offer acceptance rates

This project addresses those constraints by combining:
- **Calibrated churn risk**
- **Customer lifetime value (LTV)**
- **Simulation of retention strategies**

into an **expected-value decision framework** for retention targeting.

## 🧠 Core Idea

> Not all churners are worth saving.

Customers are ranked by **expected economic impact** rather than churn risk alone:

\[
\text{Expected Value} = P(\text{churn}) \times P(\text{accept offer}) \times \text{LTV} - \text{Incentive Cost}
\]

Retention actions are then simulated under realistic budget limits.

## 📊 Methods

### 1. Churn Modeling
- Models: Logistic Regression, Gradient Boosting
- Time-based train/validation splits to prevent leakage
- Probability calibration for decision-making use cases

### 2. Customer Value Estimation
- Estimated customer lifetime value (LTV)
- Used to weight churn risk by economic importance

### 3. Retention Simulator
A simulation framework was built to compare multiple strategies:
- **No action**
- **Random targeting**
- **Risk-only targeting** (highest churn probability)
- **Risk × Value targeting** (expected-value ranking)

Simulations were run across:
- Different incentive budgets
- Varying offer-acceptance probabilities

## 📈 Key Results

- **Risk × Value targeting increased net revenue by ~20–30%**
- **Cost per retained customer reduced by ~15–25%**
- Improvements held consistently across budget sizes and acceptance-rate assumptions

This demonstrates that **decision-focused modeling outperforms metric-focused churn prediction** in real retention settings.

## 🛠 Tech Stack

- Python
- pandas, numpy
- scikit-learn
- Gradient Boosting models
- Simulation-based evaluation

## 📁 Repository Structure

