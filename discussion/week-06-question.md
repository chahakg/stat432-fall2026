---
id: w06-train-test-roc-vs-sample-size
title: "Does more data close the k=1 train/test ROC gap?"
author: Chahak Gupta (chahak2)
---

In Homework 6 I fit KNN with k = 1, 3, 5, 10, 20 and plotted training and test ROC curves in separate panels. At k = 1 the training AUC is exactly 1.0000 while the test AUC is only 0.8856, and the gap shrinks as k grows (at k = 20 they are 0.9761 and 0.9821). At k = 1 training result each training point is its own nearest neighbor, so it gets its own label back, and the training ROC curve is a perfect right angle no matter how much data we have. My question is about sample size. If we keep k = 1 but increase n, the training AUC stays at 1, so does the test AUC keep rising toward 1, or does it level off below 1 because the classes overlap in the predictors? Basically is the training/test gap at small k caused only by too little data, or by label noise that a single neighbor can never average out? Would a larger fixed k change the answer?
