---
title: "Measuring Representational Shifts in Continual Learning: A Linear Transformation Perspective"
title_zh: 从线性变换视角衡量持续学习中的表征漂移
authors: "Joonkyu Kim, Yejin Kim, Jy-yong Sohn"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Kz1zCJRr1r"
tags: ["query:continual"]
score: 9.0
evidence: 提出表征差异度量用于量化持续学习中的表征漂移
tldr: 持续学习中衡量遗忘至关重要，现有指标多关注输出层，本文首次从理论角度分析表征遗忘，提出表征差异度量，通过线性变换比较模型快照间的表征空间。实验证明该指标与下游性能退化高度相关，能有效代理灾难性遗忘，为持续学习研究提供新的评估工具。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 826, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 813, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 858, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 806, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 808, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1744, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1672, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1621, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1191, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1232, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1646, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1757, \"height\": 1401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1625, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1727, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1738, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1071, \"height\": 804, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kz1zcjrr1r/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 461, \"height\": 350, \"label\": \"Table\"}]"
motivation: 现有持续学习遗忘度量多忽略隐藏层表征的变化，缺乏对表征遗忘的理论理解。
method: 提出表征差异度量，通过线性变换对齐两个模型快照的表征空间并计算差异。
result: 理论分析和实验表明，该度量与任务性能下降强相关，可有效指示遗忘程度。
conclusion: 表征差异是衡量持续学习遗忘的可靠代理，有助于诊断和算法设计。
---

## Abstract
In continual learning scenarios, catastrophic forgetting of previously learned tasks is a critical issue, making it essential to effectively measure such forgetting. Recently, there has been growing interest in focusing on representation forgetting, the forgetting measured at the hidden layer. In this paper, we provide the first theoretical analysis of representation forgetting and use this analysis to better understand the behavior of continual learning. First, we introduce a new metric called representation discrepancy, which measures the difference between representation spaces constructed by two snapshots of a model trained through continual learning. We demonstrate that our proposed metric serves as an effective surrogate for the representation forgetting while remaining analytically tractable. Second, through mathematical analysis of our metric, we derive several key findings about the dynamics of representation forgetting: the forgetting occurs more rapidly to a higher degree as the layer index increases, while increasing the width of the network slows down the forgetting process. Third, we support our theoretical findings through experiments on real image datasets, including Split-CIFAR100 and ImageNet1K.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究动机**：在持续学习中，灾难性遗忘是核心难题，但现有遗忘度量大多关注模型最终输出（如准确率下降），对隐藏层**表征遗忘**（representation forgetting）缺乏理论理解。论文旨在首次从理论层面分析表征遗忘的动态。
- **整体含义**：提出一种新的度量——**表征差异**（representation discrepancy），通过最优线性变换对齐两个模型快照的表征空间，并证明该度量能有效代理表征遗忘，且具有解析可处理性。理论揭示了遗忘过程的两阶段性质，以及网络深度与宽度对遗忘的影响。

## 2. 论文提出的方法论
- **核心思想**：用线性变换对齐同一任务在两个模型快照下的表征空间，最小化对齐后的最大距离，以此衡量表征空间的偏离程度。
- **关键定义**：
  - 表征空间 \( \mathcal{R}_t^k(h_{t'}) \)：模型 \( h_{t'} \) 在第 k 层对任务 t 的所有样本的激活集合。
  - 表征差异 \( D_t^k(\Delta t) = \min_T d\big(\mathcal{R}_t^k(h_t), T(\mathcal{R}_t^k(h_{t+\Delta t}))\big) \)，其中 \( T \) 为线性变换，距离 d 为两个集合中对应样本激活的最大欧氏距离。
- **理论分析**：
  - 在假设同一层权重可通过线性变换对齐（Assumption 1）下，推导出 \( D_t^k \) 的上界 \( U_t^k(\Delta t) \)，形式为 \( U_t^k = \mu_t c_t \|\mathcal{R}_t^k(h_t)\| \cdot f(\omega_t^{k-1}) \)，其中 f 为有界函数。
  - 基于该上界，证明遗忘曲线呈现**两阶段**：遗忘阶段（单调上升）和饱和阶段（趋于渐近值 \( \mu_t c_t \|\mathcal{R}_t^k(h_t)\| \)）。
  - 渐近遗忘与表征空间大小成正比，更深层的表征空间更大，因而遗忘更严重；网络宽度增加会降低收敛速率，延缓进入饱和阶段。

## 3. 实验设计
- **数据集与场景**：
  - **Split‑CIFAR100**：划分为 50 个任务，每任务 2 类。
  - **ImageNet1K**（降采样版）：同样划分为 50 个任务，每任务 5 类。
  - 模型均为修改后的 ResNet（9 个 block，保持特征图尺寸不变），采用顺序训练。
- **基准与对比方法**：
  - 本文主要验证所提度量与理论结论，并非提出新算法，因此未与传统遗忘度量指标（如反向迁移、遗忘率）进行 extensive 对比。与已有表征遗忘指标（如线性探测准确率下降）的相关性在实验中评估。
- **实验内容**：
  - 表征遗忘 \( \Delta P_t^k \)（线性探测精度差）随 \( \Delta t \) 的演化曲线，验证两阶段行为。
  - 渐近遗忘与表征空间大小 \( \|\mathcal{R}_t^k\| \) 的线性关系，以及 \( \|\mathcal{R}_t^k\| \) 与层索引 k 的线性关系。
  - 层索引 k 与网络宽度 m 对遗忘收敛速率（饱和时间 \( \Delta t_{\text{sat}} \) 的影响。
  - 附录中补充了表征差异 \( D_t^k \) 与 \( \Delta P_t^k \) 的相关性、上界 \( U_t^k \) 与实际 \( D_t^k \) 的一致性、不同架构（ResNet、ViT）对假设 1 的验证等。

## 4. 资源与算力
- 论文**未明确给出**所用 GPU 型号、数量以及训练时长。只提供了训练超参数（学习率 0.001、batch size 512、epochs 500 等），算力资源信息缺失。

## 5. 实验数量与充分性
- **实验数量**：
  - 图 4、图 5、图 6 展示了针对不同数据集、不同层索引和宽度的多组实验。
  - 附录中还有 10 余张图，验证假设普遍性、度量相关性、上界紧密度等。
- **充分性与公平性**：
  - 实验覆盖了两个标准图像数据集，并针对理论结论进行了系统性验证（演化趋势、渐近行为、收敛速率），逻辑链条清晰。由于研究重点在度量的理论性质与行为模式，并未与其他算法进行比较，实验目标客观且聚焦。但未在更多样化的数据类型（如 NLP）上测试，也未对假设放宽时的鲁棒性做分析，覆盖面仍有一定局限。

## 6. 论文的主要结论与发现
- 表征差异 \( D_t^k \) 是对表征遗忘的有效且解析可行的代理，与线性探测精度下降呈强线性相关。
- 遗忘曲线分为**遗忘阶段**（单调增）和**饱和阶段**（趋于平缓），且饱和值正比于该层表征空间大小。
- **深层遗忘更快、更严重**：渐近遗忘量随层索引 k 线性增长。
- **网络宽度增加可减缓遗忘**：更宽的网络延迟进入饱和阶段，降低收敛速率。
- 实验观察到表征空间大小与层索引 k 近似线性关系，从而间接推出渐近遗忘随 k 线性增长。

## 7. 优点
- **首次对表征遗忘进行理论分析**，填补了持续学习理论的一项空白。
- 提出的表征差异度量**简洁、可计算**，且与下游任务退化相关性强，具有实用价值。
- 理论结果（两阶段、层与宽度的影响）均得到实验印证，理论‑实验一致性高。
- 通过附录额外验证了关键假设（线性变换对齐权重）在多种架构（ResNet、ViT）下的合理性。

## 8. 不足与局限
- **假设 1 的限制**：要求同一层的权重可通过线性变换精确对齐，虽然实验提供了支持，但在复杂网络或非 ReLU 激活下可能不完全成立，未讨论违背该假设时的理论保证。
- **实验范围**：仅测试了图像分类任务，未涉及回归、NLP、强化学习等场景，任务均为类别拆分，泛化性有限。
- **度量对比**：未与其他已有的表征相似度度量（如 CCA、CKA）做全面比较，不清楚新度量相对于它们的优劣。
- **资源信息缺失**：未报告算力消耗，难以评估实验的可复现成本和规模。
- **理论部分假设网络层宽相等**（width m 均相同），实际中常遇到不同层宽度不同的情况，理论推广性有待探讨。
- **遗忘度量仅考虑最大距离**，可能对离群点敏感，不能反映分布整体的遗忘情况。

（完）
