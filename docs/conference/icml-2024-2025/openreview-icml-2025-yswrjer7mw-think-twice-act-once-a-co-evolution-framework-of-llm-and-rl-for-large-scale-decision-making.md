---
title: "Think Twice, Act Once: A Co-Evolution Framework of LLM and RL for Large-Scale Decision Making"
title_zh: 三思而行：面向大规模决策的LLM与RL协同进化框架
authors: "Xu Wan, Wenyue Xu, Chao Yang, Mingyang Sun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ySWrJer7mW"
tags: ["query:continual"]
score: 5.0
evidence: 提出LLM与RL智能体协同进化框架用于大规模工业决策
tldr: 针对大规模工业决策中LLM缺乏实时长序列决策能力和RL样本效率低的问题，提出ACE框架，通过LLM在RL训练中同时扮演策略演员与价值评论家双重角色，精炼次优动作。实验表明该方法在复杂工业决策场景中显著提升性能，为将进化思想融入工业智能体提供了新途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1691, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 830, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1698, \"height\": 868, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 856, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 860, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1756, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 1175, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1771, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yswrjer7mw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1768, \"height\": 871, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1829, \"height\": 957, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 857, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 522, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 891, \"height\": 336, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1758, \"height\": 534, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yswrjer7mw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1170, \"height\": 719, \"label\": \"Table\"}]"
motivation: LLM和RL分别面临实时决策能力不足和样本效率低下问题，尤其在大规模工业场景中。
method: 提出ACE框架，让LLM在RL训练中作为策略演员和价值评论家进行轨迹精炼。
result: 在工业决策基准上，ACE在样本效率和最终性能上均优于单独LLM或RL方法。
conclusion: 协同进化框架有效结合LLM推理与RL学习，为工业智能体进化提供新范式。
---

## Abstract
Recent advancements in Large Language Models (LLMs) and Reinforcement Learning (RL) have shown significant promise in decision-making tasks. Nevertheless, for large-scale industrial decision problems, both approaches face distinct challenges: LLMs lack real-time long-sequence decision-making capabilities, while RL struggles with sample efficiency in vast action spaces. To bridge this gap, we propose **A**gents **C**o-**E**volution (ACE), a synergistic framework between LLMs and RL agent for large-scale decision-making scenarios. ACE introduces a dual-role trajectory refinement mechanism where LLMs act as both Policy Actor and Value Critic during RL's training: the Actor refines suboptimal actions via multi-step reasoning and environment validation, while the Critic performs temporal credit assignment through trajectory-level reward shaping. Concurrently, RL agent enhance LLMs' task-specific decision-making via prioritized experience replay.

Through extensive experiments across multiple power grid operation challenges with action spaces exceeding 60K discrete actions, ACE demonstrates superior performance over existing RL methods and LLM-based methods.

---

## 论文详细总结（自动生成）

好的，以下是对论文《Think Twice, Act Once: A Co-Evolution Framework of LLM and RL for Large-Scale Decision Making》的中文结构化总结。

### 1. 论文的核心问题与整体含义
*   **研究动机与背景**：大规模工业决策（如电力系统调度）要求智能体同时具备复杂的推理能力和快速的实时响应。现有技术中，强化学习 (RL) 在庞大动作空间（>60K离散动作）面前样本效率极低；大语言模型 (LLM) 虽推理能力强，但难以处理实时、长序列决策，且推理延迟无法满足工业控制需求（<1000ms）。
*   **核心问题**：如何结合LLM的推理优势与RL的高效执行能力，在不牺牲在线决策实时性的前提下，解决大规模决策任务中的样本效率低下和方案次优问题。
*   **整体含义**：本文提出一种“协同进化”框架，将LLM作为RL训练阶段的离线“导师”，通过对RL的交互轨迹进行反思和修正，实现两者能力的共同提升，为LLM在工业界的应用提供了一种新范式。

### 2. 方法论
论文提出Agents Co-Evolution (ACE) 框架，核心思想是“三思而行”：在执行阶段，由RL智能体与环境实时交互；在训练阶段，引入LLM对RL产生的轨迹进行双重离线精炼，二者协同进化。
*   **“行” (Act Once)：直接策略学习**
    *   RL模块采用SAC算法进行离线策略训练，其目标函数为最大化含熵正则的累计回报：$J(\pi) = \mathbb{E}_{\tau \sim \pi} [\sum_{t=0}^{\infty} \gamma^t (R(s_t, a_t) + \alpha \mathcal{H}(\pi(\cdot|s_t)))]$。经验元组存储于缓冲区 $\mathcal{D}_{RL}$。
*   **“三思” (Think Twice)：LLM的双重角色轨迹精炼**
    *   **LLM作为策略演员**：对于 $\mathcal{D}_{RL}$ 中奖励值低于阈值 $\bar{r}$ 的次优决策，LLM ( $f_{LLM}$ ) 通过多步推理和环境模拟验证，生成更优的动作 $\hat{a}_t$。这一过程利用了LLM从失败案例中反事实推理的能力。生成的精炼轨迹保存于缓冲区 $\mathcal{D}_{LLM}$。
    *   **LLM作为价值评论家**：在训练后期，LLM ( $g_{LLM}$ ) 对整个回合的轨迹进行长期因果关系推理，对关键决策点进行奖励重塑（reward shaping），以解决长时延下的奖励分配难题。奖励调整量被离散化为四个等级，以实现稳定调整。这个机制可以被视为对时间差分 (TD(λ)) 方法的一种扩展。
*   **经验收集与协同进化**
    *   构建混合经验缓冲区 $\mathcal{D}_{mix}$，通过一个概率分布 $p_{mix}$ 从 $\mathcal{D}_{RL}$ 和 $\mathcal{D}_{LLM}$ 中采样。此分布使用一个基于奖励的重要性权重 $w_r(\tau)$，优先采样那些经LLM精炼后获得更高回报的转移。
    *   RL的损失函数 $L_\pi(\theta)$ 也由该重要性权重加权，鼓励策略优先学习高价值的精炼经验。
    *   利用 $\mathcal{D}_{mix}$ 对LLM进行低秩适配 (LoRA) 微调，增强其任务特定能力，形成RL与LLM互相促进的闭环。

### 3. 实验设计
*   **数据集/场景**：实验在三个不同规模和难度的电力系统运行挑战上进行，均基于 **Grid2Op** 平台：
    1.  **L2RPN WCCI 2020**：中型电网，>6万离散动作空间，包含负荷波动和线路维护等现实场景。测试集为10个不同的3天场景。
    2.  **L2RPN NeurIPS 2020**：在上述基础上引入攻击者，测试集为24个为期一周的场景。
    3.  **L2RPN WCCI 2022**：采用IEEE-118标准电网，规模更大（>7万动作），引入可再生能源和储能的不确定性。训练数据跨越32年的电网数据。
*   **基准方法**：对比了三类方法：
    1.  **专家指导的RL**：前冠军方案（WCCI 2020冠军方案），作为骨干网络。
    2.  **纯LLM方法**：GPT-4和Qwen2-7B直接进行决策。
    3.  **LLM指导的RL**：修改版的LLM4Teach，在训练阶段使用KL散度约束对齐RL策略与LLM策略。
*   **ACE实现**：使用了Qwen2-7B (带SFT)和GPT-4（不带SFT）两种LLM组件。

### 4. 资源与算力
*   论文在附录的表4中提供了 ACE (Qwen2-7B + SFT) 在 NeurIPS 2020 环境下的训练开销。总计训练时长为**6小时18分钟3秒**。
*   RL部分训练了4万步，耗时约3小时4分钟。
*   LLM的额外开销包括：508次推理调用（约1小时48分钟）、4981次采样调用（约59分钟）和2次SFT训练（约26分钟）。
*   文中**未明确提及**具体使用的GPU型号与数量，但提供了各部分的时间开销，这能间接估算算力需求。

### 5. 实验数量与充分性
*   **实验数量可观且充分**：论文包含以下多组实验：
    1.  **主要结果**：在3个不同难度、不同规模的数据集上，与3大类别的基线方法进行了全面对比，评估指标包括回合奖励、存活率、样本需求和测试时间。
    2.  **消融实验**：针对核心组件（移除 $f_{LLM}$、移除 $g_{LLM}$、移除坏案例推理、移除多轮推理）进行了消融分析。
    3.  **超参数分析**：对 $f_{LLM}$ 和 $g_{LLM}$ 内部的多个关键超参数（如查询频率、坏案例阈值、SFT频率、轨迹选择标准、奖励塑造幅度 K）进行了详细的独立影响分析。
    4.  **案例研究与可视化**：通过图表展示了ACE动作精炼的具体过程。
*   **客观性与公平性**：实验设计比较客观。基线选择有代表性（包括冠军方案和最新的LLM-RL集成方法），对比维度全面（控制效果、效率、样本效率、决策时间），并提供了详细的运行时间开销，以证明其实时部署的可行性。

### 6. 主要结论与发现
*   **性能优越**：ACE框架在三个具有挑战性的大规模电力系统竞赛中，均显著优于所有基线方法，在回合奖励和存活率指标上取得领先。
*   **样本效率极高**：ACE仅需极少数量的LLM精炼样本（如WCCI 2020中287个），就能显著加速RL的收敛，所需的总训练步数（如40K步）远少于传统RL（100K步）。
*   **协同进化有效**：通过RL交互数据和LLM精炼数据构建的混合缓冲区，不仅提升了RL策略，也通过SFT增强了LLM的任务特定决策能力，验证了“协同进化”的有效性。
*   **LLM推理方式更优**：相比于强迫RL策略在整体上与LLM对齐（如LLM4Teach），ACE选择性的轨迹精炼方式避免了LLM在长序列决策上的固有劣势，更适用于工业场景。

### 7. 优点
*   **创新性强且有效**：创造性地将LLM的推理和规划能力从在线推理转移到离线训练，设计了“演员-评论家”双重角色，成功解决了LLM在实时控制中延迟高的核心矛盾。
*   **框架设计精巧**：“三思而行”的理念清晰，各组件（演员、评论家、混合缓冲区、奖励加权）协同工作，形成了一个高效的正反馈循环。
*   **实验扎实**：在极具挑战的工业级基准上进行了验证，实验覆盖范围广、对比充分，并公开了训练开销，展现了方法的实用性。

### 8. 不足与局限
*   **领域泛化性待验证**：实验场景高度集中于电力系统控制，尽管这个领域极具代表性，但ACE框架在其他类型的大规模控制问题（如交通控制、多机器人协同）上的有效性仍需进一步验证。
*   **LLM依赖与成本**：尽管LLM仅在离线训练时使用，但其推理和微调仍然是一笔不小的开销。对于资源受限的团队或无法使用GPT-4等商用API的情况，基于开源小模型（如Qwen2-7B）的性能上限可能受限。
*   **超参数敏感性**：论文展示了多个超参数（如坏案例阈值、查询频率等）对性能有显著影响，在实际应用中可能需要额外的时间和资源进行参数调优。
*   **奖励设计的复杂性**：LLM作为价值评论家模块依赖于精心设计的提示词和奖励重塑逻辑，这本身是一种引入专家知识的方式，可能在不同环境中难以自动化地迁移。

（完）
