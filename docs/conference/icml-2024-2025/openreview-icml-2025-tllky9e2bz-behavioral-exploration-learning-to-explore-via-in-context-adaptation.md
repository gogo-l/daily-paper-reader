---
title: "Behavioral Exploration: Learning to Explore via In-Context Adaptation"
title_zh: 行为探索：通过上下文适应学习探索
authors: "Andrew Wagenmaker, Zhiyuan Zhou, Sergey Levine"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tlLkY9E2bZ"
tags: ["query:continual"]
score: 8.0
evidence: 训练智能体内化探索与适应，在新环境中快速在线适应
tldr: 自主智能体需在新环境中快速探索并在线适应行为，但现有方法依赖随机探索和慢速梯度更新。受人类快速迁移启发，本文提出行为探索，利用大规模行为克隆训练智能体掌握泛化的探索与适应策略，使其在少数交互内便能通过上下文推理进行调整。实验显示，该方法在多个连续控制任务中比随机探索和学习型探索基线更快速、更稳定，赋予智能体更接近人类的在线适应能力，对机器人和动态环境中的自主系统具有重要应用潜力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 460, \"height\": 225, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 556, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 559, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 563, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 451, \"height\": 302, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 367, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 557, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 555, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 315, \"height\": 417, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 533, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 888, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 631, \"height\": 505, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 631, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1775, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 634, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1783, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 635, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 637, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1780, \"height\": 2231, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1781, \"height\": 2235, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1782, \"height\": 2240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1783, \"height\": 2241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 566, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 567, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 554, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 553, \"height\": 378, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 565, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 557, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1755, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tllky9e2bz/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1760, \"height\": 494, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 422, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1665, \"height\": 216, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1024, \"height\": 413, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 903, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1139, \"height\": 887, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1683, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 731, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 793, \"height\": 176, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tllky9e2bz/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 731, \"height\": 450, \"label\": \"Table\"}]"
motivation: 现有方法依赖随机探索和梯度更新，无法实现快速在线适应。
method: 提出行为探索，通过大规模行为克隆训练智能体掌握上下文探索与适应能力。
result: 实验表明该方法在连续任务中比随机探索更快稳定，实现快速适应。
conclusion: 行为探索赋予智能体快速在线适应能力，对自主系统有重要应用价值。
---

## Abstract
Developing autonomous agents that quickly explore an environment and adapt their behavior online is a canonical challenge in robotics and machine learning. While humans are able to achieve such fast online exploration and adaptation, often acquiring new information and skills in only a handful of interactions, existing algorithmic approaches tend to rely on random exploration and slow, gradient-based behavior updates. How can we endow autonomous agents with such capabilities on par with humans? Taking inspiration from recent progress on both in-context learning and large-scale behavioral cloning, in this work we propose behavioral exploration: training agents to internalize what it means to explore and adapt in-context over the space of ''expert'' behaviors. To achieve this, given access to a dataset of expert demonstrations, we train a long-context generative model to predict expert actions conditioned on a context of past observations and a measure of how ''exploratory'' the expert's behaviors are relative to this context. This enables the model to not only mimic the behavior of an expert, but also, by feeding its past history of interactions into its context, to select different expert behaviors than what have been previously selected, thereby allowing for fast online adaptation and targeted, ''expert-like'' exploration. We demonstrate the effectiveness of our method in both simulated locomotion and manipulation settings, as well as on real-world robotic manipulation tasks, illustrating its ability to learn adaptive, exploratory behavior.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究动机**：在机器人学和机器学习领域，开发能够快速探索新环境并在线适应行为的自主智能体是一个重大挑战。人类能够在极少次交互中获取信息并推断出正确行为（例如，在“递给我杯子”的场景中，尝试不同的杯子直到成功），而现有算法多依赖低效的随机探索和缓慢的梯度更新。
*   **整体含义**：本文旨在赋予自主智能体“类人”的快速在线探索与适应能力。其核心思想是让智能体学习如何“有意义地”探索，即探索行为应聚焦于专家演示数据中已经存在的、合理的任务解决行为（如抓取杯子），而非漫无目的的随机动作（如随机移动手臂）。

### 2. 论文提出的方法论
*   **核心思想：行为探索**：作者提出训练一个可以“内化”探索和适应能力的策略。该策略学习在专家行为的空间内进行探索，而非在整个状态-动作空间内盲目探索。
*   **关键技术细节**：
    *   **条件分布建模**：该方法的核心是训练一个条件生成模型（具体为扩散策略+Transformer架构）来预测专家动作。该模型的条件信息不仅包括**当前状态**，还包括**历史交互记录**和**覆盖度度量值**。
    *   **覆盖度度量**：定义了一个覆盖度函数 `cov(·)`，用于量化智能体访问过的状态集合 `h` 的特征空间覆盖范围。公式为：
        `cov(h) = 1 / tr((Λ(h) + λ·I)^-1)`
    *   **训练目标**：最大化以下似然函数，让策略学习在给定历史 `h` 和期望的总覆盖率 `cov(h ∪ τ_t^k)` 的条件下，如何选择动作以达到该覆盖率。
        `Σ_t Σ_k E_h [log π_BE(a_t^k | s_t^k, h, cov(h ∪ τ_t^k))]`
    *   **部署与推理**：在测试时，通过向策略上下文输入以往收集的状态历史 `h_k` 和一个期望的“探索程度”值 `exp`，使策略能够推理出哪些专家动作最有可能增加相对于已有历史的状态覆盖度。通过调整 `exp` 可以调节策略的探索性：`exp` 值大则趋向于高覆盖度的行为，`exp` 值小则趋向于与历史相似的行为。

### 3. 实验设计
*   **数据集/场景**：
    *   **强化学习基准**：**D4RL** 数据集中的 `Antmaze`（中/大型迷宫）和 `Kitchen` 环境。这些数据集由脚本策略生成，并非最优数据，且移除了奖励标签，要求智能体在线探索以找到目标。
    *   **模拟模仿学习基准**：**LIBERO** 基准（LIBERO-90），包含90个物体操作任务，提供50条人类遥操作演示数据。
    *   **真实世界操作**：在 **WidowX** 机器人上执行抓取任务，策略在 **BridgeData V2** 数据集（6万多条演示）上训练。
*   **对比方法**：
    *   **RL对比**：`Online RND`（纯在线好奇心探索）、`ExPLORe`（利用离线数据的RND）、`HILP`（离线技能发现+在线RL）、`SUPE`（技能+好奇心探索）、标准 `BC`。
    *   **IL对比**：标准 `BC`、添加动作噪声的 `BC`、以历史为条件的 `BC`、随机任务 `BC`，真实世界场景中还包括大模型 `OpenVLA`。

### 4. 资源与算力
*   论文正文中**未明确说明**具体使用的GPU型号、数量、或总训练时长。仅提及在某些实验中使用了特定的模型架构和批次大小，但缺乏硬件级算力消耗的详细报告。

### 5. 实验数量与充分性
*   **实验数量**：实验覆盖了3个主要领域（D4RL RL任务、LIBERO模拟操作、真实世界操作），每个领域内包含多个子环境和多次试验。
    *   **D4RL**: `Antmaze`（中型和大型）和 `Kitchen`，进行了多目标、多区域覆盖测试。
    *   **LIBERO**: 在90个任务上的隐藏任务和已知任务两种评估模式。
    *   **WidowX**: 在3个不同的双物体场景下进行了8次5回合的试验。
*   **消融与分析实验**：论文提供了丰富的分析：
    *   校准性分析：通过调节覆盖度条件值，验证策略探索性的可控性。
    *   历史条件重要性分析：对比了使用在线历史与仅使用初始状态历史的 `BE`，证明历史适应性的关键作用。
    *   行为可视化：展示了 `BE` 策略如何根据不同的条件历史，生成不同的探索轨迹以覆盖未访问区域。
*   **充分性与公平性**：实验设计较为**充分和客观**。对比了从经典BC、RL探索方法到最新的离线预训练+在线微调方法，基线选择广泛且具有代表性。训练和评估过程有明确的随机种子和误差棒报告，确保了统计可靠性。

### 6. 论文的主要结论与发现
*   **高效探索与适应**：该方法在各种任务中均显著优于标准 BC 和多种基于RL的探索方法。在 `Antmaze` 和 `LIBERO` 上，它能以更少的交互次数更快地达到目标、完成更多任务。
*   **语义化探索**：与随机探索（如动作噪声）不同，该方法能够聚焦于有意义的专家行为空间进行探索，在尝试不同解决方案的同时，仍然保持较高的任务成功率，而不会引入过多的无关行为。
*   **快速上下文适应**：纯基于上下文适应，无需在线梯度更新，使策略的在线行为调整相比RL方法更快。
*   **可规模化**：方法能够有效应用于大规模、基于视觉的真实世界机器人数据集（BridgeData V2），并在直接操作任务中取得实际性能提升。

### 7. 优点
*   **方法新颖性**：首次提出利用上下文学习范式，训练策略进行覆盖感知的行为探索，将探索问题转化为一个可监督学习的条件生成问题。
*   **有效性与通用性**：在模拟RL、模拟操作和真实世界操作等不同领域均展现出优越性能，证明该方法具有良好的泛化潜力。
*   **实现简单且高效**：基于现有的扩散策略架构和行为克隆式训练，避免了复杂的RL在线训练，并能实现快速在线适应。
*   **分析深度**：通过校准性分析和消融研究，清晰地阐明了方法有效性的内在机制（上下文适应性和在专家空间内探索）。

### 8. 不足与局限
*   **依赖离线数据质量**：探索行为被严格限制在离线专家数据所覆盖的行为空间中。如果解决新任务所需的行为未在数据集中出现，该方法可能无法进行有效探索。
*   **缺少算力及训练时长报告**：未报告模型的硬件资源消耗和训练时间，不利于评估其计算成本和复现门槛。
*   **覆盖度度量简化假设**：理论推导（命题 4.2）假设了确定性环境和独热编码特征等简化条件，实际应用中采用了随机傅里叶特征作为近似，其理论保证与实际应用间存在差距。
*   **探索有效性边界**：在部署阶段，历史长度超过上下文窗口时需要随机降采样，这可能导致信息丢失，如何在更长的时间尺度上保持最优探索是一个尚未解决的问题。
*
    （完）
