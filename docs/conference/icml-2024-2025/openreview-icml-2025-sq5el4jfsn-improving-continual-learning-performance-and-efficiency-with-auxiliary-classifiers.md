---
title: Improving Continual Learning Performance and Efficiency with Auxiliary Classifiers
title_zh: 利用辅助分类器提升持续学习的性能与效率
authors: "Filip Szatkowski, Yaoyue Zheng, Fei Yang, Tomasz Trzcinski, Bartłomiej Twardowski, Joost van de Weijer"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=sq5eL4jfsn"
tags: ["query:continual"]
score: 10.0
evidence: 利用中间层辅助分类器提升持续学习
tldr: 持续学习面临灾难性遗忘挑战，该工作观察到中间层表征具有更好的抗遗忘性，因此设计辅助分类器附加于各中间层，利用这些表征进行预测，有效提高了多种持续学习算法在标准评估设置下的准确率，且计算开销低，展示了即插即用的实用价值。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 839, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1668, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1759, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1767, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 798, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 844, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 847, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 845, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1757, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1759, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1750, \"height\": 1111, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1750, \"height\": 1106, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1748, \"height\": 1106, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1764, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1755, \"height\": 1765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1747, \"height\": 1105, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1761, \"height\": 1322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1747, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1203, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1201, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1200, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1200, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1200, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1200, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1200, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1201, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1200, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1200, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1199, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1755, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1753, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1755, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1761, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1762, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1763, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1768, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1768, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1768, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 446, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1413, \"height\": 2024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1415, \"height\": 2062, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1761, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 1759, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-044.webp\", \"caption\": \"\", \"page\": 0, \"index\": 44, \"width\": 1760, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-045.webp\", \"caption\": \"\", \"page\": 0, \"index\": 45, \"width\": 1756, \"height\": 458, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1782, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1784, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1492, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1781, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1782, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1779, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1782, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1783, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1783, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1081, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1783, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1782, \"height\": 1515, \"label\": \"Table\"}]"
motivation: 缓解持续学习中的灾难性遗忘并提升效率。
method: 在神经网络中间层添加辅助分类器，利用抗遗忘表征。
result: 在多种持续学习方法上一致提升准确率。
conclusion: 辅助分类器是通用的持续学习增强模块，计算高效。
---

## Abstract
Continual learning is crucial for applying machine learning in challenging, dynamic, and often resource-constrained environments. However, catastrophic forgetting — overwriting previously learned knowledge when new information is acquired — remains a major challenge. In this work, we examine the intermediate representations in neural network layers during continual learning and find that such representations are less prone to forgetting, highlighting their potential to accelerate computation. Motivated by these findings, we propose to use auxiliary classifiers~(ACs) to enhance performance and demonstrate that integrating ACs into various continual learning methods consistently improves accuracy across diverse evaluation settings, yielding an average 10\% relative gain. We also leverage the ACs to reduce the average cost of the inference by 10-60\% without compromising accuracy, enabling the model to return the predictions before computing all the layers. Our approach provides a scalable and efficient solution for continual learning.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：该论文针对的是机器学习在动态环境和资源受限场景下的**持续学习（Continual Learning, CL）** 问题。持续学习的核心挑战是**灾难性遗忘（Catastrophic Forgetting）**，即模型在学习新任务时，会灾难性地覆盖和遗忘先前学到的知识。
*   **研究动机**：
    *   **现象观察**：通过对神经网络中间层表征的分析，作者发现网络**浅层/中间层的表征比最终层的表征更加稳定**，更不易发生灾难性遗忘。
    *   **潜在价值**：这意味着利用中间层特征进行预测，可能比只用最终层具有更好的抗遗忘能力。同时，这也为加速推理提供了可能，因为模型可以在不必计算完所有层的情况下提前给出预测。
*   **整体含义**：本文旨在弥合持续学习和推理效率（早期退出）两个研究领域。通过将辅助分类器（Auxiliary Classifiers, ACs）引入持续学习，既利用中间层表征的稳定性来提升模型整体的准确率，又通过动态推理（Dynamic Inference）机制实现计算成本的节约。

### 2. 论文提出的方法论：核心思想、关键技术细节

*   **核心思想**：在神经网络的多个中间层上附加轻量级的**辅助分类器（ACs）**。由于这些中间层的表征遗忘较慢且具有多样性，它们能正确分类最终分类器可能分类错误的样本（一种称为“过度思考”Overthinking的现象），从而在聚合多个分类器的预测后，提升模型的整体性能。
*   **模型架构与推理**：
    *   **架构**：在骨干网络的子模块 \(f_1, f_2, ..., f_{N-1}\) 之后插入辅助分类器 \(\hat{g}_i\)，连同最终分类器 \(g\)，形成多分类器网络。
    *   **静态推理（Static Inference）**：对于输入 \(x\)，获得从所有 ACs 和最终分类器的预测概率分布 \(p_i\)。最终预测结果 \(y\) 选取所有分类器中**置信度（最大概率）最高的那个分类器的预测**。
        \[
        y = y_{\arg \max_{i \in \{1,...,N\}} \max_k p_i^{(k)}}
        \]
    *   **动态推理（Dynamic Inference）**：这是一种可选的加速推理机制。推理过程按层序贯进行，在每个中间分类器 \(\hat{g}_i\) 处计算其预测概率分布 \(p_i\)。如果其最大概率（置信度）超过一个预设的阈值 \(\lambda\)，则立即返回该预测作为结果，不再计算后续的网络层；否则继续计算。若所有层都未达到阈值，则按静态推理规则返回结果。
*   **训练策略**：
    *   **联合端到端训练**：所有ACs和主网络一起进行端到端训练。分析表明，端到端训练比单独训练ACs（线性探测）效果更好。
    *   **损失加权**：为防止网络对早期层的分类器过拟合，总损失是所有分类器损失的加权和，并且给予早期分类器的损失以较低的权重。权重根据其在网络中的计算位置（例如，完成15%计算量的层，权重增加至0.15）来设定。
    *   **方法复用**：将ACs整合到现有的持续学习方法（如 LwF, BiC, EWC 等）中时，原始方法的逻辑（损失函数）会直接应用于所有分类器，且超参数保持一致。

### 3. 实验设计：数据集 / 场景、Benchmark 与对比方法

*   **数据集与场景**：
    *   **数据集**：主要在 **CIFAR100** 和 **ImageNet100**（ImageNet的前100个类）上进行评估。
    *   **任务划分**：类别增量的持续学习（Class-Incremental Learning），将数据集划分为多个任务。标准划分包括 **5-task** 和 **10-task**（每任务类数相等）。此外，还测试了 Warm-start（第一任务包含半数类别）、更细粒度的 **20-task** 和 **50-task** 划分。
*   **Benchmark 与对比方法（Baseline）**：
    *   **骨干网络**：主要使用 **ResNet32**（用于CIFAR100）和 **ResNet18**（用于ImageNet100）。为验证扩展性，还测试了更深的 **VGG19**、更宽的 **WideResNet16-2** 以及 ViT-base 架构。
    *   **对比的持续学习方法**：将ACs应用在多种主流CL算法上，包括 **FT** (朴素微调), **FT+Ex** (带样本回放), **GDumb**, **EWC**, **LwF**, **ER**, **DER++**, **BiC**, **SSIL**, **ANCL**, **LODE**。每种方法都有**无ACs（Base）** 和**有ACs（+AC）** 两个版本进行比较。
    *   **评估指标**：所有任务训练结束后的**最终平均准确率（Average Accuracy）**，以及动态推理场景下准确率随**推理成本（Inference Cost, FLOPs %）** 的变化曲线。

### 4. 资源与算力

*   文中**未明确提及**所使用的具体GPU型号、数量以及单次实验的绝对训练时长。
*   论文仅在附录B中，以相对方式讨论了ACs引入的训练开销。以最小的模型ResNet-32为例，**6个ACs** 的设置带来了约**50%的额外训练时间**和约**10%的峰值显存占用**增加。作者指出，这是最差情况下的开销，而对于更大的模型（如ViT），ACs的相对开销会更小。

### 5. 实验数量与充分性

*   **实验数量庞大且充分**，旨在全面验证方法的通用性和鲁棒性。
    *   **横向方法覆盖**：对比了11种不同类型的持续学习方法（基于正则化、回放等）。
    *   **纵向场景覆盖**：在CIFAR100和ImageNet100两个数据集上，分别进行了5-task、10-task、warm-start、更长的20/50-task序列等多种设置。
    *   **模型架构覆盖**：在CNN（ResNet, VGG, WideResNet）和ViT上都进行了测试。
    *   **消融实验详尽**：针对ACs的数量（3, 6, 12, 18个）、AC架构（独立式、级联式、集成式）、训练方式（端到端 vs. 线性探测）、不同AC数量、留一法（Leave-one-AC）等进行了系统性消融研究。
    *   **公平性**：所有实验均在统一的**FACIL**框架下运行，保持了固定的内存预算（2000个样本）和汇报了多个随机种子的平均结果，对比客观公平。

### 6. 论文的主要结论与发现

*   **发现1**：持续学习网络中，中间层表征比最终层更稳定，且其训练的分类器对旧任务数据能取得比最终分类器更好的性能（尤以不存储样本的CL方法为甚）。
*   **发现2**：持续训练的网络中存在更严重的“过度思考”现象，即中间分类器能正确分类但最终分类器却误判，这为利用ACs提升准确率提供了理论基础。
*   **结论1 (性能提升)**：将ACs整合到多种主流持续学习方法中，能**一致性地提升最终准确率**。在CIFAR100和ImageNet100的各项基准测试中，平均相对性能提升超过 **10%**。
*   **结论2 (效率提升)**：通过动态推理，ACs可以在**不牺牲最终准确率**的情况下，平均节省 **10-60%** 的推理计算量。准确率在约80-90%的计算预算时即达饱和，实现无损加速。在更大模型（VGG19, ViT）上，该效率优势更明显。

### 7. 优点：方法或实验设计上的亮点

*   **通用性强，即插即用**：ACs作为一个独立模块，可以简单、无缝地集成到绝大多数现有的持续学习方法中，而无需复杂的特定调整，具有很高的实用价值。
*   **性能与效率兼得**：该方法不仅解决了灾难性遗忘带来的性能问题，同时还能通过动态推理机制显著降低推理成本，特别适合资源受限的动态环境。
*   **理论与实验结合紧密**：文章并非直接堆砌模型，而是先通过CKA相似性分析、“过度思考”量化等深入分析，揭示了“中间层表征更稳定”和“可纠正最终层错误”的内在机理，然后用实验成功验证了基于此机理的解决方案。
*   **实验论证极其全面**：作者在多个维度进行了详尽的评估，覆盖了多种数据集、任务划分、模型架构和大量的主流CL算法，使得结论极具说服力和鲁棒性。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

*   **领域限制**：研究目前仅限于**计算机视觉的图像分类任务**，其在其他模态（如自然语言处理、语音）或更复杂的任务（如目标检测、分割）上的有效性有待验证。
*   **训练开销**：虽然推理高效，但ACs的引入确实增加了**训练时间（约50%）和显存开销**，尽管作者认为这是可接受的，但在极大规模的模型训练上可能仍是负担。
*   **超参数微调**：ACs的放置位置和损失权重等引入了一些额外的超参数（尽管作者表示这些参数在不同方法间具有鲁棒性，无需过多微调）。
*   **蒸馏方法的限制**：实验表明（Figure 4d, Table 1），对于某些强依赖于蒸馏（distillation）的方法（如ANCL, LwF, SSIL），ACs带来的收益相对较小。作者推测蒸馏可能抑制了ACs的多样性，从而削弱了其效果。

（完）
