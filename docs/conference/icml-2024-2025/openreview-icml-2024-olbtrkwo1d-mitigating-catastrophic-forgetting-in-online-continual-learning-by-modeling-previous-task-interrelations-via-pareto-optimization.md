---
title: Mitigating Catastrophic Forgetting in Online Continual Learning by Modeling Previous Task Interrelations via Pareto Optimization
title_zh: 通过帕累托优化建模先前任务间关系以缓解在线持续学习中的灾难性遗忘
authors: "Yichen Wu, Hong Wang, Peilin Zhao, Yefeng Zheng, Ying Wei, Long-Kai Huang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=olbTrkWo1D"
tags: ["query:continual"]
score: 10.0
evidence: 提出帕累托优化建模任务间关系以缓解在线持续学习中的灾难性遗忘
tldr: 现有在线持续学习的回放方法忽略已学任务间的相互依赖，导致旧任务性能次优。本文将其重构为分层梯度聚合框架，并引入帕累托优化捕捉任务间关系，从而更有效地集成先前知识，缓解灾难性遗忘。实验表明该方法显著超越已有回放方法，为在线持续学习提供了新的优化视角。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1643, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1654, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1614, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1360, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1624, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-olbtrkwo1d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1077, \"height\": 489, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1677, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1720, \"height\": 618, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1687, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1688, \"height\": 323, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 233, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 804, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1603, \"height\": 600, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1603, \"height\": 570, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1603, \"height\": 569, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-olbtrkwo1d/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1138, \"height\": 177, \"label\": \"Table\"}]"
motivation: 现有回放方法未考虑任务间交互，导致旧任务知识整合不佳。
method: 提出分层梯度聚合与帕累托优化相结合的方法来建模任务间关系。
result: 在多个基准上验证，该方法比已有回放方法显著减少遗忘。
conclusion: 帕累托优化有效捕捉任务间依赖，提升在线持续学习性能。
---

## Abstract
Catastrophic forgetting remains a core challenge in continual learning (CL), where the models struggle to retain previous knowledge when learning new tasks. While existing replay-based CL methods have been proposed to tackle this challenge by utilizing a memory buffer to store data from previous tasks, they generally overlook the interdependence between previously learned tasks and fail to encapsulate the optimally integrated knowledge in previous tasks, leading to sub-optimal performance of the previous tasks. Against this issue, we first reformulate replay-based CL methods as a unified hierarchical gradient aggregation framework. We then incorporate the Pareto optimization to capture the interrelationship among previously learned tasks and design a Pareto-Optimized CL algorithm (POCL), which effectively enhances the overall performance of past tasks while ensuring the performance of the current task. Comprehensive empirical results demonstrate that the proposed POCL outperforms current state-of-the-art CL methods across multiple datasets and different settings.

---

## 论文详细总结（自动生成）

好的，这是对给定论文的结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **核心挑战**：持续学习（CL）中的灾难性遗忘问题。模型在学习新任务时，会迅速丧失对先前学习任务的记忆，导致旧任务性能显著下降。
*   **现有方法局限**：主流的基于回放的CL方法（Replay-based Methods），通过记忆缓冲区存储旧任务数据来近似旧任务梯度，但在处理这些旧任务梯度时存在关键缺陷。
    *   **忽略任务间关系**：现有方法（如经验回放、梯度对齐）通常简单地对旧任务梯度进行等权合并，或仅让它们不与当前任务梯度冲突。它们忽略了旧任务**彼此之间**复杂的相互依赖关系。
    *   **知识整合欠优**：若两个旧任务的梯度相互冲突，简单合并会使其相互抵消，导致无法有效封装和利用所有先前知识，最终导致旧任务性能次优。
*   **研究动机**：本文旨在解决上述缺陷，通过显式建模先前任务间的相互关系，找到一个能提升所有旧任务整体表现的梯度更新方向，从而更有效地缓解灾难性遗忘。

### 2. 论文提出的方法论

论文的核心思想是引入**帕累托优化（Pareto Optimization）**来捕捉先前任务间的内在关系，并以此为指导计算出最优的梯度聚合权重。

*   **1. 统一视角：分层梯度聚合框架**
    *   作者首先从梯度加权视角重新审视了现有的回放方法，将模型的梯度更新方向 $\mathbf{u}$ 统一形式化为：
        $\mathbf{u} = \mathbf{g}_n + \sum_{i=1}^{n-1} \lambda_i \mathbf{g}_i^m$
    *   其中 $\mathbf{g}_n$ 是当前任务的梯度，$\mathbf{g}_i^m$ 是来自记忆缓冲区的第 $i$ 个旧任务的近似梯度，$\lambda_i$ 是分配给该旧任务的权重。这表明当前任务梯度拥有固定优先级，而旧任务梯度组合则起正则化作用以防止遗忘。现有方法的差异仅在于权重 $\lambda_i$ 的分配策略（如经验回放设为1，梯度对齐方法则视冲突情况而定）。

*   **2. 核心算法：POCL**
    *   **帕累托优化建模**：为了增强所有先前任务的整体性能，POCL 的目标是寻找一个聚合向量 $\mathbf{v}$，能够最大程度地有利于所有旧任务。这被形式化为一个最大最小优化问题：最大化 $\mathbf{v}$ 与所有旧任务梯度 $\mathbf{g}_i^m$ 的最小内积。
        $\max_{\mathbf{v}} \min_{1 \le i \le n-1} \langle \mathbf{g}_i^m, \mathbf{v} \rangle - \frac{1}{2}\|\mathbf{v}\|^2$
    *   **求解权重 $\lambda_i^*$**：该问题可转化为求解一个二次规划问题：在单纯形约束下，最小化聚合梯度 $\sum \lambda_i \mathbf{g}_i^m$ 的 $L_2$ 范数。
        $\min_{\lambda \in \mathcal{P}_{n-1}} \frac{1}{2}\left\|\sum_{i=1}^{n-1} \lambda_i \mathbf{g}_i^m\right\|_2^2$
    *   **求解算法**：此问题通过**Frank-Wolfe算法**高效求解，得到帕累托最优的权重 $\lambda^*$，从而得到 $\mathbf{v}^* = \sum \lambda_i^* \mathbf{g}_i^m$。
    *   **最终更新方向**：$\mathbf{u}^* = \mathbf{g}_n + \mathbf{v}^*$。

*   **3. 关键技术：超梯度实现**
    *   **问题**：直接使用原始梯度 $\mathbf{g}_i^m$ 和 $\mathbf{g}_n$ 仍可能导致最终更新方向 $\mathbf{u}^*$ 与当前任务或旧任务冲突。
    *   **解决方案**：采用**超梯度（Hyper-Gradient）**替代公式中的普通梯度。超梯度 $\mathbf{g}_j^{\text{HD}}$ 通过一个二层优化过程计算，它衡量的是：在一个特定的临时参数更新后，模型在所有已见任务上的损失变化。这种方法使得计算出的超梯度自然倾向于与所有已见任务的整体梯度方向对齐。
    *   **效果**：使用超梯度后，不同任务的梯度本身就具有较高的一致性，因此帕累托优化聚合得到的 $\mathbf{v}^*$ 与 $\mathbf{g}_n^{\text{HD}}$ 冲突的概率大大降低，从而稳定了训练过程。

### 3. 实验设计

*   **数据集**：使用了三个标准的持续学习基准数据集。
    *   **Split CIFAR-10**：分为5个任务，每任务2类。
    *   **Split CIFAR-100**：分为20个任务，每任务5类。
    *   **Split TinyImageNet**：分为20个任务，每任务10类。
*   **实验设置**：主要在**在线类别增量学习**设定下进行，每个任务仅训练一次（epoch），且测试时不提供任务ID。实验还考虑了不同记忆缓冲区大小和类别不平衡等更具挑战性的场景。
*   **对比方法**：与多个领域内最先进的（SOTA）方法进行了全面对比，覆盖了多个类别：
    *   **正则化方法**：EWC。
    *   **梯度对齐方法**：GEM, AGEM, MER, La-MAML。
    *   **经验回放方法**：ER, DER, DER++, CLSER, ER-ACE, CBA。
*   **评估指标**：
    *   **平均准确率**：最终在所有任务上的平均测试准确率。
    *   **遗忘率**：衡量模型在训练过程中对每个任务性能下降的程度。
    *   **任意时刻平均准确率**：衡量模型在整个学习过程中的平均性能，反映了模型的持续学习能力。

### 4. 资源与算力

论文未明确提及所使用的**GPU型号、数量或具体的总训练时长**。
*   唯一相关的信息是在附录中的时间复杂性分析，它对比了POCL与同样使用超梯度的MER和La-MAML在Split CIFAR-10上的单次训练时间（以秒为单位）。结果表明，POCL的训练时间（1677.10秒）远低于MER（20697.70秒），与La-MAML（750.61秒）在同一个数量级，但论文并未给出这些时间的硬件基础。

### 5. 实验数量与充分性

实验设计**较为充分且客观**，通过多维度验证支撑了其核心观点。
*   **多数据集与多设置**：在3个不同复杂度的数据集上，使用至少2种不同的缓冲区大小进行了评估，并额外测试了类别不平衡的挑战场景。
*   **全面的对比基线**：选择了超过10种具有代表性的SOTA方法，涵盖了正则化、经验回放和梯度对齐等主流范式，覆盖全面。
*   **多维度指标评估**：使用了平均准确率、遗忘率和任意时刻平均准确率三个互补的指标，能更全面地评价模型性能。
*   **机制验证实验**：通过绘制任务准确率条形图、遗忘率图、混淆矩阵和在训练过程中记录不同阶段性能的表格，直观地解释并验证了POCL提升旧任务整体表现的工作机制。
*   **消融研究**：通过分别移除超梯度和帕累托优化组件，清晰地证明了每个组件的必要性和贡献。
*   **不同模型架构测试**：除了主干的Reduced ResNet-18，还在一个更小的三层CNN上验证了其有效性，证明了方法的泛化能力。

### 6. 论文的主要结论与发现

*   提出一个统一的分层梯度聚合框架，揭示了现有回放方法本质上是对旧任务梯度进行不同策略的加权组合。
*   在此框架下，提出的POCL算法通过帕累托优化显式地建模并利用了先前任务之间的相互关系，找到了比简单合并或冲突避免更优的梯度聚合方案。
*   超梯度的引入稳定了训练过程，有效避免了聚合后的方向与当前任务梯度冲突，是POCL成功的关键组件。
*   大量实验表明，POCL在多个基准数据集和不同设置下，在平均准确率、遗忘率和任意时刻平均准确率上，一致地优于当前SOTA方法，尤其是在提升所有旧任务的综合性能方面表现突出。

### 7. 优点

*   **视角新颖**：从梯度加权和优化的角度统一了多种回放方法，理论分析清晰（如利用Minimax定理推导）。
*   **方法创新**：将多目标优化中的帕累托最优概念巧妙应用于持续学习中的旧任务关系建模，为这一挑战提供了新的解决思路。
*   **性能优异**：实验效果显著，特别是在衡量旧任务整体保留能力的指标上优势明显，有力地支撑了其核心动机。
*   **实验扎实**：实验设计全面、对比充分，特别是通过消融实验和多种可视化（如混淆矩阵）清晰地展示了各组件的贡献和算法机理。

### 8. 不足与局限

*   **计算开销**：虽然比MER快，但POCL基于超梯度的计算和Frank-Wolfe算法求解二次规划问题，其计算成本和存储开销（需要存储辅助模型参数）依然高于ER、DER++等简单的经验回放方法。
*   **缓冲区大小限制**：作为一种回放方法，其性能依然高度依赖于记忆缓冲区的大小，在极小的缓冲区设置下，所有基于回放的方法都会受到严重影响。
*   **超参数依赖与分析缺失**：方法中包含学习率 $\alpha, \beta$ 和采样批次大小等超参数，文中虽给出了设定值，但缺少关于这些超参数敏感性的分析。
*   **记忆管理策略单一**：模型聚焦于“如何使用”缓冲区中的旧数据，但“如何选择”数据存入缓冲区（记忆管理策略）同样关键，本文沿用了固定的策略，未在此方面进行探索。

（完）
