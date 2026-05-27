---
title: "Unlocking the Power of Rehearsal in Continual Learning: A Theoretical Perspective"
title_zh: 释放持续学习中排练的力量：理论视角
authors: "Junze Deng, Qinhang Wu, Peizhong Ju, Sen Lin, Yingbin Liang, Ness Shroff"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=p6nhzZ9ilZ"
tags: ["query:continual"]
score: 9.0
evidence: 对排练策略进行理论分析以对抗遗忘
tldr: 该研究探讨持续学习中排练策略的优化问题，分析并发排练与顺序排练对缓解灾难性遗忘的影响。通过过参数化线性模型的严格理论分析，揭示了顺序排练在一定条件下优于传统并发排练。实验验证了理论发现，为设计更有效的排练方法提供了理论依据，丰富了持续学习的理论基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 825, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 831, \"height\": 1110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1667, \"height\": 176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1670, \"height\": 178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1667, \"height\": 175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1669, \"height\": 178, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 524, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1694, \"height\": 623, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1778, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1148, \"height\": 507, \"label\": \"Table\"}]"
motivation: 现有持续学习排练方法多采用并发排练，不清楚是否最优。
method: 对过参数化线性模型中的并发排练与顺序排练进行理论分析比较。
result: 得出顺序排练在某些条件下优于并发排练的结论。
conclusion: 为排练策略选择提供了理论指导。
---

## Abstract
Rehearsal-based methods have shown superior performance in addressing catastrophic forgetting in continual learning (CL) by storing and training on a subset of past data alongside new data in current task. While such a concurrent rehearsal strategy is widely used, it remains unclear if this approach is always optimal. Inspired by human learning, where sequentially revisiting tasks helps mitigate forgetting, we explore whether sequential rehearsal can offer greater benefits for CL compared to standard concurrent rehearsal. To address this question, we conduct a theoretical analysis of rehearsal-based CL in overparameterized linear models, comparing two strategies: 1) Concurrent Rehearsal, where past and new data are trained together, and 2) Sequential Rehearsal, where new data is trained first, followed by revisiting past data sequentially. By explicitly characterizing forgetting and generalization error, we show that sequential rehearsal performs better when tasks are less similar. These insights further motivate a novel Hybrid Rehearsal method, which trains similar tasks concurrently and revisits dissimilar tasks sequentially. We characterize its forgetting and generalization performance, and our experiments with deep neural networks further confirm that the hybrid approach outperforms standard concurrent rehearsal. This work provides the first comprehensive theoretical analysis of rehearsal-based CL.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究问题**：持续学习（CL）中的一个关键挑战是灾难性遗忘，基于排练（rehearsal）的方法通过存储部分旧任务数据并在新任务训练时重放来缓解此问题。然而，广泛使用的**并发排练**（Concurrent Rehearsal，旧数据与新数据混合训练）是否总是最优策略，这一点尚不清楚。
- **动机**：受人类学习启发：当新旧知识不相似时，人们常先学新知识，再有针对性地复习旧知识（顺序复习），而非混在一起学。这种“先新后旧”的**顺序排练**（Sequential Rehearsal）可能在某些情况下优于并发排练。
- **核心目标**：从理论上系统比较两种排练策略（并发 vs. 顺序），揭示任务相似度等因素如何影响遗忘和泛化误差，并据此设计更优的排练策略。

### 2. 论文提出的方法论

- **理论框架**：
  - 采用**过参数化线性回归模型**（特征维度 $p >$ 总训练样本数 $n+M$），假设特征和噪声服从独立高斯分布。
  - 定义排练过程为基于记忆数据的顺序优化，利用最小范数解刻画SGD的收敛点。
  - 性能度量：**遗忘**（旧任务学习后性能下降的平均值）和**泛化误差**（最终模型在所有任务上的平均误差）。
- **排练策略的形式化定义**：
  - **并发排练**：在任务 $t$ 时，使用当前数据集 $\mathcal{D}_t$ 和记忆数据集 $\mathcal{M}_t$ 的并集进行训练，一次求解一个带约束的最小范数问题。
  - **顺序排练**：先仅用 $\mathcal{D}_t$ 训练至收敛，然后依次用每个旧任务 $h$ 的记忆数据 $\mathcal{M}_{t,h}$ 进行微调（顺序访问，一次一个任务）。
- **Hybrid Rehearsal 算法**（基于理论洞见的实用扩展）：
  - 步骤简述：
    1. 根据梯度余弦相似度将记忆中的旧任务分为“相似集” $\mathcal{M}_t^{\text{sim}}$ 和“相异集” $\mathcal{M}_t^{\text{dis}}$。
    2. 对 $\mathcal{D}_t \cup \mathcal{M}_t^{\text{sim}}$ 执行**并发训练**。
    3. 然后对 $\mathcal{M}_t^{\text{dis}}$ 中的每个任务按序执行**顺序训练**（微调）。
  - 关键参数：相似度阈值 $\tau$，用于分割记忆缓冲区。

### 3. 实验设计

- **数据集/场景**：任务增量学习（Task-IL），每个任务包含互不重叠的类别。
  - 原始数据集：Split-CIFAR-10（2类/任务 ×5任务）、Split-CIFAR-100（5类/任务 ×5任务，另增20任务版本）、Split-TinyImagenet200（10类/任务 ×5任务，另增20任务版本）。
  - 为验证任务相异度的影响，构造**腐蚀版本**数据集：对部分任务施加图像腐蚀（玻璃模糊、颜色置换、旋转、弹性像素化等）以降低相似度。
  - 额外构造不同标签腐蚀比例（$p_{\text{cor}}$）的 Split-TinyImagenet200 以控制相似度。
- **对比方法**：标准并发排练（Concurrent Rehearsal） vs. 提出的混合排练（Hybrid Rehearsal）。
- **模型架构**：CIFAR 数据集使用非预训练 ResNet-18；TinyImagenet 使用 ResNet-18；MNIST 使用3层 MLP（补充实验）。
- **评价指标**：最终平均测试准确率（Acc，作为泛化误差）和最终平均遗忘（$F_{gt}$）。
- **基线与训练细节**：采用储层采样（reservoir sampling）维护记忆，固定记忆容量，多头部输出层，SGD 优化器，阶梯式学习率衰减。

### 4. 资源与算力

- 文中在附录A.1给出了硬件配置：
  - **GPU**：NVIDIA P100 “Pascal” GPU，16GB 显存。
  - **CPU**：2.4 GHz 14-核 Intel Xeon E5-2680 v4。
  - 未提供 GPU 数量、单次训练耗时或总耗时。

### 5. 实验数量与充分性

- **实验规模**：共涉及4个数据集（CIFAR-10/100, TinyImagenet200, MNIST）及其腐蚀变体，涵盖不同任务数（5、10、20）和不同腐蚀程度（单一腐蚀、多任务腐蚀、标签比例腐蚀），实验总数较为丰富。
- **可重复性**：超参数（学习率、批大小、缓冲区大小等）在附录中详列，所有结果均报告均值和标准差（5或10次独立运行），对比公平。
- **理论验证**：在合成线性模型上进行了模拟，理论值与仿真结果高度重合（如图2），增强了可靠性。
- **不足**：未与经典 SOTA 排练方法（如 iCaRL、GEM 等）直接比较，仅以标准并发排练为基线；混合排练的超参数（相似度阈值 $\tau$ 等）选择未做详细敏感性分析。

### 6. 论文的主要结论与发现

- **理论比较**：
  - 并发排练在任务相似时更优；顺序排练在任务相异时更优（遗忘和泛化误差均更小）。
  - 当任务间差异逐渐增大时，顺序排练的优势愈加明显。
- **混合排练的优越性**：
  - 在所有真实数据集上，混合排练均优于标准并发排练：Acc 提升1.07%~4.32%，$F_{gt}$ 降低1.48~13.32个百分点。
  - 在人为增加任务相异度（图像腐蚀/标签腐蚀）后，混合排练的优势进一步扩大，印证理论预测。
  - 在长任务序列（20任务）上依然有效且优势稳定。

### 7. 优点

- **首创性理论分析**：首次给出过参数化线性模型下两种排练策略遗忘和泛化误差的显式闭式解，并严格比较。
- **清晰的理论洞察**：明确揭示任务相似度是决定排练策略优劣的关键因素，为方法设计提供理论指导。
- **实用算法贡献**：基于理论提出简单有效的杂交算法，不依赖精确相似度测量，易于实现且效果好。
- **实验设计合理**：通过多种手段（腐蚀、标签扰动）主动控制任务相似度，直接验证理论条件的适用性。

### 8. 不足与局限

- **理论假设限制**：基于线性模型和 i.i.d. 高斯数据，与实际深度非线性情况有差距。
- **比较基准有限**：仅与基础并发排练比较，未纳入其他更先进的排练或约束式方法。
- **混合方法的泛化性**：相似度分割依赖梯度余弦相似度阈值 $\tau$，未详细研究该阈值敏感性；如何综合优化排练顺序和相似度选择仍是开放问题。
- **计算开销**：顺序排练阶段需要对每个相异任务单独微调，在任务数很多时可能增加训练时间，文中未讨论效率。
- **记忆分配假设**：理论分析假设记忆数据刚采样且等分给各旧任务，实际使用中可能存在偏差。

（完）
