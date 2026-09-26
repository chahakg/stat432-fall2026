---
id: w05-chahak2-correlation-knn-dimension
title: "Correlation and the effective dimension neighbors"
author: "Chahak Gupta (chahak2)"
---

In Question 2, I expected correlated covariates to hurt KNN more than independent ones, since redundant covariates should still stretch Euclidean distance in directions that carry no extra information about $Y$. But in my single simulated dataset, KNN's test MSE was actually *lower* under $\rho=0.8$ correlation (0.197) than under independence (0.594), while lasso showed the opposite pattern (0.239 vs. 0.306).

My best explanation is that strong correlation compresses the covariates' effective dimensionality, 30 nearly redundant directions behave more like a handful of independent ones, so distances in the correlated setting may concentrate less noise per neighbor than distances built from 30 truly independent coordinates, even though none of the individual covariates became more informative about $Y$.

Is this the right mechanism, or is a single simulated dataset simply too noisy to draw any directional conclusion at all? More generally, is there a clean way to disentangle "correlation reduces effective dimension" from "correlation dilutes signal" without running many repetitions, given that both effects act on the same distance calculation simultaneously?
