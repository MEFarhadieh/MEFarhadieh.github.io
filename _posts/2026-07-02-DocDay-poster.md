---
layout: post
title: "Sample-Specific Molecular Heterogeneity in Atrial Fibrillation"
date: 2026-06-29
description: Supplementary materials for my DocDay poster on single-cell transcriptomic meta-analysis of atrial fibrillation
tags: single-cell transcriptomics atrial-fibrillation bioinformatics VAE
categories: bioinformatics
thumbnail: assets/img/dendogram_heatmap_CM_clustermap_v2.png
disqus_comments: false
related_posts: false
---

## DocDay Poster

The full poster is available below. This poster summarizes an exploratory single-nucleus transcriptomic meta-analysis of human atrial fibrillation, focusing on sample-specific molecular heterogeneity rather than only average AF-versus-SR differences.

<object data="/assets/pdf/DocDayPoster_v2.pdf" type="application/pdf" width="100%" height="850px">
    <p>
        Your browser does not support embedded PDFs.
        <a href="/assets/pdf/DocDayPoster_v2.pdf">Download the poster PDF here.</a>
    </p>
</object>

[Download the poster PDF](/assets/pdf/DocDayPoster_v2.pdf)

---

## Extended Sample Distance Heatmap

{% include figure.liquid path="assets/img/dendogram_heatmap_CM_clustermap_v2.png" class="img-fluid rounded z-depth-1" caption="Cardiomyocyte sample-distance heatmap derived from the VAE latent representation. Rows and columns represent individual samples. Sample annotations include AF/SR status, sex, atrial region, study of origin, and cluster group." %}

This heatmap provides a resolution view of the sample-level structure shown in the poster. This analysis highlights how individual samples group according to their transcriptomic similarity in the cardiomyocyte latent space.

The annotations help evaluate whether sample proximity is associated with disease status, sex, atrial region, study origin, or the inferred cluster group. This is important because atrial fibrillation is highly heterogeneous, and patient-specific molecular patterns may be partly masked in conventional group-level comparisons.

{% include figure.liquid path="assets/img/sampled_umap.png" class="img-fluid rounded z-depth-1" caption=" Four AF samples and one SR sample from the right atrium are overlaid on the full dataset shown in grey." %}

The highlighted samples occupy nearby regions of the embedding across multiple cell-type neighborhoods, suggesting shared sample-level transcriptional structure rather than a signal restricted to a single cell population. The presence of an SR sample close to these AF samples also illustrates why sample-level analysis is useful: molecular similarity may not perfectly follow the clinical AF/SR label. This supports the use of latent-space distance analysis to capture patient-level heterogeneity beyond average case-control comparisons.

---

## Structure of the VAE Model

{% include figure.liquid path="assets/img/mrvi_schematic.png" class="img-fluid rounded z-depth-1" caption="Simplified overview of the VAE framework used to model sample-level heterogeneity in single-nucleus transcriptomic data." %}

The input to the model is the integrated single-nucleus RNA-seq dataset, including cells from multiple studies, atrial regions, sexes, and disease conditions.

The model learns a compressed latent representation, referred to here as latent *z*, that captures major transcriptional patterns while reducing noise from the high-dimensional gene-expression space.

This VAE model generat with MrVI from scvi-tools. More information about scvi-tools is available at the [official GitHub repository](https://github.com/scverse/scvi-tools).

---

## Contact
[Preissl Lab](https://www.preissllab.org)

[Mohammad-Erfan Farhadieh](https://mefarhadieh.github.io)
