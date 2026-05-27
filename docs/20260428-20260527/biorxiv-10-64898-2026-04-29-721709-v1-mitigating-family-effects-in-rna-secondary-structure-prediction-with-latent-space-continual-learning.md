---
title: Mitigating Family Effects in RNA Secondary-Structure Prediction with Latent-Space Continual Learning
title_zh: 利用隐空间持续学习减轻RNA二级结构预测中的家族效应
authors: "Mokkedem, W., Pedrielli, G., Wu, T."
date: 2026-05-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.04.29.721709v1.full.pdf"
tags: ["query:continual"]
score: 9.0
evidence: 用于RNA结构预测的持续学习方法，缓解灾难性遗忘
tldr: RNA二级结构预测面临数据质量低、类别不平衡和新数据引入时的灾难性遗忘问题。RNAFOLBO提出基于潜空间贝叶斯优化的持续学习框架，将不同RNA类别作为顺序任务，联合编排训练与超参数选择。实验表明，该方法有效缓解遗忘，在多类RNA样本上提升预测精度，为生物序列分析中持续学习应用提供范例。
source: biorxiv
selection_source: fresh_fetch
motivation: 用于RNA结构预测的持续学习方法，缓解灾难性遗忘。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
尽管基于热力学的算法已有数十年历史，且深度学习架构（卷积网络、Transformer、扩散模型）已经出现，准确的RNA二级结构预测仍然困难。事实上，将RNA序列与二级结构标签配对的数据集通常质量低下、充满噪声且家族不平衡，这限制了分布外泛化能力，并在引入新数据体系时加剧灾难性遗忘。我们提出了一种基于终身贝叶斯优化（LBO）的持续学习方法——RNAFOLBO，该方法将从隐空间聚类获得的每类RNA视为顺序任务，并协调异构模型（UFold、RNA-FM、RNADiffFold）的训练和超参数选择，同时保留先验知识。具体而言，我们将LBO应用于15个聚类，这些聚类是通过在RNAGenesis的隐空间中对RNAStrAlign进行聚类获得的，RNAGenesis是一个专门用于上下文表示学习和隐空间结构化的模型，每个聚类的平均F1分数达到0.931（范围为0.177）。这些结果超越了最强的一次性基线，并在无需完全重新训练的情况下减轻了遗忘。当引入额外聚类时，增益仍然存在。总体而言，RNAFOLBO提供了更高、更稳定的性能和实用的可扩展性，用于整合新的RNA聚类或家族，从而实现更鲁棒、可迁移的RNA二级结构预测。

## Abstract
Accurate RNA secondary-structure prediction remains difficult despite decades of thermodynamics-based algorithms and the advent of deep-learning architectures (convolutional networks, Transformers, diffusion models). In fact, the datasets that pair RNA sequences with secondary-structure labels are often low-quality, noisy, and family-imbalanced, which limits out-of-distribution generalization and exacerbates catastrophic forgetting when new data regimes are introduced. We propose a continual-learning approach based on Lifelong Bayesian Optimization (LBO), RNAFOLBO, that treats each class of RNAs obtained from latent-space clustering as a sequential task and jointly orchestrates training and hyperparameter selection of heterogeneous models (UFold, RNA-FM, RNADiffFold), while preserving prior knowledge. Concretely, we apply LBO to 15 clusters obtained by clustering RNAStrAlign in the latent space of RNAGenesis, a model specialized in contextual representation learning and latent-space structuring, achieving a mean F 1 per cluster of 0.931 (with a range of 0.177). These results surpass the strongest one-shot baseline and mitigate forgetting without full retraining. The gains persist as additional clusters are introduced. Overall, RNAFOLBO delivers higher and more stable performance and practical scalability for integrating new RNA clusters or families, enabling more robust and transferable RNA secondary-structure prediction.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：RNA二级结构预测在引入新的数据体系（如新家族、新类别RNA）时，会遭遇**灾难性遗忘**（catastrophic forgetting）——模型在学习新任务时急剧丧失对先前任务的知识。
- **背景挑战**：
  - 现有RNA结构预测数据集质量低、充满噪声、家族不平衡，限制了分布外泛化。
  - 传统深度学习模型（卷积网络、Transformer、扩散模型）通常在静态数据集上一次训练，无法有效应对逐步到来的新RNA类别。
  - 需要一种能够**持续整合新数据、同时保留旧知识**的预测框架，避免每次从头重新训练的高昂成本。

### 2. 论文提出的方法论

- **整体框架名称**：RNAFOLBO（RNA Folding with Lifelong Bayesian Optimization）。
- **核心思想**：
  - 将RNA的**不同类别（通过隐空间聚类获得）视为顺序任务**，应用持续学习范式。
  - 利用**终身贝叶斯优化（Lifelong Bayesian Optimization, LBO）** 在任务序列上联合编排异构模型的训练与超参数选择。
- **关键技术细节**：
  - **隐空间聚类**：使用专门模型 **RNAGenesis**（擅长上下文表示学习和隐空间结构化）对RNAStrAlign数据集进行表示学习，在其隐空间中聚类得到15个RNA类别，作为持续学习的顺序任务。
  - **异构模型池**：集成三类不同架构的预测模型——**UFold**、**RNA-FM**、**RNADiffFold**。
  - **LBO调度**：对每个顺序到达的任务，LBO负责选择适当的模型并优化其超参数，同时在优化过程中保留先前任务的知识，避免遗忘。
  - **训练策略**：无需对历史数据完全重新训练，仅通过LBO的知识迁移与模型选择来保持性能。

### 3. 实验设计

- **数据集与场景**：
  - 基于**RNAStrAlign**数据集，通过RNAGenesis隐空间聚类产生**15个RNA类别**。
  - 序列任务流：15个聚类依次作为新任务引入。
- **Benchmark与对比方法**：
  - **最强一次性基线（one-shot baseline）**：所有数据一次性全部训练的静态模型。
  - 其他可能对比（摘要未详列）：传统非持续学习训练方式。
- **评价指标**：每个聚类的**F1分数**（平均F1 = 0.931，范围0.177）；同时评估遗忘程度和引入额外聚类后的性能增益。

### 4. 资源与算力

- **论文摘要与元数据中未提及具体算力细节**，如GPU型号、数量、训练时长等。
- 由于信息缺失，无法评估实际计算资源消耗规模。

### 5. 实验数量与充分性

- **实验组数**：
  - 在15个RNA聚类上进行持续学习实验，报告每个聚类的F1及平均F1。
  - 与一次性基线进行对比。
  - 测试引入额外聚类时性能增益的持久性。
- **充分性与客观性**：
  - 实验覆盖了多类别序列任务，验证了遗忘缓解和性能提升。
  - 但摘要未提及消融实验（如移除LBO、测试不同聚类数目敏感性、模型单一化影响）或统计显著性检验，**可能存在单维度分析的风险**。
  - 对比的一次性基线较为简单，缺乏与其他持续学习算法（如EWC、经验回放）的直接比较，公平性待考。

### 6. 论文的主要结论与发现

- RNAFOLBO在15个RNA聚类上取得平均F1 0.931，**超越最强一次性基线**。
- 该方法有效**减轻了灾难性遗忘**，无需从头重新训练即可保持先前任务的高性能。
- 当引入额外聚类时，性能增益**持续存在**，证明框架具有**可扩展性**。
- 总体而言，RNAFOLBO提供了**更高且更稳定的性能**，可用于整合新RNA家族，实现更鲁棒、可迁移的RNA二级结构预测。

### 7. 优点

- **方法创新**：首次将终身贝叶斯优化应用于RNA二级结构预测，将RNA类别视为序列任务，实现知识的持续积累。
- **实用性强**：避免完全重新训练，降低计算成本，便于实际部署中不断吸纳新数据。
- **模型异构融合**：同时调度卷积、Transformer、扩散模型三种架构，充分利用各自优势。
- **隐空间结构化**：利用RNAGenesis的隐空间聚类合理划分任务，使持续学习任务边界更清晰、语义更连贯。

### 8. 不足与局限

- **算力信息缺失**：未报告资源消耗，难以评估方法的实际可行性与效率。
- **对比方法简单**：仅与一次性全量训练对比，缺乏与经典持续学习方法（如正则化、动态架构、记忆重放）的横向比较。
- **聚类依赖性**：任务划分完全依赖RNAGenesis隐空间聚类质量，若聚类不合理，可能影响持续学习效果。
- **遗忘衡量有限**：未详细量化遗忘率或知识保留度，仅通过最终F1和增益说明。
- **实验规模局限**：仅在15个聚类上测试，未在更多样化的RNA家族数据集或跨物种数据上验证泛化性。
- **潜在偏差**：使用RNAStrAlign作为源数据，数据集中固有的噪声和家族不平衡可能影响任务划分的均匀性，进而影响结论的普适性。

（完）
