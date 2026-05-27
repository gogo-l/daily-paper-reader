---
title: Training a Generally Curious Agent
title_zh: 训练一个普遍好奇的智能体
authors: "Fahim Tajwar, Yiding Jiang, Abitha Thankaraj, Sumaita Sadia Rahman, J Zico Kolter, Jeff Schneider, Russ Salakhutdinov"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UeB3Hdrhda"
tags: ["query:continual"]
score: 4.0
evidence: Paprika微调使智能体无需额外训练即可适应新任务，类似于动态环境中的自我提升
tldr: 提出Paprika微调方法，通过在多种要求不同策略的合成交互数据上训练，使语言模型发展出通用探索与决策能力，能在新任务上根据环境反馈自适应行为，无需额外梯度更新，展示了跨任务迁移决策的潜力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1588, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1755, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1766, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1767, \"height\": 1088, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1761, \"height\": 1084, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1765, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1767, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1769, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1326, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1324, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1327, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1762, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1749, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1748, \"height\": 523, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1625, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1814, \"height\": 2137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1252, \"height\": 113, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 941, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 420, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 332, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 330, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1679, \"height\": 1471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1700, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1736, \"height\": 95, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1427, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1765, \"height\": 1058, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1410, \"height\": 1850, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1759, \"height\": 2140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1237, \"height\": 2093, \"label\": \"Table\"}]"
motivation: 现有语言模型在需要策略性信息收集的场景中探索能力不足。
method: 通过在多样策略的合成交互数据上微调，训练模型在新任务中基于反馈自适应行为。
result: Paprika微调后的模型能有效将决策能力迁移到完全未见过的任务。
conclusion: 该方法使模型具备一般化好奇心，可在新环境中灵活探索与决策。
---

## Abstract
Efficient exploration is essential for intelligent systems interacting with their environment, but existing language models often fall short in scenarios that require strategic information gathering. In this paper, we present **Paprika**, a fine-tuning approach that enables language models to develop general decision-making capabilities that are not confined to particular environments. By training on synthetic interaction data from different tasks that require diverse strategies, Paprika teaches models to explore and adapt their behavior on a new task based on environment feedback in-context without more gradient updates. Experimental results show that models fine-tuned with Paprika can effectively transfer their learned decision-making capabilities to entirely unseen tasks without additional training. Unlike traditional training, our approach's primary bottleneck lies in sampling useful interaction data instead of model updates. To improve sample efficiency, we propose a curriculum learning strategy that prioritizes sampling trajectories from tasks with high learning potential. These results suggest a promising path towards AI systems that can autonomously solve novel sequential decision-making problems that require interactions with the external world.

---

## 论文详细总结（自动生成）

好的，以下是根据论文《Training a Generally Curious Agent》生成的结构化深度分析总结。

### 1. 论文的核心问题与整体含义

-   **核心问题**：当前的大语言模型在需要战略性信息收集的序列决策任务（如多轮交互、主动探索）中表现不佳，缺乏一种通用的、不特定于单一任务的探索与决策能力。
-   **整体含义**：本文旨在赋予大语言模型一种**普遍的好奇心**，即一种可以被“摊销”（amortized）的通用探索策略。
    -   其核心思想不是为每个具体任务训练一个模型，而是通过在不同任务上微调，教会模型**如何进行上下文强化学习**。
    -   这意味着模型在面对一个全新的、未见过的任务时，能够仅凭任务描述和交互反馈，在上下文中动态调整其策略以获取信息并完成任务，而无需进行任何额外的参数更新。这为构建能够自主解决现实世界中新颖决策问题的AI系统指明了方向。

### 2. 论文提出的方法论

-   **核心思想（Paprika框架）**：该框架旨在通过大规模、多样化的合成交互数据，教会语言模型通用的元强化学习能力，使其能够在新环境中进行“零样本”泛化。

-   **关键技术细节**：
    -   **任务设计**：精心设计了10个文本化的部分可观测马尔可夫决策过程（POMDP）任务组，如“20个问题”、“猜城市”、“扫雷”和“战舰”等。这些任务覆盖了猜谜、编码与调试、客服、推理和经典游戏等多种场景，并且任务环境由其他大语言模型或硬编码程序模拟。
    -   **数据集构建**：使用基础模型，通过高温（如1.5）和Min-p采样等鼓励多样性的解码策略，为每个训练任务生成多个交互轨迹。然后将表现最好（最快成功）的轨迹作为“获胜”样本，随机选择一个更低分的轨迹作为“失败”样本，构建偏好对数据集。
    -   **优化目标**：采用一种融合方法进行微调。
        -   **监督微调**：首先，仅对高质量的成功轨迹进行监督微调，类似于行为克隆。
        -   **多轮直接偏好优化**：随后，采用一种适用于多轮对话场景的直接偏好优化目标。其核心是最大化模型生成“获胜”轨迹的概率与参考模型生成该轨迹的概率之比，同时最小化“失败”轨迹的这一比值。计算仅在模型生成的动作令牌上进行，不包括环境生成的令牌。
        -   **结合目标（RPO）**：最终，将监督微调损失和多轮DPO损失组合起来（RPO目标），以防止模型性能退化。
    -   **可扩展的在线课程学习**：为解决数据采样效率瓶颈，提出一个课程学习策略。
        -   **学习潜力度量**：定义任务的学习潜力为**变异系数** `ν = σ / R`，即任务奖励的方差 `σ²` 与平均奖励 `R` 之比。该指标衡量了一个任务产生多样化且有学习价值轨迹的潜力。
        -   **任务选择算法**：将有相似难度的任务划分为一组，将任务组选择问题建模为一个多臂老虎机（MAB）问题，并使用上置信界（UCB）算法动态选择那些当前学习潜力高的任务组进行采样和训练，从而优先利用计算资源。

### 3. 实验设计

-   **数据集/场景**：实验在作者设计的**10个任务组**上进行，包括：20个问题、猜我的城市、Wordle、元胞自动机、客服、谋杀之谜、Mastermind、战舰、扫雷和Bandit最佳臂选择。每个任务组都分为训练集和测试集。
-   **基础模型**：主要实验在`Llama-3.1-8B-Instruct`和`Gemma-3-12B-IT`两个开源大语言模型上进行。
-   **对比方法**：
    -   **基座模型**：未经微调的基础对话模型。
    -   **GPT-4o-mini**：作为闭源模型的强基线。
    -   **Paprika（Full）**：在所有10个任务组上微调的模型。
    -   **Paprika（LOO）**：留一法模型，即在9个任务组上训练，在第10个上测试，用于评估泛化能力。
    -   **Paprika（单任务组）**：仅在单个任务组上训练并测试，作为组内学习能力的基线。
    -   **SFT only（消融实验）**：只进行监督微调，不进行RPO阶段。
    -   **微调在WildChat上**：在通用的多轮对话数据上微调，以排除多轮交互数据本身的增益。

### 4. 资源与算力

-   论文在附录中提到了详细的算力配置。
-   **训练**：`Llama-3.1-8B-Instruct`模型使用单节点8个 **NVIDIA L40S GPU** 进行训练。更大的`Gemma-3-12B-IT`模型则使用单节点8个 **NVIDIA H100 GPU**。
-   **推理/采样**：用于生成训练数据和评估时，使用单个 **NVIDIA A40 GPU**。
-   **API费用**：论文提及用于生成训练数据和运行评估的总API费用约为 **20,000美元**。

### 5. 实验数量与充分性

-   **实验数量**：论文进行了相当充分和系统的实验。
    -   **主实验**：在两个不同规模、不同家族的基础模型上，于10个任务组中对比了多个基线，并评估了多个温度下的平均成功率和Pass@4成功率。
    -   **泛化实验**：通过10组留一法实验和1组全新任务（修改版Wordle）实验，系统性地检验了零样本迁移能力。
    -   **消融实验**：对比了SFT-only与RPO的效果，以及通用多轮对话数据微调的效果。
    -   **效率分析**：提供了平均解决回合数作为任务效率的补充指标。
    -   **课程学习实验**：在20个问题任务上进行了多轮训练，对比了课程学习与均匀采样的效果。
    -   **标准能力测试**：在MT-Bench、AlpacaEval等6个标准基准上评估，验证微调是否损害模型通用能力。
-   **充分性与客观性**：实验设计全面且客观。对比基线丰富，评估指标多维，并严格区分了训练集与测试集。对零样本泛化能力的检验尤为严格和扎实。

### 6. 论文的主要结论与发现

-   **Paprika能显著提升大语言模型的决策能力**：该方法在两个不同模型上平均提升了10个任务组的成功率（如在Llama-3.1-8B-Instruct上提升了47%）。
-   **所学策略具有强大的零样本泛化能力**：通过留一法实验证明，模型可以将学到的决策能力迁移到从未见过的任务组上，有时甚至超越仅在单个任务组上训练的模型。
-   **课程学习能改善数据效率**：提出的基于变异系数的课程学习策略，在“20个问题”任务上相比随机均匀采样取得了更优的性能（平均成功率提升1.4%，Pass@4提升3.3%）。
-   **Paprika不损害模型通用能力**：在标准学术基准上的测试表明，经过Paprika微调的模型没有出现性能显著退化。
-   **单纯的多轮对话数据不足以提升决策能力**：在WildChat数据集上微调的模型在所有决策任务上表现极差，说明针对信息收集任务的专门训练是必要的。

### 7. 优点

-   **新颖的范式**：提出从“为特定任务训练模型”转向“训练模型学会在上下文中进行探索和决策”，思路具有前瞻性和可扩展性。
-   **泛化能力突出**：通过系统性的留一法实验清晰展示了零样本策略迁移的泛化能力，这是该工作最核心的亮点。
-   **方法设计合理**：任务设计丰富多样，优化方法（SFT+多轮DPO）针对性强，课程学习策略在理论上对数据瓶颈问题提出了解决思路。
-   **评估全面**：不仅评估了任务成功率，还评估了效率、泛化性、对基础能力的影响以及多模型适用性，可信度高。

### 8. 不足与局限

-   **依赖强大的基础模型**：训练数据由基础模型自举生成，若基础模型性能太差，无法生成有效的学习信号，则方法会失效。
-   **环境实现成本高**：尽管借助了大语言模型生成任务，但10个任务组的实现和调试仍然需要大量的人力投入。
-   **课程学习的依赖性**：课程学习算法的效果强依赖于任务分组的质量，而良好的“相似性”分组需要先验知识。
-   **离线训练的局限性**：作者指出，由于计算资源限制，当前采用离线偏好优化。转向在线强化学习可能会带来更大的性能提升，但目前未验证。
-   **泛化性的边界**：在部分任务上，泛化效果有限，甚至出现负迁移。如何确保正向迁移是一个待研究问题。

（完）
