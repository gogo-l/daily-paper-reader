---
title: Optimal Task Order for Continual Learning of Multiple Tasks
title_zh: 持续学习多任务的最优任务顺序研究
authors: "Ziyan Li, Naoki Hiratani"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=145So0OrGC"
tags: ["query:continual"]
score: 9.0
evidence: 优化任务顺序以提升持续学习性能
tldr: 针对持续学习中多任务顺序对学习性能的影响，利用线性师生模型推导出任务相似性和顺序与性能的解析关系，提出了两条任务排序原则：从最不典型到最典型，以及相邻任务应不相似。在人工数据和真实图像数据集上验证了这些原则的有效性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1330, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1386, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1758, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1589, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1762, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1745, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 881, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1754, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1765, \"height\": 728, \"label\": \"Figure\"}]"
motivation: 任务顺序对持续学习性能影响显著，但缺乏系统的理论和优化策略。
method: 基于线性师生模型推导任务相似性和顺序对学习性能的解析关系，提出最优排序原则。
result: 在合成和真实数据上，按照提出原则排序的任务提高了MLP和卷积网络的持续学习性能。
conclusion: 该研究揭示了任务顺序的关键作用，并提供了可操作的排序策略，可普遍应用于各类持续学习场景。
---

## Abstract
Continual learning of multiple tasks remains a major challenge for neural networks. Here, we investigate how task order influences continual learning and propose a strategy for optimizing it. Leveraging a linear teacher-student model with latent factors, we derive an analytical expression relating task similarity and ordering to learning performance. Our analysis reveals two principles that hold under a wide parameter range: (1) tasks should be arranged from the least representative to the most typical, and (2) adjacent tasks should be dissimilar. We validate these rules on both synthetic data and real-world image classification datasets (Fashion-MNIST, CIFAR-10, CIFAR-100), demonstrating consistent performance improvements in both multilayer perceptrons and convolutional neural networks. Our work thus presents a generalizable framework for task-order optimization in task-incremental continual learning.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景**：深度神经网络在多任务持续学习中普遍遭受灾难性遗忘，而任务的训练顺序对最终性能有显著影响，但缺乏清晰的理论指导和通用的优化策略。
- **核心问题**：探索任务顺序如何影响持续学习性能，并建立一套可解释、可推广的任务顺序优化原则。
- **整体含义**：该研究不仅在理论上揭示任务相似性与排序之间的解析关系，还为实际应用（如自动驾驶、医学影像、课程设计等）提供了简单有效的任务排序准则，以最大化知识迁移、最小化遗忘。

### 2. 论文提出的方法论

- **核心思想**：利用带有隐变量（latent factors）的线性师生模型，推导出持续学习最终平均误差的解析表达式，从而分析任务顺序对性能的影响，并提出最优排序策略。
- **关键技术细节**：
  - **模型设定**：输入 `x = Aμ s`，目标输出 `y* = Bμ s`，其中 `s~N(0,I)` 为隐变量。输入生成矩阵 `Aμ` 和输出生成矩阵 `Bμ` 的元素服从跨任务相关的高斯分布，协方差分别由 `Cin` 和 `Cout` 刻画。
  - **线性网络与学习**：学生网络为 `y = Wx`，采用梯度下降逐个任务训练。在 `Nx >> Ns` 的极限下，利用伪逆近似和迭代展开，得到训练完所有任务后的权重 `W_P` 的闭合形式。
  - **最终误差解析式（定理3.1）**：`¯ϵf = || (Cout)^{1/2} (I - (I + Cin,U)^{-1} Cin) ||_F^2`，其中 `Cin,U` 是 `Cin` 的严格上三角矩阵，表明误差仅依赖于任务相似矩阵的上三角部分，故非置换不变，即依赖于任务顺序。
  - **线性扰动分析与排序规则（定理4.1）**：对 `Cin` 添加小扰动，将误差分解为绝对顺序依赖（`G+` 项）和相对顺序依赖（`G-` 项）：
    - **外围到核心规则（periphery-to-core rule）**：由 `G+` 导出的原则，要求最早的任务应是最不典型的（与其它任务平均相似度低），而最典型的任务放在最后学习。
    - **最大路径规则（max-path rule）**：由 `G-` 导出的原则，要求在任务不相似图上形成的哈密顿路径长度最大化，即相邻任务应尽可能不相似，远的任务反而可以更相似。
  - **简单图结构的应用**：在链、环、树、树叶等简单相似结构上验证了上述规则，最优顺序往往呈现出从外围节点开始、跳跃式遍历的模式。

### 3. 实验设计

- **数据集/场景**：
  - **合成数据**：根据自定义的 `Cin` 和 `Cout` 生成任务，用于验证解析公式和排序规则。
  - **真实图像分类**：
    - Fashion-MNIST（MLP，两层隐藏层）。
    - CIFAR-10、CIFAR-100（CNN，两层卷积+一层全连接）。
    - 任务构造：二分类（或五分类）任务，从数据集中随机划分10个类别（或CIFAR-100中选10类）生成5个任务，任务间无类别重叠。
  - 任务相似度估计：通过零样本迁移性能（zero-shot transfer）定义相似度 `ρ_AB = 1 - 0.5 * (√(ϵ_B[WA]/ϵ_B,sf) + √(ϵ_A[WB]/ϵ_A,sf))`。
- **对比方法**：
  - 外围到核心 vs. 核心到外围。
  - 最大路径 vs. 最小路径。
  - 随机任务顺序（30种随机排列的平均）。
  - 基于少量数据（1%～0.1%训练样本）估计相似度后的排序 vs. 随机顺序。

### 4. 资源与算力

- **硬件**：NVIDIA Tesla V100 GPU。
- **框架**：基于 JAX 的 Flax 库。
- **训练配置**：Adam 优化器，学习率 `10^{-3}`，每个任务训练 5 个 epoch，batch size 4。相似度估计时同样训练5个epoch。
- **算力消耗**：论文未明确报告总训练时长或 GPU 小时数，但模型规模较小，任务数量有限，综合算力需求低。

### 5. 实验数量与充分性

- **合成实验**：
  - 对比解析解与数值模拟的误差（图 2b），涵盖多种随机 `Cin`, `Cout` 和不同任务数（P）。
  - 对三任务情形绘制最优顺序相图（图 2c）。
  - 线性扰动分析在不同参数 `m`, `P` 下展示 `G+`、`G-` 和排序规则的优势（图 3、图 6）。
  - 对链、环、树等图结构，对比了所有可能顺序（P=5 共120种）下的误差（图 4）。
- **真实图像分类**：
  - 在三个数据集上分别对比不同排序规则的性能（图 5、图 7），共约 3×100 个任务集合，每个集合生成5个任务。
  - 使用不同比例的训练数据（100% vs. 1% vs. 0.1%）进行相似度估计和排序（图 9、图 10），展示鲁棒性。
- **充分性与公平性**：实验覆盖合成、经典视觉数据集、两种网络架构，对比了理论提出的顺序、相反的顺序和随机基线，且通过大量随机种子和任务集平均，保证了统计稳定性和比较的公平性。

### 6. 论文的主要结论与发现

- 线性师生模型可以精确刻画持续学习中任务相似性和顺序对最终泛化误差的影响，误差仅依赖相似矩阵的上三角部分。
- 通过线性扰动分析，解耦出两个独立影响因素，分别导出了两条优化原则：
  1. **外围到核心规则**：最不具代表性的任务先学，最典型任务后学。
  2. **最大路径规则**：相邻任务应尽量不相似，即在不相似图上构造最长哈密顿路径。
- 这两条规则在合成数据和真实图像分类任务上均稳健地提升了平均性能，即使在仅使用 1% 训练数据估计相似度时仍有效。
- 当任务间平均正相关较强时，外围到核心规则的优势更明显；最大路径规则在多种条件下均优于最短路径和随机顺序。

### 7. 优点

- **理论深度**：从简单的线性师生模型推导出清晰的解析表达式，并借助扰动分析将任务顺序效应分解为可解释的分量，为后续研究提供了理论基础。
- **原则简洁实用**：给出的排序规则概念直观，无需复杂的优化过程，仅需利用少量样本估计任务相似度即可实施。
- **实验全面**：同时在合成数据和多个真实数据集上进行验证，涵盖不同网络架构（MLP/CNN），还包括少量数据的鲁棒性测试，增强了结论的可信度。
- **与先前实证发现一致**：最大路径规则印证了 Bell & Lawrence (2022) 的实证观察，并首次从理论上进行了解释。

### 8. 不足与局限

- **模型假设限制**：
  - 理论推导基于线性网络和随机任务生成假设，虽然实验证明在非线性网络上有效，但可能不适用于更复杂的动态或任务类型。
  - 模型设定中每个任务只学习一次并训练至收敛，实际中可能存在多轮重放或未能完全收敛的情况，排序效果可能变化。
- **相似度估计依赖**：排序的质量依赖于对任务相似度的准确估计，零样本迁移方法在任务差异极大或负相关较大时可能不准确，极端情况下可能导致原则失效。
- **实验范围局限**：
  - 仅在较小规模的图像分类任务上验证，未在更大规模数据集、自然语言处理或强化学习等场景中测试。
  - 神经网络架构相对简单，未探索更深或更现代的架构（如ResNet、Transformer）对排序规则的敏感性。
- **计算开销**：虽然比全排列搜索高效，但仍需为每个任务训练一个模型估计相似度，任务数量极大时可能不可行。
- **缺乏与已有补救方法的结合**：未讨论任务排序与重放、正则化等其他持续学习方法的联合效应。

（完）
