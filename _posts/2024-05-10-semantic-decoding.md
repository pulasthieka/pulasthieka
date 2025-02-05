---
layout: post
title: Novel Computational Models for Semantic Decoding
date: 2023-10-20 11:29:00
description: Review article on the state of art on semantic decoding
tags: AI biomedical
categories: research
---
## Introduction
The human brain is an extremely complex organ with many processes that are not completely understood. This research will focus on one such area; the computation of meaning.  Recent developments in measuring brain activity and novel computational methods have led to breakthroughs in interpreting brain activity. It is now possible, with reasonable accuracy to translate brain activity into motion <sup>[[1](#1)]</sup>, interpret imagined speech, and decode neural activity to reconstruct visual <sup>[[2](#2)]</sup> or auditory stimuli <sup>[[3](#3)]</sup>. While it’s possible to decode low-level cognitive functions such as above, decoding complex processes such as semantic memory is nascent.


Semantic decoding focuses on deciphering the meaning and idea held in the mind which is different to perceptual information (how something looks or sounds).  Semantic information is associated with memory retrieval and inference. You will know that a burger is a tasty food despite looking at a printed image of it. Semantic information also incorporates a conceptual structure; similar brain regions are activated when conceptually similar objects such as a bird and an aeroplane (concept: flying objects) are shown. 


Semantic decoding helps to understand how someone else perceives the world and this is useful in treating neurological disorders like Schrisprenia and depression. Semantic information is involved in memory formation and retrieval and a better understanding of these mechanisms will help develop treatments for degenerative diseases like Alzheimer's. It will also be useful in understanding neuro-cognitive development and difficulties like autism.  Semantic decoding is instrumental in developing advanced brain-machine interfaces that can directly infer intention/meaning without requiring users to spell out each letter. 


Researchers have used methods such as fMRI<sup>[[4](#4)]</sup>, EEG<sup>[[5](#5)]</sup>, fNIRS<sup>[[6](#6)]</sup> and even intracranial electrodes<sup>[[7](#7)]</sup> to distinguish semantic concepts such as tools and mammals. Researchers prefer to use fMRI due to it’s high spatial resolution, but work is being done to use more portable devices such as fNIRS.. Recent works have been able to decode complex concepts such as contiguous language<sup>[[8](#8)]</sup> and natural movies<sup>[[9](#9)]</sup> from fMRI data by relying on deep learning-based computational methods. 


Deep learning is not yet fast enough for real-time decoding and has difficulties in explaining the underlying mechanisms. Another limitation lies in the generalizability of results. Most studies focus on a small subject group and how these results translate to a wider set of subjects is not evaluated. The use of recent developments such as transfer learning and co-learning have not yet been explored in the context of semantic decoding. This research aims to develop novel computational methods to improve semantic decoding and develop the understanding of neural semantic representation. 

## Literature Review
Philosophers, psychologists and scientists have long sought the answer to how meaning is represented and organized in the brain.  How do we know a “banana” is a banana? Is it by comparing to a prototype of a banana stored in the mind by averaging multiple exposures to the fruit or is it via the combination of attributes such as the shape and colour that are activated when we perceive a banana?  The study of semantic information in the brain aims to uncover the mechanisms that construct meaning from experience. Semantic encoding aims to predict the brain activity for a given stimulus, while semantic decoding aims to predict the stimulus from brain activity. These methods help understand the neuro-semantic code; how meaning is stored in the brain. 

Neuroimaging data can be considered to be measuring variation across a set of “units” which could be voxels for fMRI and channels for EEG. All imaging methods yield thousands of noisy measurements for each stimulus in each participant. The computational methods used to make sense of this data and predict the stimulus can be broadly categorised into three categories. 

Classification is a supervised machine learning method that fits models (Naive Bayes, Support Vector Machines, logistic regression) to classify neural activity. With more predictors (neural input) than data points overfitting is a common challenge. Regularisation methods such as the L2-norm, L1-norm, LASSO or a combination of these can be used to avoid overfitting, however, the choice of the algorithm impacts the discovery of semantic structure. 
Representational Similarity Analysis (RSA)  creates a matrix based on dissimilarity between brain activity patterns for each pair of input stimuli and uses this representational dissimilarity matrix (RDM) to understand the representational geometry of the brain. However, as semantic information covaries with many confounding factors RSA results have been difficult to interpret<sup>[[10](#10)]</sup>. 
Deep learning-based methods are a recent development that shows promising results. Deep learning architectures such as Long-Short Term Memory (LSTM), Convolutional Neural Networks (CNN), Autoencoders and Transformers have been used for decoding emotion, direction and location, music and even what is being remembered in a working memory task <sup>[[11](#11)]</sup>. 

Deep learning (DL) is an attractive method for use in semantic decoding because of its ability to learn complex, non-linear transformations in data. As larger datasets are generated with automated, long-term experimental setups for single subjects and large-scale recordings across multiple subjects, deep learning is suited to take advantage of this flood of data<sup>[[11](#11)]</sup>.
### Gaps in research

- The generalizability of results has not been evaluated. Most studies are limited to a very small group of subjects and are often taken from a distinct social group.  Semantic representation is dependent on personal experience and it is not known how results translate to the wider public.
- Developments in computational methods such as transfer-learning and co-learning have not yet been explored in the context of semantic decoding. These may allow the fine-tuning of pre-trained models to be used with  new subjects
- The variability of semantic concepts has not yet been explored. For example, would the semantic concept of a car be more activated when deciding on a car to buy or would it be the same as when seeing a car passing you in the street<sup>[[12](#12)]</sup>?
- Studies have not focused on evaluating the hypothesis of semantic representation. Most studies assume a representation, eg: vector spaces/feature networks but a different representation may perform better. New developments in LLMs may lead to new hypotheses. 

## Research Question
> Can we develop a better computational model for semantic decoding?

Developments in explaining DL models have shown methods for extracting interpretable insights from complex DL models. These methods could be instrumental in extracting the semantic representation of large models and comparing them to existing hypotheses. Such representations could also give insight into the brain’s mechanisms for processing semantic data. Advances in DL such as transfer learning and co-learning have been used in different domains with limited data to fine-tune models that are trained on a different set of data. These methods could allow models to be trained for larger sample sets. It would be exciting to use these methods to develop algorithms for semantic decoding. 
## Proposed Methodology
The research approach is designed as follows;

1. **Literature Review**:  The preliminary stage is a literature review to investigate existing methods for semantic decoding to identify the gaps and challenges in the current approaches. 
2. **Data Collection and Preprocessing**: The second stage is to design and carry out an experiment to create a dataset of brain recordings designed for training a model for semantic decoding.  Neural data can be obtained from humans or animal models. This research will focus on visual stimuli as language is known to have a left hemisphere bias. 
3. **Algorithm/ model development**: The third step is to develop a novel model architecture that addresses the gaps in research.  The algorithm should be able to incorporate developments such as transfer learning and explainable AI techniques. 
4. **Evaluation and Validation**: The fourth step is to evaluate the performance, accuracy, and insights of the new approach. Performance evaluations may involve comparing against state-of-the-art methods. The effectiveness of novel methods for generalizability will also be evaluated.

## References
1. <a name="1"></a> Hallett, M., DelRosso, L. M., Elble, R., Ferri, R., Horak, F. B., Lehericy, S., Mancini, M., Matsuhashi, M., Matsumoto, R., Muthuraman, M., Raethjen, J., & Shibasaki, H. (2021). Evaluation of movement and brain activity. Clinical Neurophysiology, 132(10), 2608–2638. [https://doi.org/10.1016/j.clinph.2021.04.023 ](https://doi.org/10.1016/j.clinph.2021.04.023 )
1. <a name="2"></a> Vodrahalli, K., Chen, P.-H., Liang, Y., Baldassano, C., Chen, J., Yong, E., Honey, C., Hasson, U., Ramadge, P., Norman, K. A., & Arora, S. (2018). Mapping between fMRI responses to movies and their natural language annotations. NeuroImage, 180, 223–231. [https://doi.org/10.1016/j.neuroimage.2017.06.042 ](https://doi.org/10.1016/j.neuroimage.2017.06.042 )
3. <a name="3"></a> Daly, I. (2023). Neural decoding of music from the EEG. Scientific Reports, 13(1). [https://doi.org/10.1038/s41598-022-27361-x ](https://doi.org/10.1038/s41598-022-27361-x )
4. <a name="4"></a> Bauer, A. J., & Just, M. A. (2019). Brain reading and behavioral methods provide complementary perspectives on the representation of concepts. NeuroImage, 186, 794–805. [https://doi.org/10.1016/j.neuroimage.2018.11.022 ](https://doi.org/10.1016/j.neuroimage.2018.11.022)
5. <a name="5"></a> Murphy, B., Poesio, M., Bovolo, F., Bruzzone, L., Dalponte, M., & Lakany, H. (2011). EEG decoding of semantic category reveals distributed representations for single concepts. Brain and Language, 117(1), 12–22. [https://doi.org/10.1016/j.bandl.2010.09.013](https://doi.org/10.1016/j.bandl.2010.09.013)
6. <a name="6"></a> Rybář, M., Poli, R., & Daly, I. (2021). Decoding of semantic categories of imagined concepts of animals and tools in fNIRS. Journal of Neural Engineering, 18(4), 046035. [https://doi.org/10.1088/1741-2552/abf2e5](https://doi.org/10.1088/1741-2552/abf2e5)
7. <a name="7"></a> Miller, K. J., Hermes, D., & Staff, N. P. (2020). The current state of electrocorticography-based brain–computer interfaces. Neurosurgical Focus, 49(1), E2. [https://doi.org/10.3171/2020.4.focus20185](https://doi.org/10.3171/2020.4.focus20185)
8. <a name="8"></a> Tang, J., LeBel, A., Jain, S., & Huth, A. G. (2023). Semantic reconstruction of continuous language from non-invasive brain recordings. Nature Neuroscience. [https://doi.org/10.1038/s41593-023-01304-9](https://doi.org/10.1038/s41593-023-01304-9)
9. <a name="9"></a> Huth, A. G., Lee, T., Nishimoto, S., Bilenko, N. Y., Vu, A. T., & Gallant, J. L. (2016). Decoding the Semantic Content of Natural Movies from Human Brain Activity. Frontiers in Systems Neuroscience, 10. [https://doi.org/10.3389/fnsys.2016.00081](https://doi.org/10.3389/fnsys.2016.00081)
10. <a name="10"></a> Devereux, B. J., Clarke, A., & Tyler, L. K. (2018). Integrated deep visual and semantic attractor neural networks predict fMRI pattern-information along the ventral object processing pathway. Scientific Reports, 8(1). [https://doi.org/10.1038/s41598-018-28865-1](https://doi.org/10.1038/s41598-018-28865-1)
11. <a name="11"></a> Livezey, J. A., & Glaser, J. I. (2020). Deep learning approaches for neural decoding across architectures and recording modalities. Briefings in Bioinformatics. [https://doi.org/10.1093/bib/bbaa355](https://doi.org/10.1093/bib/bbaa355)
12. <a name="12"></a> Frisby, S. L., Halai, A. D., Cox, C. R., Lambon Ralph, M. A., & Rogers, T. T. (2023). Decoding semantic representations in mind and brain. Trends in Cognitive Sciences. [https://doi.org/10.1016/j.tics.2022.12.006](https://doi.org/10.1016/j.tics.2022.12.006)
