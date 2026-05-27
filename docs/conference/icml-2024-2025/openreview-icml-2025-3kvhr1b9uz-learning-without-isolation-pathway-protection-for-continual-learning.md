---
title: "Learning without Isolation: Pathway Protection for Continual Learning"
title_zh: 无隔离学习：持续学习的通路保护
authors: "Zhikang Chen, Abudukelimu Wuerkaixi, Sen Cui, Haoxuan Li, Ding Li, Jingfeng Zhang, Bo Han, Gang Niu, Houfang Liu, Yi Yang, Sifan YANG, Changshui Zhang, Tianling Ren"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=3KVHR1b9UZ"
tags: ["query:continual"]
score: 10.0
evidence: 用于持续学习的通路保护，防止灾难性遗忘
tldr: 现有持续学习方法主要保护与旧任务相关的参数，但参数保护随着任务增加变得不切实际。本文受神经科学和物理学启发，提出保护网络中的通路而非参数来缓解灾难性遗忘。实验表明该方法能有效保留旧知识，为持续学习提供了一种更高效的知识留存机制。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1699, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 675, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1052, \"height\": 687, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-3kvhr1b9uz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 863, \"height\": 563, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1776, \"height\": 1088, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 859, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 858, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 865, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 738, \"height\": 153, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1104, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1102, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 993, \"height\": 371, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 994, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1764, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1765, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1423, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 984, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 982, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 980, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1767, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1767, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1450, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-3kvhr1b9uz/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1451, \"height\": 282, \"label\": \"Table\"}]"
motivation: 现有持续学习方法的参数保护面临存储效率低的问题，通路保护可能更关键。
method: 提出基于通路保护而非参数保护的持续学习方法，利用神经科学和物理学视角重新定义知识留存。
result: 实验证明通路保护能有效缓解灾难性遗忘，且参数效率更高。
conclusion: 通路保护为持续学习提供了一种新颖且高效的替代方案，强调网络连接结构的重要性。
---

## Abstract
Deep networks are prone to catastrophic forgetting during sequential task learning, i.e., losing the knowledge about old tasks upon learning new tasks. To this end, continual learning (CL) has emerged, whose existing methods focus mostly on regulating or protecting the parameters associated with the previous tasks. However, parameter protection is often impractical, since the size of parameters for storing the old-task knowledge increases linearly with the number of tasks, otherwise it is hard to preserve the parameters related to the old-task knowledge. In this work, we bring a dual opinion from neuroscience and physics to CL: in the whole networks, the pathways matter more than the parameters when concerning the knowledge acquired from the old tasks. Following this opinion, we propose a novel CL framework, learning without isolation (LwI), where model fusion is formulated as graph matching and the pathways occupied by the old tasks are protected without being isolated. Thanks to the sparsity of activation channels in a deep network, LwI can adaptively allocate available pathways for a new task, realizing pathway protection and addressing catastrophic forgetting in a parameter-effcient manner. Experiments on popular benchmark datasets demonstrate the superiority of the proposed LwI.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究背景**：深度网络在连续学习多个任务时，易发生灾难性遗忘 (catastrophic forgetting)，即学习新任务后旧任务性能急剧下降。
- **现有局限**：当前持续学习（Continual Learning, CL）方法主要聚焦于保护与旧任务相关的参数，但参数保护随任务数量线性增加存储开销，且难以有效保留所有旧任务知识，还导致任务间隔离，不利于信息共享。
- **核心观点**：受神经科学（大脑通过稀疏通路配置知识）与物理学启发，论文提出在持续学习中“通路 (pathway) 比参数更重要”的双重视角。即保护网络中数据流动的通路，而非仅保护个别参数，可更高效、自然地缓解灾难性遗忘。

## 2. 方法论
- **框架名称**：Learning without Isolation (LwI)
- **核心思想**：
  - 采用**模型融合**策略：为新任务训练一个新模型，再通过图匹配 (graph matching) 与旧模型融合，而非简单加权平均。
  - 使用**通路保护而非参数隔离**：在融合过程中，为不同任务分配不同的激活通路，避免重写旧任务知识。
- **关键技术细节**：
  - 将深度网络视为图：通道 (channel) 为节点，相邻层间连接为边。匹配仅在层内进行。
  - 相似度矩阵 \(K\) 基于边权重欧氏距离（或余弦相似度）计算：\(K[a,c,b,d]=\|e_{ac}-e_{bd}\|_2\)。
  - **浅层**：最大化相似度匹配，促进任务共性知识共享；**深层**：最小化相似度匹配（使用 \(-K\)），使不同任务走不同的通路，保护任务特异性。
  - 使用 **Sinkhorn 算法**（或匈牙利算法）求解软分配矩阵 \(P\)，逐层对齐通道。
  - 融合公式：\(W_{\text{fusion}}^{(l-1,l)} = k \cdot \hat{W}_{\text{o}}^{(l-1,l)} + (1-k) \cdot W_{\text{n}}^{(l-1,l)}\)，其中 \(\hat{W}_{\text{o}}\) 为对齐后的旧模型权重，\(k\) 为融合系数。
  - 训练时结合**知识蒸馏**（KL 散度）保持新旧模型输出分布一致，并利用旧模型作为预训练起点。
- **算法流程**：
  1. 新任务到来，训练新模型。
  2. 逐层计算匹配矩阵 \(P\)（浅层最大相似度，深层最小相似度）。
  3. 用 \(P\) 对齐旧模型权重后与新模型加权融合，得到合并模型作为后续旧模型。
  4. 重复上述过程，实现持续学习。

## 3. 实验设计
- **数据集**：
  - CIFAR-100（100类，划分成 5/10/20 splits）
  - Tiny-ImageNet（200类，划分成 5/10/20 splits）
- **网络架构**：
  - ResNet32（小模型，参数量约 0.47M）
  - ResNet18（大模型，参数量约 11.22M）
  - AlexNet（消融/补充实验）
- **基线方法**：
  - 正则化类：EWC、RWalk、LwF、SPG、SPU
  - 架构类（参数隔离）：GPM、WSN、SPU
  - 排练类（存储旧数据）：iCaRL（2000 exemplars）、LUCIR
- **评估指标**：
  - Task-agnostic accuracy（任务未知分类准确率，所有类候选统一比较）
  - Task-aware accuracy（任务已知，仅对应任务类内分类）
  - Forgetting rate（遗忘率）

## 4. 资源与算力
- **硬件环境**：使用 GeForce RTX 2080 Ti GPU 进行训练，CPU 为 Intel Xeon E5-2640 v4 @ 2.40GHz。
- **训练细节**：所有方法统一训练 200 epochs，batch size = 64，优化器 SGD（动量 0.9 或 0.0），学习率初值 0.1 并在 80/120 epochs 时衰减。
- **未明确说明**：未提供单次实验具体耗时或总 GPU 小时数。

## 5. 实验数量与充分性
- **实验组数**：
  - 3 种数据集×架构组合（CIFAR-100+ResNet32、CIFAR-100+ResNet18、Tiny-ImageNet+ResNet18）主实验，各含 3 种任务划分（5/10/20 splits）× 多个基线，约 27 组主要对比。
  - 补充实验：Tiny-ImageNet+ResNet32、CIFAR-100+AlexNet。
  - 遗忘率对比（ResNet18+CIFAR-100）。
  - 消融实验：
    - 不同深度层应用最小相似度匹配（1/2/3/4 层）
    - 是否使用任务分流模块（全部层最大相似度）
    - 相似度度量方式（欧氏距离 vs 余弦相似度）
    - 是否使用知识蒸馏（KD）模块
    - 不同任务数量（增至 100 tasks）
- **充分性与公平性判断**：实验涵盖小规模、大规模模型，不同任务划分，对比了主流三类方法（正则化、架构、排练），且消融实验系统验证了各模块贡献，整体设计较为充分、公平（统一训练超参，多次运行提供标准差）。

## 6. 主要结论与发现
- LwI 在 task-agnostic 和 task-aware 两种评估下均显著优于无排练的正则化方法和架构隔离方法（如 WSN），且在多数情况下超越排练方法。
- 模型容量越大（如 ResNet18 vs ResNet32），通路保护的优势越明显，表明其更充分利用了过参数化网络的稀疏性。
- 遗忘率显著低于对比方法，证明通路保护能有效保留旧知识且不对新任务学习造成负面干扰。

## 7. 亮点
- **视角新颖**：首次将“通路保护”系统性地引入持续学习，区别于传统参数隔离。
- **无需排练数据**：数据隐私友好，仅需历史模型，不存储旧数据。
- **任务间不隔离**：浅层共享、深层分化，促进正向迁移与个性保护，兼具合作性与特异性。
- **方法通用**：可适配不同架构，且任务未知场景下也表现优异。
- **实验全面**：多数据集、多模型、多划分，消融验证仔细。

## 8. 不足与局限
- **大模型验证缺失**：论文未在大型模型（如 Transformer、LLM）上验证，缺乏对实际大尺度应用的指导。
- **计算开销未优化**：图匹配算法虽然层内执行，但复杂度仍较高，未探讨加速策略或稀疏矩阵近似。
- **任务未知分类头不统一**：直接拼接各任务分类头可能导致类间混淆，影响 task-agnostic 性能，虽结果仍较好，但未提出专门对齐策略。
- **仅限图像分类**：实验局限于分类任务，未在更复杂的持续学习场景（如目标检测、分割）中验证。
- **融合系数敏感**：文中未详细讨论融合系数 \(k\) 的选取及其敏感性。

（完）
