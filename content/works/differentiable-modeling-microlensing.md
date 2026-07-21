---
title: "KMT-2025-BLG-1314 and KMT-2025-BLG-1392: two microlensing planetary/brown-dwarf candidates analyzed with differentiable code"
date: 2026-03-02
draft: false
description: "Two degenerate microlensing events analyzed with differentiable code, highlighting how accurate gradients enable efficient HMC inference and better mixing for the Point/Finite sub-degeneracy in KMT-2025-BLG-1314."
featured_image: "/images/mcmc-vs-hmc.png"
summary: "Using the differentiable microlensing package microlux, we analyze two highly degenerate events. Accurate derivatives enable efficient gradient-based inference, and for the Point/Finite sub-degeneracy in KMT-2025-BLG-1314, HMC mixes more robustly than traditional MCMC."
paper_url: "https://doi.org/10.1088/1674-4527/ae6f92"
code_url: "https://github.com/CoastEgo/microlux"
---

In this [paper](https://doi.org/10.1088/1674-4527/ae6f92), we apply our JAX-based differentiable microlensing code [microlux](https://github.com/CoastEgo/microlux) to two new events, KMT-2025-BLG-1314 and KMT-2025-BLG-1392. Both events are highly degenerate, so this work is also a test of differentiable microlensing inference on realistic posteriors.

The key methodological point is that `microlux` provides accurate derivatives, which makes gradient-based inference practical for binary-lens modeling. The main advantage of Hamiltonian Monte Carlo (HMC) here is its higher efficiency in correlated, high-dimensional parameter spaces. In KMT-2025-BLG-1314, this leads to much better mixing than a conventional ensemble MCMC sampler for the Point/Finite sub-degeneracy within the planetary solutions.

The most interesting result is the final figure below. For KMT-2025-BLG-1314, chains initialized at the Planet Close Point and Planet Close Finite modes converge to a consistent posterior under HMC, while the traditional MCMC runs remain initialization-dependent.

Astrophysically, the favored solutions correspond to \\(\\log q \\sim -3.5\\) for the planetary branch of KMT-2025-BLG-1314, \\(\\log q > -1.5\\) for the binary branch, and \\(\\log q \\sim -1.3\\) for KMT-2025-BLG-1392.

![MCMC vs HMC](/images/mcmc-vs-hmc.png)

Caption: Comparison of a traditional ensemble MCMC sampler (left) and HMC (right) for KMT-2025-BLG-1314. The two runs are initialized at the Planet Close Point and Planet Close Finite modes. With gradients from the differentiable model, HMC converges to a consistent posterior, while the conventional sampler remains strongly initialization-dependent.
