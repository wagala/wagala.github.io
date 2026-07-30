---
title: "Bayesian Ternary Matrix Factorization for Sign‑Aware Discrete Data"
collection: research
permalink: /research/bayesian-ternary-matrix-factorization/
---

## Overview

This project introduces **Bayesian Ternary Matrix Factorization (BTMF)** for structured data whose
entries take values in \(\{-1, 0, +1\}\). Such data arise naturally in genomics and other applications,
for example:

- copy‑number alterations encoded as deletion (−1), normal (0), amplification (+1),  
- directional effects (negative, neutral, positive), or  
- signed interaction patterns.

The goal is to uncover **sign‑aware latent factors** that explain the observed ternary structure in a
compact and interpretable way.

## Model Structure

BTMF decomposes a ternary observation matrix \(X\) into:

- a **binary activation matrix** \(W\) – indicates which latent factors are active for each sample, and  
- a **ternary loadings matrix** \(H\) – encodes negative (−1), neutral (0), or positive (+1) contributions
  of each factor to each feature.

The product of \(W\) and \(H\) (under an appropriate discrete generative model) yields a low‑rank,
sign‑aware representation of the data. This factorization:

- separates **which** factors are used (driven by \(W\)) from  
- **how** they affect each feature (captured in the signs of \(H\)).

## Bayesian Priors and Inference

To ensure interpretability and robust regularization, BTMF uses:

- **Beta–Bernoulli priors** on the columns of \(W\), encouraging **sparse and selective** factor usage;  
- **multinomial–Dirichlet priors** on the columns of \(H\), allowing the model to learn **asymmetric
  sign patterns** across \(-1, 0, +1\).

These conjugate priors lead to **closed‑form Gibbs sampling updates**, making inference efficient and
scalable to larger datasets while still providing full Bayesian uncertainty quantification.

## Outcomes

The Bayesian TMF framework:

- discovers coherent, low‑dimensional structure in ternary datasets,  
- preserves and interprets the sign information that is often lost in purely binary models, and  
- provides a principled probabilistic model suitable for **copy‑number alteration data** and other
  sign‑coded measurements.

This project complements the Boolean factorization work by extending discrete matrix factorization
to richer, sign‑aware settings, broadening the range of biological and applied problems that can be
addressed.
