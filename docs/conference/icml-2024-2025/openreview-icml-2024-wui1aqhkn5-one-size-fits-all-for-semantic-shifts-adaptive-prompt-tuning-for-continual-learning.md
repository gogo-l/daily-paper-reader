---
title: "One Size Fits All for Semantic Shifts: Adaptive Prompt Tuning for Continual Learning"
title_zh: 语义转变的通用方案：面向持续学习的自适应提示微调
authors: "Doyoung Kim, Susik Yoon, Dongmin Park, Youngjun Lee, Hwanjun Song, Jihwan Bang, Jae-Gil Lee"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=WUi1AqhKn5"
tags: ["query:continual"]
score: 9.0
evidence: 提出面向持续学习的自适应提示微调方法以应对语义转变
tldr: 本文聚焦持续学习中任务语义变化程度不一致的挑战，提出自适应提示微调方法AdaPromptCL。该方法不再预设语义转变的均匀性，而是通过“分配-优化”机制，依据任务间的语义相似性动态组建并持续优化提示组，从而灵活适应温和与突变混合的语义漂移。在多种标准持续学习数据集上的实验表明，AdaPromptCL不仅能有效抑制灾难性遗忘，在平均准确率上显著超越固定策略，还具有良好的任务整合能力，为处理现实世界复杂语义变化的持续学习系统提供了通用、高效的提示管理框架。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 851, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 824, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 693, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 392, \"height\": 610, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1507, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 842, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 843, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 838, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1305, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1651, \"height\": 685, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-wui1aqhkn5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1220, \"height\": 310, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1602, \"height\": 583, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 865, \"height\": 212, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 465, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1342, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-wui1aqhkn5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1518, \"height\": 610, \"label\": \"Table\"}]"
motivation: 现有固定提示管理策略假设语义转变程度均匀，无法应对现实混合转变。
method: 提出自适应提示微调AdaPromptCL，通过分配-优化机制根据语义相似性动态分组。
result: 在多种持续学习基准上，AdaPromptCL平均准确率显著超越固定策略且缓解遗忘。
conclusion: 灵活的自适应提示管理为混合语义转变的持续学习提供有效解决方案。
---

## Abstract
In real-world continual learning (CL) scenarios, tasks often exhibit intricate and unpredictable semantic shifts, posing challenges for *fixed* prompt management strategies which are tailored to only handle semantic shifts of *uniform* degree (i.e., uniformly mild or uniformly abrupt). To address this limitation, we propose an *adaptive* prompting approach that effectively accommodates semantic shifts of *varying* degree where mild and abrupt shifts are mixed. AdaPromptCL employs the assign-and-refine semantic grouping mechanism that dynamically manages prompt groups in accordance with the semantic similarity between tasks, enhancing the quality of grouping through continuous refinement. Our experiment results demonstrate that AdaPromptCL outperforms existing prompting methods by up to 21.3%, especially in the benchmark datasets with diverse semantic shifts between tasks.

---

## 论文详细总结（自动生成）

### 1. 论文核心问题与研究背景

- **核心问题**：现实世界的持续学习（CL）任务序列中，任务之间的语义转变程度往往**复杂多变且不可预测**，可能是同类别内的温和转变，也可能是跨类别的突变。现有基于提示（prompt）的免排练（rehearsal-free）方法采用**固定的提示管理策略**，仅能处理**单一均匀的语义转变**（要么全部温和，要么全部突变），无法有效应对**混合程度的转变**。
- **研究动机**：固定策略在混合场景下要么提示不足（通用提示）、要么提示冗余（专用提示），导致模型在知识迁移与遗忘抑制之间妥协，性能次优。因此，需要一种**自适应的提示管理方法**，能够根据任务间的实际语义关系动态调整提示的数量与共享方式。
- **整体含义**：论文提出“One Size Fits All for Semantic Shifts”，即用**一个自适应框架灵活覆盖各种语义转变情形**，克服现有方法在真实杂乱任务流中的局限性。

### 2. 方法论：自适应提示微调 (AdaPromptCL)

核心思想是在通用提示与专用提示两个极端之间动态平衡，通过**“分配-优化”的语义分组机制**管理提示，确保每个语义组共用一个提示，且组数随任务语义变化自动增减。

- **任务语义表示 (Task Semantic Extraction)**
  - 对每个新任务`τ`，先训练一个**热身提示**`ˆP_τ` (通过专用提示目标函数)。
  - 将该提示做平均池化并L2归一化，得到任务的语义向量 `s(τ)`，用于后续相似性计算。
- **语义组定义**
  - 一个语义组`G_i`是一组任务，其内部任务表示与组中心的平均距离不超过阈值`R`。
- **步骤 I：语义分配 (Semantic Assignment)**
  - 对到达任务`τ_t`，计算其与现有组`G^{t-1}`的距离。若加入任何组均会超过阈值`R`，则新建一个组；否则加入使其距离最小的最近组。
  - **前瞻提示收集**：为应对未来可能出现的组优化，系统会维护一个更大的**相邻任务集**（使用阈值`γR`，`γ>1`），并在其上运行`k-means`（`k`由轮廓系数决定）生成**前瞻语义组**。对这些前瞻组也训练提示，以备后续优化时直接取用，避免重新访问旧任务数据。
- **步骤 II：语义优化 (Semantic Refinement)**
  - **优化触发条件**：检查新任务的到来是否能**减少现有组总数**（`|G^t| ≤ |G^{t-1}|`）。通过模拟不同任务到达顺序，寻找能使组数最少的排列，且该排列下的分组必须已存在于前瞻组集合中。
  - 若找到更优分组，则执行优化：用前瞻组替换当前组，并将对应的前瞻提示取出，进一步适应当前任务。
- **训练与推理**
  - **训练**：对包含当前任务的所有前瞻组对应的提示-键对，以均匀采样的方式联合优化交叉熵损失和键匹配损失。
  - **推理**：从当前语义组的键中选取与测试样本特征最相似的键，使用对应组的提示进行预测。

### 3. 实验设计

论文构建了多种语义转变场景，并选用代表性基线进行对比，以验证方法的通用性。

- **数据集与场景**：
  - **均匀温和转变**：`CIFAR-100`（10任务）、`ImageNet-R`（10任务），任务间类别高度重合。
  - **均匀突变转变**：`VTAB-19T`（19个不同视觉任务）、`VTAB-5T`（最不相似的5个任务）。
  - **混合变化转变**：
    - `VTAB-SimS`：通过任务间数据重叠比例`S`（25%、50%、75%）制造相似任务与不相似任务混合。
    - `VTAB-RecR`：通过任务重复频率`R`（2、5、10）引入重复任务，形成混合语义流。
- **对比方法**：与主流免排练提示方法对比：`L2P`、`VPT`、`DP`、`S‑Prompts`、`LAE`。
- **评价指标**：主要使用**最终准确率**（Last Accuracy，学习完所有任务后每个任务准确率的均值），辅以**遗忘率**和聚类质量指标（ARI、NMI）。
- **实现细节**：统一采用`ViT‑B/16`（ImageNet‑1k预训练），提示插入前5层Transformer，优化器Adam，学习率0.025，批大小128。所有实验重复5次取平均并报告标准误。代码已开源。

### 4. 算力与资源消耗

- **硬件**：所有实验在 **两颗 NVIDIA RTX 3080 GPU** 上完成。
- **软件环境**：PyTorch 1.12.1、Timm 0.8.0。
- **训练时长与显存**：
  - 运行时：AdaPromptCL在均匀温和场景（ImageNet‑R）下约18.4分钟，在突变场景（VTAB‑19T）约63分钟，在混合场景（VTAB‑Rec10）约126分钟，略高于固定策略方法但仍在同量级。
  - 显存占用：混合场景下约9257 MB，因额外维护前瞻提示组仅增加约150MB（1.6%）显存，开销极小。

### 5. 实验数量与充分性

- 实验规模非常充分，覆盖了**3大类场景、超过10个不同的持续学习数据集/配置**，每种配置均与5个基线对比。
- 除主表外，还提供了：
  - **消融实验**（无优化、平均合并变体）验证核心组件贡献。
  - **分组质量分析**（ARI、NMI指标）与**t‑SNE可视化**。
  - **超参数敏感性**（阈值`R`、聚类迭代次数等）。
  - **不同预训练骨干规模**（ViT‑S/16、ViT‑T/16）的通用性测试。
  - **运行时与显存对比**、**遗忘指标**等辅助分析。
- 所有实验均多次重复，报告均值±标准误，比较公平客观。

### 6. 主要结论与发现

- 在**混合语义转变场景**下，AdaPromptCL显著超越所有基线，相对LAE（最佳通用方法）平均提升6.35%，相对S‑Prompts（最佳专用方法）平均提升6.91%。
- 在**均匀温和或均匀突变场景**，AdaPromptCL能自动退化到与场景最优方法（通用或专用）相当的性能，例如在ImageNet‑R上生成1个组，在VTAB‑19T上生成18个组，证明了其自适应灵活性。
- 语义优化机制能有效修正在线聚类顺序偏差，减少冗余组，提升分组纯度（ARI从0.89提升至0.97）。
- 方法额外计算和显存开销很小，具有实用价值。

### 7. 优点与亮点

- **首创性**：首次在提示驱动的免排练持续学习中系统性解决**非均匀语义转变**问题。
- **机制新颖**：提出的“分配-优化”分组策略，结合前瞻提示池与顺序模拟优化，无需存储旧数据即可实现类似离线聚类的效果。
- **自适应能力强**：单一方法可自动调整提示数量，在各类转变下性能均达到或接近最优固定方案。
- **资源友好**：仅微调极少量提示参数，前瞻提示带来的额外内存和时间成本极低。
- **实验扎实**：大量场景、全面对比、细致分析，可信度高，代码开源便于复现。

### 8. 不足与局限

- **任务设定局限**：实验均为图像分类任务，且各任务类别不重叠（除构造的混合场景），未验证在更复杂数据模态或类别增量重叠设置下的表现。
- **超参数依赖**：虽然对阈值`R`和`γ`不特别敏感，但`R=0.4`等最优值可能随数据变化，需适当调整。
- **语义表示依赖**：任务语义完全依靠热身专用提示，若热身提示不佳，可能影响分组准确度。
- **前瞻组收集效率**：需要在每个到达任务上运行多次`k-means`和轮廓计算，虽然实验中总耗时增加不多，但在任务极多时可能成为瓶颈。
- **假设所有组均可用提示键匹配**：推理时依赖键值选择，若不同组的键区分度不够，可能选错提示，文中未深入探讨该失败情形。

（完）
