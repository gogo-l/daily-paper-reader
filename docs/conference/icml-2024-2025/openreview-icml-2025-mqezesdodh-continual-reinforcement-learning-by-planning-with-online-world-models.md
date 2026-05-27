---
title: Continual Reinforcement Learning by Planning with Online World Models
title_zh: 通过在线世界模型规划实现持续强化学习
authors: "Zichen Liu, Guoji Fu, Chao Du, Wee Sun Lee, Min Lin"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=mQeZEsdODh"
tags: ["query:continual"]
score: 9.0
evidence: 使用在线世界模型解决持续强化学习中的灾难性遗忘
tldr: 针对持续强化学习中顺序任务学习导致的灾难性遗忘问题，本文提出利用在线世界模型进行规划。方法通过在线学习一个跟随领导者浅层模型捕捉世界动态，并使用模型预测控制执行任意奖励函数指定的任务。在线世界模型在构造上无需担心遗忘，并提供了O(√(K^2 D log T))的遗憾界保证。实验表明该方法能有效实现持续学习而不丢失先前技能，为智能体在动态环境中的终身学习提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 814, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 694, \"height\": 263, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 743, \"height\": 488, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1738, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1746, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-mqezesdodh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1745, \"height\": 941, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-mqezesdodh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 762, \"height\": 513, \"label\": \"Table\"}]"
motivation: 持续强化学习中智能体在顺序学习多个任务时会灾难性遗忘已学技能。
method: 学习一个在线世界模型，利用模型预测控制在其中规划，使模型天然免疫遗忘。
result: 获得理论上的遗憾界保证，且实验表明可有效解决多个顺序任务。
conclusion: 该方法为持续强化学习提供了一种构造性免遗忘的解决方案，具有理论保障。
---

## Abstract
Continual reinforcement learning (CRL) refers to a naturalistic setting where an agent needs to endlessly evolve, by trial and error, to solve multiple tasks that are presented sequentially. One of the largest obstacles to CRL is that the agent may forget how to solve previous tasks when learning a new task, known as catastrophic forgetting. In this paper, we propose to address this challenge by planning with online world models. Specifically, we learn a Follow-The-Leader shallow model online to capture the world dynamics, in which we plan using model predictive control to solve a set of tasks specified by any reward functions. The online world model is immune to forgetting by construction with a proven regret bound of $\mathcal{O}(\sqrt{K^2D\log(T)})$ under mild assumptions. The planner searches actions solely based on the latest online model, thus forming a FTL Online Agent (OA) that updates incrementally. To assess OA, we further design Continual Bench, a dedicated environment for CRL, and compare with several strong baselines under the same model-planning algorithmic framework. The empirical results show that OA learns continuously to solve new tasks while not forgetting old skills, outperforming agents built on deep world models with various continual learning techniques.

---

## 论文详细总结（自动生成）

好的，这是对给定论文的结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：本文旨在解决**持续强化学习** 中一个核心挑战——**灾难性遗忘**。具体而言，当一个智能体在持续变化的环境中顺序学习多个任务时，在学习新任务后往往会完全忘记之前已掌握的技能。这阻碍了构建能够终身自主学习进化的智能体。
*   **整体含义**：本文提出了一种根本性的解决方案，旨在构建一个**在线智能体**。该智能体的关键学习组件在整个生命周期中是共享且增量更新的，而不依赖于任务ID或特定于任务的结构。其核心思想是：如果将“学习可共享的世界动态模型”与“基于模型的规划”分离，那么只要世界模型本身不会遗忘，整个智能体的能力就不会退化。

### 2. 论文提出的方法论

*   **核心思想**：论文的核心思路是利用**在线世界模型进行规划**。作者指出，统一的“世界动态”是唯一一个在所有任务中都可共享且需要持续学习的组件。一个能够免遗忘地在线学习的世界模型，配合一个无训练参数的规划器，就能构建一个天然的持续学习智能体。
*   **关键技术细节**：
    *   **在线世界模型学习**：
        *   采用**追随领导者** 策略的浅层但宽的网络，该网络结构为 \(y = W \sigma(P x)\)，其中 \(P\) 是固定随机投影矩阵，\(W\) 是线性可学习权重。
        *   利用高维稀疏特征编码器 \(\phi(x)\) 处理状态-动作对 \(x_t\)，将下一状态的差异 \(y_t\) 作为学习目标。
        *   模型权重 \(W^{(t)}\) 通过带正则化项的**增量最小二乘法**求解，这等价于对迄今为止所有观察到数据的闭式解。具体更新规则如Eq. (4)所示，它仅在每次新数据到达时，对激活的特征权重进行局部高效更新，计算复杂度恒定。
        *   理论上证明了该稀疏在线模型学习是**无遗憾的**，其遗憾界为 \(\mathcal{O}(K^2 D \log(T))\)，保证了它能够收敛到离线最优解，从根本上免除了遗忘风险。
    *   **基于规划的决策**：
        *   智能体不学习策略或价值函数，而是基于最新学到的在线世界模型，使用**交叉熵方法** 进行**模型预测控制**来规划动作序列。
        *   为了提高规划效率，采用了**偏移初始化**、**有色噪声**和**记忆**等改进技术。

### 3. 实验设计

*   **基准与环境**：
    *   作者指出了现有CRL基准（如Continual-World）存在物理状态空间不一致、导致世界动态本身冲突的缺陷，因此专门设计了一个新的基准环境——**Continual Bench**。
    *   该环境基于Meta-World构建，但将6个不同难度的任务（如拔插销、关门、按按钮等）**在空间上排列**在一个统一且一致的物理世界中，确保存在一个共享的世界动态，从而能够公平地评估遗忘和迁移。
    *   任务以固定顺序呈现，相邻任务在空间上尽可能远离，以加剧分布漂移和遗忘。
*   **对比方法**：
    *   **主要对比对象**：在**基于模型的规划框架**下，将提出的在线智能体与使用深度世界模型的智能体进行比较。
    *   **基线方法**：为深度世界模型应用多种经典的持续学习技术，包括：
        *   **微调**：仅用当前任务数据训练。
        *   **突触智能**：基于正则化的方法。
        *   **核心集**：基于回放的方法。
        *   **完美记忆**：保留所有历史数据进行训练（性能上界）。
    *   **额外对比**：还在**模型无关** 框架下对比了EWC、PackNet、核心集等方法。
*   **评估指标**：
    *   **平均性能**：在任意时间步，计算智能体在所有已见任务上的平均成功率。
    *   **遗憾值**：衡量智能体的在线性能曲线与一个始终成功的“预言机”智能体之间的归一化面积差，数值越低越好。

### 4. 资源与算力

*   **算力情况**：论文明确提到了实验所需的计算资源。
    *   **硬件**：每个实验任务消耗一块**A100 GPU**和16个CPU。
    *   **训练时长**：一个完整实验的训练时间大约在**10小时到15小时**之间，总预算为600个Episode。
*   **软件**：使用MBRL Library (Meta) 进行开发。

### 5. 实验数量与充分性

*   **实验数量**：实验覆盖了多个维度，总计进行了多组实验。
    *   **主要性能对比**：在Continual Bench上比较了1种本文方法和4种深度模型基线方法，所有结果都基于7个不同随机种子的平均值和标准差。
    *   **跨框架对比**：在模型无关智能体上，比较了1种微调基线和4种CL基线的最终性能。
    *   **消融实验**：分析了在线智能体的**模型利用率**变化曲线、不同**稀疏度** 对性能的影响（ \(\Lambda = 5, 7, 9, 11\)）、以及对不同**缓冲大小**的敏感性。
    *   **模型误差分析**：额外展示了不同智能体在所有任务上的世界模型均方误差曲线。
*   **充分性与公平性**：
    *   实验设计较为充分，从性能、遗忘、模型准确度、参数影响等多个角度进行了评估。
    *   公平性较高：所有基于模型的方法均共享相同的规划器框架和超参数，确保性能差异主要来源于世界模型的学习方式。对比了不同CL范式（正则化、回放、架构）的代表性方法。提供了一个统一且具有挑战性的新基准。

### 6. 论文的主要结论与发现

*   **免遗忘能力**：所提出的在线智能体展现出了切实的**免遗忘**能力。在学习了新任务后，它在先前任务上的成功率几乎没有下降，性能与需要存储所有历史数据的“完美记忆”基线相当，甚至在某些方面更优。
*   **性能优势**：在线智能体在所有任务上的平均性能和最终性能均显著优于其他深度模型基线，其遗憾值在所有方法中最低，表明其在线学习过程更高效。
*   **模型可塑性**：所有基于模型的智能体在接触新任务时都能快速学习并达到高性能，展现了通过规划复用世界知识的能力。
*   **效率**：在线智能体通过恒定开销的增量更新实现了与“完美记忆”（计算成本随时间无限增长）相近的性能，展示了其在终身学习场景下的巨大潜力。
*   **理论支撑**：首次为基于FTL的稀疏在线世界模型学习提供了遗憾界理论证明，揭示了正则化项对于保证模型收敛的必要性。

### 7. 优点

*   **方法创新性强**：将CRL问题巧妙地转化为一个在线世界模型学习问题，通过构造实现免遗忘，思路优雅且根本。
*   **理论与实验结合紧密**：不仅给出了严谨的遗憾界证明，还在专门设计的新基准上进行了充分的实验验证，结果相互印证。
*   **基准设计合理**：提出的Continual Bench直面了现有基准的根本缺陷（状态空间不一致），为CRL领域提供了一个更科学、更具挑战性的评估平台。
*   **计算效率高**：在线更新的计算开销恒定，与依赖回放或存储所有数据的传统方法相比，在终身学习场景下的可扩展性更强。

### 8. 不足与局限

*   **环境局限性**：目前的在线世界模型仅能处理**中等维度的状态输入**，且是**确定性**的，无法捕捉世界的内在随机性和不确定性。
*   **探索不足**：当前的模型规划框架中**没有显式的探索机制**，智能体的探索可能完全依赖于CEM规划器中的噪声，在处理需要深度探索的任务时可能存在不足。
*   **任务切换设定**：Continual Bench环境仅限于**回合制**且带有**明确任务切换**的设定。这主要是为了避免非遍历性MDP中不可逆状态带来的挑战。如何在无重置环境中无缝切换任务是一个未解决的问题。
*   **特征编码依赖**：模型性能在一定程度上依赖于底层高维稀疏特征编码（Losse）的超参数选择（如稀疏度 \(\Lambda\)），虽然论文进行了消融研究，但在更复杂领域可能需要仔细调参。

（完）
