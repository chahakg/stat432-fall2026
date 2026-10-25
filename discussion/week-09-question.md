---
id: w09-c-gamma-bias-variance
title: "Do C and gamma both control flexibility?"
author: "chahak2"
---

In the radial-kernel SVM, I understand that a large cost $C$ penalizes margin violations heavily, so the model tries to classify nearly every training point correctly. In my Question 1 results, the larger-$C$ settings had higher cross-validation error, which looks like overfitting. I also understand that a larger $\gamma$ makes each point's influence more local, so the boundary becomes more wiggly.

My question is about how these two parameters relate. Both seem to make the model more flexible, so do they play the same bias-variance role? If I increase $\gamma$, would I normally need to decrease $C$ to compensate, or do they control different things? In practice, should I tune them together on a grid, or is it reasonable to fix one and tune the other?
