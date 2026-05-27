---
title: Mitigating Catastrophic Forgetting in Online Continual Learning by Modeling Previous Task Interrelations via Pareto Optimization
title_zh: 通过Pareto优化建模先前任务关联以缓解在线持续学习中的灾难性遗忘
authors: "Yichen Wu, Hong Wang, Peilin Zhao, Yefeng Zheng, Ying Wei, Long-Kai Huang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=olbTrkWo1D"
tags: ["query:continual"]
score: 9.0
evidence: 使用Pareto优化捕获任务间关联以防止遗忘
tldr: 针对在线持续学习中基于回放的方法忽视先前任务间相互依赖的问题，该研究将回放方法统一为层次梯度聚合框架，并引入Pareto优化捕获任务间关系。方法能够封装先前任务的最优集成知识，实验证明有效提升了旧任务性能并缓解了灾难性遗忘，为持续学习提供了新的优化视角。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1643, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1654, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1614, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1360, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1624, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1077, \"height\": 489, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1677, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1720, \"height\": 618, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1687, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1688, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 804, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1603, \"height\": 600, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1603, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1603, \"height\": 569, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1138, \"height\": 177, \"label\": \"Table\"}]"
motivation: 现有基于回放的持续学习方法忽略先前任务间的相互依赖关系。
method: 将回放方法统一为层次梯度聚合框架，并引入Pareto优化捕获任务相互关系。
result: 优化了先前任务的集成知识，提升整体性能。
conclusion: 通过考虑任务间关系，有效缓解灾难性遗忘，改进了在线持续学习。
---

## Abstract
Catastrophic forgetting remains a core challenge in continual learning (CL), where the models struggle to retain previous knowledge when learning new tasks. While existing replay-based CL methods have been proposed to tackle this challenge by utilizing a memory buffer to store data from previous tasks, they generally overlook the interdependence between previously learned tasks and fail to encapsulate the optimally integrated knowledge in previous tasks, leading to sub-optimal performance of the previous tasks. Against this issue, we first reformulate replay-based CL methods as a unified hierarchical gradient aggregation framework. We then incorporate the Pareto optimization to capture the interrelationship among previously learned tasks and design a Pareto-Optimized CL algorithm (POCL), which effectively enhances the overall performance of past tasks while ensuring the performance of the current task. Comprehensive empirical results demonstrate that the proposed POCL outperforms current state-of-the-art CL methods across multiple datasets and different settings.

---

## 论文详细总结（自动生成）

# 论文总结：通过 Pareto 优化建模先前任务关联以缓解在线持续学习中的灾难性遗忘

## 1. 研究动机与核心问题
- **灾难性遗忘**是持续学习的核心挑战：模型在学习新任务时性能会在旧任务上急剧下降。
- 当前基于**经验回放**的方法虽利用内存缓冲区存储旧任务数据来近似梯度，但普遍**忽略了先前任务之间的相互依赖关系**，仅对任务梯度做简单加权（均匀加权或冲突对齐），无法捕获旧任务的最优集成知识，导致旧任务整体性能欠佳。
- 本文旨在显式建模先前任务之间的关系，以更灵活地聚合旧任务梯度，从而更好地封装旧任务知识、缓解遗忘。

## 2. 方法论：Pareto 优化持续学习（POCL）
### 2.1 统一层次梯度聚合框架
- 将回放类方法统一为梯度加权形式：更新方向 \( u = g_n + \sum_{i=1}^{n-1} \lambda_i g_i^m \)，其中 \( g_n \) 为当前任务梯度，\( g_i^m \) 为缓冲区计算出的旧任务梯度，权重 \( \lambda_i \) 决定各旧任务的贡献。
- 经验回放使用均等权重；梯度对齐方法根据与当前任务梯度冲突程度赋权，但灵活性不足。

### 2.2 Pareto 优化：建模任务间关系
- 引入 Pareto 最优性概念，寻找一个聚合梯度方向 \( v \)，使其对所有旧任务均有益，即最大化与各旧任务梯度的最小内积：
  \[
  \max_v \min_{1\le i \le n-1} \langle g_i^m, v \rangle - \frac{1}{2}\|v\|^2
  \]
- 通过 Minimax 定理与对偶转换，问题最终转化为在概率单纯形上最小化加权梯度的范数：
  \[
  \min_{\lambda \in \mathcal{P}_{n-1}} \frac{1}{2} \left\| \sum_{i=1}^{n-1} \lambda_i g_i^m \right\|^2
  \]
- 采用 Frank-Wolfe 算法高效求解最优权重 \( \lambda^* \)，得到聚合旧任务梯度 \( g(\lambda^*) \)。

### 2.3 超梯度实现与整体更新
- 为稳定梯度并减少当前任务与聚合旧任务梯度间的冲突，使用**超梯度** \( g_j^{HD} \) 替代原始梯度 \( g_i^m \) 和 \( g_n \)。
- 超梯度通过双层迭代形式计算：以所有可见任务为外目标，特定任务为内目标，隐式对齐各任务梯度方向，降低互相抵消的风险。
- 最终更新方向为：\( u^* = g_n^{HD} + \sum_{i=1}^{n-1} \lambda_i^* g_i^{HD} \)，即 POCL 算法的核心。

## 3. 实验设计与评估
### 3.1 数据集与设置
- **数据集**：Split CIFAR-10（5 任务）、Split CIFAR-100（20 任务）、Split TinyImageNet（20 任务）。
- **设置**：在线类别增量学习，每个任务仅训练 1 epoch，推理时不提供任务 ID；内存缓冲区大小分别设为 0.6k、1k、2k、5k 等不同规模；另包含类别数量递减/递增的不平衡场景。

### 3.2 基线方法
- 正则化：EWC
- 梯度对齐：GEM、AGEM、MER、La-MAML
- 经验回放：ER、DER、DER++、CLSER、ER-ACE、CBA

### 3.3 评价指标
- **平均准确率（Acc）**：最终各任务准确率的均值。
- **遗忘度量（FM）**：从最高准确率到最终准确率的平均下降。
- **任意时间平均准确率（AAA）**：整个学习过程中所有时刻平均准确率的均值。

## 4. 资源与算力
- 论文未明确提及 GPU 型号、数量及具体训练时长。仅在时间效率分析中给出相对训练时间比较（POCL 显著快于 MER，与 La-MAML 相当），但无硬件配置说明。

## 5. 实验数量与充分性
- 实验覆盖 **3 个标准数据集、多种内存大小、多项评价指标**，且包含类别不平衡等更实际场景。
- 提供了丰富的**消融实验**：分别验证超梯度与 Pareto 优化的贡献；使用不同网络架构（ResNet-18 和 3 层 CNN）验证方法通用性。
- 对比方法涵盖多种主流 CL 类别，实验设置清晰，结果包含置信区间，整体**较为充分、客观且公平**。

## 6. 主要结论与发现
- POCL 在所有数据集、内存大小和评价指标上几乎一致优于现有 SOTA，能有效提升旧任务整体准确率，降低遗忘。
- Pareto 优化使聚合梯度能平衡各旧任务关系，超梯度实现进一步稳定了新旧任务梯度间的冲突。
- 统一梯度聚合框架不仅解释了已有方法，也为设计更优权重策略提供了理论基础。

## 7. 方法亮点
- **新视角**：首次将多种回放方法统一为层次梯度聚合框架，便于分析与改进。
- **创新机制**：引入 Pareto 优化自动捕获任务间依赖，无需手工设计权重。
- **稳定训练**：采用超梯度计算提升不同任务梯度的一致性，减少冲突。
- **实验全面**：涵盖多数据集、多内存配置、不同骨干网络和不平衡场景，消融分析清晰。

## 8. 不足与局限
- **计算开销**：需要求解 Frank-Wolfe 子问题及计算双层超梯度，训练时间比某些方法高（虽快于 MER，但慢于 La-MAML），在大规模任务下的可扩展性有待验证。
- **任务边界依赖**：方法明确需要任务划分，尚未扩展到无任务边界的在线学习场景。
- **单一模态验证**：仅在图像分类任务上评估，缺乏在 NLP、强化学习等其他领域的验证。
- **超参数与缓冲区管理**：未深入讨论超参数（如学习率、Frank-Wolfe 步长）的敏感性，内存更新策略沿用既有方法，未作针对性优化。
- **理论分析**：主要给出了遗憾界，缺少与 Pareto 最优性在非凸神经网络下的收敛性证明，且实际问题中梯度并非完全独立同分布，理论假设存在一定局限性。

（完）
