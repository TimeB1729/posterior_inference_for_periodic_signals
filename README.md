# Posterior Inference for Periodic Signals
This project explores Bayesian inference techniques to recover latent periodic signals from noisy time-series observations. The methods are demonstrated on synthetic data and extended to real-world Kepler space telescope light curves, illustrating how Bayesian tools can uncover periodicities in stellar brightness due to rotation or oscillation.

## 🌟 Problem Statement
Given a noisy time-series signal: $y_i = f(t_i) + \epsilon_i$
where, $\epsilon_i \sim \mathcal{N}(0, \sigma ^2)$

the task is to infer the true periodic function f(t) and obtain posterior distributions over its parameters (e.g., frequency, amplitude, phase).

## 💻 Applications
The approach is applied to two Kepler targets:

- Quiet Star (KIC 007596240): A simple harmonic model is fit to the true flux values to capture baseline periodicity.

- Rotating Star (KIC 007609553): A more flexible K=2 harmonic model is used to infer f(t) from observed flux, accounting for rotational modulation and multi-harmonic structure.

## 🛠️ Methods Used
The notebook demonstrates:

1. Modeling Periodic Signals
- Synthetic sinusoidal signals
- Kepler light curves with rotational or oscillatory behavior

2. Bayesian Inference Pipeline
- Likelihood and priors
- Posterior computation via:
- - Grid evaluation
- - MCMC sampling (emcee)

3. Harmonic Modeling
- Simple sinusoidal model: $A.\sin (2 \pi \omega t + \phi)$
- Harmonic expansion (K > 1) for capturing richer periodic behavior

4. Visualization
- Posterior heatmaps and confidence contours
- Trace plots and histograms from MCMC
- Overlay of inferred signal over raw and smoothed data

## 📁 Files
- ['posterior-inference-for-periodic-signals'](notebook/posterior-inference-for-periodic-signals.ipynb): Full pipeline including synthetic simulations and Kepler star applications.

- ['Kepler1.dat'](notebook/datasets/Kepler1.dat):
Used to infer a periodic signal from the true flux of a quiet star (KIC 007596240) using a simple harmonic model.

- ['Kepler2.dat'](notebook/datasets/Kepler2.dat):
Used to infer stellar rotation-driven periodicity from the observed flux of an active star (KIC 007609553) using a K=2 harmonic model.

## 🌌 Background & Motivation
This project was a self-initiated exploration in Bayesian inference for periodic signals, inspired by lecture notes from the Penn Summer School for Astrostatistics.

## 🤝 Acknowledgements

This is an **independent project** developed by **Shyam Banerjee** (B.Stat., ISI Kolkata) as part of a summer exploration in astrostatistical modeling. The core ideas and motivation were inspired by the lecture notes from the **Summer School for Astrostatistics** at Penn State University, particularly the sessions by **Dr. Thomas Loredo** on Bayesian Inference in Astronomy.

His Github repository on the topic, from the Summer School, can be found [here](https://github.com/tloredo/SummerSchool2025-IntroBayes).

The datasets are downloaded from the `NASA/IPAC/NExScI Star And Exoplanet` archives.

## ⚙️ Running the Notebooks

All notebooks are written in Python and run on `Jupyter`. You can install the required packages with:

```bash
pip install -r requirements.txt

