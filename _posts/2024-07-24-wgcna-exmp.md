---
layout: post
title: Understanding Weighted Gene Co-Expression Network Analysis (WGCNA) with a Simple Examples
date: 2024-07-24
description: How WGCNA works?
tags:  Bioimformatics
categories: Bioimformatics
giscus_comments: true
---

### Introduction

Weighted Gene Co-Expression Network Analysis (WGCNA) is a widely-used method in bioinformatics for identifying clusters (modules) of highly correlated genes. It is particularly useful for understanding complex biological networks and identifying key regulatory genes (hub genes) in various biological processes and diseases. In this post, we will delve into the step-by-step process of WGCNA with illustrative examples.

### Steps in WGCNA

#### 1. Filtering Genes
Before performing WGCNA, genes with low variance or incomplete data are filtered out to ensure the analysis focuses on the most informative genes.

