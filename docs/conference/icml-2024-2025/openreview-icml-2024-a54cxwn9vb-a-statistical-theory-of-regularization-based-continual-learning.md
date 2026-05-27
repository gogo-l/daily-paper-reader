---
title: A Statistical Theory of Regularization-Based Continual Learning
title_zh: 基于正则化的持续学习的统计理论
authors: "Xuyang Zhao, Huiyuan Wang, Weiran Huang, Wei Lin"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=A54CXWn9VB"
tags: ["query:continual"]
score: 9.0
evidence: 基于正则化的持续学习统计分析
tldr: 本文针对持续学习中的正则化方法进行统计分析，研究线性回归任务序列中不同正则化项对模型性能的影响。首先推导了使用全部数据时的理想估计器收敛速率，然后分析了一类广义L2正则化算法，包括最小范数估计器和持续岭回归。通过推导估计误差的迭代更新公式，确定了最优超参数。该工作为正则化持续学习提供了理论基础，有助于理解如何平衡新旧任务的学习。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-a54cxwn9vb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 841, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-a54cxwn9vb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 844, \"height\": 386, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-a54cxwn9vb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-a54cxwn9vb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-a54cxwn9vb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 872, \"height\": 435, \"label\": \"Table\"}]"
motivation: 理解正则化项如何影响持续学习性能。
method: 对线性回归任务序列进行广义L2正则化的统计分析，推导估计误差的迭代更新公式。
result: 确定了最优超参数，给出了最优算法的收敛速率。
conclusion: 为正则化持续学习算法设计提供了理论指导。
---

## Abstract
We provide a statistical analysis of regularization-based continual learning on a sequence of linear regression tasks, with emphasis on how different regularization terms affect the model performance. We first derive the convergence rate for the oracle estimator obtained as if all data were available simultaneously. Next, we consider a family of generalized $\ell_2$-regularization algorithms indexed by matrix-valued hyperparameters, which includes the minimum norm estimator and continual ridge regression as special cases. As more tasks are introduced, we derive an iterative update formula for the estimation error of generalized $\ell_2$-regularized estimators, from which we determine the hyperparameters resulting in the optimal algorithm. Interestingly, the choice of hyperparameters can effectively balance the trade-off between forward and backward knowledge transfer and adjust for data heterogeneity. Moreover, the estimation error of the optimal algorithm is derived explicitly, which is of the same order as that of the oracle estimator. In contrast, our lower bounds for the minimum norm estimator and continual ridge regression show their suboptimality. A byproduct of our theoretical analysis is the equivalence between early stopping and generalized $\ell_2$-regularization in continual learning, which may be of independent interest. Finally, we conduct experiments to complement our theory.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究背景**：持续学习（Continual Learning）要求模型依次学习多个任务，由于存储限制无法保存所有历史数据，容易发生灾难性遗忘。
- **核心问题**：正则化项（如 ℓ₂ 约束）如何影响线性回归任务序列上的持续学习性能；如何在**前向知识迁移**（利用旧知识帮助新任务）与**后向知识迁移**（防止遗忘旧任务）之间实现平衡。
- **整体含义**：本文从统计理论出发，揭示不同正则化策略的本质差异，并为如何通过矩阵形式的正则化超参数来同时解决**前‑后向权衡**和**任务间信息异质性**提供原则性指导。

### 2. 论文提出的方法论
- **核心模型**：考虑一系列线性回归任务，所有任务共享真实参数 \(\mathbf{w}^*\)，但各任务的协方差结构可以不同。
- **广义 ℓ₂‑正则化估计器（GR）**：
  - 在第 \(t\) 个任务上优化目标：
    \[
    \hat{\mathbf{w}}_t = \arg\min_{\mathbf{w}} \left\{ \frac{1}{n_t}\| \mathbf{X}_t\mathbf{w} - \mathbf{y}_t\|^2 + \|\mathbf{w} - \hat{\mathbf{w}}_{t-1}\|_{\mathbf{H}_t}^2 \right\}
    \]
    其中正则化矩阵 \(\mathbf{H}_t\) 可以是任意对称正定矩阵。
  - 当 \(\mathbf{H}_t = \lambda_t \mathbf{I}\) 时退化为**持续岭回归（CRR）**；当 \(\mathbf{H}_t \to 0\) 且数据插值时为**最小范数估计（MN）**。
- **关键理论结果**：
  - 在可同时对角化的协方差结构下，推导出估计误差在各特征方向上的迭代更新公式（公式（4））。
  - **最优超参数选择**：令
    \[
    \lambda_j^{(t)} = \frac{\sigma^2/e_j^{(0)} + \gamma_j^{(1)}n_1 + \cdots + \gamma_j^{(t-1)}n_{t-1}}{n_t}
    \]
    可使估计误差达到与**理想估计器（oracle）** 同阶的衰减率，从而彻底避免灾难性遗忘。
  - 该方法等价于使用加权旧任务协方差矩阵之和作为 \(\mathbf{H}_t\)，即
    \[
    \mathbf{H}_t \approx \frac{1}{n_t}\left(n_1\boldsymbol{\Sigma}_1 + \cdots + n_{t-1}\boldsymbol{\Sigma}_{t-1}\right),
    \]
    这一形式与在线 EWC 相似。
- **早停与正则化的等价性**：证明在广义随机梯度下降中，适当设置学习率矩阵可以与广义 ℓ₂‑正则化产生完全相同的解，拓展了单任务中的经典结论。

### 3. 实验设计
- **数据集/场景**：合成数据上的线性回归任务序列，实验分为两类设置：
  1. **无协变量偏移**：所有任务的输入协方差矩阵均为单位阵。
  2. **有协变量偏移**：每个任务的协方差矩阵通过随机生成的特征值构造（绝大多数方向方差为 1，少数方向方差为 100），引入任务间异质性。
- **对比方法**：
  - 理想估计器（ORA，可访问全部数据）；
  - 持续岭回归（CRR）；
  - 最小范数估计（MN）；
  - 本文的广义 ℓ₂‑正则化估计器（GR）使用近似最优 \(\tilde{\mathbf{H}}_t\)。
- **参数设定**：任务数 \(T=20\)，每个任务样本量 \(n_t=150\)，参数维度 \(p=200\)（单任务过参数化），噪声水平 \(\sigma^2=1\) 或 5，重复 100 次取平均。

### 4. 资源与算力
- 文中**未提及** GPU 型号、数量、训练时长等算力信息。所有实验均在合成数据上运行，计算复杂度较低，对硬件无特殊要求。

### 5. 实验数量与充分性
- 实验涵盖了不同噪声水平（2 种）、有无协变量偏移（2 种），并在同一组任务序列下对比了 4 种方法。
- 每组设置重复 100 次并提供平均性能，具有一定的统计稳健性。
- 实验设计直接服务于理论验证，**基本充分**；但仅限合成数据，缺乏真实数据集或更大规模、更多样化的任务场景，覆盖面有限。

### 6. 主要结论与发现
- **最小范数估计（MN）** 存在不可消失的估计误差下界，无法从更多任务中获益，极易发生灾难性遗忘。
- **持续岭回归（CRR）** 无法处理不同方向上的信息异质性，在最坏情况下其误差可与广义正则化方法任意大。
- **广义 ℓ₂‑正则化（GR）** 通过合理选择矩阵形式的超参数，能够同时处理前‑后向权衡和方向性信息差异，最终达到与理想估计器同阶的误差，实现持续的性能提升。
- 早停与广义 ℓ₂‑正则化在持续学习中具有等价性，需要允许学习率矩阵变化。

### 7. 优点
- **理论贡献扎实**：严格推导了误差迭代公式、最优超参数形式，并给出了非渐进界，为理解正则化持续学习提供了清晰的统计理论。
- **统一视角**：将最小范数估计、持续岭回归和在线 EWC 纳入同一框架，指出其局限并提出普适的优化方案。
- **实验一致性**：模拟结果与理论预测高度吻合，清晰地展示了不同方法的优劣。
- **拓展性讨论**：对不满足可交换假设、其他损失函数、不同真实参数等扩展方向进行了讨论。

### 8. 不足与局限
- **假设较强**：理论依赖于**固定设计**、**协方差矩阵可交换**以及**所有任务共享完全相同参数**，现实场景往往不满足。
- **实验局限**：仅在合成数据上验证，**无真实数据集或实际应用场景**（如图像分类、强化学习），缺少与主流 replay‑based 方法的对比。
- **优化超参数的可行性**：最优 \(\mathbf{H}_t\) 依赖真实协方差矩阵和未观测噪声方差，实际中需近似，虽证明了近似对误差影响可控，但实际部署的鲁棒性有待进一步考察。
- **未讨论计算与存储开销**：广义正则化矩阵可能增加计算和存储负担，理论分析未涉及时间/空间复杂度。

（完）
