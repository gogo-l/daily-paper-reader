---
title: Rethinking Momentum Knowledge Distillation in Online Continual Learning
title_zh: 反思在线持续学习中的动量知识蒸馏
authors: "Nicolas Michel, Maorong Wang, Ling Xiao, Toshihiko Yamasaki"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=UW5nO9NGjt"
tags: ["query:continual"]
score: 9.0
evidence: 提出动量知识蒸馏方法，用于在线持续学习上的连续数据流
tldr: 针对在线持续学习中数据只能单次访问的严苛约束，本文重新思考知识蒸馏的应用，提出动量知识蒸馏方法，通过动量机制增强对旧任务知识的保留，在多个在线持续学习基准上取得最优结果，提升了知识蒸馏在该领域的实用性。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 615, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 528, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 553, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 551, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 666, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 860, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 778, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1748, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1579, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1682, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 909, \"height\": 535, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 627, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 614, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 592, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1775, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 776, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 537, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 539, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 891, \"height\": 630, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 625, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1081, \"height\": 2217, \"label\": \"Table\"}]"
motivation: 知识蒸馏在离线持续学习中广泛使用，但在线持续学习中因数据流单次约束而未被充分利用。
method: 提出动量知识蒸馏，设计直接而有效的方法来应对在线持续学习中的挑战。
result: 动量知识蒸馏在在线持续学习基准上达到了最先进性能，显著减少了遗忘。
conclusion: 动量知识蒸馏为在线持续学习提供了一种简单有效的知识保留策略。
---

## Abstract
Online Continual Learning (OCL) addresses the problem of training neural networks on a continuous data stream where multiple classification tasks emerge in sequence. In contrast to offline Continual Learning, data can be seen only once in OCL, which is a very severe constraint. In this context, replay-based strategies have achieved impressive results and most state-of-the-art approaches heavily depend on them. While Knowledge Distillation (KD) has been extensively used in offline Continual Learning, it remains under-exploited in OCL, despite its high potential. In this paper, we analyze the challenges in applying KD to OCL and give empirical justifications. We introduce a direct yet effective methodology for applying Momentum Knowledge Distillation (MKD) to many flagship OCL methods and demonstrate its capabilities to enhance existing approaches. In addition to improving existing state-of-the-art accuracy by more than $10\%$ points on ImageNet100, we shed light on MKD internal mechanics and impacts during training in OCL. We argue that similar to replay, MKD should be considered a central component of OCL. The code is available at https://github.com/Nicolas1203/mkd_ocl.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将对《Rethinking Momentum Knowledge Distillation in Online Continual Learning》这篇论文进行结构化、深入且客观的总结。

### 1. 论文的核心问题与整体含义

*   **研究领域与核心问题**：论文聚焦于**在线持续学习**，核心问题是神经网络在连续、不可重复访问的流式数据上学习时面临的**灾难性遗忘**。
*   **研究动机与背景**：
    *   **在线设定的严峻约束**：在OCL中，数据只能被模型看到一次，这是一个比离线持续学习更严苛的设定。
    *   **知识蒸馏的未被充分利用**：知识蒸馏在离线持续学习中已被广泛且成功地用于保留旧知识，但在OCL中却远未得到有效利用，尽管其潜力巨大。
    *   **现有方法的局限性**：当前OCL的最先进方法（SoTA）严重依赖**经验回放**策略。少数尝试将KD引入OCL的方法存在性能不佳、计算成本高、依赖任务边界信息等问题。
*   **论文的整体目标**：论文旨在系统地分析KD在OCL中应用所面临的挑战，并提出一种有效的方法（动量知识蒸馏），将其无缝集成到现有方法中，从而显著提升OCL的性能，并赋予KD在OCL中与经验回放同等重要的核心地位。

### 2. 论文提出的方法论

*   **核心思想：动量知识蒸馏**
    *   为了解决OCL中应用KD的挑战，论文提出使用**动量知识蒸馏**。其核心是引入一个“进化中的教师模型”，其权重不是固定的快照，而是学生模型权重的**指数移动平均**。
    *   **公式表示**：教师模型参数 ${\theta}_\alpha$ 的更新公式为 ${\theta_\alpha}(t) = \alpha * {\theta}(t) + (1 - \alpha) * {\theta_\alpha}(t - 1)$，其中 ${\theta}(t)$ 是时刻 $t$ 的学生参数，$\alpha$ 是控制更新速度的超参数。

*   **关键技术细节与流程**：
    1.  **OCL中KD的三大挑战识别**：
        *   **教师模型质量**：单次数据通过可能导致任务结束时模型并未充分训练，保存的快照作为教师模型质量低下。
        *   **教师模型数量**：为每个任务存储一个教师模型会导致存储开销不合理。
        *   **未知的任务边界**：在连续数据流中，任务切换时刻不明确，难以确定何时保存教师模型快照。
    2.  **可塑性-稳定性权衡控制**：
        *   超参数 $\alpha$ 提供了对模型可塑性与稳定性的精细控制。**低 $\alpha$ 值**使教师更新慢，更侧重稳定性；**高 $\alpha$ 值**使教师更新快，更侧重可塑性。
    3.  **模型学习**：损失函数由两部分组成，并引入多视图蒸馏：
        *   **交叉熵损失** $L_{CE}$：用于学习当前任务。
        *   **蒸馏损失**：计算教师和学生模型输出之间的KL散度，并乘以一个依赖于$\alpha$的权重 $\lambda_\alpha$。
        *   **多视图蒸馏**：对输入数据 $X$ 及其数据增强版本 $\hat{X}$ 分别计算蒸馏损失并求和，以增强效果。公式为$L_{MKD}(X, Y) = L_{CE}(\hat{X}, Y) + \frac{\lambda_\alpha}{2} \text{KL}(T_\alpha(X), S(\hat{X})) + \frac{\lambda_\alpha}{2} \text{KL}(T_\alpha(\hat{X}), S(\hat{X}))$。
    4.  **模型估计**：在推理阶段，不单独使用学生或教师模型，而是取两者权重的**简单平均**作为最终模型参数，即 $\theta^\star = \frac{\theta_S + \theta_T}{2}$。
    5.  **超参数关系**：研究发现 $\alpha$ 和 $\lambda_\alpha$ 之间存在强关联，最优 $\lambda_\alpha$ 近似遵循 $\lambda_\alpha = \frac{9}{2} * \log_{10}(\alpha) + \frac{29}{2}$ 的关系，简化了调参。

### 3. 实验设计

*   **数据集**：在四个不同规模的标准图像分类数据集上进行了实验：**CIFAR-10** (拆分为5个任务)、**CIFAR-100** (拆分为10个任务)、**Tiny-ImageNet** (拆分为20个任务) 和 **ImageNet-100** (拆分为10个任务)。
*   **实验场景**：
    *   **清晰任务边界**：传统的任务顺序切换设置。
    *   **模糊任务边界**：更现实的场景，任务间存在数据平滑过渡的阶段。
*   **对比基准方法**：论文将提出的MKD方法与多个OCL领域的旗舰方法结合并对比，包括：
    *   **基础回放方法**：ER
    *   **SoTA回放方法**：DER++, ER-ACE, DVC, OCM, GSA, PCR
    *   **其他KD/EMA方法**：SDP, Temporal Ensembles
*   **评价指标**：主要采用**最终平均准确率**和**反向迁移**。
*   **模型与记忆管理**：一致使用 **ResNet-18** 作为骨干网络，采用蓄水池采样进行记忆管理。

### 4. 资源与算力

*   论文在实验部分明确提到了使用了 **RTX A5000** 和 **V100** GPU 进行训练，并在附录中通过图示（Figure 12）展示了在V100 GPU上训练CIFAR-100的不同方法所消耗的时间。
*   **未明确说明**：具体的GPU总数量、训练单个实验的精确时长或总算力消耗并未在提供的文本中详细说明。

### 5. 实验数量与充分性

*   **实验规模相当庞大**，包含：
    *   **4个数据集** × **多种记忆库大小** × **清晰/模糊两种边界设定** × **9种以上的基线方法及其与MKD的结合**，构成了数百组核心对比实验。
    *   专门设计了多项**消融研究**：包含验证最终权重平均策略、多视图蒸馏效果、超参数 $\alpha$ 和 $\lambda_\alpha$ 之间的关系等。
    *   深入分析了MKD对OCL内在机理的影响，包括**任务近因偏差、最后一层偏差、特征漂移、特征辨别力**和**反向迁移**，并提供了混淆矩阵、t-SNE可视化等定性/定量证据。
*   **充分性与公平性**：实验设计**非常充分和系统**。它不仅通过大规模对比展示了方法的有效性，还通过深入的机理分析揭示了其成功的原因。在与所有基线对比时，均使用ResNet-18和蓄水池采样，并在相同设定下进行了小范围超参数搜索，**对比公平客观**。

### 6. 论文的主要结论与发现

*   **方法有效性**：提出的MKD方法可以**无缝、即插即用**地集成到多种现有OCL方法中，并普遍带来**显著的性能提升**（在ImageNet-100上最高可提升超过10%的绝对准确率），同时还能降低标准差，使训练更稳定。
*   **设定鲁棒性**：MKD在**清晰和模糊任务边界**两种设定下均持续有效，证明了其处理未知任务边界的强大能力。
*   **机理揭示**：
    *   MKD能有效**缓解任务近因偏差**和**最后一层偏差**。
    *   MKD能显著**减少特征漂移**，提升特征的**辨别力**。
    *   MKD能显著**改善反向迁移**性能，意味着模型在学习新任务时仍能持续提升对旧任务的表现。
*   **核心论点**：论文有力地证明了**动量知识蒸馏应被视为在线持续学习的一个核心组件**，其地位与经验回放同等重要。

### 7. 优点

*   **问题洞察深刻**：明确、精准地指出了KD在OCL中失败的根本原因，即教师质量、数量和任务边界三大挑战。
*   **方法论简洁而强大**：基于EMA的MKD方案简单、计算高效、不依赖特定网络架构，并且能提供精细的“可塑性-稳定性”控制。
*   **即插即用的通用性**：方法可以轻松地作为附加模块与几乎所有基于回放的现有OCL方法结合，无需对其进行复杂修改，实用性极强。
*   **实验与理论分析并重**：不仅在多个基准上取得了显著性能提升，还通过一系列精心设计的分析和可视化实验，深刻揭示了MKD为何有效的内在机理，令人信服。
*   **解决现实问题**：特别关注并成功解决了“模糊任务边界”这一更符合真实应用场景但较少被研究的难题。

### 8. 不足与局限

*   **超参数 $\alpha$ 的敏感性**：虽然论文给出了选择指导，但最优 $\alpha$ 值仍然依赖于网格搜索，且为一个全局固定值。这可能是实践中需要调优的成本，文中未深入探讨在任务难度动态变化时自适应调整 $\alpha$ 的可能性。
*   **任务边界推断**：在模糊边界设定下，对比方法OCM需要推断任务边界，论文使用了一种相对简单的启发式规则（新类别出现+固定迭代间隔），这可能影响OCM在该设定下的表现，虽然这更凸显了MKD不依赖边界的优势，但也可能引入对比偏差。
*   **应用场景限制**：方法建立在类别增量学习（Class-IL）和存在记忆库的回放策略之上，其有效性在无记忆库的极端设定或任务增量学习（Task-IL）等其他OCL场景下有待验证。
*   **教师模型的作用**：实验显示，单独使用教师模型进行推理的效果甚至不如学生模型，其核心价值似乎是通过知识蒸馏过程来正则化学生模型。这种机制的特殊性可以进一步探讨。

（完）
