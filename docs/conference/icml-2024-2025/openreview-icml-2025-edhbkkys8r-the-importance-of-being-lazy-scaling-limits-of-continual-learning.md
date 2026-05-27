---
title: "The Importance of Being Lazy: Scaling Limits of Continual Learning"
title_zh: 懒惰的重要性：持续学习的规模极限
authors: "Jacopo Graldi, Alessandro Breccia, Giulia Lanzillotta, Thomas Hofmann, Lorenzo Noci"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=edhBkkYS8R"
tags: ["query:continual"]
score: 8.0
evidence: 研究模型规模与特征学习对持续学习中灾难性遗忘的影响
tldr: 针对持续学习中模型规模影响存在矛盾观察的问题，系统研究规模与特征学习对灾难性遗忘的影响，区分懒惰与丰富训练模式，表明增宽仅当减少特征学习时才有益。利用动态平均场理论分析无限宽动态，为扩展神经网络减轻遗忘提供理论指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 761, \"height\": 820, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 834, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 806, \"height\": 866, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 809, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 1069, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1765, \"height\": 1008, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1775, \"height\": 1097, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1774, \"height\": 1100, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1434, \"height\": 1068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 870, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1060, \"height\": 652, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1770, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1767, \"height\": 531, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1764, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1766, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1768, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1768, \"height\": 555, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1779, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1070, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1068, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1059, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1061, \"height\": 576, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-edhbkkys8r/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 890, \"height\": 438, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-edhbkkys8r/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 372, \"label\": \"Table\"}]"
motivation: 现有研究对持续学习中模型规模影响存在矛盾观察。
method: 通过可变参数化架构区分懒惰与丰富训练模式，并使用动态平均场理论分析。
result: 增加模型宽度仅在减少特征学习时有助于持续学习。
conclusion: 揭示了模型扩展对持续学习的条件性益处。
---

## Abstract
Despite recent efforts, neural networks still struggle to learn in non-stationary environments, and our understanding of catastrophic forgetting (CF) is far from complete.
In this work, we perform a systematic study on the impact of model scale and the degree of feature learning in continual learning. We reconcile existing contradictory observations on scale in the literature, by differentiating between *lazy* and *rich* training regimes through a variable parameterization of the architecture. We show that increasing model width is only beneficial when it reduces the amount of *feature learning*, yielding more laziness. Using the framework of dynamical mean field theory, we then study the infinite width dynamics of the model in the feature learning regime and characterize CF, extending prior theoretical results limited to the lazy regime. We study the intricate relationship between feature learning, task non-stationarity, and forgetting, finding that high feature learning is only beneficial with highly similar tasks. We identify a transition modulated by task similarity where the model exits an effectively lazy regime with low forgetting to enter a rich regime with significant forgetting. Finally, our findings reveal that neural networks achieve optimal performance at a critical level of feature learning, which depends on task non-stationarity and *transfers across model scales*. This work provides a unified perspective on the role of scale and feature learning in continual learning.

---

## 论文详细总结（自动生成）

好的，请查收以下基于所提供论文内容生成的结构化总结。

# 《懒惰的重要性：持续学习的规模极限》论文总结

### 1. 论文的核心问题与整体含义

*   **核心问题**：该论文旨在解决持续学习领域中，关于**模型规模（如宽度）如何影响灾难性遗忘**这一问题上存在的相互矛盾的观察结果。一些研究发现扩大模型能减少遗忘，另一些则不然。
*   **研究动机**：现代神经网络在非稳态环境下学习时，依然面临严峻的灾难性遗忘挑战。尽管已有理论工作，但它们大多局限于固定的“懒惰”训练状态，无法解释实际应用中普遍存在的“丰富”特征学习动态。因此，亟需一个统一的理论框架来阐明规模、特征学习与遗忘之间的本质关系。
*   **整体含义**：论文的核心论点是，**模型规模本身并非减少遗忘的关键，真正决定性因素是训练动态是“懒惰”还是“丰富”**。增加模型宽度只有在促进了“懒惰”学习（即减少特征演化）时才对持续学习有益。研究揭示了特征学习、任务非平稳性与遗忘之间复杂的非线性关系，并强调了在持续学习中，“懒惰”的重要性。

### 2. 论文提出的方法论

*   **核心思想**：通过在架构的参数化中引入可变因子 \(\gamma_0\)，平滑地在**两种标准的无限宽网络缩放极限**之间进行插值：
    *   **神经正切参数化 (NTP)** / 懒惰状态：\(\gamma_0 \to 0\)，特征在训练中几乎不变，网络等价于一个线性模型。
    *   **最大更新参数化 (\(\mu P\))** / 丰富状态：\(\gamma_0 = 1\)，在任意规模下都保持显著的特征学习。
*   **关键技术细节**：
    *   \(\gamma_0\) 通过缩放网络的输出层和学习率，**控制了特征学习的程度**，从而可以在一个连续谱上研究从“懒惰”到“丰富”的动态变化。
    *   **动态平均场理论 (DMFT) 扩展**：将 DMFT 框架从稳态训练推广到**多任务序列训练**的非稳态场景，提出了**命题 4.1**。该命题证明，在无限宽极限下，网络内部状态（如预激活值）的演化可以由一个自洽的随机过程描述，其关键变量（如特征核、梯度核）会收敛到其期望值，从而可以精确模拟遗忘动态。
*   **关键公式**：定义跨任务的神经正切核 (NTK) \(K_{\alpha_i\beta_j}(t)\)，遗忘的动态直接由它和预测残差 \(\Delta\) 的乘积决定。\(\gamma_0\) 项在动态方程中表现为特征学习修正项，当 \(\gamma_0 \to 0\) 时，该修正项消失，系统退化为已知的懒惰状态。

### 3. 实验设计

*   **数据集/场景**：
    *   **主要视觉任务**：Split-CIFAR10（任务增量学习）、Split-TinyImagenet（不同任务数和每任务类别数）、Permuted-MNIST（通过像素置换程度控制任务相似度）。
    *   **简化模拟任务**：在 Permuted-MNIST 的一个小型子集（30个样本）上训练一个两层非线性MLP，用于验证无限宽理论模拟。
*   **Benchmark 与对比方法**：
    *   对比了 **NTP 和 \(\mu P\) 两种参数化**在宽度缩放时对遗忘的影响。
    *   在 \(\mu P\) 框架下，系统地改变 \(\gamma_0\) 值，研究不同特征学习程度下的行为。
    *   在有限宽度网络上进行实验，并与基于**DMFT的无限宽理论模拟结果**进行对比。
*   **评估指标**：除了传统的遗忘指标，作者引入了**灾难性遗忘率 (CFr)**，即准确率的相对下降，以更公平地比较不同性能水平的模型。

### 4. 资源与算力

*   **GPU 型号**：所有训练和实验在 **单个 NVIDIA GeForce RTX 4090 或 NVIDIA RTX A6000** GPU 上执行。
*   **其他细节**：论文未提及使用的 GPU 总数量、单次训练的耗时，或完成所有实验的总体计算时长。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了大量、多维度的实验，涵盖：
    *   **多个数据集**：3个主要图像数据集（CIFAR10, TinyImagenet, MNIST）。
    *   **多种模型架构**：ResNet、CNN 和 MLP。
    *   **不同缩放维度**：对宽度、深度以及两者在不同参数化下的组合进行了消融研究。
    *   **多维度参数扫描**：系统性地扫描了宽度（64 到 4096）、\(\gamma_0\) 值（\(10^{-3}\) 到 \(10^0\)）、任务相似度、训练时长等关键变量。
    *   **理论与实证结合**：将有限宽度的实证结果与无限宽理论模型的模拟结果进行对照，相互印证。
*   **充分性与客观性**：实验设计**非常充分且系统**。它通过控制变量法，逐一解耦并研究了参数化、宽度、特征学习强度、任务相似度等关键因素对遗忘的独立和交互影响。新的评估指标 CFr 的提出也增强了比较的客观性。对相关文献中矛盾的实验条件（如训练时长）进行了复现和解释，体现了较强的客观性。

### 6. 论文的主要结论与发现

*   **宽度缩放效果取决于参数化**：在 NTP（懒惰）下增宽可减少遗忘，但在 \(\mu P\)（丰富）下则不行，解释了以往研究的矛盾。
*   **“懒惰-丰富转变 (LRT)”**：存在一个关于 \(\gamma_0\) 的非线性过渡区域。低于此区域，网络处于“有效懒惰”状态，遗忘率低；高于此区域，特征演化急剧增加，遗忘率显著升高。
*   **存在最优特征学习程度 \(\gamma^*_0\)**：在非稳态环境下，性能随 \(\gamma_0\) 增加呈 U 型曲线，**最佳塑性与稳定性权衡在中等偏低的 \(\gamma^*_0\) 值达到**，并且此最优值可以跨模型宽度迁移。
*   **高任务相似度推迟 LRT**：任务相似度越高，特征演化越少，“懒惰-丰富转变”点 \(\gamma_{LRT}\) 和最优特征学习点 \(\gamma^*_0\) 都向 1 移动（即更偏向丰富学习）。反之，在高度非平稳场景下，懒惰性至关重要。
*   **预训练效应**：当任务间相似度极高时，出现了先学任务作为“预训练”减少后续任务特征演化的现象，此时增宽又变得有益，再现了先前研究的观察。

### 7. 优点

*   **统一的理论视角**：通过引入“懒惰-丰富”训练机制这一核心概念，成功地调和了持续学习领域中关于模型规模影响的矛盾观察，提供了一个统一且深刻的解释框架。
*   **理论与实证的紧密结合**：将 DMFT 理论扩展到非稳态学习场景是一项重要的理论贡献，并且该理论预测得到了有限宽度实验的精确验证，大大增强了结论的可信度。
*   **方法论的创新**：巧妙地利用 \(\mu P\) 框架中的 \(\gamma_0\) 参数进行受控实验，实现了对“特征学习程度”这一抽象概念的精细量化研究。
*   **实用的洞察**：发现最优特征学习程度 \(\gamma^*_0\) 可以跨宽度迁移，这为模型调优提供了实际指导，即可以在小模型上找到最佳的 \(\gamma_0\)，然后将其应用于大模型。

### 8. 不足与局限

*   **资源与算力信息不全**：论文未提供 GPU 数量和总训练时长等详细算力消耗数据，使得难以评估其研究的经济成本和可行性。
*   **理论模型的简化**：用于无限宽模拟的理论模型仅限于**两层非线性MLP**，并在小型数据集上进行，其结论向更深、更复杂的架构（如文中实验所用的 ResNet）的泛化性需要通过更复杂的理论或实验进一步证明。
*   **主要关注宽度缩放**：虽然论文对深度缩放进行了初步讨论，但其核心理论和大部分实验都围绕模型宽度展开。对深度缩放规律的完整刻画尚需未来工作。
*   **特征学习度量依赖代理指标**：文中使用 CKA 相似度作为特征演化的代理度量，这种度量虽然是标准做法，但可能无法完全捕捉关于任务遗忘的所有特征变化。
*   **特定架构与优化器**：结论主要在 ResNet 和简单的 CNN/MLP 架构及 SGD 优化器下验证，其向 Transformer 等现代主流架构和 Adam 等优化器的推广仍有待研究。

（完）
