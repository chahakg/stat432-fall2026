---
id: w07-chahak2-shared-covariance
title: "When does sharing a covariance matrix help LDA?"
author: "Chahak Gupta (chahak2)"
---
## Bias and variance in LDA vs. QDA

LDA uses one pooled covariance matrix $\boldsymbol\Sigma$ for all classes, while QDA estimates a separate $\boldsymbol\Sigma_k$ for each class. In my simulation with two classes and $p=10$, the class covariances were identical at $\rho=0$ and differed more as $\rho$ grew. With only 100 training points per class, LDA had the lower test error at small $\rho$, but QDA was clearly better at large $\rho$.

So my question is: how does the bias-variance trade-off explain this crossover? Specifically, why does pooling reduce variance, when does it add bias, and how might the training sample size change the value of $\rho$ where the two methods break even?
