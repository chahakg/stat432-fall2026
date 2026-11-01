---
id: w10-oob-vs-cv
title: "OOB error as a substitute for cross-validation"
author: "chahak2"
---

I understand that bagging averages trees fit on bootstrap samples, which reduces variance because individual trees are unstable but their average is not. Each bootstrap sample leaves out roughly 37% of observations, so every point is out-of-bag (OOB) for about a third of the trees. Predicting each point using only those trees gives an error estimate without a separate validation set.

What I'm unsure about is why OOB error is considered a fair estimate of test error. Each OOB prediction averages only about a third of the trees, not the full forest, so is it slightly pessimistic compared to the real ensemble? And since OOB error is so cheap, is there any reason to prefer cross-validation for tuning `mtry` or the number of trees, or does OOB basically replace it for random forests?
