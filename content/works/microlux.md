---
title: A differentiable binary microlensing model using adaptive contour integration method
date: 2025-01-21
draft: false
description: "Differentiable binary microlensing software built with JAX and adaptive contour integration."
featured_image: "/images/microlux.png"
summary: "We develop a differentiable binary microlensing model with adaptive contour integration. The code extends VBBinaryLensing and uses JAX to compute accurate light curves and derivatives for optimization and inference."
paper_url: "https://arxiv.org/abs/2501.07268"
code_url: "https://github.com/CoastEgo/microlux"
slides_url: "https://space-science.llnl.gov/sites/space_science/files/2024-04/26th-microlensing-conference-53-ren.pdf"
---

In this [paper](https://arxiv.org/abs/2501.07268), we develop a differentiable binary microlensing model using adaptive contour integration. The code is a modified version of [VBBinaryLensing](https://github.com/valboz/VBBinaryLensing) (Bozza 2010, Bozza et al. 2018) that can compute the binary microlensing light curve and its derivatives both efficiently and accurately. The implementation is based on [JAX](https://github.com/jax-ml/jax) and is available on [GitHub](https://github.com/CoastEgo/microlux). With accurate derivatives, we can use gradient-based methods for both optimization and statistical inference. We also demonstrate the application of this code to real microlensing event modeling.

![microlux](/images/microlux.png)

Caption: An example binary-lens light curve (top panel) and its derivative with respect to the planet-to-star mass ratio q (middle panel). Only microlux with \( E^d \), the new gradient error estimator proposed in this work, yields a smooth and accurate derivative curve.


An early conference presentation of this work is available at [26th-microlensing-conference](https://space-science.llnl.gov/sites/space_science/files/2024-04/26th-microlensing-conference-53-ren.pdf).
