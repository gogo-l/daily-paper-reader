---
title: Improving Continual Learning Performance and Efficiency with Auxiliary Classifiers
title_zh: 利用辅助分类器提升持续学习性能与效率
authors: "Filip Szatkowski, Yaoyue Zheng, Fei Yang, Tomasz Trzcinski, Bartłomiej Twardowski, Joost van de Weijer"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=sq5eL4jfsn"
tags: ["query:continual"]
score: 8.0
evidence: 利用辅助分类器提高持续学习方法的性能和效率
tldr: 本文发现持续学习中的神经网络中间层表示更不易遗忘，据此提出利用辅助分类器来提升持续学习性能与效率，将其集成到多种CL方法中，在多种评估设置下一致地提高了准确率并降低了计算开销，提供了一种即插即用的增强技术。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 839, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1668, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1759, \"height\": 332, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1767, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 798, \"height\": 605, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 844, \"height\": 292, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 847, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 845, \"height\": 291, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1757, \"height\": 882, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1759, \"height\": 879, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1750, \"height\": 1111, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1750, \"height\": 1106, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1748, \"height\": 1106, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1764, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1755, \"height\": 1765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1747, \"height\": 1105, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1761, \"height\": 1322, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1747, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1203, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1201, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1200, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1200, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1200, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1200, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1200, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1201, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1200, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1200, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1199, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1755, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1753, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1755, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1761, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1762, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1763, \"height\": 334, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1768, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1768, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1768, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 446, \"height\": 335, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1413, \"height\": 2024, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1415, \"height\": 2062, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1761, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 1759, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-044.webp\", \"caption\": \"\", \"page\": 0, \"index\": 44, \"width\": 1760, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-sq5el4jfsn/fig-045.webp\", \"caption\": \"\", \"page\": 0, \"index\": 45, \"width\": 1756, \"height\": 458, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1782, \"height\": 711, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1784, \"height\": 466, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1770, \"height\": 254, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1492, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1781, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1782, \"height\": 394, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1779, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1782, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1783, \"height\": 431, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1783, \"height\": 510, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1081, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1783, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-sq5el4jfsn/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1782, \"height\": 1515, \"label\": \"Table\"}]"
motivation: 持续学习中的灾难性遗忘问题依然严重，需要新思路提升方法效果。
method: 通过分析中间层表示，提出在多种CL方法中集成辅助分类器。
result: 辅助分类器一致提升了准确率，并加速了计算。
conclusion: 辅助分类器为持续学习方法提供了一种简单有效的性能增强途径。
---

## Abstract
Continual learning is crucial for applying machine learning in challenging, dynamic, and often resource-constrained environments. However, catastrophic forgetting — overwriting previously learned knowledge when new information is acquired — remains a major challenge. In this work, we examine the intermediate representations in neural network layers during continual learning and find that such representations are less prone to forgetting, highlighting their potential to accelerate computation. Motivated by these findings, we propose to use auxiliary classifiers~(ACs) to enhance performance and demonstrate that integrating ACs into various continual learning methods consistently improves accuracy across diverse evaluation settings, yielding an average 10\% relative gain. We also leverage the ACs to reduce the average cost of the inference by 10-60\% without compromising accuracy, enabling the model to return the predictions before computing all the layers. Our approach provides a scalable and efficient solution for continual learning.

---

## 论文详细总结（自动生成）

好的，这是对论文《Improving Continual Learning Performance and Efficiency with Auxiliary Classifiers》的结构化、深入、客观的总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：持续学习（Continual Learning, CL）面临的主要挑战是**灾难性遗忘（Catastrophic Forgetting）**，即模型在学习新任务时会覆盖先前学到的知识。如何在提升模型抗遗忘能力的同时，保证计算效率，尤其是在资源受限的动态环境中，是一个关键难题。
*   **整体含义**：本文旨在桥接持续学习和高效推理两个研究领域。其核心发现是，在持续学习中，神经网络**中间层的表示比最终层更稳定、更不易遗忘**。基于此，作者提出通过集成**辅助分类器（Auxiliary Classifiers, ACs）** 来同时提升现有持续学习方法的性能（准确率）和效率（推理速度），将其作为一种通用、即插即用的增强方案。

### 2. 论文提出的方法论

*   **核心思想**：在深度神经网络的多个中间层上添加轻量级的辅助分类器。由于中间层表示对旧知识遗忘更少，这些辅助分类器能够对最终分类器预测失败的样本做出正确分类，从而提升整体系统性能。同时，这允许进行“提前退出”（Early Exit），显著降低推理计算开销。
*   **关键技术细节**：
    *   **辅助分类器（ACs）设计**：在主干网络 `f = fN(...(f1(x)))` 的多个中间子模块 `f1, f2, ..., fN-1` 之后，添加 `N-1` 个辅助分类器 `ĝi`。ACs 由一个池化层和一个全连接层构成。
    *   **静态推理（Static Inference）规则**：模型计算出所有分类器（所有辅助分类器+最终分类器）的预测概率分布，最终选择**置信度最高**的预测作为输出。
    *   **动态推理（Dynamic Inference）规则**：允许模型提前退出以节省计算。在推理时，按顺序计算从浅到深的分类器预测。若某个分类器的最大预测置信度超过预设阈值 `λ`，则立即返回该预测。若所有分类器均未达到阈值，则回退到**静态推理**规则。这被称为“基于最大置信度”的推理范式，区别于传统早退方法中“默认使用最后分类器”的做法。
    *   **训练方法**：采用端到端训练，并允许梯度在所有分类器之间回传。为防止网络过度拟合到早期分类器，会根据分类器在网络中的位置（计算量占比）对其损失进行加权，位置越浅，损失权重越小。

### 3. 实验设计

*   **数据集**：
    *   **CIFAR100**：标准图像分类基准。
    *   **ImageNet100**：从 ImageNet 中选取的前 100 类。
*   **场景与划分**：
    *   **标准类增量学习（Class-Incremental Learning）**：将数据集分为 5 或 10 个互不相交的任务。
    *   **Warm-start 持续学习**：首个任务包含 50 个类（模拟预训练），剩余类分为 5 或 10 个任务。
    *   **长序列任务**：将 CIFAR100 分为 20 或 50 个任务。
*   **对比基准方法（CL methods）**：作者将 ACs 集成到共计 11 种不同类型的持续学习方法中，覆盖了正则化、回放、参数隔离等多个类别。
    *   **Finetuning（FT/FT+Ex）**：朴素微调及其带样本回放的版本。
    *   **正则化类**：LwF、EWC、ANCL。
    *   **回放类**：ER、DER++、GDUMB、LODE。
    *   **其他**：BiC、SSIL。
*   **网络架构**：
    *   **残差网络（ResNet）**：ResNet32（用于 CIFAR100），ResNet18（用于 ImageNet100）。
    *   **VGG**：VGG19（用于 CIFAR100），评估更深网络。
    *   **视觉Transformer（ViT）**：ViT-base（用于 ImageNet100），评估与大型模型的兼容性。
    *   **宽残差网络（WideResNet）**：WideResNet16-2（用于 CIFAR100），评估对宽度的敏感性。

### 4. 资源与算力

*   论文**未明确提及**实验所使用的具体 GPU 型号、数量或总训练时长。
*   文章仅在致谢部分提到使用了波兰 PLGrid 高性能计算基础设施（HPC Center: ACK Cyfronet AGH），并给出了计算拨款的编号。此外，提供了关于训练时间和峰值GPU内存的开销分析表（附录 B），可以作为对算力需求的参考。例如，在基座模型最小的 ResNet32 上，标准 6 个 ACs 的设置相比基线增加了约 50% 的训练时间和 10% 的峰值显存占用，这是报告中显存和算力开销增加最多的场景。

### 5. 实验数量与充分性

*   **实验数量巨大，覆盖面广**。论文包含约 70 组以上的主要实验和消融实验，从其大量的图表和表格即可看出其实验的规模。
*   **充分性与客观性**：
    *   **多维度验证**：实验覆盖了（1）**多个数据集**，（2）**多种任务划分**（5/10/20/50 任务 + warm-start），（3）**多种代表性的 CL 方法**（总计 11 种），以及（4）**多种深度学习架构**（CNN、ViT）。这种交叉验证的设计非常全面，强有力地证明了方法的鲁棒性和通用性。
    *   **公平性**：在将 ACs 集成到现有方法时，作者保持了原有方法的所有超参数不变，仅添加了 ACs 及其相关损失，这确保了对比的公平性。所有回放类方法均使用固定的 2000 个样本的内存预算。
    *   **全面的消融与分析**：不仅展示了最终结果，还深入分析了（1）表示稳定性（CKA），（2）单个 AC 的判别力，（3）过度思考（Overthinking）现象，（4）AC 网络架构、数量和位置的影响，（5）端到端训练 vs. 线性探测的对比，（6）动态推理阈值的影响等。这些分析为方法的有效性提供了有力的内在解释。

### 6. 论文的主要结论与发现

*   **中间层表示更稳定**：在持续学习中，网络浅层/中间层的特征表示相较于深层/最终层变化更小，表现出更强的抗遗忘能力。
*   **辅助分类器（ACs）能提升性能**：将 ACs 集成到任何 CL 方法中，几乎都能一致地提升最终的分类准确率。在 CIFAR100 和 ImageNet100 上，平均相对性能提升超过 10%，尤其对朴素微调和简单的正则化方法（如 EWC）增益显著。
*   **ACs 能提升效率**：通过动态推理，AC 增强的模型可以在仅使用 40%–60% 计算量的情况下，达到与原始完整模型相当的准确率。即使在损失无损的情况下，也能节省 10-20% 的推理计算量。
*   **可扩展性**：ACs 方法对更深、更宽的网络（VGG19, ViT）同样有效，甚至增益更大，表现出良好的可扩展性。

### 7. 优点

*   **分析深入且具有启发性**：通过对“过度思考（Overthinking）”现象的量化，深刻揭示了为什么 ACs 在 CL 场景中特别有效，而不仅仅是推理加速工具。
*   **方法通用且即插即用**：提出的方法可以无缝集成到绝大多数现有 CL 方法中，无需调整原有方法的超参数或改变其核心逻辑，易用性极强。
*   **双重收益**：同时提升了持续学习模型的准确率和推理效率，这是该领域一个非常有价值的特性。
*   **评估极其扎实**：实验设计全面、系统，从多个维度（方法、架构、任务划分）证明了方法的有效性，并配有详尽的消融研究和机理分析，结论可信度高。

### 8. 不足与局限

*   **训练开销增加**：尽管推理可以加速，但引入 ACs 会增加训练过程中的计算量和显存占用（尤其在较小模型中相对开销更明显），论文语言中确认了这一点。
*   **研究模态单一**：所有实验均面向**计算机图像分类**任务，其结论在其他模态（如 NLP、语音）或任务（如目标检测、分割）上的适用性有待验证。
*   **AC 设计缺乏自适应**：AC 的位置、数量和权重等设计选择目前是预设的，可能需要针对特定任务和架构进行调整以获得最佳效果。虽然论文显示性能对参数不敏感，但最优设置依然可能存在。
*   **动态推理依赖阈值**：动态推理的性能增益依赖于置信度阈值的设定，尽管实验表明其不敏感，但在实际部署中仍需校准。

（完）
