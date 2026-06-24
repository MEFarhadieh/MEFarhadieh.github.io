---
layout: post
title: "Sample-Specific Molecular Heterogeneity in Atrial Fibrillation"
date: 2026-07-02
description: Supplementary materials for my DocDay poster on single-cell transcriptomic meta-analysis of atrial fibrillation
tags: single-cell transcriptomics atrial-fibrillation bioinformatics mrVI VAE
categories: bioinformatics
thumbnail: assets/img/dendogram_heatmap_CM_clustermap_v2.png
disqus_comments: false
related_posts: false
---

## DocDay Poster

The full poster is available below. This poster summarizes an exploratory single-nucleus transcriptomic meta-analysis of human atrial fibrillation, focusing on sample-specific molecular heterogeneity rather than only average AF-versus-SR differences.

<object data="/assets/pdf/DocDayPoster.pdf" type="application/pdf" width="100%" height="850px">
    <p>
        Your browser does not support embedded PDFs.
        <a href="/assets/pdf/DocDayPoster.pdf">Download the poster PDF here.</a>
    </p>
</object>

[Download the poster PDF](/assets/pdf/DocDayPoster.pdf)

---

## Extended Sample Distance Heatmap

{% include figure.liquid path="assets/img/dendogram_heatmap_CM_clustermap_v2.png" class="img-fluid rounded z-depth-1" caption="Extended cardiomyocyte sample-distance heatmap derived from the mrVI latent representation. Rows and columns represent individual samples. Sample annotations include AF/SR status, sex, atrial region, study of origin, and cluster group." %}

This extended heatmap provides a higher-resolution view of the sample-level structure shown in the poster. Instead of focusing only on broad AF-versus-SR separation, this analysis highlights how individual samples group according to their transcriptomic similarity in the cardiomyocyte latent space.

The annotations help evaluate whether sample proximity is associated with disease status, sex, atrial region, study origin, or the inferred cluster group. This is important because atrial fibrillation is highly heterogeneous, and patient-specific molecular patterns may be partly masked in conventional group-level comparisons.

---

## Why Use a VAE / mrVI Model?

{% include figure.liquid path="assets/img/mrvi_schematic.png" class="img-fluid rounded z-depth-1" caption="Simplified overview of the mrVI/VAE framework used to model sample-level heterogeneity in single-nucleus transcriptomic data." %}

The input to the model is the integrated single-nucleus RNA-seq dataset, including cells from multiple studies, atrial regions, sexes, and disease conditions.

The model learns a compressed latent representation, referred to here as latent *z*, that captures major transcriptional patterns while reducing noise from the high-dimensional gene-expression space.

I used this representation to compare samples more systematically and to identify groups of AF samples with distinct cardiomyocyte molecular profiles.

---

## Interpretation

This page provides additional material for the poster, with emphasis on the sample-distance analysis. The main idea is that AF-associated transcriptional changes are not uniform across all patients. While average AF-versus-SR differential expression captures only a limited signal, the latent-space analysis reveals structured sample-to-sample heterogeneity.

The extended heatmap therefore supports the central message of the poster: single-cell meta-analysis can uncover patient-specific molecular patterns that may be missed by standard case-control comparisons.
