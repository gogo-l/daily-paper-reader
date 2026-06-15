---
title: Generalisable tissue-wide molecular reconstruction from histology
title_zh: 从组织学图像实现可推广的全组织分子重建
authors: "Zhang, A., Yu, L., Bian, B., Cao, Y., Ye, S., Han, E., Robertson, H., Dong, Y., Mao, Y., Liu, B., Patrick, E., Kim, J., Yang, J. Y. H."
date: 2026-06-12
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.09.731252v1.full.pdf"
tags: ["query:med-lifelong"]
score: 8.0
evidence: "GHIST+从H&E组织学预测单细胞分子状态，实现空间转录组学分析。"
tldr: "空间转录组技术因测量稀疏和基因面板异质难以扩展。本研究提出GHIST+框架，整合细胞形态、局部组织背景和共享组织表示，从H&E染色图像预测全组织单细胞分子状态。在多种癌症和正常乳腺组织中，GHIST+从稀疏TMA数据重建了保留空间结构和细胞类型组织的分子图谱，并关联年龄状态。该方法将稀疏空间实验转化为可扩展的队列规模组织学分子重建。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以处理稀疏分子测量、部分重叠基因面板和跨异构数据集的组织范围重建。
method: "GHIST+整合细胞形态、局部组织背景和共享组织表示，从H&E组织学预测全组织单细胞分子状态。"
result: 在多种癌症和GTEx乳腺组织中，GHIST+从稀疏TMA数据重建了保留空间结构、细胞类型和年龄状态的组织范围分子图谱。
conclusion: GHIST+提供了将稀疏空间分析转化为组织范围分子图谱的可扩展框架，实现队列规模的组织学分子重建。
---

## 摘要
空间转录组学技术测量完整组织内的基因表达，但仍然难以在大面积组织切片和患者队列中进行扩展。因此，许多研究依赖于组织微阵列（TMAs）或稀疏的空间分析设计，其中分子测量仅适用于有限的组织区域，并且通常使用异质性基因面板生成。现有的从H&E到空间基因表达预测方法仍面临稀疏分子测量、部分重叠的基因面板以及跨异质空间数据集的全组织重建等挑战。在这里，我们提出了GHIST+，一个从H&E组织学图像重建全组织单细胞分子状态的框架。GHIST+整合了细胞形态、局部组织环境和共享组织表征，将稀疏分子测量扩展为跨异质空间数据集的全组织分子图谱。在多种癌症类型和GTEx乳腺组织中，GHIST+从稀疏的TMA衍生测量中重建出具有生物学意义的全组织分子组织，同时保留了空间组织结构、细胞类型组成以及与年龄相关的组织状态，适用于癌症和非癌症场景。GHIST+建立了一个可扩展的框架，将稀疏的空间分析实验转化为全组织分子图谱，从而在异质空间转录组学设置下，从常规组织学图像实现队列规模的分子重建。

## Abstract
Spatial transcriptomics technologies measure gene expression within intact tissues but remain difficult to scale across large tissue sections and patient cohorts. Consequently, many studies rely on tissue microarrays (TMAs) or sparse spatial profiling designs, where molecular measurements are available for only limited tissue regions and are often generated using heterogeneous gene panels. Existing H&E to spatial gene expression prediction methods remain challenged by sparse molecular measurements, partially overlapping gene panels and tissue-wide reconstruction across heterogeneous spatial datasets. Here, we present GHIST+, a framework for tissue-wide reconstruction of single-cell molecular states from H&E histology. GHIST+ integrates cellular morphology, local tissue context and shared tissue representations to extend sparse molecular measurements into tissue-wide molecular maps across heterogeneous spatial datasets. Across multiple cancer types and GTEx breast tissues, GHIST+ reconstructs biologically meaningful tissue-wide molecular organisation from sparse TMA-derived measurements while preserving spatial tissue structure, cell-type organisation and age-associated tissue states across cancer and non-cancer settings. GHIST+ establishes a scalable framework for transforming sparse spatial profiling experiments into tissue-wide molecular maps, enabling cohort-scale molecular reconstruction from routine histology under heterogeneous spatial transcriptomic settings.