---
id: w03-chahak2-collinearity-shrinkage
title: "Why does ridge shrink coefficients?"
author: "Chahak Gupta (chahak2)"
---
## Instability and shrinkage

In Homework 3 (Question 2), $X_1$ and $X_2$ were built from the same latent variable plus a small independent perturbation, giving $\operatorname{cor}(X_1,X_2)\approx0.998$ and a tiny smallest singular value $d_{\min}$. Under OLS, $\widehat\beta_1-\widehat\beta_2$ had a standard deviation nearly 35 times larger than $\widehat\beta_1+\widehat\beta_2$, but a small ridge penalty ($\lambda=0.02$) cut that variance roughly 10-fold while leaving the fitted values, training MSE, and test MSE almost unchanged.

So my question is that if ridge shrinks the component of $\widetilde{\mathbf y}$ along each left singular vector $\mathbf u_j$ by $\rho_j(\lambda)=d_j^2/(d_j^2+n\lambda)$, then why does shrinking the direction associated with $d_{\min}$ barely move the fitted values $\mathbf X\widehat{\boldsymbol\beta}_\lambda$, even though it drastically changes $\widehat\beta_1$ and $\widehat\beta_2$ individually?