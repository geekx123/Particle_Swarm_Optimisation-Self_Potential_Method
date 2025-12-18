## 📌 Overview

This repository presents a Particle Swarm Optimization (PSO)–based inversion framework for Self Potential (SP) data interpretation. The objective is to estimate subsurface source parameters by minimizing the misfit between observed SP data and forward-modeled responses. The workflow integrates physics-based geophysical modeling with nature-inspired optimization, making it suitable for exploration geophysics and data-driven subsurface characterization.

The implementation is provided as a Jupyter Notebook for transparency, reproducibility, and educational value.

## 🧠 Core Concepts Used
### 1. Self Potential (SP) Method

The Self Potential method is a passive geophysical technique that measures natural electric potential differences at the Earth’s surface. These anomalies are commonly associated with:

Electrochemical processes

Fluid flow through porous media

Sulfide mineralization

Geothermal and groundwater systems

In this repository, SP anomalies are modeled as responses from subsurface sources, and inversion is used to recover the governing parameters.

### 2. Forward Modeling

Forward modeling involves computing theoretical SP responses for a given set of subsurface parameters (e.g., source location, depth, intensity). This step establishes the physics-based link between the model space and the observed data space.

Mathematically:

Input: Model parameters

Output: Synthetic SP response

This synthetic response is later compared with observed data.

### 3. Inversion as an Optimization Problem

SP inversion is treated as a non-linear optimization problem, where the goal is to minimize a cost (loss) function defined as:

#### Misfit Function:
Measures the difference between observed SP data and forward-modeled SP data (typically using RMSE or L2 norm).

Due to the non-linearity and potential multi-modality of the solution space, classical gradient-based methods are often insufficient—motivating the use of PSO.

### 4. Particle Swarm Optimization (PSO)

PSO is a population-based stochastic optimization algorithm inspired by the social behavior of birds and fish schools.

Each particle represents a candidate subsurface model and has:

Position (model parameters)

Velocity (search direction)

Personal best (pBest)

Global best (gBest)

PSO is particularly effective for:

Non-linear problems

Multi-dimensional search spaces

Avoiding local minima

## ⚙️ Algorithmic Workflow
### Step 1: Initialization

Define search bounds for subsurface parameters.

Initialize a swarm of particles with random positions and velocities.

### Step 2: Forward Simulation

For each particle:

Compute the SP response using the forward model.

Compare it with observed SP data.

### Step 3: Fitness Evaluation

Calculate the misfit (loss function).

Update:

Particle’s personal best (pBest)

Global best (gBest)

### Step 4: Velocity and Position Update

Particle velocities and positions are updated using:

Inertia term (exploration)

Cognitive component (self-learning)

Social component (swarm learning)

This balances global exploration and local exploitation.

### Step 5: Iterative Optimization

Repeat Steps 2–4 for a fixed number of iterations or until convergence.

Track misfit reduction across iterations.

### Step 6: Final Output

Optimized subsurface parameters.

Best-fit SP response.

Convergence behavior of the optimization.

## 📈 Key Outcomes

Robust estimation of SP source parameters

Stable convergence without gradient information

Clear separation between physics (forward modeling) and optimization (PSO)

Extendable to joint inversion or hybrid ML–physics workflows

## 🔧 Technologies Used

Python

NumPy / Pandas – numerical computation and data handling

Matplotlib – visualization

Jupyter Notebook – reproducible experimentation

## 🚀 Applications & Extensions

Mineral and groundwater exploration

Geothermal prospecting

Joint inversion with gravity or resistivity data

Hybrid PSO + Machine Learning inversion schemes
