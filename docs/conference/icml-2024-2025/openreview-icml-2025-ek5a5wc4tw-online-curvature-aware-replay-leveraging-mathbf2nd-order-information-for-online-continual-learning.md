---
title: "Online Curvature-Aware Replay: Leveraging $\\mathbf{2^{nd}}$ Order Information for Online Continual Learning"
title_zh: 在线曲率感知重放：利用二阶信息进行在线持续学习
authors: "Edoardo Urettini, Antonio Carta"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ek5a5WC4TW"
tags: ["query:continual"]
score: 9.0
evidence: 利用二阶信息（K-FAC）进行在线持续学习，以防止遗忘并加速收敛。
tldr: 针对在线持续学习中任务转换后的不稳定性，本文将基于回放的在线持续学习形式化为带显式KL约束的二阶在线联合优化问题，提出OCAR方法，利用K-FAC近似费雪信息矩阵进行梯度预调节，稳定重放并加速收敛，在多个基准上有效缓解遗忘。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 796, \"height\": 245, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 776, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1756, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1620, \"height\": 1097, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1216, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1214, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1217, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 874, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1053, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1719, \"height\": 483, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ek5a5wc4tw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 670, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ek5a5wc4tw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ek5a5wc4tw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 651, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ek5a5wc4tw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 643, \"height\": 517, \"label\": \"Table\"}]"
motivation: 传统在线持续学习方法在任务转换后容易出现不稳定，回放方法受到遗忘影响。
method: 提出OCAR，将回放OCL建模为二阶优化，使用K-FAC近似FI矩阵进行梯度预调节。
result: OCAR在标准OCL基准上显著降低了遗忘并提升了学习效率。
conclusion: 二阶信息为在线持续学习提供了一种稳定且高效的重放策略。
---

## Abstract
Online Continual Learning (OCL) models continuously adapt to nonstationary data streams, usually without task information. These settings are complex and many traditional CL methods fail, while online methods (mainly replay-based) suffer from instabilities after the task shift. To address this issue, we formalize replay-based OCL as a second-order online joint optimization with explicit KL-divergence constraints on replay data. We propose Online Curvature-Aware Replay (OCAR) to solve the problem: a method that leverages second-order information of the loss using a K-FAC approximation of the Fisher Information Matrix (FIM) to precondition the gradient. The FIM acts as a stabilizer to prevent forgetting while also accelerating the optimization in non-interfering directions. We show how to adapt the estimation of the FIM to a continual setting, stabilizing second-order optimization for non-iid data, uncovering the role of the Tikhonov damping in the stability-plasticity tradeoff.
  Empirical results show that OCAR outperforms state-of-the-art methods in continual metrics, achieving higher average accuracy throughout the training process in three different benchmarks.

---

## 论文详细总结（自动生成）

好的，我将根据论文内容，按照指定要点进行结构化总结。

### 1. 论文的核心问题与整体含义
*   **研究背景**：在线持续学习 (Online Continual Learning, OCL) 要求模型在不获取任务边界、身份等信息的非平稳数据流上连续学习，并同时保持对旧知识的稳定性和对新知识的快速适应能力（可塑性）。
*   **问题揭示**：现有OCL方法（尤其是基于回放的方法）在任务切换后常出现“稳定性差距”（性能骤降后缓慢恢复），且在稳定性与可塑性之间难以取得良好平衡，甚至出现可塑性丧失。传统持续学习中的二阶方法（如EWC）不适合无任务边界的OCL场景。
*   **整体含义**：本文提出应将OCL视为一个带显式约束的连续滤波过程，通过引入损失函数的二阶信息（曲率），从优化层面根本性地改善稳定性和可塑性，实现更平稳的在线学习。

### 2. 论文提出的方法论
*   **核心思想**：将基于回放的OCL构建为一个二阶在线联合优化问题，在优化新数据和回放数据KL散度的同时，加入对回放数据上模型预测分布变化的硬性KL约束，以此显式控制遗忘。
*   **关键技术细节**：
    *   **优化问题形式化**：目标函数为新数据和回放数据的 KL 散度之和，并受两项约束：① 回放数据上模型输出分布的变化 ≤ ρ；② 参数更新量 L2 范数 ≤ ε。
    *   **求解与近似**：利用二阶泰勒展开，将约束转化为 Hessian 矩阵和 Fisher 信息矩阵 (FIM)。通过近似 Hessian 为 FIM（利用 FIM 等价于广义高斯-牛顿矩阵及信息几何度量张量的性质），得到最终更新式：
        `δ* = -α (F_N + (1+λ)F_B + τI)^{-1} (∇_N + ∇_B)`
        其中 `F_N` 和 `F_B` 分别为新数据和回放数据的 FIM，`λ` 控制稳定性约束强度，`τ` 为 Tikhonov 阻尼，`α` 为学习率。
    *   **高效实现 (K-FAC)**：使用 Kronecker-factored Approximate Curvature (K-FAC) 对块对角 FIM 做低秩近似，极大降低求逆计算量。
    *   **在线适配调整**：
        *   `λ` 在类增量场景下随已见类别数增长，域增量场景下随时间增长。
        *   `τ` 初始化为 `α`，并在每一步按固定值递增，以逐步增强长期稳定性。
        *   在分类头形状变化时（新增类别），重置该层 K-FAC 因子 `G` 的指数移动平均。
*   **算法流程**（文字说明）：每一步获取新数据和回放批次 → 计算损失梯度 → 更新阻尼 τ 和稳定性权重 λ → 计算当前批次的 K-FAC 因子并做指数滑动平均 → 组装并求逆预条件矩阵 `F_EMA + τI` → 用该矩阵预条件梯度 → 更新参数 → 回放池做储层采样更新。

### 3. 实验设计
*   **数据集与场景**：
    *   Split-CIFAR100 (20个任务，类增量)
    *   Split-TinyImageNet (20个任务，类增量)
    *   Online CLEAR (10个任务，域增量)
*   **对比基准 (Benchmark)**：与十余种SOTA方法全面对比，包括 ER、GDumb、AGEM、ER+LwF、MIR、RAR、DER++、ER-ACE、SCR、OnPro、OCM、LPR（ICML 2024）等。
*   **评估指标**：采用OCL专用指标 —— 最差情况准确率 (WC-Acc)、平均随时准确率 (AAA)、最终平均准确率 (Acc)，以及线性探测准确率 (Probed Acc)。
*   **实验框架**：重用Avalanche框架和先前工作（Soutif-Cormerais et al., 2023; Yoo et al., 2024）的代码及设置，确保公平性。
*   **其他验证**：
    *   在凸优化小场景下对比 ER、EWC 和自然梯度。
    *   在 Split-MNIST 上进行损失曲面轨迹可视化。
    *   超参数网格搜索（α 与 α/τ）分析稳定性-可塑性权衡。
    *   与 ER-ACE 等方法的组合实验。

### 4. 资源与算力
*   **GPU**：Nvidia Tesla V100 16GB GPU，未使用多卡并行。
*   **训练耗时**：论文在附表中提供了首个任务的训练时间对比。例如在 Split-CIFAR100 上，OCAR 单任务训练约需 38 秒，慢于纯 ER（14 秒），但明显快于 MIR（31 秒）、SCR（131 秒）和 LPR（213 秒）。
*   **总体算力**：本文未给出完整实验的总 GPU 小时数，但通过各方法单任务耗时可大致估算。

### 5. 实验数量与充分性
*   **实验数量**：覆盖 3 个性质不同的标准基准，对比 12+ 种方法，并额外进行了定性可视化、凸设定分析、超参数消融及组合方法实验，实验组数较为丰富。
*   **充分性与公平性**：
    *   **充分性**：实验涵盖了类增量和域增量场景，评估了稳定性、可塑性、最终性能以及表征质量，指标全面。消融实验清晰展示了 α 和 α/τ 对稳定性-可塑性权衡的影响。
    *   **公平性**：使用了公开的标准评估框架和设置，复用了对比方法的公开结果，并在相同条件下重跑了部分关键SOTA方法（OnPro, OCM, LPR）。超参数选择遵循了社区标准流程（在第一段少量任务上进行搜索）。

### 6. 论文的主要结论与发现
*   OCAR 在反映整体在线学习过程的连续性指标（AAA, WC-Acc）上，于所有基准上均显著超越现有SOTA方法，表明了更优的全时稳定性。
*   在最终准确率和线性探测准确率上，OCAR 同样具备竞争力或最佳，尤其在组合 ER-ACE 后，最终准确率在 Split-CIFAR100 上甚至超越了 i.i.d. 训练上限。
*   OCAR 在域增量场景（Online CLEAR）上性能优势尤为突出，验证了其优化改进的鲁棒性。
*   学习轨迹可视化证实，OCAR 能实现比 ER 更平滑、更直接的优化路径，有效缓解任务边界的扰动。
*   超参数 α 和 τ 的比值可用于解释和控制稳定性与可塑性的权衡：低比值导致不稳定，高比值增加遗忘。

### 7. 优点
*   **理论创新**：首次将信息几何和二阶自然梯度视角系统性地引入到带重放的在线持续学习优化中，给出了从二阶约束优化到参数更新的清晰推导。
*   **实践指导性强**：揭示了 Tikhonov 阻尼（τ）及其与学习率比值在 OCL 稳定性-可塑性平衡中的关键作用，提供了超参数调节的直观依据。
*   **效果显著且兼容**：在多个基准上大幅提升全时稳定性和学习效率，并能与其他损失修改方法（如 ER-ACE）无缝结合，效果进一步提升。
*   **效率合理**：虽然比简单ER慢，但比许多复杂的SOTA方法更快，具备实际可用性。

### 8. 不足与局限
*   **超参数敏感性与搜索**：超参数选择基于短的初始流可能偏向可塑性，且 τ 的调度策略为固定增量，未能实现完全自适应的动态调整。
*   **方法前提限制**：方法建立在对 KL 散度（或其衍生的损失函数）进行二阶优化的基础上，若替换为偏离此框架的损失（如 DER++），方法可能失效。
*   **所需额外信息**：在类增量设置下，λ 的自动增长需要知道每个新经验中的类别数量，尽管作者指出这可以通过观察前几步的类别数来估计。
*   **计算开销**：仍需动态估计和求逆 K-FAC 矩阵，在极大规模网络上或对延迟极度敏感的场景中可能有额外挑战。

（完）
