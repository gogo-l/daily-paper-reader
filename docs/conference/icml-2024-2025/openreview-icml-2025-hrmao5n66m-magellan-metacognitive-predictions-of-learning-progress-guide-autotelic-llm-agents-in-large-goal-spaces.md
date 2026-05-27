---
title: "MAGELLAN: Metacognitive predictions of learning progress guide autotelic LLM agents in large goal spaces"
title_zh: MAGELLAN：元认知学习进度预测引导大目标空间中的自驱动LLM代理
authors: "Loris Gaven, Thomas Carta, Clément ROMAC, Cédric Colas, sylvain lamprier, Olivier Sigaud, Pierre-Yves Oudeyer"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=hRMAo5N66M"
tags: ["query:continual"]
score: 8.0
evidence: 元认知学习进度预测用于演化目标空间中的自驱动代理
tldr: 大目标空间中自驱动的持续探索要求代理高效评估学习进度，但传统方法采样成本高且依赖专家分组。MAGELLAN框架使LLM代理获得元认知监测能力，在线预测自身胜任力与学习进度，通过建模目标语义关系实现样本高效的学习进度估计和动态目标优先级调整，显著提升了在演化目标空间中的探索效率和学习效果，为自进化智能体研究提供了可扩展的方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 830, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 841, \"height\": 597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 694, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 823, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 759, \"height\": 1173, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 832, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 783, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 810, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1724, \"height\": 1714, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1029, \"height\": 674, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1608, \"height\": 1184, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1070, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1071, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1074, \"height\": 864, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1689, \"height\": 861, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1764, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1772, \"height\": 906, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1421, \"height\": 1100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1626, \"height\": 1200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1708, \"height\": 1430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 575, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 575, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 571, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 573, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 577, \"height\": 393, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 842, \"height\": 1298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1718, \"height\": 1206, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-hrmao5n66m/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1389, \"height\": 604, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 679, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 884, \"height\": 329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1669, \"height\": 462, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1594, \"height\": 714, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 713, \"height\": 665, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 524, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 410, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-hrmao5n66m/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 444, \"height\": 315, \"label\": \"Table\"}]"
motivation: 开放环境中自驱动代理需高效预估学习进度，传统方法采样成本高或依赖手工分组。
method: 提出元认知框架MAGELLAN，让LLM代理在线学习预测自身能力与学习进度，利用语义关系。
result: 实验表明MAGELLAN提升目标达成率，实现样本高效探索，在演化目标空间中表现更优。
conclusion: 元认知引导的自驱探索为自进化智能体提供高效可扩展方案。
---

## Abstract
Open-ended learning agents must efficiently prioritize goals in vast possibility spaces, focusing on those that maximize learning progress (LP). When such autotelic exploration is achieved by LLM agents trained with online RL in high-dimensional and evolving goal spaces, a key challenge for LP prediction is modeling one’s own competence, a form of metacognitive monitoring. Traditional approaches either require extensive sampling or rely on brittle expert-defined goal groupings. We introduce MAGELLAN, a metacognitive framework that lets LLM agents learn to predict their competence and learning progress online. By capturing semantic relationships between goals, MAGELLAN enables sample-efficient LP estimation and dynamic adaptation to evolving goal spaces through generalization. In an interactive learning environment, we show that MAGELLAN improves LP prediction efficiency and goal prioritization, being the only method allowing the agent to fully master a large and evolving goal space. These results demonstrate how augmenting LLM agents with a metacognitive ability for LP predictions can effectively scale curriculum learning to open-ended goal spaces.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：开放式的自主学习代理（Autotelic Agents）在面对海量、高维且不断演化的目标空间时，如何高效地评估和优先选择那些能带来最大“学习进度”（Learning Progress, LP）的目标，从而组织起高效的自动课程学习（Automatic Curriculum Learning）。
*   **研究动机**：
    *   人类是优秀的开放式学习者，其内在驱动力之一是好奇心，特别是对学习进度的追求。让AI具备类似能力是通往通用人工智能的重要一步。
    *   传统LP估计方法存在严重缺陷：要么依赖对整个目标空间进行昂贵的、周期性的全量评估（Evaluation-based），要么只能在线更新被练习的目标的LP，无法捕捉目标间的能力迁移（Online methods），要么依赖专家预先定义的目标分组来缓解前两者的问题，但这种方式又“脆”又缺乏灵活性。
    *   近期，以大型语言模型（LLM）为核心的在线强化学习代理展现了强大的语言理解和泛化能力，这为解决上述问题提供了新可能。
*   **整体含义**：论文提出，最关键的不是发明全新的LP计算公式，而是赋予LLM代理一种“元认知监测”能力，让其能够自我建模和预测自身在不同目标上的能力变化，并利用语言的语义结构将这种预测泛化到未见过的目标上，从而在广阔的目标空间中高效、动态地构建学习路径。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

*   **核心思想 (MAGELLAN框架)**：MAGELLAN（MetAcognitive GEneralization of LeArning progress in LANguage model agents）是一个元认知模块，它不直接计算LP，而是通过学习一个**胜任力估计器（Competence Estimator）** $C_{\theta_t}(g)$ 来持续预测代理当前策略 $\pi_t$ 在任意目标 $g$ 上的成功率。然后用两个不同时间点的胜任力估计值的绝对差值来近似**绝对学习进度（ALP）**。
*   **关键技术细节**:
    *   **胜任力估计器学习**：
        *   **输入**: 目标 $g$（即任务描述）。
        *   **架构**: 利用代理内部的LLM将 $g$ 编码成隐向量，然后接一个多层感知器（MLP）头来输出预测的成功概率 $C_{\theta_t}(g)$。
        *   **训练**: 使用一个缓冲区 $D_t$ 存储最近的 $M$ 个训练片段（目标-结果对），通过最小化二元交叉熵损失来在线更新LLM的LoRA适配器和MLP的参数 $\theta_t$。这样，更新一个目标的胜任力会通过LLM的语义表示空间自动影响相似的目标。
    *   **绝对学习进度（ALP）计算**：
        *   维护一个权重缓冲区 $B_t$，定期保存胜任力估计器的参数。
        *   $\hat{ALP}_{\pi_t}(g) = |C_{\theta_t}(g) - C_{\theta_{t-N}}(g)|$，其中 $N$ 是回溯步数。
    *   **目标选择与课程构建**：
        *   采用多臂老虎机方案，每个目标都是一个“臂”，其效用值就是MAGELLAN为其估算的ALP值。
        *   然后使用退火 $\epsilon$-贪心策略，按ALP值的比例去采样下一个要练习的目标。
    *   **整体流程**：代理与环境交互，完成一个目标后获得二元成功/失败结果，该结果被存入缓冲区 $D_t$。MAGELLAN利用 $D_t$ 更新 $C_{\theta}$。当需要选择下一个目标时，利用缓冲区 $B_t$ 中当前和最旧的参数计算所有目标的 $\hat{ALP}$，并据此选择一个高LP的目标进行练习。该过程周而复始。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

*   **实验场景 (Environment)**:
    *   **主要场景**: **Little-Zoo** —— 论文专门为此研究设计的全文本交互环境，用于测试基于常识的泛化能力。环境包含家具、植物、食草动物、食肉动物等对象，目标具有层次结构（如“抓取”、“种植植物”、“饲养食草动物”等），且绝大多数目标因缺少关键物品而无法完成，模拟了真实世界中目标空间的稀疏性。完整目标空间约有2000万个组合。
    *   **辅助场景**: **OpenR1-Math-220k** 和 **BabyAI-text** —— 用于验证MAGELLAN在更通用领域的胜任力估计能力。
*   **Baseline 对比方法**:
    *   **Online-ALP**: 仅在线更新被练习目标的胜任力，LP由其自身历史表现的差值计算。
    *   **Eval-ALP**: 定期（如每1000步）停止训练，对所有目标进行全面评估来计算LP（因计算成本过高，仅在Q1实验中作为参考，未在完整训练中运行）。
    *   **EK-Online/Eval-ALP**: 前述方法的“增强版”，依赖“专家知识”（Expert Knowledge, EK）将目标预先分为5个组（4个可行目标组+1个不可能目标组），LP和课程均按组进行估测和选择。
    *   **Uniform**: 完全随机均匀采样目标，不使用LP。
*   **实验评估指标**:
    *   胜任力估计误差（与Eval-ALP的最新估计对比）。
    *   代理在各类目标上的成功率。
    *   泛化到未见过的测试目标时的胜任力估计误差。
    *   在动态变化的目标空间中，代理掌握新目标的速度（样本效率）。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。

*   **资源与算力**:
    *   **模型**: 主要使用Flan-T5-248M作为代理和MAGELLAN的基础LLM。
    *   **量化与加速**: 采用4-bit量化（QLoRA）以减少GPU显存占用；使用向量化环境并行（32个实例）；部署2个LLM实例进行数据并行以加速训练。
    *   **GPU**: 每个LLM实例使用1张Nvidia H100 80GB GPU，完整实验运行需 **2张H100**。
    *   **训练时长**: 对于Q2（在线课程学习）实验，一个随机种子训练50万步约需 **80 GPU小时**。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。

*   **实验数量与充分性**:
    *   **主要实验组数**: 论文围绕4个核心研究问题（Q1-Q4）设计了系统性的实验。
        *   **Q1（胜任力估计）**: 在3种不同大小的目标空间（25k, 50k, 100k）下对比了5种方法（含不同专家知识依赖的变体），并在2个额外场景（OpenR1, BabyAI）中验证。
        *   **Q2（在线课程学习）**: 在25k目标空间下，使用4种方法各进行50万步的完整RL训练。
        *   **Q3（泛化能力）**: 对Q2中训练好的代理在保留的测试集上进行评估，并对模型的嵌入空间进行了深入的可视化分析。
        *   **Q4（适应动态目标空间）**: 在训练过程中的10个不同时间点，进行目标空间的替换，测试3种方法在50k步内的适应能力。
        *   **消融实验**: 针对MAGELLAN的架构进行了4种变体对比，并对LLM模型规模的影响进行了评估。
    *   **充分性与公平性**:
        *   **充分**: 实验覆盖面广，从静态估计到动态学习，从已知目标到未知目标，从固定环境到变化环境，形成了完整的证据链。尤其难得的是对“专家知识”这一关键输入进行了控制变量，清晰展示了其影响。
        *   **客观**: 所有实验均使用8个随机种子汇报均值和标准差，保证了结果的可重复性和统计显著性。
        *   **公平**: 在对比时，明确指出了各方法的信息获取成本（如Eval-ALP的评估开销，EK系列方法的专家知识依赖），并在评估指标中予以区分（如虚线表示依赖专家知识），对比维度全面且公平。

### 6. 论文的主要结论与发现

*   **高效且准确的LP估计 (A1)**: MAGELLAN能够在零额外评估成本下，实现与昂贵全量评估方法（Eval-ALP）准确性相当的胜任力估计，其误差远低于在线方法（Online-ALP），且性能可与依赖专家知识的方法媲美。
*   **最优的课程学习效果 (A2)**: 在完整的在线RL训练中，MAGELLAN是**唯一一个**不依赖专家知识就能让代理掌握所有目标类别（包括最难的“饲养食肉动物”）的方法，且学习速度显著快于Online-ALP。
*   **强大的泛化能力 (A3)**: MAGELLAN不仅能学习目标间的语义关系，动态地形成聚类（如将“饲养食草动物”和“饲养食肉动物”聚在一起），还能将这种能力精准泛化到从未见过的测试目标上，使其在未知目标上的胜任力估计误差极小。
*   **对动态目标空间的快速适应 (A4)**: 当训练中途面临全新的目标集时，MAGELLAN能利用已学到的语义结构，迅速为新目标估算出合理的LP，并几乎无缝地延续其课程，其适应速度远超基线方法，并与依赖专家知识的方法持平。

### 7. 优点：方法或实验设计上有哪些亮点

*   **方法创新性强且优雅**:
    *   **元认知视角**: 将LP估计问题巧妙地转化为一个持续的自我能力监测问题，这是一种更本质的解决方案。
    *   **零成本泛化**: 利用LLM本身的语义嵌入空间来隐式地建模目标间的关系和迁移，无需任何专家分组或预训练，自适应性强。
    *   **架构解耦**: 论文通过消融实验证明，将策略学习和元认知学习分别使用独立的LoRA适配器是最佳实践，避免了两者的表征需求冲突。
*   **实验设计精妙**:
    *   **可控的测试平台（Little-Zoo）**: 为研究基于常识的泛化而专门设计的文本环境，目标空间庞大但结构清晰，完美平衡了复杂性和可控性，是评估该问题的理想“显微镜”。
    *   **多维度评估**: 实验设计从估计准确性、学习效率、泛化能力到动态适应性，层层递进，全面评估了提案的各方面性能，使得结论非常扎实。
    *   **对“专家知识”的控制**: 实验设计清晰地区分了方法内部能力（如泛化）和外部信息输入（专家分组）的作用，这大大增强了论证的说服力。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

*   **实验环境的局限性**: Little-Zoo是一个专门构建的、相对简单的结构化文本世界。其目标层次和相关性非常清晰（线性技术树）。MAGELLAN能否在更复杂、更模糊、语义关系更纠缠的真实世界任务空间（如代码生成、复杂机器人任务）中同样有效，还有待验证。
*   **对奖励信号的依赖**: 该方法依赖二元成功/失败信号来训练胜任力估计器。在稀疏奖励或难以定义明确成功标准的开放式任务中，其效果可能会打折扣。
*   **忽略知识遗忘**: 文中使用的ALP是绝对差值的计算，这同时捕捉了学习进步和知识遗忘。虽然在某些动态环境中这是合理的，但在稳定的学习场景下，遗忘信号可能会干扰LP估计，导致代理反复回到已掌握的任务上。文中未对此进行深入分析和解决。
*   **专家知识的“理想化”**: 基线中的EK系列方法依赖论文作者完美分组的专家知识（例如，将所有不可能目标归入一个类别）。在现实应用中，这种完美的、先验的知识是不存在的，这使得与EK方法的对比更像是一个理论上界，而非完全公平的现实对比。
*   **LLM规模的局限性**: 实验主要在2.5亿参数的Flan-T5上进行。虽然消融实验显示在一个5亿参数的模型上也表现稳健，但更大规模（7B， 70B+）的LLM在表征和泛化能力上的质变可能带来不同的表现和现象，论文未做探索。
（完）
