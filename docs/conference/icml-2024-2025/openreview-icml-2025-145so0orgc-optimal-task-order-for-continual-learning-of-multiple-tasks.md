---
title: Optimal Task Order for Continual Learning of Multiple Tasks
title_zh: 多任务持续学习的最优任务顺序
authors: "Ziyan Li, Naoki Hiratani"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=145So0OrGC"
tags: ["query:continual"]
score: 8.0
evidence: 优化任务顺序以提升持续学习性能
tldr: 该研究针对多任务持续学习中任务顺序如何影响性能的问题展开探索。通过线性师生模型推导出任务相似度和排序与学习性能之间的解析表达，总结出两条普适原则：任务应由最不典型到最典型排列，且相邻任务应不相似。在合成和真实图像分类数据集上的实验证实了这些规则的有效性，为持续学习的课程设计提供了理论支持。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1330, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1386, \"height\": 672, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1758, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1589, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1759, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1762, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1745, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 881, \"height\": 397, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1754, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-145so0orgc/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1765, \"height\": 728, \"label\": \"Figure\"}]"
motivation: 任务顺序对持续学习性能影响巨大，但缺乏理论指导。
method: 利用线性师生模型推导出任务相似性与排序对学习性能的解析关系，并提出最优排序原则。
result: 验证了“从最不典型到最典型排列且相邻任务不相似”的规则的普适性。
conclusion: 为持续学习中的任务顺序安排提供了有效策略。
---

## Abstract
Continual learning of multiple tasks remains a major challenge for neural networks. Here, we investigate how task order influences continual learning and propose a strategy for optimizing it. Leveraging a linear teacher-student model with latent factors, we derive an analytical expression relating task similarity and ordering to learning performance. Our analysis reveals two principles that hold under a wide parameter range: (1) tasks should be arranged from the least representative to the most typical, and (2) adjacent tasks should be dissimilar. We validate these rules on both synthetic data and real-world image classification datasets (Fashion-MNIST, CIFAR-10, CIFAR-100), demonstrating consistent performance improvements in both multilayer perceptrons and convolutional neural networks. Our work thus presents a generalizable framework for task-order optimization in task-incremental continual learning.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究问题**：在多任务持续学习（Task-Incremental Continual Learning）中，任务的学习顺序如何影响最终的整体性能？如何优化任务的排列顺序以最大化知识迁移并最小化灾难性遗忘？
*   **整体含义**：本文旨在为持续学习中的任务顺序优化问题提供一个理论框架和实用策略。通过理论分析揭示了任务顺序效应的两个基本原理，并在多个图像分类任务上验证了其有效性，为设计更好的持续学习课程提供了指导。

### 2. 论文提出的方法论
*   **理论模型**：采用带有潜在因子的线性教师-学生模型（Linear Teacher-Student Model with Latent Factors）。数据生成过程为：潜变量 \( s \) 通过混合矩阵 \( A_\mu \) 和 \( B_\mu \) 生成输入 \( x \) 和输出 \( y^* \)，不同任务的混合矩阵具有任务间的相关性（由 \( C^{in} \) 和 \( C^{out} \) 矩阵控制）。
*   **核心公式推导**：考虑任务序列逐个训练，假设 \( N_s / N_x \to 0 \)，推导出所有任务训练结束后的平均最终误差 \( \bar{\epsilon}_f \) 的解析表达式（定理3.1）：
    \[
    \bar{\epsilon}_f = \left\| (C^{out})^{1/2} \left[ I - (I + C^{in,U})^{-1} C^{in} \right] \right\|_F^2
    \]
    其中 \( C^{in,U} \) 是输入相关性矩阵 \( C^{in} \) 的严格上三角部分，表明误差与任务顺序有关。
*   **顺序优化原则**：通过线性扰动分析（令 \( C^{in}_{\mu\nu} = m + \delta M_{\mu\nu} \)），将最终误差分解为任务间隔距离（相对顺序）和任务位置（绝对顺序）两个因素的贡献，引出两个优化规则：
    1.  **外围到核心规则（Periphery-to-Core Rule）**：基于 \( G^+ \) 项，主张将最不具代表性的、不典型的任务安排在学习序列的开头，将最典型的任务放在最后。
    2.  **最长路径规则（Max-Path Rule）**：基于 \( G^- \) 项，在任务不相似度图上，相邻的任务应尽可能不相似，即选择最长哈密顿路径的任务顺序。
*   **相似度估计方法**：在实际应用中，通过测量任务间零样本迁移（Zero-shot Transfer）性能，并定义一个对称的相似度指标 \( \rho_{AB} \) 来估计任务相似性，从而应用上述规则。

### 3. 实验设计
*   **数据集与场景**：
    *   **合成数据**：基于线性教师-学生模型生成的合成任务，具有链、环、树等简单图状相似性结构。
    *   **真实图像数据集**：Fashion-MNIST (MLP)、CIFAR-10 (CNN)、CIFAR-100 (CNN)。将数据集中的类别随机配对或分组，构造多个二分类或多分类（5分类）的任务。
*   **基准比较**：
    *   与**随机任务顺序**的平均性能进行比较。
    *   在规则验证中，直接比较符合规则（外围到核心、最大路径）与违反规则（核心到外围、最小路径）的任务顺序的性能。
*   **对比方法**：主要对比不同任务顺序（如最佳路径 vs. 最差路径、外围到核心 vs. 核心到外围），而非对比不同的持续学习算法。重点在于验证顺序优化原则本身的增益。

### 4. 资源与算力
*   文中**未明确提及**具体使用的GPU数量、详细型号及训练总时长等精确算力资源。仅在附录C.3中提到使用 NVIDIA Tesla V100 GPU，模型实现基于Flax/JAX。

### 5. 实验数量与充分性
*   **实验数量**：
    *   **理论仿真**：验证解析表达式的准确性（图2b）；分析30种任务顺序下的误差（图2c）；对1000个随机生成的相关性矩阵进行任务顺序性能评估（图3e,g）；研究5个任务在链、环、树等4种图结构下的所有 \(5! = 120\) 种顺序的性能（图4）。
    *   **图像实验**：在3个数据集（Fashion-MNIST, CIFAR-10, CIFAR-100）上，各生成100组随机任务集（如5个二分类任务），并对每组任务评估不同顺序，结果按平均相似度进行分桶统计（图5）；在CIFAR-100上研究了不同任务数量（3, 5, 7）的影响（图5g,h）；进行了使用1%和0.1%数据估计相似度的数据效率验证（图9,10）；在CIFAR-10上验证了使用训练集评估相似度的鲁棒性（图7c,d）。
*   **充分性**：实验设计较为全面，覆盖了从理论仿真到多种真实数据集的验证，考虑了不同网络结构（MLP, CNN）、任务类型（二分类、多分类）、任务数量和数据效率，并通过大量随机任务集和顺序的对比来确保统计显著性。实验是客观且公平的，对比的是同一模型下不同顺序的效果，核心在于验证提出的排序原则。

### 6. 论文的主要结论与发现
*   **任务相似性与顺序的解析关系**：成功推导出线性模型中最终误差是任务输入相关性矩阵的上三角部分（即顺序相关）的函数。
*   **两个最优排序原则**：
    1.  **外围到核心规则**：不典型任务应先学，典型任务后学。
    2.  **最长路径规则**：相邻的任务应尽可能不相似，即在不相似度图上寻找最长路径。
*   **理论与实验一致性**：上述原则不仅在合成数据中有效，在Fashion-MNIST、CIFAR-10/100等真实图像分类任务中，无论是MLP还是CNN，都能显著优于随机顺序和相反规则的顺序。
*   **数据效率**：使用仅1%的训练数据来估计任务相似性，就能获得与使用全量数据接近的顺序优化性能提升。

### 7. 优点
*   **理论贡献清晰**：基于简化的线性模型，成功给出了任务顺序效应的解析解释，将复杂现象分解为绝对位置（典型性）和相对位置（路径长度）两个可解释的因子。
*   **原理通用性强**：提出的两个规则在合成数据和多种真实图像数据集、不同网络架构（MLP, CNN）上均得到了验证，展现了超越特定模型的泛化潜力。
*   **方法简单实用**：任务相似度的估计方法仅需训练一次各任务的单任务模型并测量零样本迁移能力，计算成本 \( O(P) \) 远低于暴力搜索的 \( O(P!) \)，且对数据量要求不高。
*   **洞察深入**：揭示了最优任务顺序往往是非贪心的（图4f），并验证了此前经验观察（如最长路径优于最短路径）。

### 8. 不足与局限
*   **理论假设限制**：理论推导基于线性教师-学生模型和随机任务生成假设，且要求 \( N_s / N_x \to 0 \) 和 \( P \ll N_x / N_s \)，直接应用范围有限。未考虑非线性网络和多轮次训练（train to convergence）。
*   **任务设置简化**：实验中构造的任务（如二分类）较为简单，每个任务只用单头（single-head）且训练至收敛，不涉及动态切换或样本回放等更复杂的持续学习策略。
*   **相似度估计依赖先验数据**：方法需要预先收集一小部分跨任务的数据（pilot dataset）来估计相似度，不适用于严格的在线学习场景。当数据量极少（如0.1%）时性能增益不稳定。
*   **泛化性待验证**：未在更复杂的领域（如强化学习、自然语言处理、机器人）和更大规模的数据集或模型上进行验证。

（完）
