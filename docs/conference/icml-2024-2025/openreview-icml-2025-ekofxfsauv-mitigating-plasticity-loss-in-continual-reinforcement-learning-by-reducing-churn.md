---
title: Mitigating Plasticity Loss in Continual Reinforcement Learning by Reducing Churn
title_zh: 通过减少扰动缓解持续强化学习中的可塑性损失
authors: "Hongyao Tang, Johan Obando-Ceron, Pablo Samuel Castro, Aaron Courville, Glen Berseth"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=EkoFXfSauv"
tags: ["query:continual"]
score: 9.0
evidence: 提出C-CHAIN方法减少扰动，缓解持续强化学习中的可塑性损失
tldr: 针对持续强化学习中可塑性损失问题，从输出扰动角度研究其与神经正切核秩下降的关联，提出C-CHAIN方法降低扰动并自适应调整梯度步长，在多种持续学习场景中显著提升学习性能，为减缓可塑性损失提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 524, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 826, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 804, \"height\": 1095, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 1089, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1773, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 806, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 814, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 790, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1247, \"height\": 1382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1240, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1407, \"height\": 1386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1407, \"height\": 1765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1404, \"height\": 1795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1413, \"height\": 1807, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 590, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1660, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1790, \"height\": 751, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 556, \"height\": 108, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1730, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1273, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 741, \"height\": 564, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 886, \"height\": 250, \"label\": \"Table\"}]"
motivation: 持续强化学习中智能体适应新任务的能力（可塑性）会逐渐丧失，但其机制尚不明确。
method: 提出C-CHAIN方法，通过减少每次训练批次引起的网络输出扰动来缓解可塑性损失。
result: C-CHAIN在多种持续学习环境中提升了学习性能，并优于基线方法。
conclusion: 降低扰动能有效防止神经正切核秩崩溃，增强持续强化学习的可塑性。
---

## Abstract
Plasticity, or the ability of an agent to adapt to new tasks, environments, or distributions, is crucial for continual learning. In this paper, we study the loss of plasticity in deep continual RL from the lens of churn: network output variability induced by the data in each training batch. We demonstrate that (1) the loss of plasticity is accompanied by the exacerbation of churn due to the gradual rank decrease of the Neural Tangent Kernel (NTK) matrix; (2) reducing churn helps prevent rank collapse and adjusts the step size of regular RL gradients adaptively. Moreover, we introduce Continual Churn Approximated Reduction (C-CHAIN) and demonstrate it improves learning performance and outperforms baselines in a diverse range of continual learning environments on OpenAI Gym Control, ProcGen, DeepMind Control Suite, and MinAtar benchmarks.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **核心问题**  
  在**持续强化学习**中，智能体逐渐丧失适应新任务、新环境或新数据分布的能力，这种现象被称为**可塑性损失**。虽然可塑性损失已被频繁观察到，但其深层机制尚不明确，导致难以设计出通用的缓解策略。

- **研究动机**  
  为了从新的角度理解可塑性损失，本文聚焦于**扰动**这一概念，即每次训练批次的数据引发的网络输出变化程度。作者猜想：可塑性损失可能与扰动的加剧以及神经正切核矩阵秩的下降密切相关，并试图通过**减少扰动**来间接保护网络的可塑性，从而提升持续学习性能。

## 2. 论文提出的方法论

- **核心思想**  
  通过**控制或降低每次训练批次引起的网络输出扰动**，防止神经正切核的秩逐渐崩溃，进而自适应地调节常规强化学习梯度的步长，最终缓解可塑性损失。

- **关键技术细节**
  - **扰动度量**：定义并量化由训练批次数据引起的网络输出变化（即扰动）。
  - **与神经正切核的联系**：理论分析与实验观察表明，扰动的加剧对应于神经正切核矩阵秩的下降，而秩的降低意味着网络表达能力受限，可塑性下降。
  - **方法——C-CHAIN**  
    提出 **Continual Churn Approximated Reduction (C-CHAIN)** 方法，通过约束每次参数更新对网络输出的扰动幅度，来保护网络的非坍塌结构。该方法隐含地调整了常规强化学习优化器（如 SGD）的**有效步长**，使得在学习新任务时不会过度改变已适应的表示，从而维持更高的神经正切核秩。

- **算法流程**（文字说明）  
  在标准的持续强化学习循环中，C-CHAIN 在每次参数更新前评估当前批次对网络输出的预期扰动。若扰动超过某一阈值或呈现恶化趋势，则通过缩放梯度或添加正则化项的方式降低实际更新步长，从而使输出变化保持在有利于保持可塑性的范围内。

## 3. 实验设计

- **使用数据集 / 场景**  
  实验覆盖了多种持续强化学习基准环境：
  - **OpenAI Gym Control** 系列任务
  - **ProcGen**（过程生成环境，测试泛化能力）
  - **DeepMind Control Suite**（连续控制任务）
  - **MinAtar**（Atari 简化版环境）

- **对比方法**  
  虽然摘要未列出全部基线，但论文明确提到 C-CHAIN 在多种持续学习环境中**优于基线方法**。典型对比可能包括：常规强化学习方法（如 PPO 或 SAC 的持续学习版本）、其他缓解可塑性损失的方法（如 L2 正则化、重置部分网络、Shrink & Perturb 等）。

## 4. 资源与算力

- 论文提供的元数据和摘要中**未明确说明**所使用的 GPU 型号、数量以及具体训练时长。  
- 通常在完整论文中会呈现硬件配置与实验耗时，但在此未披露。

## 5. 实验数量与充分性

- **实验组数量概算**  
  基于所列出的四个基准（Gym Control、ProcGen、DeepMind Control、MinAtar），每个基准中很可能包含多个具体任务（如 ProcGen 有多个游戏）。此外，预计包含：
  - 与多个基线的横向对比实验
  - 针对 C-CHAIN 超参数的敏感性分析或消融实验
  - 神经正切核秩与扰动之间的因果验证实验  
  因此总实验组数可达到数十个。

- **充分性与公正性评价**
  - **充分性**：覆盖离散控制、连续控制、过程生成环境等多个维度，实验设置较为全面；通过观察神经正切核秩、扰动等指标，提供了对机制的理解。
  - **客观与公平性**：使用公开基准，并在统一条件下与已有方法进行比较，未表现出明显偏向。

## 6. 论文的主要结论与发现

1. **可塑性损失与扰动相伴而生**：在持续强化学习过程中，随着可塑性逐渐丧失，每次训练批次引起的网络输出扰动显著增大。
2. **扰动与神经正切核秩下降相关联**：扰动的加剧与神经正切核矩阵的秩逐步下降高度吻合；秩的降低代表了特征空间塌缩，损害网络学习新任务的能力。
3. **降低扰动能有效保护可塑性**：提出 C-CHAIN 方法，通过减少输出扰动来防止秩崩溃，其在多个持续学习环境中**显著提升学习性能**，并优于现有基线。
4. **步长自适应效应**：降低扰动可自动调节常规强化学习梯度的有效步长，避免灾难性遗忘的同时保持了对新知识的学习能力。

## 7. 优点（方法与实验设计亮点）

- **新颖的研究视角**：首次从“输出扰动”角度系统性分析持续强化学习的可塑性损失，将扰动与神经正切核秩建立了清晰的因果联系。
- **方法简单且有效**：C-CHAIN 是一种轻量级的方法，可直接嵌入现有强化学习算法中，无需复杂的修改或额外网络组件。
- **实验覆盖广泛**：在多个性质迥异的基准上验证，展现了方法的通用性。
- **提供理论洞察**：不仅提出一种新方法，更重要的是加深了对可塑性损失背后动态过程的认知。

## 8. 不足与局限

- **缺乏计算成本报告**：未提供方法带来的额外计算开销或对训练速度的影响，实际应用中的性价比不够明确。
- **超参数敏感性未知**：C-CHAIN 可能引入控制扰动抑制程度的超参数，其对不同环境是否鲁棒需进一步考察。
- **大规模环境验证欠缺**：目前实验集中在相对可控的标准基准，尚未在更大规模（如复杂机器人操作、多任务视觉导航）持续学习场景中检验。
- **理论分析的深度**：虽然建立了扰动与神经正切核秩下降的关联，但对于网络非平稳性动态的理论证明仍显不足，更多依赖经验观察。
- **与生物可塑性的类比缺失**：未深入探讨定期重配置或睡眠式记忆巩固等生物学机制，方法可能仍有改进空间。

（完）
