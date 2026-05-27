---
title: Policy-Regret Minimization in Markov Games with Function Approximation
title_zh: 具有函数逼近的马氏博弈中策略遗憾最小化
authors: "Thanh Nguyen-Tang, Raman Arora"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=eZ5QyZV7zi"
tags: ["query:continual"]
score: 4.0
evidence: 研究动态演化环境中马尔可夫博弈的策略遗憾最小化
tldr: 本文研究动态演化环境下智能体面对自适应对手时的策略遗憾最小化问题，提出通用算法框架，在满足Eluder型条件的广泛问题中实现最优O(√T)策略遗憾。该框架揭示了利用对手学习信号是处理反应性对手的关键，扩展了策略遗憾最小化在大规模问题中的应用。虽然主要聚焦博弈场景，但方法对动态环境中智能体自适应决策有启发意义。
source: ICML-2025-Accepted
selection_source: conference_retrieval
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ez5qyzv7zi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1630, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ez5qyzv7zi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1642, \"height\": 403, \"label\": \"Table\"}]"
motivation: 动态环境中智能体需在与自适应对手博弈时最小化策略遗憾。
method: 提出通用算法框架，利用对手学习实现最优策略遗憾。
result: 在满足Eluder型条件下达到O(√T)最优遗憾。
conclusion: 该方法为动态环境中智能体的自适应决策提供了新范式。
---

## Abstract
We study policy-regret minimization problem in dynamically evolving environments, modeled as Markov games between a learner and a strategic, adaptive opponent. We propose a general algorithmic framework that achieves the optimal $\mathcal{O}(\sqrt{T})$ policy regret for a wide class of large-scale problems characterized by an Eluder-type condition--extending beyond the tabular settings of previous work. Importantly, our framework uncovers a simpler yet powerful algorithmic approach for handling reactive adversaries, demonstrating that leveraging opponent learning in such settings is key to attaining the optimal $\mathcal{O}(\sqrt{T})$ policy regret.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：在多智能体强化学习中，当学习者面对一个**策略性、自适应的对手**时，如何在动态演化的环境中实现**策略遗憾（Policy Regret）最小化**。策略遗憾衡量的是学习者的实际收益与“若采用某个固定策略、对手会如何反应”这一反事实收益之间的差距。
- **研究动机**：
  - 经典的外部遗憾（External Regret）无法刻画对手的适应性反应，而策略遗憾更能体现真实交互情景。
  - 现有理论工作多局限于**表格化、状态-动作空间离散且有限**的马尔可夫博弈，难以推广到大规模或连续空间。
  - 本文旨在**将策略遗憾最小化扩展到具有函数逼近的大规模问题中**，并回答文献[1]中提出的若干开放问题。
- **整体含义**：提出第一个在一般函数逼近条件下实现 O(√T) 最优策略遗憾的算法框架，揭示了**利用对手学习信号**（批处理+联合乐观估计）是处理自适应对手的关键。

### 2. 论文提出的方法论
- **算法框架**：BOVL（Batching and Optimism based on Value and Likelihood fitting）。
- **核心思想**：
  - **批处理**：将总交互回合划分为等长批次，每个批次内保持策略不变，使对手对固定策略的响应趋于稳定（应对记忆有界对手）。
  - **联合乐观学习**：同时维护**值函数置信集**（平方损失拟合）和**对手行为模型置信集**（极大似然估计），并通过乐观规划选择策略。
- **关键技术细节**：
  - **对手建模**：假设对手满足 **m-记忆有界** 且稳定，其响应依赖于学习者最近 m 个策略。利用行为模型类 Ψ 逼近对手响应。
  - **条件假设**：引入 ℓ₂型 Eluder 维度条件分别刻画值函数类和对手类的复杂度，同时要求 Lipschitz 连续性。
  - **置信集更新**：在批次起始点，基于历史数据更新值函数置信集（包含近似 Bellman 完备的函数）和对手置信集（包含似然比不超过 β 的模型）。
  - **误差分解**：策略遗憾被分解为值函数误差项和对手模型总变差误差项，利用 Eluder 条件控制批次内误差，最终得到 O(√T) 界。
- **公式与算法流程（文字描述）**：
  - 输入：值函数类 F、对手模型类 Ψ、策略类 ΠA、回合数 T、批次数 K。
  - 对每个批次：
    1. 通过乐观规划选出当前最优策略：在联合置信集中选择使初始状态值最大的 (f, μ, π)。
    2. 执行该策略收集轨迹，对手基于最近 m 个策略响应。
    3. 批次结束后，基于所有历史数据更新 F 和 Ψ 的置信集。
  - 分析时利用 Eluder 型不等式将批次内累积误差转化为批次计数的上界，再通过柯西-施瓦茨得到最终遗憾界。

### 3. 实验设计
- **数据集与场景**：本文为**纯理论分析论文，未进行任何实验**。其结论基于理论推导和定理证明。
- **Benchmark 与对比方法**：在定理陈述和表格中，将本工作的理论保障与 Nguyen-Tang & Arora (2024a) 在**表格设定**下的策略遗憾界进行了对比，并给出在线性函数逼近和表格情况下的实例化结果。

### 4. 资源与算力
- 本文为纯理论研究，**未使用任何 GPU 或算力资源**，故文中未提及相关配置。

### 5. 实验数量与充分性
- 本文**没有实验部分**，因此无实验数量、消融实验等概念。
- 其“充分性”体现在理论证明的严谨性和对前人结果的改进：文中对定理提供了详细证明框架，并在附录中给出了完整推导。通过与已有工作的理论界对比，说明其优势。

### 6. 论文的主要结论与发现
- 在满足值函数和对手类的 ℓ₂型 Eluder 条件、Bellman 完备性、Lipschitz 连续性以及对手行为可实现的假设下，BOVL 算法达到期望的策略遗憾上界 **PR(T) = Õ(√T)**。
- 当实例化到**线性模型**和**表格模型**时，得到的界均优于前人工作，特别是表格情形下改善了因子 √(HSAB/d*)，其中 d* 为最小正访问概率，该量在大型问题中可能任意小。
- 解决了[1]中提出的三个开放问题：1) 扩展到函数逼近；2) 用更简单的算法设计达到更紧的界；3) 放松了一致性对手假设。

### 7. 优点
- **算法设计简洁通用**：将批处理与联合乐观估计结合，避免了之前方法中复杂的逐层探索和截断操作。
- **理论结果显著**：首个在函数逼近下实现最优策略遗憾的工作，且对先前的表格化结果有数量级改进。
- **技术贡献新颖**：提出用 ℓ₂型 Eluder 条件控制批次内损失，并巧妙绕开了对数似然损失缺乏下尾界的难题，用**总变差损失**代替，为在线密度估计等场景提供了新工具。
- **假设更温和**：用 Lipschitz 对手假设替代了严格的一致性条件，扩展了对手类的适用范围。

### 8. 不足与局限
- **纯理论无实验**：缺乏在模拟环境或真实游戏场景下的实证验证，实用性待评估。
- **强假设依赖**：要求对手**记忆有界且稳定**，这在长期交互中可能不成立；需要 Eluder 维度有限和 Bellman 完备性，对于复杂函数类（如神经网络）可能不满足或难以验证。
- **离线对手建模**：对手模型类需事先给定且包含真实对手，未讨论对手模型类不匹配时的健壮性。
- **计算复杂性**：乐观规划涉及**三层优化**（π, μ, f），文中承认一般情形难以高效求解，未探讨实际优化方案。
- **局限场景**：仅研究两人零和或一般和博弈中的对手学习，未涉足合作场景或更多智能体情况。

（完）
