---
title: "AM115 Section 1: Beyond Binomial - Modeling Continuous Phenomena"
author: "AM115 Course Staff"
format: beamer
---

# AM115 Section 1

## The Battery Replacement Dilemma

Your laptop battery is dying. At the store you find:

- **Brand A**: $45, mixed reviews about lifespan
- **Brand B**: $65, claims "40% longer life"

How do you decide if the extra $20 is worth it?

# Real Data from Reviews

## Brand A Battery Lifespans (months):
18.2, 24.5, 15.3, 22.1, 28.9, 19.7, 26.3, 21.4

## Brand B Battery Lifespans (months):
31.2, 28.7, 35.4, 29.8, 33.1, 30.9

**Question:** Which is the better value?

# Why Not Binomial?

## Binomial tells us:
- How many successes in $n$ trials
- Probability of success/failure

## But we need to know:
- WHEN will the battery fail?
- What's the expected lifespan?
- Is the extra cost justified?

**We need a continuous time model!**

# The Exponential Distribution

## For modeling time until failure:

**Probability density:** $f(t) = \lambda e^{-\lambda t}$

**Survival probability:** $P(T > t) = e^{-\lambda t}$

**Mean lifetime:** $E[T] = 1/\lambda$

## Key insight:
- $\lambda$ = failure rate (failures per month)
- $1/\lambda$ = expected lifespan

# Finding MLE for Battery Data

## Given lifespans $t_1, t_2, \ldots, t_n$:

Likelihood: $L(\lambda) = \prod \lambda e^{-\lambda t_i}$

Log-likelihood: $\log L = n \log \lambda - \lambda \sum t_i$

Derivative: $\frac{d}{d\lambda} \log L = \frac{n}{\lambda} - \sum t_i = 0$

**Result:** $\hat{\lambda} = \frac{n}{\sum t_i} = \frac{1}{\text{mean lifespan}}$

# Making the Decision

## Brand A:
- Mean lifespan ≈ 22 months
- Cost: $45
- Cost per month: $2.04

## Brand B:
- Mean lifespan ≈ 31 months
- Cost: $65
- Cost per month: $2.10

**The cheaper battery is actually the better value per month!**

# Your Turn!

## We'll work through:
1. Why exponential for failure times?
2. Derive MLE on the board
3. Implement in Python
4. Make data-driven decisions

**Remember:** Real-world modeling helps us make better choices!
