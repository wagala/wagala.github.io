---
title: "A Joint Bayesian Boolean Matrix Factorization with Application to Chromosomal Copy Number Alterations in Multiple Myeloma"
collection: research
permalink: /research/joint-bayesian-boolean-matrix-factorization/
---

## Overview
In this project is an extension of BBMF for jointly analyzing paired binary datasets through shared latent signatures and dependent loading matrices, enabling Bayesian data integration and uncertainty quantification. We develop Joint Bayesian Boolean Matrix Factorization (JBBMF), a method for discovering shared low‑dimensional structure in related binary datasets. Unlike standard Boolean matrix factorization, which treats each matrix separately, JBBMF jointly factorizes two binary matrices using a common set of latent Boolean factors and dataset‑specific loadings. The model is fully Bayesian, providing both reconstructions and uncertainty quantification via an efficient Gibbs sampler with closed-form updates and explicit noise modeling.

We validate the approach in simulation, showing improved recovery of shared latent factors compared to independent factorizations. We then apply JBBMF to paired copy number alteration (CNA) profiles from multiple myeloma patients at diagnosis and relapse, where we identify a common set of recurrently co‑altered chromosomal arms, distinguish stable versus relapse‑specific patterns, and recover patient‑level activation patterns consistent with known clonal evolution.

## Problem

Many scientific studies collect paired binary datasets that represent the same subjects under different conditions, such as diagnosis and relapse, before and after treatment, or multiple experimental platforms. Existing Boolean matrix factorization methods typically analyze each dataset independently, failing to exploit the dependence between related observations and limiting the ability to identify shared and condition-specific latent structure.

## Solution

This project develops Joint Bayesian Boolean Matrix Factorization (jBBMF), a Bayesian framework for jointly analyzing paired binary datasets through shared latent signatures and dependent loading matrices. The model explicitly captures the relationship between paired observations while providing posterior inference for latent factors, observation model parameters, and dependence parameters using Gibbs sampling with full uncertainty quantification.

## Highlights

**Status:** Active development

**Manuscript:** in preparation

**Open-source R package:** under active development.

**Public repository available:** [wagala/jBBMF](https://github.com/wagala/jBBMF)


