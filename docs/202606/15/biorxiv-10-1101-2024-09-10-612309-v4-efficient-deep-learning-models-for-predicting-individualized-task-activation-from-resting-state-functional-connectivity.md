---
title: Efficient Deep Learning Models for Predicting Individualized Task Activation from Resting-State Functional Connectivity
title_zh: 基于静息态功能连接预测个体任务激活的高效深度学习模型
authors: "Madsen, S. J., Lee, Y.-E., Quah, S. K. L., Uddin, L. Q., Mumford, J. A., Barch, D. M., Fair, D. A., Gotlib, I. H., Poldrack, R. A., Kuceyeski, A., Saggar, M."
date: 2026-06-12
pdf: "https://www.biorxiv.org/content/10.1101/2024.09.10.612309v4.full.pdf"
tags: ["query:med-lifelong"]
score: 7.0
evidence: 开发高效深度学习模型从静息态fMRI预测任务激活，推进医学图像分析
tldr: 深度学习可从静息态功能连接预测个体任务激活，但模型效率与可扩展性待提升。本研究基于BrainSurfCNN提出BrainSERF（引入通道注意力）与BrainSurfGCN（利用皮层拓扑图消息传递）。结果表明所有模型预测性能相当，但BrainSurfGCN大幅降低模型大小与训练时间。预测精度受行为表现、数据质量和信号可靠性制约，凸显先验结构对高效预测的价值。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有模型预测个体大脑激活的效率与可扩展性不足，需探索架构优化以提升实用性。
method: 基于HCP数据，系统比较BrainSurfCNN及其扩展BrainSERF（通道注意力）和BrainSurfGCN（图卷积）的预测性能。
result: 所有模型预测准确度相当，BrainSERF稍优个体特征捕获，BrainSurfGCN显著压缩模型并加速训练；低信噪比与高个体差异限制预测。
conclusion: 融入拓扑与功能先验可在不损失精度下提升模型效率，但预测上限由神经信号可靠性决定。
---

## 摘要
深度学习模型已展现出从静息态功能磁共振成像预测任务诱发脑激活的潜力，为无需任务数据的个体化脑图谱绘制提供了途径。本研究系统评估了提高此类模型效率和可扩展性的架构策略。利用人类连接组计划的数据，我们复现了BrainSurfCNN框架，并提出两种扩展：BrainSERF通过压缩与激励模块引入通道注意力，BrainSurfGCN则是一种基于图的模型，利用皮层网格拓扑进行高效消息传递。在空间相关、Dice系数、Dice AUC和个体识别准确率等多个评价指标上，所有模型均取得了可比的预测性能。尽管精度相近，所提模型各有优势。BrainSERF在捕获个体特异性特征方面略有提升，而BrainSurfGCN显著减小了模型体积和训练时间，展现出性能与计算效率之间的有利权衡。除架构比较外，我们还探讨了影响预测精度波动的原因。我们发现，行为任务表现、静息态数据质量以及任务激活的个体间差异共同制约预测保真度。特别是，信号可靠性较低且变异性较高的对比在所有模型中都表现出较低的可预测性。这些发现共同表明，融入拓扑和功能结构先验可以在不牺牲精度的前提下提高深度学习模型的效率，同时强调预测性能从根本上受限于底层神经信号的可靠性。

## Abstract
Deep learning models have demonstrated the potential to predict task-evoked brain activation from resting-state fMRI, offering a pathway toward individualized brain mapping without requiring task-based data. In this study, we systematically evaluate architectural strategies for improving the efficiency and scalability of such models. Using data from the Human Connectome Project, we replicate the BrainSurfCNN framework and introduce two extensions: BrainSERF, which incorporates channel-wise attention through squeeze-and-excitation modules, and BrainSurfGCN, a graph-based model that leverages cortical mesh topology for efficient message passing. Across multiple evaluation metrics, including spatial correlation, Dice score, Dice AUC, and subject identification accuracy, all models achieve comparable predictive performance. Despite similar accuracy, the proposed models o!er distinct advantages. BrainSERF provides modest improvements in capturing individual-specific features, while BrainSurfGCN achieves substantial reductions in model size and training time, highlighting a favorable trade-off between performance and computational efficiency. Beyond architectural comparisons, we investigate factors driving variability in prediction accuracy. We find that behavioral task performance, resting-state data quality, and inter-subject variability in task activation jointly constrain prediction fidelity. In particular, contrasts with lower signal reliability and higher variability exhibit reduced predictability across all models. Together, these findings demonstrate that incorporating topological and functional structural priors can improve the efficiency of deep learning models without sacrificing accuracy, while also emphasizing that prediction performance is fundamentally limited by the reliability of the underlying neural signals.