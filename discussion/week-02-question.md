---
id: w02-cp-vs-search-algorithm
title: "Cp as a criterion vs. how we search"
author: "chahak2"
---

I understand why training MSE keeps dropping as we add predictors: a bigger model can always match the smaller one's fit and then do a little better, so RSS is monotone. Test MSE doesn't share that guarantee because the fitted coefficients depend on the training noise, and that estimation variance grows with each added parameter, eventually outweighing any further drop in bias. But what aboutt split between a selection criterion like $C_p$ and the algorithm used to search through models. If $C_p$ already tells us how to trade off fit against complexity, why do we still need a separate search strategy instead of just training every possible model directly toward minimizing $C_p$? Is it purely computational like ifthe number of subsets grows too fast to fit them all when $p$ is large or does the search strategy itself introduce some bias or variance into which model ends up selected, beyond what $C_p$ already accounts for?