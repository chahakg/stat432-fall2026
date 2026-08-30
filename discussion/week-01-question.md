---
id: w01-gaussian-vs-laplace-likelihood
title: "Gaussian vs. Laplace Likelihood"
author: "Chahak Gupta (chahak2)"
---

While working through the Gaussian likelihood question in this week's homework, I noticed that for fixed $\sigma^2$, maximizing the log-likelihood over $\boldsymbol\beta$ reduces exactly to minimizing the residual sum of squares. This is a direct consequence of assuming Gaussian errors: the log-likelihood contains a $-\frac{1}{2\sigma^2}(\mathbf{y} - \mathbf{X}\boldsymbol\beta)^{\mathsf{T}}(\mathbf{y} - \mathbf{X}\boldsymbol\beta)$ term, and the Gaussian density's exponent is quadratic in the residuals, so maximizing likelihood and minimizing squared error become the same optimization problem.

However, I want to know if that connection is only to the Gaussian assumption. If the errors were instead assumed to follow a different distribution like Laplace for example, the log-likelihood would involve $\sum_i |y_i - \mathbf{x}_i^{\mathsf{T}}\boldsymbol\beta|$ rather than squared residuals, since the Laplace density's exponent is linear in absolute deviation rather than quadratic.

Would maximizing that likelihood instead correspond to minimizing absolute error rather than squared error, and would that estimator behave differently in the presence of outliers?
