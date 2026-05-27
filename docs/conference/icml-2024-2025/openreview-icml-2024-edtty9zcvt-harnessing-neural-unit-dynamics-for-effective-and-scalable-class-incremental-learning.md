---
title: Harnessing Neural Unit Dynamics for Effective and Scalable Class-Incremental Learning
title_zh: 利用神经单元动态实现高效可扩展的类增量学习
authors: "Depeng Li, Tianqi Wang, Junwei Chen, Wei Dai, Zhigang Zeng"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=eDtty9ZCvt"
tags: ["query:continual"]
score: 9.0
evidence: 基于神经单元动态的类增量学习，可扩展网络扩展
tldr: 本文提出一种基于神经单元动态的连接主义模型，用于类增量学习。在每轮训练中，通过监督机制引导网络扩展，其规模与新任务的内在复杂度相匹配，从而构建接近最小的网络。推理时自动重新激活所需的神经元以检索知识，其余神经元保持不活跃以防止遗忘。实验表明该方法既能有效学习新类，又能保持紧凑的模型大小。该工作为可扩展且抗遗忘的持续学习提供了新架构。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-edtty9zcvt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1625, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-edtty9zcvt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 520, \"height\": 304, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-edtty9zcvt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 900, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-edtty9zcvt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 641, \"height\": 362, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1649, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1259, \"height\": 641, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 541, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1137, \"height\": 415, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 806, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 749, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1354, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1075, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 755, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1009, \"height\": 285, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-edtty9zcvt/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 724, \"height\": 316, \"label\": \"Table\"}]"
motivation: 类增量学习需要从非平稳数据流中学习新类而不遗忘旧类。
method: 提出一种通过神经单元动态调整网络行为的连接主义模型，使用监督机制指导网络扩展。
result: 构建接近最小的网络，推理时自动激活相关单元以保持知识。
conclusion: 为类增量学习提供了一种紧凑且可扩展的解决方案。
---

## Abstract
Class-incremental learning (CIL) aims to train a model to learn new classes from non-stationary data streams without forgetting old ones. In this paper, we propose a new kind of connectionist model by tailoring neural unit dynamics that adapt the behavior of neural networks for CIL. In each training session, it introduces a supervisory mechanism to guide network expansion whose growth size is compactly commensurate with the intrinsic complexity of a newly arriving task. This constructs a near-minimal network while allowing the model to expand its capacity when cannot sufficiently hold new classes. At inference time, it automatically reactivates the required neural units to retrieve knowledge and leaves the remaining inactivated to prevent interference. We name our model AutoActivator, which is effective and scalable. To gain insights into the neural unit dynamics, we theoretically analyze the model’s convergence property via a universal approximation theorem on learning sequential mappings, which is under-explored in the CIL community. Experiments show that our method achieves strong CIL performance in rehearsal-free and minimal-expansion settings with different backbones.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **研究动机**：类增量学习（Class-Incremental Learning, CIL）的核心挑战在于，模型在从非平稳数据流中持续学习新类别时，会灾难性地遗忘先前学到的旧类别知识。现有主流方法存在明显局限：基于回放的方法受限于内存和隐私问题；基于正则化的方法在固定容量模型上难以找到最优解；基于架构的方法则往往导致模型规模随任务数量无节制地增长。
*   **核心问题**：如何在无需存储旧样本（无回放）的前提下，构建一个既能有效学习新知识、又能完全保留旧知识，且模型容量增长能紧凑地适应任务复杂度的可扩展 CIL 方法。
*   **整体含义**：本文受认知神经科学中记忆稳定化机制的启发，提出了一种全新的连接主义模型——AutoActivator。该模型通过设计“神经单元动态”来驱动网络行为，为 CIL 提供了一种理论上收敛、实践中高效且内存开销极低的解决方案。

### 2. 论文提出的方法论

*   **核心思想**：将神经网络组织成可扩展的“神经单元”（一组神经元的集合）。在训练时，通过监督机制动态地、精简地为新任务招募神经元，构建接近最小的网络结构；在推理时，自动激活与当前输入相关的神经单元以检索知识，而让其他单元保持静默，从而从根源上避免新旧任务间的干扰（灾难性遗忘）。
*   **关键技术细节**：
    *   **监督式节点生成与连接 (Supervisory Mechanism)**：在每个训练阶段，随机生成多批候选节点（神经元及其输入权重和偏置）。根据一个特定的不等式条件（公式 7）筛选出能显著降低当前任务残差的候选节点。该条件由**定理 4.2（通用逼近定理）** 支撑，保证了模型在序列学习上的收敛性。只有引起训练误差最大程度降低的那一批节点才会被正式“招募”并连接到对应的神经单元。
    *   **动态逐步更新输出权重**：当新节点被加入后，模型的输出权重通过一个基于矩阵伪逆的分块更新公式（公式 8-10）进行高效计算。该方法无需完整的反向传播重新训练，只需利用旧矩阵和新节点输出即可直接得到最小二乘意义下的最优解，极大提升了训练效率。
    *   **基于激活阈值的推理 (Reactivation)**：在训练阶段，为每个神经单元计算一个“激活阈值”（公式 11），该阈值由该单元对训练样本的预测概率均值决定。在推理时，面对未知任务标识的测试样本，模型会计算每个神经单元在测试样本上的瞬时阈值，并选择与训练阈值最匹配的单元（公式 12）进行激活，利用其输出做出最终预测，实现了任务无关的自动推理。
*   **算法流程**：模型从一个空的或极小的网络开始。对于每个新任务，循环执行“生成候选节点 -> 监督机制筛选 -> 招募最优批次 -> 动态更新输出权重”，直至达到预设的终止条件（如最大节点数或期望精度）。训练完成后，计算并保存该任务神经单元的激活阈值。所有任务依次训练完毕后，模型便具备了自动推理能力。

### 3. 实验设计

*   **数据集与场景**：实验覆盖了从小规模到大规模、从标准到鲁棒性测试的多个数据集，并在不同任务划分下进行评估。
    *   **小规模**：**MNIST**（5任务，每任务2类）和**FashionMNIST**（5任务，每任务2类）。
    *   **中规模**：**CIFAR-100**（10任务，每任务10类 / 25任务，每任务4类）。
    *   **大规模**：**ImageNet-R**（10任务，每任务20类）和**ImageNet-100/1K**。
*   **基准对比方法**：与三大类CIL方法以及最新工作进行广泛比较。
    *   **基于回放**：IL2M, BiC, LOGD, FS-DGPM, RPS-Net, ER, DER++ 等。
    *   **基于正则化**：EWC, SI, MAS, OLEWC 等。
    *   **基于架构**：PCL, DER, FOSTER, RPS-Net, EFT, AOP, CRNet 等。
    *   **基于预训练+提示(Prompt)**：L2P, DualPrompt, CODA-Prompt。
*   **评估指标**：使用**平均分类准确率(ACA)**、**平均增量准确率(AIA)**、**反向迁移(BWT/Forgetting)** 和**对齐内存预算(Memory Budget)** 进行全面评估。

### 4. 资源与算力

*   论文的“附录 C”部分提到，所有实验基于 **PyTorch** 实现，并使用 **NVIDIA RTX 3080-Ti GPU** 进行计算。
*   论文比较了不同方法的训练时间（附录 D.3），例如，在相同条件下，该方法每轮训练耗时约12秒，而其他基于回放的方法（如GEM, LOGD等）耗时在33到333秒之间，显示了本方法在效率上的优势。然而，论文并未明确提及完成所有实验所使用的GPU总数量或总训练时长。

### 5. 实验数量与充分性

*   **实验数量**：论文提供了相当全面的实验验证，大致包括：
    *   **主实验**：在4种主要数据集设定（MNIST, FashionMNIST, CIFAR-100 10/25, ImageNet-R）上与超过20种基线方法进行对比。
    *   **分析与消融实验**：深入分析了监督机制的核心参数（步长*l*和最大生成次数*T_max*）、神经单元的表征学习（t-SNE可视化）、实际扩展配额、激活阈值的两个核心组件的有效性。
    *   **扩展与鲁棒性实验**：包括**非均衡任务序列**、**单类增量学习**和**在线类增量学习**场景下的性能，以及**模型可扩展性**（内存随任务增长曲线）的分析。
*   **充分性与公平性**：
    *   **充分性**：实验设计由浅入深（从小数据集到大数据集，从标准划分到非均衡/在线设定），并从准确性、遗忘率、内存开销、计算效率等多个维度进行了评估，非常全面。
    *   **公平性**：论文遵循了CIL领域的公平比较建议，将模型大小和回放缓冲区统一折算为“内存预算”进行比较。所有比较方法都经过仔细复现或参考了其最佳设定，并允许在冻结或微调预训练骨干网络中选择最佳结果，确保了比较的客观和公正。

### 6. 论文的主要结论与发现

*   AutoActivator 在**无回放**和**最小化网络扩展**的严苛设定下，在多个数据集上取得了**最先进的CIL性能**，在准确率上显著超越了包括基于回放、正则化和架构的方法，以及最新的基于提示的方法。
*   该方法具有**近乎为零的灾难性遗忘**（BWT接近0），其设计的神经单元完全隔离机制本质上是抗遗忘的。
*   通过监督机制，模型的**网络扩展规模能够自然地与任务的固有复杂度相匹配**，构建了一个非常紧凑的模型，其最终内存预算甚至优于部分非扩展的固定网络方法。
*   **激活阈值机制**是实现任务无关推理的关键，它有效地校正了不同任务神经单元间的类别混淆。
*   理论上的**收敛性证明**为模型的可靠性和有效性提供了坚实保障。

### 7. 优点

*   **方法新颖且理论扎实**：从神经单元动态的全新视角解决CIL问题，并用通用逼近定理为模型收敛性提供了理论保证，这在CIL领域较为少见。
*   **完美平衡了有效性与效率**：实现了无回放、高精度、低遗忘和极低模型增长率的最佳组合，在准确率和内存预算上达到了优异的权衡。
*   **即插即用的潜力**：该方法可以作为一个通用的CIL分类器，注入到不同的先进骨干网络（如ResNet, ViT）中，并可与现有的提示学习方法（如DualPrompt）结合以带来进一步提升。
*   **任务顺序鲁棒性强**：多次不同任务顺序的实验结果标准差很小，表明方法性能稳定可靠。

### 8. 不足与局限

*   **训练时依赖任务边界**：方法假设在训练阶段有明确的任务划分（Task Boundary），连续接收一个任务的所有数据。这在某些真正的在线流式数据场景中可能是一个限制性假设。
*   **矩阵运算的可扩展性**：尽管论文声称可扩展，但其核心的动态逐步更新算法涉及矩阵伪逆和乘法运算。当神经单元和输出类别数量变得极大时，这些矩阵运算本身的计算成本和内存占用可能成为新的瓶颈，论文对此讨论不足。
*   **超参数敏感性**：方法引入了如最大随机生成次数（\(T_{max}\)）、步长（\(l\)）等特定超参数。尽管论文分析了它们的影响，但在不同规模和特性的数据集上，这些参数可能需要繁琐的调整，且其最优值可能依赖于经验。
*   **偏差与公平性风险**：论文承认，当使用预训练骨干网络时，原模型中可能存在的偏差和公平性问题会延续到CIL过程中，这需要使用者额外注意和审查。

（完）
