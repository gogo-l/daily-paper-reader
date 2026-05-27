---
title: Harnessing Neural Unit Dynamics for Effective and Scalable Class-Incremental Learning
title_zh: 利用神经单元动态实现有效且可扩展的类增量学习
authors: "Depeng Li, Tianqi Wang, Junwei Chen, Wei Dai, Zhigang Zeng"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=eDtty9ZCvt"
tags: ["query:continual"]
score: 9.0
evidence: 类增量学习算法动态扩展网络防止遗忘
tldr: 本文针对类增量学习中的灾难性遗忘问题，提出利用神经单元动态机制自适应调整网络行为。每个训练阶段引入监督机制引导网络扩展，扩展规模与任务复杂度相匹配，构建近最小网络；推理时自动激活相关单元、抑制无关单元。实验表明该方法在有效防止遗忘的同时保持紧凑模型，在多个基准上取得先进性能，为非平稳数据流下的增量学习提供了可扩展方案。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-edtty9zcvt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1625, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-edtty9zcvt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 520, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-edtty9zcvt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 900, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-edtty9zcvt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 641, \"height\": 362, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1649, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1259, \"height\": 641, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1137, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 806, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 749, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1354, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1075, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 755, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1009, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 724, \"height\": 316, \"label\": \"Table\"}]"
motivation: 类增量学习需在不忘记旧类的前提下学习新类，现有方法难以兼顾容量与遗忘。
method: 设计神经单元动态机制，训练时按任务复杂度指导网络扩展，推理时选择性激活单元。
result: 在多个类增量学习基准上达到领先水平，模型规模接近最小。
conclusion: 该方法兼顾了遗忘抑制与模型效率，适用于非平稳数据流。
---

## Abstract
Class-incremental learning (CIL) aims to train a model to learn new classes from non-stationary data streams without forgetting old ones. In this paper, we propose a new kind of connectionist model by tailoring neural unit dynamics that adapt the behavior of neural networks for CIL. In each training session, it introduces a supervisory mechanism to guide network expansion whose growth size is compactly commensurate with the intrinsic complexity of a newly arriving task. This constructs a near-minimal network while allowing the model to expand its capacity when cannot sufficiently hold new classes. At inference time, it automatically reactivates the required neural units to retrieve knowledge and leaves the remaining inactivated to prevent interference. We name our model AutoActivator, which is effective and scalable. To gain insights into the neural unit dynamics, we theoretically analyze the model’s convergence property via a universal approximation theorem on learning sequential mappings, which is under-explored in the CIL community. Experiments show that our method achieves strong CIL performance in rehearsal-free and minimal-expansion settings with different backbones.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：类增量学习（CIL）要求模型在非稳态数据流中学习新类的同时不遗忘旧类，即克服灾难性遗忘。现有方法主要分为回放（依赖旧样本存储，受隐私和内存限制）、正则化（固定容量模型难以灵活适应）和架构扩展（易导致模型过度膨胀且缺乏理论保证）三类，难以在模型紧凑性、准确率和无回放之间取得平衡。
- **整体含义**：受神经科学中记忆再激活机制的启发，本文设计了一种新型联结主义模型 AutoActivator，通过定制**神经单元动态**（包括节点生成、连接、激活阈值和更新规则）来适应 CIL。它能够在每个任务上构建与其内在复杂度相匹配的近最小网络，并在推理时自动再激活相关神经单元以检索知识，同时保持其他单元失活以避免干扰，从而在免回放和最小扩展的设置下实现有效且可扩展的类增量学习。

### 2. 论文提出的方法论
- **核心思想**：将神经单元视为可动态扩展的节点集合，通过**监督机制**引导网络扩展，使得每次增加的新节点必须满足一定的残差缩减条件，从而构建一个与每个任务复杂度相称的紧凑模型。在推理时，利用训练阶段计算的**激活阈值**选择性地激活对应神经单元，实现无任务身份标识的决策。
- **关键技术细节**：
    - **监督式节点扩展**：每个训练阶段，随机生成若干批候选节点。依据定理 4.2 的通用逼近定理，要求新一批节点 \( G_l \) 满足不等式约束：\[ \langle e_{L-l,c}(t), G_l \beta_{l,c}(t) \rangle \geq \delta_{L,c}(t) \] 其中 \( e_{L-l,c} \) 是当前残差，\( \delta_{L,c} \) 用于控制收敛速度。满足条件的节点放入候选池，最终选择能使训练误差**最大下降**的那一批加入神经单元。通过这种方式，扩展规模与任务的内在难度自适应匹配。
    - **输出权值更新**：采用动态逐步更新算法（基于分块矩阵的伪逆），在添加节点时无需完全重训练，仅通过已有矩阵的简单计算即可得到最小二乘意义下的最优输出权值，避免了误差反向传播。
    - **推理阶段的再激活**：训练时为每个神经单元计算激活阈值，即该单元对所属类别的最高预测概率均值 \( \text{threshold}(t) = \text{mean}(\max(\text{softmax}(\hat{Y}_t)) - \alpha(t)) \)。推理时，对一批测试样本计算其预测阈值，选择与存储阈值距离最近的神经单元进行预测：\( c \leftarrow \arg\min_t |\text{threshold}(t) - \tilde{\text{threshold}}(t)| \)，从而自动激活相应单元并抑制其他单元。
- **算法流程**：每个任务内循环生成节点、更新权值，直到满足终止条件（最大节点数或期望准确率）；之后计算并存储该单元的激活阈值。测试时根据阈值距离自动激活对应单元并预测类别。

### 3. 实验设计
- **数据集与场景**：
    - 小规模：MNIST 和 FashionMNIST，均分为 5 个任务，每任务 2 类，使用 MLP 架构。
    - 中规模：CIFAR-100，分为 10 任务（每任务 10 类）和 25 任务（每任务 4 类），使用 ResNet-18 骨干网络，部分方法允许预训练。
    - 大规模：ImageNet-R（200 类），分为 10 任务，每任务 20 类，使用 ViT-B/16 预训练骨干网络。
    - 额外测试了不均匀任务分割（intra-sequence imbalanced）、单类增量（100 任务）、在线 CIL、ImageNet-100/1K 等场景。
- **对比方法**：涵盖三大类 CIL 方法，如正则化类（EWC, MAS, SI, OWM 等）、回放类（IL2M, BiC, LOGD, FS-DGPM 等）、架构类（PCL, DER, RPS-Net, EFT, CRNet 等），以及基于提示的方法（L2P, DualPrompt, CODA-Prompt）。以 SGD 为下界、多任务联合训练（MTL）为上界。
- **评价指标**：平均分类准确率（ACA）、后向迁移（BWT）/遗忘率、内存预算（模型参数量 + 回放样本量），并特别强调在免回放和模型规模方面的公平比较。

### 4. 资源与算力
- 论文指出代码基于 PyTorch 实现，使用 **NVIDIA RTX 3080-Ti GPU**。在参数分析中（Table 4）给出了不同设置下整个任务序列的训练时间（秒），例如在 MNIST-10/5 上时间约为 10 至 65 秒，FashionMNIST 上类似。然而，论文**未明确说明使用的 GPU 数量、显存占用以及整体训练耗时**的具体总消耗，也未提及除推理时间外的其他算力开销细节。

### 5. 实验数量与充分性
- 进行了**至少 10 组以上的主要对比实验**：覆盖 4 种不同规模的数据集和多种任务划分（包括均衡与不均衡），并在有无预训练、不同骨干网络下进行比较。
- 开展了详尽的**消融和参数分析**：包括监督机制中步长 \( l \)（逐节点 vs 批量）、最大随机尝试次数 \( T_{\max} \) 的影响；激活阈值的两个组件（修正类间混淆与校准）的消融；还分析了实际扩展配额与任务复杂度的关系（Table 5）、时间成本对比（Table 8）、模型规模增长曲线（Figure 4）等。
- **公平性**：采用统一的内存预算指标对齐模型大小与回放样本开销；对所有基线均调至最佳超参数并多次随机任务顺序运行；允许方法在最有利的设置下（如是否启用预训练）比较。因此，实验设计**充分且客观**。

### 6. 论文的主要结论与发现
- AutoActivator 在**免回放、最小扩展**的约束下，于多个 CIL 基准上取得了**最先进的分类准确率**，同时展现出极低甚至为零的遗忘（BWT≈0），表明模型对灾难性遗忘天然免疫。
- 通过理论证明（通用逼近定理），模型在序列学习任务上具有**收敛性保证**，填补了 CIL 社区的理论空白。
- 网络的实际扩展量与每个任务的**内在复杂度高度相关**，最终模型内存预算远低于许多需要回放或过度扩展的方法，并具备较强的任务顺序鲁棒性。
- 即使与依赖预训练和提示的方法结合，AutoActivator 也能进一步提升性能，显示出良好的**通用性与可扩展性**。

### 7. 优点
- **理论驱动**：用通用逼近定理严格证明了序列学习下模型扩展的收敛性，为网络增长提供了理论基础。
- **高效紧凑**：自适应匹配任务复杂度的扩展机制，构建近最小网络，在免回放条件下大幅降低内存占用。
- **生物可解释性**：模拟大脑的神经元再激活模式，通过激活阈值实现无任务 ID 的自动知识检索，设计新颖。
- **多场景验证**：覆盖从简单 MLP 到 ViT 的不同架构，以及均衡、不均衡、单类增量、在线 CIL 等多样化场景，证明方法的普适性。

### 8. 不足与局限
- **训练时依赖任务边界**：方法假设训练阶段已知任务切换边界（如任务 t 何时结束），而在完全连续无边界的数据流场景中可能不适用。
- **预训练模型的偏差风险**：当使用预训练骨干时，原模型的偏见和公平性问题可能延续到增量学习过程中。
- **计算瓶颈隐忧**：虽然更新公式避免反向传播，但节点选择过程中需要反复生成候选节点并计算伪逆，当候选池极大或网络很深时，计算开销可能上升。
- **超参敏感性**：监督机制中的期望准确率 \( R(t) \)、最大随机尝试次数 \( T_{\max} \) 等需按任务调整，极端不平衡的小样本任务上可能需要更细致的调参。
- **未充分探索的边界**：对严重类别不平衡流（class-imbalance）、开放世界未知类等更具挑战的 CIL 变体尚未深入验证。

（完）
