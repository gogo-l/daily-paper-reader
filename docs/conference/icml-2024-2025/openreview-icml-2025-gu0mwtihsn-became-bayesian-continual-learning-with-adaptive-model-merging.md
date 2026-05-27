---
title: "BECAME: Bayesian Continual Learning with Adaptive Model Merging"
title_zh: BECAME：贝叶斯持续学习与自适应模型合并
authors: "Mei Li, Yuxiang Lu, Qinyan Dai, Suizhi Huang, Yue Ding, Hongtao Lu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=gU0MwTihsn"
tags: ["query:continual"]
score: 9.0
evidence: 贝叶斯持续学习与自适应模型合并方法，用于稳定性-可塑性权衡
tldr: 针对持续学习中稳定性与可塑性权衡的挑战，提出BECAME方法，基于贝叶斯持续学习原理推导出闭式解，通过自适应模型合并提升新旧任务间的平衡，实验表明其在多个基准上有效缓解灾难性遗忘。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1365, \"height\": 823, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 852, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 850, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 849, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1752, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1752, \"height\": 228, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1769, \"height\": 1692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1760, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1765, \"height\": 1682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1760, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1768, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-gu0mwtihsn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1766, \"height\": 368, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1770, \"height\": 628, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1777, \"height\": 492, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 867, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1568, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1566, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1765, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1438, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1674, \"height\": 509, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1300, \"height\": 381, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1728, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-gu0mwtihsn/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1470, \"height\": 213, \"label\": \"Table\"}]"
motivation: 现有持续学习方法在平衡知识保留与新任务适应方面仍存在困难，模型合并方法多依赖经验假设。
method: 提出BECAME，将模型合并机制重新表述为贝叶斯持续学习，推导出闭式合并方案。
result: 实验表明，BECAME在多个持续学习基准上取得了稳定的性能提升，优于现有方法。
conclusion: BECAME提供了一种理论驱动的自适应模型合并策略，有效提升了持续学习的稳定性-可塑性平衡。
---

## Abstract
Continual Learning (CL) strives to learn incrementally across tasks while mitigating catastrophic forgetting. A key challenge in CL is balancing stability (retaining prior knowledge) and plasticity (learning new tasks). While representative gradient projection methods ensure stability, they often limit plasticity. Model merging techniques offer promising solutions, but prior methods typically rely on empirical assumptions and carefully selected hyperparameters. In this paper, we explore the potential of model merging to enhance the stability-plasticity trade-off, providing theoretical insights that underscore its benefits. Specifically, we reformulate the merging mechanism using Bayesian continual learning principles and derive a closed-form solution for the optimal merging coefficient that adapts to the diverse characteristics of tasks. To validate our approach, we introduce a two-stage framework named BECAME, which synergizes the expertise of gradient projection and adaptive merging. Extensive experiments show that our approach outperforms state-of-the-art CL methods and existing merging strategies https://github.com/limei0818/BECAME.

---

## 论文详细总结（自动生成）

好的，我将按照要求，基于提供的论文内容，生成一份详细的中文总结，并以Markdown格式组织。

### 1. 论文的核心问题与整体含义
本论文聚焦于**持续学习**中的核心挑战：如何平衡**稳定性**（保留旧任务知识）与**可塑性**（学习新任务能力），从而缓解灾难性遗忘。
*   **研究动机**：现有的梯度投影方法能很好地保证稳定性，但往往严重限制了模型学习新任务的可塑性。另一方面，模型合并技术虽展现出平衡稳定-可塑权衡的潜力，但以往方法多依赖经验假设（如假设新旧任务相互独立、采用固定合并系数等）和精心调参，缺乏理论指导且难以适应任务间的差异性。
*   **核心问题**：论文旨在探索模型合并如何能更有效地改善持续学习中的稳定-可塑权衡，并试图解决两个根本性问题：
    1.  模型合并为何能有效？
    2.  能否推导出一个自适应、闭式的最优合并系数？

### 2. 论文提出的方法论
论文提出了一个名为 **BECAME** 的两阶段框架，其核心思想是将模型合并机制与贝叶斯持续学习原理相结合，并基于拉普拉斯近似推导出闭式的最优合并系数。

*   **理论核心**：
    *   **更好的最优解（引理3.1）** ：作者证明，从旧任务的最优参数到新任务的无约束最优参数的线性路径上，总存在一个合并点，其累积损失低于两个端点。这为模型合并的有效性提供了理论保证。
    *   **闭式最优合并系数（公式17 & 20）** ：
        1.  **贝叶斯视角**：将持续学习过程重新表述为后验概率的最大后验估计(MAP)，即 `p(θ|D1:t) ∝ p(Dt|θ)p(θ|D1:t-1)`。
        2.  **拉普拉斯近似**：将难以处理的后验 `p(θ|D1:t-1)` 近似为一个多元高斯分布，其精度矩阵用费雪信息矩阵(FIM)的累加和来递归计算。
        3.  **凸优化求解**：将合并后的参数 `θ(λ) = (1-λ)θ_t−1 + λθ̂_t` 代入MAP目标函数，并对其进行二阶泰勒展开。作者证明该目标函数关于合并系数`λ`是**凸函数**，且导数在`λ=0`和`λ=1`处符号相反，因此存在唯一的全局最优解`λ*`。令导数为零，即可推导出`λ*`的闭式解。

*   **两阶段训练框架 (BECAME)**：
    *   **第一阶段（保证稳定性）**：模型在旧任务参数`θ*_{t-1}`基础上，使用**梯度投影**方法训练新任务，得到参数`θ^{GP}_t`。此时遗忘极少，但塑性受限。
    *   **第二阶段（增强可塑性）**：从`θ^{GP}_t`开始，不加任何约束地继续训练，得到参数`θ̂_t`。此时新任务性能最优，但遗忘严重。
    *   **自适应合并**：应用推导出的闭式解公式，在`θ^{GP}_t`和`θ̂_t`连线上计算出最优合并系数`λ*_t`，得到最终模型`θ*_t`。该系数基于新旧任务的费雪信息矩阵和参数变化量`Δθ`自适应决定，无需手动调参。
    *   **理论验证**：作者证明将起点从`θ*_{t-1}`替换为`θ^{GP}_t`是等价的，并且由于`θ^{GP}_t`的新任务损失更低，从而为合并后模型的损失提供了一个更紧的上界。

### 3. 实验设计
论文通过详尽的实验验证了BECAME的有效性。
*   **数据集/场景**：实验覆盖了4个主流的持续学习基准数据集：**20-Split CIFAR-100**, **10-Split CIFAR-100**, **25-Split TinyImageNet**, 和 **20-Split MiniImageNet**。此外，还在**5-Datasets**和**CIFAR-100 Superclass**上进行了补充实验。
*   **Baseline方法**：对比分为两大类，覆盖了持续学习的主流范式。
    *   **基于梯度投影的方法 (GPM-based)**：包括GPM及其变体TRGP、SGP、GPCNS，作为直接优化目标。
    *   **其他对比方法**：包括Adam-NSCL (NSCL)、Connector (结合NSCL与模型合并)、OWM、EWC、SI、LwF、A-GEM、FS-DGPM、ER-Res等代表性的正则化、重放和优化方法。
*   **合并策略对比**：直接比较了不同的模型合并策略，如等权重平均(`1/t`) 、固定系数(CoMA)和费雪加权平均(CoFiMA)，以证明其自适应系数`λ`的优越性。

### 4. 资源与算力
论文明确提到了实验所用算力：
*   **GPU型号**：所有实验均在一张 **NVIDIA GeForce RTX 4080** 显卡上完成。
*   **训练时长/效率**：论文在MiniImageNet数据集上对比了训练时长和显存占用。例如，GPM+Ours的训练时间为584秒，而TRGP为776秒；显存占用约为375 MB，远低于TRGP (1854 MB) 和 GPCNS (998 MB)。更新费雪信息矩阵的效率很高，每次任务仅需0.69秒。

### 5. 实验数量与充分性
实验设计非常充分、客观且公平，具有很强的说服力。
*   **实验组数**：大约在**4个主要基准数据集 × 8种以上的方法组合**上进行，加上不同合并策略的消融、效率和泛化性分析等，构成了一个庞大且系统的实验矩阵。
*   **公平性**：
    *   **网络架构一致**：GPM-based和NSCL-based实验分别使用与各自baseline完全相同的网络（5层AlexNet和ResNet-18）。
    *   **超参数一致**：大部分超参数沿用原方法的设定，仅做了适配性微调，确保了比较的公平性。
    *   **多次重复**：所有实验均使用**5个不同的随机种子**重复进行，并报告了均值和标准差，结果稳健可靠。
*   **评估指标全面**：采用了ACC、BWT、IM等多个指标，从整体性能、稳定性、可塑性多角度评估。还提出了AOA、STD等指标来评估泛化能力、前向迁移和任务间平衡性。

### 6. 论文的主要结论与发现
*   BECAME通过自适应模型合并，显著提升了梯度投影方法（GPM, NSCL等）的性能天花板，尤其是在**大幅提升可塑性(降低IM)** 的同时，**保持了良好的稳定性(BWT)**。
*   在多个基准数据集上，BECAME不仅在原始baseline基础上取得了一致的巨大提升（例如在NSCL上的10-Split CIFAR-100精度提升超8%），而且**超越了所有对比的State-of-the-Art方法**。
*   与其他需要繁琐超参调节的模型合并策略(CoMA, CoFiMA)相比，本文提出的闭式解不仅性能更优或相当，且完全自适应，无需任何手动调参，具有更强的泛化适用性。
*   该方法在提升精度的同时，还能使模型在不同任务上的表现更加**平衡**，并展现出更强的**泛化能力**。

### 7. 优点
*   **坚实的理论支撑**：从贝叶斯持续学习角度为启发式的模型合并提供了理论解释，并严格推导出闭式最优解，这是本文最大的亮点。
*   **方法简洁有效**：BECAME框架实现简单，可作为一个即插即用的模块无缝集成到任何梯度投影方法中，带来显著的性能提升。
*   **自适应性**：摒弃了经验性的调参，合并系数完全由数据和模型状态自适应决定，解决了不同任务、不同模型需不同合并系数的问题。
*   **实验全面扎实**：在多个基准、多种baseline上进行了详尽的对比，评估指标丰富，并对效率、任务平衡性等进行了深入分析，结果极具说服力。

### 8. 不足与局限
*   **对梯度投影方法的依赖**：该方法目前仅针对基于梯度投影的持续学习方法进行了验证和集成，将其扩展到其他类型的CL方法（如基于重放的方法）的有效性是未知的。
*   **拉普拉斯近似的精度**：方法的理论推导依赖于拉普拉斯近似和费雪信息矩阵的对角近似，当真实后验分布严重偏离高斯分布时，推导出的闭式解可能不是全局最优。
*   **两阶段训练的额外开销**：尽管额外开销在可接受范围内，但两阶段训练的本质意味着训练步骤和时间会比单阶段的baseline要长，存在效率上的折衷。
*   **应用场景局限**：实验集中于图像分类的Task-Incremental Learning设定，在更复杂的Class-Incremental Learning或Online CL等场景下的表现有待验证。

（完）
