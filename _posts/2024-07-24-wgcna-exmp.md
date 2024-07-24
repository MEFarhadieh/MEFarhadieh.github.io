---
layout: post
title: Understanding Weighted Gene Co-Expression Network Analysis (WGCNA) with a Simple Example
date: 2024-07-24
description: How WGCNA works?
tags: Bioinformatics
categories: Networks
giscus_comments: true
related_posts: false
---

### Introduction

Weighted Gene Co-Expression Network Analysis (WGCNA) is a widely-used method in bioinformatics for identifying clusters (modules) of highly correlated genes. It is particularly useful for understanding complex biological networks and identifying key regulatory genes (hub genes) in various biological processes and diseases. In this post, we will delve into the step-by-step process of WGCNA with illustrative examples.

### Steps in WGCNA

#### 1. Filtering Genes
Before performing WGCNA, genes with low variance or incomplete data are filtered out to ensure the analysis focuses on the most informative genes.

**Example:**

| Sample | Gene1 | Gene2 | Gene3 | Gene4 | Gene5 | Gene6 |
|--------|-------|-------|-------|-------|-------|-------|
| A      | 5     | 0     | 50    | 100   | 2     | 10    |
| B      | 6     | 0     | 52    | 95    | 3     | 12    |
| C      | 5     | 1     | 48    | 98    | 2     | 9     |
| D      | 7     | 0     | 51    | 102   | 4     | 11    |
| E      | 6     | 0     | 49    | 97    | 3     | 10    |

Genes with low variance (Gene2) and incomplete data (Gene5) are filtered out:

| Sample | Gene1 | Gene3 | Gene4 | Gene6 |
|--------|-------|-------|-------|-------|
| A      | 5     | 50    | 100   | 10    |
| B      | 6     | 52    | 95    | 12    |
| C      | 5     | 48    | 98    | 9     |
| D      | 7     | 51    | 102   | 11    |
| E      | 6     | 49    | 97    | 10    |

#### 2. Normalization
Data normalization helps in reducing non-biological variations. Methods like Z-score normalization are commonly used.

**Example:**

| Sample | Gene1  | Gene3  | Gene4  | Gene6  |
|--------|--------|--------|--------|--------|
| A      | -1.0   | -0.1   | 0.5    | -0.5   |
| B      | 0.0    | 1.3    | -1.1   | 1.5    |
| C      | -1.0   | -1.5   | -0.3   | -1.5   |
| D      | 1.0    | 0.7    | 1.1    | 0.5    |
| E      | 0.0    | -0.3   | -0.5   | 0.0    |

#### 3. Calculating Similarity Matrix
The similarity between pairs of genes is calculated using Pearson correlation.

**Example:**

|        | Gene1 | Gene3 | Gene4 | Gene6 |
|--------|-------|-------|-------|-------|
| Gene1  | 1.0   | 0.8   | 0.4   | 0.6   |
| Gene3  | 0.8   | 1.0   | 0.5   | 0.7   |
| Gene4  | 0.4   | 0.5   | 1.0   | 0.3   |
| Gene6  | 0.6   | 0.7   | 0.3   | 1.0   |

#### 4. Creating Weighted Adjacency Matrix
The similarity measures are raised to a power β to emphasize strong correlations and diminish weak ones.

**Example:**

|        | Gene1   | Gene3   | Gene4   | Gene6   |
|--------|---------|---------|---------|---------|
| Gene1  | 1.0     | 0.2621  | 0.0041  | 0.0467  |
| Gene3  | 0.2621  | 1.0     | 0.0156  | 0.1176  |
| Gene4  | 0.0041  | 0.0156  | 1.0     | 0.0007  |
| Gene6  | 0.0467  | 0.1176  | 0.0007  | 1.0     |

#### 5. Constructing Gene Network
Using the weighted adjacency matrix, a gene network is created where nodes represent genes, and edges represent weighted connections.

#### 6. Identifying Modules
Clustering algorithms are used to identify modules, which are groups of genes with similar expression patterns.

**Example Modules:**

- **Module 1:** Gene1, Gene3, Gene6
- **Module 2:** Gene4

### Conclusion
WGCNA is a powerful tool for identifying gene modules and understanding gene networks in large-scale biological data. This method helps in uncovering key regulatory genes and pathways involved in various biological processes and diseases, thereby providing insights that can drive future research and therapeutic strategies.

### References
1. Langfelder P, Horvath S. WGCNA: an R package for weighted correlation network analysis. BMC Bioinformatics. 2008.
2. Zhang B, Horvath S. A general framework for weighted gene co-expression network analysis. Stat Appl Genet Mol Biol. 2005.
