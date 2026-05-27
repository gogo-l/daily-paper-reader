---
title: Provable Contrastive Continual Learning
title_zh: 可证明的对比持续学习
authors: "Yichen Wen, Zhiquan Tan, Kaipeng Zheng, Chuanlong Xie, Weiran Huang"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=V3ya8RlbrW"
tags: ["query:continual"]
score: 9.0
evidence: 对比持续学习的理论保证
tldr: 该研究针对对比持续学习框架缺乏理论解释的问题，建立了理论性能保证，揭示了模型性能受先前任务训练损失约束的机制。理论分析表明预训练有助于持续学习，并据此提出一种新的对比学习方法。实验验证了理论的有效性，为对比持续学习提供了坚实的理论基础。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-v3ya8rlbrw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1753, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-v3ya8rlbrw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 690, \"height\": 515, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-v3ya8rlbrw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1778, \"height\": 685, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-v3ya8rlbrw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 693, \"height\": 277, \"label\": \"Table\"}]"
motivation: 现有对比持续学习框架缺乏理论解释。
method: 建立理论性能保证，揭示对比持续学习中模型性能如何受先前任务训练损失约束，并提出新对比学习方法。
result: 理论解释揭示预训练可助益持续学习，为对比持续学习提供支撑。
conclusion: 为对比持续学习提供了理论依据，并推动了方法改进。
---

## Abstract
Continual learning requires learning incremental tasks with dynamic data distributions. So far, it has been observed that employing a combination of contrastive loss and distillation loss for training in continual learning yields strong performance. To the best of our knowledge, however, this contrastive continual learning framework lacks convincing theoretical explanations. In this work, we fill this gap by establishing theoretical performance guarantees, which reveal how the performance of the model is bounded by training losses of previous tasks in the contrastive continual learning framework. Our theoretical explanations further support the idea that pre-training can benefit continual learning. Inspired by our theoretical analysis of these guarantees, we propose a novel contrastive continual learning algorithm called CILA, which uses adaptive distillation coefficients for different tasks. These distillation coefficients are easily computed by the ratio between average distillation losses and average contrastive losses from previous tasks. Our method shows great improvement on standard benchmarks and achieves new state-of-the-art performance.

---

## 论文详细总结（自动生成）

好的，以下是基于所提供的论文内容生成的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **研究背景**：持续学习（Continual Learning）要求模型在学习一系列增量任务时，能够平衡对新任务的学习能力（可塑性）与对旧知识的记忆能力（稳定性），避免灾难性遗忘。
*   **核心问题**：当前，结合对比损失（Contrastive Loss）和蒸馏损失（Distillation Loss）的对比持续学习框架在实践中表现出色，但缺乏令人信服的理论解释来阐明其为何有效。
*   **研究动机与目标**：本工作旨在填补这一理论空白，为对比持续学习框架建立理论性能保证，揭示其工作机制，并基于理论洞察提出性能更优的新算法。

### 2. 论文提出的方法论

*   **核心思想**：为对比持续学习框架建立理论保证，证明最终模型在所有已见任务上的总体测试性能可以被一系列任务上的训练损失所限定。
*   **关键理论分析**：
    *   **引理 1**：建立了连续两个模型（`ft` 和 `ft-1`）在任意数据分布上的对比损失之间的关系，该关系通过蒸馏损失来连接。
    *   **定理 1**：推导了最终模型`fT`的测试损失上界和下界。该界可以表示为一个线性组合，由首任务训练损失和后续各任务的训练损失（包含对比损失和蒸馏损失）加权求和组成。权重系数与蒸馏系数λ、任务权重`k`和任务顺序有关。
    *   **推论与洞察**：
        *   理论表明，最小化每个任务阶段的训练损失对于提升最终模型性能是必要且有效的。
        *   分析从理论上支持了“预训练有益于持续学习”的观点：初始任务的训练性能对最终模型整体性能的影响权重要大于后续任务。
*   **提出算法：CILA（Contrastive Incremental Learning with Adaptive distillation）**
    *   **技术细节**：受理论分析启发，特别是蒸馏系数`λ`的选择对性能界限的影响，提出了自适应调整蒸馏系数的算法。
    *   **自适应策略**：对于任务`t`，其蒸馏系数`λt`不再固定为常数，而是根据历史任务的**平均蒸馏损失与平均对比损失的比值**进行动态计算。具体公式为：
        `λt = max(1, κ * (∑_{j=2}^{t-1} L_dis(fj) / ∑_{j=2}^{t-1} L_con(fj)))`，其中`κ`是平衡系数。从任务3开始自适应调整，任务2的`λ`为1。
    *   **算法流程**：
        1.  初始化模型和缓冲区。
        2.  对于每个新任务，构建包含当前任务数据和缓冲区数据的训练集。
        3.  如果任务数大于1，则根据上述公式自适应计算当前任务的蒸馏系数`λt`。
        4.  计算总损失：对比损失 + `λt` * 蒸馏损失。
        5.  更新模型并管理缓冲区样本。

### 3. 实验设计

*   **数据集与场景**：
    *   **Seq-CIFAR-10**：源自CIFAR-10，划分为5个任务，用于 **Class-IL（类增量学习）** 和 **Task-IL（任务增量学习）** 场景。
    *   **Seq-Tiny-ImageNet**：源自Tiny-ImageNet，划分为10个任务，用于 **Class-IL** 和 **Task-IL** 场景。
    *   **R-MNIST**：源自MNIST的变体，图像随机旋转，包含20个任务，用于 **Domain-IL（域增量学习）** 场景。
*   **对比基准（Baselines）**：
    *   与多种回放（Replay）基线方法进行了对比，包括 **ER, GEM, A-GEM, iCaRL, FDR, GSS, HAL, DER, DER++**，以及当前最先进的对比持续学习方法 **Co²L**。
*   **评估与细节**：
    *   模型架构：Seq-CIFAR-10和Seq-Tiny-ImageNet使用ResNet-18，R-MNIST使用简单卷积网络。
    *   缓冲区大小：200 和 500 两种设置。
    *   训练方式：遵循Co²L的“先预训练表征，后线性探测”策略。
    *   评测指标：在所有已见任务上训练线性分类器后的分类准确率。

### 4. 资源与算力

*   **文中未提及**：所提供的论文内容中，没有明确说明实验所使用的GPU型号、数量或具体训练时长。

### 5. 实验数量与充分性

*   **实验数量**：
    *   **主实验**：在3个数据集、2种缓冲区大小、3种持续学习场景（Seq-CIFAR-10和Seq-Tiny-ImageNet各有Class-IL/Task-IL，R-MNIST为Domain-IL）下，与10种基线方法进行了性能对比。所有结果均在10次独立试验上取平均值并报告标准差。
    *   **消融实验**：在Seq-CIFAR-10（缓冲区200）的Class-IL和Task-IL场景下，设计了3种`λt`的变体（纯自适应、最小自适应、最大自适应）进行对比，以验证自适应蒸馏系数的有效性。
*   **实验充分性与公平性**：
    *   **充分性**：实验覆盖了主要的持续学习场景、标准和常用数据集以及多种基线方法，并包含了消融研究来验证所提出核心组件的效果，整体设计较为充分。
    *   **公平性**：与基线方法的对比遵循了统一的训练和评估协议（如“预训练-线性探测”），并通过多次试验报告均值和标准差，确保了对比的客观性与公平性。

### 6. 论文的主要结论与发现

1.  **理论保证**：成功为对比持续学习框架建立了理论性能界限，揭示了最终模型性能受先前任务训练损失约束的机制。
2.  **预训练的重要性**：理论分析表明，在对比持续学习中，初始任务的训练效果对最终性能至关重要，这为预训练的价值提供了理论支撑。
3.  **算法有效性**：基于理论指导提出的CILA算法，通过自适应调整蒸馏系数，在所有测试的基准、场景和缓冲区大小上均超越了所有基线方法，尤其在Class-IL场景下对先前SOTA方法Co²L有显著提升（例如，在Seq-CIFAR-10上缓冲区500时提升了约1.77%）。

### 7. 优点

*   **理论创新**：为经验上成功的对比持续学习框架首次提供了理论性能保证，弥补了领域空白。
*   **理论与实践结合**：不仅停留在理论分析，还基于理论洞察（`λ`系数的影响）设计出实用且有效的算法CILA，实现了理论与实践的良性互动。
*   **方法简洁有效**：CILA的自适应蒸馏系数计算方法简单，易于实现，且能带来显著的性能提升。
*   **实验扎实**：在多种标准场景、数据集和缓冲区配置下进行了全面的实验验证和消融研究，结果具有说服力。

### 8. 不足与局限

*   **资源消耗未明**：论文未提供任何关于实验所需算力资源的信息，使得其他研究者难以评估和复现其计算成本。
*   **蒸馏系数设计的局限**：自适应`λt`的计算策略虽然有效，但可能并非全局最优。该策略主要基于经验和理论趋势的启发，且其性能可能对平衡系数`κ`敏感。
*   **实验设定限制**：所有实验均在相对小规模的数据集（如CIFAR-10， Tiny-ImageNet， MNIST）上进行。该方法在大规模数据集或更复杂的持续学习场景下的有效性和可扩展性尚未得到验证。
*   **理论假设**：理论分析基于特定的对比损失（带一个或k个负样本）和蒸馏损失公式，其结论向其他形式的对比学习或知识蒸馏方法的推广性可能存在限制。
*   **应用限制**：该框架采用“先预训练表征，后训练线性分类器”的策略，这与端到端联合训练分类头和表征的主流范式不同，可能在某些应用场景下不直接适用。

（完）
