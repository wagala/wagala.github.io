---
title: "Unsupervised Learning via Discrete Matrix Factorization for Multiple Myeloma"
collection: research
permalink: /research/discrete-matrix-factorization-mm
---

My current research focuses on **unsupervised learning via Discrete Matrix Factorization**, developing
methodologies that are generally applicable but are specifically motivated by **Multiple Myeloma (MM)**.

Multiple myeloma is a malignancy of post-germinal centre B cells (plasma cells) that is typically driven by
primary and secondary chromosomal events. Cytogenetic experiments have identified numerous recurrent
chromosomal and genetic alterations, including:

- chromosomal translocations  
- copy-number abnormalities (CNAs)  
- point mutations  

CNAs are particularly important in MM, influencing prognosis, therapeutic choices, and sometimes appearing
only at relapse. CNA events include frequent gains and losses of whole chromosomes or chromosome arms,
deletions of 1p, and gains of the long arm of chromosome 1 (1q). In this project I analyse **CNA data**
encoded as a discrete matrix with entries for deletions (−1), normal state (0), and amplifications (+1).

I am developing **Bayesian methodologies for factorizing discrete matrices**, including:

1. **Bayesian Boolean Matrix Factorization (BBooMF)** for Boolean data  
2. **Bayesian Ternary Matrix Factorization (BTMF)** for ternary data  

These decompositions reveal latent structure, produce compact and interpretable representations, and remain
robust to noise.

## 1. Bayesian Boolean Matrix Factorization (BBooMF)

### 1.1 BBooMF for Single Data Sets

BBooMF factorizes a Boolean data matrix by assuming it is generated from an underlying latent Boolean
structure. A loading matrix \(W\) and latent pattern matrix \(H\) combine via Boolean conjunction and
disjunction to produce an ideal reconstruction, and the observed data are treated as a noisy realization of
this latent structure.

Using Boolean algebra provides clear interpretability: a 1 in the reconstruction appears only when a factor
is active in a row and contributes that feature, and multiple factors combine through logical OR. This
directly captures presence–absence relationships and keeps the data discrete, avoiding arbitrary
thresholding of continuous factorizations.

To estimate \(W\) and \(H\), BBooMF places **Beta–Bernoulli priors** on their binary entries, learning how
sparse or dense each factor should be. The latent pattern matrix \(H\) also uses a **spike-and-slab prior**,
allowing the model to switch entire latent factors on or off in a data-driven way. These hierarchical priors
control model complexity, prevent overfitting, and promote concise Boolean patterns within an
interpretable probabilistic framework.

### 1.2 Joint Bayesian Boolean Matrix Factorization (JBBooMF)

The **Joint BBooMF** extension simultaneously factorizes two related Boolean data sets,
\(X^{(1)}\) and \(X^{(2)}\). Each data set has its own loading matrix, \(W^{(1)}\) and \(W^{(2)}\), while
they share a common latent pattern matrix \(H\). The Boolean generative process is unchanged, but
sharing \(H\) forces both data sets to express their structure through the same latent Boolean features.

This is well suited to paired biological measurements such as MM CNA profiles collected at diagnosis and
relapse:

- \(X^{(1)}\): CNAs present at diagnosis  
- \(X^{(2)}\): CNAs present at relapse  

The joint model discovers latent CNA patterns in \(H\), while \(W^{(1)}\) and \(W^{(2)}\) describe how
strongly each pattern is expressed at each time point. The spike-and-slab prior on \(H\) determines which
factors are globally active, automatically highlighting CNA features that **persist** across stages or
**diverge** between diagnosis and relapse. This yields an interpretable framework for comparing
chromosomal changes over time and identifying biologically meaningful evolution of the disease.

## 2. Bayesian Ternary Matrix Factorization (BTMF)

I have also developed a **Bayesian Ternary Matrix Factorization (BTMF)** model for structured data whose
entries take values in \(\{-1, 0, +1\}\). BTMF decomposes a ternary observation matrix into:

- a **binary activation matrix** \(W\), indicating which latent factors are expressed  
- a **ternary loadings matrix** \(H\), capturing negative, neutral, or positive contributions of each factor  

To ensure interpretability and regularization, BTMF places:

- **Beta–Bernoulli priors** on the columns of \(W\), encouraging sparse and selective factor usage  
- **multinomial–Dirichlet priors** on the columns of \(H\), allowing the model to learn asymmetric sign
  patterns in the data  

These conjugate priors yield closed-form **Gibbs sampling** updates, leading to an efficient inference
algorithm that scales to larger problems while producing coherent latent representations.

Overall, the Bayesian TMF framework provides a probabilistic, sign-aware model for discovering structured
and interpretable latent patterns in ternary datasets, with MM CNA data as a central motivating
application.
