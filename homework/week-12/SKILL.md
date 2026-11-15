a. **Define the skill.** The skill below is saved as `SKILL.md`. The line `disable-model-invocation: true` makes it load only when I invoke it explicitly (for example, `/cluster-explorer`), and I pass the dataset details in the invocation prompt.

```markdown
---
name: cluster-explorer
description: Compare several clustering algorithms on a user-supplied dataset, select one, and write a one-page report. Use only when explicitly invoked.
disable-model-invocation: true
---

# Clustering exploration

The user supplies the data file path, which column identifies each observation, which columns are the features, and any optional known labels. Never assume column names. If something is unclear, ask.

## Workflow

1. Inspect. Report the number of observations and features, data types, missing values, and scale differences. Exclude identifier and label columns from the features. Never use labels for fitting, tuning, or selection.

2. Preprocess. Handle missing values and state how. Standardize features unless they are already on comparable scales. When features greatly outnumber observations, consider variance-based feature filtering or PCA (enough components for roughly 80-90% of variance) and state the choice. Set a random seed.

3. Cluster. Run at least three algorithms from different families, such as K-means, hierarchical (try several linkages), spectral, Gaussian mixture, or DBSCAN. PCA, UMAP, or t-SNE alone is not a clustering algorithm; use these only for preprocessing or plotting.

4. Tune. For each method, scan the number of clusters over a sensible range (for example 2 to min(10, n/3)) and tune its hyperparameters (linkage, neighbors or affinity, covariance type, eps). Use multiple random starts. Check stability by subsampling and comparing runs with the adjusted Rand index.

5. Compare and select. Use internal criteria only: silhouette, Calinski-Harabasz, Davies-Bouldin, gap statistic or elbow, BIC for mixture models, and stability. Penalize tiny clusters and unstable solutions. Choose one method and one number of clusters, and justify it. If methods are close, prefer the simpler and more stable one.

6. Interpret. Describe cluster sizes and separation, and identify which features or components drive the structure (for example, features with the largest between-cluster variance). Only after selection, if known labels were provided, cross-tabulate them with the selected clustering and report agreement (adjusted Rand index, purity). Treat this as validation, not as a selection criterion.

## Report rules (strict)

- The report must fit on ONE printed page, including all text, figures, and tables. Render it to PDF, check the page count, and cut or shrink content until it fits.
- Present clustering results from ONLY the selected method: one main figure (for example, a PCA scatter plot colored by cluster) and at most one small table.
- Mention the other methods only briefly, in one or two sentences, to justify the selection (name them and give the metric that ruled them out). Do not show their plots, assignments, or cluster results.
- Include: data and preprocessing, methods considered and selection rationale, the selected method and number of clusters, main findings, and limitations.
- Limitations to consider: small sample size, sensitivity to preprocessing and tuning, disagreement between internal metrics, clusters not necessarily matching meaningful categories, and no significance testing. Avoid causal claims.
- Write concise plain prose with labeled axes and legible fonts.
```