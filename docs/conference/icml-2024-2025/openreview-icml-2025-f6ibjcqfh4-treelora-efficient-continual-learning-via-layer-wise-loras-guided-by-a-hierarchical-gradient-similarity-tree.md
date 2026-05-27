---
title: "TreeLoRA: Efficient Continual Learning via Layer-Wise LoRAs Guided by a Hierarchical Gradient-Similarity Tree"
title_zh: "TreeLoRA: 基于分层梯度相似树的逐层低秩适配器高效持续学习"
authors: "Yu-Yang Qian, Yuan-Ze Xu, Zhen-Yu Zhang, Peng Zhao, Zhi-Hua Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=f6ibJCQfH4"
tags: ["query:continual"]
score: 9.0
evidence: 利用逐层LoRA的高效持续学习
tldr: 本文提出TreeLoRA，一种高效的持续学习方法，特别针对大型预训练模型。通过构建层次化梯度相似树来指导逐层低秩适配器的分配，TreeLoRA能够在线更新模型以适应新任务，同时保留旧知识，防止灾难性遗忘。实验表明该方法显著降低了计算开销和参数增长，在多个持续学习基准上实现了优越的性能。该工作为在资源受限的环境下部署大模型持续学习提供了有效途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 619, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1747, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 626, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1748, \"height\": 725, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1042, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1773, \"height\": 699, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 525, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 818, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 633, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1773, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 717, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1599, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1755, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 546, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1749, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1342, \"height\": 209, \"label\": \"Table\"}]"
motivation: 在数据流环境中需要高效持续学习以防止灾难性遗忘。
method: 提出TreeLoRA，利用分层梯度相似树构建逐层低秩适配器。
result: 显著降低大模型持续学习的计算和参数成本。
conclusion: 为大规模预训练模型的高效持续学习提供了新方法。
---

## Abstract
Many real-world applications collect data in a streaming environment, where learning tasks are encountered sequentially. This necessitates *continual learning* (CL) to update models online, enabling adaptation to new tasks while preserving past knowledge to prevent catastrophic forgetting. Nowadays, with the flourish of *large pre-trained models* (LPMs), *efficiency* has become increasingly critical for CL, due to their substantial computational demands and growing parameter sizes. In this paper, we introduce TreeLoRA (K-D Tree of Low-Rank Adapters), a novel approach that constructs *layer-wise* adapters by leveraging hierarchical gradient similarity to enable efficient CL, particularly for LPMs. To reduce the computational burden of task similarity estimation, we employ *bandit* techniques to develop an algorithm based on lower confidence bounds to efficiently explore the task structure. Furthermore, we use sparse gradient updates to facilitate parameter optimization, making the approach better suited for LPMs. Theoretical analysis is provided to justify the rationale behind our approach, and experiments on both *vision transformers* (ViTs) and *large language models* (LLMs) demonstrate the effectiveness and efficiency of our approach across various domains, including vision and natural language processing tasks.

---

## 论文详细总结（自动生成）

好的，以下是对论文《TreeLoRA: Efficient Continual Learning via Layer-Wise LoRAs Guided by a Hierarchical Gradient-Similarity Tree》的结构化总结。

### 1. 论文的核心问题与整体含义

*   **研究背景与核心问题**：许多现实应用中的数据是以流的形式顺序到达的，模型需要以**持续学习**的方式在线更新，以适应新任务并防止灾难性遗忘。随着**大型预训练模型**的兴起，其巨大的计算开销和参数量对持续学习的效率提出了严峻挑战。
*   **整体含义与目标**：本文旨在解决**面向大型预训练模型的高效持续学习**问题。核心目标是设计一种方法，既能在线高效地适应新任务，又能保留旧知识，同时避免计算复杂度随任务数量线性增长。

### 2. 论文提出的方法论

*   **核心思想**：TreeLoRA（K-D树结构的低秩适配器）的核心是利用**层级化的任务梯度相似性**来构建一个树形结构，以高效地组织和管理历史任务的知识，实现知识共享与冲突隔离。
*   **关键技术细节**：
    *   **TreeLoRA树结构设计**：
        *   该结构模拟了深度神经网络分层的特性：**根节点**代表所有任务，**浅层节点**的适配器捕获多组任务间的共享模式，**深层节点**则对应任务特化的语义，**叶节点**对应于单个任务的适配器。
        *   任务是依据**梯度方向的L1范数相似度**进行分组的，相似度超过阈值δ的任务被归为同一组（节点）。
    *   **基于老虎机的自适应树构建**：
        *   为减少计算所有历史任务梯度的开销，TreeLoRA将寻找最相关任务组建模为**多臂老虎机问题**，将每个历史任务（或任务组）视为一个摇臂。
        *   引入**下置信界算法**来选择最有潜力的子节点。在每轮迭代，算法根据公式 `LCB_k = \hat{\mu}_k - 2\sqrt{\frac{\log t}{n_k}}` （及非叶节点的变体）计算各节点的LCB值，并选择值最小的分支进行探索，以平衡探索与利用。
    *   **高效的稀疏更新**：
        *   模型参数的更新公式为 `w_{t+1}^n = w_t^n - \alpha \cdot S[\nabla\ell(w_t^n; x_t, y_t)] - \lambda \cdot \|\hat{g}_t^n - \hat{g}_t^k\|_1`。
        *   该更新通过一个**低秩稀疏化函数** `S[\cdot]` 和基于梯度残差的**自适应正则化项**实现，仅更新当前任务组中最相关的参数，从而保留先前学到的知识。
    *   **理论保证**：论文证明了在光滑树结构的假设下，该方法相比不使用树结构的传统老虎机算法，其遗憾界从 `O(\sqrt{N})` 降低至 `O(\sqrt{\log N})`，其中N为任务数。

### 3. 实验设计

*   **数据集/场景**：实验覆盖了视觉和自然语言处理两大领域。
    *   **视觉任务**：采用**Split CIFAR-100、Split ImageNet-R和Split CUB-200**三个基准数据集，将图像分类任务分割为顺序到达的子任务。
    *   **自然语言处理任务**：采用专为LLM持续学习设计的**TRACE基准**，包含8个不同的数据集，涉及多语言、代码生成、数学推理等挑战性任务。
*   **对比方法**：TreeLoRA与以下多个类别的方法进行了比较：
    *   **基线方法**：常规按顺序微调LoRA的 `SeqLoRA`。
    *   **基于回放的方法**：`GEM`。
    *   **基于正则化的方法**：`EWC`。
    *   **基于提示的方法**：`L2P`, `DualPrompt`。
    *   **层次化分解方法**：`HiDePrompt`, `HiDeLoRA`。
    *   **正交子空间方法**：`O-LoRA` 以及其他一些先进方法如 `SAPT`, `TASL`, `InfLoRA`。

### 4. 资源与算力

*   **视觉实验算力**：使用了**8块Nvidia V100 GPU**。
*   **语言模型实验算力**：使用了**4块Nvidia A800 (80GB) GPU**。
*   **训练时长**：论文在结果表格中展示了训练时间（TIME），例如在ViT的CIFAR-100数据集上，TreeLoRA训练时间为214秒，相比对比方法有最高**3.2倍**的速度提升；在LLM的TRACE基准上，训练时间有最高**2.4倍**的速度提升。

### 5. 实验数量与充分性

*   **实验数量充足**：论文进行了多组实验，覆盖了**4种不同规模的LLM**（Mistral-7B, LLaMA-2-7B, Gemma-2B, LLaMA-3.2-1B）和**3个ViT基准**，并对比了**10种以上的方法**。
*   **分析全面**：
    *   **消融研究**：验证了梯度相似性惩罚项和基于LCB的搜索策略两个核心组件的有效性。
    *   **效率与性能权衡分析**：通过速度-精度对比图，直观展示了TreeLoRA在效率和性能上的综合优势。
    *   **超参数敏感性分析**：测试了正则化系数λ和学习率α对性能的影响，表明方法对超参数选择具有鲁棒性。
    *   **树结构可视化与深度影响分析**：通过对学习到的树结构进行可视化，证明了其捕获任务内在语义关系的能力；并分析了不同树深度对性能的影响。
    *   **鲁棒性验证**：额外的实验（如不同任务顺序、15个任务的长序列）验证了方法的稳定性和可扩展性。

### 6. 论文的主要结论与发现

*   TreeLoRA在对大型预训练模型进行持续学习时，**能够达到与最先进方法相当甚至更优的性能**。
*   TreeLoRA在**训练效率上具有显著优势**，在ViT和LLM上分别实现了高达3.2倍和2.4倍的速度提升。
*   该方法能够**有效地捕获任务间的层次化相似性结构**，从而促进知识共享并缓解灾难性遗忘。
*   理论分析证明，其树状老虎机搜索策略能实现**更紧的遗憾界**，从理论上支撑了其高效性。

### 7. 优点

*   **高创新性**：巧妙地将K-D树结构、低秩适配器与老虎机算法相结合，创新性地解决了大型模型持续学习中的效率瓶颈。
*   **理论与实验并重**：既有扎实的理论推导（遗憾界分析），又有全面且坚实的实验验证，包括多种模型、数据集和全面的消融、分析实验。
*   **实用性强**：方法在保持高性能的同时，显著降低了计算和存储开销（GPU内存和磁盘占用小），非常贴合大型模型在资源受限环境下部署的实际需求。
*   **可解释性好**：学习到的树结构本身可视化了任务之间的关系，具备良好的可解释性。

### 8. 不足与局限

*   **树结构对任务序列的敏感性**：论文中提到未来将研究时变任务结构，表明该树状结构可能对任务到达的顺序比较敏感，不同的任务序列可能会构建出不同的树，从而影响性能。
*   **新任务类型可能受限**：方法假设新任务与历史任务存在某种梯度相似性。若遇到一个与所有历史任务都极不相似的孤立新任务，算法可能仍需为其创建独立分支，此时的效率和知识迁移优势可能会减弱。
*   **超参数细节未完全脱离手动设置**：虽然任务相似性阈值δ可以自动确定，但树的深度、正则化系数λ、学习率α等关键参数仍需手动设定，尽管实验证明其对λ和α不敏感。
*   **实验偏差风险**：尽管对比了众多方法，但所有实验均基于Transformer架构（ViT和LLM），虽然论文声称具有通用性，但未在CNN等其他主流架构上验证。

（完）
