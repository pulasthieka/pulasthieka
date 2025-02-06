---
layout: post
title: Explainable AI for Understanding Cell-Cell Interactions
date: 2023-05-05 11:29:00
description: Research proposal on using explainable AI for intercellular communication
tags: AI biomedical
categories: research
---

## Introduction and background information
Although multicellular organisms have a common genome contained in their cells, the sub-cellular processes are vastly different due to variations in gene expression and gene morphology. The heterogeneity of cells occurs due to a wide range of mechanisms of gene regulation that are affected by internal processes and signals from the surrounding tissue. Recent developments like single-cell RNA sequencing (scRNAseq) have enabled researchers to profile gene expression of differentiated cells and are used to discover new biological processes, understand mechanisms of disease and evaluate the effectiveness of treatments. However, spatial information essential for understanding cell fate is lost during single-cell sequencing.

Spatial genomics and spatial transcriptomics include a range of novel methods that provide DNA or RNA expression profiles mapped to their location in the tissue.  Fluorescence in-situ hybridisation (FISH) technology and its derivatives (smFISH, MERFISH, seqFISH, seqFISH+, osmFISH) use fluorescent chemical probes and microscopy imaging to capture spatial patterns of gene expression. This, however, requires priori knowledge of the targeted genes. Next-generation sequencing (NGS) based methods such as Visium are able to perform untargeted analysis but are unable to achieve single-cell resolution needing computational methods to infer cellular features. 

Cell-cell interactions (CCI) form a multicellular network of molecular signals that play a key role in various biological processes. Understanding these interactions would help to discover the mechanisms behind processes such as organ development and tumour progression. Single-cell sequencing methods rely on identifying the expression of known ligand-receptor pairs for inferring CCI. Intercellular communication is highly dependent on the spatial structure due to the differences in signalling range between the different types of CCI. For example, juxtacrine interactions rely on physical contact between cells, and therefore an expression of juxtacrine ligand-receptor pairs in spatially distant cells would not indicate CCI.  Therefore, spatial information is crucial for properly understanding these processes. 

Existing methods either lack experimental throughput or the spatial resolution for efficiently capturing spatial genomic data. While imaging-based processes are being improved, computational techniques are being used to improve the resolution of NGS methods. Deep learning (DL) methods have been used for increasing spatial resolution via reconstruction and spot deconvolution. DL methods have been in general better than other statistical methods and these improvements are useful for downstream analysis like understanding CCI. DL methods are also being used in estimating cell-cell interactions, but are currently limited to simple interactions (SpaOTsc, Giotto, MISTy). Considering the complexity of biological systems there is a need for more complex models.

## Statement of problem and justification
The problem with DL methods lies in the interpretation of the model. Simpler models have high interpretability but are unable to capture complex non-linear relationships so complex “black box” models are often used. While this is acceptable for applications such as computer vision, the interpretability of models is crucial in spatial omics as there is a need for discovering and understanding underlying biological processes. Frameworks such as DeepLIFT, Integrated Gradients, and DeepExplain have been developed for debugging machine learning models but their utility in understanding CCI needs to be investigated.  

## Scope of the research
This research aims to develop explainable deep-learning models for estimating cell-cell interactions using spatial omic data. 
To this end, the following objectives have been identified;

1. Identify the limitations of existing methods of estimating CCI
2. Develop deep-learning models to address these shortcomings
3. Integrate interpretability techniques and relate to underlying biological processes.

## Proposed Methodology
The main goal of the research is to develop an explainable deep-learning framework for enhancing spatial genomic workflows. We propose a multi-tiered approach to tackle this objective.

The research approach is designed as follows;
- **Literature Review**:  The preliminary stage is to conduct an extensive literature review to investigate existing methods for estimating CCI to identify the gaps and challenges in the current approaches.

- **Data Collection and Preprocessing**: The second stage is to acquire suitable spatial genomic datasets and ligand-receptor databases for training and validating the models. This step could also involve the creation of a standardized benchmarking dataset if such a dataset does not exist. 

- **Model Architecture Design**: The third step is to develop a novel deep-learning architecture that integrates explainable components. The architecture should effectively capture complex cellular interactions and allow for interpretable model predictions.

- **Comparative Analysis**: The fourth step is to perform a comparative analysis of the proposed framework with existing methods. The performance, accuracy, and interpretability can be compared to highlight the advantages of the new approach.

- **Case Studies and Real-World Application**: The final step is to apply the developed explainable deep-learning model to a medically significant application.

## References
1. A. Ali Heydari, Suzanne S. Sindi; Deep learning in spatial transcriptomics: Learning from the next next-generation sequencing. Biophysics Rev. 1 March 2023; 4 (1): 011306. [https://doi.org/10.1063/5.0091135 ](https://doi.org/10.1063/5.0091135)

2. Tang, X., Huang, Y., Lei, J. et al. The single-cell sequencing: new developments and medical applications. Cell Biosci 9, 53 (2019). [https://doi.org/10.1186/s13578-019-0314-y](https://doi.org/10.1186/s13578-019-0314-y)

3. Cardozo Gizzi, A.M. (2021) ‘A shift in paradigms: Spatial Genomics approaches to reveal single-cell principles of Genome Organization’, Frontiers in Genetics, 12. [https://doi.org/10.3389/fgene.2021.780822 ](https://doi.org/10.3389/fgene.2021.780822 )

4. Williams, C.G., Lee, H.J., Asatsuma, T. et al. An introduction to spatial transcriptomics for biomedical research. Genome Med 14, 68 (2022). [https://doi.org/10.1186/s13073-022-01075-1 ](https://doi.org/10.1186/s13073-022-01075-1)

5. Liu, Z., Sun, D. & Wang, C. Evaluation of cell-cell interaction methods by integrating single-cell RNA sequencing data with spatial information. Genome Biol 23, 218 (2022). [https://doi.org/10.1186/s13059-022-02783-y ](https://doi.org/10.1186/s13059-022-02783-y )

6. Atta, L., Fan, J. Computational challenges and opportunities in spatially resolved transcriptomic data analysis. Nat Commun 12, 5283 (2021). [https://doi.org/10.1038/s41467-021-25557-9 ](https://doi.org/10.1038/s41467-021-25557-9)

7.Mateo Sokač Lars Dyrskjøt Benjamin Haibe-Kains Hugo J.W.L. Aerts Nicolai J Birkbak 2023GENIUS: GEnome traNsformatIon and spatial representation of mUltiomicS dataeLife12:RP87133
[https://doi.org/10.7554/eLife.87133.1 ](https://doi.org/10.7554/eLife.87133.1)


