---
title: "CausticFlow: a machine-learning proposal engine for binary microlensing"
date: 2026-07-06
draft: false
description: "Fast posterior proposals for irregular binary-microlensing light curves using Neural CDEs and normalizing flows."
featured_image: "/images/causticflow-overview.png"
summary: "CausticFlow converts irregular light curves into posterior proposals for conventional optimization, recovering about 80% of simulated events and 7 of 10 real events in the paper's test set."
paper_url: "https://arxiv.org/abs/2607.04955"
---

In this [paper](https://arxiv.org/abs/2607.04955), we introduce `CausticFlow`, a machine-learning framework for binary microlensing inference that combines Neural CDEs with normalizing flows. The model is designed for irregularly sampled light curves with gaps, and it learns posterior distributions that can capture both parameter correlations and multi-modal structure.

The main idea is not to replace detailed event modeling, but to make it much faster to find good solutions. Once trained on simulated KMTNet-like light curves, `CausticFlow` can generate posterior samples in a fraction of a second and provide strong initial guesses for downstream local optimization. With ten posterior-guided local optimizations, the workflow recovers the input-model fit quality for about 80% of simulated events and improves the precision of key binary-lens parameters such as \\(q\\) and \\(s\\).

We also test the framework on 10 real binary microlensing events from the 2023--2025 seasons. Despite mismatches between the simulations and real observations, the method recovers the reference solutions, light-curve morphology, and lens geometry for 7 of the 10 events after simple local refinement, with a computational cost of about 10 CPU minutes per event. This makes `CausticFlow` a practical proposal engine for systematic modeling in future large microlensing surveys such as Roman, CSST, and ET.

![CausticFlow overview](/images/causticflow-overview.png)

Caption: Schematic overview of `CausticFlow`. The framework first encodes an irregular microlensing light curve with a Neural CDE-based representation, then uses a conditional normalizing flow to generate samples from the learned binary-lens posterior.
