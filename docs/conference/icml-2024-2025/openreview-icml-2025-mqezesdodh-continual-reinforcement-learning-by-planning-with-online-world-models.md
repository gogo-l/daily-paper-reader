---
title: Continual Reinforcement Learning by Planning with Online World Models
title_zh: 基于在线世界模型规划的持续强化学习
authors: "Zichen Liu, Guoji Fu, Chao Du, Wee Sun Lee, Min Lin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=mQeZEsdODh"
tags: ["query:continual"]
score: 10.0
evidence: 提出通过在线世界模型规划解决持续强化学习中的灾难性遗忘
tldr: 本文针对持续强化学习中的灾难性遗忘问题，提出通过在线世界模型进行规划的方法。具体学习一个Follow-The-Leader浅层模型在线捕捉世界动态，并利用模型预测控制规划解决任务。该方法理论上免于遗忘，具有O(√(K²D log T))的遗憾界，为持续学习提供了一种无需遗忘的智能体进化方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 814, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 694, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 743, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1738, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1746, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1745, \"height\": 941, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mqezesdodh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 762, \"height\": 513, \"label\": \"Table\"}]"
motivation: 持续强化学习中，智能体在顺序学习多个任务时容易遗忘先前任务，即灾难性遗忘问题。
method: 提出在线世界模型规划方法，学习Follow-The-Leader浅层模型在线捕捉动态，并利用模型预测控制进行规划。
result: 理论证明该方法免于遗忘，具有O(√(K²D log T))的遗憾界，确保性能有界。
conclusion: 该方法为持续强化学习提供了一种无需遗忘的解决方案，推动了智能体在动态环境中的终身学习。
---

## Abstract
Continual reinforcement learning (CRL) refers to a naturalistic setting where an agent needs to endlessly evolve, by trial and error, to solve multiple tasks that are presented sequentially. One of the largest obstacles to CRL is that the agent may forget how to solve previous tasks when learning a new task, known as catastrophic forgetting. In this paper, we propose to address this challenge by planning with online world models. Specifically, we learn a Follow-The-Leader shallow model online to capture the world dynamics, in which we plan using model predictive control to solve a set of tasks specified by any reward functions. The online world model is immune to forgetting by construction with a proven regret bound of $\mathcal{O}(\sqrt{K^2D\log(T)})$ under mild assumptions. The planner searches actions solely based on the latest online model, thus forming a FTL Online Agent (OA) that updates incrementally. To assess OA, we further design Continual Bench, a dedicated environment for CRL, and compare with several strong baselines under the same model-planning algorithmic framework. The empirical results show that OA learns continuously to solve new tasks while not forgetting old skills, outperforming agents built on deep world models with various continual learning techniques.

---

## 论文详细总结（自动生成）

## 核心问题与整体含义

*   **研究动机**：持续强化学习（CRL）要求智能体在顺序呈现的多个任务中不断进化，但灾难性遗忘（在学习新任务时忘记旧技能）是其主要障碍。现有方法多依赖任务特定组件（如独立权重、任务ID），难以构建真正可终身共享且增量更新的智能体。
*   **整体含义**：本文旨在构建一个**在线智能体（Online Agent）**，通过仅维护一个跨任务共享的在线世界模型，并利用规划（而非任务特定策略或价值函数）来处理不同奖励函数，从而实现无遗忘的持续学习。核心思想是：世界动态是统一的、可共享的，而奖励函数可变。

## 方法论

*   **核心思想：规划与在线世界模型**
    *   智能体框架为模型预测控制（MPC）+ 在线学习的世界模型。世界模型捕捉统一的动力学 $P_u$，规划器（CMC）基于该模型和当前奖励函数 $R_\tau$ 搜索动作序列，无需适应不同任务。
    *   世界模型采用**追随领导者（FTL）浅层网络**，支持高效的在线更新，理论可免遗忘。
*   **关键技术细节**：
    *   **稀疏特征编码**：输入状态-动作对 $(s_t, a_t)$ 经随机投影和软分箱得到高维稀疏特征 $\phi(x_t) \in \mathbb{R}^D$，激活节点数 $K \ll D$ 固定，保证恒定开销。
    *   **在线学习规则**：通过求解带岭回归的在线最小二乘问题 $W^{(t)} = \arg\min \|\Phi_{t-1}W - Y_{t-1}\|^2_F + \frac{1}{\lambda}\|W\|^2_F$，得到闭式解。利用特征稀疏性，仅局部更新权重阵：  
        $\widetilde{W}^{(t)}_s = (A^{(t-1)}_{ss} + \frac{1}{\lambda}I)^{-1}(B^{(t-1)}_s - A^{(t-1)}_{ss} W^{(t-1)}_s)$，其中 $A = \Phi^\top \Phi$, $B = \Phi^\top Y$ 为充分统计量。  
        *注：岭正则项 $(1/\lambda)I$ 保证局部更新有唯一解，尤其在初期数据不足时。*
    *   **规划器**：采用改进的交叉熵方法（CEM），加入平移初始化、有色噪声和记忆机制，提升采样效率。
*   **理论保证**：
    *   在温和假设下（特征映射稳定、输入输出有界、激活节点数 $K$ 合适），证明了稀疏在线更新的**遗憾界（Regret Bound）为 $\mathcal{O}(\sqrt{K^2 D \log T})$**，表明模型无遗憾，即性能接近离线最优解。

## 实验设计

*   **评估环境**：
    *   专门设计了 **Continual Bench** 环境，基于 Meta-World 任务原语，但将不同任务**空间排列**（以圆环放置）而非时序拼接，从而保证**统一的世界动力学**，避免了物理冲突（如开门与开抽屉轨迹矛盾）。包含 6 个任务：`pick-place`, `button-press`, `door-open`, `peg-unplug`, `window-close`, `faucet-close`。
    *   状态空间 26 维，动作空间 4 维，任务序列按空间最远距离排列以增大分布漂移。
*   **评价指标**：
    *   **平均成功率（AP）**：在全局时间步 $w$ 上，智能体在所有历史任务上的平均成功率，衡量离线稳定性（防遗忘）。
    *   **遗憾（Reg）**：在线智能体与理论上一直是完美的智能体之间性能曲线的归一化面积差。
*   **对比方法**：
    *   **模型基（Model‑based）**：均采用相同的 MPC+CEM 规划框架，仅世界模型学习方式不同。
        *   `Fine‑tuning`：仅用当前任务数据微调深度模型。
        *   `SI`：引入突触智能（Synaptic Intelligence）正则化。
        *   `Coreset`：维护固定大小的经验回放池（水库采样）。
        *   `Perfect Memory`：使用所有历史数据训练的深度模型（上界参考）。
    *   **模型无关（Model‑free）**：基于 SAC 算法加上 EWC、PackNet、Coreset 等持续学习技术，作为另一维度对比。

## 资源与算力

*   **实验硬件**：每项实验使用 1 张 **A100 GPU** 和 **16 个 CPU**。
*   **训练时长**：单次实验训练约 **10 到 15 小时**（共 600 个 episode 预算）。所有实验在内部集群上运行。

## 实验数量与充分性

*   **主要对比实验**：
    *   模型基方法在 Continual Bench 上的 6 任务连续学习曲线（7 次随机种子）。
    *   模型基与模型无关方法的最终 AP 和 Reg 对比表。
*   **消融与分析**：
    *   在线世界模型**稀疏性**（不同 bin 数 $\Lambda=5,7,9,11$）对性能的影响。
    *   不同**回放缓冲区大小**下 OA 与 Coreset/Perfect Memory 的性能对比。
    *   OA **模型利用率**（已激活权重占比）随任务增长的曲线。
    *   模型**预测误差**（MSE）随任务的演变曲线（附录）。
*   **充分性与公平性**：实验覆盖了主流持续学习范式（正则化、重放、架构），在统一规划框架下对比，排除了规划器差异干扰；多种消融验证了方法关键设计。实验设计客观，重复数充分，可作为 CRL 的公平基准。

## 主要结论与发现

*   **无遗忘在线学习**：FTL 在线世界模型（OA）在顺序学习 6 个任务中，始终维持对旧任务的高成功率，性能与`Perfect Memory`持平，而免去了不断增长的存储和重训开销。
*   **快速适应**：所有模型基方法（包括基线）在新任务学习期内均能有效提升，显示出基于统一动态规划的快速适应性。
*   **基线问题**：深度模型+微调会立即遗忘；`SI`缓和有限；`Coreset`在回放比例下降后遗忘加剧。模型无关方法普遍遗憾更高，适应性差。
*   **理论与实证一致**：提出的稀疏在线更新可视为“实时求解的最小二乘”，理论上 no‑regret，实践上也确实避免了遗忘。

## 优点

*   **方法创新**：首次将 FTL 浅层在线学习与 MPC 规划结合，作为无遗忘持续强化学习的解决方案，理论扎实。
*   **统一框架**：仅学习统一的动态模型，无需任务 ID、边界信息或额外记忆，符合“在线智能体”的自然设定。
*   **计算高效**：模型在线更新复杂度恒定（与 $K$、$D$ 相关，而非数据总量），远优于重训全部历史数据的 deep agent。
*   **基准贡献**：提出了 Continual Bench，纠正了现有 CRL 基准中动力学冲突问题，可同时评估遗忘与传递。
*   **实验对比充分**：在同一模型‑规划框架下对比多个持续学习技巧，给出了清晰的性能归因。

## 不足与局限

*   **输入模态限制**：当前在线世界模型仅适用于**中等维度的状态向量**，无法直接处理高维图像观测，也**不捕捉环境不确定性**（即确定性预测）。
*   **任务切换依赖 episode 边界**：Continual Bench 是分幕式（episodic）环境，任务切换在 episode 间显式发生，未涉及无重置（reset‑free）或更平滑的任务转换。
*   **探索能力缺失**：规划器（CEM）基于当前模型，未包含显式探索机制，可能在复杂环境中探索不足。
*   **稀疏性依赖假设**：理论遗憾界依赖于对 $K$、稳定性和输入有界等假设，实际中需通过超参（如 $\Lambda$）调优。
*   **任务选取有限**：实验仅包含 6 个桌面机械臂操作任务，在更丰富或更大尺度的环境中的泛化能力有待验证。

（完）
