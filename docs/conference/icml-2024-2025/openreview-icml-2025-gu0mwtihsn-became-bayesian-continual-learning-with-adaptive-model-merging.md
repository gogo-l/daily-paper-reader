---
title: "BECAME: Bayesian Continual Learning with Adaptive Model Merging"
title_zh: "BECAME: 贝叶斯持续学习与自适应模型合并"
authors: "Mei Li, Yuxiang Lu, Qinyan Dai, Suizhi Huang, Yue Ding, Hongtao Lu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=gU0MwTihsn"
tags: ["query:continual"]
score: 9.0
evidence: 贝叶斯持续学习与模型合并，平衡稳定性与可塑性
tldr: 本文从贝叶斯持续学习原则出发，探索模型合并在持续学习中的应用。将合并机制重新表述为贝叶斯持续学习，并推导出闭式解，从而无需人工选择超参数即可平衡稳定性和可塑性。在多个标准基准上的实验表明，该方法优于现有的梯度投影和模型合并方法。该工作为持续学习中的稳定性-可塑性权衡提供了理论和实践上的双重新视角。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1365, \"height\": 823, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1752, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1752, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1769, \"height\": 1692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1760, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1765, \"height\": 1682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1760, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1768, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1766, \"height\": 368, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1777, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 867, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1568, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1566, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1765, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1674, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1300, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1728, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1470, \"height\": 213, \"label\": \"Table\"}]"
motivation: 持续学习需要在保留旧知识和学习新任务之间取得平衡。
method: 提出BECAME，利用贝叶斯持续学习原理推导模型合并的闭式解。
result: 在标准持续学习基准上超越现有方法，无需人工调参。
conclusion: 为持续学习的稳定性-可塑性权衡提供了理论基础和有效算法。
---

## Abstract
Continual Learning (CL) strives to learn incrementally across tasks while mitigating catastrophic forgetting. A key challenge in CL is balancing stability (retaining prior knowledge) and plasticity (learning new tasks). While representative gradient projection methods ensure stability, they often limit plasticity. Model merging techniques offer promising solutions, but prior methods typically rely on empirical assumptions and carefully selected hyperparameters. In this paper, we explore the potential of model merging to enhance the stability-plasticity trade-off, providing theoretical insights that underscore its benefits. Specifically, we reformulate the merging mechanism using Bayesian continual learning principles and derive a closed-form solution for the optimal merging coefficient that adapts to the diverse characteristics of tasks. To validate our approach, we introduce a two-stage framework named BECAME, which synergizes the expertise of gradient projection and adaptive merging. Extensive experiments show that our approach outperforms state-of-the-art CL methods and existing merging strategies https://github.com/limei0818/BECAME.

---

## 论文详细总结（自动生成）

好的，我将根据论文内容，生成一份结构化的中文总结。

### 1. 论文的核心问题与整体含义

- **核心问题**：持续学习面临的核心挑战是 **稳定性（保留旧知识）与可塑性（学习新任务）的权衡**。现有的梯度投影方法虽能保证稳定性，但往往会限制模型学习新任务的可塑性。模型合并技术是解决此权衡的潜力方案，但**如何从理论上证明模型合并的有效性，以及如何在不同任务特性下自适应地确定最优合并系数**，仍是未解决的关键问题。
- **整体含义**：本文旨在从理论上证明模型合并能找到一个优于单独新旧模型的“最优点”，并将合并过程纳入贝叶斯持续学习框架，推导出**无需手动调节、能自适应计算的最优合并系数闭式解**，从而在实践上提出一个**简单、通用且能显著提升多种梯度投影方法性能**的两阶段框架 BECAME。

### 2. 论文提出的方法论

- **核心思想**：将模型合并与梯度投影的优势相结合。首先通过梯度投影保证稳定性，再以此为基础进行无约束训练增强可塑性，最后通过**贝叶斯推断和拉普拉斯近似**，在这两个模型之间找到一个自适应平衡点进行参数合并。
- **关键技术细节与公式**：
  - **理论证明（引理 3.1）**：论文证明了在从旧任务最优参数 $\theta^*_{t-1}$ 到新任务最优参数 $\hat{\theta}_t$ 的线性路径上，总是**存在一个合并点**，其累积损失低于路径两端点的损失，即 $L_{1:t}((1-\lambda)\theta^*_{t-1} + \lambda\hat{\theta}_t) \le \min\{L_{1:t}(\theta^*_{t-1}), L_{1:t}(\hat{\theta}_t)\}$。
  - **贝叶斯重述与自适应合并系数（3.3节）**：将 MAP 估计下的持续学习目标函数进行拉普拉斯近似，并证明沿合并路径的优化目标是**凸函数**。通过令导数为零，推导出**最优合并系数 $\lambda^*_t$ 的闭式解**，其值由新旧参数差 $\Delta\theta$、新任务的**费舍尔信息矩阵（FIM）** $F_t(\hat{\theta}_t)$ 和历史任务的**累积精度矩阵** $\sum_{i=1}^{t-1} F_i(\theta^*_i)$ 共同决定：
    $$\lambda^*_t = \frac{\Delta\theta^\top F_t(\hat{\theta}_t) \Delta\theta}{\Delta\theta^\top (F_t(\hat{\theta}_t) + \sum_{i=1}^{t-1} F_i(\theta^*_i)) \Delta\theta}$$
- **算法流程（BECAME）**：
  1.  **第一阶段（保证稳定性）**：使用梯度投影方法在旧模型 $\theta^*_{t-1}$ 的基础上学习任务 $t$，得到模型 $\theta^{GP}_t$。
  2.  **第二阶段（增强可塑性）**：从 $\theta^{GP}_t$ 出发，不施加约束地继续训练，得到模型 $\hat{\theta}_t$。
  3.  **自适应合并**：利用上述公式计算最优系数 $\lambda^*_t$，并合并模型 $\theta^*_t = (1-\lambda^*_t)\theta^{GP}_t + \lambda^*_t\hat{\theta}_t$。
  4.  **更新精度矩阵**：计算 $\theta^*_t$ 的 FIM，并累加到先前任务的累计精度矩阵上，为后续任务做准备。

### 3. 实验设计

- **数据集/场景**：在四种广泛使用的持续学习基准上进行任务增量学习评估。
  - **20-Split CIFAR-100** 和 **10-Split CIFAR-100**。
  - **25-Split TinyImageNet**。
  - **20-Split MiniImageNet**。
- **对比方法**：
  - **基础梯度投影方法**：GPM、Adam-NSCL。
  - **梯度投影改进方法**：TRGP、SGP、GPCNS、Connector。
  - **其他代表方法**：EWC（正则化）、A-GEM、ER-Res（回放）、OWM（梯度投影）等。
  - **不同合并策略**：固定系数合并 (1/t)、CoMA、CoFiMA。
- **评估指标**：
  - **平均准确率 (ACC)**：衡量整体性能。
  - **后向迁移 (BWT)**：衡量稳定性。
  - **非适应性度量 (IM)**：衡量可塑性。
  - 新增了 **单轮次后准确率 (AOA)** 指标来评估泛化能力和前向迁移。

### 4. 资源与算力

- 论文提到，所有实验均在**单块 NVIDIA GeForce RTX 4080 GPU** 上运行。
- 在效率分析中对比了训练时间和GPU内存占用，例如在 MiniImageNet 数据集上，GPM + Ours 的训练时间为 584.14 秒，GPU 内存占用为 375.72 MB，展示了其相对于其他改进方法（如TRGP）的效率和性能优势。

### 5. 实验数量与充分性

- **实验数量充足**：
  - 在 **4个不同规模的基准数据集**上进行了测试。
  - 以 **4种梯度投影方法（GPM, TRGP, SGP, GPCNS）和1种方法（NSCL）** 为基线，分别应用BECAME并对比，合计超过10组主实验。
  - 进行了**多种合并策略（5种）的消融/对比实验**。
  - 深入分析了**稳定性-可塑性权衡、任务间平衡性、泛化能力和效率**。
- **公平性与客观性**：
  - 所有实验均使用与基线方法相同的网络架构、数据划分和超参数设置。
  - 严格复现了基线方法，并采用**5个随机种子**报告均值和标准差，确保了结果的可信度。

### 6. 论文的主要结论与发现

- **理论发现**：从理论上证明，在保持稳定性和增强可塑性的两个模型参数的连线上，总存在一个累积损失更低的**最优合并点**。
- **方法有效性**：所提出的 BECAME 框架能**一致且显著地提升多种梯度投影方法的性能**（例如在10-Split CIFAR-100上将GPM的ACC从71.81%提升至75.05%，Adam-NSCL的ACC从72.91%提升至81.66%），尤其在**可塑性指标（IM）**上有巨大改善，同时保持了良好的稳定性（BWT）。
- **自适应合并优势**：推导出的**闭式解合并系数**能够根据任务特性自适应调整，在提升整体性能的同时，实现了更好的任务间平衡，并展现出比固定系数或人工调参更强的泛化能力和前向迁移能力。

### 7. 优点

- **坚实的理论基础**：基于贝叶斯持续学习原则，为模型合并提供了理论支撑和闭式解法，而非依赖经验技巧。
- **方法简单且通用**：作为一个即插即用的框架，BECAME能与多种现有的梯度投影方法结合，无需复杂的超参数调节即可稳定提升性能。
- **性能提升显著**：在多个基准上超越了当前最优方法，尤其在改善模型可塑性方面效果突出，很好地解决了梯度投影方法的核心痛点。
- **分析全面深入**：不仅关注最终性能，还对稳定性-可塑性权衡、任务平衡性、泛化能力、效率等多个维度进行了细致的剖析。

### 8. 不足与局限

- **计算开销**：虽然优于部分基线，但BECAME需要额外一个无约束训练阶段，总计两个训练阶段，相比单阶段方法会增加训练时间。
- **依赖梯度投影**：框架当前建立在梯度投影方法之上，其有效性依赖于第一阶段梯度投影对旧知识的良好保持（即假设公式21成立），该方法对于非梯度投影类方法的泛化性未在文中探讨。
- **费舍尔信息矩阵近似**：对FIM采用对角近似以降低计算负担，这虽然是常规做法，但可能带来精度损失，其影响未被深入分析。
- **应用场景限制**：所有实验均在任务增量学习的视觉分类基准上进行，其在领域增量学习或更复杂场景（如强化学习、自然语言处理）中的表现有待验证。

（完）
