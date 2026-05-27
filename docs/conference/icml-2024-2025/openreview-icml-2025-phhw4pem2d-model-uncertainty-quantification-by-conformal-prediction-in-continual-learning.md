---
title: Model Uncertainty Quantification by Conformal Prediction in Continual Learning
title_zh: 在持续学习中通过共形预测进行模型不确定性量化
authors: "Rui Gao, Weiwei Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=PHhW4PEm2D"
tags: ["query:continual"]
score: 8.0
evidence: 研究持续学习中的校准以量化模型不确定性
tldr: 针对持续学习中任务顺序学习导致数据非可交换、传统校准方法失效的问题，提出利用共形预测量化模型预测不确定性，即使在序列任务学习下也能提供具有理论高覆盖保证的预测集。实验表明该方法有效提升了模型校准可靠性，为安全关键部署奠定基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-phhw4pem2d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 795, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-phhw4pem2d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1618, \"height\": 935, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-phhw4pem2d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1680, \"height\": 1025, \"label\": \"Figure\"}]"
motivation: 持续学习中的任务顺序学习违反数据可交换性，导致传统校准方法失效。
method: 提出基于共形预测的持续学习模型不确定性量化方法。
result: 在序列任务上获得了具有理论覆盖保证的预测集。
conclusion: 为持续学习模型的可靠校准提供了有效解决方案。
---

## Abstract
Continual learning has attracted increasing research attention in recent years due to its promising experimental results in real-world applications. In this paper, we study the issue of calibration in continual learning which reliably quantifies the uncertainty of model predictions. Conformal prediction (CP) provides a general framework for model calibration, which outputs prediction intervals or sets with a theoretical high coverage guarantee as long as the samples are exchangeable. However, the tasks in continual learning are learned in sequence, which violates the principle that data should be exchangeable. Meanwhile, the model learns the current task with limited or no access to data from previous tasks, which is not conducive to constructing the calibration set. To address these issues, we propose a CP-based method for model uncertainty quantification in continual learning (CPCL), which also reveals the connection between prediction interval length and forgetting. We analyze the oracle prediction interval in continual learning and theoretically prove the asymptotic coverage guarantee of CPCL. Finally, extensive experiments on simulated and real data empirically verify the validity of our proposed method.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
-   **研究动机**：持续学习（Continual Learning）面临的一个重要却尚未充分研究的问题是模型的**校准（Calibration）**。一个校准良好的模型能够可靠地量化其预测的不确定性，这对医疗影像等安全攸关的应用至关重要。
-   **核心挑战**：传统的共形预测（Conformal Prediction, CP）要求数据满足可交换性（Exchangeability），以保证理论上的覆盖率。然而，持续学习中任务按序列学习，破坏了数据的可交换性，且前序任务数据受限或不可得，导致难以构建足够且合适的校准集。
-   **整体目标**：本文旨在为持续学习中的回归模型，提出一种能够提供具有**渐近条件覆盖率保证**的预测区间的校准方法。

### 2. 论文提出的方法论
本文提出的方法称为 **CPCL（Conformal Prediction for Continual Learning）**，其核心思想是通过重放机制构建校准集，并利用分位数回归森林（Quantile Regression Forests, QRF）捕捉分数间的序列依赖性，从而估计条件分位数并构造预测区间。

-   **校准集构建**：采用重放（Replay）策略，为每个已完成的任务维护一个缓冲区，存储`N_cal`个样本。当学习当前任务`τ_T`时，校准集为所有已见任务缓冲区样本的并集。
-   **非一致性分数函数（Nonconformity Score）**：
    -   定义预测误差：`μ̂_ti = Y_ti - f̂_T(X_ti)`，其中`f̂_T`是当前训练好的模型。
    -   分数函数采用Sigmoid形式：`s(X_ti, Y_ti) = 1 / (1 + e^{-μ̂_ti})`，将分数范围限制在`(0,1)`，以保证QRF训练的严谨性，同时函数可逆，便于后续重写预测区间。
-   **捕捉序列依赖性并估计条件分位数**：
    -   计算校准集中所有样本的分数，得到分数序列。
    -   为考虑到分数间的序列依赖性，重构一个新数据集`D_{RT} = {(X_{Ri}, Y_{Ri})}`，其中输入`X_{Ri} = [S^1_i, S^2_i, ..., S^T_i]` 是一个包含T个连续任务分数的向量，输出`Y_{Ri}`是对来自包含所有已见任务知识的“并集任务”的真实分数的近似（通过选定一个任务的分数并乘以系数得到）。
    -   在此重构数据集上训练分位数回归森林（QRF），得到条件分布函数`F̂(s|x)`和条件分位数估计器`Q̂_T(x; α)`。
-   **预测区间构造**：
    -   对于给定的显著性水平`α`，利用`Q̂_T`得到分数上的预测区间`[Q̂(x; β̂), Q̂(x; 1-α+β̂)]`。
    -   选择`β̂`以最小化区间长度。
    -   利用分数函数的逆，将分数区间转换为在输出空间上的预测区间`Ĉ_ut`。
-   **与遗忘的关联**：随着任务数增加，遗忘加剧，导致模型在旧任务上的预测误差增大，从而增大`Q̂(x; 1-α+β̂)`与`Q̂(x; β̂)`的差距，最终使得**预测区间长度增加**。这就建立了预测区间长度与遗忘现象之间的内在联系。
-   **理论保证**：论文在一定假设下（条件累积分布函数利普希茨连续、严格单调递增；QRF树叶子节点尺寸趋于零等），证明了当校准集样本数量`N_cal`趋于无穷时，CPCL估计的条件分布函数和条件分位数均收敛于真实值，从而得到**预测区间的渐近条件覆盖率**。

### 3. 实验设计
-   **数据集/场景**：
    -   **模拟数据**：生成两个回归任务，特征服从不同均值的高斯分布，目标值由线性模型生成。
    -   **真实数据**：使用Tiny ImageNet数据集，随机选择5个类别构成5个顺序学习的回归任务。
-   **基准对比方法**：实验结合了多种经典的持续学习方法作为底层模型（用户指定的预测算法），以验证CPCL在不同策略下的有效性。这些方法包括：
    -   **微调（Finetuning）**：作为基线，不施加任何遗忘缓解策略。
    -   **正则化方法**：SI（突触智能）、EWC（弹性权重巩固）、MAS（记忆感知突触）。
    -   **重放方法**：DGR（深度生成重放）。
-   **评价指标**：
    -   **覆盖率（Coverage）**：测试样本的真实值落入预测区间的比例。
    -   **平均区间长度（Average Length）**：衡量预测区间的效率。
-   **具体设置**：
    -   模拟实验：设置不同显著性水平`α`从0.05到0.3，运行100次。
    -   真实数据实验：每个任务500样本（80%训练，20%校准），50个测试样本，使用预训练AlexNet生成数据，用ResNet-18作为模型，运行20次。考察`α`为0.1, 0.2, 0.3时，不同任务数量下的覆盖率和平均区间长度。

### 4. 资源与算力
论文正文部分**未明确提及**使用的GPU型号、数量或具体训练时长等算力消耗信息。

### 5. 实验数量与充分性
-   **实验数量**：论文进行了**模拟数据和真实数据**两组主要实验。模拟实验针对单种数据分布，进行了100次随机运行；真实实验使用Tiny ImageNet，设定了包含5种方法的对比，进行了20次随机运行。
-   **充分性与公平性**：
    -   实验覆盖了**多种代表性的持续学习方法**（Fine-tuning, EWC, MAS, SI, DGR），较为全面地展示了CPCL在不同机制下的表现，对比公平。
    -   在**多个显著性水平α**下验证了覆盖率，并考察了**随任务数量增加**时覆盖率和区间长度的变化趋势，提供了足够的深度。
    -   然而，实验仅在**回归任务**下进行，且真实数据集只用了Tiny ImageNet一种，场景多样性有限。论文未设计针对方法内部模块（如重放缓冲区大小、重构数据集构建方式）的消融实验。

### 6. 论文的主要结论与发现
-   **CPCL的有效性**：实验表明，结合不同持续学习方法的CPCL，其预测区间的覆盖率均能**达到或超过**设定的显著性水平`1-α`，验证了方法的有效性。
-   **揭示遗忘现象**：随着学习任务数量的增加，CPCL产生的**平均预测区间长度呈上升趋势**。这有效地反映了持续学习中灾难性遗忘的加剧，为衡量持续学习方法性能提供了一个新的视角。

### 7. 优点
-   **首次探索**：本文是**首次将共形预测系统地应用于持续学习的不确定性量化**，并解决了数据非可交换性和校准集受限这两大核心挑战。
-   **理论与方法的创新结合**：
    -   创造性地利用**重放机制**和**分位数回归森林**，将离散的分数序列转化为可建模依赖关系的数据集，巧妙地适配了QRF。
    -   为CPCL提供了**渐近条件覆盖率保证**的理论证明，增强了方法的可靠性。
-   **提供新洞察**：揭示了**预测区间长度与遗忘程度**之间的内在联系，为理解持续性学习模型的退化提供了可量化的工具。

### 8. 不足与局限
-   **应用范围受限**：本文**只关注回归（Regression）场景**，没有涉及分类任务，而分类任务在持续学习中更为普遍。
-   **实验广度有限**：真实数据集只使用了Tiny ImageNet，未在更多样化的基准（如CIFAR-100、CORe50等持续学习标准数据集）上进行验证。同时，缺乏对CPCL各组件（如QRF替代方案、缓冲区大小等）的消融研究。
-   **偏差风险**：
    -   方法的有效性依赖于**重放样本**，这可能引入重放方法本身的偏差，且其表现受缓冲区大小影响，但文中未做讨论。
    -   理论保证依赖于若干假设，这些假设在实际复杂模型中可能难以完全满足。
-   **计算开销**：虽然未明确说明，但为每个任务训练QRF、维护重放缓冲区等操作会引入额外的计算和存储开销，论文未对这一方面的效率进行分析。

（完）
