---
title: "The Importance of Being Lazy: Scaling Limits of Continual Learning"
title_zh: 懒惰的重要性：持续学习的规模限制
authors: "Jacopo Graldi, Alessandro Breccia, Giulia Lanzillotta, Thomas Hofmann, Lorenzo Noci"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=edhBkkYS8R"
tags: ["query:continual"]
score: 9.0
evidence: 研究持续学习中的灾难性遗忘，揭示懒惰训练模式有助于知识保留
tldr: 针对持续学习中灾难性遗忘，系统研究模型规模与特征学习程度的影响，通过区分懒惰与丰富训练制度，发现增加网络宽度仅在减少特征学习时有益，并运用动力平均场理论分析无限宽动态，为通过控制学习惰性缓解遗忘提供理论见解。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 761, \"height\": 820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 834, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 806, \"height\": 866, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 809, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 1069, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1765, \"height\": 1008, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 1097, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1774, \"height\": 1100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1434, \"height\": 1068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 870, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1060, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1770, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1767, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1764, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1766, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1768, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1768, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1779, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1070, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1068, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1059, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1061, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 890, \"height\": 438, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-edhbkkys8r/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 372, \"label\": \"Table\"}]"
motivation: 持续学习中模型规模对灾难性遗忘的影响存在矛盾观察，亟待澄清。
method: 通过可变参数化架构区分懒惰与丰富训练制度，结合动力平均场理论分析。
result: 增加网络宽度仅在减少特征学习（更懒惰）时提升持续学习性能。
conclusion: 控制特征学习程度、增加惰性是缓解灾难性遗忘的关键。
---

## Abstract
Despite recent efforts, neural networks still struggle to learn in non-stationary environments, and our understanding of catastrophic forgetting (CF) is far from complete.
In this work, we perform a systematic study on the impact of model scale and the degree of feature learning in continual learning. We reconcile existing contradictory observations on scale in the literature, by differentiating between *lazy* and *rich* training regimes through a variable parameterization of the architecture. We show that increasing model width is only beneficial when it reduces the amount of *feature learning*, yielding more laziness. Using the framework of dynamical mean field theory, we then study the infinite width dynamics of the model in the feature learning regime and characterize CF, extending prior theoretical results limited to the lazy regime. We study the intricate relationship between feature learning, task non-stationarity, and forgetting, finding that high feature learning is only beneficial with highly similar tasks. We identify a transition modulated by task similarity where the model exits an effectively lazy regime with low forgetting to enter a rich regime with significant forgetting. Finally, our findings reveal that neural networks achieve optimal performance at a critical level of feature learning, which depends on task non-stationarity and *transfers across model scales*. This work provides a unified perspective on the role of scale and feature learning in continual learning.

---

## 论文详细总结（自动生成）

# 论文总结：懒惰的重要性——持续学习的规模限制

## 1. 论文的核心问题与整体含义
- **研究问题**：持续学习中的灾难性遗忘现象，以及模型规模（宽度、深度）究竟如何影响遗忘。此前文献中存在矛盾结论：有研究称宽度增大可减少遗忘，另一部分则指出这种益处依赖于训练时长或预训练。
- **核心动机**：阐明规模与特征学习程度的相互作用，统一现有矛盾，并揭示在非平稳任务分布下，神经网络的最优行为特性。
- **整体含义**：**懒惰（lazy）训练制度（即特征学习程度低）对知识保留至关重要**；单纯扩大网络规模未必有益，其效果取决于网络是否处于“懒惰”状态。这为持续学习中的规模设计提供了新原则。

## 2. 方法论
- **核心思想**：通过一个可变参数化因子 **γ₀** 在**神经正切参数化（NTP，即懒惰极限）** 与**最大更新参数化（µP，即丰富特征学习）** 之间平滑插值。γ₀ → 0 对应懒惰，γ₀ = 1 对应丰富。
- **关键架构**：带残差的网络/MLP，宽度 N，隐藏层 L，前向传播由分支比例 βₗ 和输出比例 γ 控制（见原文表1）。µP 下学习率与 γ₀ 平方成正比。
- **理论工具**：
  - 将**动力平均场理论（DMFT）** 从平稳训练推广到非平稳多任务序列训练，推导了 µP 下无限宽网络的自洽动力学方程（命题4.1）。
  - 定义了跨任务神经正切核（NTK）K_{αiβj}(t)，以及前向、后向核 Φ、G，描述了特征和梯度的演化。
  - 自洽系统包含一维随机过程，描述前向激活和梯度变量的演化，从而在函数空间精确计算遗忘动态。
- **新颖评价指标**：提出**灾难性遗忘率（CFr）**，即相对精度/损失下降率，避免因模型初始学习能力不同造成的比较偏差。
- **损失景观分析**：引入有效锐度（effective sharpness）和有效归一化迹，研究非凸性与遗忘的关系。

## 3. 实验设计
- **数据集**：
  - **Split‑CIFAR10**（5×2 类，任务增量学习 TIL）
  - **Permuted‑MNIST**（5 任务，域增量学习 DIL，通过像素排列控制任务相似性 ρ∈[0,1]）
  - **Split‑TinyImagenet**（不同任务数/每任务类数，如 5/2、5/40 等，TIL）
- **模型与训练**：
  - **ResNet**（基础宽度 N=64，深度 L=6），SGD，余弦学习率计划，无动量/权重衰减，每任务重新开始学习率。
  - **2 层非线性 MLP**（ReLU），用于无限宽 DMFT 仿真，仅在 30 样本的 MNIST 子集上进行（受限于 P²T² 内存和 P³T³ 时间复杂度）。
  - 额外测试了**无跳跃连接的 CNN** 和不同深度配置（包括 µP+1/√L 参数化）。
- **对比方法/消融**：
  - 不同参数化：**NTP** vs. **µP**，并扫过 γ₀ 从 10⁻³ 到 1。
  - 宽度缩放（64→4096）、深度缩放、训练时长。
  - 任务相似性插值：Permuted‑MNIST 中改变相同像素比例，Split‑TinyImagenet 中改变每任务类数。
  - 损失景观对比（Hessian 锐度、迹）。

## 4. 资源与算力
- 文中明确指出：所有训练在**单个 NVIDIA GeForce RTX 4090 或 NVIDIA RTX A6000** 上执行。
- 无限宽度理论仿真使用 3000 个初始高斯过程的随机样本，通过欧拉法求解 ODE，规模受限于数据点平方和训练步立方复杂度。
- 没有提及具体训练总时长或 GPU 小时数，但鉴于任务周期较短（每任务训练 5~10 个 epoch、30 样本的小 MLP），所需算力属于**中等规模学术资源**。

## 5. 实验数量与充分性
- **实验组数众多**：涵盖三个核心视觉数据集，多个宽度、γ₀、深度、参数化组合，加上任务相似性变化和无限宽度仿真，总实验量估计超过数百组独立运行（含不同随机种子，其中 Split‑CIFAR10 重复 5 次）。
- **充分性评价**：
  - 多维度（宽度、深度、训练时长、任务相似性）消融，有效分离了规模与特征学习的影响。
  - 从有限宽度验证到无限宽度理论一致性，提供了现象背后的机制解释。
  - 使用新指标 CFr 提高了对比公平性。
  - 整体实验设计**全面、客观且公平**，支撑了主要结论。

## 6. 主要结论与发现
1. **宽度影响取决于参数化**：NTP 下宽度增加可降低遗忘，µP 下则无此益处；规模本身并非关键，懒惰性才是。
2. **懒惰‑丰富过渡（LRT）与遗忘剧增**：存在临界 γ₀ 值（~0.1），低于此值网络处于“有效懒惰”区，遗忘极低；高于此值则进入丰富区，特征急剧演化，遗忘飙升。
3. **最优特征学习水平可跨尺度转移**：在非平稳训练中，存在一个中间水平的 γ₀*（如 0.1），使平均误差最小，且该最优值**在不同宽度、甚至深度（在 µP+1/√L 下）之间保持一致**，可实现超参数零样本迁移。
4. **任务相似性调制作用**：任务越相似（越接近平稳），最优 γ₀* 越移向 1（允许更多特征学习）。任务高度不同时，懒惰极其重要。
5. **预训练效应**：当每任务包含较多类别时（如 Split‑TinyImagenet 的 5/40），第一个任务训练后网络自动变得懒惰，后续任务特征几乎不再改变，此时宽度扩展甚至能直接降低遗忘。
6. **理论验证**：无限宽 DMFT 仿真与有限宽度实验高度吻合，并表明在高 γ₀ 下，跨任务 NTK 的演化导致遗忘加剧；微扰展开显示特征学习对遗忘的二阶贡献。
7. **损失景观洞察**：高特征学习对应于多任务损失曲面的高曲率（锐度）和负迹增加，指示优化到达鞍点或非凸区域，这与高遗忘相关。

## 7. 优点
- **统一了关于规模与遗忘的矛盾观点**，通过引入训练制度的维度给出合理解释。
- 提出了**可跨模型尺度迁移的最优懒惰性 γ₀***，具有实用价值，有望实现小模型调参、大模型零样本超参数转换。
- 将**动力平均场理论推广至持续学习**，提供了非平稳训练下无限宽动力学的严格刻画，弥补了之前理论仅限于懒惰制度的空白。
- **新指标 CFr** 比传统绝对遗忘值更适合比较不同性能水平的模型。
- 实验体系严谨，从合成到真实数据，从有限到无限宽度，从宽度到深度，**环环相扣**，结论有力。
- 揭示了懒惰‑丰富过渡现象，并发现其与特征演化、遗忘之间的非线性关系，深化了对特征学习代价的理解。

## 8. 不足与局限
- **理论分析局限**：DMFT 推导仅针对**单隐层无跳跃连接的 MLP**，未完全覆盖深度 ResNet 的场景；微扰分析也对小 γ₀ 有效，无法解析丰富区的行为。
- **任务与规模局限**：所有实验均在中等规模的视觉分类任务上进行，尚未在大型语言模型或其他模态上验证。
- **优化器与正则化未包括**：仅使用普通 SGD，未考虑动量、权重衰减或专用持续学习方法（如 EWC、经验回放），实际部署中可能需调整。
- **深度扩展初探**：深度影响仅在 µP+1/√L 下做了初步测试，对更普适的深度‑宽度联合缩放有待系统研究。
- **LRT 成因未完全阐明**：文中推测与学习率平方缩放有关，但确切的动力学根源尚未探讨。
- **损失景观分析为初步性质**，未彻底解决赫森矩阵归一化统计难题。
- 无限宽仿真因计算代价限制到极少数样本，可能掩盖大数据量下的某些特性。

（完）
