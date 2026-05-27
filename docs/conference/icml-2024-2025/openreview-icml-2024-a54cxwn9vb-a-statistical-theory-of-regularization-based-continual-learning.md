---
title: A Statistical Theory of Regularization-Based Continual Learning
title_zh: 基于正则化的持续学习的统计理论
authors: "Xuyang Zhao, Huiyuan Wang, Weiran Huang, Wei Lin"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=A54CXWn9VB"
tags: ["query:continual"]
score: 7.0
evidence: 对正则化持续学习方法的统计理论分析
tldr: 本文对基于正则化的持续学习进行统计理论分析，在线性回归任务序列下，推导了广义ℓ2正则化算法的误差迭代更新公式，并确定了最优超参数，得到了与离线估计器接近的收敛速率。该理论为理解不同正则项如何影响遗忘提供了依据，对设计更有效的正则化策略具有指导意义。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-a54cxwn9vb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 841, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-a54cxwn9vb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 844, \"height\": 386, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-a54cxwn9vb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-a54cxwn9vb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 868, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-a54cxwn9vb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 872, \"height\": 435, \"label\": \"Table\"}]"
motivation: 缺少对正则化持续学习方法的理论分析，难以指导算法设计。
method: 在线性回归任务序列上，分析广义ℓ2正则化族，推导误差更新并求最优超参数。
result: 给出最优算法收敛速率与离线估计器接近的理论保证。
conclusion: 该理论为持续学习的正则化方法选择和设计提供了理论支持。
---

## Abstract
We provide a statistical analysis of regularization-based continual learning on a sequence of linear regression tasks, with emphasis on how different regularization terms affect the model performance. We first derive the convergence rate for the oracle estimator obtained as if all data were available simultaneously. Next, we consider a family of generalized $\ell_2$-regularization algorithms indexed by matrix-valued hyperparameters, which includes the minimum norm estimator and continual ridge regression as special cases. As more tasks are introduced, we derive an iterative update formula for the estimation error of generalized $\ell_2$-regularized estimators, from which we determine the hyperparameters resulting in the optimal algorithm. Interestingly, the choice of hyperparameters can effectively balance the trade-off between forward and backward knowledge transfer and adjust for data heterogeneity. Moreover, the estimation error of the optimal algorithm is derived explicitly, which is of the same order as that of the oracle estimator. In contrast, our lower bounds for the minimum norm estimator and continual ridge regression show their suboptimality. A byproduct of our theoretical analysis is the equivalence between early stopping and generalized $\ell_2$-regularization in continual learning, which may be of independent interest. Finally, we conduct experiments to complement our theory.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究背景**：持续学习（Continual Learning）要求模型在序列化任务中不断学习，但面临灾难性遗忘（catastrophic forgetting）的挑战。基于正则化的方法是缓解遗忘的重要策略，然而其理论性质（尤其在前向/后向知识迁移权衡、数据异质性影响等方面）尚不明确。
- **核心问题**：在线性回归任务序列上，不同的正则化项如何影响模型性能？能否通过统计理论指导最优正则化超参数的选择，从而在持续学习设定下达到接近离线联合训练（oracle）的估计误差？
- **整体含义**：论文从统计角度为基于正则化的持续学习建立了理论框架，揭示了正则化矩阵的选择可以平衡前向/后向迁移、适应任务间异质性，并提供了一种可以达到最优收敛速率的广义ℓ₂正则化算法，为实践中的算法设计提供了理论依据。

### 2. 论文提出的方法论
- **问题设定**：考虑 $T$ 个顺序到达的线性回归任务，所有任务共享真实参数 $w^*\in\mathbb{R}^p$。第 $t$ 个任务的数据 $X_t\in\mathbb{R}^{n_t\times p}$，标签 $y_t = X_t w^* + \varepsilon_t$。允许单任务过参数化（$n_t<p$），但总体聚合后欠参数化。
- **核心方法：广义ℓ₂正则化（GR）**  
  算法迭代更新：  
  $\hat{w}_t^{(GR)} = \arg\min_w \left\{\frac{1}{n_t}\|X_t w - y_t\|^2 + \|w - \hat{w}_{t-1}^{(GR)}\|^2_{H_t}\right\}$  
  其中 $H_t$ 为矩阵值超参数，控制对新任务的拟合程度与对旧知识的保留程度。
- **理论分析关键**：
  - 在协方差矩阵可交换的假设下，将误差投影到特征空间各方向，推导出投影误差 $e_j^{(t)}$ 的迭代更新公式：  
    $E[e_j^{(t)}] = E[e_j^{(t-1)}] - 2\frac{\gamma_j^{(t)} E[e_j^{(t-1)}]}{\lambda_j^{(t)}+\gamma_j^{(t)}} + \frac{(\gamma_j^{(t)})^2 E[e_j^{(t-1)}] + \gamma_j^{(t)}\sigma^2/n_t}{(\lambda_j^{(t)}+\gamma_j^{(t)})^2}$
  - 通过最小化该公式，得到每一时刻各方向的最优正则化系数：  
    $\lambda_j^{(t)} = \frac{\sigma^2/e_j^{(0)} + \sum_{\tau=1}^{t-1} \gamma_j^{(\tau)} n_\tau}{n_t}$
  - 在该最优超参数下，估计误差为：  
    $L(\hat{w}_t^{(GR)}) = \sum_{j=1}^p \frac{\sigma^2}{\sigma^2/e_j^{(0)} + \sum_{\tau=1}^t \gamma_j^{(\tau)} n_\tau}$  
    与离线oracle估计器误差 $\sum_j \frac{\sigma^2}{\sum_{\tau=1}^T \gamma_j^{(\tau)} n_\tau}$ 同阶（仅多一个初始项）。
- **其他发现**：
  - 给出最小范数估计器（MN）和持续岭回归（CRR）的下界，证明其在异质性下可能次优。
  - 证明早期停止（early stopping）与广义ℓ₂正则化在持续学习中的等价性（通过合适的学习率矩阵和停止步数）。
  - 提出实用近似：用 $\tilde{H}_t = \frac{1}{n_t}\sum_{\tau=1}^{t-1} n_\tau \Sigma_\tau$ 代替最优 $H_t$，并给出理论保证。

### 3. 实验设计
- **数据集/场景**：模拟数据，线性回归任务序列。
  - **无协变量偏移**：特征 $x_t^{(i)}\sim\mathcal{N}(0,I_p)$，噪声 $\varepsilon_t^{(i)}\sim\mathcal{N}(0,\sigma^2)$。
  - **有协变量偏移**：真参数 $w^*\sim\mathcal{N}(0,I_p)$，每个任务的协方差矩阵 $\Sigma_t$ 随机生成（特征值大部分为1，少数为100），特征从对应正态分布采样。
- **对比方法**：
  - 持续岭回归（CRR）
  - 最小范数估计器（MN）
  - 广义ℓ₂正则化（GR）使用近似 $\tilde{H}_t$
  - 离线oracle估计器（ORA，作为上界）
- **参数设置**：任务数 $T=20$，样本量 $n_t=150$，维度 $p=200$（单任务过参数化），噪声水平 $\sigma^2=1$ 或 $5$，重复实验100次。

### 4. 资源与算力
- 论文未提及具体的GPU型号、数量或训练时长。实验为合成数据上的线性回归，计算量不大，未对算力进行专门说明。

### 5. 实验数量与充分性
- **实验组数**：考虑了两种噪声水平、两种协变量偏移情形，共计4种主要配置，每种重复100次。
- **充分性与公平性**：
  - 实验覆盖了过参数化和异质性的关键场景，对比方法均为同类正则化持续学习方法。
  - 所有方法使用相同的数据和任务序列，比较公平。
  - 目的为验证理论发现（MN受噪声影响严重、CRR在协变量偏移下退化、GR始终递减并逼近oracle），实验结果与理论一致，具有说服力。
  - 但实验仅限于合成线性回归，未涉及真实数据或更复杂的模型，外部有效性有限。

### 6. 论文的主要结论与发现
- **最优正则化设计**：通过矩阵形式正则化并按照旧任务累积信息和新任务噪声自适应设置各方向权重，可以有效平衡前向-后向知识迁移，适应数据异质性。
- **最优算法性能**：如此设计的广义ℓ₂正则化估计器（GR）在过参数化单任务、异质性协方差下仍可实现误差单调递减，并与离线oracle估计器同阶，避免了灾难性遗忘。
- **常用方法的局限性**：最小范数估计器对噪声过于敏感，误差有下界；持续岭回归因对各方向统一惩罚而无法处理信息异质性，在最坏情况下相对GR的性能比可能无穷大。
- **早期停止等价性**：通过灵活的学习率矩阵，早期停止与广义ℓ₂正则化在持续线性回归中等价，为理论分析和算法设计建立了桥梁。
- **实用算法可行性**：用历史任务协方差加权和近似最优正则化矩阵，在实践中可计算且有理论保证。

### 7. 优点
- **理论深度**：首次在统计框架下严格推导持续学习中正则化带来的误差动态，给出最优超参数的闭式解，并建立与oracle的速率对比。
- **洞察具体**：明确指出前向-后向权衡和信息异质性是影响持续学习性能的关键，并展示了如何通过矩阵值正则化同时解决二者。
- **对现有算法的理论补充**：对最小范数估计器和持续岭回归给出了下界，解释了它们的局限性；同时揭示了早期停止与显式正则化的等价性。
- **实用性指导**：提出的近似算法与经典的弹性权重巩固（EWC）等方法存在联系，且计算简单，可直接应用于线性情形。

### 8. 不足与局限
- **模型假设较强**：要求协方差矩阵可交换（可同时对角化），真实数据往往不满足；尽管实验中违反假设时方法仍有效，理论推广需进一步非交换分析。
- **线性模型限制**：仅研究线性回归，对非线性模型、一般凸损失函数的推广虽有提及，但未详细推导。
- **同质真实参数**：假设所有任务共享同一个 $w^*$，未考虑任务参数不同的情形（如类增量学习），可能限制适用范围。
- **实验单一**：仅在合成数据上验证，缺乏真实数据集或更复杂的持续学习基准（如Split CIFAR等），实验结论的外部有效性有限。
- **近似正则化矩阵的差分影响未充分实证**：仅理论分析了近似误差的影响条件，实验中都使用近似矩阵，未对比最优与近似矩阵的具体性能差异。

（完）
