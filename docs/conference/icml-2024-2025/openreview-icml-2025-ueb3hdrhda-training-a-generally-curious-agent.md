---
title: Training a Generally Curious Agent
title_zh: 训练一个通用好奇心智能体
authors: "Fahim Tajwar, Yiding Jiang, Abitha Thankaraj, Sumaita Sadia Rahman, J Zico Kolter, Jeff Schneider, Russ Salakhutdinov"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=UeB3Hdrhda"
tags: ["query:continual"]
score: 6.0
evidence: 智能体基于环境反馈调整行为，无需梯度更新
tldr: 本文提出Paprika，一种微调方法，使语言模型成为具有通用好奇心的智能体。通过在不同任务的合成交互数据上训练，模型能学会根据环境反馈在上下文中调整行为，而无需额外梯度更新。实验表明，微调后的模型能够将决策能力迁移到全新任务，展示了在动态环境中的自适应性。该工作为构建自我改进的AI系统提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1588, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1755, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1766, \"height\": 524, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1767, \"height\": 1088, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1769, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1761, \"height\": 1084, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1765, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1767, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1769, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1326, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1324, \"height\": 444, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1327, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1762, \"height\": 842, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1749, \"height\": 509, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ueb3hdrhda/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1748, \"height\": 523, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 855, \"height\": 553, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1625, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1814, \"height\": 2137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1252, \"height\": 113, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 941, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 420, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 332, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 330, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1679, \"height\": 1471, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1700, \"height\": 443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1736, \"height\": 95, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1427, \"height\": 599, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1765, \"height\": 1058, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1410, \"height\": 1850, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1759, \"height\": 2140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ueb3hdrhda/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1237, \"height\": 2093, \"label\": \"Table\"}]"
motivation: 现有语言模型在需要策略性信息收集的场景中探索不足。
method: 提出Paprika微调方法，利用多样化任务的合成交互数据训练模型在上下文中探索和适应。
result: 微调后的模型能有效将决策能力迁移到未见任务，无需额外训练。
conclusion: 为构建能动态适应的自我改进智能体提供了有效途径。
---

## Abstract
Efficient exploration is essential for intelligent systems interacting with their environment, but existing language models often fall short in scenarios that require strategic information gathering. In this paper, we present **Paprika**, a fine-tuning approach that enables language models to develop general decision-making capabilities that are not confined to particular environments. By training on synthetic interaction data from different tasks that require diverse strategies, Paprika teaches models to explore and adapt their behavior on a new task based on environment feedback in-context without more gradient updates. Experimental results show that models fine-tuned with Paprika can effectively transfer their learned decision-making capabilities to entirely unseen tasks without additional training. Unlike traditional training, our approach's primary bottleneck lies in sampling useful interaction data instead of model updates. To improve sample efficiency, we propose a curriculum learning strategy that prioritizes sampling trajectories from tasks with high learning potential. These results suggest a promising path towards AI systems that can autonomously solve novel sequential decision-making problems that require interactions with the external world.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
*   **核心问题**：当前的大语言模型在需要与环境进行多轮交互、策略性地收集信息的顺序决策任务（Sequential Decision-Making Problems）中表现不佳。模型通常缺乏一种通用的、能迁移到新环境中的“好奇心”或“探索能力”。
*   **研究动机**：构建能够自主实现目标的智能体系统，关键在于其与外部世界进行有效交互和信息收集的能力。传统训练方法要么缺乏相应的交互数据，要么因直接部署到现实世界风险过高而不可行。因此，通过合成数据训练模型，使其具备能在上下文中进行强化学习（In-Context RL）的泛化能力，成为一个重要的研究方向。
*   **整体含义**：本文旨在探索一种可扩展的微调方法，不是教会模型解决特定任务，而是教会模型解决任务的“通用过程”，使其在遇到全新任务时，能像人类一样通过探索和互动来收集信息并完成任务。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
*   **核心思想**：通过在一系列多样化、需要信息收集的文本任务上，使用模型自我生成的数据进行微调，来培养LLM通用的序列决策能力。该方法被称为 **Paprika**。
*   **关键技术细节**：
    *   **任务设计**：设计了10个多样化的文本式任务组（如20个问题、猜城市、Wordle、扫雷等），要求模型进行多轮交互和策略性探索。
    *   **数据构建**：
        1.  使用基础模型以高温度和Min-p采样策略，为每个任务生成多条交互轨迹，以确保数据多样性。
        2.  根据任务成功率对轨迹进行评分。
        3.  构建偏好数据对 `(hw, hl)`，其中 `hw` 是表现最好的轨迹，`hl` 是随机选择的低分轨迹。
    *   **优化目标**：采用一种**序列化版本的直接偏好优化（DPO）** 来增加成功轨迹的相对似然。该变体仅计算模型所生成的动作（Action）token上的损失，而忽略环境生成的观察（Observation）token。
        具体损失函数（RPO）结合了监督微调（SFT）和序列DPO损失：
        `LRPO(DDPO) = LDPO(DDPO) + α · LSFT(DDPO)`
    *   **可扩展的在线课程学习**：
        *   **动机**：数据采样是训练瓶颈，不同任务的难度差异大，统一采样效率低。
        *   **学习潜力度量**：定义了任务 `τ` 在策略 `π` 下的学习潜力 `νπ(τ)` 为变异系数（Coefficient of Variation）：`νπ(τ) = σπ(τ) / Rπ(τ)`。高方差和高平均奖励的任务被认为具有更高的学习潜力。
        *   **算法流程**：将任务选择问题建模为一个多臂老虎机（MAB）问题，使用上置信界（UCB）算法动态地从不同任务组中优先采样具有高学习潜力的任务，以提高样本效率。

### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法。
*   **数据集/场景**：论文设计了10个自定义文本任务组作为benchmark，包括：20个问题、猜我所在的城市、Wordle、细胞自动机、客服、谋杀之谜、Mastermind、战舰、扫雷、多臂老虎机最佳臂选择。这些任务被划分为训练集和测试集。
*   **基础模型**：主要使用 **Llama-3.1-8B-Instruct** 和 **Gemma-3-12B-IT** 作为基座模型进行微调。
*   **对比方法/基线**：
    *   **基线模型**：原始的未微调基础模型。
    *   **强基线**：GPT-4o-mini。
    *   **消融实验**：
        *   **Paprika (Full)**：在所有10个任务组上训练。
        *   **Paprika (LOO, Leave-One-Out)**：在除测试任务组外的所有其他任务组上训练，以测试零样本泛化能力。
        *   **Paprika (Single Task Group)**：仅在单个任务组上训练和测试。
        *   **Paprika (SFT only)**：仅进行监督微调，不进行后续的RPO（DPO+SFT）阶段，用于验证RPO的必要性。
        *   **微调在常规多轮数据上**：在WildChat数据集上微调，以验证仅有交互结构的数据是否有效。

### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。
*   **GPU型号与数量**：
    *   Llama-3.1-8B-Instruct模型训练：使用**8块NVIDIA L40S GPU**组成的单节点。
    *   Gemma-3-12B-IT模型训练：使用**8块NVIDIA H100 GPU**组成的单节点。
    *   推理和数据生成：使用**单块NVIDIA A40 GPU**。
*   **其他成本**：
    *   用于生成训练数据和评估的API（调用GPT-4o-mini等）总成本约为**20,000美元**。
    *   运行一次完整实验的API成本估计不超过1,000美元。

### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。
*   **实验数量**：论文进行了多组全面的实验，包括：
    *   在10个任务组上对两个主流LLM进行全量微调评估。
    *   对10个任务组分别进行留一法（LOO）实验以测试泛化性。
    *   对10个任务组进行单任务组训练和测试。
    *   在一组（20 questions）任务上进行课程学习与均匀采样的多轮训练对比。
    *   对6个任务组进行SFT vs. SFT+RPO的消融实验。
    *   与在WildChat上微调的模型进行比较，以排除交互结构本身的影响。
    *   在标准NLP基准（MT-Bench, MMLU-Pro等）上评估模型能力是否有退化。
    *   在不同温度（0.3, 0.7, 1.0）下进行评估，并采用多种成功率指标（平均成功率、Pass@4成功率）。
*   **充分性与公平性**：实验设计非常充分和系统。通过留一法和单任务组训练，公平地检验了方法的泛化性，而非仅在单任务上过拟合。消融实验清晰展示了方法各组成部分（RPO损失、课程学习）的价值。对比WildChat微调等基线，排除了混淆因素。多种评估指标和温度设置增加了结果的可靠性。

### 6. 论文的主要结论与发现。
*   Paprika能够显著提升LLM在多样化顺序决策任务上的表现。例如，在Llama-3.1-8B-Instruct上，平均成功率提升了47%。
*   Paprika训练出的模型的决策能力（策略性探索）可以**零样本泛化**到全新的、未见过的任务组中。
*   在多个任务组上看到的多样化轨迹有助于模型学习更好的组内策略（Paprika (Full) 优于 Paprika (Single Task Group)）。
*   提出的基于变异系数的课程学习算法能够提高数据效率，优于均匀采样策略。
*   Paprika微调不仅提升了任务成功率，还提高了任务效率（减少了平均所需回合数），并且**未损害模型在标准NLP基准上的常规能力**。

### 7. 优点：方法或实验设计上有哪些亮点。
*   **概念新颖**：提出“上下文强化学习”的微调范式，旨在教会模型通用的探索和决策过程，而非特化到某个任务。
*   **方法简洁有效**：使用自我生成的数据和序列DPO进行微调，无需依赖已知的最优算法（如UCB）来生成训练数据。
*   **强大的泛化能力**：实验有力地证明了学习到的策略可以跨任务组进行零样本迁移，这是迈向通用智能体的关键一步。
*   **实验设计严谨**：通过大量的消融实验、与强基线的对比、多种评估指标以及对常规能力不降级的验证，使得结论具有很强的说服力。
*   **关注数据效率**：识别出数据采样是瓶颈，并提出了一个理论驱动（变异系数）且实用的（分组元数据+UCB）课程学习解决方案。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等。
*   **对基座模型的依赖**：该方法属于“拒绝采样”微调，其性能高度依赖于初始基座模型的能力。如果基座模型在合理预算内无法产生任何成功的轨迹，Paprika将难以发挥作用。
*   **未使用在线RL**：训练采用了离线的DPO而非在线强化学习。作者承认，鉴于在线RL在其它领域的成功，使用在线RL可能会带来更大的性能提升。
*   **任务设计成本**：任务组的实现（尽管由GPT-4辅助）仍需要大量人工设计和工程努力，如何自动生成高质量、多样化的训练环境仍是一个挑战。
*   **课程学习对元数据的依赖**：课程学习算法的有效性取决于预先定义的任务分组（如难度等级）的质量，这需要领域知识或额外的计算资源。
*   **环境模拟的误差**：对于使用LLM模拟环境的任务，存在环境被“hack”或反馈不准确的风险，尽管使用了LLM-Judge，仍无法完全避免。

（完）
