---
title: Rethinking the Stability-Plasticity Trade-off in Continual Learning from an Architectural Perspective
title_zh: 从架构角度重新思考持续学习中的稳定性-可塑性权衡
authors: "Aojun Lu, Hangjie Yuan, Tao Feng, Yanan Sun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yO95ALeoGw"
tags: ["query:continual"]
score: 10.0
evidence: 该论文从架构层面分析了持续学习中的稳定性-可塑性权衡，发现更深网络具有更好的可塑性，更宽网络具有更好的稳定性。
tldr: 该论文针对持续学习中稳定性-可塑性权衡问题，从网络架构角度进行了深入分析。研究发现，在参数数量相同的条件下，增加网络深度有利于提升可塑性（学习新知识），而增加宽度则增强稳定性（保留旧知识）。这些见解为设计更高效的持续学习模型提供了架构层面的指导原则。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1702, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1692, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1773, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 932, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1786, \"height\": 1239, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1737, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 1045, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1695, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 812, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1072, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1505, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1061, \"height\": 299, \"label\": \"Table\"}]"
motivation: 现有持续学习方法多关注参数层面的权衡，忽视了网络架构对稳定性和可塑性的影响。
method: 通过在等参数量约束下对比不同深度和宽度的网络，分析其在持续学习中的稳定性和可塑性表现。
result: 深度网络表现出更强的可塑性，宽度网络则保持更好的稳定性。
conclusion: 架构设计是解决持续学习稳定性-可塑性困境的关键因素，为模型设计提供了新思路。
---

## Abstract
The quest for Continual Learning (CL) seeks to empower neural networks with the ability to learn and adapt incrementally. Central to this pursuit is addressing the stability-plasticity dilemma, which involves striking a balance between two conflicting objectives: preserving previously learned knowledge and acquiring new knowledge. While numerous CL methods aim to achieve this trade-off, they often overlook the impact of network architecture on stability and plasticity, restricting the trade-off to the parameter level. In this paper, we delve into the conflict between stability and plasticity at the architectural level. We reveal that under an equal parameter constraint, deeper networks exhibit better plasticity, while wider networks are characterized by superior stability. To address this architectural-level dilemma, we introduce a novel framework denoted Dual-Arch, which serves as a plug-in component for CL. This framework leverages the complementary strengths of two distinct and independent networks: one dedicated to plasticity and the other to stability. Each network is designed with a specialized and lightweight architecture, tailored to its respective objective. Extensive experiments demonstrate that Dual-Arch enhances the performance of existing CL methods while being up to 87% more compact in terms of parameters.

---

## 论文详细总结（自动生成）

# 论文总结：从架构视角重新思考持续学习中的稳定性-可塑性权衡

### 1. 核心问题与整体含义
- **核心问题**：持续学习（Continual Learning, CL）的核心挑战是平衡 **稳定性（保留旧知识）** 和 **可塑性（学习新知识）** ，即“稳定性-可塑性困境”。现有方法多在参数层面（如正则化、动态扩展）优化这一权衡，而 **忽略了网络架构本身对稳定性和可塑性的内在影响**。
- **研究动机**：论文发现，在总参数量大致相等的约束下，神经网络的架构设计（深度 vs. 宽度）本身就蕴含着稳定性与可塑性的冲突。具体而言：
    - **更深**的网络倾向于具有更好的 **可塑性**（新任务准确率更高），但 **稳定性较差**（遗忘更严重）。
    - **更宽（且更浅）** 的网络则倾向于具有更好的 **稳定性**（遗忘更少），但 **可塑性较差**。
- **整体含义**：稳定性和可塑性的权衡不仅存在于参数优化层面，更 **根植于网络架构设计** 之中。这一发现为从架构设计角度解决持续学习困境开辟了新途径。

### 2. 方法论
- **核心思想**：基于上述发现，论文提出一个名为 **Dual-Arch** 的即插即用框架。该框架**利用两个架构专用的独立网络来分别负责可塑性和稳定性**，并通过知识蒸馏将新学知识从可塑性网络转移到稳定性网络，从而在架构层面实现优势互补。
- **关键技术细节**：
    - **可塑性网络（Plastic Learner）**：采用**深而窄**的架构设计，负责在当前新任务数据上进行训练，专注于提取新知识，允许遗忘旧知识。其训练目标仅为当前任务的交叉熵损失。
    - **稳定性网络（Stable Learner）**：采用**宽而浅**的架构设计，作为主模型。其训练目标由三部分组成：
        1. 当前任务的 **交叉熵损失**（硬标签）。
        2. 与可塑性网络输出之间的 **知识蒸馏损失**（软标签），用于从可塑性网络吸收新知识。
        3. 特定CL方法的 **正则化损失**，用于保留旧知识。
    - **架构设计实例**：以ResNet-18为基础，Stable Network通过减少残差块数量并增大分类器前特征图尺寸来实现“宽而浅”；Plastic Network则保持深度但大幅减少初始通道数来实现“深而窄”。两者参数量均得到控制。
    - **算法流程**：
        1. 对于每个新任务，首先仅用交叉熵损失训练**可塑性网络**直至收敛。
        2. 冻结训练好的可塑性网络，将其作为**教师模型**。
        3. 使用复合损失训练**稳定性网络**，通过知识蒸馏从教师模型中学习新知识。
        4. 重复上述步骤。
- **公式表示（文字描述）**：
    - 可塑性网络损失： \( L_{\text{plastic}} = L_{CE} \)
    - 稳定性网络损失： \( L_{\text{stable}} = \alpha L_{CE} + (1 - \alpha)L_{KD} + L_{CL} \)
    - 其中，\( L_{KD} \) 是教师模型（可塑性网络）与学生模型（稳定性网络）之间的KL散度。

### 3. 实验设计
- **数据集与场景**:
    - **CIFAR100** 和 **ImageNet100**。
    - **任务划分**：每个数据集被划分为两种任务序列，构建四个基准：将100个类分为10个任务（每任务10类）和20个任务（每任务5类）。
    - **主要场景**：聚焦于最通用和现实的 **类别增量学习（Class-Incremental Learning）**，推理时任务ID未知。
    - **扩展场景**：在任务边界模糊的 **泛化类别增量学习（GCIL）** 和更长的任务序列（CIFAR100/50）上也进行了验证。
- **对比方法**：
    - **5种典型的CL基线方法**：iCaRL、WA、DER、Foster、MEMO（涵盖重放、正则化、基于架构三大类）。
    - **即插即用对比**：将Dual-Arch框架与上述5种方法结合，对比它们使用 **原始ResNet-18** 的性能。
    - **架构基线**：与专门为CL设计单一友好架构的方法 **ArchCraft** 进行比较。
    - **架构验证**：将框架迁移到Vision Transformer（SepViT）上进行验证。
- **评估指标**：
    - **最终准确率（Last Accuracy, LA）** 和 **平均增量准确率（Average Incremental Accuracy, AIA）** 衡量总体性能。
    - **平均遗忘（Average Forgetting, AF）** 和 **最终平均遗忘（Final Average Forgetting, FAF）** 衡量稳定性。
    - **新任务平均准确率（Average Accuracy on New tasks, AAN）** 衡量可塑性。

### 4. 资源与算力
- **未明确说明**：论文正文未明确提及所使用的GPU型号、数量及具体训练次数。
- **训练时长对比**：论文比较了Dual-Arch与基线的训练时间（分钟），指出由于需要顺序训练两个网络，训练时间有所增加（约为基线的1.39到1.77倍）。
- **计算量对比**：论文以FLOPs衡量计算开销，指出其设计的Stable-Net和Plastic-Net的**总FLOPs低于ResNet-18基线**，且推理时仅使用Stable-Net，故推理阶段计算效率更高。

### 5. 实验数量与充分性
- **实验丰富度**：论文进行了大量且多维度实验，较为充分。
    - **主体实验**：在4个基准（2个数据集 × 2种任务划分）上，对5种主流CL方法进行了即插即用测试，并对比了单一架构基线。总计至少 \( 4 \times (5+1+1) \) 组核心对比。
    - **消融实验**：系统研究了双网络和专用架构两大核心设计的作用，通过移除其中一个或交换架构来验证其有效性。
    - **效率分析**：专门分析了参数效率、计算效率（FLOPs）和训练时间。
    - **专项分析**：深入分析了框架对稳定性-可塑性权衡的平衡作用，并通过混淆矩阵可视化了其对任务近期偏差的缓解效果。
    - **扩展验证**：在MLP、Vision Transformer架构，以及更复杂的GCIL、更多任务数（50个）场景下验证了结论的泛化能力。
- **客观性与公平性**：实验设置严谨，使用统一的开源库（PyCIL）和超参数，固定内存大小，遵循标准实践，对比公平。

### 6. 主要结论与发现
- **架构层面存在稳定性-可塑性困境**：在等参预算下，更深网络更具可塑性，更宽网络更具稳定性。
- **双架构框架有效**：提出的Dual-Arch通过结合专用于可塑性和稳定性的两个轻量网络，成功从架构层面平衡了这一困境。
- **性能与效率双重提升**：Dual-Arch作为即插即用组件，能显著提升多种现有CL方法的性能（LA最高提升超10%），同时参数量可减少最高 **87%**，参数效率极高。
- **有效缓解任务近期偏差**：Dual-Arch能有效减少将旧类样本误分为新类的“任务近期偏差”，这是其提升性能的内在原因之一。
- **结论具有架构泛化性**：该结论不仅适用于ResNet，在MLP和Vision Transformer上也同样成立。

### 7. 优点
- **新颖的视角**：从参数层面扩展到架构层面重新审视稳定性-可塑性权衡，为持续学习研究提供了新维度。
- **方法简便有效且通用**：Dual-Arch作为一个不依赖特定CL算法的**即插即用组件**，可与多种现有方法无缝结合，通用性强。
- **高效性突出**：在显著提升性能的同时，大幅降低了参数量，尤其适合资源受限环境。
- **实验扎实全面**：覆盖了多种主流方法、数据集、任务划分，并通过丰富的消融、分析和扩展实验，论证充分可信。
- **可解释性强**：通过遗忘曲线、准确率曲线和混淆矩阵，清晰解释了框架如何结合两类架构的优势、缓解任务近期偏差。

### 8. 不足与局限
- **训练时间增加**：由于需要顺序训练两个模型，导致训练时间相比单模型基线有显著增加（约1.4至1.8倍），是其主要的计算代价。
- **架构设计启发式**：具体的“深/窄”和“宽/浅”架构是基于手工修改和标准化基础网络（ResNet-18）得出的，其最优设计可能依赖基础模型，缺乏自动搜索或理论上的最优性保证。
- **应用场景聚焦**：主要验证集中在图像分类的类别增量学习上，虽然覆盖了最现实的场景，但在其他持续学习范式（如任务增量、领域增量）或任务（如分割、检测）上的直接效果有待进一步检验。

（完）
