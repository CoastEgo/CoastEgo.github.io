---
title: A differentiable binary microlensing model using adaptive contour integration method
date: 2025-01-21
draft: false
cascade:
    featured_image: "/images/microlux.png"
omit_header_text: true
summary: "In this work, we delevelop a differentiable binary microlensing model using adaptive contour integration method. This code is a modified version of VBBinaryLensing (Bozza 2010, Bozza et al. 2018) which can compute the binary microlensing light curve and its derivatives both efficiently and accurately.  The code is based on Jax and available on GitHub.."
---

In this [work](https://arxiv.org/abs/2501.07268), we delevelop a differentiable binary microlensing model using adaptive contour integration method. This code is a modified version of [VBBinaryLensing](https://github.com/valboz/VBBinaryLensing) (Bozza 2010, Bozza et al. 2018) which can compute the binary microlensing light curve and its derivatives both efficiently and accurately.  The code is based on [Jax](https://github.com/jax-ml/jax) and available on [GitHub](https://github.com/CoastEgo/microlux). With the accurate derivatives, we can use the gradient-based methods for both optimization and statistical inference. We also demonstrate the application of this code on a real microlensing event modeling.

![microlux](/images/microlux.png)

Caption: An example binary-lens light curve (top panel) and its derivative with respect to the planet-to-star mass ratio q (middle panel). Only microlux with \( E^d \) (new error estimator for gradient proposed in this work) is able to yield smooth (and accurate) model gradient curve.


The talk slides of this work (**in the early stage**) can be found on [26th-microlensing-conference](https://space-science.llnl.gov/sites/space_science/files/2024-04/26th-microlensing-conference-53-ren.pdf)


