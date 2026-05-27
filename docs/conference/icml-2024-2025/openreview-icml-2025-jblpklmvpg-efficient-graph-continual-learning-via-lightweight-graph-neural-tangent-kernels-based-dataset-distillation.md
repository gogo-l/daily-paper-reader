---
title: Efficient Graph Continual Learning via Lightweight Graph Neural Tangent Kernels-based Dataset Distillation
title_zh: 基于轻量级图神经正切核的数据蒸馏实现高效图持续学习
authors: "Rihong Qiu, Xinke Jiang, Yuchen Fang, Hongbin Lai, Hao Miao, Xu Chu, Junfeng Zhao, Yasha Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JblpkLmvPg"
tags: ["query:continual"]
score: 8.0
evidence: 提出基于轻量级GNTK的高效数据集蒸馏框架用于图持续学习。
tldr: 针对图神经网络在多个下游任务上持续学习时计算成本高的问题，该论文提出了一种基于轻量级图神经正切核（LIGHTGNTK）的高效数据集蒸馏框架。通过伯努利采样和低秩近似加速核计算，在低位宽存储的合成数据上直接适配新任务，无需繁重微调。实验表明该方法在保证性能的同时大幅降低了计算开销。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jblpklmvpg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1742, \"height\": 1100, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1774, \"height\": 830, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 611, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 619, \"height\": 347, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 697, \"height\": 1154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1183, \"height\": 634, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1004, \"height\": 277, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1597, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1768, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1637, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1535, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jblpklmvpg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1526, \"height\": 273, \"label\": \"Table\"}]"
motivation: 预训练GNN直接应用于下游任务时持续学习计算成本高，阻碍大规模图模型发展。
method: 设计轻量级GNTK并通过伯努利采样和低秩近似加速核计算，实现高效的数据集蒸馏。
result: 在多个图任务上，该方法能以极低存储和计算开销达到与全量微调相当的性能。
conclusion: 为图持续学习提供了可推广的高效解决方案，减少了部署成本。
---

## Abstract
Graph Neural Networks (GNNs) have emerged as a fundamental tool for modeling complex graph structures across diverse applications.
However, directly applying pretrained GNNs to varied downstream tasks without fine-tuning-based continual learning remains challenging, as this approach incurs high computational costs and hinders the development of Large Graph Models (LGMs).
In this paper, we investigate an efficient and generalizable dataset distillation framework for Graph Continual Learning  (GCL) across multiple downstream tasks, implemented through a novel Lightweight Graph Neural Tangent Kernel (LIGHTGNTK).
Specifically, LIGHTGNTK employs a low-rank approximation of the Laplacian matrix via Bernoulli sampling and linear association within the GNTK. This design enables efficient capture of both structural and feature relationships while supporting gradient-based dataset distillation.
Additionally, LIGHTGNTK incorporates a unified subgraph anchoring strategy, allowing it to handle graph-level, node-level, and edge-level tasks under diverse input structures.
Comprehensive experiments on several datasets show that LIGHTGNTK achieves state-of-the-art performance in GCL scenarios, promoting the development of adaptive and scalable LGMs.

---

## 论文详细总结（自动生成）

# 论文总结：Efficient Graph Continual Learning via Lightweight Graph Neural Tangent Kernels-based Dataset Distillation

## 1. 论文的核心问题与整体含义

近年来，图神经网络（GNN）在多项任务中取得显著进展，并催生了以GPT-GNN等为代表的大规模图模型（LGM）。然而，将预训练的LGM直接应用到多样化的下游任务时，面临两大核心挑战：

- **计算开销巨大**：为了适配新任务，传统的持续学习（Graph Continual Learning, GCL）需要在下游全量数据上执行昂贵的参数微调，其计算成本常常与重新训练一个LGM相当，严重阻碍了实际部署。
- **任务结构不匹配**：现有的基于数据集蒸馏的GCL方法大多局限于图级（graph-level）任务，难以泛化到节点级（node-level）和边级（edge-level）任务，因为不同级别任务的输入图结构存在显著差异。

针对上述问题，本文提出了一种**高效且可泛化的数据集蒸馏框架**，其核心含义在于：仅利用下游任务中极少量的、经过挑选的合成样本，即可对预训练LGM进行快速适配，从而大幅降低持续学习的计算负担，同时保持甚至提升模型性能。该工作为构建自适应、可扩展的大规模图模型（LGM）提供了有力支撑。

## 2. 论文提出的方法论

论文提出了 **LIGHTGNTK（Lightweight Graph Neural Tangent Kernel）** 框架，主要包括以下几个核心模块：

### 2.1 统一子图任务定义
为统一处理图级、节点级和边级任务，框架采用**子图锚定策略**：
- 对于节点或边，以目标节点（或边两端节点）为中心，提取其k跳邻居构成查询子图。
- 对于整个图，将其视为一个子图。  
通过这种方式，所有下游任务都被映射到统一的子图相似性比较框架中，利用支持集（原型子图）的logits原型进行分类或链接预测。

### 2.2 轻量级图神经正切核（LIGHTGNTK）近似
传统的图神经正切核（GNTK）计算涉及全秩拉普拉斯矩阵操作，时间复杂度为 \(O(n^2 d)\)，难以扩展到大规模图。LIGHTGNTK 采用两项关键技术进行加速：

- **低秩近似（Low-Rank Approximation）**：对图拉普拉斯矩阵 \(L = U\Lambda U^\top\) 的所有特征值进行伯努利采样（概率 \(p = r/n\)），仅保留 \(r\) 个特征值及其对应特征向量，构成低秩拉普拉斯矩阵 \(\tilde{L} = \tilde{U}\tilde{\Lambda}\tilde{U}^\top\)。随后通过分解计算 \(\tilde{L}X\)，将复杂度降至 \(O(nrd)\)（\(r\ll n\)）。
- **结构化优化**：包括（1）在子图上执行特征分解以缩小矩阵尺寸；（2）对极大规模的图级任务采用蒙特卡洛采样批加速；（3）仅利用网络最后一层的梯度计算核相似度，放弃全层梯度。

理论分析证明，该近似的梯度误差在期望上有严格上界，且近似误差随着采样概率 \(p\) 的增加而减小，保证了蒸馏质量。

### 2.3 基于GNTK的数据选择与微调
流程如下：
1. **预训练LGM**：在大规模无标签图数据上，通过掩码信号重建和链路预测的自监督任务预训练GNN骨干网络。
2. **计算GNTK相似度矩阵**：使用验证集作为测试集的代理（假设验证集与测试集同分布），利用 LIGHTGNTK 计算训练样本与验证样本之间的梯度协方差矩阵 \(K\)。
3. **样本选择**：对于每个候选训练样本，取其与所有验证样本 GNTK 相似度的最小值作为得分，选取得分最低的 \(N_{syn}\) 个样本构成合成数据集 \(D_{syn}\)。
4. **监督微调**：仅使用挑选出的极少样本对预训练LGM进行微调，分类损失采用交叉熵加L2正则化。

### 2.4 关键公式举例
- **GNTK 定义**：\(\Theta_\theta(G_1,G_2) = [\nabla_\theta f_\theta(L_1,X_1)] [\nabla_\theta f_\theta(L_2,X_2)]^\top\)
- **LIGHTGNTK 近似**：\(\Theta(G_i,G_j) = [\nabla_\theta f_\theta(\tilde{U}_i\tilde{\Lambda}_i\tilde{U}_i^\top X_i)]\cdot [\nabla_\theta f_\theta(\tilde{U}_j\tilde{\Lambda}_j\tilde{U}_j^\top X_j)]^\top\)
- **样本选择得分**：\(I(G_c) = \min_{G_v \in D_{val}} \Theta(G_c,G_v)\)

## 3. 实验设计

### 3.1 数据集与任务场景
在 **13个基准数据集** 上进行了全面评估，覆盖三类图学习任务：
- **图分类 (7个)**：NCI1, NCI109, PROTEINS, DD (TUDataset)；ogbg-molhiv, ogbg-molbbbp, ogbg-molbace (Open Graph Benchmark)
- **节点分类 (4个)**：Cora, CiteSeer, PubMed (Planetoid)；ogbn-arxiv (OGB)
- **链接预测 (2个)**：ogbl-collab, ogbl-ddi (OGB)

### 3.2 对比方法（Benchmark）
与三类基线方法比较：
- **核心集选择方法**：Random Sampling, Herding, K-Center Greedy Selection
- **基于学习的图蒸馏**：DosCond（梯度匹配）
- **核近似方法**：KIDD（基于GNTK的岭回归蒸馏，仅适用图级任务）
- **全量数据训练**（Whole Dataset）作为性能上界参考
- **GNTK（未优化版）** 作为消融对照

实验设定：每类分别蒸馏出1、10、50个样本，验证极限数据量下的性能。每组实验重复5次，报告均值和标准差。

## 4. 资源与算力

实验实现采用 **PyTorch 2.5.1** 和 **Python 3.12**。硬件平台为 **NVIDIA GeForce RTX 3090 GPU**（论文未明确说明使用的GPU数量）。训练细节方面：
- 使用Adam优化器，L2正则化。
- 预训练任务为二分类边预测。
- 微调时采用早停法（耐心值50 epoch）。
**未明确提供单次实验总训练时长**，但在效率分析中报告了蒸馏阶段的核计算时间（秒），例如NCI1上GNTK耗时196秒，LIGHTGNTK耗时144秒，其他数据集也均有提速。

## 5. 实验数量与充分性

论文进行了大量实验，充分验证了方法的有效性和泛化能力，具体包括：
- **主实验**：在3种任务类型、13个数据集、每个类1/10/50样本的设置下，对比了7种方法（含全量数据），累计 **超过200组独立实验**。
- **消融实验**：
  - 不同低秩策略对比（top-r、bottom-r、Bernoulli采样）在6个数据集上的性能。
  - 伯努利采样率（0.05, 0.1, 0.2, 0.5）对性能和计算时间的影响。
- **效率分析**：系统比较了GNTK与LIGHTGNTK在7个图分类数据集上的蒸馏耗时。
- **理论分析**：通过附录提供了梯度近似误差上界、GNTK近似误差分析、以及训练-测试梯度关系的推导，支撑了方法的合理性。
- **分布假设验证**：计算了验证集与测试集嵌入的MMD和KL散度，证实了两者分布相近。

实验设计客观、公平，基线覆盖全面，样本量设置极具挑战性（低至每类1个样本），表格报告了标准差，结果可信度较高。

## 6. 论文的主要结论与发现

- **性能优越**：LIGHTGNTK 在所有任务级别（图、节点、边）上几乎均超越了现有蒸馏方法，并且在使用极少量样本（如每类1个）时，性能接近或达到使用全量数据的效果。例如，在PROTEINS上仅用2.25%的数据就达到了74.7%的准确率（全量78.6%）。
- **效率显著**：LIGHTGNTK 相比标准GNTK，蒸馏计算时间减少了6%~27%，实现了在大型图上可接受的耗时代价。
- **组件有效**：消融研究表明，伯努利采样策略在捕获全局和局部结构信息上优于仅保留最大或最小特征值的方法；采样率为0.1时实现了性能与效率的最佳平衡。
- **理论支撑**：给出了低秩近似下的梯度误差及GNTK逼近误差上界，从理论上保证了方法的可靠性。

## 7. 优点

- **统一的任务框架**：通过子图锚定策略，首次将图、节点、边级下游任务统一在相同的蒸馏和微调范式下，扩展了GNTK的适用场景。
- **理论保障的轻量化设计**：从拉普拉斯谱采样出发，提供了梯度误差和核近似的可证明上界，而非单纯的启发式加速，兼顾了效率与精度的可解释性。
- **极致的样本效率**：在极端小样本（1-shot）条件下仍能取得有竞争力的性能，对于数据稀缺或计算资源受限的持续学习场景极具价值。
- **计算与性能的均衡**：在维持甚至提升SOTA性能的同时，显著降低了蒸馏阶段的计算开销，并简化了微调所需的数据量。

## 8. 不足与局限

- **依赖验证集代理**：方法假设验证集与测试集同分布，并使用验证集指导样本选择。当现实应用中分布偏移显著时，选择的样本可能并非最优，影响泛化能力。
- **大图级任务的潜在瓶颈**：尽管通过蒙特卡洛采样缓解，但对于节点数极其庞大的超大规模图，子图分解和拉普拉斯特征分解仍可能成为负担，文中未能提供在超大规模社交网络上的实验验证。
- **超参数敏感性**：伯努利采样率 \(p\) 对性能和效率的影响在文中虽有分析，但最优值可能依赖数据集，未提供自动选择机制。
- **仅限于分类/链接预测**：方法主要针对分类和链接预测任务设计，未探索回归或异常检测等其他下游任务。
- **计算环境未详细说明**：GPU数量未提及，可能影响对算力需求的理解；缺少与其他预训练适配范式（如提示学习）的对比。

（完）
