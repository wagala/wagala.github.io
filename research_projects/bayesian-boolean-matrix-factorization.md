---
title: "Bayesian Boolean Matrix Factorization for Multiple Myeloma Copy‑Number Data"
collection: research
permalink: /research/bayesian-boolean-matrix-factorization/
---

## Overview

This project develops **Bayesian Boolean Matrix Factorization (BBooMF)** methods for discovering
latent structure in **binary** genomic data, with a focus on Multiple Myeloma (MM) copy‑number
alterations (CNAs) collected at diagnosis and relapse.

MM CNA data encode the presence or absence of chromosomal events such as deletions and gains.
Representing these profiles as Boolean matrices allows us to model **presence–absence patterns**
directly, without forcing continuous approximations or arbitrary thresholds.


## Problem

Copy-number alteration (CNA) data are high-dimensional, binary, and often noisy, making it difficult to identify interpretable genomic patterns while accounting for uncertainty. Existing Boolean matrix factorization methods typically rely on deterministic optimization and do not provide probabilistic inference or uncertainty quantification.

## Solution

This project develops a Bayesian Boolean Matrix Factorization (BBMF) framework for learning interpretable latent genomic signatures from binary CNA data. The model combines Boolean matrix factorization with Bayesian inference, enabling posterior estimation of latent signatures, sample-specific loadings, and observation model parameters through Gibbs sampling while naturally quantifying uncertainty.

## Highlights

**Status:** Active development

**Manuscript:**  [A Bayesian Boolean Matrix Factorization with Application to Copy Number Analysis in Cancer (arXiv:2606.17491)](https://arxiv.org/abs/2606.17491)

**Open-source R package:** under active development.

**Public repository available:**  coming soon.
