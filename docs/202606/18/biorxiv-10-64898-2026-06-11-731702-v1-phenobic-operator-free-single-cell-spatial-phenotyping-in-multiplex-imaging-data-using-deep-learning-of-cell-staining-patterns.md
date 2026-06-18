---
title: "PhenoBIC: operator-free single-cell spatial phenotyping in multiplex imaging data using deep learning of cell staining patterns"
title_zh: PhenoBIC：利用细胞染色模式的深度学习对多重成像数据进行无操作员单细胞空间表型分型
authors: "Sankaranarayanan, A., Zhao, C., Hernandez, M. G., Clemens, E. A., Smythe, K. S., Kazerouni, A. S., Carr, L. L., Li, C. I., Partridge, S. C., Vinayak, S., Mittal, S."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731702v1.full.pdf"
tags: ["query:med-lifelong"]
score: 7.0
evidence: 深度学习用于多重组织成像中的细胞分类
tldr: 多重成像技术虽能精细描绘组织微环境，但现有分析流程大多依赖人工进行细胞表型分类，导致分析速度慢、人力成本高且结果存在操作者偏差。为此，我们开发了PhenoBIC，一种基于深度学习的图像分类模型，它直接利用细胞上多重生物标志物的染色模式（生物标志物印记）自动判别细胞表型。在多种生物标志物组合、组织样本类型及不同成像平台的验证中，PhenoBIC取得了约0.88的F1分数，显著超越手动圈门及其他机器学习方法。我们已公开发布包含约140万个手工标注细胞标签的训练与验证数据集，并开源模型代码，同时通过QuPath接口实现了广泛的社区部署。
source: biorxiv
selection_source: fresh_fetch
motivation: 减少多重成像分析中人工细胞表型分型带来的低效与主观性，实现高通量、可重复的单细胞空间表型。
method: 构建PhenoBIC深度学习模型，对单个细胞的多重生物标志物染色图像进行分类，实现无需人工圈门的自动表型判别。
result: 在多个组织类型、成像平台和标志物组合上，PhenoBIC的F1得分约0.88，优于手动圈门和传统机器学习方法。
conclusion: 发布大规模标注数据集和开源工具，并通过QuPath集成推动社区应用，助力标准化单细胞空间组学分析。
---

## 摘要
多重成像是一种在单细胞水平上空间解析组织微环境以揭示生物学和临床见解的宝贵工具。然而，大多数多重图像分析工作流程目前需要人工干预进行细胞表型分型，这减慢了进展，耗费人力，并产生依赖于操作员的结果。在这里，我们开发了PhenoBIC，一种预训练的深度学习模型，用于对细胞内多重生物标志物信号（细胞的生物标志物印记）进行图像分类，以对细胞表型进行分类。我们表明，在细胞标记物表达分类方面，PhenoBIC（F1分数约为0.88）优于广泛使用的人工设门和其他基于机器学习的计算方法。我们在多种生物标志物、组织采样策略（全活检和组织微阵列）、多重面板、成像平台和组织类型中验证了这一点。我们已发布了约140万个手工整理细胞表达真实标签的内部训练和验证数据集。我们已将PhenoBIC开源，并通过QuPath接口实现其社区范围的部署。

## Abstract
Multiplex imaging is a valuable tool for spatially examining tissue microenvironments at the single-cell level to uncover biological and clinical insights. However, most multiplex image analysis workflows currently require manual intervention for cell phenotyping, which slows progress, demands human effort, and yields operator-dependent outputs. Here, we developed PhenoBIC, a pre-trained deep learning model for image classification of the multiplexed biomarker signals in a cell (Biomarker Imprint of a Cell) to classify cell phenotypes. We show that PhenoBIC (F1-score ~0.88) outperforms manual gating (widely used) and other machine learning-based computational approaches for cell marker expression classification. We validated this across multiple biomarkers, tissue sampling strategies (whole biopsies and tissue microarrays), multiplex panels, imaging platforms, and tissue types. We have released our in-house training and validation datasets of ~1.4 million manually curated cell expression ground truth labels. We have also open-sourced PhenoBIC and enabled its community-wide deployment via the QuPath interface.