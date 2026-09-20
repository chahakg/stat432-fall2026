---
id: w04-chahak2-cv-test-leakage
title: "Why can't the test set be used to choose λ?"
author: "Chahak Gupta (chahak2)"
---
## Tuning without leakage

Suppose $y$ is independent of 100 predictors, so the best possible model is intercept-only with test MSE equal to the noise variance $\sigma^2$. I fit a lasso path over a grid of $\lambda$ values on the training data, compute the test MSE for every $\lambda$, and report the smallest one as my final test error. No model was ever fit on the test data.

So my question is: why is this reported error optimistically biased (typically below $\sigma^2$), and how does running cross-validation on the training data only, then evaluating the single chosen $\widehat\lambda$ once on the test data, remove that bias?
