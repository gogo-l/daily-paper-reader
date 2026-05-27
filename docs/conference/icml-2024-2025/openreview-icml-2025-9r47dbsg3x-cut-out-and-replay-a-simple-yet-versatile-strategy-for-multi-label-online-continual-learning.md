---
title: "Cut out and Replay: A Simple yet Versatile Strategy for Multi-Label Online Continual Learning"
title_zh: 剪切与重放：一种简单通用的多标签在线持续学习策略
authors: "Xinrui Wang, Shao-Yuan Li, Jiaqiang Zhang, Songcan Chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=9R47dBSG3x"
tags: ["query:continual"]
score: 9.0
evidence: 提出剪切重放策略用于多标签在线持续学习，处理灾难性遗忘、标签缺失和类别失衡
tldr: 多标签在线持续学习面临着遗忘、标签缺失和类别不平衡等挑战，现有方法忽视了标签特定区域的识别。本文利用输入数据的内在结构信息定位相关区域，设计剪切与重放策略进行增量特征学习。实验表明该方法在多个多标签持续学习数据集上性能领先，有效缓解遗忘并适应在线场景。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 818, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1754, \"height\": 741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 715, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 833, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1696, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1654, \"height\": 414, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1684, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1684, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 799, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 767, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1691, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1327, \"height\": 617, \"label\": \"Table\"}]"
motivation: 现有多标签在线持续学习方法忽略标签特定区域识别与特征学习，难以应对在线增量监督。
method: 利用数据内在结构定位标签区域，采用剪切与重放机制进行在线增量学习。
result: 在多标签持续学习基准中，该方法有效对抗灾难性遗忘，且能处理缺失标签和类别不均。
conclusion: 剪切重放策略为多标签在线持续学习提供了简单而有效的解决方案。
---

## Abstract
Multi-Label Online Continual Learning (MOCL) requires models to learn continuously from endless multi-label data streams, facing complex challenges including persistent catastrophic forgetting, potential missing labels, and uncontrollable imbalanced class distributions. While existing MOCL methods attempt to address these challenges through various techniques, \textit{they all overlook label-specific region identifying and feature learning} - a fundamental solution rooted in multi-label learning but challenging to achieve in the online setting with incremental and partial supervision. To this end, we first leverage the inherent structural information of input data to evaluate and verify the innate localization capability of different pre-trained models. Then, we propose CUTER (CUT-out-and-Experience-Replay), a simple yet versatile strategy that provides fine-grained supervision signals by further identifying, strengthening and cutting out label-specific regions for efficient experience replay. It not only enables models to simultaneously address catastrophic forgetting, missing labels, and class imbalance challenges, but also serves as an orthogonal solution that seamlessly integrates with existing approaches. Extensive experiments on multiple multi-label image benchmarks demonstrate the superiority of our proposed method. The code is available at \href{https://github.com/wxr99/Cut-Replay}{https://github.com/wxr99/Cut-Replay}

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：
    该论文聚焦于**多标签在线持续学习** 这一新兴且更具挑战性的范式。与传统的单标签场景不同，MOCL 要求模型从无限的多标签数据流中持续学习，这带来了三个相互交织的核心难题：
    *   **灾难性遗忘**：学习新任务时，模型会迅速遗忘先前学到的知识。
    *   **标签缺失（虚假负样本）**：在任意时刻，数据流中的样本只标注了当前任务相关的标签，而图像中可能含有的旧任务或未来任务的对象则未被标注，这些未被标注的类别成为了误导模型的“虚假负样本”，加剧了遗忘。
    *   **不可控的类别不平衡**：数据流中的类别天然遵循长尾分布，模型容易偏向头部类而忽略尾部类，尤其当头部类和尾部类共现于同一图像时，情况更为复杂。

*   **核心问题与意义**：
    论文指出，现有 MOCL 方法试图通过各种技巧（如伪标签、知识蒸馏、重采样策略）来缓解上述问题，但它们都**忽略了多标签学习中的一个根本性解决方案——识别和学习标签特定的区域与特征**。然而，在在线、增量、部分监督的设置下，实现这一点极具挑战性。因此，本文旨在从根本上填补这一空白，通过挖掘和利用预训练模型天生的目标定位能力，来同时应对 MOCL 中的遗忘、标签缺失和类别失衡三大挑战。

### 2. 论文提出的方法论：CUTER

*   **核心思想**：
    提出了一种名为 **CUTER（剪切与经验重放）** 的策略，其核心是“剪切-重放”：首先在图像中精准定位并裁剪出与单个给定标签对应的物体区域，然后将这些局部区域（而非整张图像）存入记忆缓冲区进行重放。这样做的优势在于：
    *   **避免标签共现干扰**：将多标签分类问题转化为多个单标签子图像分类问题。
    *   **缓解类别不平衡**：在存储时，可以直接控制每个物体类别在缓冲区中的数量，实现高效的类别平衡。
    *   **提供细粒度监督**：为经验重放提供了像素级别的、更精确的监督信号。

*   **关键技术细节与算法流程**：
    CUTER 方法由三个关键步骤组成：
    1.  **零样本定位能力评估**：
        *   为了选择合适的预训练模型来执行“剪切”，论文提出了一种**无需标注的评估协议**。
        *   受图论和谱聚类启发，论文发现**图拉普拉斯矩阵的菲德勒值**（第二小特征值）可以作为衡量模型零样本定位能力的有效指标。菲德勒值越低，意味着由图像特征块构建的图的可分性越强。
        *   计算少量下游数据集上特征图的平均菲德勒值，可以有效评估不同预训练模型的定位潜力，从而选择最适合的模型（如 DINO 系列）。
    2.  **选择性重放（标签-区域匹配）**：
        *   对于输入的图像，使用基于 Normalized Cut 的迭代方法 **MaskCut** 生成多个候选的物体区域掩码，并将其裁剪为子图像。
        *   将这些子图像重新输入分类模型，根据预测结果建立标签-区域的精确对应关系。筛选条件为：`子图像预测置信度 > τ` 且 `次大置信度 < 0.5`，确保每个裁剪区域只对应一个高置信度标签。
        *   存储时，根据类别频率采用不同的置信度阈值（`τ1`, `τ2`），并结合一种改进的、更简洁的**重平衡蓄水池采样策略**，将子图像及其对应标签存入缓冲区。该策略计算复杂度更低，且类别平衡效果更优。
    3.  **定位感知的特征正则化**：
        *   为了缓解模型自身定位能力在持续学习过程中的退化（类似遗忘），论文提出从图信号的角度进行正则化。
        *   **核心定理**：论文证明了，如果一个特征图的邻接矩阵可以分解为理想块对角矩阵和一个噪声矩阵，那么其菲德勒值可以被噪声矩阵的范数所上界。
        *   基于此，通过在分类损失（非对称损失）上增加一个**低秩（核范数）正则项**，来约束特征图的邻接矩阵向理想块对角结构靠拢，从而持续增强和巩固模型的定位能力。

### 3. 实验设计

*   **数据集与场景**：
    实验在三个标准的多标签图像基准数据集上进行：
    *   **PASCAL VOC 2007**：20 个类别，划分为 5 个任务（每任务 4 类）。
    *   **MS-COCO 2014**：80 个类别，划分为 8 个任务（每任务 10 类）。
    *   **NUS-WIDE**：81 个类别，划分为 8 个任务。

*   **对比基准方法**：
    对比了来自不同领域的 10 种先进方法，以确保全面性：
    *   **在线持续学习方法**：RS, GSS, iCarl, NsCE (将其修改为适配多标签场景)。
    *   **多标签类增量学习方法**：KRT, APPLE。
    *   **多标签在线持续学习方法**：PRS, OCDM, AGCN, AGCN++。

*   **评估指标**：
    *   平均精度均值（mAP）。
    *   每类 F1 分数（CF1）和 整体 F1 分数（OF1）。
    *   报告“跨任务平均性能”（已见类别上的平均）和“最终性能”（所有类别上的表现），以评估抗遗忘能力。

### 4. 资源与算力

*   **论文中未明确说明**：
    论文正文及附录中**未提及** 具体的 GPU 型号、数量、训练时长或总计算开销等与算力相关的信息。仅在吞吐量分析部分（Appendix E.2）提到，CUTER 因需要多轮 MaskCut 操作和核范数计算，其模型吞吐量低于简单的经验重放方法，指出在计算开销和性能之间存在权衡。

### 5. 实验数量与充分性

*   **实验数量**：
    论文设计了较为全面的实验，大致包括：
    1.  **主实验**：在三个数据集上与 10 种方法对比，包含平均和最终性能的多个指标。
    2.  **预训练模型分析**：评估了 DINO v1/v2, MoCo v3, MAE, iBOT 等 6+ 种预训练模型的定位能力。
    3.  **消融实验**：系统验证了“剪切-重放”、“重平衡采样”、“低秩正则化”等各个组件的贡献。
    4.  **部件级/集成实验**：验证 CUTER 作为即插即用组件与 KRT、AGCN 等方法的兼容性。
    5.  **正则化项对比**：比较了低秩、稀疏、平滑三种不同正则化方案的效果。
    6.  **敏感性分析**：分析了正则化系数 `α` 及置信度阈值 `τ1` 和 `τ2` 对性能的影响。
    7.  **骨干网络分析**：探索了 ViT-S/B/T 及 ResNet50 等不同架构和预训练策略下的表现。

*   **充分性与公平性**：
    *   **充分性**：实验覆盖了多个主流数据集、多种方法类型，并通过消融、集成和敏感性分析深入探究了方法的内在机制，实验设计较为充分。
    *   **公平性**：论文力求公平比较，为所有方法（除特定方法 KRT 外）统一了 Vision Transformer 骨干网络（ViT-S/16）和预训练权重；对单标签 OCL 方法进行了适配以用于多标签场景；且所有实验均重复五次并报告均值和标准差。但将某些方法（如 KRT）排除在统一 ViT 骨干之外，可能引入轻微的不公平比较。

### 6. 论文的主要结论与发现

*   **性能卓越**：CUTER 在所有三个基准数据集上均显著优于现有最先进方法，尤其在衡量抗遗忘能力的“最终性能”指标上提升巨大。
*   **本质有效性**：通过识别和重放标签特定区域，可以从根本上有效缓解多标签在线持续学习中的灾难性遗忘、标签缺失和类别不平衡问题。
*   **预训练模型评估**：基于图论的**平均菲德勒值** 是一个无需标注、有效评估预训练模型零样本定位能力的指标。多尺度裁剪一致性训练（如 DINO）极大地增强了这种能力。
*   **正则化有效性**：基于图谱理论的**低秩正则化** 能有效维持甚至增强模型在持续学习过程中的定位能力，从而提升下游任务性能。
*   **方法普适性**：CUTER 不仅是一个独立方法，也可以作为一个正交的、即插即用的组件，无缝集成到现有方法（如 KRT, AGCN）中并提升其性能。

### 7. 优点

*   **视角新颖**：首次将标签特定学习的思想引入多标签在线持续学习领域，直击问题本质。
*   **理论支撑扎实**：巧妙地运用了图论和谱聚类理论，不仅用于评估预训练模型，还用于指导设计维持定位能力的正则化项，并有定理证明。
*   **方法简洁有效，通用性强**：“剪切-重放”策略简单直观，且被证明可以作为一个正交组件与多种现有方法结合，展现出强大的通用性。
*   **实验设计全面，说服力强**：实验覆盖了多个数据集、大量先进对比方法、深入的消融和组件分析，并通过吞吐量、可视化等多维度验证，结论坚实可靠。

### 8. 不足与局限

*   **计算开销较大**：论文承认，多轮 MaskCut 操作和核范数计算带来了额外的计算负担，导致模型吞吐量下降，这可能限制了其在要求极低延迟或资源极度受限的在线场景中的应用。
*   **架构依赖性强**：方法高度依赖于 Vision Transformer 的图块（patch）结构来构建图，虽然也可用于 ResNet 等 CNN 架构，但性能提升相对较弱，泛化性受到一定限制。
*   **剪切策略的局限**：论文中的剪切策略依赖 MaskCut，这是一种无监督方法，其定位的精确度和召回可能并非完美，尤其在复杂场景下可能出错，从而引入噪声区域。
*   **理论分析假设**：低秩正则化的有效性依赖于“理想邻接矩阵是块对角的”这一假设，在真实复杂图像中，这一假设可能不完全成立，但其实际效果仍然显著。

（完）
