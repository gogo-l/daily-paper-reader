---
title: Learning to Reuse Policies in State Evolvable Environments
title_zh: 在状态可演化环境中学习重用策略
authors: "Ziqian Zhang, Bohan Yang, Lihe Li, Yuqi Bian, Ruiqi Xue, Feng Chen, Yi-Chen Li, Lei Yuan, Yang Yu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=1R84O2Xr1k"
tags: ["query:continual"]
score: 7.0
evidence: 状态特征演化下RL策略重用以持续适应
tldr: 强化学习策略依赖状态特征，传感器维护或新增会导致特征空间演化，使策略失效。该工作将问题形式化为状态可演化强化学习，要求智能体在状态空间变化后快速适应而无需重训练，提出学习策略重用方法，在多种不可预测演化场景下保持性能，为动态环境中智能体的持续适应提供新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1550, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1736, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 821, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 809, \"height\": 585, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 835, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1023, \"height\": 303, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1027, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1721, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 868, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1752, \"height\": 845, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1267, \"height\": 1316, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1761, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1388, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1711, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1768, \"height\": 1110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1754, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-1r84o2xr1k/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 868, \"height\": 591, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-1r84o2xr1k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1752, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1r84o2xr1k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1744, \"height\": 162, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1r84o2xr1k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 732, \"height\": 1340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-1r84o2xr1k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 914, \"height\": 832, \"label\": \"Table\"}]"
motivation: 传感器变化导致状态特征演化，使已有策略失效。
method: 形式化状态可演化强化学习问题，提出策略重用学习。
result: 在多种状态演化下维持策略性能，避免重训练。
conclusion: 为动态环境中的策略持续适应提供了有效路径。
---

## Abstract
The policy trained via reinforcement learning (RL) makes decisions based on sensor-derived state features. It is common for state features to evolve for reasons such as periodic sensor maintenance or the addition of new sensors for performance improvement. The deployed policy fails in new state space when state features are unseen during training. Previous work tackles this challenge by training a sensor-invariant policy or generating multiple policies and selecting the appropriate one with limited samples. However, both directions struggle to guarantee the performance when faced with unpredictable evolutions. In this paper, we formalize this problem as state evolvable reinforcement learning (SERL), where the agent is required to mitigate policy degradation after state evolutions without costly exploration. We propose **Lapse** by reusing policies learned from the old state space in two distinct aspects. On one hand, Lapse directly reuses the *robust* old policy by composing it with a learned state reconstruction model to handle vanishing sensors. On the other hand, the behavioral experience from the old policy is reused by Lapse to train a newly adaptive policy through offline learning, better utilizing new sensors. To leverage advantages of both policies in different scenarios, we further propose *automatic ensemble weight adjustment* to effectively aggregate them. Theoretically, we justify that robust policy reuse helps mitigate uncertainty and error from both evolution and reconstruction. Empirically, Lapse achieves a significant performance improvement, outperforming the strongest baseline by about $2\times$ in benchmark environments.

---

## 论文详细总结（自动生成）

好的，根据您提供的论文内容，以下是根据要求生成的详细中文总结：

### 1. 论文的核心问题与整体含义
*   **核心问题**：在现实部署中，强化学习智能体依赖的传感器会因维护、新增或磨损而导致状态特征空间发生演化。原有的策略在面对全新的、未在训练中出现过的状态特征时会失效，即策略退化。
*   **研究动机**：现有方法（如训练传感器不变策略或预先枚举多种源策略）难以应对**不可预测**的状态演化，且无法保证性能。因此，需要一个能在状态空间演化后，**无需昂贵试错探索**即可快速适应、缓解策略退化的方法。
*   **整体含义**：本文将这一问题形式化为**状态可演化强化学习（SERL）**，并提出了解决方法，为强化学习智能体在动态变化的环境中长期稳定运行提供了新范式。

### 2. 论文提出的方法论（Lapse）
Lapse的核心思想是通过两种不同方式重用旧状态空间中学习的策略，并自动聚合它们以适应新状态空间。
*   **关键假设**：假设智能体知道哪些传感器会被维护或新增，这使得它能在状态演化的短暂重叠期内，同时观测到新旧状态特征，从而收集一小批配对数据 \(D_n\)。
*   **核心技术一：鲁棒策略重用与状态重构**
    *   **机制**：当旧传感器消失时，学习一个从新状态空间 \(S_{n+1}\) 到旧状态空间 \(S_n\) 的**状态重构模型** \(g_n\)（基于条件GAN），然后将旧策略 \(\pi_n\) 与该模型组合，形成新的重构策略 \(\pi^{recon}_{n+1}\)。
    *   **关键设计**：为应对重构误差导致的策略性能崩溃，在训练初始策略 \(\pi_0\) 时加入**鲁棒性正则化项** \(L_{robust}\)，强制策略在输入状态受到微小扰动时保持稳定的动作分布。
*   **核心技术二：行为知识重用与离线策略学习**
    *   **机制**：为利用新传感器信息，并减轻重构误差累积问题，利用旧策略采集到的有限数据集 \(D_n\)（包含新状态、动作、奖励等），通过**离线强化学习**（如TD3+BC）训练一个新的自适应策略 \(\pi^{off}_{n+1}\)。
    *   **关键设计**：在离线学习中也加入鲁棒性正则化项，增强其稳定性。同时，动态调整行为克隆保守性系数 \(\beta_{n+1}\)，演化早期侧重模仿，后期则趋于更乐观的探索。
*   **核心技术三：策略聚合与自动权重调整**
    *   **机制**：通过线性混合的方式，将重构策略 \(\pi^{recon}_{n+1}\) 和离线策略 \(\pi^{off}_{n+1}\) 组合成最终部署的策略：\( \pi_{n+1} = \kappa \pi^{recon}_{n+1} + (1 - \kappa) \pi^{off}_{n+1} \)。
    *   **关键设计**：集成权重 \(\kappa\) 根据旧策略的性能（相对初始性能的比值）以及两个新策略与旧策略的动作分布差异，实现**动态、自动调整**，以在不同演化阶段发挥各自优势。
*   **理论支撑**：论文证明了，如果演化映射满足 \(ϵ_R-ϵ_P\) 一致性，且策略足够鲁棒以限制重构前后的动作分布差异，那么组合策略的性能损失可以被边界化。

### 3. 实验设计
*   **数据集/场景**：
    *   **向量状态任务**：MuJoCo连续控制环境（`Ant`, `HalfCheetah`, `Hopper`, `Walker`）。
    *   **像素图像任务**：Atari游戏环境（`BankHeist`, `Freeway`, `Pong`, `RoadRunner`）。
    *   **演化模拟**：模拟多种不可预测的传感器变化，包括增加/移除传感器、视角旋转、添加干扰物体、线性映射及添加噪声。每次演化可收集的数据极有限（MuJoCo仅10条轨迹，Atari仅15条轨迹）。
*   **基准方法**：
    *   **RL-GAN**：直接用GAN重构状态重用旧策略，但无鲁棒训练。
    *   **LUSR**：学习解耦的潜在状态表示进行域适应。
    *   **PAD**：利用自监督信号在部署中微调策略。
    *   **Offline**：直接用离线RL学习新策略。
    *   **FPT**：面向小样本的策略迁移框架。
    *   **CUP**：基于Critic引导的多源策略重用与选择。

### 4. 资源与算力
*   文中**未明确说明**所使用的具体GPU型号、数量及总训练时长。仅提及了各模块的训练步数（如状态重构模型训练10000/20000步，离线策略训练10000/40000步）及采用多随机种子（5次）进行实验。

### 5. 实验数量与充分性
*   **实验数量**：较为充分。
    *   **主实验**：在8个任务（4个MuJoCo, 4个Atari）上与6种基线方法进行了连续5个演化阶段的性能对比。
    *   **消融实验**：通过移除鲁棒性、离线策略、重构策略、动态权重等关键组件，验证各部分的贡献。
    *   **分析性实验**：包括验证理论分析（对比鲁棒/普通策略的重用效果）、展示学习过程（策略性能与权重变化）、参数敏感度分析（如\(λ\)）、策略剪枝效率对比，以及扩展至15个演化阶段的长期测试。
*   **客观公平性**：实验设计客观公平。所有方法在相同的数据限制（\(D_n\)）和评估流程下进行比较，结果汇报了均值和标准差，并使用了多种演化顺序和环境避免偏差。

### 6. 论文的主要结论与发现
*   Lapse在所有8个测试任务和连续演化阶段中，均取得了最优的适应性能，平均表现约为最强基线的**2倍**（91.09% vs 45.51%）。
*   仅靠状态重构而**不结合鲁棒训练**的策略，会因重构误差和分布偏移迅速失败，证明了鲁棒性对策略重用的关键作用。
*   离线学习的自适应策略能更好地利用新传感器信息，并有效缓解长期演化中重构误差累积的问题。
*   自动调整的**动态集成权重**机制能有效整合两种重用策略的优势，在不同演化场景下做出最佳权衡，优于固定权重。

### 7. 优点
*   **问题新颖且现实**：SERL问题设定贴近传感器变更的实际部署场景，填补了RL在状态空间动态演化方面的研究空白。
*   **方法论全面协同**：Lapse整合了状态重构、鲁棒训练、离线学习和动态集成，形成了完整的解决方案，且各组件在理论与实验上均被证明是必要和互补的。
*   **零试错适应**：方法完全利用演化过渡期数据，在部署新策略过程中无需与环境进行代价高昂的在线试错交互。
*   **实验扎实**：在离散和连续动作、向量和像素输入等多种任务上进行了全面评估，并通过详细消融和分析实验增强了结论的可信度。

### 8. 不足与局限
*   **依赖配对数据 \(D_n\)**：方法要求短暂期内同时观察新旧状态特征以收集配对数据，这在实际中可能因传感器同时失效等场景而无法满足，限制了应用范围。
*   **长期演化能力下降**：在Walker任务的长期测试（15个演化阶段）中性能出现下滑，表明在处理某些特定任务或极端长期演化时仍有局限。
*   **参数敏感性**：方法的性能依赖一些关键超参数（如重构损失系数 \(λ\)、保守性系数 \(\beta\) 等），需针对不同任务进行调节。
*   **演化假设**：理论分析依赖于 \(ϵ_R−ϵ_P\) 一致性的假设，虽然较为温和，但在演化极度剧烈、状态空间产生根本性剧变时，方法的性能边界可能失效。

（完）
