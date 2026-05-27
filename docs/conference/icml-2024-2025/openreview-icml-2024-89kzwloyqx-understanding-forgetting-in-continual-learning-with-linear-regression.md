---
title: Understanding Forgetting in Continual Learning with Linear Regression
title_zh: 理解线性回归下持续学习中的遗忘
authors: "Meng Ding, Kaiyi Ji, Di Wang, Jinhui Xu"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=89kZWloYQx"
tags: ["query:continual"]
score: 7.0
evidence: 使用线性回归和SGD对持续学习中的遗忘进行理论分析
tldr: 本文在线性回归模型下通过SGD对持续学习中的遗忘进行了一般性理论分析，适用于欠参数化和过参数化情形，揭示了任务序列和算法参数与遗忘之间的复杂关系，填补了持续学习理论理解的空白。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-89kzwloyqx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1725, \"height\": 974, \"label\": \"Figure\"}]"
motivation: 持续学习中灾难性遗忘的理论理解仍不充分，尤其是因素交互。
method: 基于线性回归模型和SGD进行理论分析，考虑欠参数和过参数化情形。
result: 理论框架揭示了任务序列与算法参数对遗忘的非平凡影响。
conclusion: 该工作为持续学习的遗忘机制提供了理论框架，加深了理解。
---

## Abstract
Continual learning, focused on sequentially learning multiple tasks, has gained significant attention recently. Despite the tremendous progress made in the past, the theoretical understanding, especially factors contributing to $\textit{catastrophic forgetting}$, remains relatively unexplored. In this paper, we provide a general theoretical analysis of forgetting in the linear regression model via Stochastic Gradient Descent (SGD) applicable to both under-parameterized and overparameterized regimes. Our theoretical framework reveals some interesting insights into the intricate relationship between task sequence and algorithmic parameters, an aspect not fully captured in previous studies due to their restrictive assumptions. Specifically, we demonstrate that, given a sufficiently large data size, the arrangement of tasks in a sequence—where tasks with larger eigenvalues in their population data covariance matrices are trained later—tends to result in increased forgetting. Additionally, our findings highlight that an appropriate choice of step size will help mitigate forgetting in both under-parameterized and overparameterized settings. To validate our theoretical analysis, we conducted simulation experiments on both linear regression models and Deep Neural Networks (DNNs). Results from these simulations substantiate our theoretical findings.

---

## 论文详细总结（自动生成）

好的，以下是根据论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：研究**持续学习** 中**灾难性遗忘** 现象的理论成因。具体来说，是探究在顺序学习多个任务时，模型为什么会忘记之前学到的知识。
*   **研究动机**：当前持续学习的研究多为经验性方法，对遗忘的理论理解相对匮乏。现有理论工作存在局限性，例如：
    *   假设过强（如要求数据服从高斯分布）。
    *   仅适用于过参数化场景。
    *   依赖于最小范数解等非实际训练的闭式解。
*   **整体含义**：本文旨在提供一个更通用、更贴近实际训练过程（使用SGD）的理论框架，以揭示任务序列特性（如数据协方差矩阵的谱）和算法参数（如步长、数据量）如何共同影响模型遗忘的程度。

### 2. 论文提出的方法论

*   **模型设定**：采用**线性回归模型**，通过**多步随机梯度下降** 算法训练。模型依次学习M个任务，每个任务的数据从不同分布中抽取。
*   **核心思想**：通过分析SGD迭代的动态过程，推导出模型在全部任务上平均超额风险（即遗忘的度量）的**上界和下界**。这个界是数据协方差矩阵的特征谱、步长、样本量及有效维度等的函数。
*   **关键技术细节与公式**：
    *   **遗忘度量**：`G(M) = (1/M) * Σ_{m=1}^M L_m(w_{MN})`，其中`w_{MN}`为最终模型参数，`L_m`为任务m的总体风险，量化了模型在当前参数下对旧任务的遗忘程度。
    *   **误差分解**：将平均超额风险的界分解为**方差误差**和**偏差误差**。
    *   **方差误差**受模型固有噪声`σ²`和由特征谱、步长、任务顺序决定的有效维度`Deff_1`等影响。
    *   **偏差误差**受初始参数偏差`||w0 - w*||²`、投影累积项`Γ₁ᴹ`（反映历史任务动态对后续任务的影响）、以及由步长和协方差矩阵共同作用的累积项`Φ`等影响。
    *   **核心因子**：
        *   **特征值 (`λ_iᵐ`)** 和**截断索引 (`k*_m`)**：根据条件`λ_iᵐ ≥ 1/(Nη)`划分特征空间，用于界定界中各项的主导行为。
        *   **投影累积项 (`Γⁱ_{(p,q)}` 和 `Γ^q_p`)**：定义为 `Π_{j=p}^{q} (1-ηλ_iʲ)^{2N}` ，刻画了从任务`p`到`q`的学习动态传递和衰减。

### 3. 实验设计

*   **数据集与场景**：使用**合成数据** 进行验证。设计了3个不同的任务，其特征值的衰减速率不同（λ_i = i⁻¹, i⁻², i⁻³），以模拟具有不同特征谱的数据分布。标签中添加了高斯噪声（标准差0.1）。
*   **基准对比**：实验是验证性的，而非与不同持续学习算法进行性能对比。其主要对比不同**任务序列**（共6种排列顺序）对遗忘结果的影响。
*   **验证模型**：不仅在**线性回归模型**上验证，还在一个包含输入层、一个含10神经元隐藏层和输出层的**深度神经网络** 上进行了相同的实验，以检验理论洞见在非线性模型上的推广能力。

### 4. 资源与算力

论文中**并未明确提及**所使用的GPU型号、数量或具体训练时长。由于实验使用合成数据和较小规模的网络，可以推断其对算力的要求相对较低，属于常规的桌面级计算资源。

### 5. 实验数量与充分性

*   **实验组数**：实验通过控制变量法设计了多组对比实验，具体包括：
    *   **任务序列变化**：6种不同的任务顺序。
    *   **模型参数规模变化**：低维（10维，欠参数化）和高维（1000维，过参数化）两种设置。
    *   **数据规模变化**：样本量从100到950，增量为50。
    *   **步长变化**：学习率取0.01和0.001。
*   **实验充分性与公平性**：
    *   **充分性**：实验系统地考察了理论所关注的核心变量（特征值顺序、数据维度、步长）对遗忘的影响，覆盖了欠参数化和过参数化两种场景，验证较为充分。
    *   **公平性**：作为一项以理论验证为主的仿真实验，其对比公平性体现在所有实验设置下，除了被研究的变量外，其他条件保持一致。其目的是验证理论预测，而非与其他方法比较优劣。

### 6. 论文的主要结论与发现

*   **任务序列的影响**：当数据量足够大时，将**总体数据协方差矩阵特征值更大的任务放在序列后面训练，会导致更严重的遗忘**。这是因为后训练的大方差任务可能导致模型过拟合，覆盖了之前学到的知识。
*   **步长的影响**：选择合适的（特别是较小的）步长，可以有效减轻欠参数化和过参数化两种场景下的遗忘，因为它使参数更新更精细。
*   **维度的影响**：
    *   **线性回归**：在欠参数化下，维度影响不大；在过参数化下，固定数据量时，增加维度会导致更严重的遗忘。
    *   **深度神经网络**：此趋势与线性回归一致，但通过增加数据量可以缓解高维带来的遗忘。

### 7. 优点

*   **理论框架的通用性**：该分析突破了现有研究的诸多限制，适用于**欠参数化和过参数化**两种设置，且对数据分布的假设（仅需满足四阶矩条件）比高斯假设更为宽松，分析贴近真实SGD训练过程。
*   **深刻的洞见**：揭示了**任务序列（特征谱顺序）与算法参数（步长）之间复杂的交互关系**，并给出了直观解释，如后期训练大方差任务导致过拟合，深化了对遗忘机制的理解。
*   **理论与实验的结合**：理论分析不仅本身完善，还通过在**线性模型和深度神经网络**上的仿真实验得到验证，增强了结论的可信度和泛化潜力。

### 8. 不足与局限

*   **模型简化**：核心理论分析基于线性回归模型，虽然实验拓展到了简单DNN，但其对复杂深度网络和实际复杂任务的适用性仍有待考证。
*   **实验规模有限**：
    *   仅在**合成数据** 上进行了验证，缺乏在真实世界基准数据集上的测试。
    *   使用的DNN结构和任务设置较为简单，未能充分模拟现实中的复杂持续学习场景。
*   **假设的潜在限制**：实验和理论中假设了所有任务的样本量`N`相等，而实际场景中不同任务的数据量常有差异。此外，理论中关于“充分大数据量”的结论是一个渐近性质，其所需的临界样本量在实际中可能难以满足。
*   **理论聚焦**：分析重点关注了任务序列和步长，对任务间可能存在的相关性、不同优化器的影响等其他因素探讨较少。

（完）
