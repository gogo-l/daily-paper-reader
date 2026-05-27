---
title: Task-aware Orthogonal Sparse Network for Exploring Shared Knowledge in Continual Learning
title_zh: 任务感知正交稀疏网络在持续学习中探索共享知识
authors: "Yusong Hu, De Cheng, Dingwen Zhang, Nannan Wang, Tongliang Liu, Xinbo Gao"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=tABvuya05B"
tags: ["query:continual"]
score: 9.0
evidence: 通过三部分网络结构解决灾难性遗忘
tldr: 针对当前基于彩票假说的网络分区方法在长期持续学习中欠拟合的问题，提出任务感知正交稀疏网络，将网络分为三部分以探索新旧任务间的知识共享。实验表明该方法在多个持续学习基准上实现了无遗忘且性能提升，尤其在任务数量多时优势明显。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1713, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 661, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-tabvuya05b/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 836, \"height\": 432, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-tabvuya05b/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1760, \"height\": 456, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tabvuya05b/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 854, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-tabvuya05b/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1747, \"height\": 276, \"label\": \"Table\"}]"
motivation: 现有彩票假说网络分区方法在长期持续学习中出现严重欠拟合。
method: 提出任务感知正交稀疏网络，将网络分为三部分以探索知识共享。
result: 在长期持续学习实验中实现无遗忘且性能优于基准方法。
conclusion: 三部分结构和正交稀疏约束有效解决了长期学习中的容量和遗忘冲突。
---

## Abstract
Continual learning (CL) aims to learn from sequentially arriving tasks without catastrophic forgetting (CF). By partitioning the network into two parts based on the Lottery Ticket Hypothesis---one for holding the knowledge of the old tasks while the other for learning the knowledge of the new task---the recent progress has achieved forget-free CL. Although addressing the CF issue well, such methods would encounter serious under-fitting in long-term CL, in which the learning process will continue for a long time and the number of new tasks involved will be much higher. To solve this problem, this paper partitions the network into three parts---with a new part for exploring the knowledge sharing between the old and new tasks. With the shared knowledge, this part of network can be learnt to simultaneously consolidate the old tasks and fit to the new task. To achieve this goal, we propose a task-aware **Orthogonal Sparse Network** (OSN), which contains shared knowledge induced network partition and sharpness-aware orthogonal sparse network learning. The former partitions the network to select shared parameters, while the latter guides the exploration of shared knowledge through shared parameters. Qualitative and quantitative analyses, show that the proposed OSN induces minimum to no interference with past tasks, *i.e.*, approximately no forgetting, while greatly improves the model plasticity and capacity, and finally achieves the state-of-the-art performances.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：持续学习（CL）要求模型顺序学习多个任务而不发生灾难性遗忘（CF）。基于彩票假说（Lottery Ticket Hypothesis）的方法将网络参数划分为“旧任务保留”和“新任务学习”两部分，虽然能实现无遗忘，但在**长期持续学习**（任务数量很大）中会出现**严重欠拟合**，因为被冻结的旧任务子网络完全垄断了重要参数，导致新任务可用的容量和可塑性急剧下降。
- **整体含义**：本文提出在旧任务子网络和新任务自由参数之间引入**第三部分——共享参数**，用于探索新旧任务间的**共享知识**，从而同时提升模型的稳定性（防遗忘）和可塑性（学新任务），有效缓解长期持续学习中的稳定性-可塑性困境。

### 2. 论文提出的方法论
- **核心思想**：将网络划分为三个部分：
  - 旧任务专属冻结参数（保持旧知识）；
  - 新任务自由训练参数（学习新知识）；
  - 共享参数（从旧任务子网络中选取，通过正交投影更新以学习共享知识）。
- **关键技术细节**：
  1. **共享知识驱动的网络分区**：首先通过彩票假说剪枝得到旧任务的重要子网络（掩码 \(M_{t-1}\)），然后在训练新任务时利用权重重要性函数 \(CWI(\cdot)\) （结合权重范数和梯度范数）评估旧任务子网络中参数对新任务的重要性，选出 top-k% 作为共享参数（用掩码 \(m_t\) 表示，共享参数为 \(M_{t-1} \cap m_t\)）。
  2. **正交稀疏网络学习**：对三类参数采用不同学习策略：
     - 冻结参数（\(M_{t-1} \setminus (M_{t-1} \cap m_t)\)）：保持旧任务性能，梯度清零。
     - 自由参数（\(1 - M_{t-1}\)）：用常规梯度下降更新，学习新知识。
     - 共享参数（\(M_{t-1} \cap m_t\)）：将其梯度投影到旧任务特征空间的**正交补空间**上，使得参数更新不干扰旧任务输出，从而在不遗忘的前提下实现知识共享。
  3. **锐度感知正交投影**：传统正交投影通过SVD近似构造投影矩阵 \(P_{t-1}\)，但可能不精确。本文提出**锐度感知正交投影**，通过寻找损失景观中的平坦最小值（加入最大扰动 \(\delta\) 的正则项 \( \max_{\|\delta\|\le \rho} (L(\theta+\delta)-L(\theta)) \)）和训练数据混合增强（mixup），使模型在参数更新时对旧任务损失的影响更小，提升共享知识学习的稳定性。投影矩阵由旧任务特征矩阵的SVD中最小奇异值对应的奇异向量构造。
- **算法流程**（Algorithm 1）：对每个任务，先训练第一个任务获得剪枝掩码和正交投影矩阵；对于后续任务，计算重要性选共享掩码，用增强数据和锐度感知损失训练网络，共享参数正交更新，自由参数常规更新，最后更新剪枝掩码和投影矩阵。

### 3. 实验设计
- **数据集**：
  - 标准持续学习数据集：PMNIST（10任务）、Split CIFAR-100（10任务）、CIFAR-100 Superclass（20任务）、5-Datasets（5个不同数据集组成）、Split TinyImageNet（40任务）。
  - 长期持续学习额外测试：Split TinyImageNet（40任务，已含）、Split CIFAR-100-50（50任务，每个任务2类）。
- **评估指标**：平均准确率 ACC（%），以及反向迁移 BWT（%）（衡量遗忘程度）。
- **对比方法**：
  - 正则化方法：EWC。
  - 参数剪枝／分配方法：PackNet、SupSup、WSN。
  - 正交投影方法：GPM、TRGP、Connector、DualGPM、API、DFGP。
  - 其他：La-MaML、FS-DGPM。
- **实验设置**：模型架构与超参严格遵循 WSN 等基线，公平对比。

### 4. 资源与算力
- **GPU 配置**：所有实验在 **四块 NVIDIA 2080Ti GPU** 上使用 PyTorch 实现。
- **训练时长**：论文未提及具体总训练时间，但给出了各数据集的训练 epoch 数（如 PMNIST 15 个 epoch，CIFAR-100 50 个 epoch，5-Datasets 80 个 epoch，TinyImageNet 40 个 epoch），批量大小和学习率等均有说明，但无整体时钟时间报告。

### 5. 实验数量与充分性
- **实验组数**：
  - 5个主流数据集 + 2个长期设置。
  - 主要对比表（Table 1）涵盖 13 种方法 × 5 个数据集。
  - 消融实验：验证各组件（剪枝、网络分区、正交投影、锐度感知正交投影）的贡献（Table 3）。
  - 网络容量（CAP）对比（Table 2）。
  - 模型可塑性分析：对比 OSN 与 WSN 在不同任务数下的对角线 ACC（Figure 3）。
  - 不同稀疏比 c 的性能对比（Figure 5）。
  - 共享参数选取比例 k 的敏感性分析（Figure 4）。
- **充分性与公平性**：实验设计完整，对比方法全面，数据集覆盖不同规模和任务划分，消融分析合理，严格遵循已有工作的设置，结果报告了均值和标准差，可信度高。

### 6. 论文的主要结论与发现
- 引入共享参数第三部分，通过正交稀疏网络有效探索新旧任务间的共享知识，极大缓解了长期持续学习中的欠拟合问题。
- OSN 在多个数据集上实现了**几乎无遗忘（BWT ≈ 0）**，并大幅提升模型可塑性和容量，在 ACC 上全面超越现有 SOTA，尤其在长期持续学习（40 任务和 50 任务）中优势显著（Split TinyImageNet 上 ACC 提升 3.46%）。
- 共享参数的数量调节可以实现稳定性与可塑性的某种权衡，选择合适的比例可进一步优化性能。
- 锐度感知正交投影相较传统近似正交投影能更好地保持旧任务性能，提升共享知识学习效果。

### 7. 优点
- **创新性强**：首次在基于剪枝的持续学习方法中明确提出“共享知识”概念，并将网络三分，打破了旧任务子网络垄断参数的局限。
- **技术扎实**：两阶段共享参数选取（剪枝 + 重要性评估）、正交投影更新、锐度感知优化环环相扣，理论依据和实现清晰。
- **性能突出**：在多项基准上达到 SOTA，尤其在长期持续学习任务中表现优异，同时 BWT 极低，成功兼顾稳定性与可塑性。
- **可解释性好**：通过容量（CAP）、对角线 ACC、BWT 及消融实验等多角度分析，验证了各组件的有效性。

### 8. 不足与局限
- **依赖任务标识**：方法主要面向**任务增量学习（TIL）**，需要已知任务 ID 来选择对应的掩码和投影矩阵，不能直接用于无任务标识的类增量学习（CIL）。
- **存储开销**：需要为每一个旧任务保存掩码和特征空间投影矩阵，随着任务数增加，存储成本线性增长（虽然经过压缩）。
- **计算复杂度**：共享参数重要性评估和正交投影矩阵的 SVD 更新会增加训练开销，论文未讨论训练时间开销对比。
- **数据增强与锐度感知参数敏感**：mixup 权重 γ 和扰动半径 ρ 等超参可能需要仔细调优，对性能有影响。
- **理论假设局限**：正交投影保持旧任务输出的理论基于线性近似，对深层非线性网络可能存在误差，实际中 BWT 并非绝对 0，实验显示仍有极少量遗忘（如 -0.01%）。

（完）
