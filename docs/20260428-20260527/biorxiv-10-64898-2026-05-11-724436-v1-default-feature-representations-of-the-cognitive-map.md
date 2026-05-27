---
title: Default Feature Representations of the Cognitive Map
title_zh: 认知地图的默认特征表示
authors: "Bazarjani, A., Piray, P."
date: 2026-05-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.11.724436v1.full.pdf"
tags: ["query:continual"]
score: 6.0
evidence: 提出认知图的特征化参数化方法，随环境变化更新，实现持续表征更新
tldr: 在环境变化时更新预测性认知地图对生物智能体与强化学习至关重要，但现有方法或依赖显式模型，或需学习完整状态-索引地图。本研究提出默认特征表示（DFR），将认知地图分解为固定特征基和自适应环境运算符。无模型DFR仅从采样转换中学习运算符，即可重构扰动地图，其规划性能与基于模型的解相当，在重规划任务中显著优于后继表示基线，还能复现网格细胞的局部重映射现象。DFR为认知地图的快速更新提供了基于样本的计算解释，彰显了内嗅皮层网格场跨环境稳定性的潜在机制。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有更新认知地图的方法或需显式环境模型，或需从零学全状态索引，缺乏从局部经验快速适应的样本高效机制。
method: 提出默认特征表示（DFR），将认知地图参数化为固定特征基与自适应环境运算符的组合，并给出模型已知条件下闭式解和从样本学习的时序差分学习规则。
result: 无模型DFR仅凭采样转移就能恢复环境扰动后的地图，其规划表现与模型解法相当，且重规划远超后继表示基线，并成功复现了局部环境变化下网格细胞的局部重映射。
conclusion: DFR通过分解认知地图为稳定特征基和快速适应运算符，为基于样本的预测地图更新提供了计算理解，解释了内嗅皮层网格场跨环境的稳定性。
---

## 摘要
当环境发生变化时，更新预测性认知地图是生物智能体和强化学习面临的核心问题，然而现有方法要么依赖于明确的模型知识，要么从样本中学习完整的状态索引地图。我们提出了默认特征表示（DFR），这是一种对预测性认知地图进行特征化参数化的方法，其中固定的特征基与编码当前环境的算子相结合。我们提供了该算子的两种形式：当环境间的结构变化已知时，采用基于模型的闭式解；以及一种无模型的时序差分学习规则，该规则能从采样转移中恢复出算子，并可证明收敛至基于模型的解。无模型的DFR仅从样本中重建受扰动的地图，其规划性能可与基于模型的解相媲美，并在重新规划任务上显著优于后继表示基线。我们还表明，DFR能捕捉到局部环境变化下观察到的网格细胞局部重映射现象。通过将认知地图分为稳定的特征基和快速适应的算子，DFR从样本层面解释了预测地图如何根据局部经验进行更新，这与内嗅皮层网格野在不同环境中的稳定性相呼应。

## Abstract
Updating a predictive cognitive map when the environment changes is a central problem for both biological agents and reinforcement learning, yet existing approaches either depend on explicit model knowledge or learn the full state-indexed map from samples. We propose Default Feature Representations (DFR), a featurized parameterization of predictive cognitive maps in which a fixed feature basis is composed with an operator that encodes the current environment. We provide two forms for the operator: a model-based closed form when the structural change between environments is known, and a model-free temporal-difference learning rule that recovers the operator from sampled transitions, with provable convergence to the model-based solution. The model-free DFR reconstructs the perturbed map from samples alone, achieves planning performance comparable to the model-based solution, and substantially outperforms successor-representation baselines on replanning tasks. We also show that DFR captures the local remapping of grid cells observed under local environmental change. By separating the cognitive map into a stable feature basis and a fast-adapting operator, DFR offers a sample-based account of how a predictive map can be updated from local experience, mirroring the stability of entorhinal grid fields across environments.