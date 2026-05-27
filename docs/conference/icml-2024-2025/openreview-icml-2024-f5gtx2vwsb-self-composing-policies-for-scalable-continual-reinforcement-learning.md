---
title: Self-Composing Policies for Scalable Continual Reinforcement Learning
title_zh: 面向可扩展持续强化学习的自组合策略
authors: "Mikel Malagon, Josu Ceberio, Jose A. Lozano"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=f5gtX2VWSB"
tags: ["query:continual"]
score: 9.0
evidence: 模块化网络架构防止持续强化学习中的灾难性遗忘
tldr: 本文提出自组合策略，采用可增长的模块化网络架构，各模块可选择性结合先前策略及内部策略，自然避免灾难性遗忘和干扰，加速当前任务学习。实验在连续控制和视觉问题上表明，该方法参数量随任务线性增长而不牺牲可塑性，实现了优于已有方法的知识迁移和性能，为持续强化学习的可扩展性提供了新方向。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1780, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1616, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 811, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1786, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1367, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 813, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 790, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 819, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1484, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1795, \"height\": 1454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1615, \"height\": 1299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1788, \"height\": 1439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1789, \"height\": 1441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1793, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1504, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 908, \"height\": 682, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1068, \"height\": 910, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 987, \"height\": 840, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1729, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1752, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 146, \"label\": \"Table\"}]"
motivation: 持续强化学习中遗忘和干扰阻碍智能体长期学习，现有增长型网络方法可塑性不足。
method: 设计模块化网络，每个模块允许选择性组合先前策略与内部策略，线性增长参数。
result: 在基准测试中超越其他方法，实现知识迁移和持续学习。
conclusion: 自组合策略在不牺牲可塑性的前提下实现可扩展的持续强化学习。
---

## Abstract
This work introduces a growable and modular neural network architecture that naturally avoids catastrophic forgetting and interference in continual reinforcement learning. The structure of each module allows the selective combination of previous policies along with its internal policy accelerating the learning process on the current task. Unlike previous growing neural network approaches, we show that the number of parameters of the proposed approach grows linearly with respect to the number of tasks, and does not sacrifice plasticity to scale. Experiments conducted in benchmark continuous control and visual problems reveal that the proposed approach achieves greater knowledge transfer and performance than alternative methods.

---

## 论文详细总结（自动生成）

# 论文总结：自组合策略：面向可扩展持续强化学习

## 1. 核心问题与研究动机
- 持续强化学习（CRL）要求智能体在连续的任务流中不断学习、复用并迁移知识，避免灾难性遗忘与任务间干扰。
- 已有增长型神经网络（如 Progressive Nets）通过为每项任务新增模块来保留旧知识，但参数量通常呈二次增长，且推理成本高，难以扩展。
- 参数固化或屏蔽类方法（如 PackNet）虽能控制遗忘，却常常牺牲可塑性，面临稳定性-可塑性两难。
- 本研究旨在提出一种新的可增长模块化架构，既自然避免遗忘，又能线性增长参数、保持可塑性，同时无需额外组合网络即可实现策略复用与迁移。

## 2. 方法论
### 2.1 整体架构：CompoNet
- 每遇到一项新任务，冻结旧模块参数，新增一个可训练的“自组合策略模块”。
- 新模块接收当前环境状态 `s` 及所有先前模块的输出矩阵 `Φ_{k;s}`（大小为 (k-1) × |A|），输出动作分布。
- 该架构形成级联图结构，随任务数增加深度自动增长。

### 2.2 自组合策略模块内部结构（图2）
每个模块包含三个部分：

**输出注意力头**  
- 基于当前编码状态 `h_s`，对先前策略输出进行注意力加权组合，生成试探性向量 `v`。
- 查询 `q = h_s W^Q_out`，键 `K = (Φ + E_out) W^K_out`，值 `V = Φ`，使用缩放点积注意力得到 `v`。
- 该结构允许直接复用高相关度的旧策略。

**输入注意力头**  
- 输入为 `h_s` 以及由 `v` 与 `Φ` 行拼接得到的矩阵 `P`。
- 通过可学习的线性变换生成 `q`、`K`、`V`，同样执行注意力运算，输出上下文向量。
- 作用是为内部策略提供有关先前策略与试探输出的关键特征。

**内部策略**  
- 由前馈多层感知机组成，输入为输入注意力头的输出和 `h_s`，输出一个与 `v` 同维的修正向量。
- 最终模块输出 = `v` + 内部策略输出（在连续动作下可能经归一化）。
- 残差结构使其既可保留试探结果，也可从头学习全新策略。

### 2.3 应对三种任务场景
- **场景(i)：** 旧策略可直接解决新任务 → 输出注意力头高度关注该旧策略，内部策略输出接近零，模块直接复用。
- **场景(ii)：** 新任务可由旧策略的某种函数表示 → 三个组件协同学习该组合函数。
- **场景(iii)：** 新任务与旧策略完全无关 → 内部策略主导输出，覆盖输出注意力头结果，实现无干扰从头学起。

### 2.4 计算特性
- 单模块参数量为常数，总参数量随任务数 `n` 呈 **线性增长 O(n)**。
- 推理时单个模块复杂度 `O(n)`，整体序列计算复杂度 `O(n²)`，但实测在 300 个任务内未见明显二次增长趋势，推理效率远优于 Progressive Nets。

## 3. 实验设计
### 3.1 任务序列与基准
- **Meta-World 序列**（连续控制）：20 个机械臂操作任务（10 种任务各重复一次），状态 39 维，动作 4 维，每任务分配 `1M` 步，使用 SAC 算法。
- **SpaceInvaders 序列**（视觉离散控制）：10 种游戏模式，图像输入（210×160），动作离散 6 维，每任务 `1M` 步，使用 PPO 算法。
- **Freeway 序列**（视觉离散控制）：7 种游戏模式，动作 3 维，每任务 `1M` 步，使用 PPO 算法。

### 3.2 对比方法
- **Baseline**：每任务从零训练一个随机初始化网络。
- **FT-1**：持续微调单一网络（不防遗忘）。
- **FT-N**：每任务结束后保存模型，再微调同一网络，仅靠保存防遗忘。
- **ProgressiveNet**：类似 CompoNet 的增长型网络（侧向连接），但参数量二次增长。
- **PackNet**：通过迭代剪枝在同一网络中固化各任务参数，需预知任务总数 N。

### 3.3 评价指标
- 平均性能 `P(T)`（训练结束时各任务成功率均值）。
- 前向迁移 `FTr_i`：相对于从零训练基线的归一化面积差，衡量知识迁移增益。
- 参考前向迁移 `RT`：基于两两任务微调的最大迁移值，作为方法应至少达到的基线。

## 4. 资源与算力
- 实验在两个集群节点上进行：
  - 8 × RTX3090 GPU + Intel Xeon Silver 4210R CPU + 345GB RAM
  - 8 × Nvidia A5000 GPU + AMD EPYC 7252 CPU + 377GB RAM
- 训练时间：SpaceInvaders 和 Freeway 每任务约 1.5 小时；Meta-World 每任务约 3 小时。

## 5. 实验数量与充分性
- 在三个任务序列上对 5 种方法进行了完整对比，每个方法跑 10 个随机种子，结果以均值和标准差报告。
- 针对 CompoNet 进行了专门验证实验（架构验证）：
  - 场景(i) 验证（含已训练当前任务模块的利用效率）。
  - 场景(iii) 验证（全随机旧模块下的学习能力）。
  - 消融实验：移除输出注意力头或输入注意力头，分析组件贡献。
- 扩展性测试：模拟 49~511 个非信息旧模块时注意力的聚焦能力。
- 实验覆盖了连续控制、视觉离散任务以及不同难易度，对比基线选择适当，公平性较好。

## 6. 主要结论与发现
- CompoNet 在所有三个序列上都取得了最高的平均性能和前向迁移，且是唯一在 Meta-World 上实现正向前移植的模型（无干扰），证明其鲁棒性。
- 在各序列中均超越了参考前向迁移 `RT`，说明不仅能利用单个最佳迁移源，还能通过组合多个旧任务的知识来获得额外增益。
- 该架构能够根据任务关系自动在“复用旧策略”、“学习组合函数”和“从头学起”三种模式间切换，且对大量非相关旧模块不敏感。

## 7. 优点
- **避免遗忘**：模块参数冻结，自然无遗忘。
- **保持可塑性**：新模块可自由学习，不受旧参数约束。
- **线性参数增长**：显著优于 ProgressiveNet 等二次增长方法，易于扩展。
- **自组合机制**：无需额外训练的组合网络，模块通过注意力自主决定如何利用此前策略，训练稳定。
- **灵活的迁移**：既能直接复用，又能学习组合，还能在无关时独立从头学习，适应性强。
- **实验扎实**：包含多种环境与测度，附带充分的消融与压力测试。

## 8. 不足与局限
- 依赖任务边界和标识已知的假设（常见于 CRL 文献），未来需集成自动任务切换机制。
- 推理的理论复杂度为 O(n²)，在极多任务（如数千）时可能成为瓶颈；文中只测到了 300 个任务，并建议可结合量化、知识蒸馏等措施。
- 状态编码策略要求任务间状态空间大致相同，对跨不同模态或域的任务尚不适用（除非使用统一预训练编码器，文中仅简单探讨了 ViT 可行性）。
- 在真实世界、非平稳流任务中的验证有待开展；目前仅限于 benchmark 序列。
- 实验未涵盖在任务数量远超 512 时的注意力退化程度，仅对最多 512 个模块进行了测试。

（完）
