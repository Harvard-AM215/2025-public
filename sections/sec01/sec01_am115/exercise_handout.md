---
title: "AM115 Section 1: Laptop Battery Lifespan Analysis"
author: "Name: ___________________"
date: "Section: ___________________"
geometry: margin=1in
fontsize: 11pt
---

# AM115 Section 1: The Battery Replacement Decision

## Background
You need to replace your laptop battery and are comparing two brands based on lifespan data from online reviews.

**Brand A**: $45 replacement battery  
**Brand B**: $65 replacement battery (claims "40% longer life")

## Part A: Model Selection (Group Discussion - 10 min)

1. Why can't we use a binomial model for battery lifespans?

\vspace{0.75in}

2. Sketch what you think the distribution of battery lifespans looks like. Why might exponential be appropriate?

\vspace{1.25in}

3. What is the "memoryless property" and does it make sense for batteries?

\vspace{0.75in}

## Part B: Quick Analysis (5 min)

**Brand A lifespans (months):** 18.2, 24.5, 15.3, 22.1, 28.9, 19.7, 26.3, 21.4

1. Calculate the mean lifespan (quick approximation is fine)

   Mean = _______________ months

2. Estimate the failure rate $\lambda$

   $\lambda$ = _______________ failures/month

3. What's the monthly cost?

   $45 ÷$ mean lifespan = $_______________ per month

## Part C: Maximum Likelihood (15 min)

1. For exponential distribution with lifespans $t_1, t_2, \ldots, t_n$, write the likelihood:

   $L(\lambda) = $

\vspace{0.75in}

2. Write the log-likelihood:

   $\log L(\lambda) = $

\vspace{0.75in}

3. Find the MLE by taking the derivative:

   $\frac{d}{d\lambda} \log L = $

\vspace{0.5in}

   Solving for $\lambda$:

\vspace{0.75in}

   $\hat{\lambda}_{MLE} = $ _______________

## Part D: Decision Making (5 min)

1. If Brand B batteries last 31 months on average, what's its cost per month?

   Cost per month = $_______________

2. Based on cost per month of use, which battery is the better value?

\vspace{0.5in}

3. What other factors might affect your decision?

\vspace{0.75in}

## Part E: Model Validation

For exponential: $P(T > t) = e^{-\lambda t}$

1. Using Brand A's $\lambda$, what's the probability a battery lasts > 2 years (24 months)?

   $P(T > 24) = $ _______________

2. In the Brand A data, what fraction actually lasted > 24 months?

   Fraction = _______________

## Notes
We'll implement this analysis in Python next, where we can handle larger datasets and create visualizations to support our decision.
