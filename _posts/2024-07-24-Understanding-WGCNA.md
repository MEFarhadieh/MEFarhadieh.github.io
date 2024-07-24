---
layout: post
title: Understanding Weighted Gene Co-Expression Network Analysis (WGCNA) with a Simple Example
date: 2024-07-24
description: How WGCNA works?
tags: Bioinformatics
categories: Networks
related_posts: false
---

### Introduction

Weighted Gene Co-Expression Network Analysis (WGCNA) is a widely-used method in bioinformatics for identifying clusters (modules) of highly correlated genes. It is particularly useful for understanding complex biological networks and identifying key regulatory genes (hub genes) in various biological processes and diseases. In this post, we will delve into the step-by-step process of WGCNA with illustrative examples.

### Steps in WGCNA

#### 1. Filtering Genes
Before performing WGCNA, genes with low variance or incomplete data are filtered out to ensure the analysis focuses on the most informative genes.

**Example:**

<div class="table-responsive">
<table class="table table-bordered">
  <thead>
    <tr>
      <th>Sample</th>
      <th>Gene1</th>
      <th>Gene2</th>
      <th>Gene3</th>
      <th>Gene4</th>
      <th>Gene5</th>
      <th>Gene6</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>5</td>
      <td>0</td>
      <td>50</td>
      <td>100</td>
      <td>2</td>
      <td>10</td>
    </tr>
    <tr>
      <td>B</td>
      <td>6</td>
      <td>0</td>
      <td>52</td>
      <td>95</td>
      <td>3</td>
      <td>12</td>
    </tr>
    <tr>
      <td>C</td>
      <td>5</td>
      <td>1</td>
      <td>48</td>
      <td>98</td>
      <td>2</td>
      <td>9</td>
    </tr>
    <tr>
      <td>D</td>
      <td>7</td>
      <td>0</td>
      <td>51</td>
      <td>102</td>
      <td>4</td>
      <td>11</td>
    </tr>
    <tr>
      <td>E</td>
      <td>6</td>
      <td>0</td>
      <td>49</td>
      <td>97</td>
      <td>3</td>
      <td>10</td>
    </tr>
  </tbody>
</table>
</div>

Genes with low variance (Gene2) and incomplete data (Gene5) are filtered out:

<div class="table-responsive">
<table class="table table-bordered">
  <thead>
    <tr>
      <th>Sample</th>
      <th>Gene1</th>
      <th>Gene3</th>
      <th>Gene4</th>
      <th>Gene6</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>5</td>
      <td>50</td>
      <td>100</td>
      <td>10</td>
    </tr>
    <tr>
      <td>B</td>
      <td>6</td>
      <td>52</td>
      <td>95</td>
      <td>12</td>
    </tr>
    <tr>
      <td>C</td>
      <td>5</td>
      <td>48</td>
      <td>98</td>
      <td>9</td>
    </tr>
    <tr>
      <td>D</td>
      <td>7</td>
      <td>51</td>
      <td>102</td>
      <td>11</td>
    </tr>
    <tr>
      <td>E</td>
      <td>6</td>
      <td>49</td>
      <td>97</td>
      <td>10</td>
    </tr>
  </tbody>
</table>
</div>

#### 2. Normalization
Data normalization helps in reducing non-biological variations. Methods like Z-score normalization are commonly used.

**Example:**

<div class="table-responsive">
<table class="table table-bordered">
  <thead>
    <tr>
      <th>Sample</th>
      <th>Gene1</th>
      <th>Gene3</th>
      <th>Gene4</th>
      <th>Gene6</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>A</td>
      <td>-1.0</td>
      <td>-0.1</td>
      <td>0.5</td>
      <td>-0.5</td>
    </tr>
    <tr>
      <td>B</td>
      <td>0.0</td>
      <td>1.3</td>
      <td>-1.1</td>
      <td>1.5</td>
    </tr>
    <tr>
      <td>C</td>
      <td>-1.0</td>
      <td>-1.5</td>
      <td>-0.3</td>
      <td>-1.5</td>
    </tr>
    <tr>
      <td>D</td>
      <td>1.0</td>
      <td>0.7</td>
      <td>1.1</td>
      <td>0.5</td>
    </tr>
    <tr>
      <td>E</td>
      <td>0.0</td>
      <td>-0.3</td>
      <td>-0.5</td>
      <td>0.0</td>
    </tr>
  </tbody>
</table>
</div>

#### 3. Calculating Similarity Matrix
The similarity between pairs of genes is calculated using Pearson correlation.

**Example:**

<div class="table-responsive">
<table class="table table-bordered">
  <thead>
    <tr>
      <th></th>
      <th>Gene1</th>
      <th>Gene3</th>
      <th>Gene4</th>
      <th>Gene6</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Gene1</td>
      <td>1.0</td>
      <td>0.8</td>
      <td>0.4</td>
      <td>0.6</td>
    </tr>
    <tr>
      <td>Gene3</td>
      <td>0.8</td>
      <td>1.0</td>
      <td>0.5</td>
      <td>0.7</td>
    </tr>
    <tr>
      <td>Gene4</td>
      <td>0.4</td>
      <td>0.5</td>
      <td>1.0</td>
      <td>0.3</td>
    </tr>
    <tr>
      <td>Gene6</td>
      <td>0.6</td>
      <td>0.7</td>
      <td>0.3</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
</div>

#### 4. Creating Weighted Adjacency Matrix
The similarity measures are raised to a power β to emphasize strong correlations and diminish weak ones.

**Example:**

<div class="table-responsive">
<table class="table table-bordered">
  <thead>
    <tr>
      <th></th>
      <th>Gene1</th>
      <th>Gene3</th>
      <th>Gene4</th>
      <th>Gene6</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Gene1</td>
      <td>1.0</td>
      <td>0.2621</td>
      <td>0.0041</td>
      <td>0.0467</td>
    </tr>
    <tr>
      <td>Gene3</td>
      <td>0.2621</td>
      <td>1.0</td>
      <td>0.0156</td>
      <td>0.1176</td>
    </tr>
    <tr>
      <td>Gene4</td>
      <td>0.0041</td>
      <td>0.0156</td>
      <td>1.0</td>
      <td>0.0007</td>
    </tr>
    <tr>
      <td>Gene6</td>
      <td>0.0467</td>
      <td>0.1176</td>
      <td>0.0007</td>
      <td>1.0</td>
    </tr>
  </tbody>
</table>
</div>

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

---

<!-- Comments Section -->
<div id="disqus_thread"></div>
<script>
(function() { // DON'T EDIT BELOW THIS LINE
var d = document, s = d.createElement('script');
s.src = 'https://YOUR_DISQUS_SHORTNAME_HERE.disqus.com/embed.js';
s.setAttribute('data-timestamp', +new Date());
(d.head || d.body).appendChild(s);
})();
</script>
<noscript>Please enable JavaScript to view the comments powered by Disqus.</noscript>
