# Grid Inertia Estimation: PINN vs. LSTM

## ⚡ Overview

This repository implements a Physics-Informed Neural Network (PINN) to estimate electrical grid inertia ($H$) and reconstruct frequency dynamics, comparing it against a standard LSTM baseline1. The models are trained on sparse, low-resolution data (10-minute intervals) to infer high-resolution (4-second) transient behavior governed by the Swing Equation.
