---
title: "DINMC: A Deep Learning Framework for Interpretable Normative Model Construction and Pathological Brain Alteration Detection"
title_zh: DINMC：一个用于可解释规范模型构建和病理性脑改变检测的深度学习框架
authors: "Ge, Z., Liu, S., Dou, W."
date: 2026-05-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728652v1.full.pdf"
tags: ["query:med-lifelong"]
score: 8.0
evidence: 可解释规范建模用于脑图像分析，检测神经退行性疾病相关改变
tldr: 现有神经影像规范性建模方法缺乏可解释性，难以捕捉临床相关病理变化。本研究提出DINMC框架，结合U形卷积自编码器与统计假设检验，从大规模健康队列构建可解释模型，并融合原始与偏差特征计算病理置信度。在小脑型多系统萎缩症预后中，分类AUC达0.972，回归R2达0.432，性能显著优于传统方法。该框架为神经影像分析提供了可解释、高性能的工具，并可扩展至其他生物医学领域。
source: biorxiv
selection_source: carryover_cache
motivation: 现有方法缺乏可解释性，且无法有效捕捉神经退行性疾病的临床相关神经解剖病理变化。
method: 利用多中心健康队列神经影像数据训练U形卷积自编码器，通过融合原始与偏差特征空间计算病理置信度。
result: 病理置信度揭示了受影响脑区及其与临床量表的相关性；分类AUC达0.972，回归R2达0.432，优于传统方法。
conclusion: DINMC为神经影像分析提供了深度可解释框架，结合深度学习与统计检验，提升了可解释性与性能，应用前景广泛。
---

## 摘要
背景与目的 规范建模是理解神经退行性疾病（如小脑型多系统萎缩）脑部改变的关键工具。然而，现有方法缺乏可解释性，且未能捕获具有临床意义的病理变化。本研究提出 DINMC，一个深度可解释规范模型构建框架，将基于自编码器的学习与统计假设检验相结合，以更好地捕捉和解释疾病特异性神经解剖学改变。

方法 DINMC 框架利用来自多中心大规模健康队列的神经影像数据构建规范模型。它使用 U 形卷积自编码器训练这些模型，然后将其应用于同一研究队列中患者和健康对照的脑特征重建。通过融合原始特征空间和偏差特征空间导出病理置信度值，提供每个特征维度所反映的疾病相关病理的度量。该框架通过统计分析和预后分类与回归任务进行验证。

结果 病理置信度为疾病影响最严重的神经解剖区域以及这些区域的变化与临床评估量表之间的相关性提供了宝贵见解。我们的最优模型在预后预测任务中优于传统方法，分类任务的 AUC 为 0.972，回归任务的 R² 为 0.432。

结论 DINMC 为神经影像分析提供了一个新颖且可解释的框架。通过结合深度学习和统计假设检验，该框架为改进神经影像规范模型的可解释性和性能提供了独特的解决方案。该方法可扩展到其他神经影像数据集，为更广泛的生物医学应用提供了一个通用工具。

## Abstract
Background and ObjectiveNormative modeling is a key tool for understanding brain alterations in neurodegenerative diseases, such as cerebellar-type multiple system atrophy. However, existing methods lack interpretability and fail to capture clinically meaningful pathological changes. This study presents DINMC, a Deep Interpretable Normative Model Construction framework, which combines autoencoder-based learning with statistical hypothesis testing to better capture and interpret disease-specific neu-roanatomical changes.

MethodsThe DINMC framework constructs normative models using neuroimaging data from multi-site large healthy cohorts. It utilizes a U-shaped convolutional autoencoder to train these models, which are then applied to reconstruct brain features from both patients and healthy controls within the same study cohort. Pathological confidence values are derived by fusing original and deviation feature spaces, offering a measure of disease-related pathology reflected in each dimension of the features. The framework was validated through statistical analysis and prognostic classification and regression tasks.

ResultsThe pathological confidence provides valuable insights into the neuroanatomical regions most affected by the disease, as well as the correlation between changes in these regions and clinical assessment scales. Our optimal model outperform traditional methods in prognostic prediction tasks, with an AUC of 0.972 for classification tasks and an R2 of 0.432 for regression tasks.

ConclusionDINMC provides a novel and interpretable framework for neuroimaging analysis. By combining deep learning and statistical hypothesis testing, this framework offers a unique solution to improving both the interpretability and performance of normative models in neuroimaging. The approach is scalable to other neuroimaging datasets, offering a versatile tool for broader biomedical applications.