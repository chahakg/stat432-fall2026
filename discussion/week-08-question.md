---
id: w08-chahak2-skill-specificity
title: "How specific should reusable AI skills be?"
author: "Chahak Gupta (chahak2)"
---
## Specifics for reusable AI skills

A reusable skill should work on any dataset, so it cannot mention particular variables or results. But when I reviewed a classmate's LDA/QDA skill, it said only "chosen number of components" and "a simple average" for the blend. Two agents following it could pick different PCA grids and blend weights, and so reach different final models. Vague instructions made the analysis hard to reproduce.

I wonder, where should a skill draw the line between guidance that is too vague and guidance that is too tied to one dataset? Specifically, which choices (such as the candidate grid, the random seed, shared CV folds, or tie-breaking among models) should a dataset-independent skill fix in advance, and which should it leave for the agent to decide based on the data? How would you phrase one of these rules so it stays general but still gives repeatable results?
