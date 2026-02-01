Closed-Loop Capacity Optimization with Predictive Control

Overview:
Modern cloud systems must balance two competing goals: minimizing infrastructure cost and avoiding SLA violations caused by under-provisioning. Most production systems rely on reactive capacity planning, which responds to demand after it occurs. This approach leads to delayed reactions, instability during demand spikes, and excessive safety buffers.

This project presents a closed-loop predictive capacity control framework that combines time-series forecasting with proactive provisioning. Capacity decisions are driven by short-term demand forecasts, creating a feedback loop between prediction, action, and observed system behavior. The goal is to reduce SLA violations while maintaining efficient resource usage.

The system is evaluated under multiple stress scenarios to demonstrate robustness, scalability, and cost-efficiency.

Key Results:

Scenario: Normal
	Baseline SLA: 0.48
	Predictive SLA: 0.28
	Improvement: 42% reduction

Scenario: Demand Spikes
	Baseline SLA: 0.54
	Predictive SLA: 0.23
	Improvement: 57% reduction

Scenario: High Noise
	Baseline SLA: 0.53
	Predictive SLA: 0.39
	Improvement: 27% reduction

Scenario: Lag = 7 days
	Baseline SLA: 0.53
	Predictive SLA: 0.16
	Improvement: 71% reduction

A key observation is that the predictive controller becomes more valuable as provisioning delays increase, indicating strong robustness in challenging operating conditions.

Main Figure:
	Cost vs SLA tradeoff across scenarios is available in:
	reports/figures/frontiers.png


How to Reproduce:
Create a virtual environment and install dependencies:

	python3 -m venv .venv
	source .venv/bin/activate
	pip install -r requirements.txt

Launch Jupyter:
	jupyter notebook

Open the notebook:
	notebooks/01_data_exploration.ipynb

All generated outputs are saved under:
	reports/tables
	reports/figures

Repository Structure:
	data
	notebooks
	src
	reports
	figures
	tables

Planned Extensions:
	Probabilistic demand forecasting
	Automatic buffer tuning
	Reinforcement learning based control
	Multi-region capacity simulation
	
	
Author:
Rajesh Khanna Bolloju
# closed-loop-capacity-optimization
