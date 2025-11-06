🦠 QSIR: Universal Differential Equation Model for COVID-19 (Italy)

This project implements a Universal Differential Equation (UDE) based on the classical SIR epidemiology model, enhanced with a Lux.jl neural network to learn the hidden quarantine strength 
𝑄
(
𝑡
)
Q(t) directly from real COVID-19 case data.
The goal is to build a data-driven, interpretable model that can reconstruct infection trends and understand the effect of policy interventions such as lockdowns.

📘 Project Overview

Traditional SIR models cannot represent quarantine dynamics or rapid behavioral changes during a pandemic.
This project augments the SIR differential equations with a neural network term, creating a Universal Differential Equation (UDE) that:

Learns the quarantine function 
𝑄
(
𝑡
)
Q(t) directly from data

Improves predictions for infected, recovered, and quarantined populations

Produces an interpretable signal showing when policies took effect

Allows comparison between model-learned inflection points and real lockdown timings

The project uses Italy’s COVID-19 data (Infected, Recovered, Dead) from the Johns Hopkins dataset.




## How to Run (Quick)

- Install the latest version of Julia (1.10+ recommended).
- Clone this repository and open it in a terminal.
- Add the required libraries:
  - If the repo has `Project.toml`:
    - Run: `julia --project -e 'using Pkg; Pkg.instantiate()'`
  - Otherwise, install dependencies manually:
    - Run:
      `julia -e 'using Pkg; Pkg.add(["DifferentialEquations","DiffEqFlux","Lux","Optimization","OptimizationFlux","Zygote","MAT","Plots"])'`
- Make sure the dataset file `Rise_Italy_Track.mat` is placed in the project directory.
- Run the main script to train the QSIR UDE model:
  - `julia --project training/train_qsir.jl`
- View the prediction plots and the learned quarantine strength Q(t) produced during/after execution.
