---
title: "Unlocking the Power of Rehearsal in Continual Learning: A Theoretical Perspective"
title_zh: 解锁复述在持续学习中的潜力：一个理论视角
authors: "Junze Deng, Qinhang Wu, Peizhong Ju, Sen Lin, Yingbin Liang, Ness Shroff"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=p6nhzZ9ilZ"
tags: ["query:continual"]
score: 9.0
evidence: 复述方法解决灾难性遗忘，比较顺序与并行复述
tldr: 本文对持续学习中的复述策略进行理论分析，探讨顺序复述是否比常用的并行复述更有效。受人类学习启发，在过参数化线性模型上对比两种策略：将新旧数据一起训练的并行复述，与依次回顾旧任务的顺序复述。通过推导泛化误差，研究发现顺序复述在特定条件下更有利于缓解灾难性遗忘。该工作为复述方法的设计提供了理论指导，有助于提升持续学习的稳定性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 862, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 825, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 831, \"height\": 1110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1667, \"height\": 176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1670, \"height\": 178, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1667, \"height\": 175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-p6nhzz9ilz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1669, \"height\": 178, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 594, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 524, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 854, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 845, \"height\": 506, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1694, \"height\": 623, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1778, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-p6nhzz9ilz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1148, \"height\": 507, \"label\": \"Table\"}]"
motivation: 复述方法在持续学习中效果显著，但最优策略尚不明确。
method: 对过参数化线性模型中的并行复述和顺序复述进行理论分析。
result: 证明顺序复述在某些条件下比并行复述更有效。
conclusion: 为持续学习的复述策略设计提供了理论依据。
---

## Abstract
Rehearsal-based methods have shown superior performance in addressing catastrophic forgetting in continual learning (CL) by storing and training on a subset of past data alongside new data in current task. While such a concurrent rehearsal strategy is widely used, it remains unclear if this approach is always optimal. Inspired by human learning, where sequentially revisiting tasks helps mitigate forgetting, we explore whether sequential rehearsal can offer greater benefits for CL compared to standard concurrent rehearsal. To address this question, we conduct a theoretical analysis of rehearsal-based CL in overparameterized linear models, comparing two strategies: 1) Concurrent Rehearsal, where past and new data are trained together, and 2) Sequential Rehearsal, where new data is trained first, followed by revisiting past data sequentially. By explicitly characterizing forgetting and generalization error, we show that sequential rehearsal performs better when tasks are less similar. These insights further motivate a novel Hybrid Rehearsal method, which trains similar tasks concurrently and revisits dissimilar tasks sequentially. We characterize its forgetting and generalization performance, and our experiments with deep neural networks further confirm that the hybrid approach outperforms standard concurrent rehearsal. This work provides the first comprehensive theoretical analysis of rehearsal-based CL.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
持续学习（CL）希望智能体能够顺序学习多个任务而不遗忘旧知识。基于复述（rehearsal）的方法通过存储并回放旧数据的子集，是当前缓解灾难性遗忘的SOTA方案。然而，最常用的 **并发复述（concurrent rehearsal）** 策略（将新旧数据混合训练）是否总是最优仍是一个开放问题。  
受人类学习启发（学生按顺序复习不同科目），本文从理论角度探索一种新的 **顺序复述（sequential rehearsal）** 策略：先充分学习新任务，再依次逐个回顾旧任务。核心目标是回答：**顺序复述在何种条件下优于并发复述？** 由此进一步指导实际算法设计，为复述式CL建立首个完整的理论分析框架。

## 2. 论文提出的方法论
- **理论模型**：采用过参数化线性回归设置（特征维度 $p >$ 训练样本数），任务依次到达，记忆缓冲区等量分配给所有旧任务，训练优化收敛到最小范数解。
- **两种复述策略的形式化**：
  - **并发复述**：在任务 $t$ 上，同时在新数据 $D_t$ 和记忆数据 $M_t$ 上训练，使参数接近初始点。
  - **顺序复述**：先仅在 $D_t$ 上训练得到中间点，然后按照从旧到新的顺序，依次在对应的记忆数据集 $M_{t,h}$ 上微调。
- **性能指标**：定义模型误差 $L_i(w)=\|w - w^*_i\|^2$，进一步定义 **遗忘** $F_T$（旧任务误差的平均增长）和 **泛化误差** $G_T$（全部任务最终误差的平均值）。
- **核心理论结果**：
  - 给出两种策略下 $F_T$ 和 $G_T$ 的显示期望表达式（定理 5.1），它们具有相同结构：由基线误差项、任务相似度（参数 $\|w^*_j-w^*_k\|^2$）相关项与噪声项组成。
  - 当任务相似度较低时，顺序复述的相似度项系数更小，因此在遗忘和泛化误差上可能更优（定理 5.3 两任务情形，定理 5.5 多任务极端不相似例子）。
- **混合复述（Hybrid Rehearsal）算法**：根据梯度余弦相似度将旧任务分为相似组和相异组。对相似任务采用并发训练，对相异任务在新任务训练后逐一顺序回顾（算法1）。理论推广给出其系数表达式（附录H）。

## 3. 实验设计
### 数据集与场景
- **线性仿真**：构造 $T=5$ 个任务，控制任务参数之间的距离（任务间隔）从 0 到 2.0，验证两种复述策略的预测与实际表现（图2）。
- **深度神经网络实验**：
  - **Split-CIFAR-10**、**Split-CIFAR-100**、**Split-TinyImagenet200**：将原数据集类别随机划分为 $5$ 个任务，同时构造 **Corrupted** 变体（对其中一个任务施加图像损坏）以增大任务间差异。
  - 额外包含 **Split-MNIST**、更长的任务序列（20 任务）以及标签损坏比例控制实验（5%, 10%, 20% 标签重分配）。
### Benchmark 比较
- 主要对比 **并发复述** 与 **混合复述**（即本文提出的方法）。
- 两种方法均使用相同的记忆缓冲区大小、ResNet‑18 骨干网络（Split‑MNIST 使用 MLP）、SGD 优化器和 StepLR 调度器。
- 评估指标：最终平均准确率（Acc ↑）和最终平均遗忘（F_gt ↓）。

## 4. 资源与算力
论文在附录 A.1 中列出了实验硬件配置：
- 操作系统：Red Hat Enterprise Linux Server 7.9
- CPU：2.4 GHz 14‑Core Intel Xeon E5‑2680 v4
- GPU：NVIDIA P100 “Pascal” GPU，16 GB 显存

文中 **未明确说明** 使用的 GPU 数量、单次实验的训练时长及总计算开销，但给出了上述硬件型号与规格。

## 5. 实验数量与充分性
实验设计较为充分，覆盖了多个维度：
- **理论验证**：1 组仿真实验（5 个任务，变化任务间隔），对比理论预测与模拟值。
- **标准数据集**：3 个数据集（CIFAR‑10/100, TinyImagenet200），每组 5 任务，各重复 10 次独立运行，报告均值和标准差。
- **任务差异性扩展**：对每个数据集构造损坏版本（Corrupted），共 3 组，验证理论中“任务越不相似，混合复述优势越大”的推断。
- **长序列实验**：Split‑CIFAR‑100 和 TinyImagenet200 上 20 任务设定，5 次独立运行。
- **相似度控制实验**：通过控制标签损坏比例（5%,10%,20%）以及 Different 数量的损坏任务，进一步测试相似度的影响（5 次独立运行）。
- **额外数据集**：Split‑MNIST 及其损坏版本。
- **消融/对比公平性**：并发复述与混合复述采用相同的缓冲大小、模型、优化器；混合复述中的相似/相异划分基于梯度余弦相似度并设定阈值，未经过细致调优，但旨在验证理论启发的有效性。

总体看，实验数量充足、对比公平，较好地支持了理论结论。

## 6. 论文的主要结论与发现
- **顺序复述的理论优势**：当任务间差异较大时，顺序复述相比并发复述能产生更低的遗忘和泛化误差；任务越不相似，优势越明显。
- **混合方法的有效性**：将顺序复述融入并发复述形成的混合策略，在深度神经网络上一致优于纯并发复述，尤其在任务差异大（如数据损坏）时性能提升更显著，例如在 Corrupted Split‑TinyImagenet200 上准确率提升 +2.38%，遗忘降低 −13.32%。
- **任务相似度的作用规律**：通过控制标签损坏比例或损坏任务数量，实验显示性能增益随任务相异性增加而扩大，与理论预测吻合。
- **首个系统性理论分析**：给出了显式遗忘和泛化误差表达式，为复述策略的设计提供了理论依据。

## 7. 优点
- **理论贡献突出**：首次对复述式CL进行严格理论分析，推导出两种策略的期望性能闭合解，明确揭示了任务相似度、记忆大小等因素的作用。
- **创新性策略**：提出顺序复述新范式，并基于理论洞察设计出简单有效的混合算法，无需复杂额外机制。
- **理论与实验相互印证**：仿真与深度网络实验一致表明顺序复述在低相似任务上的优势，且混合方法泛化良好。
- **分析维度丰富**：不仅比较策略，还考虑噪声、记忆分配、多任务扩展等，为后续研究提供了可参考的数学框架。

## 8. 不足与局限
- **理论假设限制实际推广**：分析建立在过参数化线性回归、等量记忆分配、数据新鲜未重用等严格假设上，对深度非线性的准确预测仍有距离。
- **顺序复述的顺序未优化**：文中仅按从旧到新顺序回顾，更优的复习顺序设计是重要开放问题。
- **相似度度量与阈值依赖**：混合方法依赖手动设定的梯度余弦相似度阈值，其鲁棒性未被充分讨论，且未比较其他相似度度量方式。
- **实验规模与任务类型**：仅使用图像分类任务和单一任务增量设定；训练细节（如记忆大小固定）未做全面消融；未与其他非复述类 CL 方法（如正则化、投影）对比混合方法的绝对性能。
- **计算开销未分析**：顺序复述比并发复述增加了额外的微调步骤，文中未讨论其对训练时间或显存的影响。

（完）
