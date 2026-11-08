---
id: w11-chahak2-kmeans-starts
title: "If K-means converges, is the answer the best one?"
author: "Chahak Gupta (chahak2)"
---
## K-means converges, but to which solution?

In Homework 11, I wrote my own K-means function and ran it on the same 10 observations from two different random starting assignments. Both runs stopped because the assignments stopped changing, but they ended with different groupings and different within-cluster sums of squares (10.474 and 10.4304). Each run looked finished, yet at least one of them was not the best answer.

I wonder, if K-means always converges, why doesn't it always find the smallest possible within-cluster sum of squares? Since each step can only lower the objective or leave it the same, what is the algorithm missing that lets it get stuck? And in practice, how should we decide how many random starts to try, and how can we tell whether the solution we kept is trustworthy or just the best of a few lucky tries?
