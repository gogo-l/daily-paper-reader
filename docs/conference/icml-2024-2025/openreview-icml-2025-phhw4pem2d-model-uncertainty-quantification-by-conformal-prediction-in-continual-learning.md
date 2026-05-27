---
title: Model Uncertainty Quantification by Conformal Prediction in Continual Learning
title_zh: 持续学习中基于共形预测的模型不确定性量化
authors: "Rui Gao, Weiwei Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=PHhW4PEm2D"
tags: ["query:continual"]
score: 7.0
evidence: 研究持续学习中的校准问题，使用共形预测
tldr: 针对持续学习中模型校准和不确定性量化问题，利用共形预测框架，解决序列学习中数据可交换性违背的挑战，提出新的校准方法。实验结果证明了该方法在保度覆上有效性，为持续学习系统提供可靠的不确定性估计。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-phhw4pem2d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 795, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-phhw4pem2d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1618, \"height\": 935, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-phhw4pem2d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1680, \"height\": 1025, \"label\": \"Figure\"}]"
motivation: 持续学习的序列性破坏数据可交换性，传统共形校准方法失效。
method: 设计适应序列学习的共形预测框架，处理非交换数据。
result: 在持续学习设置下实现了有效的覆盖率保证和校准效果。
conclusion: 为持续学习模型提供了实用的不确定性量化工具，增强系统可靠性。
---

## Abstract
Continual learning has attracted increasing research attention in recent years due to its promising experimental results in real-world applications. In this paper, we study the issue of calibration in continual learning which reliably quantifies the uncertainty of model predictions. Conformal prediction (CP) provides a general framework for model calibration, which outputs prediction intervals or sets with a theoretical high coverage guarantee as long as the samples are exchangeable. However, the tasks in continual learning are learned in sequence, which violates the principle that data should be exchangeable. Meanwhile, the model learns the current task with limited or no access to data from previous tasks, which is not conducive to constructing the calibration set. To address these issues, we propose a CP-based method for model uncertainty quantification in continual learning (CPCL), which also reveals the connection between prediction interval length and forgetting. We analyze the oracle prediction interval in continual learning and theoretically prove the asymptotic coverage guarantee of CPCL. Finally, extensive experiments on simulated and real data empirically verify the validity of our proposed method.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义

### 研究动机与背景
- **核心问题**：持续学习（Continual Learning）领域主要关注减轻灾难性遗忘，但忽略了模型校准（Calibration），即如何可靠地量化模型预测的不确定性。
- **背景**：校准在许多应用中至关重要，例如医学影像诊断，模型需提供预测不确定性以辅助医生决策。共形预测（CP）是一个模型无关、非参数、分布自由的校准框架，能在数据**可交换（Exchangeable）** 的条件下提供理论覆盖保证。然而，持续学习中任务依序学习，破坏了数据可交换性，且过往任务数据受限，导致传统CP方法失效。
- **整体含义**：论文旨在解决持续学习中的不确定性量化难题，提出一种适用于非交换数据场景的CP方法，同时揭示预测区间长度与遗忘现象之间的内在联系。

## 2. 论文提出的方法论

### 核心思想
- **CPCL（Conformal Prediction for Continual Learning）**：一种基于共形预测的持续学习模型不确定性量化方法，通过重放过往任务样本构建校准集，并利用条件分位数估计量处理校准分数中的序列依赖关系。

### 关键技术细节
- **校准集构建**：受重放方法启发，维护一个缓冲区存储每个之前任务的 \(N_{cal}\) 个样本，与当前任务样本共同组成校准集，以解决过往数据不可访问的问题。
- **非一致性分数函数**：采用Sigmoid函数 \( s(X_{ti}, Y_{ti}) = \frac{1}{1+e^{-\hat{\mu}_{ti}}} \)，其中 \(\hat{\mu}_{ti}\) 为预测误差。该函数值域为 (0,1)，具有可逆性，便于后续构建预测区间并进行理论证明。
- **依赖关系处理**：不再直接使用经验分位数，而是重构一个数据集 \(\mathcal{D}^T_R = \{ (X^R_i, Y^R_i) \}\)，其中输入 \(X^R_i\) 包含连续任务的分数序列，以捕捉分数间的依赖；输出 \(Y^R_i\) 近似于包含所有已见任务知识的联合任务分数。
- **分位数回归森林（QRF）**：在重构数据集上训练QRF，获得条件分布函数 \(\hat{F}(y|X^R_{N_{cal}})\) 的估计，进而得到条件分位数估计量 \(\hat{Q}_T(x = X^R_{N_{cal}}; \alpha)\)。
- **预测区间构建**：利用条件分位数估计量定义预测区间 \(\hat{C}^\alpha_{ut} = \{ Y_{Tu} : \hat{Q}_T(X^R_{N_{cal}}; \hat{\beta}) \le s \le \hat{Q}_T(X^R_{N_{cal}}; 1 - \alpha + \hat{\beta}) \}\)，并通分过分数函数的逆推导出显式区间表达式。其中 \(\hat{\beta}\) 通过最小化区间长度选择。
- **算法流程**（见原文Algorithm 1）：对每个任务，训练模型，收集校准样本，计算分数，重构数据集，训练QRF获取条件分位数估计量，最后为测试输入构建预测区间。

### 理论贡献
- 分析了持续学习中的Oracle预测区间。
- 证明CPCL的预测区间具有渐近条件覆盖保证（即当 \(N_{cal} \to \infty\) 时，真实值落入区间内的概率收敛至 \(1-\alpha\)）。

## 3. 实验设计

### 数据集与场景
- **模拟数据**：遵循Zou & Liu (2024)的设置，生成两个回归任务，每个包含5000训练样本和2000测试样本（每任务各1000），使用线性预测器。
- **真实数据**：Tiny ImageNet子集，包含200类的子集，随机选择5个类构成5个任务，每个类500样本（80%训练，20%校准），外加50个测试样本。使用预训练AlexNet生成条件分布，ResNet-18为训练模型。

### 评价指标
- **覆盖率（Coverage）**：测试样本中真实输出落入预测区间内的比例，与目标置信水平 \(1-\alpha\) 对比。
- **平均区间长度（Average Interval Length）**：所有测试样本预测区间的平均宽度。

### 对比方法
- 在真实数据上，评估了多种经典持续学习方法结合CPCL的性能：SI、EWC、MAS、DGR以及Fine-tuning（作为基线），以考察持续学习方法对CPCL的影响。

## 4. 资源与算力
- 论文**未明确说明**使用的GPU型号、数量或具体训练时长。实验设置仅提及了数据集规模和模型结构，计算资源信息缺失。

## 5. 实验数量与充分性

### 实验组数
- **模拟数据**：针对 \(\alpha \in \{0.05, 0.1, 0.15, 0.2, 0.25, 0.3\}\) 共6个水平，每个水平进行100次随机重复实验，并展示小提琴图评估覆盖率分布。
- **真实数据**：针对 \(\alpha \in \{0.1, 0.2, 0.3\}\) 共3个水平，进行20次随机重复实验。每个水平下，展示5个任务（任务2至5）的覆盖率和区间长度变化情况。

### 实验充分性评价
- **充分性**：实验覆盖了模拟与真实场景，重复次数足够（100/20次），统计结果稳定。多水平的 \(\alpha\) 和多种持续学习方法的对比提供了客观性验证。
- **局限性**：真实数据仅用 Tiny ImageNet 一个数据集，且任务数（5个）和类别较少，消融研究有限（未分析不同重放策略或QRF参数的影响）。

## 6. 论文的主要结论与发现
- **CPCL有效性**：在仿真和真实数据上，CPCL 结合不同持续学习方法均能实现接近甚至超过目标覆盖率的区间覆盖，验证了方法的有效性。
- **区间长度与遗忘的关联**：随着学习任务数增加，预测区间平均长度呈上升趋势，表明CPCL能反映灾难性遗忘的程度，为评估持续学习方法的记忆保持能力提供了新视角。
- **理论保证**：严格证明了在给定假设下，CPCL的预测区间具有渐近条件覆盖保证，解决了非交换数据场景下的量化难题。

## 7. 优点
- **首创性应用**：首次将共形预测系统性地应用于持续学习的不确定性量化，解决了数据非交换和校准集缺失的关键挑战。
- **方法创新**：通过分数序列重构和QRF捕捉依赖，设计巧妙；Sigmoid分数函数的使用兼具理论严谨性和实践便利性。
- **理论完整**：给出了渐近覆盖保证的严格证明，并揭示了区间长度与遗忘的现象学联系，增强了方法的可解释性。
- **实验扎实**：模拟和真实实验验证了覆盖率的有效性，多方法对比增加了可信度。

## 8. 不足与局限
- **实验覆盖范围有限**：仅在一个真实图像数据集（Tiny ImageNet）上测试，任务复杂度较低（5个任务，每类1任务），未扩展到更多类别或更复杂的持续学习基准（如Permuted MNIST、CIFAR-100等）。
- **回归局限**：论文仅考虑回归设置，未探讨分类问题中的预测集构造，而分类是持续学习的主流场景。
- **重放策略简单**：校准集构建仅采用等量样本重放，未比较其他更高级的重放或生成方法对校准性能的影响。
- **计算资源未报告**：缺乏GPU型号、训练时间等信息，不利于评估方法在资源受限场景下的可行性。
- **假设依赖**：渐近理论依赖于Lipschitz连续性等假设，实际复杂任务中可能不严格满足，影响实际覆盖表现。

（完）
