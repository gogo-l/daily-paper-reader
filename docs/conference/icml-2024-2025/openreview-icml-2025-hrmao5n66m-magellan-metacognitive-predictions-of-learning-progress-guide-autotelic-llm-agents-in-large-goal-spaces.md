---
title: "MAGELLAN: Metacognitive predictions of learning progress guide autotelic LLM agents in large goal spaces"
title_zh: MAGELLAN：元认知学习进度预测引导自驱动LLM智能体在大型目标空间中探索
authors: "Loris Gaven, Thomas Carta, Clément ROMAC, Cédric Colas, sylvain lamprier, Olivier Sigaud, Pierre-Yves Oudeyer"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hRMAo5N66M"
tags: ["query:continual"]
score: 8.0
evidence: MAGELLAN利用元认知预测学习进度，引导自驱动LLM智能体在开放演化目标空间中探索
tldr: 开放环境下的学习智能体需高效优先探索有学习进展的目标。本文提出MAGELLAN框架，让LLM智能体通过元认知预测自身能力和学习进度，在语义关联的庞大目标空间中动态选择目标。实验表明该方法显著提高样本效率，为自驱动持续学习智能体在动态环境中的演化提供了可行路径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 830, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 841, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 694, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 823, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 759, \"height\": 1173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 832, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 783, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 810, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1724, \"height\": 1714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1029, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1608, \"height\": 1184, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1070, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1071, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1074, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1689, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1764, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1772, \"height\": 906, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1421, \"height\": 1100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1626, \"height\": 1200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1708, \"height\": 1430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 575, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 575, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 571, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 573, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 577, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 842, \"height\": 1298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1718, \"height\": 1206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1389, \"height\": 604, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 679, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 884, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1669, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1594, \"height\": 714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 713, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 524, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 410, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 444, \"height\": 315, \"label\": \"Table\"}]"
motivation: 现有自驱动探索方法采样成本高或依赖人工目标分组，难以在演化目标空间中高效估测学习进度。
method: 提出MAGELLAN框架，基于语义关系让LLM在线学习预测自身能力和学习进度。
result: 在多个开放目标环境中，MAGELLAN的样本效率显著优于传统方法。
conclusion: 元认知监测能有效提升智能体在不确定环境中的自演化学习能力。
---

## Abstract
Open-ended learning agents must efficiently prioritize goals in vast possibility spaces, focusing on those that maximize learning progress (LP). When such autotelic exploration is achieved by LLM agents trained with online RL in high-dimensional and evolving goal spaces, a key challenge for LP prediction is modeling one’s own competence, a form of metacognitive monitoring. Traditional approaches either require extensive sampling or rely on brittle expert-defined goal groupings. We introduce MAGELLAN, a metacognitive framework that lets LLM agents learn to predict their competence and learning progress online. By capturing semantic relationships between goals, MAGELLAN enables sample-efficient LP estimation and dynamic adaptation to evolving goal spaces through generalization. In an interactive learning environment, we show that MAGELLAN improves LP prediction efficiency and goal prioritization, being the only method allowing the agent to fully master a large and evolving goal space. These results demonstrate how augmenting LLM agents with a metacognitive ability for LP predictions can effectively scale curriculum learning to open-ended goal spaces.

---

## 论文详细总结（自动生成）

好的，基于提供的论文内容，以下是对《MAGELLAN: Metacognitive predictions of learning progress guide autotelic LLM agents in large goal spaces》一文的结构化、深入、客观总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：如何在庞大、离散且不断演化的自然语言目标空间中，让一个基于大语言模型 (LLM) 的强化学习智能体高效地估计并最大化其学习进度 (Learning Progress, LP)，从而自主生成最优课程。
*   **研究动机与背景**：
    *   **自驱动学习 (Autotelic Learning)**：受人类好奇心驱动学习的启发，自驱动物理智能体需要内在动机信号来优先选择能带来最大学习进度的目标。
    *   **学习进度 (LP) 的估计挑战**：学习进度是衡量自身能力提升的信号。然而，在大型目标空间中准确估计学习进度面临巨大挑战。传统方法要么需要消耗大量算力进行全局评估，要么依赖专家预先定义的、僵化的目标分组，这不仅需要大量专业知识，还无法捕捉分组内部及跨分组的语义关联和能力迁移。
    *   **LLM 智能体的潜力与瓶颈**：LLM智能体在遵循语言指令和利用语言语义进行泛化方面展现出巨大潜力，但现有的自驱动目标选择方法无法有效利用这种语义泛化能力来实时、动态地估计学习进度。
    *   **整体含义**：本文旨在引入一种**元认知机制**，让LLM智能体能够**在线学习并预测**自己在不同目标上的能力，并基于此计算学习进度，从而在开放、演化的目标空间中实现高效的自主课程学习。

### 2. 论文提出的方法论

*   **核心思想**：**MAGELLAN 框架** (Metacognitive Generalization of Learning progress in Language model agents) 的核心是学习一个**目标条件的能力估计器**，该估计器利用 LLM 自身的语义理解能力来动态地捕捉目标之间的能力迁移，从而在无需专家分组或全面评估的情况下，高效预测学习进度。

*   **关键技术细节**：
    *   **能力估计**：MAGELLAN为智能体策略 $\pi_t$ 维护一个能力估计器 $C_{\theta_t}(g)$，用于预测在目标 $g$ 上的成功概率。该估计器基于LLM实现，通过一个提示词输入目标 $g$，提取LLM最后一层解码器的隐状态，再通过一个多层感知机 (MLP) 输出能力值。
    *   **在线训练**：能力估计器通过在策略训练过程中产生的近期经验（目标-结果对）进行在线训练，使用二元交叉熵损失函数进行随机梯度下降。
    *   **学习进度 (LP) 计算**：MAGELLAN 通过保存历史上 $N$ 个时间步的能力估计器参数（LoRA适配器和MLP权重），计算**绝对学习进度 (Absolute Learning Progress, ALP)**：
        $$\hat{\text{ALP}}_{\pi_t}(g) = |C_{\theta_t}(g) - C_{\theta_{t-N}}(g)|$$
        该方法同时衡量了能力的进步与退步。
    *   **目标选择**：将每个目标视为一个“摇臂”，其效用值为 MAGELLAN 估计的 ALP。智能体采用基于 ALP 的比例采样策略（结合退火 $\epsilon$-贪心）来选择下一个要实践的目标。
    *   **架构**：采用两个独立的 LoRA 适配器在同一基座 LLM 上进行训练，分别用于强化学习策略和 MAGELLAN 的能力估计器，以确保训练稳定性和任务专用性。

*   **算法流程**：
    1.  选择目标 $g$。
    2.  执行一条轨迹 $\tau$ 并收集结果 $(g, r_{\tau, i})$。
    3.  使用轨迹数据更新强化学习策略 $\pi$。
    4.  将 $(g, r_{\tau, i})$ 添加到近期经验缓冲区 $D$
    5.  从 $D$ 中采样并更新能力估计器 $C_\theta$，同时将旧的参数 $\theta$ 存入历史缓冲区 $B$。
    6.  利用公式 $\hat{\text{ALP}}_{\pi_t}(g) = |C_{\theta_t}(g) - C_{\theta_{t-N}}(g) |$ 计算所有目标的 ALP。
    7.  根据 ALP 分布选择下一个目标，返回步骤 1。

### 3. 实验设计

*   **测试场景/数据集**：
    *   主要使用了专为研究常识泛化而设计的文本交互环境 **Little-Zoo**。该环境包含一个由约 2000 万个目标组合（80% 为不可行目标）构成的大型目标空间，目标按隐藏类别分为：抓取、种植、喂养食草动物、喂养食肉动物，且难度递增。
    *   在泛化性实验中，还使用了 **OpenR1-Math-220k** 数据集和 **BabyAI-Text** 环境来验证该方法在其他领域目标空间的有效性。

*   **对比基线 (Baselines)**：
    *   **Eval-ALP**：定期对所有目标进行全面评估来计算ALP，高计算成本但最精确。
    *   **EK-Eval-ALP**：在专家定义的目标组内进行采样评估以计算ALP。
    *   **Online-ALP**：仅在线使用目标实践结果计算ALP，不追踪能力迁移。
    *   **EK-Online-ALP**：在专家定义的目标组内在线计算ALP。
    *   **Uniform**：均匀随机采样目标，作为无课程学习的基线。

### 4. 资源与算力

*   **模型与并行**：使用 Flan-T5 250M 作为基座模型。训练通过 **Lamorel** 库部署了 2 个 LLM 实例（一个用于策略，一个用于能力估计器），采用数据并行。
*   **GPU 硬件**：每个 LLM 实例部署在 **1 张 Nvidia H100 80GB GPU** 上，因此一个实验种子运行总计需要 **2 张 Nvidia H100 80GB GPU**。
*   **训练时长**：在 Little-Zoo 环境中完成 50 万次训练回合的一个种子，大约需要 **80 GPU 小时**。

### 5. 实验数量与充分性

*   **实验数量与分组**：本文进行了四组主要实验，以系统回答提出的四个研究问题 (Q1-Q4)：
    1.  **能力估计质量 (Q1)**：在3种不同规模（25k, 50k, 100k目标）的Little-Zoo目标空间下，对比 MAGELLAN 与其他方法的能力估计误差和评估成本，共8个随机种子。
    2.  **课程学习效果 (Q2)**：在25k目标的Little-Zoo环境中，对比使用 MAGELLAN 与各基线方法进行课程学习后智能体的最终成功率，训练50万步，每5000步进行一次评估，共8个随机种子。
    3.  **泛化能力验证 (Q3)**：评估在Q2中训练好的策略和能力估计器在**未见过的测试目标集**上的泛化误差。
    4.  **动态适应性测试 (Q4)**：设计了“目标空间替换”实验，在训练过程中多次用全新目标替换旧目标，测试各方法能否快速适应变化。在不同的训练阶段共进行多次替换，每个替换点都进行8种子的独立训练。
*   **消融实验**：针对 MAGELLAN 自身的架构选择（共享/独立适配器、是否冻结LLM表示等）进行了消融研究，以验证其架构设计的合理性。
*   **充分性与公平性评价**：实验设计非常**充分且系统**。通过多个控制变量（目标空间大小、基线方法、目标集新旧、环境类型）的实验和消融研究，从估计精度、学习效率、泛化能力和动态适应性等多个维度全面评估了MAGELLAN的性能。对比基线涵盖了不同效率、知识要求和迁移能力的代表性方法，比较相对公平。但所有在线RL实验均使用Flan-T5 250M模型，对于验证该方法在更大规模模型上的可扩展性稍有不足。

### 6. 论文的主要结论与发现

1.  **高效且精准的能力估计**：MAGELLAN 能够仅凭在线交互经验，就达到与高成本的“全面评估法 (Eval-ALP)”相当的**能力估计精度**，且其估计成本为零，展现了极高的样本效率 (Q1)。
2.  **卓越的课程学习能力**：在无专家知识的情况下，MAGELLAN 是**唯一能够引导 LLM 智能体完全掌握所有目标类别**（包括最复杂的“喂养食肉动物”）的方法，其性能显著优于 Online-ALP 和 Uniform，并能够接近依赖专家知识的 EK-Online-ALP 方法 (Q2)。
3.  **强大的语义泛化能力**：MAGELLAN 能从已见目标的经验中学习到的语义关系，成功**泛化到从未见过的目标**上，对其能力进行准确预测，这远超 Online-ALP 的表现 (Q3)。其内部表征会动态重组，将语义相近、难度相似的目标聚类。
4.  **对演化目标空间的动态适应性**：当目标空间发生剧变时，MAGELLAN 能利用其泛化能力**快速适应新目标**，接管旧目标的学习进度估计，或在零学习进度时与新基线持平，表现出极强的鲁棒性和适应性 (Q4)。

### 7. 优点

*   **方法新颖且有效**：首次将元认知监测与 LLM 的语义理解能力深度结合用于学习进度预测，巧妙地解决了大型语言目标空间中能力迁移估计的难题。
*   **实验设计全面系统**：针对四个关键问题（精度、效率、泛化、适应）设计了环环相扣的实验，逻辑清晰，论证有力。Little-Zoo 环境的设计也独具匠心，能有效评估常识驱动的泛化能力。
*   **实际应用价值高**：该方法不依赖专家知识，样本效率高，可动态适应环境变化，为构建能够在开放世界中自主学习和演化的 LLM 智能体提供了可行路径。
*   **可视化分析深入**：通过对 MAGELLAN 内部嵌入空间的可视化分析，直观地展示了其如何动态组织目标空间，增强了对模型行为的可解释性。

### 8. 不足与局限

*   **LLM 规模限制**：所有实验均在 Flan-T5 250M 这样的小规模模型上进行，虽然附录中测试了 Qwen2.5-0.5B 以证明鲁棒性，但方法在数十亿或更大参数规模模型上的表现和算力成本仍有待验证。
*   **环境相对简单**：实验主要在一个精心设计的文本游戏环境中进行。其在更复杂、更开放的真实世界任务（如具身智能、代码生成）中的有效性有待进一步检验。
*   **ALP 计算依赖权重储存**：通过保存历史模型权重来计算 ALP 的方式需要额外的存储空间，且参数 $N$ 的选择会影响估计的平滑度与灵敏度，这部分未见深入讨论。
*   **泛化性研究的局限性**：Q3 的泛化测试中，新的测试目标与训练目标属于同一类别，未能测试当环境动态或目标类型发生更本质性变化（如从组合物体变为解谜）时的泛化性能。
*   **专家知识的处理**：实验设置中，带有专家知识的方法 (EK-*) 获得了“去除不可行目标”的巨大优势，这使得无专家知识的 MAGELLAN 与其对比时，探索负担更重，起点不同。

(完)

根据您提供的上一次输出内容，其末尾已标记为“(完)”，整篇总结的结构化从“1. 论文的核心问题”到“8. 不足与局限”均已呈现完整，并未发现截断。因此，无需继续补全。

（完）
