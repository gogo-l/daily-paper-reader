---
title: Temporal-Difference Variational Continual Learning
title_zh: 时间差分变分持续学习
authors: "Luckeciano Carvalho Melo, Alessandro Abate, Yarin Gal"
date: 2025-01-23
pdf: "https://openreview.net/pdf?id=6Uh73Wl8Je"
tags: ["query:continual"]
score: 9.0
evidence: 提出时间差分变分持续学习方法
tldr: 针对持续学习中变分方法存在累积近似误差导致遗忘的问题，提出时间差分变分持续学习方法，通过时间差分递归更新后验分布以缓解遗忘。实验证明该方法在多个持续学习基准上优于现有变分方法，有效平衡了可塑性和稳定性。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 648, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1417, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1787, \"height\": 955, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1771, \"height\": 696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1777, \"height\": 812, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1775, \"height\": 872, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1883, \"height\": 900, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1875, \"height\": 956, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1843, \"height\": 965, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1779, \"height\": 863, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uh73wl8je/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1793, \"height\": 869, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1487, \"height\": 791, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1666, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1608, \"height\": 794, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1784, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1757, \"height\": 538, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1682, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1488, \"height\": 790, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uh73wl8je/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1428, \"height\": 1566, \"label\": \"Table\"}]"
motivation: 现有变分持续学习方法因递归近似误差累积而失效。
method: 提出时间差分变分学习目标，用时间差分更新后验分布以减少误差扩散。
result: 在标准持续学习基准上超越现有变分方法，显著缓解遗忘。
conclusion: 时间差分策略有效提升变分持续学习的稳定性和可塑性平衡。
---

## Abstract
Machine Learning models in real-world applications must continuously learn new tasks to adapt to shifts in the data-generating distribution. Yet, for Continual Learning (CL), models often struggle to balance learning new tasks (plasticity) with retaining previous knowledge (memory stability). Consequently, they are susceptible to Catastrophic Forgetting, which degrades performance and undermines the reliability of deployed systems. In the Bayesian CL literature, variational methods tackle this challenge by employing a learning objective that recursively updates the posterior distribution while constraining it to stay close to its previous estimate. Nonetheless, we argue that these methods may be ineffective due to compounding approximation errors over successive recursions. To mitigate this, we propose new learning objectives that integrate the regularization effects of multiple previous posterior estimations, preventing individual errors from dominating future posterior updates and compounding over time. We reveal insightful connections between these objectives and Temporal-Difference methods, a popular learning mechanism in Reinforcement Learning and Neuroscience. Experiments on challenging CL benchmarks show that our approach effectively mitigates Catastrophic Forgetting, outperforming strong Variational CL methods.

---

## 论文详细总结（自动生成）

# 论文结构化总结：时间差分变分持续学习

## 1. 论文核心问题与整体含义

- **研究背景**：现实世界的机器学习系统需要在非平稳数据流中持续学习新任务，面临“可塑性”（学习新知识）与“记忆稳定性”（保留旧知识）的权衡，极易出现灾难性遗忘。
- **具体问题**：贝叶斯连续学习中的变分方法（如 VCL）在递归更新后验时，仅依赖单一的上一个后验近似，导致近似误差在多次递归中不断累积、放大，最终使得遗忘加剧。
- **整体含义**：作者将强化学习中的时间差分（Temporal-Difference, TD）思想引入变分连续学习，提出利用多个历史后验估计来构造学习目标，以稀释单个近似误差、阻止误差累积，从而更稳健地平衡可塑性与稳定性。

## 2. 方法论

- **核心思想**：不再仅使用最新的后验估计进行正则化，而是通过重新展开 VCL 的 KL 散度目标，得到一系列基于多个过去后验估计的等价表达式。
- **关键技术细节**：
  - **n-Step KL Regularization (n-Step TD-VCL)**：将标准 VCL 目标等价变形为加权求和形式，其中正则化项被均分到过去 n 个后验估计上，对数似然项也按时间远近加权，从而稀释任一近似误差的影响。
  - **TD(λ)-VCL**：进一步引入衰减因子 λ∈[0,1)，对不同时间步的后验估计进行几何加权，形成类似 λ-回报的复合目标，控制偏倚与方差之间的平衡。
- **数学形式**（文字描述）：
  - n-Step KL 损失 = 权重为 (n−i)/n 的对数似然项之和 + 权重为 1/n 的 KL 项之和（i=0 至 n−1）。
  - TD(λ)-VCL 损失 = 按 λ^i 加权进行折扣组合，归一化后等价于 n 步 TD 目标的折扣求和。
  - 联系：TD(λ)-VCL 当 λ=0 退化为 vanilla VCL，当 λ→1 趋于 n-Step KL Regularization，形成从 VCL 到 n-Step KL 的算法谱系。
- **算法流程**：在每一时间步 t，利用过去 n 个后验估计和对应任务数据，计算上述复合损失，通过蒙特卡洛采样和重参数化梯度进行优化，无需额外的两阶段优化，天然包含了经验回放机制。

## 3. 实验设计

- **数据集/场景**：
  - **新提出的更高难度基准**：PermutedMNIST-Hard、SplitMNIST-Hard、SplitNotMNIST-Hard（均限制单头分类器和少量回放内存）。
  - **传统挑战基准**：CIFAR100-10、TinyImageNet-10（均为 10 个增量任务）。
- **对比方法**：
  - 非变分基线：Online MLE（仅当前任务数据）、Batch MLE（带有缓冲区）。
  - 变分基线：Vanilla VCL、VCL CoreSet、UCL（节点级不确定性正则）、UCB（不确定性引导学习率）。
  - TD 增强版本：将 TD(λ) 目标与 UCL、UCB 结合得到 TD-UCL、TD-UCB。
- **评价指标**：每步观测到 t 个任务时，所有过往任务的平均准确率。

## 4. 资源与算力

- **硬件**：所有实验使用单张 **NVIDIA RTX 4090** 运行。
- **调参算力**：每个方法（含基线）的随机超参数搜索限制在约 **1 GPU 天**的算力，以保证公平。
- **训练配置**：使用 Adam 优化器，早停法（耐心 5 epoch），大幅减少了收敛所需周期数。

## 5. 实验数量与充分性

- **实验组数**：
  - 在 **5 个 benchmark** 上对 **6 种主要方法**（含 TD 变体）进行全面对比，每个设置报告 5 或 10 个随机种子的平均值和置信区间。
  - 对 **n-Step KL** 和 **TD(λ)-VCL** 分别进行了 **超参数鲁棒性分析**（网格搜索 n, λ, β），在 PermutedMNIST-Hard 上画出了各类消融曲线。
  - 对 **TD-UCL、TD-UCB** 等组合方法也进行了完整表格对比。
- **充分性与公平性**：
  - 所有方法都遵循相同的回放缓冲区限制，使用相同架构和训练流程。
  - 基线和提出的方法都经过了同等算力的超参数搜索，保证了比较的客观性。
  - 全任务级别的逐任务性能分析进一步揭示了灾难性遗忘的缓解情况。

## 6. 主要结论与发现

- **显著缓解遗忘**：在所有 benchmark 中，TD-VCL（尤其是 TD(λ)-VCL）的平均准确率在后期任务上明显优于标准 VCL 及其他变分基线，例如在 PermutedMNIST-Hard 上达到约 89%，而 VCL 仅为 78%。
- **逐任务稳定性**：早期任务在 VCL 下会遗忘到极低水平（如任务 1 降至 50%），而 TD-VCL 维持在 80% 以上。
- **正交增强能力**：TD 目标可直接嵌入 UCL、UCB 等变分方法，带来一致的性能提升，显示其与底层正则化机制的正交性。
- **超参数鲁棒性**：n 在 5 左右达到饱和，λ 的影响在任务数增多时更明显，但整体不太敏感；β（似然温度参数）仍需适当选择。

## 7. 优点

- **理论创新**：巧妙地将 RL 中的 TD 方法引入贝叶斯连续学习，建立了严格的等价变换，给出了从 VCL 到 n-Step KL 的完整算法谱系，并揭示了“经验回放”自然产生于目标函数的推导。
- **实现简洁**：无需两阶段优化，直接通过单一损失函数实现多步正则化和数据重放，对现有 VCL 框架改动最小。
- **实验扎实**：多处设计增强挑战性（单头分类器、极小回放缓冲区），提供了丰富的消融研究、逐任务曲线和与多个基线的对比，结果可靠。

## 8. 不足与局限

- **超参数依赖性**：n 和 λ 的最佳取值依赖于具体任务，需根据情景调优，增加了实际使用时的调节成本。
- **内存开销**：需要在内存中保留多个过去后验估计（如 n 个变分参数集），对深层网络或大规模后验近似会产生额外存储负担，虽然文中指出这可通过低秩适配（如 Bayesian LoRA）缓解，但并未在实验中验证。
- **实验覆盖的局限**：
  - 仅测试了任务增量（task-incremental）场景，未涉及类别增量或在线连续学习下的无任务边界设定。
  - 模型架构相对较小（MLP 和 AlexNet），缺乏与最新大型预训练模型结合的实验。
  - 所有实验均在单一 4090 GPU 上完成，未给出极端大规模系统上的收敛特性。
- **潜在偏差风险**：超参数搜索的空间对所有方法虽然相同，但 n 和 λ 是额外新增的自由度，可能使得对比时稍有利。

（完）
