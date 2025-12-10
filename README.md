# Grid Inertia Estimation: PINN vs. LSTM

## ⚡ Overview

This repository implements a Physics-Informed Neural Network (PINN) to estimate electrical grid inertia ($H$) and reconstruct frequency dynamics, comparing it against a standard LSTM baseline1. The models are trained on sparse, low-resolution data (10-minute intervals) to infer high-resolution (4-second) transient behavior governed by the Swing Equation.

## 🛠️ Tech Stack

* Python 3.x
* TensorFlow: Neural network architecture and automatic differentiation.
* Pandas/NumPy: Data ingestion and preprocessing.

## 📂 Code Structure

* `Data gathering.ipynb`: Fetches generation data (ESIOS API), performs linear interpolation, and injects Gaussian noise ($\sigma=1\%$) for augmentation.
* `Synthetic data generation - Electrical grid frequency.ipynb`: Solves the continuous damped Swing Equation to generate "Ground Truth" frequency labels.
* `pinn_model.ipynb`: Implements the MLP (5 layers, 50 neurons, Tanh) where Inertia ($H$) is a trainable variable updated via the physics residual.
* `lstm_model.ipynb`: Baseline RNN architecture (128 units + Dense layers).
