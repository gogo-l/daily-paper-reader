---
title: Mitigating Plasticity Loss in Continual Reinforcement Learning by Reducing Churn
title_zh: 通过减少输出波动缓解持续强化学习中的可塑性损失
authors: "Hongyao Tang, Johan Obando-Ceron, Pablo Samuel Castro, Aaron Courville, Glen Berseth"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=EkoFXfSauv"
tags: ["query:continual"]
score: 10.0
evidence: 降低输出波动缓解持续强化学习可塑性损失
tldr: 深度持续强化学习中可塑性丧失限制智能体适应新任务，该工作从神经切线核秩下降角度揭示输出波动（churn）加剧与可塑性下降相关，提出连续波动近似降低算法（C-CHAIN）自适应调整梯度步长，在多种持续学习和环境适应任务中超越基线方法，证实降低输出波动是保持网络可塑性的有效手段。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 524, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 826, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 804, \"height\": 1095, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 1089, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1773, \"height\": 318, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 806, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 814, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 790, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1247, \"height\": 1382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1240, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1407, \"height\": 1386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1407, \"height\": 1765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1404, \"height\": 1795, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ekofxfsauv/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1413, \"height\": 1807, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 590, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1660, \"height\": 325, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1790, \"height\": 751, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 852, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 556, \"height\": 108, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1730, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1273, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 741, \"height\": 564, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ekofxfsauv/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 886, \"height\": 250, \"label\": \"Table\"}]"
motivation: 持续RL中可塑性丧失阻碍新任务学习。
method: 分析NTK秩下降与输出波动关系，提出C-CHAIN降低波动。
result: 在多种持续学习场景中提升性能，超越基线。
conclusion: 降低输出波动是保持持续学习可塑性的有效策略。
---

## Abstract
Plasticity, or the ability of an agent to adapt to new tasks, environments, or distributions, is crucial for continual learning. In this paper, we study the loss of plasticity in deep continual RL from the lens of churn: network output variability induced by the data in each training batch. We demonstrate that (1) the loss of plasticity is accompanied by the exacerbation of churn due to the gradual rank decrease of the Neural Tangent Kernel (NTK) matrix; (2) reducing churn helps prevent rank collapse and adjusts the step size of regular RL gradients adaptively. Moreover, we introduce Continual Churn Approximated Reduction (C-CHAIN) and demonstrate it improves learning performance and outperforms baselines in a diverse range of continual learning environments on OpenAI Gym Control, ProcGen, DeepMind Control Suite, and MinAtar benchmarks.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：在深度持续强化学习（Continual RL）中，智能体在学习一系列变化的任务时，会逐渐丧失适应新数据或新目标的能力，这种现象被称为“可塑性丧失”（loss of plasticity）。  
- **研究动机**：已有研究指出神经元死亡、梯度秩下降等是可塑性丧失的潜在表现，但其根本因果机制尚不明确。本文从**输出波动（churn）** 的角度切入，即小批量训练时网络对未参与更新的“参考数据”所产生的输出变化，旨在揭示可塑性丧失与输出波动加剧之间的内在联系，并探索通过减少输出波动来维持可塑性的方法。

### 2. 论文提出的方法论
- **核心思想**：通过神经正切核（NTK）矩阵建立输出波动与可塑性丧失的形式化桥梁，指出任务序列变化会导致 NTK 秩逐渐降低、梯度间相关性增强，进而加剧输出波动并形成恶性循环。为此，提出**连续输出波动近似降低（Continual Churn Approximated Reduction, C‑CHAIN）** 方法，在正常训练的同时不断抑制对参考数据的输出波动。
- **关键技术细节**：
  - 定义输出波动 \(C_f(\bar{x},\theta,\Delta\theta) = f_{\theta'}(\bar{x}) - f_{\theta}(\bar{x})\)，并利用一阶泰勒展开将其与 NTK 矩阵 \(N_\theta\) 关联：\(C_f(\bar{x},\theta,\Delta\theta) \approx -\eta\, N_\theta(\bar{x},x)\,\nabla_{f_\theta}L(\theta,x)\)。
  - 分析表明，持续学习过程中 NTK 秩下降会使输出波动加剧，反之，降低输出波动有助于阻止秩坍塌并自适应调整常规 RL 梯度的步长。
  - C‑CHAIN 在实际算法中，从经验回放缓冲区采样与训练批次 \(B_{\text{train}}\) 不重叠的参考批次 \(B_{\text{ref}}\)，额外最小化输出波动的平方损失：\(\mathcal{L}_{\text{cr}}^f(\theta) = \frac{1}{2}\mathbb{E}_{\bar{x}\in B_{\text{ref}}}\left[ C_f(\bar{x},\theta,\Delta\theta)^2\right]\)。
  - 理论分解显示，该正则化项产生两种效应：① 抑制 NTK 矩阵的非对角线项，实现梯度去相关（对应公式中的 ① 项，依赖于 Hessian‑like 梯度）；② 利用参考数据梯度信息对原始训练梯度进行投影缩放，自适应调节有效步长（对应公式中的 ② 项，以 TD 学习为例表现为投影与缩放）。
- **算法流程（文字概括）**：在每一个交互步，智能体收集数据并更新经验缓冲区；根据所在 RL 算法（如 PPO）计算常规参数更新 \(\Delta\theta\)；同时从缓冲区采样参考批次，计算输出波动正则化损失并反向传播，完成一次联合更新。此过程无需显式任务边界检测，也不依赖跨任务缓冲区。

### 3. 实验设计
- **数据集/场景**：
  - OpenAI Gym Control：CartPole‑v1、Acrobot‑v1、LunarLander‑v2、MountainCar‑v0，每个环境通过为每个任务采样唯一的观测噪声构建任务序列（共 10 个任务，MountainCar 为 5 个）。
  - ProcGen：全部 16 个环境，每个任务为程序生成的不同关卡（5 个任务，每任务 2M 步）。
  - DeepMind Control Suite（DMC）：构建了 Walker（站立→走→跑）、Quadruped（走→跑→走）、Dog（站立→走→跑→小跑）三种连续控制任务链。
  - MinAtar：连续任务串联 SpaceInvaders、Asterix、Seaquest。
  - 监督学习对照：RandomLabel‑MNIST 和 Permuted‑MNIST。
- **对比方法**：Vanilla PPO/DoubleDQN、Oracle（每任务重新初始化）、TRAC、Weight Clipping、L2 Init（Regenerative Regularization）、LayerNorm、ReDo（Recycles Dormant Neurons）、AdamRel（相对时间步 Adam）。
- **评价指标**：以任务序列上的平均性能 \( \bar{J}(\mathbb{T}) \) 作为主要指标，并使用 Reliable metrics（中位数、IQM、最优性差距等）进行聚合评价。

### 4. 资源与算力
- 文中明确说明：每项 Gym Control 和 ProcGen 实验分配**单个 V100 GPU、16 个 CPU、32 GB 内存**；Gym Control 任务训练时间约**4 小时**，ProcGen 约**20 小时**。其他环境（DMC、MinAtar）的 GPU 及资源未单独列出，但整体实验均在类似计算条件下完成。

### 5. 实验数量与充分性
- **主实验数量**：
  - 4 个 Gym Control 环境 × 6 种对比方法 × 6 个随机种子。
  - 16 个 ProcGen 环境 × 9 种方法 × 6 个种子，共 864 次独立运行，并用高可靠性统计指标汇总。
  - 3 种 DMC 连续任务链（每链 3–4 个子任务）× 3 种方法 × 12 个种子。
  - 1 个 MinAtar 任务序列 × 2 种方法 × 12 个种子。
  - 2 个监督学习任务 × 3 种方法 × 3 个种子。
  - 额外包含 NTK 演化分析、C‑CHAIN 梯度分解消融（仅正交分量/仅投影分量）等深入剖析实验。
- **充分性与公平性**：实验覆盖离散/连续控制、程序生成环境、不同底层算法（PPO、DoubleDQN）以及监督学习，任务多样性高；所有对比方法均在同一代码基（TRAC 官方实现）上实现，超参数统一或经单独搜索，评价维度丰富（学习曲线、聚合指标、NTK 结构分析），整体实验设计系统、客观且公平。

### 6. 论文的主要结论与发现
- 输出波动（churn）与可塑性丧失密切相关：任务不断切换时，NTK 矩阵的秩逐渐下降，梯度高度相关，导致输出波动加剧，学习动力学不稳定，最终表现为可塑性丧失。
- 通过 C‑CHAIN 持续降低输出波动，可以有效阻止 NTK 秩坍塌，保持梯度多样性，并自适应调节 RL 梯度步长，从而显著缓解可塑性丧失。
- 在 Gym Control、ProcGen、DMC、MinAtar 等多种持续强化学习场景中，C‑CHAIN 在平均性能和聚合指标上均优于现有方法（包括 TRAC、Weight Clipping、L2 Init 等），甚至在某些任务上超越单任务重置的 Oracle 基准。
- 在简单的监督学习基准（RandomLabel‑MNIST、Permuted‑MNIST）上，C‑CHAIN 优势有限，暗示其专门针对 RL 中由链式效应导致的累积性输出波动问题更为有效。

### 7. 优点
- **新颖的视角**：首次从输出波动与 NTK 结构的角度系统解释持续 RL 中的可塑性丧失，提供了清晰的理论框架。
- **理论与实践的紧密结合**：通过公式推导揭示 C‑CHAIN 的双重效应（梯度去相关与步长调整），并给出直观的代数解释。
- **方法普适且易集成**：C‑CHAIN 无需任务边界信号，可作为任何标准 RL 算法（PPO、DoubleDQN）的即插即用模块，在离散和连续控制中均展现出良好效果。
- **实验全面扎实**：跨越多个 benchmark 和不同的任务构建方式，引入高可靠性统计指标，并通过 NTK 可视化、消融实验等深度支撑理论主张，说服力强。

### 8. 不足与局限
- **监督学习场景效果有限**：在 MNIST 类易拟合任务上，C‑CHAIN 未能像 L2 Init 和 Weight Clipping 那样大幅提升性能，表明其解决的问题更聚焦于 RL 特有的非稳态累积效应，在更一般的持续监督学习中的适用性有待进一步检验。
- **部分任务早期性能较低**：在探索要求较高的环境（如 MountainCar）中，C‑CHAIN 早期学习较慢，可能与减少输出波动同时减缓了探索行为的泛化有关，需更精细的权衡策略。
- **未在更大规模模型（如 Transformer、LLM）或真实机器人上验证**，其在高维复杂非线性网络中的表现及计算开销尚未讨论。
- **数学推导依赖一阶近似和 NTK 假设**，在处理具有强非线性和长时程依赖的网络时，所揭示的效应可能与实际有所偏差。

（完）
