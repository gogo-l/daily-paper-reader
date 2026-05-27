---
title: "TreeLoRA: Efficient Continual Learning via Layer-Wise LoRAs Guided by a Hierarchical Gradient-Similarity Tree"
title_zh: TreeLoRA：通过层次梯度相似树引导的逐层低秩适配器实现高效持续学习
authors: "Yu-Yang Qian, Yuan-Ze Xu, Zhen-Yu Zhang, Peng Zhao, Zhi-Hua Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=f6ibJCQfH4"
tags: ["query:continual"]
score: 9.0
evidence: 利用低秩适配器和梯度相似树实现高效持续学习
tldr: 随着基础模型规模增大，持续学习的效率成为瓶颈。TreeLoRA提出了一种基于K-D树的逐层低秩适配器方法。通过构建层次梯度相似树指导适配器的分配与组合，以极低的参数量实现新任务学习并有效防止灾难性遗忘。实验表明，TreeLoRA在流式数据持续学习任务上显著降低了内存和计算开销，同时保持了与全量微调相当的性能，为大规模预训练模型的在线持续学习提供了高效解决方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 619, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1747, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 626, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 859, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1769, \"height\": 426, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-f6ibjcqfh4/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1748, \"height\": 725, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1042, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 862, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1773, \"height\": 699, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 525, \"height\": 249, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 818, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 633, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1773, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 717, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1599, \"height\": 201, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1755, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 546, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1749, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-f6ibjcqfh4/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1342, \"height\": 209, \"label\": \"Table\"}]"
motivation: 大规模预训练模型在流式数据持续学习中面临高计算成本与灾难性遗忘。
method: 构建层次梯度相似树，引导逐层分配和组合低秩适配器（LoRA）实现高效持续学习。
result: 实验证明TreeLoRA以极少参数实现高性能，显著降低遗忘和计算开销。
conclusion: 分层低秩适配为大规模模型在线持续学习提供高效可行方案。
---

## Abstract
Many real-world applications collect data in a streaming environment, where learning tasks are encountered sequentially. This necessitates *continual learning* (CL) to update models online, enabling adaptation to new tasks while preserving past knowledge to prevent catastrophic forgetting. Nowadays, with the flourish of *large pre-trained models* (LPMs), *efficiency* has become increasingly critical for CL, due to their substantial computational demands and growing parameter sizes. In this paper, we introduce TreeLoRA (K-D Tree of Low-Rank Adapters), a novel approach that constructs *layer-wise* adapters by leveraging hierarchical gradient similarity to enable efficient CL, particularly for LPMs. To reduce the computational burden of task similarity estimation, we employ *bandit* techniques to develop an algorithm based on lower confidence bounds to efficiently explore the task structure. Furthermore, we use sparse gradient updates to facilitate parameter optimization, making the approach better suited for LPMs. Theoretical analysis is provided to justify the rationale behind our approach, and experiments on both *vision transformers* (ViTs) and *large language models* (LLMs) demonstrate the effectiveness and efficiency of our approach across various domains, including vision and natural language processing tasks.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究动机**：许多现实应用以流式数据形式在线收集数据，模型需要**持续学习（Continual Learning, CL）**，即按顺序适应新任务，同时保留旧知识以避免**灾难性遗忘**。
*   **核心挑战**：随着**大预训练模型（LPMs）**（如视觉Transformer、大语言模型）的盛行，CL的**效率**问题愈发突出，因为LPMs计算成本高、参数量巨大。现有CL方法（如重放、正则化）往往计算复杂度与任务数量线性相关，不适用于LPMs的持续微调。
*   **整体含义**：提出一种高效持续学习方法，利用任务间的层次相似结构，在不线性依赖任务数的前提下快速适应新任务并减缓遗忘。

### 2. 论文提出的方法论
*   **核心思想**：基于**梯度相似性**构造一棵层次树（K-D Tree），每一层对应模型的不同深度，浅层捕获任务共享模式，深层捕获任务特异语义，叶子节点对应具体任务。通过在这棵树上搜索最相似的历史任务组，共享知识以加速新任务适应。
*   **关键技术细节**：
    *   **TreeLoRA结构**：每个节点代表一个任务组（由梯度方向L1距离≤δ的任务构成）。新任务到来时，通过Bandit算法在树上选择最相似分支。
    *   **Bandit搜索**：将每个历史任务视为一个臂，使用**下置信界（LCB）算法**平衡探索与利用，仅需一次梯度查询即可找到最相关的任务组，避免计算所有历史梯度。
    *   **稀疏更新**：在选定任务组后，通过**自适应稀疏正则化项**（基于当前样本梯度与任务组梯度的L1范数差异）仅更新最相关参数，保护旧知识。
    *   **更新流程**：通过LCB选择分支 → 稀疏梯度更新 → 记录任务特定低秩适配器（LoRA）→ 更新树结构（插入或合并节点）。
*   **理论依据**：在“平滑树”假设下，TreeLoRA的遗憾界将从普通Bandit的**O(√N)** 降至**O(√log N)**（关于任务数的依赖），从而加速相似任务组的识别。

### 3. 实验设计
*   **数据集与场景**：
    *   **视觉Transformer（ViTs）**：Split CIFAR-100, Split ImageNet-R, Split CUB-200（均为10个连续任务）。
    *   **大语言模型（LLMs）**：TRACE基准（包含8个多领域、多语言、代码、数学推理等任务，共200k样本），另有Math-LLM数据集及长任务序列实验（15任务）。
*   **对比方法**：
    *   基础方法：SeqLoRA（标准LoRA顺序训练）。
    *   重放：GEM。
    *   正则化：EWC。
    *   提示方法：L2P, DualPrompt。
    *   层次分解：HiDePrompt, HiDeLoRA。
    *   正交子空间：O-LoRA。
    *   还有SAPT, TASL, InfLoRA等扩展比较（附录）。
*   **评价指标**：整体准确率（OP）、后向迁移/遗忘率（BWT）、训练时间。

### 4. 资源与算力
*   **ViTs实验**：8块Nvidia V100 GPU，搭配2个Intel Xeon Gold 6248R CPU。
*   **LLMs实验**：4块Nvidia A800 (80GB) GPU，搭配2个Intel Xeon Gold 6430 CPU；使用DeepSpeed Stage 2、混合精度（BF16）训练。
*   **未明确说明整体训练总时长**（仅给出单任务或相对训练时间），但提供了各方法训练耗时对比。

### 5. 实验数量与充分性
*   **实验组数丰富**：
    *   ViT上3个基准数据集对比9种以上方法。
    *   LLM上4种不同规模的底座模型（Mistral-7B, LLaMA-2-7B, Gemma-2B, LLaMA-3.2-1B）在TRACE上对比10种方法。
    *   进一步进行：不同训练epochs的影响、树深度敏感性、消融实验（惩罚项和LCB搜索）、超参数敏感性（λ, α）、长任务流（15任务）、任务顺序变化、扩展到13B模型、效率FLOPS对比、树结构可视化等。
*   **公平性**：方法大多按照原作者设置实现，TreeLoRA在LLM实验中使用更少的训练epoch仍取得优势，但也说明了其他方法减少epoch会掉点。消融和敏感性分析较为完整，增强了结论可信度。

### 6. 论文的主要结论与发现
*   TreeLoRA在ViTs和LLMs的持续学习任务上均取得了**最优或竞争性的准确率**，同时显著**降低了遗忘（BWT）**。
*   **效率优势突出**：训练时间相比之前的方法实现**最高3.2×（ViTs）和2.4×（LLMs）的加速**，且仅需少量epoch即可达到接近最佳的性能。
*   学习到的树结构能**自然地反映任务之间的语义关系**（如数学推理类任务聚集，多语言NLU任务聚集）。
*   **理论分析**验证了层次树结构下Bandit搜索的遗憾界优于无结构方法。

### 7. 优点
*   **高效**：通过层次树和Bandit搜索将任务相似性查询复杂度降为O(1)（查询一次），避免了线性依赖任务数。
*   **结构与模型天然契合**：树结构与Transformer的分层特性对齐，浅层共享、深层特异，适配器参数开销极小。
*   **无需手动调阈值**：树分裂的相似性阈值δ采用中位数自动确定，降低调参成本。
*   **理论与实验结合**：提供了遗憾界证明，实验覆盖多种模型尺度和领域，验证了方法的泛化性。

### 8. 不足与局限
*   **树深度选择**：虽然做了敏感性分析，但树深度仍是一个关键超参数（默认ViT 5层，LLM 64层），文中未给出深度自适应的策略。
*   **任务粒度**：限定在任务边界清晰（task identity仅在测试时不可知）的设定，对于更复杂的无任务边界的“在线”漂移场景未做探索。
*   **任务结构假设**：依赖“平滑树”假设，当任务间关系高度动态变化或非层次化时，方法可能退化。
*   **存储与内存**：虽然声称额外存储和GPU内存开销很小（几乎等同于SeqLoRA），但在极限任务数下，存储的适配器节点数增多，文中提及了一种合并策略，但其对性能的影响未全面评估。
*   **理论局限**：遗憾界证明是在子最优间隙恒定的条件下给出的具体阶，实际任务中间隙可能是动态的。

（完）
