---
title: Knowledge Retention in Continual Model-Based Reinforcement Learning
title_zh: 持续基于模型的强化学习中的知识保持
authors: "Haotian Fu, Yixiang Sun, Michael Littman, George Konidaris"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DiqeZY27XK"
tags: ["query:continual"]
score: 9.0
evidence: 使用合成经验重放和内在探索保持知识
tldr: 针对基于模型的强化学习在序列任务中遗忘世界动力学的问题，提出DRAGO方法，结合合成经验重放和内在奖励驱动重访机制，维护增量发展的世界模型。实验显示该方法在连续任务中有效保持动力学知识，促进后续任务的快速学习。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1379, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1350, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 777, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1516, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1611, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1719, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1529, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1734, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1645, \"height\": 307, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 1018, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 1348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1779, \"height\": 580, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1782, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1096, \"height\": 1145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1075, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1457, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1322, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 963, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 839, \"height\": 203, \"label\": \"Table\"}]"
motivation: 基于模型的强化学习在多任务序列中容易遗忘世界动力学。
method: 结合合成经验重放和内在探索奖励，维护和重新获取旧任务知识。
result: 在连续任务中有效保持动力学模型，加快后续任务学习。
conclusion: 重放与探索协同是实现持续模型强化的有效路径。
---

## Abstract
We propose DRAGO, a novel approach for continual model-based reinforcement learning aimed at improving the incremental development of world models across a sequence of tasks that differ in their reward functions but not the state space or dynamics. DRAGO comprises two key components: *Synthetic Experience Rehearsal*, which leverages generative models to create synthetic experiences from past tasks, allowing the agent to reinforce previously learned dynamics without storing data, and *Regaining Memories Through Exploration*, which introduces an intrinsic reward mechanism to guide the agent toward revisiting relevant states from prior tasks. Together, these components enable the agent to maintain a comprehensive and continually developing world model, facilitating more effective learning and adaptation across diverse environments. Empirical evaluations demonstrate that DRAGO is able to preserve knowledge across tasks, achieving superior performance in various continual learning scenarios.

---

## 论文详细总结（自动生成）

好的，作为资深学术论文分析助手，我将根据您提供的论文内容，为您生成一份详细、结构化的中文总结。

### 1. 论文的核心问题与整体含义
*   **核心问题**：论文聚焦于**持续模型强化学习**中的**灾难性遗忘**问题。具体而言，当智能体在一个任务序列上顺序学习时（任务只有奖励函数不同，但状态空间和动态转移规律相同），它会倾向于忘记之前任务中学到的环境动力学知识。
*   **研究动机与背景**：
    *   **现实需求**：理想的模型强化学习应能增量式地建立一个通用的世界模型。但在许多现实场景（如机器人、隐私敏感应用）中，智能体由于存储限制、隐私法规等原因，无法保留之前任务的全部原始交互数据。
    *   **问题挑战**：在无法存储过往数据的最严苛设定下，标准的模型强化学习会导致严重的灾难性遗忘，即新知识覆盖旧知识，导致世界模型不完整且泛化能力差。
*   **整体含义**：论文旨在提出一种方法，让智能体在不直接存储过往数据的前提下，能够持续维护和发展一个日益完善的世界模型，从而在后续相关任务上实现快速适应和迁移。

### 2. 论文提出的方法论
论文提出了 **DRAGO** 方法，包含两个核心组件：
*   **合成经验重演**
    *   **核心思想**：借鉴生物体在睡眠中巩固记忆的机制，通过生成式模型“做梦”并“排练”旧任务的合成经验，以强化对旧动态的记忆。
    *   **关键技术细节**：
        1.  **生成式模型**：维护一个持续学习的生成式模型（如VAE），用于捕捉所有先前任务的“状态-动作”对的联合分布 $p_G(s, a; \theta)$。同时，保存一个训练好的旧世界模型 $T_{old}$（一个模型代表所有先前任务，而非每个任务存一个）。
        2.  **数据生成**：从生成模型中采样 $(\hat{s}, \hat{a}) \sim p_G(s,a;\theta)$，然后用冻结的旧世界模型 $T_{old}$ 预测下一个状态 $\hat{s}' = T_{old}(\hat{s}, \hat{a})$。
        3.  **训练目标**：将当前任务的真实数据与生成的合成数据混合，共同训练新的世界模型 $T_{\psi}$，其动力学损失函数为：
            $L_{dyn}(\psi) = E_{(s,a,s') \sim D_i}[\|s' - T_i(s,a;\psi)\|^2] + \lambda E_{(\hat{s},\hat{a}) \sim p_G}[\|T_{old}(\hat{s},\hat{a}) - T_i(\hat{s},\hat{a};\psi)\|^2]$
            其中，生成式模型本身也通过“重演”自己之前生成的样本来对抗遗忘。
*   **通过探索重获记忆**
    *   **核心思想**：合成数据可能不够丰富，且存在模型误差。为了让世界模型更完整、连接起不同任务的经验片段，需要引导智能体主动探索环境，重访旧模型熟悉的区域。
    *   **关键技术细节**：
        *   **内在奖励机制**：设计一个内在奖励信号，引导智能体探索对于旧世界模型 $T_{i-1}$ 预测准确，但对于当前模型 $T_i$ 预测不准确的状态。公式定义为：
            $r_{cont}(s_t, a_t, s_{t+1}) := \sigma(-\log|T_{i-1}(s_t, a_t) - s_{t+1}|) - \alpha \cdot \sigma(-\log|T_i(s_t, a_t) - s_{t+1}|)$
            其中 $\sigma$ 是Sigmoid函数，$\alpha$ 是平衡系数。
        *   **双智能体架构**：维护一个“学习者”（最大化环境奖励）和一个“评论者”（最大化上述内在奖励）。两者共享同一个世界模型，但拥有独立的策略和价值网络，从而将任务求解和探索记忆的目标解耦。

### 3. 实验设计
*   **数据集/场景**：
    1.  **MiniGrid（网格世界）**：一个 27x27 的网格迷宫，包含4个房间。4个训练任务分别设定在一个房间内，目标是在房间内导航。迁移任务则要求智能体在房间之间穿梭。
    2.  **DeepMind Control Suite（深度控制套件）**：在 **Cheetah** 和 **Walker** 两个域的连续控制任务上进行测试。训练任务为不同的运动模式（如跑、跳、后退），迁移任务则要求智能体组合这些运动模式（如从跳跃切换到奔跑，或同时奔跑和跳跃）。
*   **对比方法**：
    *   **从零开始训练**：为每个新任务从头训练一个TDMPC模型。
    *   **持续TDMPC**：用上一任务学到的世界模型初始化下一任务，并直接使用任务奖励进行训练。
    *   **EWC**：在持续TDMPC的基础上，加入弹性权重巩固等正则化方法。
    *   **其他消融实验**：如“基于回放的MBRL”、“伪排练MBRL”等。

### 4. 资源与算力
*   论文在正文和附录中**没有明确提及**所使用的**GPU型号、数量**，以及具体的**训练时长**。

### 5. 实验数量与充分性
*   **实验数量**：实验设计较为丰富，涵盖了：
    *   **3个不同域的任务**（MiniGrid, Cheetah, Walker）。
    *   **12个迁移任务**的性能对比主实验（图5）。
    *   **8个少样本迁移任务**的性能对比（表1）。
    *   **世界模型覆盖率**的定性分析（图4）。
    *   **关键组件的消融实验**（图7），验证了“合成经验重演”和“通过探索重获记忆”各自的作用。
    *   **额外基线对比**，如与“基于回放的MBRL”和“伪排练MBRL”的比较（图6）。
*   **充分性与公平性**：从实验覆盖来看，该研究在两个经典的大类环境（离散状态网格和连续控制）上，通过丰富的横向对比和组件消融，系统性验证了方法的有效性和各模块的贡献。对比方法的选择涵盖了从零开始、无措施持续学习、以及一种经典的正则化方法，比较公平。

### 6. 论文的主要结论与发现
*   **DRAGO能有效缓解灾难性遗忘**：与持续TDMPC相比，DRAGO能更好地保留之前任务学到的动力学知识，构建出更完整的世界模型。
*   **DRAGO的迁移学习能力显著更强**：在绝大多数需要组合过往知识的迁移和少样本迁移任务上，DRAGO的性能和样本效率均优于所有基线方法。
*   **两个组件协同工作且缺一不可**：消融实验证明，“合成经验重演”和“通过探索重获记忆”都能单独提升性能，但两者结合（即完整版DRAGO）能取得最佳效果，表明它们是互补的。

### 7. 优点
*   **问题设定严苛且实用**：聚焦于完全不存储旧数据的最困难场景，符合许多现实应用（如隐私、存储限制）的需求。
*   **方法设计创新且优雅**：将神经科学中的“记忆巩固与重演”概念与内在激励驱动的探索巧妙结合，并用“双智能体”架构解耦目标，思路清晰。
*   **经验验证扎实**：不仅看最终性能，还通过可视化“世界模型覆盖率”直观展示了方法的有效性，证据充分。

### 8. 不足与局限
*   **任务规模与复杂度的局限**：目前测试的任务数量和环境的总体复杂度有限。生成式模型可能随着任务数增多出现“模式崩溃”或记忆“模糊”的问题，论文已指出这一点，但未在当前规模下显现。
*   **生成式模型的遗忘风险**：维持单一生成式模型不断学习也面临自身遗忘的问题，论文虽通过混合真实数据缓解，但未解决根本问题。
*   **假设较强**：方法假设所有任务共享相同的状态、动作空间和动力学，仅奖励函数不同。这限制了其在动力学也发生变化的场景中的直接应用。
*   **算力需求未明**：由于需要维护和训练额外的生成模型、评论者网络，以及进行合成数据生成，其计算开销相比普通方法必然更高，但论文未提供量化分析。

（完）
