---
title: "Behavioral Exploration: Learning to Explore via In-Context Adaptation"
title_zh: 行为探索：通过上下文适应学习如何探索
authors: "Andrew Wagenmaker, Zhiyuan Zhou, Sergey Levine"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tlLkY9E2bZ"
tags: ["query:continual"]
score: 6.0
evidence: 上下文适应使智能体能够在线探索和调整行为，模拟自我进化
tldr: 自主智能体快速在线探索和适应仍是挑战，人类能少量交互即获取新技能。受上下文学习和行为克隆启发，本文提出行为探索：训练智能体在上下文环境中内化探索与适应策略。实验显示该方法使智能体能够快速适应新环境，模仿专家行为。此工作为构建自我进化智能体提供了不依赖梯度更新的高效适应途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 460, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 556, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 559, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 563, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 451, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 367, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 557, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 555, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 315, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 533, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 888, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 631, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 631, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1775, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 634, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1783, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 635, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 637, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1780, \"height\": 2231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1781, \"height\": 2235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1782, \"height\": 2240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1783, \"height\": 2241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 566, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 567, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 554, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 553, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 565, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 557, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1755, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1760, \"height\": 494, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 422, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1665, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1024, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 903, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1139, \"height\": 887, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1683, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 731, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 793, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 731, \"height\": 450, \"label\": \"Table\"}]"
motivation: 现有探索方法依赖随机性和慢梯度更新，无法实现类人快速在线适应。
method: 利用上下文学习和大规模行为克隆，训练智能体在上下文中学习探索与适应。
result: 智能体展示出快速探索和环境适应能力，接近人类水平的少量交互学习。
conclusion: 上下文适应为自主智能体的快速在线自我改进提供了新范式。
---

## Abstract
Developing autonomous agents that quickly explore an environment and adapt their behavior online is a canonical challenge in robotics and machine learning. While humans are able to achieve such fast online exploration and adaptation, often acquiring new information and skills in only a handful of interactions, existing algorithmic approaches tend to rely on random exploration and slow, gradient-based behavior updates. How can we endow autonomous agents with such capabilities on par with humans? Taking inspiration from recent progress on both in-context learning and large-scale behavioral cloning, in this work we propose behavioral exploration: training agents to internalize what it means to explore and adapt in-context over the space of ''expert'' behaviors. To achieve this, given access to a dataset of expert demonstrations, we train a long-context generative model to predict expert actions conditioned on a context of past observations and a measure of how ''exploratory'' the expert's behaviors are relative to this context. This enables the model to not only mimic the behavior of an expert, but also, by feeding its past history of interactions into its context, to select different expert behaviors than what have been previously selected, thereby allowing for fast online adaptation and targeted, ''expert-like'' exploration. We demonstrate the effectiveness of our method in both simulated locomotion and manipulation settings, as well as on real-world robotic manipulation tasks, illustrating its ability to learn adaptive, exploratory behavior.

---

## 论文详细总结（自动生成）

好的，以下是基于您提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：如何让自主智能体（如机器人）像人类一样，在全新的场景中通过少量、有目的的交互尝试，快速探索环境并在线调整行为，从而解决问题？
*   **研究动机**：现有的探索方法大多依赖随机策略（如动作噪声）和缓慢的、基于梯度的在线更新，效率低下且行为缺乏目的性，无法实现类人级别的快速在线适应。
*   **整体含义**：本文提出了“行为探索”这一新范式。其核心思想不再是让智能体在无限的状态-动作空间中随机或盲目探索，而是利用已有的专家示范数据，让智能体学会在“有意义的专家行为空间”内进行上下文（in-context）探索与适应。

### 2. 论文提出的方法论

核心思想是训练一个策略，使其内化“如何成为探索性的专家”这一概念，从而在部署时能根据历史交互信息，从示范数据集中选择不同的、但同样合理的专家行为，实现快速在线适应。

**关键技术细节**：

1.  **探索目标的定义**：
    *   论文提出通过状态特征的覆盖率来量化探索，将“最大化覆盖率”作为探索的目标。
    *   为了避免在无关状态上浪费算力，他们定义了**行为覆盖（ `cov_β`）**，即只关注专家策略 `π_β` 所覆盖的、有用的特征空间。目标变为最大化对该行为空间的覆盖。
2.  **行为探索（BE）目标函数**：
    *   **核心洞察**：最佳的探索策略不是简单地克隆专家，而是根据当前已访问的历史状态，从专家策略的概率分布中，有条件地筛选出那些能最大程度增加覆盖率的动作。
    *   基于此，提出了一个监督学习目标：训练一个长上下文生成式策略 `π_BE`，使其在给定“**当前状态 `s_t`**、**过去交互历史 `h`** 和**一个期望的未来覆盖率指标 `cov`**”的条件下，最大化预测专家动作 `a_t` 的对数似然。
    *   该目标可以自然地扩展到任务条件设定，通过加入任务标签 `y_t` 来限制探索范围。
3.  **模型架构与部署**：
    *   **模型**：采用基于Transformer的**扩散模型**，能够有效处理连续动作空间中的复杂、多模态分布，并利用Transformer的长上下文能力捕获历史交互信息。
    *   **部署**：在线交互时，策略 `π_BE` 接收“当前状态”、“已收集的历史状态”和“期望的探索程度（`exp`）”作为上下文输入。通过设定高探索值，策略会倾向于采样能带来高覆盖率的行为，从而在专家行为空间中实现指向性探索；反之，则倾向重复已有行为。

### 3. 实验设计

论文在模拟强化学习、模拟模仿学习和真实世界机器人任务三个维度进行了评估。

*   **数据集与场景**：
    *   **强化学习基准（D4RL）**：使用`Antmaze`（导航）和`Kitchen`（机械臂操作）环境，利用其离线数据（移除奖励标签），测试智能体在不知目标的情况下，通过探索找到目标的能力。
    *   **模仿学习基准（Libero）**：使用包含90个任务的模拟机器人操作数据集`Libero 90`。设计了两种评估：一是“隐藏任务”，测试策略通过尝试不同任务来探索出正确目标的能力；二是“给定任务”，测试策略在6次尝试内解决特定任务的能力。
    *   **真实世界机器人（WidowX）**：在真实机械臂上，利用大规模数据集`BridgeData V2`训练，评估策略在歧义指令下通过探索不同操作行为（如接触不同的物体）来完成任务的能力。

*   **对比方法**：
    *   **RL探索方法**（用于D4RL）：`Online RND`、`ExPLORe`、`HILP`、`SUPE`。
    *   **行为克隆（BC）变体**（用于所有实验）：标准`BC`、`BC+动作噪声`、`BC+历史条件`。
    *   **通用策略**（用于WidowX）：`OpenVLA`。

### 4. 资源与算力

*   文中未明确提及训练所使用的具体GPU型号、数量或总训练时长。

### 5. 实验数量与充分性

*   **实验组数**：论文在至少3个不同规模的领域上进行了实验，涵盖了6个以上的具体任务环境。
*   **充分性与公平性**：
    *   **对比充分**：对比方法涵盖了主流的在线RL探索基线、多种BC变体以及最先进的通用机器人策略（OpenVLA），比较全面公正。
    *   **评估维度**：评估指标不仅包括任务成功率，还包括探索覆盖率（如访问区域数、目标达成比例），且所有实验均报告了标准误差，评估次数充足（如D4RL实验用80个试次）。
    *   **消融与分析**：通过校准实验（调节覆盖率调节值 `exp`）验证了策略的可控性；通过Maze2D可视化分析，清晰展示了策略对历史上下文的适应性。
    *   **结论**：实验设计系统、多维度，对比全面，充分验证了方法的有效性、适应性及相对于基线方法的优势。

### 6. 论文的主要结论与发现

1.  BE可以实现**快速在线适应**，无需任何梯度更新，其“在上下文中适应”的机制远比基于在线RL的方法高效。
2.  BE的探索是**语义化和有指向性的**，它能在专家演示数据所定义的有用行为空间内进行探索，同时保持高任务成功率，这优于随机探索（如BC+噪声）或历史盲目探索。
3.  BE在多个领域（模拟RL、机器人操控）和多个尺度上均表现出显著增益，在真正的大规模真实世界任务中也具有可扩展性。

### 7. 优点

*   **方法创新**：巧妙地将上下文学习引入探索领域，通过简单的监督学习目标实现了复杂的探索行为，是本研究的一大亮点。
*   **效率极高**：实现了无梯度的在线适应，部署时仅需一次前向传播，计算效率远超传统的在线RL方法。
*   **安全性/合理性**：探索空间被限制在专家行为分布内，生成的探索行为比无约束的随机探索更安全、更连贯，更适合机器人应用。
*   **可扩展性**：方法基于标准的行为克隆范式，易于与当前最先进的策略架构（如扩散策略、Transformer）和工具包结合。

### 8. 不足与局限

*   **探索的边界**：BE的探索能力被严格限制在离线示范数据的分布内。对于需要超出示范数据范围才能找到最优解的场景，该方法可能失效。
*   **依赖状态表征**：方法依赖于一个好的状态特征映射 `φ(s)` 来计算覆盖率并定义“新颖性”，如何设计这个特征对于实际效果至关重要，但文中未深入探讨不同特征选择的影响。
*   **训练数据分布**：训练时使用的历史分布 `H(D)` 被简单地设为均匀采样，这可能与在线部署时策略实际遇到的状态分布存在偏差，影响泛化能力。
*   **计算资源未明确**：缺乏对训练所需算力资源的说明，使得该方法在实践中的落地成本不透明。

---
（完）
