---
title: "LADA: Scalable Label-Specific CLIP Adapter for Continual Learning"
title_zh: LADA：用于持续学习的可扩展标签特定CLIP适配器
authors: "Mao-Lin Luo, Zi-Hao Zhou, Tong Wei, Min-Ling Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=u2jH71U9T6"
tags: ["query:continual"]
score: 9.0
evidence: 提出标签特定记忆单元用于CLIP以在持续学习中防止遗忘
tldr: 针对CLIP在持续学习中需选择任务特定参数易出错导致遗忘的问题，提出标签特定适配器LADA，为冻结编码器附加轻量记忆单元，聚合任务无关知识生成判别特征，无需参数选择即可有效防止遗忘。在多个基准上达到先进性能，实现了可扩展且低遗忘的持续学习。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-u2jh71u9t6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1774, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u2jh71u9t6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1684, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u2jh71u9t6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 378, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1644, \"height\": 1070, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1644, \"height\": 1004, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 876, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1643, \"height\": 1074, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1640, \"height\": 1000, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1353, \"height\": 659, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1352, \"height\": 661, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1353, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1352, \"height\": 661, \"label\": \"Table\"}]"
motivation: 现有CLIP持续学习方法需在推理时选择任务特定参数，易出错导致遗忘。
method: 设计标签特定适配器，为冻结的图像编码器附加轻量记忆单元。
result: 在多个基准上实现了可扩展且低遗忘的持续学习。
conclusion: LADA提供了一种简单有效的标签级持续学习方案。
---

## Abstract
Continual learning with vision-language models like CLIP offers a pathway toward scalable machine learning systems by leveraging its transferable representations. Existing CLIP-based methods adapt the pre-trained image encoder by adding multiple sets of learnable parameters, with each task using a partial set of parameters. This requires selecting the expected parameters for input images during inference, which is prone to error that degrades performance. To address this problem, we introduce LADA (**L**abel-specific **ADA**pter). Instead of partitioning parameters across tasks, LADA appends lightweight, label-specific memory units to the frozen CLIP image encoder, enabling discriminative feature generation by aggregating task-agnostic knowledge. To prevent catastrophic forgetting, LADA employs feature distillation for seen classes, preventing their features from being interfered with by new classes. Positioned after the image encoder, LADA prevents gradient flow to the frozen CLIP parameters, ensuring efficient training. Extensive results show that LADA achieves state-of-the-art performance in continual learning settings.  The implementation code is available at [https://github.com/MaolinLuo/LADA](https://github.com/MaolinLuo/LADA).

---

## 论文详细总结（自动生成）

好的，根据提供的论文内容，以下是对论文《LADA: Scalable Label-Specific CLIP Adapter for Continual Learning》的结构化深入总结。

### **1. 论文的核心问题与整体含义**
*   **研究动机**: 预训练视觉语言模型（如CLIP）具有强大的可迁移表征，是构建可扩展持续学习系统的理想基础。然而，在持续学习场景中，模型在学习新任务时往往会遗忘旧知识，即“灾难性遗忘”。
*   **核心问题**: 现有基于CLIP的持续学习方法（如基于提示的方法或混合专家适配器）通常需要为不同任务划分或激活不同的参数子集。这导致在推理时，必须为输入图像选择正确的参数（如提示或适配器）。这种**参数选择过程容易出错（误分配）**，从而显著降低分类性能。此外，这些方法还面临**前向遗忘**（丧失预训练泛化能力）和**后向遗忘**（遗忘已学任务）的双重挑战。
*   **整体含义**: 本文旨在解决上述参数选择错误和灾难性遗忘问题，提出一种**无需参数选择、可扩展且高效**的CLIP适配器方法，以实现更稳定和更具可塑性的持续学习。

### **2. 论文提出的方法论**
*   **核心思想**: 引入**LADA (Label-Specific Adapter，标签特定适配器)**。该方法不划分特定于任务的参数，而是在**冻结的CLIP图像编码器之后**，为每个类别附加一组轻量级、标签特定的可学习向量（记忆单元）。通过这些记忆单元与图像特征的交互，将任务无关的知识聚合为具有判别性的标签特定特征，从而完全消除推理时的参数选择步骤。
*   **关键技术细节**:
    1.  **构建标签特定特征**:
        *   对于当前任务中的每个类别，使用K-Means聚类提取其图像特征的λ1个聚类中心，记为W，作为该类别的初始记忆单元。
        *   对于一张输入图像，其特征i通过与所有记忆单元W进行内积运算，生成标签特定的特征映射 φ(i)。
    2.  **训练与防止遗忘**:
        *   **训练当前任务**: 引入一个固定的（最近邻）分类器h，将构建的标签特定特征转换为分类logits，并计算交叉熵损失以优化当前任务的记忆单元W(k)。
        *   **缓解灾难性遗忘**:
            *   **冻结旧参数**: 训练第k个任务时，冻结前k-1个任务的记忆单元W(1)…W(k-1)。
            *   **特征蒸馏**: 为旧任务的每个类别存储少量（λ2个）特征原型，并在新任务训练时重放这些原型来计算蒸馏损失，防止旧类别特征被新类别干扰。
            *   **分布保留训练**: 为了更充分地保留旧任务的数据分布，引入高斯混合模型拟合旧任务的分布，并通过对原型进行高斯噪声增强来生成更多样的样本，从而计算更鲁棒的分类损失。
    3.  **整体框架**: LADA与一个经微调的文本编码器协同工作。训练时，联合优化来自文本编码器和LADA的损失。推理时，对于已见类别，加权融合来自文本特征和LADA特征的预测；对于未见类别，则直接使用原始CLIP的零样本分类结果。由于LADA置于冻结的图像编码器之后，梯度无需回传至编码器，因此训练高效。
*   **公式与算法流程（文字说明）**:
    *   **公式 (5)**: φk(i) = [W_k^1 i, ..., W_k^M_k i]，描述了如何通过记忆单元W和图像特征i的内积为任务k构建特征。
    *   **公式 (6)**: (h ◦ φ) (i)_ij = ϕ(W_i^j i) 1，表示使用固定分类器将内积转换为分类logits，其中ϕ是一个将内积映射到非负值的激活函数。
    *   **公式 (7) 和 (10)**: 分别为当前任务数据和旧任务增强原型的分类损失，用于联合优化。
    *   **算法流程**: 循环处理每个任务 → 为新类别初始化记忆单元 → 联合当前任务数据与旧任务增强原型 → 计算交叉熵损失（融合文本编码器与LADA的logits） → 更新当前任务记忆单元和文本编码器适配部分 → 冻结已更新的参数。

### **3. 实验设计**
*   **数据集/场景**: 实验基于**X-TAIL (Cross-domain Task-Agnostic Incremental Learning)** 基准，该基准包含10个不同类型的图像分类数据集：Aircraft, Caltech101, DTD, EuroSAT, Flowers, Food, MNIST, OxfordPet, StanfordCars, SUN397。该场景要求模型在无任务标识的情况下，增量学习这10个任务并区分所有100个类别。
*   **实验设置**: 论文评估了两种设置。
    *   **16-shot设置**: 每个类别随机抽取16个样本进行训练。
    *   **全量设置 (Full-shot)**: 使用数据集的全部原始训练样本，这是一个更具现实挑战性的场景。
*   **评估指标**: 采用 **Transfer**（衡量对未来任务的零样本泛化能力，反映前向遗忘）、**Average**（所有时间步的平均准确率，综合衡量稳定性和可塑性）和 **Last**（最终准确率，反映后向遗忘）三项指标。
*   **对比方法**: 与多种基线方法进行了比较，包括：
    *   经典的持续学习方法：LwF
    *   鲁棒微调方法：WiSE-FT
    *   基于CLIP的持续学习方法：ZSCL、MoE-Adapters
    *   当前先进的分类器扩展方法：Primal-RAIL、Dual-RAIL

### **4. 资源与算力**
*   文中提到，所有LADA的实验均在**单张NVIDIA 4090 GPU** 上完成。未提及具体的总训练时长。

### **5. 实验数量与充分性**
*   **实验数量**: 论文进行了相当数量的实验，主要包括：
    *   **主要结果对比**: 在两个不同设置（16-shot和全量）、两种不同任务顺序下，与多个基线方法进行了全面比较。
    *   **消融实验**: 系统地分析了基本框架 (BF)、LADA模块和分布保留训练 (DPT) 各自的作用。
    *   **超参数分析**: 详尽分析了LADA维度 (λ1) 和原型数量 (λ2) 对性能和计算开销（时间、显存、参数量）的影响。
    *   **深入分析**: 通过实验探讨了LADA为何能在某些任务上超越零样本CLIP的原因，对比了是否使用零样本CLIP选择器的效果。
*   **充分性与公平性**: 实验设计**充分且公平**。多种实验设置和全面的评估指标确保了结论的鲁棒性。详细的超参数和计算成本分析体现了方法的实用性。与最新且多样化的基线方法进行比较，增强了结果的说服力。

### **6. 论文的主要结论与发现**
*   LADA在两种X-TAIL设置下均**达到了最先进的性能**，在Transfer、Average和Last准确率上均超越了先前的方法。
*   LADA通过**消除参数选择环节**及**有效缓解前向和后向遗忘**，显著提升了持续学习的稳定性和可塑性。
*   LADA是**高效且可扩展的**，随着任务数量增加，其计算资源和参数量的增长温和可控。
*   消融研究证实，LADA模块和分布保留训练模块都对性能提升有积极贡献。
*   通过学到的知识增强已见类和未见类之间的区分能力，LADA在某些任务的迁移性能上甚至可以**超过原始零样本CLIP模型**。

### **7. 优点**
*   **方法优点**:
    *   **范式简洁有效**: 通过“标签特定记忆单元”的设计，完全摒弃了主流方法中易出错的参数选择步骤，思路新颖。
    *   **训练高效**: 结构置于冻结的图像编码器之后，无需进行代价高昂的反向传播。
    *   **遗忘抑制全面**: 结合参数冻结、特征蒸馏和创新的分布保留训练，有效应对了正向和反向遗忘。
    *   **可扩展性强**: 模型参数和计算开销随任务增长缓慢，具有良好的扩展性。
*   **实验设计优点**:
    *   **基准设置全面**: 同时评估了16-shot和更具挑战性的全量设置。
    *   **评估指标综合**: 采用了能分别衡量稳定性、可塑性及综合性能的多维度指标。
    *   **分析深入**: 不仅报告性能，还对方法的工作原理（如为何超越零样本性能）和资源开销进行了细致的分析。

### **8. 不足与局限**
*   **依赖于存储**: 为了防止遗忘，该方法需要为每个旧类别存储特征原型和协方差矩阵，这可能带来一定的存储开销，尤其是在类别极多的情况下。
*   **固定特征提取器**: 方法完全冻结了图像编码器，这在带来效率优势的同时，也可能限制了其在某些与预训练数据分布差异巨大的任务上的终极适应能力。
*   **未见类选择机制**: 虽然论文解释了其如何增强区分能力，但最终分类仍需在“已见类”和“未见类”预测结果间进行选择或融合，这一步骤的泛化能力极限未作深入探讨。
*   **论文未覆盖的实验**: 作者未提供在更大规模或有显著领域差异的预训练模型（如ViT-L/14）上的实验，其扩展性有待进一步验证。

（完）
