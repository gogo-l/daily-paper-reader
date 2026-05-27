---
title: "Cut out and Replay: A Simple yet Versatile Strategy for Multi-Label Online Continual Learning"
title_zh: 剪切与重放：一种简单但多用途的多标签在线持续学习策略
authors: "Xinrui Wang, Shao-Yuan Li, Jiaqiang Zhang, Songcan Chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=9R47dBSG3x"
tags: ["query:continual"]
score: 9.0
evidence: 多标签在线持续学习的剪切重放策略，缓解遗忘
tldr: 多标签在线持续学习面临灾难性遗忘、标签缺失和类别不平衡等复合挑战。现有方法忽视了标签特定区域识别这一关键。本文提出剪切-重放策略，利用输入数据内在结构定位并突出标签相关区域，通过选择性重放巩固知识。实验表明，该方法在多种多标签数据流基准上有效降低了遗忘，提升了在线增量学习性能，为复杂持续学习场景提供了一种简单实用的解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 818, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1754, \"height\": 741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 715, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 833, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1696, \"height\": 693, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-9r47dbsg3x/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1654, \"height\": 414, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1684, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1684, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 799, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 767, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1691, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-9r47dbsg3x/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1327, \"height\": 617, \"label\": \"Table\"}]"
motivation: 多标签在线持续学习同时受灾难性遗忘、标签缺失和类别失衡困扰。
method: 提出剪切-重放策略，利用标签特定区域定位和特征学习缓解遗忘。
result: 实验表明方法在多种基准上有效降低遗忘，性能鲁棒且简单通用。
conclusion: 基于结构信息的剪切重放为多标签持续学习提供有效新思路。
---

## Abstract
Multi-Label Online Continual Learning (MOCL) requires models to learn continuously from endless multi-label data streams, facing complex challenges including persistent catastrophic forgetting, potential missing labels, and uncontrollable imbalanced class distributions. While existing MOCL methods attempt to address these challenges through various techniques, \textit{they all overlook label-specific region identifying and feature learning} - a fundamental solution rooted in multi-label learning but challenging to achieve in the online setting with incremental and partial supervision. To this end, we first leverage the inherent structural information of input data to evaluate and verify the innate localization capability of different pre-trained models. Then, we propose CUTER (CUT-out-and-Experience-Replay), a simple yet versatile strategy that provides fine-grained supervision signals by further identifying, strengthening and cutting out label-specific regions for efficient experience replay. It not only enables models to simultaneously address catastrophic forgetting, missing labels, and class imbalance challenges, but also serves as an orthogonal solution that seamlessly integrates with existing approaches. Extensive experiments on multiple multi-label image benchmarks demonstrate the superiority of our proposed method. The code is available at \href{https://github.com/wxr99/Cut-Replay}{https://github.com/wxr99/Cut-Replay}

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
*   论文背景是多标签在线持续学习（MOCL），模型需要从持续到达的多标签数据流中不断学习。
*   核心挑战包括灾难性遗忘（catastrophic forgetting）、普遍存在的标签缺失（missing labels）以及不可控的类别不平衡（class imbalance）。
*   现有方法忽略了标签特定区域（label-specific regions）的识别与特征学习，而这正是多标签学习的根本解决思路，但在在线场景下由于增量式部分监督而难以实现。
*   本文提出 CUTER（CUT-out-and-Experience-Replay），一种利用输入数据内部结构信息定位、增强并剪切标签特定区域进行高效经验重放的简洁策略，旨在同时应对遗忘、标签缺失和类别不平衡。

## 2. 论文提出的方法论
*   **零样本定位能力评估**：借助图谱理论，提出基于平均 Fiedler 值（图拉普拉斯矩阵的第二小特征值）的评估指标，无需标注框即可评估预训练模型的无监督物体定位潜力。Fiedler 值越低，特征图连接越弱，更利于分割。
*   **选择性重放（Cut‑out‑and‑Replay）**：
    - 使用选定的预训练模型（如 DINO）+ 多轮 MaskCut 生成二值掩码，裁剪出候选前景物体。
    - 将裁剪后的子图送入分类器，仅保留满足以下条件的区域：最高预测分数 > τ 且次高预测分数 < 0.5（单标签高置信度）。
    - 为平衡类别分布，针对低频类别采用更低阈值 τ₁，高频类别用 τ₂，并以改进的平衡蓄水池采样（基于类别频次的移除机制）存入记忆缓冲区。
    - 最终训练时，将原始样本的不对称损失与缓冲区重放样本的损失相结合。
*   **定位感知特征正则化**：
    - 发现持续学习中模型的定位能力会退化（Fiedler 值升高），提出通过低秩正则化稳定特征图的结构。
    - 理论证明：通过约束特征图相似度邻接矩阵 A 的核范数 ∥A∥∗，可以间接减小噪声扰动矩阵 ϵ 的范数，从而压低 Fiedler 值。
    - 实际训练目标：L = L_asy(f, x, y) + α∥A∥∗。

## 3. 实验设计
*   **数据集**：PASCAL VOC 2007（20类）、MS-COCO 2014（80类）、NUS-WIDE（81类，重新抓取版）。类别按名称的字典序分割成任务，如VOC分成5任务×4类，COCO分成8任务×10类，NUS-WIDE首任务11类后续各10类。
*   **对比基线**：
    - 单标签在线持续学习（OCL）方法：RS, GSS, iCaRL, NsCE（修改分类器与损失以适应多标签）。
    - 多标签类增量学习（MLCIL）方法：KRT, APPLE（主要为离线设定，迁移至在线）。
    - 多标签在线持续学习（MOCL）方法：PRS, OCDM, AGCN, AGCN++。
*   **评估指标**：跨任务平均性能（Average mAP, CF1, OF1）和最终全部类别的性能（Last mAP, CF1, OF1）。
*   **实现细节**：
    - 骨干网络：ImageNet-21k 预训练的 ViT-S/16 (DINO v1)为主，除KRT外均统一。
    - 优化器：AdamW，学习率1e-4，权重衰减1e-4。
    - 记忆缓冲区大小：1000×224×224×3。每项实验重复5次，报告均值和标准差。

## 4. 资源与算力
*   论文未明确提供GPU型号、数量、训练时长等算力信息。仅提及部分方法（如CUTER）因多轮 MaskCut 无法并行而吞吐量较低（Figure 8），并指出未来将开发加速技术。因此，算力消耗细节缺失。

## 5. 实验数量与充分性
*   **主要对比实验**：3个数据集 × 约10种基线方法，涵盖各类指标，是充分的。
*   **消融实验**：
    - 不同正则化项（低秩、稀疏、平滑）的影响（Table 3）。
    - CUTER作为即插即用模块与PRS、OCDM、KRT、AGCN集成的效果（Table 5）。
    - 组件拆分（基准、仅剪切重放、加正则、固定骨干等）的逐步增益（Table 6）。
*   **敏感性分析**：正则化系数α、阈值τ₁、τ₂的取值影响（Figure 6）。
*   **其他分析**：
    - 不同预训练模型（DINO v1/v2, MoCo, MAE, iBOT等）的Fiedler值与零样本定位性能的相关性（Figure 2, 3）。
    - 训练过程中Fiedler值及定位性能的变化（Figure 5, 8右）。
    - 模型吞吐量对比（Figure 8左）。
    - 不同骨干架构（ViT-S/T/B, ResNet50）及不同预训练方法的性能对比（Table 7）。
*   实验设计较为全面，充分考察了方法的多方面有效性及影响因素，对比公平。

## 6. 主要结论与发现
*   CUTER通过剪切标签特定区域并重放，显著提升了MOCL的性能，尤其在后期任务上的“最终性能”优势明显。
*   低秩正则化（核范数）在防止模型定位能力退化方面优于稀疏或平滑正则化。
*   所提策略与现有方法（PRS, OCDM, KRT, AGCN）正交叠加时可进一步增益，具备良好的兼容性。
*   视觉Transformer预训练模型（尤其是使用多裁剪一致性训练的DINO系列）具有更强的零样本定位潜能，适合作为MOCL的初始化骨干。

## 7. 优点
*   **视角新颖**：首次将标签特定区域学习引入在线持续多标签场景，解决了根本性的区域‑标签对应问题。
*   **方法简洁有效**：仅通过剪切、筛选、重放和轻量正则化即可同时缓解三大核心挑战。
*   **理论支撑**：利用图谱理论（Fiedler值、摄动分析）解释并指导预训练模型选型和正则化设计。
*   **即插即用**：可作为与现有重放、蒸馏、图网络等方法结合的通用组件。
*   **评估全面**：包含多种预训练模型、不同骨干及多项消融实验，验证了方法的鲁棒性和普适性。

## 8. 不足与局限
*   **算力开销**：多轮 MaskCut 增加计算负担，吞吐量较低，文中未给出具体加速方案或效率优化。
*   **骨干限制**：方法依赖ViT的图块结构构建图，对CNN架构（ResNet）适应性较差，性能有所下降（Table 7）。
*   **离线预评估需求**：选择最佳预训练模型需要下游少量数据计算Fiedler值，若完全未知任务时需依赖经验选择（如建议使用多裁剪一致性预训练模型），通用性有限。
*   **缺少部分最新对比**：由于代码或设置差异，未对比 CSC、RebLL 等最近期MLCIL方法。
*   **算力报告缺失**：未提供GPU资源、训练时长等具体消耗，不利于复现成本评估。

（完）
