---
layout: post
title: Estimating Osteoarthritis Progression With Multimodal Deep Learning 
date: 2024-12-03 11:29:00
description: A Biomedical application of multimodal AI 
tags: AI biomedical
categories: research
---
## Introduction 
Osteoarthritis (OA) is the most common form of arthritis characterized by deterioration of articular cartilage. It commonly affects the knee, hip and spine and is one of the leading causes of disability worldwide. There is no cure for OA and the current standard of care is to manage symptoms until joint replacement surgery is required<sup>[[1](#1)]</sup>. The development of treatment strategies is hindered by the inability to predict the progression of OA due to its diverse etiology and heterogenous disease trajectories<sup>[[2](#2)]</sup>. OA was believed to be driven by the wear-and-tear of cartilage due to overuse or injury, but is now considered to be multifactorial<sup>[[2](#2)]</sup> in nature and a sedentary lifestyle is ironically a risk factor. 

Diagnosis of OA is usually confirmed by x-ray imaging, however given the involvement of soft tissues, MRIs are increasingly being used. However, evaluating structural features in MRI images is time consuming and reader dependent<sup>[[3](#3)]</sup> and automated methods are being researched [3]. Progression of OA is estimated by both patient reported symptoms such as pain and stiffness, range of motion, as well as radiographic results. However, most contemporary models in medicine are unimodal; i.e., they can process only one kind of data such as images (functional or anatomical) or text. Some models attempt to integrate multiple sources by condensing data into “biomarkers” based on (and therefore limited by) expert knowledge but they also discard a lot of potentially relevant information.  

Recent developments in artificial intelligence (AI) have enabled AI models to process multiple types of data such as images and sound enabling tasks such as visual question answering. These techniques are not limited to just text, images and audio, and can be applied to integrate omics data, biosignals and other clinical observations into deep learning models. Such Multimodal Deep Learning (MMDL) models will be able to consider data from multiple sources for diagnosis just like clinicians and learn high-dimensional representations from raw data that may uncover novel relationships between modalities. Being able to consider multiple sources without prejudice is advantageous for analysing diseases that are not fully understood such as OA.

MMDL has been successfully applied in medical tasks<sup>[[4](#4)]</sup>; learning features for predicting cancer survival, cardiovascular risk etc, and learning representations for classifying and segmenting tumours. Research<sup>[[4,5](#4)]</sup> has shown that MMDL models perform better than unimodal methods in these tasks. Predicting disease progression requires going beyond static representations and understanding temporal information from longitudinal data. RNN-based methods have been used to learn spatiotemporal representations of degenerative diseases such as Alzheimer's <sup>[[6](#6)]</sup> and estimate disease progression<sup>[[7](#7)]</sup>. However, OA is not purely degenerative as not all patients will progress symptomatically, radiologically, or to joint replacement. The diverse pathophysiology  of OA makes developing MMDL models a challenge.

## Statement of problem and justification
Emerging research suggests that OA is a collection of heterogeneous pathologies that result in a common outcome rather than being a single disease. This heterogeneity includes disease subtypes, the structures affected, where OA processes begin, and risk factors, all depending on the joints . This diversity of pathologies hinder effective allocation of resources and are a challenge when evaluating new treatments. 

Longitudinal MMDL models are able to process features in medical images (MRI, X-ray) along with patient symptoms and risk factors to learn complex spatiotemporal representations of OA. These representations can help in classification of patients for clinical trials, act as digital twins for evaluating treatments, and may uncover reasons for  different progression pathways. 

In addition to clinical value, this research may also result in novel solutions for handling irregularly spaced data;  data fusion techniques for medical images and for investigating how MMDL models behave with discordant data and discrepant outcomes.

## Scope of the research
This research aims to develop a multimodal model to estimate the progression of OA and use insights from the learned representation to understand the pathophysiology of OA. 

To this end, the following objectives have been identified;
1. Develop an MMDL model using longitudinal OA datasets such as OAI/MOST. 
2. Apply interpretability techniques to discover novel relationships and relate them to biological processes.  

## Proposed Methodology
1. Literature Review:  The preliminary stage is to conduct an extensive literature review to investigate existing methods for predicting the progression of OA, extracting OA relevant features from medical images and existing methods of multimodal data fusion.

2. Model Architecture Design: The second step is to develop a novel MMDL model using medical images, pain scores, chemical data and other clinical data to estimate future visit data and outcomes using the OAI dataset.
    1. Evaluate strategies for missing data.
    2. Evaluate strategies to handle irregular time intervals between data points.
    3. Evaluate different data fusion strategies for combining image data and text

3. Understanding Pathophysiology: Use Explainable AI techniques to investigate relationships between features. Evaluate if these insights are statistically significant to patient outcomes and are related to known processes.


## References
1. <a name="1"></a> Halilaj, E., Le, Y., Hicks, J. L., Hastie, T. J., & Delp, S. L. (2018). Modeling and predicting osteoarthritis progression: data from the osteoarthritis initiative. Osteoarthritis and Cartilage, 26(12), 1643–1650. [https://doi.org/10.1016/j.joca.2018.08.003](https://doi.org/10.1016/j.joca.2018.08.003)

2. <a name="2"></a> Deveza, L. A., Melo, L., Yamato, T. P., Mills, K., Ravi, V., & Hunter, D. J. (2017). Knee osteoarthritis phenotypes and their relevance for outcomes: a systematic review. Osteoarthritis and Cartilage, 1926–1941. [https://doi.org/10.1016/j.joca.2017.08.009](https://doi.org/10.1016/j.joca.2017.08.009)

3. <a name="3"></a> Kijowski, R., Fritz, J., & Deniz, C. M. (2023). Deep learning applications in osteoarthritis imaging. Skeletal Radiology. [https://doi.org/10.1007/s00256-023-04296-6](https://doi.org/10.1007/s00256-023-04296-6)

4. <a name="4"></a> J. Venugopalan, L. Tong, H. R. Hassanzadeh, and M. D. Wang, “Multimodal deep learning models for early detection of Alzheimer’s disease stage,” Sci Rep, vol. 11, no. 1, p. 3254, Feb. 2021, doi: [10.1038/s41598-020-74399-w.](https://doi.org/10.1038/s41598-020-74399-w.)

5. <a name="5"></a> X. Pei, K. Zuo, Y. Li, and Z. Pang, “A Review of the Application of Multi-modal Deep Learning in Medicine: Bibliometrics and Future Directions,” Int J Comput Intell Syst, vol. 16, no. 1, p. 44, Mar. 2023, doi: [10.1007/s44196-023-00225-6.](https://doi.org/10.1007/s44196-023-00225-6)

6. <a name="6"></a> D. Lachinov, A. Chakravarty, C. Grechenig, U. Schmidt-Erfurth, and H. Bogunovic, “Learning Spatio-Temporal Model of Disease Progression with NeuralODEs from Longitudinal Volumetric Data,” Nov. 08, 2022, arXiv: arXiv:2211.04234. Accessed: Oct. 01, 2024. [Online]. Available: [http://arxiv.org/abs/2211.04234](http://arxiv.org/abs/2211.04234)

7. <a name="7"></a> M. Al Olaimat, J. Martinez, F. Saeed, S. Bozdag, and Alzheimer’s Disease Neuroimaging Initiative, “PPAD: a deep learning architecture to predict progression of Alzheimer’s disease,” Bioinformatics, vol. 39, no. Supplement_1, pp. i149–i157, Jun. 2023, doi: [10.1093/bioinformatics/btad249.](https://doi.org/10.1093/bioinformatics/btad249)

