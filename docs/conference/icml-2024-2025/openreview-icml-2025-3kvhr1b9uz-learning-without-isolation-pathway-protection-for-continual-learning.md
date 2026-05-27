---
title: "Learning without Isolation: Pathway Protection for Continual Learning"
title_zh: 学习无隔离：持续学习的通路保护
authors: "Zhikang Chen, Abudukelimu Wuerkaixi, Sen Cui, Haoxuan Li, Ding Li, Jingfeng Zhang, Bo Han, Gang Niu, Houfang Liu, Yi Yang, Sifan YANG, Changshui Zhang, Tianling Ren"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=3KVHR1b9UZ"
tags: ["query:continual"]
score: 9.0
evidence: 通路保护以防止灾难性遗忘
tldr: 针对深度网络在序列任务学习中灾难性遗忘问题，现有方法主要保护旧任务参数但扩展性差。本文受神经科学启发，提出保护网络通路而非参数的新视角，认为通路对保存旧知识更为重要。实验表明通路保护方法有效缓解了灾难性遗忘，为持续学习开辟了新的研究方向。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1699, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 675, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1052, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 863, \"height\": 563, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 1088, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 858, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 738, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1104, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1102, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 993, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 994, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1764, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1765, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1423, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 984, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 982, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 980, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1767, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1767, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1450, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1451, \"height\": 282, \"label\": \"Table\"}]"
motivation: 现有持续学习方法聚焦参数保护但不可扩展，通路在保存旧知识中更为关键。
method: 受神经科学和物理学启发，提出保护网络通路而非参数的持续学习方法。
result: 表明通路保护比参数保护更有效应对灾难性遗忘。
conclusion: 为持续学习提供了新的通路保护视角，突破参数保护的限制。
---

## Abstract
Deep networks are prone to catastrophic forgetting during sequential task learning, i.e., losing the knowledge about old tasks upon learning new tasks. To this end, continual learning (CL) has emerged, whose existing methods focus mostly on regulating or protecting the parameters associated with the previous tasks. However, parameter protection is often impractical, since the size of parameters for storing the old-task knowledge increases linearly with the number of tasks, otherwise it is hard to preserve the parameters related to the old-task knowledge. In this work, we bring a dual opinion from neuroscience and physics to CL: in the whole networks, the pathways matter more than the parameters when concerning the knowledge acquired from the old tasks. Following this opinion, we propose a novel CL framework, learning without isolation (LwI), where model fusion is formulated as graph matching and the pathways occupied by the old tasks are protected without being isolated. Thanks to the sparsity of activation channels in a deep network, LwI can adaptively allocate available pathways for a new task, realizing pathway protection and addressing catastrophic forgetting in a parameter-effcient manner. Experiments on popular benchmark datasets demonstrate the superiority of the proposed LwI.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文，以Markdown形式，对该论文进行结构化、深入且客观的总结。

### 1. 论文的核心问题与整体含义

- **核心问题**:
  - 深度网络在序列化学习多个任务时，会遭受**灾难性遗忘**：学习新任务后，几乎完全丧失执行旧任务的能力。
  - 现有的持续学习方法大多侧重于**参数保护**，即通过正则化、权重掩码等方式，隔离并固定与旧任务相关的模型参数。这种方法存在两个主要弊端：
    1.  **可扩展性差**：存储旧任务知识的参数量通常随任务数量线性增长。
    2.  **任务隔离**：为不同任务创建的参数子网络彼此独立，阻碍了任务间的知识共享和正向迁移。

- **整体含义**:
  - 本文受神经科学（大脑稀疏连接、通路重配置）和物理学启发，提出了一个针对持续学习的新观点：**在整体网络中，通路比参数更重要**。
  - 在此观点下，论文旨在探索一种全新的持续学习方向——**通路保护**，以参数高效的方式，在避免灾难性遗忘的同时，不隔离不同任务，允许它们共享信息。

### 2. 论文提出的方法论

- **核心思想**:
  - 提出一个名为**无隔离学习 (Learning without Isolation, LwI)** 的持续学习框架。
  - **通路保护**：利用深度网络中激活通道的**稀疏性**，为不同任务自适应地分配不同的激活通路，而非直接隔离或固化参数。
  - **模型融合**：当学习新任务时，并非直接在新模型上进行微调，而是先为新任务训练一个单独的模型，然后通过图匹配算法将其与旧模型进行融合。

- **关键技术细节**:
  - **模型融合即图匹配 (Model Fusion as Graph Matching)**：将两个模型的融合问题形式化为图匹配问题。
    - **节点与边**：将网络中某一层的通道视为图的节点，相邻层通道间的连接视为图的边。
    - **分层对齐**：为避免全图匹配的高额计算开销，采用逐层匹配策略，在每一层内计算两个模型的通道对齐关系。
    - **公式化**：目标为寻找一个置换矩阵 `P`，使得对齐后两个模型对应边的相似度之和最大（或最小）。这是一个二次分配问题，计算相似度矩阵 `K`，其元素 `K[a,c,b,d]` 代表模型X中边 `(a,c)` 与模型Y中边 `(b,d)` 的欧氏距离。
  - **差异化匹配策略**：这是实现通路保护的关键，根据网络不同深度的特性采取不同匹配逻辑。
    1.  **浅层网络——最大化相似度匹配**：浅层倾向于学习任务间的共性特征。因此，在此阶段将两个模型最相似的通道对齐并融合（使用相似度矩阵 `K` 本身），以促进任务间的协作与知识共享。
    2.  **深层网络——最小化相似度匹配**：深层倾向于学习任务独有的特异性特征。因此，在此阶段将两个模型最不相似的通道对齐并融合（使用相似度矩阵的相反数 `-K`），实现“错位融合”，从而为不同任务保留和分配各自独特的通路，实现通路保护。
  - **算法流程**:
    1.  **训练新模型**：在新任务的数据上训练模型，同时使用知识蒸馏损失，对齐新旧模型的输出，防止特征空间漂移。
    2.  **融合新旧模型**：使用上述图匹配算法计算每一层的置换矩阵 `P`。然后，按照置换矩阵对旧模型的通道进行重排，使其与新模型在通路上一一对应。最后，通过加权平均的方式融合两个模型的参数。

### 3. 实验设计

- **数据集**:
  - **CIFAR-100**：包含100个类别，划分成5、10、20个任务（5/10/20 splits）进行序列学习。
  - **Tiny-ImageNet**：包含200个类别，同样划分成5、10、20个任务。

- **基础架构**:
  - **ResNet32**：较小的残差网络，用于评估模型容量较小时的性能。
  - **ResNet18**：标准的残差网络，用于评估模型容量较大时的性能。

- **对比方法**:
  - **正则化方法**: EWC， RWalk, LwF， SPG。
  - **参数隔离/架构方法**: GPM, WSN, SPU。
  - **基于回放的方法**: iCaRL, LUCIR（存储2000个样本作为范例）。

- **评估场景**:
  - **Task-Aware（任务已知）**: 测试时已知数据来自哪个任务，可直接使用对应的分类头。
  - **Task-Agnostic（任务未知）**: 测试时不知道数据来源任务，需要在所有见过的类别中进行分类。

### 4. 资源与算力

- **论文中明确说明的算力情况**:
  - 所有实验在一个本地Linux服务器上进行。
  - **GPU型号**: GeForce RTX 2080 Ti GPUs。
  - **CPU**: 双路 Intel(R) Xeon(R) CPU E5-2640 v4 @ 2.40GHz，32个逻辑核心。
  - **训练时长**: 文中未明确提及训练总时长。

### 5. 实验数量与充分性

- **实验数量**:
  - **主体实验**: 包含2个架构(ResNet32, ResNet18) × 2个数据集(CIFAR-100, Tiny-ImageNet) × 3种任务分割(5/10/20 splits) × 2种测试模式(Task-Aware, Task-Agnostic) 的超24组主要精度对比实验。
  - **遗忘率分析**: 1组关于不同方法在CIFAR-100上Task-Aware遗忘率的对比实验。
  - **消融实验**: 进行了4组关键的消融研究，以验证方法各组件的有效性：
    1.  **通路分流模块有效性**：对比了在所有层都使用最大化相似度匹配（`w/o task diversion`）的效果。
    2.  **最小化相似度匹配的层数**：测试了在最后1、2、3、4层分别使用最小化相似度匹配的影响。
    3.  **相似度度量方式**：对比了欧氏距离和余弦相似度两种度量方法。
    4.  **知识蒸馏模块有效性**：对比了有无知识蒸馏（`w/o KD`）的性能。
  - **极限任务数量实验**：在Tiny-ImageNet上将任务数增加至100进行测试。

- **充分性与公平性评估**:
  - **充分性**: 实验设计全面，覆盖了不同规模的数据集、不同容量的网络、多种任务分割粒度以及两种核心评估协议。消融实验对方法的两个关键创新点（任务分流和差异化匹配）进行了验证，结论明确。增加任务数量到100的实验进一步证明了方法的可扩展性。
  - **客观性与公平性**: 对比基线涵盖了正则化、参数隔离、基于回放等主流流派，具有代表性。所有对比方法都遵循了相同的骨干网络和训练超参数（如学习率、优化器、epoch数），确保了比较的公平性。对测试模式（Task-Aware与Agnostic）的区分也使得评估更为严谨。

### 6. 论文的主要结论与发现

- **通路保护优于参数保护**：提出的LwI方法在CIFAR-100和Tiny-ImageNet数据集上，无论是任务已知还是任务未知的场景下，其性能整体超越了现有的无回放持续学习方法（正则化、参数隔离），甚至在某些情况下媲美或超越了基于回放的方法。
- **有效缓解灾难性遗忘**：通过遗忘率实验证实，LwI的遗忘率显著低于EWC、RWalk、LwF等传统方法，甚至优于一些利用回放样本的方法。
- **模型容量与性能正相关**：实验发现，随着模型容量增大（从ResNet32到ResNet18），LwI方法的性能提升更为显著，这验证了其利用大模型稀疏性进行通路保护的核心假设。
- **差异化匹配策略至关重要**：
  - 浅层最大化相似度匹配、深层最小化相似度匹配的“任务分流”策略是实现高性能的关键。
  - 实验表明，仅在最终层进行最小化相似度匹配，就能获得最优或接近最优的效果。

### 7. 优点

- **新颖的视角**：从参数保护转向**通路保护**，为持续学习提供了新的研究范式，概念上更具整体性和生物合理性。
- **创新的方法论**：巧妙地将**图匹配**技术应用于持续学习的模型融合场景，并通过**差异化匹配策略**实现了对不同深度网络通路功能的解耦和利用，设计思想精巧。
- **无数据依赖与隐私保护**：该方法本质上是**无数据**的，即不需要存储旧任务的数据样本，在数据隐私保护方面具有显著优势。
- **性能优异且可扩展**：在多个基准测试中取得了超越主流方法的性能，并且模型容量越大，效果越好，显示出良好的可扩展潜力。
- **实验扎实**：实验设计系统、详尽，对比充分，消融研究到位，有力地支撑了核心论点。

### 8. 不足与局限

- **模型大小与算力验证不足**：
  - 承认了未在**大型模型**（如LLMs）上验证方法的有效性，这是一个重要的局限性声明。
  - 尽管在2080 Ti上运行，但未给出具体训练时长，其计算开销与其它方法相比是高是低不够明确。图匹配过程本身也有一定计算复杂度，可能成为在大模型上应用的瓶颈。
- **任务未知场景下的性能**：在CIFAR-100的部分任务未知设定下，性能仍落后于使用了回放样本的方法（如LUCIR）。这表明，若不统一分类头的输出范围，仅靠通路保护在任务识别上仍有挑战。
- **图匹配算法的效率**：文中明确指出，分层匹配后的时间复杂度仍为 `O(C^4)`（C为每层通道数），这在网络通道数很多时计算量仍然很大，作者也提出未来需使用稀疏矩阵技术等方法来加速。
- **超参数影响**：方法涉及融合系数 `k`、知识蒸馏损失权重 `λ` 等超参数，论文隐含了这些参数的选择，但未深入探讨其敏感性。

（完）
