---
title: Task-aware Orthogonal Sparse Network for Exploring Shared Knowledge in Continual Learning
title_zh: 基于任务感知正交稀疏网络的持续学习中共享知识探索
authors: "Yusong Hu, De Cheng, Dingwen Zhang, Nannan Wang, Tongliang Liu, Xinbo Gao"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=tABvuya05B"
tags: ["query:continual"]
score: 9.0
evidence: 提出任务感知正交稀疏网络，在持续学习中探索共享知识，缓解长期学习中的遗忘和欠拟合
tldr: 现有持续学习方法常通过二分网络隔离新旧任务以避免遗忘，但长期学习会出现严重欠拟合。本文提出三分网络结构，新增共享知识探索部分，通过正交稀疏约束提取任务间共性。在长期持续学习基准中，该方法在零遗忘的同时保持高拟合度，显著提升模型可扩展性。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1713, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 836, \"height\": 432, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-tabvuya05b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1760, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tabvuya05b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tabvuya05b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1747, \"height\": 276, \"label\": \"Table\"}]"
motivation: 现有二分网络持续学习方法在长期学习中面临欠拟合问题，限制了知识共享。
method: 提出三分网络结构，增加共享知识探索层，运用正交稀疏性提取任务间共享表示。
result: 在长期持续学习设定下，该方法实现了无遗忘且无欠拟合的高性能。
conclusion: 共享知识探索是解决持续学习长期欠拟合的关键，正交稀疏网络提供了有效实现。
---

## Abstract
Continual learning (CL) aims to learn from sequentially arriving tasks without catastrophic forgetting (CF). By partitioning the network into two parts based on the Lottery Ticket Hypothesis---one for holding the knowledge of the old tasks while the other for learning the knowledge of the new task---the recent progress has achieved forget-free CL. Although addressing the CF issue well, such methods would encounter serious under-fitting in long-term CL, in which the learning process will continue for a long time and the number of new tasks involved will be much higher. To solve this problem, this paper partitions the network into three parts---with a new part for exploring the knowledge sharing between the old and new tasks. With the shared knowledge, this part of network can be learnt to simultaneously consolidate the old tasks and fit to the new task. To achieve this goal, we propose a task-aware **Orthogonal Sparse Network** (OSN), which contains shared knowledge induced network partition and sharpness-aware orthogonal sparse network learning. The former partitions the network to select shared parameters, while the latter guides the exploration of shared knowledge through shared parameters. Qualitative and quantitative analyses, show that the proposed OSN induces minimum to no interference with past tasks, *i.e.*, approximately no forgetting, while greatly improves the model plasticity and capacity, and finally achieves the state-of-the-art performances.

---

## 论文详细总结（自动生成）

好的，以下是对这篇题为《Task-aware Orthogonal Sparse Network for Exploring Shared Knowledge in Continual Learning》论文的结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：持续学习旨在让模型像人类一样逐步学习新任务，其核心挑战在于**灾难性遗忘**，即模型在学习新任务后会急剧遗忘旧任务的知识。现有基于参数剪枝（Parameter Pruning）的方法（如WSN）借鉴“彩票假说”，将网络一分为二：一部分冻结以保留旧知识，另一部分用于学习新知识。虽然这能有效缓解遗忘，但存在一个严重瓶颈。
*   **核心问题**：这种“二分网络”策略导致用于学习新任务的那部分网络容量极其有限。尤其在**长期持续学习**场景下，随着任务数量不断增多，模型会出现严重的**欠拟合**，丧失学习新知识的能力（即可塑性差），因为它**忽略了新旧任务之间可以共享的知识**。
*   **整体含义**：本文指出，简单地隔离新旧任务参数是低效的。相反，应该在网络中明确划分出一个独立的“共享空间”，来探索和学习任务间的共性知识，从而在不引入遗忘的前提下，显著提升模型的容量和可塑性，更好地解决稳定性-可塑性困境。

### 2. 论文提出的方法论

论文提出了一种名为**任务感知正交稀疏网络（OSN）** 的新方法。其核心思想是将传统的“二分”网络结构，扩展为“三分”结构，并赋予每个部分不同的学习策略。关键技术细节如下：

*   **核心思想：三分网络结构**
    网络参数被划分为三个互不重叠的部分：
    1.  **冻结的旧任务参数** (`M_{t-1}^l - m_t^l`)：用于固化旧知识，保持稳定性。
    2.  **自由的新任务参数** (`1 - M_{t-1}^l`)：用于不受限制地学习新知识，保证可塑性。
    3.  **共享参数** (`M_{t-1}^l \cap m_t^l`) ：用于探索新旧任务的**共享知识**，这是本文的创新核心。

*   **关键技术1：共享知识驱动的网络划分**
    *   该过程旨在从已有的冻结子网络（`M_{t-1}^l`）中，筛选出那些对新任务也重要的参数，作为共享参数。
    *   使用了一个**权重重要性函数** `CWI(·)`，该函数结合了参数的绝对值和其在当前新任务上的梯度L1范数，来量化每个旧任务参数对新任务的敏感度。
    *   通过选择TOP-k最重要的参数，即可得到共享参数的掩码 `m_t^l`。

*   **关键技术2：锐度感知的正交稀疏网络学习**
    *   **正交投影**：为使共享参数能在巩固旧任务的同时拟合新任务，其梯度更新方向被限制在与旧任务特征空间正交的子空间内。这由**引理3.1**保证：当参数更新与旧任务输入特征正交时，模型在旧任务上的输出保持不变。这通过一个正交投影矩阵 `P_{t-1}^l` 实现。
    *   **锐度感知优化**：传统正交投影是近似的，可能导致共享参数更新时仍对旧任务产生微小干扰。OSN引入了锐度感知最小化思想，**寻求损失函数平面上的“平坦”最小值而非“尖锐”最小值**。这样，在相同参数变化量下，平坦区域对应的旧任务损失变化更小，能更好地保留旧知识，从而提升知识共享的效果。
    *   **数据增强**：在训练新任务时，通过对小批量数据进行线性混合，生成增强样本，以进一步平滑损失函数平面，辅助寻找更平坦的最小值。改进后的正交投影矩阵由旧任务特征的SVD分解结果，根据奇异值阈值重新计算得到。

### 3. 实验设计

*   **数据集/场景**:
    *   **标准CL数据集**: PMNIST, Split CIFAR-100, CIFAR-100 Superclass, 5-Datasets。
    *   **长期CL数据集**: Split TinyImageNet (40个任务) 和 Split CIFAR-100-50 (50个任务)。
    *   **实验场景**主要集中在任务增量学习。

*   **基准对比方法**:
    *   对比了多个类别的SOTA方法，包括正则化（EWC）、参数扩展、参数剪枝（PackNet, SupSup, WSN）、正交投影（GPM, DualGPM）、以及近期工作（Connector, API, DFGP）等共十余种方法。

### 4. 资源与算力

*   论文明确指出，所有实验均在 **4块 NVIDIA 2080Ti GPU** 上使用 **PyTorch** 框架实现。
*   不同数据集的训练轮数、批大小、学习率等超参数在论文第4.2节和附录中有详细说明。论文未给出训练所需的总时间。

### 5. 实验数量与充分性

*   **实验数量丰富**，覆盖了**5个标准数据集和2个长期数据集**的全面对比。
*   **对比方法全面**，与各类SOTA方法进行了对比，结果有说服力。
*   **消融实验设计合理**，逐步验证了“剪枝”、“网络划分”、“正交投影”和“锐度感知优化”各模块的贡献。
*   **分析维度多样**，包括网络容量（CAP指标）、模型可塑性（对角线精度）、不同稀疏度下的性能、以及共享参数比例（k值）的敏感性分析。实验设计**客观、公平**，严格遵循了基线方法WSN的实验设置。

### 6. 论文的主要结论与发现

*   通过在网络中明确划分“共享参数”并利用正交投影进行学习，可以有效挖掘新旧任务间的**共享知识**，为解决持续学习中的稳定性-可塑性困境提供了新思路。
*   提出的**OSN方法不仅能实现“近似零遗忘”**，还**极大地提升了模型的可塑性和容量**，解决了现有参数剪枝方法在长期学习中欠拟合的问题。
*   在多个基准测试中，OSN均刷新了SOTA性能，尤其在长期CL场景下优势显著（如在Split TinyImageNet上比第二名WSN高出**3.46% ACC**）。

### 7. 优点

*   **视角新颖**：首次在参数剪枝框架下，明确提出三分网络结构和共享参数的概念，以探索新旧任务间的共享知识。
*   **理论与方法结合**：通过一个引理说明正交投影能保证旧知识不遗忘，进而结合锐度感知优化从技术上实现更好的知识共享，理论基础扎实。
*   **性能卓越**：在不牺牲稳定性的前提下（几乎零遗忘），大幅提升了模型的可塑性，尤其在长期CL任务上优势明显，取得了SOTA结果。
*   **实验完善**：实验设计全面，不仅有与众多SOTA方法的量化对比，还有详尽的消融研究和参数敏感性分析，论证充分。

### 8. 不足与局限

*   **实验场景局限**：本文主要聚焦于**任务增量学习**，即测试时已知任务ID。作者在结论中也承认，将该方法扩展到更具挑战性的**类增量学习**是未来的工作。
*   **计算与内存开销**：该方法需要维护特征矩阵并进行SVD分解以计算正交投影，同时引入锐度感知优化。文中未对其带来的额外计算复杂度和训练时间进行量化分析。
*   **超参数敏感性**：方法引入了多个超参数，如剪枝率 `c`、共享参数比例 `k`、正交投影阈值 `ε_{th}^l` 等。虽然论文分析了 `k` 的敏感度，但多超参数的联合调优和不同数据集下的最佳设置可能需要较多经验。
*   **未在更大规模数据集上验证**：实验使用的数据集（如CIFAR， TinyImageNet）规模相对较小，在大规模数据集（如全量ImageNet）上的有效性有待考证。

（完）
