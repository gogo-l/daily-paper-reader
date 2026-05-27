---
title: Knowledge Retention in Continual Model-Based Reinforcement Learning
title_zh: 持续基于模型的强化学习中的知识保留
authors: "Haotian Fu, Yixiang Sun, Michael Littman, George Konidaris"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DiqeZY27XK"
tags: ["query:continual"]
score: 9.0
evidence: 提出持续模型强化学习中知识保留方法以防止遗忘
tldr: 针对基于模型强化学习在连续任务中世界模型遗忘的问题，提出DRAGO方法，结合合成经验重演与内在奖励驱动的探索，使智能体在不存储数据的情况下强化过往动态，并主动回访相关状态，持续构建世界模型。实验显示有效缓解遗忘，为持续模型强化学习提供了实用方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1379, \"height\": 612, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1350, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 777, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1516, \"height\": 922, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1611, \"height\": 910, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1719, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1529, \"height\": 306, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1734, \"height\": 340, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-diqezy27xk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1645, \"height\": 307, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1449, \"height\": 389, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 1018, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 1348, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1779, \"height\": 580, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1782, \"height\": 478, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1096, \"height\": 1145, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1075, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1457, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1322, \"height\": 167, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 963, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-diqezy27xk/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 839, \"height\": 203, \"label\": \"Table\"}]"
motivation: 基于模型的强化学习在跨任务时出现世界模型遗忘。
method: 利用生成模型合成过往经验，并引入内在奖励引导状态回访。
result: 在多个连续任务中实现了世界模型的持续发展且遗忘大幅减少。
conclusion: DRAGO为持续模型强化学习提供了有效的知识保留机制。
---

## Abstract
We propose DRAGO, a novel approach for continual model-based reinforcement learning aimed at improving the incremental development of world models across a sequence of tasks that differ in their reward functions but not the state space or dynamics. DRAGO comprises two key components: *Synthetic Experience Rehearsal*, which leverages generative models to create synthetic experiences from past tasks, allowing the agent to reinforce previously learned dynamics without storing data, and *Regaining Memories Through Exploration*, which introduces an intrinsic reward mechanism to guide the agent toward revisiting relevant states from prior tasks. Together, these components enable the agent to maintain a comprehensive and continually developing world model, facilitating more effective learning and adaptation across diverse environments. Empirical evaluations demonstrate that DRAGO is able to preserve knowledge across tasks, achieving superior performance in various continual learning scenarios.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究背景**：基于模型的强化学习（MBRL）通过学习世界模型来预测环境动态，但在多任务序列中会出现灾难性遗忘——智能体学习新任务时会遗忘先前学到的动态，导致世界模型碎片化。
- **核心问题**：在无法存储过往任务原始交互数据的约束下（存储、隐私、设备限制），如何让世界模型持续整合新知识，避免遗忘旧任务中的动态，从而逐步构建一个更完整的通用世界模型？
- **整体含义**：提出一种无需重放真实数据、仅依靠生成模型和内部探索的持续MBRL方法，使世界模型在任务序列中稳定积累知识，提升对新任务的迁移适应能力。

### 2. 方法论
DRAGO由两个核心组件和一个整体算法框架构成：

#### 2.1 合成经验重演（Synthetic Experience Rehearsal）
- **动机**：模拟生物记忆巩固，在不访问旧数据的情况下，通过生成合成经验来强化过往动态。
- **技术细节**：
  - 持续训练一个变分自编码器（VAE）作为生成模型 \(G\)，学习过往所有任务的状态-动作联合分布。
  - 保存一份旧世界模型 \(T_{\text{old}}\) 的冻结拷贝。
  - 生成合成状态-动作对 \((\hat{s}, \hat{a}) \sim p_G(s, a)\)，然后用 \(T_{\text{old}}\) 预测下一状态 \(\hat{s}'\)。
  - 将合成数据与当前任务数据共同训练动态模型，损失函数包括当前数据预测误差和合成数据蒸馏损失（公式5）。
- **生成模型的持续学习**：用前一阶段的VAE生成伪数据，与当前任务真实数据混合训练新VAE，防止VAE自身遗忘。

#### 2.2 通过探索重新获得记忆（Regaining Memories Through Exploration）
- **动机**：合成数据可能无法覆盖真实经验，并且缺少不同任务区域之间的实际连接。通过内在奖励鼓励智能体重新访问旧模型熟悉的状态，弥补片段化的世界模型。
- **内在奖励设计**（公式7）：
  \[
  r_{\text{cont}}(s_t, a_t, s_{t+1}) = \sigma(-\log|T_{i-1}(s_t, a_t) - s_{t+1}|) - \alpha \cdot \sigma(-\log|T_i(s_t, a_t) - s_{t+1}|)
  \]
  - 第一项奖励旧世界模型 \(T_{i-1}\) 预测准确的状态，引导重新访问旧任务相关状态。
  - 第二项惩罚当前模型 \(T_i\) 已预测准确的状态，鼓励探索新区域并发现连接。
  - \(\alpha\) 加权系数平衡两项。
- **实现方式**：引入一个独立的“审阅者”（reviewer）策略，专门最大化累积内在奖励，与任务求解的“学习者”（learner）共享同一个动态模型但拥有独立的奖励、价值网络和策略。

#### 2.3 整体算法流程（基于TDMPC）
- 训练时同时更新学习者与审阅者的策略、价值网络、奖励模型，以及共享的世界模型和VAE。
- 推理时采用模型预测路径积分（MPPI）规划，使用学到的价值函数进行轨迹评估。
- 关键设计：审阅者和学习者分离，避免内在奖励干扰原始任务学习；动态模型也从审阅者的经验中学习，增强状态覆盖。

### 3. 实验设计

#### 数据集/场景
- **MiniGrid**：27×27网格世界，四个任务分别在不同房间，障碍物各异，通过中心门连接；迁移任务要求跨房间导航（如Room1到Room3）。
- **DeepMind Control Suite**：
  - **Cheetah**：序列任务（run → jump → backward），迁移任务包括从跳跃状态转为奔跑、跳跃与奔跑同时进行等。
  - **Walker**：序列任务（run → walk → stand → backward），迁移任务类似（如walk2run、back2run）。

#### 基准对比方法
- 从头训练TDMPC（Scratch）。
- 朴素持续TDMPC（Continual TDMPC）：加载上一任务模型但无防遗忘机制。
- 弹性权重巩固（EWC）：经典正则化持续学习方法。
- 额外基线：重放有限存储数据的Replay-based MBRL、使用预训练VAE但无持续训练的Pseudo-rehearsal MBRL、持续TDMPC+好奇心探索。

#### 评估指标
- 在迁移任务上的平均回报（训练曲线）。
- 少样本迁移性能：仅训练20个回合后的累积奖励。
- 定性分析：世界模型在整个网格中的预测准确性热力图。

### 4. 资源与算力
论文正文和附录中**未明确提及**使用的GPU型号、数量或具体训练时长。仅提到计算资源来自布朗大学计算与可视化中心。

### 5. 实验数量与充分性
- **实验组数**：
  - 三个域（MiniGrid、Cheetah、Walker），每个域含多种训练任务序列和若干迁移测试任务。
  - 总体性能对比（图5）涵盖12个迁移任务（每域4个）。
  - 消融实验（图7）针对4个迁移任务。
  - 少样本迁移表1在8个任务上比较。
  - 额外分析：与重放基线对比（图6）、世界模型预测热力图（图4）、持续训练任务性能（表3）、复习者内在奖励集成方式消融（表5）、基于PETS的方法验证（表6）、规划参数影响、合成重演频率影响等。
- **充分性与公平性**：
  - 对比基线多样且合理，涵盖普通持续学习、正则化、重放基线等。
  - 实验设计重复多次（均值和标准差），任务设计确保不同任务覆盖状态空间的有限且部分重叠部分，能有效检验遗忘与迁移。
  - 消融实验验证了两个组件的贡献。
  - 局限性：任务规模相对较小（最多4个任务），未测试更长的任务序列或高维视觉输入，生成模型可能存在的模式坍塌未体现。

### 6. 主要结论与发现
- DRAGO在所有三个域中均显著优于朴素继续训练、EWC和从头训练，尤其在新任务迁移上实现更快适应和更高最终性能。
- 合成重演有效抑制世界模型遗忘，通过生成旧任务分布数据蒸馏旧动态；内在奖励驱动探索帮助模型连接不同任务区域，构建更完整的世界模型。
- 两组件互补：单独使用任一组件都能改善遗忘，但组合后性能最佳。
- 在少样本迁移场景下，DRAGO在8个任务中的6个达到最优，且在其余任务上保持竞争力。
- 持续训练过程中，DRAGO不会损害当前任务的学习性能（表3）。

### 7. 优点
- **无需存储原始数据**：仅保留生成模型和旧动态模型，存储成本低，适用隐私和存储受限场景。
- **双组件互补设计**：合成重演保障旧知识，内在探索建立连接，两者协同提升世界模型完整性。
- **模型无关性**：可与不同MBRL基座（如TDMPC、PETS）集成，架构灵活。
- **策略分离**：独立审阅者机制避免内在奖励干扰主任务学习。
- **定性评估直观**：通过热力图清晰展示世界模型覆盖面的保持情况。

### 8. 不足与局限
- **任务序列长度有限**：实验仅涉及3-4个任务，当任务数量大幅增加时，生成模型可能出现模式坍塌或记忆“模糊”问题，该现象未在实验中出现和分析。
- **生成模型持续学习压力**：仅依靠VAE和前一模型采样来防止遗忘，缺乏更强力的持续生成模型策略，可能限制扩展性。
- **环境复杂性**：当前测试域（MiniGrid、低维DMControl）任务间的动态分歧较小，未考察更复杂视觉输入或更大状态空间。
- **内在奖励超参敏感**：系数α和审阅者分离机制的效果依赖调参，迁移到新域时可能需要额外调整。
- **与重放基线的比较不够深入**：虽然展示了有限存储重放的对比，但未系统分析不同存储预算下的性能差异。

---
（完）
