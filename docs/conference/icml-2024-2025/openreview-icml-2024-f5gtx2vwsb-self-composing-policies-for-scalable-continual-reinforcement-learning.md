---
title: Self-Composing Policies for Scalable Continual Reinforcement Learning
title_zh: 自组合策略实现可扩展的持续强化学习
authors: "Mikel Malagon, Josu Ceberio, Jose A. Lozano"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=f5gtX2VWSB"
tags: ["query:continual"]
score: 9.0
evidence: 可增长的模块化架构用于持续强化学习避免灾难性遗忘
tldr: 针对持续强化学习中的灾难性遗忘和干扰问题，提出一种自组合的可增长模块化神经网络架构，通过选择性组合先前策略和内部策略加速当前任务学习。参数数量随任务线性增长，不牺牲可塑性，实验表明该方法在知识迁移和性能上优于其他方法。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1780, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1616, \"height\": 328, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 811, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1786, \"height\": 637, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1367, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 813, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 790, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 819, \"height\": 550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1484, \"height\": 420, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1795, \"height\": 1454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1615, \"height\": 1299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1788, \"height\": 1439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1789, \"height\": 1441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1793, \"height\": 921, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1504, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-f5gtx2vwsb/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 908, \"height\": 682, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1758, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 132, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1068, \"height\": 910, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 987, \"height\": 840, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1729, \"height\": 145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1752, \"height\": 146, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-f5gtx2vwsb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1447, \"height\": 146, \"label\": \"Table\"}]"
motivation: 现有持续强化学习方法在避免遗忘和干扰方面存在困难，尤其是基于增长的方法参数膨胀严重，需要更高效的模块化架构。
method: 提出可增长且模块化的神经网络架构，每个模块包含内部策略和选择性组合先前策略的机制，自然避免灾难性遗忘和干扰。
result: 在连续控制和视觉基准任务中，该方法参数线性增长，不仅没有牺牲可塑性，还实现了更好的知识迁移和性能。
conclusion: 自组合策略为持续强化学习提供了一种高效且可扩展的解决方案，在避免遗忘的同时保持了学习能力。
---

## Abstract
This work introduces a growable and modular neural network architecture that naturally avoids catastrophic forgetting and interference in continual reinforcement learning. The structure of each module allows the selective combination of previous policies along with its internal policy accelerating the learning process on the current task. Unlike previous growing neural network approaches, we show that the number of parameters of the proposed approach grows linearly with respect to the number of tasks, and does not sacrifice plasticity to scale. Experiments conducted in benchmark continuous control and visual problems reveal that the proposed approach achieves greater knowledge transfer and performance than alternative methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究背景**：在持续强化学习中，智能体需序贯学习多个任务，深度神经网络面临灾难性遗忘和干扰，即学习新任务会损害已有知识。
- **现有瓶颈**：现有可增长神经网络架构通过冻结旧参数、添加新模块避免遗忘，但参数规模随任务数量二次增长，严重限制可扩展性；部分方法通过剪枝或压缩折衷记忆与可塑性，导致学习新知识的能力下降。
- **本文目标**：提出一种新型可增长模块化架构，在避免遗忘与干扰的同时，使参数数量随任务数量**线性增长**，并保持对旧知识的复用能力和对新任务的学习塑性。

### 2. 方法论
- **核心思想**：构建**自组合策略模块（self-composing policy module）**，每个任务对应一个新模块，冻结旧模块后新模块可直接访问所有先前模块的输出，并自主学习如何选择性组合它们，无需额外控制器网络。
- **架构细节**：
  - **状态编码**：对于高维图像输入，每个模块可配备独立CNN编码器；低维向量可直接使用，从而保证输入分布一致性。
  - **模块内部三个子块**（如图）：
    1. **输出注意力头**：基于当前状态 \( h_s \) 对先前所有模块的输出矩阵 \( \Phi_{k;s} \) 进行注意力加权，生成一个试探性动作向量 \( v \)。
    2. **输入注意力头**：再次使用注意力机制，从先前模块输出和输出注意力头结果中提取信息，为内部策略提供上下文。
    3. **内部策略**：前馈多层感知机，以当前状态和输入注意力头输出为输入，产生一个修正向量，与试探向量 \( v \) 相加得到最终动作输出。
  - **工作原理**：
    - 若先前某策略可直接解决当前任务，输出注意力头将注意力集中在该模块，内部策略输出零，直接复用。
    - 若可通过函数组合解决，三个子块协同学习组合函数。
    - 若先前策略无关，内部策略重置并主导输出，忽略无关信息。
- **计算成本**：参数数量随任务数线性增长，推理时间在实验中直到300任务仍表现为准线性增长，显著优于渐进网络。

### 3. 实验设计
- **数据集与场景**：
  - **Meta-World 序列**：10种不同机器人操作任务重复两次（共20任务），连续控制，动作连续，状态低维向量。每任务1M步交互预算。
  - **Atari 游戏序列**：
    - *SpaceInvaders*：10种游戏模式，离散动作，图像观测（210×160），每任务1M步。
    - *Freeway*：7种游戏模式，类似设置。
- **优化算法**：Meta-World使用SAC，Atari使用PPO。
- **对比方法**：
  - Baseline：每任务从头训练。
  - FT-1：跨任务连续微调单网络。
  - FT-N：每任务保存模型副本，防止遗忘。
  - ProgressiveNet：经典渐进网络，横向连接增长，参数二次增长。
  - PackNet：利用剪枝和掩码在单网络中保存多任务策略。
- **评估指标**：最终成功率（Performance）、前向迁移（Forward Transfer）、参考前向迁移（RT）等。

### 4. 资源与算力
- **硬件配置**：
  - 两个集群节点：节点1含8块NVIDIA RTX3090 GPU、Intel Xeon Silver 4210R CPU、345GB内存；节点2含8块NVIDIA A5000 GPU、AMD EPYC 7252 CPU、377GB内存。
- **训练时长**：
  - SpaceInvaders和Freeway每任务约1.5小时；Meta-World每任务约3小时。
- 未详细说明总实验消耗的GPU时数，但提供了执行时间参考。

### 5. 实验数量与充分性
- **主体实验**：3个任务序列 × 6种方法 × 10个随机种子 → 至少180组独立运行。
- **消融研究**：
  - 移除输出注意力头对性能影响的消融。
  - 移除输入注意力头对信息提取能力的消融。
- **边界情形验证**：
  - 在先前策略包含可复用策略和随机策略时，展示架构能正确利用或忽略信息。
  - 在无信息场景中展现与从头训练相当的性能。
- **可扩展性测试**：分析参数规模、推理时间随任务数增至300的变化，以及注意力头在数百个非信息模块干扰下仍准确提取有效策略的能力。
- 实验覆盖连续控制、离散动作视觉任务，对比方法具有代表性，指标全面，评估客观公平。

### 6. 主要结论与发现
- CompoNet在三个任务序列上均取得最优或接近最优的最终性能和前向迁移，尤其在高干扰环境下显著优于其他方法。
- 架构能够有效复用先前知识、学习组合函数，并在无关任务中几乎不受干扰地从头学习。
- 参数数量线性增长，推理成本可接受，在多达300任务的序列中仍保持实用。
- 相比现有方法，CompoNet不牺牲塑性，避免了稳定性-可塑性困境。

### 7. 优点
- **自然避免遗忘**：冻结参数和模块化设计固有地解决遗忘和干扰。
- **高效迁移**：利用注意力机制直接组合先前策略，无需额外组合网络，实现自组合。
- **线性扩展性**：内存和参数线性增长，优于二次增长的渐进网络。
- **保持塑性**：无需压缩或剪枝，内部策略可自由覆盖无关信息。
- **实验全面**：在多种环境、任务类型上验证，并有充分的消融和可扩展性分析。

### 8. 不足与局限
- **假设限制**：要求任务边界和标识符已知，实时自动化添加模块仍需未来解决。
- **理论复杂度**：推理复杂度理论上为 \( O(n^2) \)，虽然实验显示准线性，但超大规模任务序列可能渐显瓶颈。
- **状态编码**：图像任务中每个模块需单独CNN，模块数量过多时存储成本不容忽视；文中虽提及可使用视觉基础模型作为统一编码器，但未深入验证。
- **任务类型覆盖**：测试仅在Meta-World和少数Atari游戏模式变化上，未探讨更广泛的任务变化（如奖励函数大幅改变、状态空间异构等）。
- **超参数与敏感度**：未分析架构超参数（如 \( d_{model} \)）对性能的敏感度，可能影响实际部署。
- **未完全避免遗忘影响**：对于微调基线等方法的遗忘指标分析显示CompoNet本身零遗忘，但其他方法存在遗忘，这符合设计前提，但现实应用中若无法准确检测任务边界，策略复用可能引入风险。

（完）
