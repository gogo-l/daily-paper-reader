---
title: "One Size Fits All for Semantic Shifts: Adaptive Prompt Tuning for Continual Learning"
title_zh: 语义变化一视同仁：持续学习的自适应提示调优
authors: "Doyoung Kim, Susik Yoon, Dongmin Park, Youngjun Lee, Hwanjun Song, Jihwan Bang, Jae-Gil Lee"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=WUi1AqhKn5"
tags: ["query:continual"]
score: 10.0
evidence: 针对持续学习中语义变化的自适应提示调优
tldr: 真实场景中的持续学习任务常伴随不可预测的语义漂移，固定的提示管理策略难以应对。本文提出AdaPromptCL，采用分配-精炼语义分组机制，动态管理提示组以适应不同程度语义变化。实验结果显示该方法优于现有方法，有效提升了持续学习在混合语义变化下的性能，为灵活提示管理提供了新思路。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 824, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 693, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 392, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1507, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 842, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 843, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 838, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1305, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1651, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1220, \"height\": 310, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1602, \"height\": 583, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1342, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1518, \"height\": 610, \"label\": \"Table\"}]"
motivation: 真实持续学习任务中语义变化程度不一，固定提示策略无法有效适应。
method: 提出AdaPromptCL，通过动态分配和精炼语义分组，自适应管理提示以应对不同语义变化。
result: 在混合语义变化的数据集上，AdaPromptCL优于固定提示管理方法，验证了自适应机制的有效性。
conclusion: 自适应提示调优能够灵活处理现实中的复杂语义漂移，为持续学习提供更鲁棒的解决方案。
---

## Abstract
In real-world continual learning (CL) scenarios, tasks often exhibit intricate and unpredictable semantic shifts, posing challenges for *fixed* prompt management strategies which are tailored to only handle semantic shifts of *uniform* degree (i.e., uniformly mild or uniformly abrupt). To address this limitation, we propose an *adaptive* prompting approach that effectively accommodates semantic shifts of *varying* degree where mild and abrupt shifts are mixed. AdaPromptCL employs the assign-and-refine semantic grouping mechanism that dynamically manages prompt groups in accordance with the semantic similarity between tasks, enhancing the quality of grouping through continuous refinement. Our experiment results demonstrate that AdaPromptCL outperforms existing prompting methods by up to 21.3%, especially in the benchmark datasets with diverse semantic shifts between tasks.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的结构化、深入、客观的中文总结。

---

### **1. 论文的核心问题与整体含义（研究动机和背景）**

- **核心问题**：在现实世界的持续学习场景中，接踵而至的任务之间往往存在复杂且不可预测的**语义变化**——这些变化既包含温和的（如商品分类中从食品到饮料），也包含剧烈的（如从商品分类到服饰分类）。现有基于提示（prompt）的免排练持续学习方法采用**固定的提示管理策略**，即“通用提示”（为所有任务共享一个提示，适合均匀温和变化）或“特定提示”（每个任务独立提示，适合均匀剧烈变化）。这两种极端策略均无法有效处理**语义变化程度混合**的状况，会导致提示不足或冗余，进而陷入遗忘抑制与知识迁移之间的次优妥协。
- **整体含义**：论文主张提示方法应能适应不同程度混合的语义变化，并提出一种**自适应提示策略**，通过动态管理提示组来匹配任务间的语义相似性，从而实现“一把钥匙开一把锁”，而非“一刀切”式的固定策略。

### **2. 论文提出的方法论**

- **核心思想**：提出 **AdaPromptCL** 框架，其核心是 **“分配-精炼”语义分组机制（Assign-and-Refine Semantic Grouping）**。该机制根据任务间的语义相似度动态分配和管理提示组，使语义相似的任务共享提示，语义迥异的任务使用独立提示，并在有新信息时对既有分组进行精炼优化。

- **关键技术细节与流程**：
    - **任务语义表示提取**：对每个新任务，先训练一个预热提示（warm-up prompt），然后通过平均池化和L2归一化该提示的向量，得到一个任务的语义表示 `s(τ)`。
    - **步骤一：语义分配（Assignment）**
        - **任务分组**：利用在线聚类思想，为每个新任务计算其语义表示到现有各组质心的平均距离。若最小距离超过阈值 `R`，则创建新组；否则将其归入最近的已有组。这防止了语义无关任务的错误合并。
        - **前瞻性提示收集（Prospective Prompt Collection）**：为解决未来任务未知带来的局部最优问题，该步骤主动预留未来可能出现的**前瞻语义组**及其提示。它首先通过一个更宽松的阈值 `γR` 构建“邻近任务集”，然后在每个邻近集上多次运行 **k-means 聚类**，并利用**轮廓系数**确定最佳聚类数，所得到的聚类即作为前瞻语义组。每个前瞻组都会预先训练好一个适配其成员任务的提示。
    - **步骤二：语义精炼（Refinement）**
        - **精炼准则**：目标是减少语义组总数，即用更少的组来概括任务，从而优化目标函数。通过模拟不同任务到达顺序的聚类结果，找到能形成最少语义组且能与现有前瞻组匹配的顺序。
        - **执行精炼**：若模拟发现更优分组，则触发精炼，将现有任务按新分组重新组织，并从之前存储的前瞻提示库中检索对应的提示进行适配。
    - **训练与推理**：在训练时，对包含当前任务的所有语义组（包括现有组和前瞻组）的提示-键值对进行统一优化。在推理时，通过计算测试样本与各现有语义组键的相似度，选择最匹配的提示进行预测。

### **3. 实验设计**

- **数据集与场景**：
    - **均匀温和变化场景**：**CIFAR-100** 和 **ImageNet-R**（随机拆分为10个任务，类不重叠），模拟高相似度的任务流。
    - **均匀剧烈变化场景**：**VTAB** 基准，包括 **VTAB-19T**（19个视觉任务各为一项任务）和 **VTAB-5T**（从中挑选5个最不相似的任务）。
    - **混合变化场景**：基于VTAB构建 **VTAB-SimS**（通过任务间数据重叠率 `S`% 控制相似度，测试了 S=25, 50, 75）和 **VTAB-RecR**（通过任务循环出现次数 `R` 控制相似度，测试了 R=2, 5, 10），以模拟真实世界中温和与剧烈变化混合的情况。
- **对比方法（Benchmarks）**：与代表性的免排练持续学习方法对比，包括 **L2P**、**VPT**、**LAE**（通用提示），**S-Prompts**（特定提示），以及 **DP**（混合策略）。
- **评估指标**：主要采用**最终准确率（Last Accuracy）**，并辅以**遗忘率（Forgetting）**、聚类质量指标（调整兰德指数、归一化互信息）、提示数量动态变化和计算耗时分析。

### **4. 资源与算力**

- **硬件**：所有实验均在**两块 NVIDIA RTX 3080 GPU** 上进行。
- **软件与框架**：基于 PyTorch 1.12.1 和 Timm 0.8.0 实现，采用了自动混合精度优化。
- **模型与训练**：在所有方法中共享一个在 ImageNet-1k 上预训练的 **ViT-B/16** 作为主干网络。优化器为 Adam，批量大小为 128。通用方法训练 5 个 epoch，特定方法及本方法相关训练为 50 个 epoch 或 150 次预热迭代。
- **计算开销**：在均匀温和变化场景下，AdaPromptCL 的计算耗时与通用提示方法相当；在剧烈变化场景下与特定提示方法接近。由于前瞻提示的微调，在混合变化场景下会额外增加约 12.5% 的 GPU 运行时间，以及约 1.6% 的显存占用（约150MB）。

### **5. 实验数量与充分性**

- **实验组数**：实验设计相当全面。
    - 在 **3大类（温和、剧烈、混合）共9个具体数据集场景** 上与 **5个基线方法** 进行了全面的性能对比。
    - 进行了详尽的**消融实验**，验证了“语义精炼”和“前瞻性提示调优”两个核心组件的有效性。
    - 通过**调整兰德指数和归一化互信息**等聚类指标，定量分析了语义分组的正确性。
    - 使用 **t-SNE** 可视化展示了语义分组的效果。
    - 分析了关键超参数（分组阈值 `R`）的**敏感性**。
    - 验证了方法在**不同规模的预训练主干网络（ViT-S/16, ViT-T/16）**上的泛化性。
    - 对比了**提示数量**和**准确率**随任务流演变的动态过程。
- **充分性与公平性**：实验涵盖的场景丰富，对比方法广泛，评估指标多样，并包含了消融、可视化和参数分析。所有实验重复5次并报告了标准误差，结果具有统计可靠性。各方法使用相同的主干网络和公平的基准配置，确保了对比的客观性。

### **6. 论文的主要结论与发现**

- **卓越的自适应能力**：AdaPromptCL 在混合语义变化场景下，性能显著优于所有固定提示管理基线方法，相较于 LAE 和 S-Prompts 平均提升达 6.35% 和 6.91%，最高提升 21.3%（与S-Prompts在VTAB-Rec10上的表现对比高达13.6%）。
- **普适的稳健性**：在均匀温和变化场景下，性能与最优的通用提示方法持平；在均匀剧烈变化场景下，性能与最优的特定提示方法持平。这表明该方法能在一个框架内有效应对从温和到剧烈的各种语义变化。
- **机制有效性**：消融实验证明，“精炼”机制显著提升了分组的准确性并防止了局部最优，“前瞻提示”机制则确保了精炼后提示的适配质量，两者缺一不可。
- **分组精确性**：在混合变化场景中，AdaPromptCL 能成功地将冗余的语义组合并精炼，使形成的语义组数量更接近真实情况，聚类质量指标接近理论最优值。

### **7. 优点**

- **问题动机新颖且实际**：首次系统性地关注并解决提示持续学习中语义变化程度混合的挑战，更贴近真实应用。
- **方法论创新**：提出的 **“分配-精炼”框架**优雅地解决了在线持续学习中未知未来任务的语义分组难题，特别是前瞻性提示收集和基于顺序模拟的精炼机制设计巧妙。
- **实验严谨全面**：实验设计覆盖了均匀和混合两大类场景，对比了全面的基线，并通过消融、量化聚类指标、可视化、多规模主干网络等多种方式，充分验证了方法的有效性和鲁棒性。
- **轻量级实现**：作为提示调优方法，只需调整极少量参数，计算和存储开销增加不大，兼具高效性。

### **8. 不足与局限**

- **超参数依赖性**：方法的性能依赖于几个关键超参数，如分组阈值 `R`、邻近任务集缩放因子 `γ` 等，论文虽然做了敏感性分析，但在实际部署中可能需要针对具体任务流进行调优。
- **极端场景优势有限**：在纯粹的均匀（极度温和或极度剧烈）变化场景下，AdaPromptCL 的性能与已针对该场景优化的固定策略几乎相同，其自适应优势在此类简单场景下无法充分体现，且可能会因额外的分组机制带来微小的额外计算开销。
- **任务语义表示方法的局限性**：任务语义表示完全依赖于一个经过短暂预热的提示。如果该预热提示无法有效捕获任务的核心语义（例如标记数据极少时），整个分组机制的基础可能会动摇。
- **类别增量与域增量**：实验主要在类别增量或域增量设置下进行，对于任务标识未知的任务无关持续学习场景，其适用性有待进一步验证。

（完）
