---
title: Towards Understanding Catastrophic Forgetting in Two-layer Convolutional Neural Networks
title_zh: 面向理解两层卷积神经网络中的灾难性遗忘
authors: "Boqi Li, Youjun Wang, Weiwei Liu"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=WkqZ6Qmmq2"
tags: ["query:continual"]
score: 9.0
evidence: 对两层CNN中的灾难性遗忘进行了理论分析，揭示了学习动态的见解。
tldr: 该论文对两层卷积神经网络中的灾难性遗忘进行了理论解析。利用多视角数据模型，分析了持续学习过程中不同特征的学习动态，推导出遗忘如何发生的理论依据。模拟和真实数据实验支持了理论发现，为深入理解CNN中的遗忘机制及设计更好的克服策略奠定了基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 869, \"height\": 887, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 867, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 853, \"height\": 863, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 858, \"height\": 305, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1411, \"height\": 1323, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1416, \"height\": 1326, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1779, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1782, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1782, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1741, \"height\": 1787, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1751, \"height\": 1757, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1762, \"height\": 603, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-wkqz6qmmq2/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1765, \"height\": 602, \"label\": \"Figure\"}]"
motivation: CNN中灾难性遗忘普遍存在，但缺乏对其的理论理解。
method: 采用多视角数据模型分析两层CNN在持续学习中的特征学习动态，推导理论见解。
result: 理论揭示了不同特征在持续学习中的遗忘模式，实验结果与之吻合。
conclusion: 为CNN中遗忘机制提供了理论支撑，有助于开发针对性缓解方法。
---

## Abstract
Continual learning (CL) focuses on the ability of models to learn sequentially from a stream of tasks. A major challenge in CL is catastrophic forgetting (CF). CF is a phenomenon where the model experiences significant performance degradation on previously learned tasks after training on new tasks. Although CF is commonly observed in convolutional neural networks (CNNs), the theoretical understanding about CF within CNNs remains limited. To fill the gap, we present a theoretical analysis of CF in a two-layer CNN. By employing a multi-view data model, we analyze the learning dynamics of different features throughout CL and derive theoretical insights. The findings are supported by empirical results from both simulated and real-world datasets.

---

## 论文详细总结（自动生成）

好的，以下是对该论文的结构化深度总结。

### 1. 论文的核心问题与整体含义

- **研究背景**：持续学习要求模型从连续的任务流中顺序学习，但其面临的核心挑战是灾难性遗忘——模型在学习新任务后，对旧任务的性能急剧下降。
- **核心问题**：虽然灾难性遗忘在卷积神经网络中普遍存在，但对其在 CNN 内部如何发生的**理论理解仍然非常有限**。现有理论工作多集中于线性模型，缺乏对非线性模型（尤其是 CNN）学习动态的深入分析。
- **整体含义**：本文旨在填补这一理论空白，通过在简化的两层 CNN 模型上对灾难性遗忘进行严格的理论分析，揭示其发生的根本原因，为设计和理解缓解遗忘的方法提供理论洞见。

### 2. 论文提出的方法论

- **核心思想**：采用一个精心设计的**多视角数据模型**，将输入数据分解为不同性质的组件（任务特定特征、通用特征、随机特征、背景噪声），并通过分析梯度下降过程中模型对这些组件的**学习动态**，来理论推导灾难性遗忘发生的条件和过程。
- **关键技术细节**：
  - **数据模型**：每个任务的数据由多个正交的“视角”或特征图块构成。这些特征包括：
    - **任务特定特征**：仅在当前任务中与标签相关。
    - **通用/鲁棒特征**：在两个任务中均与标签相关，具有不变性。
    - **随机特征**：与标签无关，但在不同任务中表现为其他任务的任务特定特征，其强度由参数控制。
  - **模型架构**：采用的简化模型是一个具有个通道的两层卷积神经网络（CNN），仅训练第一层权重，第二层固定为全1向量，激活函数为多项式。
  - **分析流程**：在任务增量的设定下，分两个阶段用梯度下降训练模型。
    - **第一阶段学习动态**：理论推导表明，当任务特定特征的信号强度远大于通用特征时，模型会优先且主要学习任务特定特征，而忽略信号微弱的通用特征。
    - **第二阶段遗忘动态**：分析表明，当第一阶段学到的任务特定特征在第二阶段表现为一个信号强度大的“随机特征”时，该特征的权重会因梯度的方向而被迅速“洗掉”或遗忘，导致模型在旧任务上的性能崩溃。
    - **正则化方法效果分析**：理论也证明了，在第二阶段训练时**重放**少量旧任务数据，可以改变特征权重的更新方向，从而有效抑制遗忘。
  - **理论条件**：正式定义了灾难性遗忘，并通过一系列的理论定理和引理，给出了遗忘发生的充分条件，并以定理形式呈现。

### 3. 实验设计

实验旨在验证理论发现，分为模拟数据和真实数据两部分。

- **数据集与场景**：
  - **模拟数据集**：严格按照论文定义的多视图数据模型生成，通过调节参
    数来控制不同特征（通用特征、随机特征）的信号强度。
  - **真实世界数据集**：
    - **CIFAR-10 和 CIFAR-100**：将其拆分为多个二分类任务。
    - **Tiny-ImageNet**：同样拆分为多个二分类任务。
  - **场景设定**：主要为两任务的任务增量学习。
- **基准与对比方法**：
  - 实验的主要目的不是与现有方法对比性能，而是**验证理论结论**。
  - 实验对比了不同参数（、）下的模型行为。
  - 同时验证了**重放方法**减轻遗忘的效果，将其作为一种验证理论洞见的手段。
- **评估指标**：
  - **分类准确率**：分别评估模型在两个任务上的性能。
  - **特征可视化**：利用T-SNE可视化模型学到的特征表示。
  - **特征相关性分析**：通过计算特征与最大奇异向量的内积，分析模型学到的特征如何随学习阶段变化。

### 4. 资源与算力

- **文中未明确说明**：原文未提及实验所使用的具体 GPU 型号、数量或训练时长等算力资源细节。

### 5. 实验数量与充分性

- **实验数量**：
  - 在**模拟数据**上，进行了两组主要实验：一是可视化不同学习阶段各通道对特征的响应；二是系统性地改变参数进行网格搜索，观察准确率变化。
  - 在**真实数据**上，进行了三类实验：一是在多个数据集上测绘任务间的通用性；二是用T-SNE可视化两阶段特征空间演变；三是分析特征与最大奇异向量的内积。
- **实验充分性评估**：
  - **充分性**：实验设计精准地围绕理论推导出的几个关键条件展开，通过模拟和真实数据集，从特征学习动态、最终性能、表示空间变化等多维度验证了理论的正确性，具有较强说服力。
  - **客观性与公平性**：实验并非与其他算法进行性能比拼，而是验证理论本身，因此不存在对比不公平的问题。网格搜索和多次实验取平均值的做法保证了结果的客观性。

### 6. 论文的主要结论与发现

- **遗忘的根本原因**：灾难性忘在两层CNN中以极高概率发生，需同时满足两个条件：
  1. **通用特征信号弱**：任务间的共享、鲁棒特征比任务特有特征的信号弱，导致模型在第一阶段主要学习任务特有特征。
  2. **旧特征成为强干扰**：在第一阶段学到的任务特有特征，在后续任务中表现为一种与标签无关但信号较强的“随机特征”，从而在梯度更新中被快速抹除。
- **特征学习偏好**：梯度下降倾向于学习训练数据中**信号最强的特征**，而非最鲁棒或最具泛化能力的特征。
- **重放方法的原理**：重放旧任务样本能够有效对抗遗忘，其理论机制在于它改变了权重更新的梯度方向，阻止了对旧任务重要特征的抹除。

### 7. 优点

- **理论创新性强**：首次在非线性（两层CNN）模型下，通过明确的特征学习动态对灾难性遗忘给出了严格的理论分析，填补了领域的理论空白。
- **模型设计精妙**：提出的多视图数据模型具备高度的可解释性，将复杂的图像识别过程抽象为对不同性质特征的学习，成功隔离并剖析了导致遗忘的关键因素。
- **理论与实验结合紧密**：实验设计并非简单的性能测试，而是精心设计用以验证理论的每一个关键论断，使结论非常扎实。
- **洞见深刻**：揭示了“学习最强而非最鲁棒特征”这一导致遗忘的内在机制，为未来研究指明了方向，比如开发能鼓励模型学习鲁棒特征的算法。

### 8. 不足与局限

- **模型与假设的简化**：分析基于简化的两层CNN、特定的多项式激活函数和高度结构化的合成数据模型。这些假设与实际应用的复杂深度网络和真实数据的分布有较大差距，结论的泛化性有待进一步验证。
- **任务设定的局限**：分析限定在两任务的**任务增量学习**场景，未涉及更广泛的类增量学习或无任务边界设定的在线持续学习。
- **实验覆盖的局限**：
  - 真实数据集实验主要停留在特征可视化和现象验证，缺乏对理论中具体参数（如特征强度）与真实数据性能之间的量化关联分析。
  - 未与任何现代的持续学习方法进行对比，未能展示其理论相较于现有工作的解释优势。
- **潜在偏差风险**：理论推导中诸多常数和量级的假设可能对结论的普适性构成潜在风险。
- **算力信息缺失**：缺乏对计算资源需求的描述，使得复现成本无法评估。

（完）
