---
title: Meta-Reinforcement Learning Robust to Distributional Shift Via Performing Lifelong In-Context Learning
title_zh: 通过执行终身上下文学习实现分布偏移下鲁棒的元强化学习
authors: "Tengye Xu, Zihao Li, Qinyuan Ren"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=laIOUtstMs"
tags: ["query:continual"]
score: 8.0
evidence: 终身上下文学习实现分布偏移鲁棒的元强化学习
tldr: 元强化学习方法泛化性常局限于训练任务分布，该工作提出后验采样贝叶斯终身上下文强化学习（PSBL），元训练Transformer网络直接进行最优策略的预测后验分布摊销推断，训练后冻结参数，智能体在线通过采样动作探索并逐步降低不确定性，无需对每个新任务微调，在任务分布偏移下展现鲁棒适应，体现了终身学习和进化能力。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-laioutstms/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1745, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-laioutstms/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1766, \"height\": 1058, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-laioutstms/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1744, \"height\": 1057, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-laioutstms/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 738, \"height\": 606, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-laioutstms/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1794, \"height\": 541, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-laioutstms/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 1369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-laioutstms/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 872, \"height\": 685, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-laioutstms/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 675, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-laioutstms/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1727, \"height\": 639, \"label\": \"Table\"}]"
motivation: 元强化学习对任务分布偏移敏感，泛化能力受限。
method: 元训练Transformer进行最优策略后验的摊销推断。
result: 冻结参数在线探索适应新任务，无需微调。
conclusion: 终身上下文学习赋予代理持续的分布适应与进化能力。
---

## Abstract
A key challenge in Meta-Reinforcement Learning (meta-RL) is the task distribution shift, since the generalization ability of most current meta-RL methods is limited to tasks sampled from the training distribution. In this paper, we propose Posterior Sampling Bayesian Lifelong In-Context Reinforcement Learning (PSBL), which is robust to task distribution shift. PSBL meta-trains a variant of transformer to directly perform amortized inference about the Predictive Posterior Distribution (PPD) of the optimal policy. Once trained, the network can infer the PPD online with frozen parameters. The agent then samples actions from the approximate PPD to perform online exploration, which progressively reduces uncertainty and enhances performance in the interaction with the environment. This property is known as in-context learning. Experimental results demonstrate that PSBL significantly outperforms standard Meta RL methods both in tasks with sparse rewards and dense rewards when the test task distribution is strictly shifted from the training distribution.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机**：元强化学习（meta‑RL）的目标是让智能体快速适应新任务，但现有方法在测试任务分布与训练分布发生**偏移（Out‑of‑Distribution, OOD）**时泛化能力严重下降，往往退化为从零开始的普通RL，需要大量在线交互，难以实际部署。
- **整体含义**：本文提出一种**对任务分布偏移鲁棒**的元强化学习方法，通过让预训练的Transformer网络在冻结参数下持续进行**终身上下文学习（Lifelong In‑context Learning）**，逐步降低动作不确定性、优化策略，从而在分布外任务上依然能持续提升性能。

### 2. 方法论
- **核心思想**：利用Transformer直接进行**最优策略的预测后验分布（Predictive Posterior Distribution, PPD）的摊销推断**。训练完成后冻结网络参数，智能体在交互中从近似的PPD中采样动作进行在线探索，逐步降低不确定性——即“终身上下文学习”。
- **关键技术细节**：
  - **LILTrans网络**：一种基于Transformer编码器的变体，带有时间嵌入网络和两个前馈网络，输出近似PPD的下一状态、奖励和动作分布。
  - **后验采样框架**：最小化PPD与网络输出之间的交叉熵损失，包括监督损失 \(\ell_s\)（预测下一观察和奖励）和最优策略损失 \(\ell_a\)。
  - **获取贝叶斯最优策略信号**：由于真实最优策略未知，使用**模拟退火**与Q函数近似最优策略：\(P(a_{t+1}|\tau_t) \propto \exp(\frac{1}{\alpha}Q(a_{t+1},\tau_t))\)，并以此计算KL散度损失。
  - **终身学习支持**：引入**动态窗口**（仅保留最近 \(b\) 个episode的交互历史）和**时间嵌入**，使训练时固定长度的上下文能够在测试时无限延伸，实现跨episode的持续改进。
  - **总训练目标**：\(\mathcal{L} = \lambda_s\ell_s + \lambda_a\ell_a + \lambda_c\ell_c\)，其中 \(\ell_c\) 是基于TD误差的评论家损失。
- **算法流程**（文字概括）：
  1. 从任务分布中采样MDP，将交互序列存入重播缓冲区。
  2. 根据动态窗口截取最近的交互序列，输入LILTrans。
  3. 计算监督损失、最优策略损失和评论家损失并更新网络参数。
  4. 测试时，冻结网络，动作采样自网络输出的近似PPD，交互序列持续滚动，动态窗口向前推进，实现终身改进。

### 3. 实验设计
- **环境与数据集**：
  - **离散导航任务**：Gridworld（5×5训练，6×6/7×7/8×8测试）和Dark‑Key‑to‑Door（9×9训练，10×10/11×11/12×12测试），均使用稀疏奖励。
  - **连续控制任务**：HalfCheetah‑Vel（目标速度0‑3 m/s训练，3‑3.5/3.5‑4/4‑4.5测试）和Walker‑2D‑Param（物理参数随机缩放因子3训练，4/5/6测试），均使用密集奖励。
- **Benchmark方法**：AMAGO、VariBAD、RL²、PEARL（后者仅用于连续任务）。所有方法均从头训练，测试时严格使用与训练分布不同的OOD任务。
- **评估方式**：每组实验采用64个并行随机环境、3个随机种子，记录平均回报随episode的变化。

### 4. 资源与算力
- **文中未提及**：论文未明确说明使用的GPU型号、数量、训练时长等计算资源细节。

### 5. 实验数量与充分性
- **实验组数**：在**4个环境**（2离散+2连续）上进行了与4种基准方法的对比实验，每个环境包含1个ID和2~3个OOD难度级别。另外进行了1组消融实验（探究不同动态窗口/记忆长度的影响）。
- **充分性与公平性**：实验覆盖了离散/连续、稀疏/密集奖励场景；对比了当前主流的上下文与任务推断类meta‑RL方法；每次评估采用多随机种子和多并行环境，结果以均值和学习曲线呈现，消融实验分析了关键组件的作用。整体实验设计较为客观、公平，能够支撑主要结论。

### 6. 主要结论与发现
- PSBL能够在**冻结参数**下实现**终身上下文学习**：在稀疏奖励任务中性能跨episode逐步提升，在密集奖励任务中可在1‑2个episode内快速收敛。
- 在**严格OOD任务**上，PSBL显著优于所有对比方法，且随着分布偏移距离增大，优势愈发明显。
- 动态窗口与较长的记忆/训练horizon有助于终身学习和性能提升。

### 7. 优点
- **分布偏移鲁棒性**：冻结参数直接适应OOD任务，无需在线梯度更新，避免了传统方法退化为从零开始RL的问题。
- **终身学习能力**：通过动态窗口与时间嵌入，实现跨episode的持续策略改进，突破了传统meta‑RL仅在训练horizon内适应的限制。
- **理论上合理的结合**：将元学习、贝叶斯推断和上下文学习融合，并给出了损失函数与PPD近似的理论关联。
- **实验全面性**：在多种性质和奖励类型的任务上验证，并与多个强基线对比。

### 8. 不足与局限
- **算力需求未知**：未报告训练计算资源消耗，难以评估实际部署成本。
- **任务规模与多样性有限**：实验仅在相对简单的网格世界和MuJoCo控制任务上进行，未涉及更复杂的视觉输入或更长的horizon任务，性能是否能扩展尚不明朗。
- **超参数敏感性**：方法包含多个损失权重、窗口长度、训练‑测试horizon等超参数，消融实验仅涉及窗口相关设定，其他参数的影响未充分分析。
- **与最新方法的对比**：未比较一些较新的off‑policy meta‑RL或基于模型的meta‑RL方法（如一些2023‑2024的高效方法），对比可能不够全面。
- **理论保证限制**：PPD近似和终身学习的理论上界未深入讨论，实际收敛性可能受环境动态影响。

（完）
