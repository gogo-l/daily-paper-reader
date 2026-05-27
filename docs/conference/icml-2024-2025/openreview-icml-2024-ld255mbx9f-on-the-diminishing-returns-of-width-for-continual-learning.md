---
title: On the Diminishing Returns of Width for Continual Learning
title_zh: 再论宽度对持续学习收益递减
authors: "Etash Kumar Guha, Vihan Lakshman"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=Ld255Mbx9F"
tags: ["query:continual"]
score: 7.0
evidence: 理论分析网络宽度对持续学习中灾难性遗忘的影响，证明宽度增加对减少遗忘的收益递减
tldr: 本文首次构建了分析持续学习理论的框架，证明在前馈网络中宽度与遗忘直接相关，但增加宽度以减少遗忘的收益呈递减趋势，并通过大规模宽度实验验证了这一现象。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1680, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1736, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1624, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1696, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 752, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 747, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1680, \"height\": 1325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1696, \"height\": 1365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1180, \"height\": 904, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1280, \"height\": 678, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1286, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1625, \"height\": 761, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 682, \"height\": 1286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1281, \"height\": 641, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1383, \"height\": 1910, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1282, \"height\": 1933, \"label\": \"Table\"}]"
motivation: 尽管经验表明更宽的神经网络能降低灾难性遗忘，但宽度与遗忘的精确关系尚未得到理论刻画。
method: 构建了持续学习理论分析框架，严格证明前馈网络中宽度对遗忘的影响及收益递减。
result: 理论证明宽度增加减少遗忘的收益递减，实验在之前未探索的大宽度下验证了这一结论。
conclusion: 研究为理解宽度在持续学习中的作用提供了理论基础，揭示了收益递减特性。
---

## Abstract
While deep neural networks have demonstrated groundbreaking performance in various settings, these models often suffer from *catastrophic forgetting* when trained on new tasks in sequence. Several works have empirically demonstrated that increasing the width of a neural network leads to a decrease in catastrophic forgetting but have yet to characterize the exact relationship between width and continual learning. We design one of the first frameworks to analyze Continual Learning Theory and prove that width is directly related to forgetting in Feed-Forward Networks (FFN), demonstrating that the diminishing returns of increasing widths to reduce forgetting. We empirically verify our claims at widths hitherto unexplored in prior studies where the diminishing returns are clearly observed as predicted by our theory.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

深度神经网络在序列化学习多个任务时普遍存在**灾难性遗忘**（catastrophic forgetting）问题。尽管已有实证研究发现，**增加网络宽度**（hidden dimension）可以有效减轻遗忘，但其精确的理论关系尚未被揭示。本研究首次构建了用于分析持续学习（Continual Learning）理论框架，旨在严格刻画**前馈网络（FFN）宽度与持续学习误差**之间的定量关系。核心结论是：增加宽度对减少遗忘的收益呈**递减性**（diminishing returns），即宽度越大，进一步加宽带来的提升越小。

## 2. 方法论：核心思想与关键技术细节

论文的核心思路建立在**“懒性训练”**（lazy training）的观察之上：过参数化的宽网络在训练过程中，权重距离初始化更近。这一性质被用作一个显式假设（Assumption 4.3），从而在持续学习场景中自然地提供**函数空间正则化**。

- **训练设置与稀疏性**：
  - 模型为深度为 $L$、宽度为 $W$ 的 FFN，激活函数 $\phi_l$ 具有 $L_l$-Lipschitz 平滑性。
  - 每个任务以概率 $\alpha$ 随机选择网络中间层的**一组活跃行**（active rows），仅这些行参与训练和推理，其余行冻结。该机制模拟了文献中“行稀疏化”降低遗忘的策略（当 $\alpha=1$ 时即全密集训练）。

- **理论分析流程**：
  1. **共享活跃行数量**：两个连续任务在各层的活跃行交集期望为 $\alpha^2 W$（引理 4.2）。
  2. **距离初始化假设**：对于任意任务 $t$，在用梯度下降方法在数据集 $\mathcal{D}_{t+1}$ 上训练得到 $\mathcal{M}_{t+1}$ 后，有
     $$
     \frac{\|A_{t+1,\ell}[\mathcal{A}_{t+1,\ell}] - A_{t,\ell}[\mathcal{A}_{t+1,\ell}]\|_F}{\|A_{t,\ell}[\mathcal{A}_{t+1,\ell}]\|_2} \le \gamma \, |\mathcal{A}_{t+1,\ell}|^{-\beta},
     $$
     其中 $\gamma,\beta > 0$ 为数据依赖常数。这刻画了宽网络权重更新幅度的下降。
  3. **权重扰动界**：结合共享行数量，在期望意义下可导出单层权重的相对变化上界为 $\bar{\lambda}\, \gamma W^{-\beta} \alpha^{(1-2\beta)/2}$（引理 4.4）。
  4. **输出误差累积**：利用逐层扰动分析（基于 Lipschitz 性质），可得到模型在旧任务输入上的输出差异期望上界（定理 4.1）：
     $$
     \mathbb{E}\big[\|\mathcal{M}_t(x) - \mathcal{M}_{t'}(x)\|_2\big] = \mathcal{O}\!\left( (t'-t)\, L^{2L}\,\bar{\lambda}\,\chi \Big(\prod_{\ell=1}^L L_\ell\|A_{t,\ell}\|_2\Big)\, \gamma W^{-\beta} \alpha^{\frac{1-2\beta}{2}} \right).
     $$
  - 该上界明确表明，持续学习误差随**宽度 $W$ 以幂律 $W^{-\beta}$ 衰减**，且随任务间隔 $t'-t$ 线性增长，随深度 $L$ 指数级恶化。
  - 进一步通过引入**层缓冲**（layer cushion）和**激活压缩**（activation contraction）等噪声稳定性概念，可以移除上界中对权重谱范数的直接依赖，得到更紧的界（定理 4.8）。

## 3. 实验设计

- **数据集与基准**：
  - 使用四个图像分类数据集：**Rotated MNIST**、**Rotated Fashion MNIST**、**Rotated SVHN** 和 **Rotated GTSRB**。
  - 每个数据集构造 5 个连续任务，对应原图旋转 $0^\circ, 22.5^\circ, 45^\circ, 67.5^\circ, 90^\circ$。

- **评价指标**：
  - **平均准确率（AA）**、**平均遗忘（AF）**、**学习准确率（LA）** 和 **联合准确率（JA）**。

- **模型与对比**：
  - 主体实验使用不同宽度的 **Feed-Forward Network**（1‑3 层隐藏层），隐藏层宽度从 32 指数级增加到 $2^{16}$（65536）。
  - 优化器：**SGD** 和 **Adam**。
  - 为进一步验证架构影响，还使用 **Wide ResNet** 进行扩展实验。
  - 消融实验涉及：不同深度（最高 6 层）、行稀疏度（$\alpha = 0.1$）、Dropout 概率、任务数量对遗忘的影响。

## 4. 资源与算力

所有实验均在单块 **NVIDIA A10 GPU**（AWS g5g.8xlarge 实例）上完成。论文未明确提及具体训练时长或总 GPU 小时数。

## 5. 实验数量与充分性

- 实验覆盖 **4 个标准数据集**，针对 **数十种宽度**（从 32 至 65536）、**多种深度**（1～6 层）、**两种主流优化器**（SGD 和 Adam）、**稀疏化设置**以及 **Wide ResNet** 进行了系统测试。
- 额外开展了 **距离初始化测量**、**遗忘随任务数变化的分析**、**Dropout 影响** 等补充实验。
- 总体实验量较大，能够在不同条件下验证理论预测的 **收益递减**、**深度正向关联遗忘**、**稀疏性降低遗忘** 等主要关系。
- 实验设计合理，对比公平（相同训练流程、仅改变目标变量），具有一定的客观性和可复现性。

## 6. 主要结论与发现

1. **宽度收益递减**：在一定范围内，增加宽度能减少遗忘，但当宽度增长到一定程度（如 $2^{11}$ 后），**遗忘值下降趋缓甚至饱和**，理论上表现为 $W^{-\beta}$ 的衰减速率。
2. **深度的影响**：增加网络深度会**显著增加遗忘**，与理论中指数级深度依赖相一致；但深度过大时，由于梯度消失导致整体精度下降，遗忘可能假性降低。
3. **稀疏性的作用**：通过行稀疏（如 $\alpha=0.1$）可以大幅降低遗忘，同时几乎不损失单任务学习精度，验证了理论中 $\alpha^{(1-2\beta)/2}$ 的积极作用。
4. **任务数与遗忘的线性关系**：最终模型对越旧的任务遗忘越严重，且遗忘量大致随任务索引呈**线性增加**，与理论中 $(t'-t)$ 的因子吻合。
5. 这些规律在 **MLP** 和 **Wide ResNet** 上一致，表明结论具有一定的架构普适性。

## 7. 优点

- **理论奠基**：率先为有限宽度非线性前馈网络建立了严格的持续学习误差界，将宽度、深度、任务数、稀疏度等核心因素统一在同一个框架下。
- **实证充分**：在远超以往研究的宽度范围内（至 65536）验证了收益递减，并定性验证了多个理论推论。
- **现象解释**：从“懒性训练”和“功能正则化”的视角，为宽网络缓解遗忘提供了清晰机制解释，并将行稀疏性与遗忘改善关联起来。
- **方法通用性**：理论分析与实际实验中同时考虑并验证了行稀疏、噪声稳定性等技巧，拓展了结论的适用范围。

## 8. 不足与局限

- **关键假设待证明**：理论核心建筑在“距离初始化随宽度递减”的经验观察上，但该假设本身未被严格证明，可能限制上界的严谨性。
- **架构局限性**：理论部分仅针对**前馈网络**展开，分析尚未扩展至现代架构（如 CNN、Transformer、残差网络），尽管实验部分用 Wide ResNet 做了初步探索。
- **数据集相对简单**：仅使用了旋转图像构造的类增量式任务，任务间差异模式单一，尚未在更复杂、更实际的持续学习基准（如分割的 Permuted MNIST、Split CIFAR-100、CORe50 等）上验证。
- **误差界并非精确预测**：理论界中存在大量依赖常数的量（如 $\bar{\lambda}$、$\gamma$、$\beta$），无法直接给出精确的遗忘数值，且常数与数据、初始化强相关。
- **方法较为基础**：实验采用最朴素的“依次微调”策略，未与记忆重放、参数正则化、动态架构等主流持续学习方法做横向对比，其结论在结合这些技术时是否成立尚不明确。

（完）
