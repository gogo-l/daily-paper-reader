---
title: Learning to Continually Learn with the Bayesian Principle
title_zh: 基于贝叶斯原理的学习持续学习
authors: "Soochan Lee, Hyeonseong Jeon, Jaehyeon Son, Gunhee Kim"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=IpPnmhjw30"
tags: ["query:continual"]
score: 10.0
evidence: 利用元学习和贝叶斯原理防止灾难性遗忘
tldr: 针对神经网络在非稳态数据流上的灾难性遗忘问题，提出元持续学习框架，融合神经网络表示能力与贝叶斯顺序更新的遗忘免疫性。通过元学习优化更新规则，使网络能在序列任务中持续学习而不遗忘，实验表明在多个数据集上性能优于现有方法。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 1392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1141, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1787, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1781, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1359, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1425, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1349, \"height\": 136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1350, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 822, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 681, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 681, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 676, \"height\": 715, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1575, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 746, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 808, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 664, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1328, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1152, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1239, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1068, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1322, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1150, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1341, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1169, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1322, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1151, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1503, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1302, \"height\": 384, \"label\": \"Table\"}]"
motivation: 神经网络在序列学习时易灾难性遗忘，简单统计模型则无此问题但表达力弱。
method: 提出元持续学习框架，用元学习训练网络模拟贝叶斯顺序更新规则。
result: 在分割数据集上取得比现有持续学习方法更优的抗遗忘性能。
conclusion: 结合神经网络表达力与贝叶斯更新遗忘免疫性的方法极具潜力。
---

## Abstract
In the present era of deep learning, continual learning research is mainly focused on mitigating forgetting when training a neural network with stochastic gradient descent on a non-stationary stream of data. On the other hand, in the more classical literature of statistical machine learning, many models have sequential Bayesian update rules that yield the same learning outcome as the batch training, i.e., they are completely immune to catastrophic forgetting. However, they are often overly simple to model complex real-world data. In this work, we adopt the meta-learning paradigm to combine the strong representational power of neural networks and simple statistical models' robustness to forgetting. In our novel meta-continual learning framework, continual learning takes place only in statistical models via ideal sequential Bayesian update rules, while neural networks are meta-learned to bridge the raw data and the statistical models. Since the neural networks remain fixed during continual learning, they are protected from catastrophic forgetting. This approach not only achieves significantly improved performance but also exhibits excellent scalability. Since our approach is domain-agnostic and model-agnostic, it can be applied to a wide range of problems and easily integrated with existing model architectures.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **研究动机**：深度学习中的持续学习（Continual Learning, CL）核心挑战是灾难性遗忘，即使用随机梯度下降（SGD）在非平稳数据流上训练神经网络时，新知识会覆盖旧知识。相比之下，经典的统计机器学习模型通过序列贝叶斯更新（Sequential Bayesian Update）可以完全免疫遗忘，但这类模型过于简单，难以建模复杂真实数据。
*   **整体含义**：本文旨在结合神经网络的强大表示能力与简单统计模型对遗忘的鲁棒性。提出一种元持续学习框架（Meta-Continual Learning, MCL），使得持续学习仅发生在统计模型中（通过理想贝叶斯更新），而神经网络通过元学习被训练为原始数据与统计模型之间的桥梁，且在学习过程中固定不变，从而从根本上避免遗忘。

### 2. 论文提出的方法论

*   **核心思想**：利用费希尔-达莫瓦-库普曼-皮特曼定理（Fisher-Darmois-Koopman-Pitman theorem）指出的特性：指数族分布是唯一能通过固定维度充分统计量实现无损序列更新的分布族。因此，采用指数族分布（如因子化高斯分布）作为变分后验 \( q_\phi(z|\mathcal{D}) \)，对该后验执行理想的序列贝叶斯更新。
*   **关键技术细节**：
    *   **框架名称**：Sequential Bayesian Meta-Continual Learning (SB-MCL)。
    *   **学习目标**：最大化给定训练流后测试集的对数似然，通过变分下界进行优化。对于监督学习：
        \[
        \log p_\theta(\tilde{y}_{1:N}|\tilde{x}_{1:N},\mathcal{D}) \ge \mathbb{E}_{z\sim q_\phi(z|\mathcal{D})} \left[ \sum_{n}\log p_\theta(\tilde{y}_n|\tilde{x}_n,z) + \sum_{t}\log p_\theta(y_t|x_t,z) \right] - D_{KL}(q_\phi(z|\mathcal{D}) \parallel p_\theta(z)) - \text{const}
        \]
    *   **持续学习过程**：在单个CL episode中，变分先验 \( q_\phi(z) \) 初始为高斯分布；一个称为“learner”的神经网络对每个训练示例 \((x_t, y_t)\) 输出噪声观测 \(\hat{z}_t\) 和精度 \(P_t\)，随后通过解析公式更新后验均值和精度：
        \[
        \Lambda_t = \Lambda_{t-1} + P_t, \quad \mu_t = \Lambda_t^{-1}(\Lambda_{t-1}\mu_{t-1} + P_t \hat{z}_t)
        \]
        该过程无需梯度下降，仅需前向传播，且在元训练阶段可利用并行计算实现批量推理。测试时，模型（model）接收从后验采样的 \( z \) 或其后验均值，并生成预测。
    *   **框架统一性**：SB-MCL 涵盖 GeMCL（高斯混合分类）、Prototypical Networks（原型网络）、ALPaCA（在线回归）等已有方法，并支持将任意模型转换为SB-MCL，通过向解码器注入潜变量 \( z \) 实现。

### 3. 实验设计

*   **数据集/场景**：涵盖监督与无监督任务，包括：
    *   **图像分类**：Omniglot、CASIA（中文字符）、Celeb（MS-Celeb-1M人脸）。
    *   **正弦回归**：合成正弦波回归。
    *   **图像补全**：预测图像下半部分。
    *   **旋转预测**：预测随机旋转角度。
    *   **深度生成建模**：VAE和DDPM的生成任务，数据集包括CASIA和Celeb。
*   **基准方法与对比**：
    *   **SGD-based MCL**：OML（基于MAML）及其一阶近似OML-Rep。
    *   **序列建模方法**：Transformer (TF) 和 Linear Transformer (Linear TF)。
    *   **离线/在线学习**：作为性能上界参考。
    *   **SB-MCL家族**：针对不同领域分别使用GeMCL、ALPaCA或通用因子化高斯变体。
*   **评估设置**：元训练采用10任务-10样本（10-task 10-shot），元测试评估相同设置下的性能，并测试泛化至更多任务/样本、不同数据集的能力。指标包括分类错误率、回归损失等（越低越好）。

### 4. 资源与算力

*   论文在“表6：元训练时间比较”中明确报告了算力信息：
    *   **GPU型号**：单块A40 GPU。
    *   **训练时长**：针对不同任务，训练50K步所需时间：
        *   分类：OML 6.5小时，TF 1.2小时，SB-MCL 40分钟。
        *   补全：OML 16.5小时，TF 1.4小时，SB-MCL 1.2小时。
        *   VAE：OML 19小时，SB-MCL 1.2小时（TF不适用）。
        *   DDPM：OML 5天，SB-MCL 8小时。
*   可见SB-MCL在元训练效率上显著优于OML，也快于TF。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了大量实验，涵盖5大任务类别（分类、正弦回归、补全、旋转预测、生成建模），在多个数据集上进行测试。针对每种任务，均有基准对比表（表2-4），并有详细的任务数/样本数泛化实验（图3和附录表7-18），以及跨数据集泛化实验（表5）。总计报告了超过20组不同设置的定量结果。
*   **充分性与公平性**：实验覆盖领域广，基准方法包含不同范式（SGD-based、序列模型、离线/在线）。所有方法共享相同的编码器架构（如适用），超参数针对10-task 10-shot设定调整，报告5次运行的平均值和标准差，比较相对公平。消融实验通过对比SB-MCL与其MAP变体体现稳健性，但缺少对潜变量维度、后验分布类型等方面的进一步消融。

### 6. 论文的主要结论与发现

*   SB-MCL家族在所有测试基准上均显著优于基于SGD的MCL方法和Linear Transformer，与性能最强但计算代价随序列长度增长的Transformer相当。
*   SB-MCL展现出更强的泛化能力：在更多任务、更多样本以及跨数据集场景下性能退化极小，甚至随着样本数增加性能略有提升，而SGD方法和Transformer会出现严重性能下降。
*   由于指数族后验的固定充分统计量特性，SB-MCL在理论上保证了遗忘为0，将CL问题转化为表示能力优化问题，从而可以专注于架构设计和数据收集。
*   训练效率极高，得益于贝叶斯更新的恒定计算成本和并行性，元训练时间远少于OML，也优于Transformer。

### 7. 优点

*   **方法设计**：巧妙融合元学习和贝叶斯原理，利用指数族后验的遗忘免疫性，既保留了神经网络的表达能力，又从根本上解决遗忘问题，无需回放缓冲区或复杂的正则化近似。
*   **通用性强**：框架领域无关、模型无关，可轻易适配现有架构，并统一了多种先前工作，兼具理论和实践价值。
*   **实验亮点**：实验范围极其广泛，从传统分类回归延伸到深度生成模型（VAE、DDPM），提供了丰富的对比和泛化性分析，证明了方法的鲁棒性和可扩展性。
*   **计算优势**：元训练阶段支持完全并行化，无需二阶梯度，大幅降低计算资源需求。

### 8. 不足与局限

*   **顺序无关的假设**：框架完全忽略训练数据的顺序，对于需要课程学习（curriculum learning）或知识依赖顺序的真实场景不适用。这是由指数族后验的交换性本质决定的。
*   **表示能力上限**：尽管引入神经网络作为特征提取器，但变分后验被限制为指数族（如高斯），其信息瓶颈可能限制对高度复杂数据的适应能力；论文未深入探讨表示能力的极限。
*   **实验覆盖**：虽做了大量任务，但未对潜变量维度、后验分布族（如更复杂的指数族）进行消融研究；也没有与基于回放缓冲区或正则化的经典CL方法在非元学习设定下直接比较。
*   **数据依赖**：MCL范式依赖大规模的元训练集，对于无法提前获取大量相似分布数据的场景，该方法难以应用。论文也指出目前MCL数据集有限。

（完）
