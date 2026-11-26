# Electron Dynamics Analysis with Reduced Methods and Schrödinger Equation

Electron dynamics and POD-Galerkin reduced-order modeling on a circular bi-crystal domain using the time-dependent Schrödinger equation, developed for the Model Order Reduction Techniques course at Politecnico di Milano (Assignment 1, by Alessia Cecchini).

## Project Overview

The study models electron wave-function evolution $\Psi(x, t)$ on a circular domain of radius $1/\pi$ centered at $(0, 0)$ with homogeneous Dirichlet boundary conditions and initial Gaussian wave packet $\Psi(x, 0) = e^{-100\|x\|^2}$, governed by the Schrödinger equation with parameter-dependent potential $V_{\mu}(x) = E^{\top}x + \Delta V_0 \mathbf{1}_{[0, +\infty)}(x_2)$ for $\boldsymbol{\mu} = [E, \Delta V_0]$ with $E, \Delta V_0 \in [0, 1000]$.

The notebook covers:
- **FOM Code & Mesh Setup**: Building a 1st-order finite element mesh and assembling mass, stiffness, and potential matrices in `FOMsolve` over real and imaginary state components, plus auxiliary functions for electron probability and capture evaluation.
- **SVD & POD Basis Setup**: Loading precomputed FOM snapshot data from `ACassignment1.npz` via Google Drive (`gdown`) or generating new parameter samples and FOM trajectories.

## Repository & Notebook Structure

- `Electron_Dynamics_POD-Galerkin_Alessia_Cecchini.ipynb` — Google Colab notebook containing the FOM solver, probability/capture helpers, data loading/generation, and POD setup (partially showing results from the assignment).
- External Drive / `dlroms` assets — `ACassignment1.npz` downloaded via `gdown` and `NicolaRFranco/dlroms` installed when needed.

## Usage

1. Open the notebook in Google Colab (or clone the repository and run in a compatible Python/Colab environment).
2. Run the setup cell to import `dlroms`, `numpy`, and `matplotlib`, and build the circular finite element mesh (`Vh`, `nh = 995`) and `FOMsolver`.
3. Run the data loading cell to download and load `ACassignment1.npz` (or let the notebook generate FOM trajectories if no pre-saved data is loaded).
