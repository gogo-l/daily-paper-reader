---
title: Temporal-Difference Variational Continual Learning
title_zh: 时间差分变分持续学习
authors: "Luckeciano Carvalho Melo, Alessandro Abate, Yarin Gal"
date: 2025-01-23
pdf: "https://openreview.net/pdf?id=6Uh73Wl8Je"
tags: ["query:continual"]
score: 9.0
evidence: 提出时间差分变分方法以减轻持续学习中的灾难性遗忘
tldr: 针对贝叶斯变分持续学习中递归更新目标导致近似误差累积、加剧灾难性遗忘的问题，提出时间差分变分推断方法，以时序差分目标替代递归约束，减少误差传播。在多个基准上取得更优的记忆稳定性与任务性能，为贝叶斯持续学习提供了有效改进。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1417, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1787, \"height\": 955, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1771, \"height\": 696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1777, \"height\": 812, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1775, \"height\": 872, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1883, \"height\": 900, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1875, \"height\": 956, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1843, \"height\": 965, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1779, \"height\": 863, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1793, \"height\": 869, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1487, \"height\": 791, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1666, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1608, \"height\": 794, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1784, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1757, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1682, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1488, \"height\": 790, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1428, \"height\": 1566, \"label\": \"Table\"}]"
motivation: 现有变分持续学习因递归更新产生累积近似误差，导致遗忘。
method: 引入时间差分学习目标替代递归约束，减少误差累积。
result: 在多个标准基准上取得了更优的记忆保持与任务性能。
conclusion: 提出的方法显著提升了贝叶斯持续学习的稳定性。
---

## Abstract
Machine Learning models in real-world applications must continuously learn new tasks to adapt to shifts in the data-generating distribution. Yet, for Continual Learning (CL), models often struggle to balance learning new tasks (plasticity) with retaining previous knowledge (memory stability). Consequently, they are susceptible to Catastrophic Forgetting, which degrades performance and undermines the reliability of deployed systems. In the Bayesian CL literature, variational methods tackle this challenge by employing a learning objective that recursively updates the posterior distribution while constraining it to stay close to its previous estimate. Nonetheless, we argue that these methods may be ineffective due to compounding approximation errors over successive recursions. To mitigate this, we propose new learning objectives that integrate the regularization effects of multiple previous posterior estimations, preventing individual errors from dominating future posterior updates and compounding over time. We reveal insightful connections between these objectives and Temporal-Difference methods, a popular learning mechanism in Reinforcement Learning and Neuroscience. Experiments on challenging CL benchmarks show that our approach effectively mitigates Catastrophic Forgetting, outperforming strong Variational CL methods.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **核心问题**：在持续学习（Continual Learning, CL）中，模型需在依次到达的任务流上不断学习新知识（可塑性）同时保留旧知识（记忆稳定性），否则会出现灾难性遗忘。贝叶斯持续学习方法（如变分持续学习 VCL）通过递归更新后验逼近并约束其不要远离上一时刻的后验，但这种方法因每一步近似误差会随递归累积，导致较差的长期记忆保持。
- **整体含义**：本文提出一种新的变分目标族——时间差分变分持续学习（TD-VCL），将正则化约束分散到多个历史后验估计上，有效稀释单次近似误差的影响，从而减缓遗忘，并揭示其与强化学习中的时序差分（TD）方法的内在联系。

### 2. 论文提出的方法论

- **核心思想**：将 VCL 的递归目标等价地重写为多个过去后验估计的加权组合，使当前后验的更新接受来自多个历史估计的正则化，而不只依赖最近一个。
- **关键技术细节**：
  - **n-Step KL 正则化目标**：将 VCL 目标等价表示为前 \(n\) 步后验估计的加权对数似然加 KL 散度组合（式 4），每个历史估计仅贡献 \(1/n\) 的 KL 正则化权重，稀释误差影响。
  - **TD(\(\lambda\))-VCL 目标**：在 n-Step 基础上引入指数衰减权重 \(\lambda\)（式 5），使得越近期的估计贡献越大，形成类似强化学习中 \(\lambda\)-回报的折扣求和结构，构成广义谱系（\(\lambda=0\) 退化为标准 VCL，\(\lambda\to1\) 退化为 n-Step KL 正则化）。
  - **TD 目标定义**：定义 n-Step TD 目标（式 6），并证明 TD(\(\lambda\))-VCL 是折扣的 n-Step TD 目标之和（命题 4.4），从而与强化学习中平衡蒙特卡洛估计方差和自举偏差的思想建立桥梁。
- **算法流程（文字描述）**：
  - 顺序到达任务 \(t\) 时，保留历史 \(n\) 个后验近似 \(q_{t-1},\dots,q_{t-n}\)。
  - 使用蒙特卡洛采样估计对数似然项，并解析计算若干 KL 散度（针对当前变分分布与各历史分布）。
  - 按 n-Step 平均或 \(\lambda\) 折扣权重组合这些项形成联合目标，执行一步梯度更新（单步优化，无需额外两阶段训练）。
  - 训练时采用高斯逼近、重参化技巧、似然温度控制和早停等技巧。

### 3. 实验设计

- **数据集与基准**：
  - 引入三个新设计的困难基准：**PermutedMNIST-Hard**（10 个顺序置换任务，限制记忆回放仅最近 2 个任务，单头分类器）、**SplitMNIST-Hard**（5 个二分类任务，回放仅最近 1 个任务，单头分类器）、**SplitNotMNIST-Hard**（类似分割但使用多字体 notMNIST 字符，同样严格限制回放和单头）。
  - 两个困难自然图像基准：**CIFAR100-10**（10 任务各 20 类）、**TinyImageNet-10**（10 任务各 20 类），均限制回放内存大小。
- **对比方法**：
  - 非变分基线：Online MLE（仅当前任务）、Batch MLE（缓冲回放）。
  - 贝叶斯变分方法：VCL、VCL CoreSet、UCL（基于节点不确定性的自适应正则化）、UCB（基于参数不确定性的自适应学习率）。
  - 本文方法：**n-Step TD-VCL**、**TD(\(\lambda\))-VCL** 以及将 TD 目标嵌入 UCL/UCB 的 **TD-UCL**、**TD-UCB**。
- **评估指标**：随时间推移所有已见任务上的平均分类准确率，并展示每任务单独准确率随序列变化的曲线。

### 4. 资源与算力

- 文中明确说明所有实验使用 **单张 NVIDIA RTX 4090 GPU**。
- 未报告具体训练总时长，但提到每种方法分配约 **1 GPU·天** 的预算用于公平超参搜索，并采用早停策略减少每个新任务所需的训练 epoch 数（最大 100 但早停耐心为 5 个 epoch），整体计算开销在单一 GPU 下可接受。

### 5. 实验数量与充分性

- **实验组数**：在 **5 个不同数据集**（3 个 MNIST 相关基准 + CIFAR100-10 + TinyImageNet-10）上进行了多方法对比，每个基准分别报告多个时间步的平均准确率。
- **消融与鲁棒性分析**：
  - 超参数灵敏度分析：在 PermutedMNIST-Hard 上分别对 **n-Step KL** 的步数 \(n\) 和温度参数 \(\beta\)，以及对 **TD(\(\lambda\))-VCL** 的 \(n\) 和 \(\lambda\) 进行网格搜索，绘制了详细的热力图或曲线（附录）。
  - 针对不同基准和不同贝叶斯基础方法（VCL、UCL、UCB）均比较了其 TD 增强版本，展示目标函数的通用性和增益。
- **公平性与客观性**：
  - 所有方法使用相同架构、相同重播内存限制、相同优化器（Adam）和早停设置，并报告多随机种子（10 或 5）的均值和 2 倍标准差。
  - 超参数对所有方法均进行了随机搜索，预算相同。
  - 实验覆盖了从简单到困难的多种数据分布，并特别强调了单头分类器和严格重播限制以增加难度，避免传统 MNIST 基准被多分类头“饱和”的问题，评估较为全面、客观。

### 6. 论文的主要结论与发现

- TD-VCL 目标族在多个难度递增的持续学习基准上 **显著优于** 标准 VCL 及其变体，在任务数增多时尤其明显，有效缓解了灾难性遗忘。
- 每任务单独精度分析显示，早期任务的遗忘被大幅抑制，方法更鲁棒。
- TD 目标可 **与不同贝叶斯方法（UCL、UCB）正交结合**，均带来一致的性能提升，体现其通用性。
- 超参数分析表明，适度扩大回顾步数 \(n\)（到 5 左右）有益，但过大可能饱和或略降；方法对 \(\lambda\) 有较好的鲁棒性，仅在任务数较多时略有差异。
- 与强化学习 TD 方法的理论联系为持续学习提供了新的视角。

### 7. 优点

- **理论创新与解释性**：将变分持续学习目标与 TD 方法建立严谨联系，揭示了“复合更新”与“自举”的关系，并统一谱系涵盖从标准 VCL 到 n-Step 平均的多种算法。
- **误差稀释机制**：利用多个历史后验估计分散单次近似误差的影响，直观而有效，并且重播机制自然地融入目标函数，无需额外两阶段训练。
- **实验设计严格**：创建了更困难的基准（限制回放、单头分类器），避免过时的 MNIST 基准被简单方法饱和，评估更贴近现实挑战。
- **通用性强**：与现有多种变分方法兼容（VCL、UCL、UCB），即插即用可提升性能，说明其原理不局限于特定实现。
- **工程可复现**：提供代码，给出详细超参数表，使用单 GPU 且早停，计算开销适中。

### 8. 不足与局限

- **超参数依赖性**：需要调节回顾步数 \(n\) 和衰减系数 \(\lambda\) 以及似然温度 \(\beta\)，不同基准下最佳取值不同，需额外搜索。
- **内存与计算开销**：需要存储多个历史后验估计（尽管当代贝叶斯参数子空间方法可缓解），在极大规模模型上可能增加内存压力，文中未对存储量做定量分析。
- **任务序列假设**：推导依赖任务 i.i.d. 假设，虽然在实验中通过回放部分缓解序列相关性，但理论上未讨论任务分布漂移剧烈时的适应性。
- **评估局限**：实验集中在图像分类领域，缺少文本、强化学习或更复杂的任务增量和域增量场景的验证。
- **θ 近似建模**：所有实验使用高斯均值场近似，未在更丰富的变分族上测试，表现可能受近似能力限制。

（完）
