---
layout: page
title: Epigenetic Roles on T Cell Terminal Exhaustion in Endometrial and Ovarian Cancers
description: Multi-Omic Single-Cell Study
img: assets/img/Proj_Texhus1.png
importance: 4
category: work
related_publications: true
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/Proj_Texhus1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Credit: Alex Ritter, Jennifer Lippincott Schwartz and Gillian Griffiths, National Institutes of Health Killer T cells (green and red) surround a cancer cell (blue, center).
</div>

### Project Overview

This project aims to investigate the epigenetic mechanisms underlying the progression of endometrial and ovarian cancers, utilizing single-cell RNA sequencing (scRNA-Seq) and single-cell ATAC sequencing (scATAC-Seq) data. The focus is on uncovering the pathways and transcription factors (TFs) that drive T cells from an effector state to a dysfunctional, terminally exhausted state.

### Objectives

1. **Characterize Cell Populations**: Identify and characterize various cell populations within the tumor microenvironment, including T cells, using scRNA-Seq and scATAC-Seq data.
2. **Epigenetic Landscape Analysis**: Analyze the chromatin accessibility profiles of T cells to understand the epigenetic landscape that contributes to their exhaustion.
3. **Pathway Identification**: Identify key pathways and transcription factors involved in T cell exhaustion.
4. **Integration of Multi-Omics Data**: Integrate scRNA-Seq and scATAC-Seq data to correlate transcriptional changes with epigenetic modifications.

### Methodology

1. **Data Collection**: Obtain single cell maltioum data endometrial and ovarian cancers.
2. **Metadata Collection**: Obtain sample metadata and confounding factors.
3. **Data Processing and Quality Control**:
   - Use computational tools to process raw count data, ensuring high-quality reads.
   - Perform quality control to filter out low-quality cells and artifacts.
4. **Cluster Analysis**:
   - Apply clustering algorithms to identify distinct cell populations within the tumor microenvironment.
   - Use differential expression analysis to determine unique markers for each cluster.
5. **Integration and Multi-Omics Analysis**:
   - Integrate scRNA-Seq and scATAC-Seq data to create a comprehensive map of gene expression and chromatin accessibility.
   - Correlate changes in chromatin accessibility with transcriptional activity to identify regulatory elements.
6. **Pathway and TF Identification**:
   - Use pathway enrichment analysis to identify signaling pathways involved in T cell exhaustion.
   - Identify key transcription factors regulating these pathways by analyzing motifs in accessible chromatin regions.

<div class="row justify-content-sm-center">
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Proj_Texhus2.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/Proj_Texhus3.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Credit: Active Motif®
</div>

### Expected Outcomes

1. **Detailed Cell Atlas**: A detailed atlas of cell populations within endometrial and ovarian tumors, highlighting the heterogeneity and complexity of the tumor microenvironment.
2. **Epigenetic Insights**: Insights into the epigenetic mechanisms driving T cell exhaustion, providing a better understanding of how chromatin accessibility changes during T cell dysfunction.
3. **Novel Pathways and TFs**: Identification of novel pathways and transcription factors involved in T cell exhaustion, offering potential targets for therapeutic intervention.
4. **Integrated Multi-Omics Data**: A comprehensive dataset integrating transcriptional and epigenetic information, enabling deeper insights into the regulatory networks at play in cancer.

### Significance

This study will advance our understanding of the epigenetic regulation of immune cell function in cancer. By identifying the key factors driving T cell exhaustion, we can develop new therapeutic strategies to rejuvenate T cell function and improve the efficacy of immunotherapies in treating endometrial and ovarian cancers.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/Proj_Texhus4.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Credit: Franco, Fabien, et al. "Metabolic and epigenetic regulation of T-cell exhaustion." Nature metabolism 2.10 (2020): 1001-1012.
</div>

As the above figure provides a detailed journey of T cells as they transition from their naive state to becoming terminally exhausted, particularly within the context of persistent antigen exposure, such as in chronic infections or cancer. Starting as naive T cells, they can differentiate into effector T cells, which are crucial for immediate immune responses, or memory T cells, which provide long-term immunity. However, under continuous antigen stimulation, such as in the tumor environment, T cells progress through various stages of exhaustion. This journey involves significant epigenetic changes, where initial effector and memory-like states, characterized by accessible chromatin regions and active gene expression, give way to more intermediate and finally terminally exhausted states. These exhausted states exhibit closed chromatin regions and suppressed gene expression of effector functions, while genes associated with exhaustion, like PD-1, become highly expressed. Understanding these transitions and the underlying epigenetic mechanisms provides critical insights into how T cells become dysfunctional, offering potential targets to restore their function in cancer therapy. This project uses advanced single-cell RNA and ATAC sequencing technologies to dissect these complex processes in endometrial and ovarian cancers, aiming to identify key transcription factors and pathways that could be therapeutically targeted to reverse T cell exhaustion and enhance anti-tumor immunity.

### Status

This project is being done in collaboration with [Arash Bagherabadi](https://sites.google.com/view/arash-bagherabadi/about), Fatemeh Hedayat, and [Amirreza Hooshmand](https://sites.google.com/view/amirreza-hooshmand).  
