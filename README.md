# Rare Event Estimation in Quality Control using Simulation

##  Project Overview
This project focuses on simulating and estimating **Rare Events** (events with very low probabilities, typically $< 5\%$) using advanced statistical simulation techniques. The project evaluates the pH level of a Water Potability dataset to predict extreme acidic or alkaline critical conditions.

##  Methodologies Implemented
This repository contains the mathematical justification and Python implementation of three core simulation algorithms:

1. **Accept-Reject Algorithm (Distribution Fitting):**
   - Fitted a Gamma distribution as the target analytical model.
   - Utilized a Laplace distribution as the proposal (envelope) due to its heavy tails.
   - Achieved a highly efficient theoretical and practical acceptance rate of ~75%.

2. **Standard Monte Carlo (SMC):**
   - Simulated $10^6$ samples to estimate the probability of the rare event.
   - Demonstrated the inherent inefficiency (high relative variance and wasted computational resources) of SMC for rare events.

3. **Importance Sampling (IS):**
   - Shifted a Laplace proposal distribution directly into the critical region ($\mu = 10$).
   - Calculated likelihood ratios (Importance Weights) to correct the bias.
   - **Result:** Successfully reduced the Standard Error to $10^{-6}$ using only $10^4$ samples, achieving a massive variance reduction and a $100x$ increase in computational efficiency compared to SMC.

##  File Structure
* `water_potability.csv`: The raw dataset used for empirical analysis.
* `Simulation_Rare_Events.ipynb`: The Jupyter Notebook containing all Python codes, visualizations (Log-Log plots), and algorithms built from scratch without using direct generator libraries.
* `Project_Requirements.pdf`: The original assignment constraints and analytical questions.
* `Final_Report.pdf`: Comprehensive Persian report detailing mathematical proofs, convergence analysis, and responses to analytical questions.

##  Key Results
The **Log-Log plot** of the Standard Error vs. Sample Size ($N$) mathematically proves that while both SMC and IS share the same convergence rate of $\mathcal{O}(N^{-0.5})$, Importance Sampling drastically reduces the initial variance (y-intercept), making it the only viable solution for rare-event simulations.

---
*Developed as a University Project for Computer Simulation Course.*
