---
title: "Brainana: an end-to-end preprocessing framework for macaque neuroimaging"
title_zh: Brainana：猕猴神经成像的端到端预处理框架
authors: "Liu, X., Zhang, Y., Yin, Z., Zhen, Z., Arcaro, M. J."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729972v1.full.pdf"
tags: ["query:med-lifelong"]
score: 6.0
evidence: 猕猴MRI的端到端预处理框架，支持医学图像分析
tldr: 针对猕猴MRI预处理流程分散、难以集成和复现的问题，该研究开发了Brainana自动化端到端框架。该框架整合了结构像和功能像预处理、皮层表面重建、质量控制等模块，并内置猕猴特异性的深度学习脑提取和组织分割模型。通过容器化封装，Brainana可在本地或云端部署，显著降低了非人灵长类神经影像分析的门槛，提升了标准化和可复现性。它兼容BIDS标准，并利用猕猴训练的深度学习模型，有效应对了非标准采集的挑战。其云访问功能使得没有本地计算资源的研究者也能轻松使用。该工具为猕猴脑影像研究提供了高效、统一的预处理方案，支撑了后续的高级分析和解释。
source: biorxiv
selection_source: fresh_fetch
motivation: 猕猴MRI的端到端预处理框架，支持医学图像分析。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
猕猴MRI连接了非侵入式系统神经科学与细胞和回路层面的机制，但预处理仍分散于难以整合、难以适应非人灵长类数据采集且难以重复部署的各种工具中。我们提出了Brainana，一个自动化、BIDS兼容的猕猴神经成像预处理框架。Brainana在一个容器化包中集成了结构和功能预处理、皮层表面重建、质量控制、变换跟踪和脑图谱投影，并为无本地计算资源的用户提供云端访问。它包含了经过猕猴训练的深度学习模型，用于脑提取和组织分割，标准化多变的数据采集，以及针对猕猴神经解剖学优化的表面重建。在23个成像站点，Brainana处理了来自异构扫描仪、协议、物种和分辨率的数据，得到了130只猴子的准确解剖对应、可靠的本地空间皮层表面、定位的任务诱发激活和可重复的全脑静息态相关结构。Brainana实现了可重复、可扩展且易于获取的猕猴MRI预处理，支持跨研究比较和从神经元到网络的多空间尺度多模态整合。

## Abstract
Macaque MRI bridges non-invasive systems neuroscience with cellular and circuit-level mechanisms, but preprocessing remains fragmented across tools that are difficult to integrate, adapt to non-human primate acquisitions, and deploy reproducibly. We present Brainana, an automated, BIDS-compatible preprocessing framework for macaque neuroimaging. Brainana integrates structural and functional preprocessing, cortical surface reconstruction, quality control, transform tracking, and atlas projection within a containerized package, with cloud access for users without local compute. It incorporates macaque-trained deep learning models for brain extraction and tissue segmentation, conformation to standardize variable acquisitions, and surface reconstruction optimizations for macaque neuroanatomy. Across 23 imaging sites, Brainana processed data spanning heterogeneous scanners, protocols, species, and resolutions, yielding accurate anatomical correspondence across 130 monkeys, reliable native-space cortical surfaces, localized task-evoked activations, and reproducible brain-wide resting-state correlation structure. Brainana enables reproducible, scalable, and accessible macaque MRI preprocessing that supports cross-study comparison and multimodal integration across spatial scales, from neurons to networks.