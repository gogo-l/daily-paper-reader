---
title: Understanding Forgetting in Continual Learning with Linear Regression
title_zh: 利用线性回归理解持续学习中的遗忘
authors: "Meng Ding, Kaiyi Ji, Di Wang, Jinhui Xu"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=89kZWloYQx"
tags: ["query:continual"]
score: 9.0
evidence: 线性回归下持续学习遗忘的理论分析
tldr: 针对持续学习中遗忘因素缺乏理论分析的问题，该工作在欠参数化与过参数化线性回归模型下，利用随机梯度下降进行通用遗忘理论分析，揭示任务序列与算法参数的复杂互动对遗忘程度的影响，通过理论框架明确迭代间遗忘的数学机理，弥补了以往假设限制导致的不足，为理解灾难性遗忘本质及设计缓解算法提供重要理论视角。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-89kzwloyqx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1725, \"height\": 974, \"label\": \"Figure\"}]"
motivation: 缺乏对持续学习中遗忘因素的理论理解。
method: 在欠参数化和过参数化线性回归中通过SGD分析遗忘。
result: 揭示任务序列和算法参数对遗忘的定量影响。
conclusion: 为理解和缓解灾难性遗忘提供了理论基础。
---

## Abstract
Continual learning, focused on sequentially learning multiple tasks, has gained significant attention recently. Despite the tremendous progress made in the past, the theoretical understanding, especially factors contributing to $\textit{catastrophic forgetting}$, remains relatively unexplored. In this paper, we provide a general theoretical analysis of forgetting in the linear regression model via Stochastic Gradient Descent (SGD) applicable to both under-parameterized and overparameterized regimes. Our theoretical framework reveals some interesting insights into the intricate relationship between task sequence and algorithmic parameters, an aspect not fully captured in previous studies due to their restrictive assumptions. Specifically, we demonstrate that, given a sufficiently large data size, the arrangement of tasks in a sequence—where tasks with larger eigenvalues in their population data covariance matrices are trained later—tends to result in increased forgetting. Additionally, our findings highlight that an appropriate choice of step size will help mitigate forgetting in both under-parameterized and overparameterized settings. To validate our theoretical analysis, we conducted simulation experiments on both linear regression models and Deep Neural Networks (DNNs). Results from these simulations substantiate our theoretical findings.

---

## 论文详细总结（自动生成）

好的，请看以下对该论文的结构化深入总结。

### 1. 论文的核心问题与整体含义

*   **研究动机与背景**：持续学习 (Continual Learning) 模型在学习新任务时，会在旧任务上表现急剧下降，这被称为灾难性遗忘。尽管经验研究取得了显著进展，但对遗忘现象的理论理解，特别是导致遗忘的关键因素，尚不充分。
*   **核心问题**：本文旨在为持续学习中的灾难性遗忘提供一个通用且深入的理论分析，揭示任务序列、算法参数（如步长）与数据特性（如数据协方差矩阵特征值）之间的复杂互动关系如何影响遗忘程度。
*   **整体含义**：该研究填补了持续学习在理论层面的空白，为理解遗忘的根本原因和指导设计更有效的缓解策略提供了坚实的理论支架。

### 2. 论文提出的方法论

本论文通过构建一个严谨的数学框架来分析遗忘行为，其核心思想和技术细节如下：
*   **核心模型与算法**：
    *   模型设定为多任务线性回归，模型参数通过随机梯度下降 (SGD) 按顺序在不同任务的数据上进行迭代更新。
    *   同现有许多仅关注过参数化或施加严格数据分布假设（如高斯分布）的研究不同，本方法同时适用于欠参数化和过参数化两种学习场景，并且仅依赖更弱的“四阶矩条件”作为数据分布假设。
*   **关键理论公式与框架**：
    *   定义了一个遗忘度量 `G(M)`，即模型在顺序学习完 `M` 个任务后，在所有任务上的平均过剩人口风险。
    *   **核心定理（定理 3.1 和 3.2）**：推导出了遗忘度量的理论上界和下界。这两个界均由 **偏差误差** 和 **方差误差** 组成。
        *   **方差误差**：源于模型和数据本身的噪声，其大小与步长 `η`、噪声水平 `σ²` 以及有效维度 `Deff` 相关。
        *   **偏差误差**：源于训练初始点与最优解的距离。它主要由一个反映过去任务对当前任务影响的 **投影累积项 (`Γ`)** 和 **协方差累积项 (`Φ`)** 决定。
    *   **关键变量解读**：
        *   **投影累积 (`Γ`)**：刻画了之前任务的学习动态对后续任务的影响，公式中表现为`(I − ηH_j)^(2N)`的连乘，其中 `H_j` 是任务 `j` 的总体数据协方差矩阵，`N` 是迭代次数。
        *   **协方差累积 (`Φ`)**：展现了历史任务信息如何被保留并影响模型对新任务的适应性，与各历史任务协方差矩阵 `H_j` 和内积有关。
        *   **有效维度 (`Deff`)**：由投影累积项 `Γ`、数据协方差矩阵的特征值 `λ` 和截断索引 `k*` 共同决定，反映了问题内在的复杂性。

### 3. 实验设计

*   **数据集/场景**：
    *   **合成数据**：为验证理论而设计，构造了三个线性回归任务（任务1、2、3），其特征值的衰减速率分别为 `i^{-3}`、`i^{-2}` 和 `i^{-1}`（即任务3特征值最大）。数据标签中加入标准差为 0.1 的高斯噪声。
*   **基准 (Benchmark) 设置**：
    *   主要不是与其它方法对比，而是通过改变任务顺序、维度、数据量和步长等参数，来验证理论推导出的遗忘趋势是否正确。
    *   评估了所有六种可能的任务顺序：`[1,2,3]`、`[2,1,3]`、`[1,3,2]`、`[3,1,2]`、`[2,3,1]`、`[3,2,1]`。
*   **模型与方法对比**：
    *   **线性回归模型**：在低维（10个特征）和高维（1000个特征）下分别测试。
    *   **深度神经网络 (DNN)**：包含一个输入层、一个具有10个神经元的隐藏层和一个输出层，用于验证理论结论在非线性模型上的可推广性。

### 4. 资源与算力

*   原文未明确提及实验所使用的 GPU 型号、数量或具体训练时长。因此，无法总结这部分算力信息。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了较为系统的参数敏感性分析，基于合成数据探索了多维因素。
    *   **影响因素**：实验覆盖了任务顺序 (6种)、数据大小 (从100到950)、特征维度 (低/高)、学习率 (0.01/0.001) 等多个维度。
    *   **模型类型**：验证同时在线性模型和深度神经网络上进行。
*   **充分性与客观性**：
    *   实验设计紧密围绕理论发现展开，旨在验证而非单纯追求性能，逻辑上具有内在的客观性和公平性。
    *   然而，实验全部基于合成数据，缺乏在真实世界数据集上的验证，这是一个明显的局限。与现有持续学习基线方法的直接性能比较也完全缺失。

### 6. 论文的主要结论与发现

1.  **任务序列与特征值的关系**：当数据量足够大时，**将具有更大总体数据协方差矩阵特征值的任务排在后面训练，会加剧灾难性遗忘**。因为模型可能过度拟合这些方差大的后期任务。
2.  **步长的影响**：**选择适当小的步长可以有效缓解遗忘**，这在欠参数化和过参数化设置下均成立。小步长通过影响投影累积项，稳定了遗留知识。
3.  **维度的影响**：
    *   在线性回归中，当数据量固定时，过参数化设置下的高维度会加剧遗忘，但在欠参数化下影响不大。
    *   在深度神经网络中，高维度的负面影响可以通过增加数据集大小来缓解，这与线性模型行为不同。

### 7. 优点

*   **理论贡献扎实**：首次为基于 SGD 的线性回归持续学习场景提供了泛用性强（覆盖欠参数化和过参数化）的遗忘上下界分析，揭示了过去研究因强假设（如高斯数据、最小范数解）而未能捕捉的复杂关系。
*   **揭示关键机理**：清晰阐明了遗忘是由偏差和方差两部分组成，并指出了**投影累积**和**协方差累积**这两个核心动态过程，为理解遗忘本质提供了新的视角。
*   **洞见具有实用指导意义**：关于任务排序（特征值大的任务后练导致更多遗忘）和步长选择（小步长缓解遗忘）的发现，对实际持续学习算法设计具有启发性。

### 8. 不足与局限

*   **假设的局限性**：
    *   虽然比之前的研究更宽松，但仍局限于线性回归模型，对于真实世界中占主导地位的深度非线性模型，其理论无法直接泛化。
    *   假设各任务数据量 `N` 相同、标签噪声 `σ²` 一致，这可能与实际情况不符。
    *   步长分析限于**恒定步长**，未深入探讨衰减步长等更复杂的调度策略。
*   **实验覆盖不足**：
    *   **数据集单一**：所有实验均在构造的合成数据上进行，未在真实世界基准（如 permuted MNIST、split CIFAR-100）上测试结论的有效性。
    *   **缺乏对比**：没有与现有的正则化、记忆回放等持续学习方法进行横向比较，无法评估基于该理论设计的策略在实践中的相对优劣。
    *   DNN 实验仅作为一个初步验证，结构简单，其结论的推广性有待进一步考证。
*   **理论到实践的鸿沟**：理论发现（如根据特征值对任务排序可影响遗忘）依赖于对全体数据协方差矩阵特征值的了解，这在实际应用中很难事先获取，限制了其直接操作的便利性。

（完）
