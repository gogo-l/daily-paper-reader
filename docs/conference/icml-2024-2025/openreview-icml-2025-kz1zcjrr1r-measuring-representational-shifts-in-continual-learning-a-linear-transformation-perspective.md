---
title: "Measuring Representational Shifts in Continual Learning: A Linear Transformation Perspective"
title_zh: 从线性变换视角测量持续学习中的表征偏移
authors: "Joonkyu Kim, Yejin Kim, Jy-yong Sohn"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=Kz1zCJRr1r"
tags: ["query:continual"]
score: 8.0
evidence: 引入表征差异度量评估隐含层灾难性遗忘
tldr: 本文首次对持续学习中的表征遗忘进行理论分析，提出表征差异度量，通过比较两个模型快照的隐藏层空间差异来有效衡量遗忘程度。该度量可作为评估遗忘的可靠替代指标，为理解和缓解灾难性遗忘提供了新的视角和工具。实验验证了其有效性，对持续学习评估方法有重要补充作用。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 826, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 813, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 858, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 806, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 808, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 846, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1744, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1672, \"height\": 695, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1621, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1191, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1232, \"height\": 589, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1646, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1757, \"height\": 1401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1625, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1727, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1738, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-kz1zcjrr1r/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1071, \"height\": 804, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-kz1zcjrr1r/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 461, \"height\": 350, \"label\": \"Table\"}]"
motivation: 持续学习中灾难性遗忘的评估至关重要，但隐含层表征遗忘缺乏理论分析。
method: 首次理论分析表征遗忘，提出表征差异度量，衡量模型快照间隐藏层空间差异。
result: 实验证明该度量是评估遗忘的有效替代指标。
conclusion: 该工作为持续学习的表征遗忘提供了理论和度量工具。
---

## Abstract
In continual learning scenarios, catastrophic forgetting of previously learned tasks is a critical issue, making it essential to effectively measure such forgetting. Recently, there has been growing interest in focusing on representation forgetting, the forgetting measured at the hidden layer. In this paper, we provide the first theoretical analysis of representation forgetting and use this analysis to better understand the behavior of continual learning. First, we introduce a new metric called representation discrepancy, which measures the difference between representation spaces constructed by two snapshots of a model trained through continual learning. We demonstrate that our proposed metric serves as an effective surrogate for the representation forgetting while remaining analytically tractable. Second, through mathematical analysis of our metric, we derive several key findings about the dynamics of representation forgetting: the forgetting occurs more rapidly to a higher degree as the layer index increases, while increasing the width of the network slows down the forgetting process. Third, we support our theoretical findings through experiments on real image datasets, including Split-CIFAR100 and ImageNet1K.

---

## 论文详细总结（自动生成）

好的，以下是基于提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义
*   **核心问题**：在持续学习场景中，如何有效地衡量模型在隐藏层（即表征层面）对旧知识的遗忘（表征遗忘）。过去的研究大多集中在最终输出层面的遗忘，对表征遗忘缺乏理论分析。
*   **研究动机**：理解表征遗忘至关重要，原因在于：（1）在无监督持续学习等场景中，我们关心的正是模型的内部表征而非最终输出；（2）理解表征遗忘本身有助于更深入地理解最终输出层面的遗忘。
*   **整体含义**：本文旨在为表征遗忘提供首个理论分析框架，通过提出一个名为“表征差异”的新度量，来量化持续学习过程中模型内部表征空间的演变规律，并揭示网络结构（如层深、宽度）如何影响遗忘的动态过程。

### 2. 论文提出的方法论
*   **核心思想**：提出“表征差异”作为衡量表征遗忘的替代指标。该指标衡量的是模型在持续学习两个不同时间点的表征空间，在通过一个**最优线性变换对齐后**所残余的最小差异。
*   **关键技术细节**：
    *   **度量定义**：对于任务 t 和模型在训练了额外 Δt 个任务后的第 k 层，表征差异 `Dkt(ht, Δt)` 定义为：在对齐变换 T 下，两个模型对旧任务数据产生的表征空间之间的最小最大距离。这避免了直接计算最优线性分类器，使得分析更易处理。
    *   **理论分析**：
        *   **提出上界**：论文推导了表征差异的一个理论上界 `Ukt(Δt)`，该上界由一项独立于 Δt 的因子（包含表征空间大小、层缓冲和激活收缩常数）和一项依赖于 Δt 的函数（`ω(Δt)`）组成。
        *   **动态分析**：通过分析上界函数，预言了表征遗忘的两个阶段：**遗忘阶段**（差异随 Δt 单调增加）和 **饱和阶段**（差异逐渐收敛至一个渐近值）。
        *   **关键推论**：
            1.  渐近的表征差异与对应层的**表征空间的大小**成正比。
            2.  更深的层（更高的层索引 k）进入饱和阶段的速度更快。
            3.  增加网络的**宽度**会延迟饱和阶段的到来。

### 3. 实验设计
*   **数据集**：使用了 Split-CIFAR100 和 ImageNet1K 这两个真实的图像数据集。类别被划分成 50 个任务，Split-CIFAR100 每任务 2 类，ImageNet1K 每任务 5 类。
*   **模型与基准**：采用修改过的 ResNet 架构，通过调整步幅和卷积核大小来保持隐藏层特征图尺寸一致。网络层数 L=9，默认通道数为 8。主要验证对象是**本文提出的理论发现**，而非与其他持续学习方法对比性能。
*   **度量与评估**：采用线性探测准确率的下降 (`ΔPkt(Δt)`) 作为衡量“表征遗忘”的实测指标，并分析其与本文提出的理论上界 (`Ukt`) 以及表征空间大小 (`∥Rktht∥`) 之间的关系。

### 4. 资源与算力
*   论文的实验部分和附录中，并未明确提及所使用 GPU 的型号、数量或具体的训练时长等算力信息。只列出了优化器（AdamW）、学习率（0.001）、批次大小（512）和训练轮数（500）等超参数。

### 5. 实验数量与充分性
*   **实验数量**：实验设计覆盖了多个维度，以验证理论发现，主要包括：
    *   在两个主流数据集上的核心结论复现。
    *   对不同网络层（k=1 到 9）的遗忘演化规律分析。
    *   对不同网络宽度（通道数 m=64, 128, 256，或对应不同 `# channels`）的影响分析。
    *   对理论假设（如 Assumption 1）的实证支持，并在全连接网络、ResNet 和 ViT 上都进行了验证。
    *   验证了表征差异、表征空间大小、遗忘率和层索引之间的线性关系。
*   **充分性与公平性**：实验主要致力于验证自己的理论，而非与其他算法进行性能比拼，这在理论分析论文中是合理且充分的。实验设计能有效回应其提出的每一个理论发现。但作为理论验证，其结论的可推广性受限于所测试的模型架构和数据集。

### 6. 论文的主要结论与发现
*   **提出了一种有效的替代度量**：表征差异 (`Dkt`) 与实测的表征遗忘 (`ΔPkt`) 之间存在强线性关系，能有效作为后者的替代指标。
*   **揭示了遗忘的两阶段动态**：表征遗忘曲线呈现先单调增加（遗忘阶段）后逐渐饱和（饱和阶段）的特征。
*   **关联了遗忘量与表征空间大小**：渐近的表征遗忘程度与表征空间的规模成正比，并且表征空间的大小随层索引增加而线性增长。综上，更深的层会遗忘得更彻底。
*   **阐明了网络结构的影响**：遗忘的收敛速度随层深增加而加快，但随网络宽度增加而减慢。这意味着高层比低层遗忘得更快，而增加宽度可以减缓遗忘过程。

### 7. 优点
*   **首创性**：首次对持续学习中的表征遗忘现象进行了严格的理论分析，填补了该领域的空白。
*   **度量设计巧妙**：提出的“表征差异”度量通过引入最优线性变换，巧妙地解决了表征空间中因旋转等不改变输出性能的变化而导致的度量失效问题，既有效又便于理论分析。
*   **理论结果直观且实用**：得出的关于层深、宽度与遗忘动态的结论具有清晰的物理意义和指导价值，得到了实验的良好印证。
*   **分析框架清晰**：通过建立上界并分析其渐近行为和收敛速率，清晰地刻画了遗忘的动态特性。

### 8. 不足与局限
*   **理论假设较强**：分析依赖于一些较强的假设，如 Assumption 1（权重矩阵间存在精确的线性变换）和 Assumption 2（表征空间距离随任务数线性增长），这些假设虽得到部分实验支持，但其普适性可能有限。
*   **评估指标局限**：线性探测准确率下降作为一个性能指标，可能无法完全捕捉表征遗忘的所有方面。论文主要关注对第一个任务的遗忘，缺乏对后续任务遗忘、任务间干扰等更复杂动态的分析。
*   **任务设置简化**：实验将数据集按顺序分为类别不重叠的任务，这是一种最简单、最经典的持续学习设定，未涉及任务边界未知、数据分布渐变等更复杂的现实场景。
*   **缺乏与缓解方法的关联**：论文仅分析了遗忘的规律，但并未探讨如何利用这些理论发现来设计更好的算法以缓解表征遗忘，理论与实践应用之间存在距离。

（完）
