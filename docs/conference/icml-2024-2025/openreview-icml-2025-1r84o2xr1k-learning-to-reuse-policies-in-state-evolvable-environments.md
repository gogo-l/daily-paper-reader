---
title: Learning to Reuse Policies in State Evolvable Environments
title_zh: 在状态可演化环境中学习策略重用
authors: "Ziqian Zhang, Bohan Yang, Lihe Li, Yuqi Bian, Ruiqi Xue, Feng Chen, Yi-Chen Li, Lei Yuan, Yang Yu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=1R84O2Xr1k"
tags: ["query:continual"]
score: 5.0
evidence: 通过策略重用适应状态特征演化
tldr: 强化学习策略依赖固定状态空间，但实际应用中传感器配置常发生演变，导致策略性能骤降。本文定义状态可演化强化学习（SERL），要求智能体在状态空间变化后迅速减轻性能损失。提出一种基于策略重用的方法，利用新旧状态间的结构关系，对已有策略进行组合与微调。实验结果显示，该方法在多种演变情景下显著优于训练传感器不变策略或从候选策略池中择优的基线，证明了策略重用是应对状态演化的有效手段，对工业自动化中传感器更新等场景具有实用价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1550, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1736, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 821, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 809, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 835, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1023, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1027, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1721, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 868, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1752, \"height\": 845, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1267, \"height\": 1316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1761, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1388, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1711, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1768, \"height\": 1110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1754, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 868, \"height\": 591, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-1r84o2xr1k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1r84o2xr1k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1744, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1r84o2xr1k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 732, \"height\": 1340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1r84o2xr1k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 914, \"height\": 832, \"label\": \"Table\"}]"
motivation: 传感器演变导致状态空间变化，预训练策略失效，现有方法难以保证性能。
method: 形式化SERL问题，提出策略重用方法，组合微调旧策略适应新状态空间。
result: 实验表明方法有效抑制性能退化，优于传感器不变策略及多策略选择方法。
conclusion: 策略重用为状态演变下的强化学习提供稳健自适应方案。
---

## Abstract
The policy trained via reinforcement learning (RL) makes decisions based on sensor-derived state features. It is common for state features to evolve for reasons such as periodic sensor maintenance or the addition of new sensors for performance improvement. The deployed policy fails in new state space when state features are unseen during training. Previous work tackles this challenge by training a sensor-invariant policy or generating multiple policies and selecting the appropriate one with limited samples. However, both directions struggle to guarantee the performance when faced with unpredictable evolutions. In this paper, we formalize this problem as state evolvable reinforcement learning (SERL), where the agent is required to mitigate policy degradation after state evolutions without costly exploration. We propose **Lapse** by reusing policies learned from the old state space in two distinct aspects. On one hand, Lapse directly reuses the *robust* old policy by composing it with a learned state reconstruction model to handle vanishing sensors. On the other hand, the behavioral experience from the old policy is reused by Lapse to train a newly adaptive policy through offline learning, better utilizing new sensors. To leverage advantages of both policies in different scenarios, we further propose *automatic ensemble weight adjustment* to effectively aggregate them. Theoretically, we justify that robust policy reuse helps mitigate uncertainty and error from both evolution and reconstruction. Empirically, Lapse achieves a significant performance improvement, outperforming the strongest baseline by about $2\times$ in benchmark environments.

---

## 论文详细总结（自动生成）

# Learning to Reuse Policies in State Evolvable Environments 论文详细总结

## 1. 论文的核心问题与整体含义
- **研究背景**：强化学习策略依赖固定的感官状态特征，但在实际部署中，传感器会因维护、磨损或升级而发生“演化”，导致状态空间改变（如部分维度消失或新增传感器维度），原有策略在新状态空间下失效。
- **核心问题**：现有解决方案要么试图训练“传感器不变”策略（难以应对不可预见的演化），要么预先生成多个源策略再从中选择（组合爆炸，泛化有限），都难以保证性能。论文将这一问题形式化为**状态可演化强化学习 (State Evolvable Reinforcement Learning, SERL)**。
- **整体含义**：SERL 要求智能体在状态空间多次演化后，**无需昂贵在线试错**就能快速减缓策略性能衰退，利用短时间可获取的“重叠期”配对数据，实现低成本、高效的自适应。

## 2. 方法论：Lapse 的核心思想与技术细节
Lapse 的目标是在不进行大量在线探索的前提下，通过两个维度的“策略重用”应对状态演化：

- **鲁棒策略重用 + 状态重建 (Robust Policy Reuse with State Reconstruction)**
  - 利用演化前后短时间内的配对状态 $(s_n, s_{n+1})$，训练一个基于条件 GAN（Pix2Pix）的状态重建模型 $g_n: S_{n+1} \to S_n$，并用 L1/L2 损失提升重建精度。
  - 在部署时，将新状态通过 $g_n$ 重建为旧状态，再用**旧策略 $\pi_n$ 直接决策**，得到 $\pi_{n+1}^{\text{recon}} = \pi_n \circ g_n$。
  - 为应对重建误差导致的策略崩溃，在初始策略训练阶段引入**鲁棒正则项**（Wocar-PPO 或 RADIAL-DQN），最小化策略对输入微小扰动的动作分布差异，从理论上保证重建误差被控制。

- **行为知识重用 + 离线自适应学习 (Offline Policy Learning with Knowledge Reuse)**
  - 收集的有限数据 $D_n$ 包含旧策略的行为轨迹，虽然不能直接利用新传感器，但通过离线 RL（MuJoCo 用 TD3+BC，Atari 用 CQL）训练一个**新自适应策略 $\pi_{n+1}^{\text{off}}$**。
  - 离线学习损失中加入**鲁棒光滑正则**（RORL 风格），增强新策略对输入扰动的鲁棒性。
  - 保守系数 $\beta_{n+1}$ 随演化阶段数递增，以平衡模仿旧策略与利用新信息。

- **自动集成权重调整 (Automatic Ensemble Weight Adjustment)**
  - 最终策略 $\pi_{n+1} = \kappa_{n+1} \pi_{n+1}^{\text{recon}} + (1-\kappa_{n+1}) \pi_{n+1}^{\text{off}}$。
  - 权重 $\kappa_{n+1}$ 由旧策略的性能衰减比例和两个新策略与旧策略的 KL 散度自动计算，早期更信任重建策略，后期逐步倾向离线自适应策略。

- **理论支撑**
  - 定义演化函数的 $\epsilon_R$–$\epsilon_P$ 一致性，量化状态演化带来的奖赏与转移不确定性。
  - 证明：若旧策略足够鲁棒，即使重建模型存在误差，由重建误差引起的性能下降也能被有效约束（Proposition 3.2, 3.3）。

## 3. 实验设计
- **数据集与场景**
  - **连续控制（MuJoCo）**：Ant、HalfCheetah、Hopper、Walker，状态为向量。
  - **离散动作图像输入（Atari）**：BankHeist、Freeway、Pong、RoadRunner，状态为像素图像。
  - 状态演化模拟：移除传感器、添加传感器、视角旋转、加入干扰物体、线性映射等，共 5 次连续演化。

- **对比基线**
  - RL‑GAN（简单状态转换 + 原策略复用）
  - LUSR（隐空间统一状态表征）
  - PAD（基于自监督的在线适配）
  - Offline（仅用 $D_n$ 训练新策略的离线 RL）
  - FPT（少样本策略迁移 + 行为克隆）
  - CUP（基于 Critic 的策略选择与引导）

- **评估指标**：5 个演化阶段的平均测试回报，归一化到初始阶段策略的回报（百分比）。

## 4. 资源与算力
- 论文**未明确说明**使用的 GPU 型号、数量及具体训练时长。
- 文中提到训练重建模型、离线策略的步数（如 MuJoCo 每阶段 10K 步，Atari 更高），所有结果基于 5 个随机种子取平均，但未给出算力消耗的定量描述。

## 5. 实验数量与充分性
- **主实验**：8 个任务 × 7 个方法对比，每个任务 5 阶段，每阶段 10 个测试 episode，5 种子。
- **消融研究**：移除重建策略、离线策略、鲁棒性训练、自动权重调整（图 5、附录）。
- **理论验证实验**：比较鲁棒策略与非鲁棒策略在相同重建模型下的测试性能与动作差异（图 3）。
- **学习过程分析**：展示各阶段重建策略与离线策略的分别表现，以及集成权重的动态变化（图 4）。
- **超参数敏感性**：对 $\lambda$（重建损失系数）、数据集大小等进行扫描。
- **演化阶段扩展**：测试最多 15 个演化阶段（附录），以及剪枝策略对存储和延迟的影响。
总体来说，实验设计**全面、系统，对比公平**（所有基线在相同数据限制下适配，共享相同的初始策略训练条件）。

## 6. 主要结论与发现
- Lapse 在所有任务的平均性能保持上**显著优于最强基线**，整体归一化回报达到 91%，约为最强基线（Offline 45%）的 2 倍。
- 旧策略的**鲁棒训练**对重建复用至关重要，普通策略即使配合精确重建模型仍会崩溃。
- 结合重建复用与离线自适应学习的自动集成机制，能在不同演化阶段自适应地平衡两种策略的优势。
- 理论分析表明，通过限制动作分布偏移，可以有效控制状态重建与演化不确定性带来的性能损失。

## 7. 优点
- **问题新颖且实际**：首次在 RL 中形式化 SERL，关注部署后传感器的自然演化，填补了领域空白。
- **方法双重互补**：从“重建复用旧策略”和“离线学习新策略”两个角度同时解决问题，互有弥补。
- **无痛部署**：仅需短暂重叠期数据，无需在线试错，适合真实世界应用。
- **理论与实证并重**：推导性能界，并与实验现象相互验证。
- **实验扎实**：覆盖连续与离散动作、像素与向量状态，对比基线多样，消融和敏感性分析充分。

## 8. 不足与局限
- **依赖重叠期配对数据 $D_n$**：在一些真实场景中，可能无法同时获取新旧状态空间的对齐数据，限制了直接应用。
- **极端演化可能失效**：若状态空间演化过于剧烈（如传感器完全替换、维度剧变），重建模型精度可能不足，导致鲁棒策略也失效。
- **存储与延迟**：随着演化次数增加，组合的模型数量膨胀，需要剪枝策略缓解，但仍可能影响实际工程部署。
- **离线算法依赖**：Atari 环境下离线 RL 方法性能有限（如 CQL 在部分游戏效果不佳），可能影响最终效果。
- **超参数较多**：需分别调节 GAN 损失系数、离线保守系数、鲁棒强度等，可能增加调参负担。

（完）
