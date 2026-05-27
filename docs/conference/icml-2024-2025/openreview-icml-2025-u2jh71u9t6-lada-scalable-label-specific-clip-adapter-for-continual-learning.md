---
title: "LADA: Scalable Label-Specific CLIP Adapter for Continual Learning"
title_zh: LADA：面向持续学习的可扩展标签专用CLIP适配器
authors: "Mao-Lin Luo, Zi-Hao Zhou, Tong Wei, Min-Ling Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=u2jH71U9T6"
tags: ["query:continual"]
score: 9.0
evidence: 用于CLIP持续学习的标签专用适配器
tldr: 针对基于CLIP的持续学习方法在推理时需选择期望参数易出错的问题，该研究提出LADA，一种标签专用适配器。方法在冻结的CLIP图像编码器上附加轻量级标签记忆单元，通过聚合任务无关知识生成判别特征，无需划分参数。实验表明LADA有效提升了持续学习的性能和可扩展性，为大规模视觉-语言模型的持续学习铺平了道路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-u2jh71u9t6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1774, \"height\": 388, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u2jh71u9t6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1684, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-u2jh71u9t6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 863, \"height\": 378, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1644, \"height\": 1070, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1644, \"height\": 1004, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 876, \"height\": 455, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1643, \"height\": 1074, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1640, \"height\": 1000, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1353, \"height\": 659, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1352, \"height\": 661, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1353, \"height\": 660, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-u2jh71u9t6/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1352, \"height\": 661, \"label\": \"Table\"}]"
motivation: 现有CLIP持续学习方法存在推理时参数选择易出错的问题。
method: 提出标签特异记忆单元附加到冻结的CLIP编码器，实现判别特征生成。
result: 避免参数划分，提升持续学习性能。
conclusion: LADA为视觉-语言模型持续学习提供了高效且可扩展的方案。
---

## Abstract
Continual learning with vision-language models like CLIP offers a pathway toward scalable machine learning systems by leveraging its transferable representations. Existing CLIP-based methods adapt the pre-trained image encoder by adding multiple sets of learnable parameters, with each task using a partial set of parameters. This requires selecting the expected parameters for input images during inference, which is prone to error that degrades performance. To address this problem, we introduce LADA (**L**abel-specific **ADA**pter). Instead of partitioning parameters across tasks, LADA appends lightweight, label-specific memory units to the frozen CLIP image encoder, enabling discriminative feature generation by aggregating task-agnostic knowledge. To prevent catastrophic forgetting, LADA employs feature distillation for seen classes, preventing their features from being interfered with by new classes. Positioned after the image encoder, LADA prevents gradient flow to the frozen CLIP parameters, ensuring efficient training. Extensive results show that LADA achieves state-of-the-art performance in continual learning settings.  The implementation code is available at [https://github.com/MaolinLuo/LADA](https://github.com/MaolinLuo/LADA).

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景与动机**：  
  - 视觉-语言模型如CLIP具有强大的零样本迁移能力，是持续学习（continual learning）的自然候选者。  
  - 现有基于CLIP的持续学习方法（如提示类方法、MoE适配器）一般在图像编码器中添加多组可学习参数，不同任务使用部分参数。  
  - **核心问题**：推理阶段需要为输入图像选择预期的任务参数（提示或适配器），这种选择过程容易出错，导致性能下降。  
  - 此外，还面临灾难性遗忘的挑战，包括前向遗忘（预训练知识退化）和后向遗忘（旧任务知识丢失）。  
- **整体含义**：  
  - 提出LADA（Label-specific ADApter）——一种轻量、可扩展的标签专用CLIP适配器，旨在消除参数选择过程，同时缓解遗忘问题，实现高性能持续学习。

### 2. 论文提出的方法论

- **核心思想**：  
  - 不划分任务参数，而是在冻结的CLIP图像编码器之后附加**标签特定的记忆单元（label-specific memory units）**。  
  - 这些记忆单元通过聚合所有任务的信息，将CLIP表示转化为**标签专用特征**，无需在推理时选择任务专属参数。

- **关键技术细节**：  
  - **特征构造**：  
    - 对每个类的训练样本提取CLIP图像特征，进行K-means聚类，得到 $\lambda_1$ 个聚类中心 $W^{k}_j \in \mathbb{R}^{\lambda_1 \times d}$。  
    - 对任务 $T_k$ 构造标签专用特征映射 $\phi_k(i) = [W_1^k i, \dots, W_{M_k}^k i]$，然后拼接所有任务的特征 $\phi(i) = [\phi_1(i), \dots, \phi_k(i)]$。  
  - **固定分类器**：  
    - 采用类最近邻分类器 $h \circ \phi$，通过内积加指数变换 $ \phi = \exp(-\beta(1-x)) $ 转化为非负值，直接输出各类的logits。  
  - **遗忘缓解**：  
    - **冻结旧记忆**：学习新任务时，只更新 $W^k$，冻结 $W^1, \dots, W^{k-1}$。  
    - **特征蒸馏**：对旧任务类进行特征蒸馏，使用保留的聚类中心 $p_i^j$ 或通过**高斯混合模型（GMM）拟合分布**，生成增强原型 $\tilde{p}_i^j(l)$，并对其计算分类损失。  
  - **联合优化**：  
    - 同时微调文本编码器（采用AdaptFormer以参数高效微调）和LADA模块，将文本logits和LADA logits相加后计算交叉熵。  
    - 推理时，对已见类综合文本特征和LADA输出进行线性加权；对未见类直接使用零样本CLIP文本特征。

- **公式流程概览**（文字说明）：  
  1. 对当前任务每个类 $j$ 的图像计算CLIP特征，得到 $W_j^k$。  
  2. 通过 $\phi(i)$ 生成所有任务拼接的特征，送入固定分类器 $h$ 得到logits。  
  3. 当前任务损失：基于训练样本的交叉熵。  
  4. 旧任务损失：基于蒸馏原型（$p_i^j$）或分布增强原型（$\tilde{p}_i^j$）的交叉熵。  
  5. 总损失 = 当前任务损失 + 旧任务损失（蒸馏/分布增强）。  
  6. 同时优化文本编码器的AdaptFormer参数和LADA的 $W^k$。

### 3. 实验设计

- **数据集/场景**：  
  - 使用 **X-TAIL (Cross-domain Task-Agnostic Incremental Learning)** 基准，包含10个图像分类数据集：Aircraft, Caltech101, DTD, EuroSAT, Flowers, Food, MNIST, OxfordPet, StanfordCars, SUN397，共1100类。  
  - 两种训练设定：16-shot（每个类16个训练样本）和full-shot（原数据集分布）。  
  - 任务顺序：字母顺序（Aircraft→…→SUN397）和随机顺序（StanfordCars→…→EuroSAT）。  
- **对比方法**：  
  - 传统持续学习方法：LwF, WiSE-FT。  
  - CLIP持续学习方法：ZSCL, MoE-Adapters, Primal-RAIL, Dual-RAIL。  
  - 零样本CLIP作为baseline。  
- **评价指标**：  
  - *Transfer*（评估前向遗忘：训练某任务后对未来任务的准确率）、*Average*（所有时间步平均准确率）、*Last*（最终模型在各任务上的准确率，衡量后向遗忘）。

### 4. 资源与算力

- 论文明确指出：所有LADA实验在**单块NVIDIA 4090 GPU**上完成。  
- 未提供训练总时长，但提供了每批次（秒）的时间成本和峰值内存使用（在消融实验中）。例如，λ₁=16, λ₂=4时，full-shot最后任务时间为0.289秒/批次，内存18.51 GB。

### 5. 实验数量与充分性

- **主要实验**：  
  - 16-shot和full-shot两套主要结果表，含多种基线方法。  
  - 对两种任务顺序（字母顺序和随机顺序）均提供实验结果。  
- **消融实验**：  
  - 分析基线文本微调框架（BF）、分布保持训练（DPT）、LADA三个模块的贡献。  
  - 不同λ₁（标签专用特征维度）和λ₂（每类蒸馏原型数）对性能和计算代价的影响。  
  - 是否需要零样本CLIP作为选择器的对比。  
- **分析实验**：  
  - 各任务在所有训练步骤上的准确率变化曲线（图2）。  
  - 16-shot和full-shot下task recall与准确率差异（图3）。  
- **实验充分性评价**：  
  - 实验设计较全面，覆盖了多种设定、多个指标、消融和超参数分析。对比方法选择具有代表性，结果报告详细。实验公平，所有方法使用相同基准和评估协议。

### 6. 论文的主要结论与发现

- LADA在X-TAIL 16-shot和full-shot设置下均取得**最先进的性能**，在Transfer、Average、Last指标上显著优于之前方法（如16-shot下Transfer提高2.5%，full-shot下Transfer提高2.9%，Average提高2.4%，Last提高2.9%）。  
- LADA通过聚合任务知识生成标签专用特征，**完全消除推理时的参数选择步骤**，避免了因选择错误导致的性能下降。  
- 冻结旧类记忆单元并结合特征蒸馏/分布增强，有效缓解灾难性遗忘，同时保持对新任务的学习能力。  
- LADA的Transfer指标在某些数据集上**超过零样本CLIP**，说明其能利用已学知识提升未见类的分类能力，而无需额外选择器。  
- 方法在训练效率上具有优势，无需梯度回传至CLIP图像编码器，且参数量/计算开销随任务数缓慢增长。

### 7. 优点

- **方法设计**：  
  - 创新地将标签特定记忆单元直接附加于冻结编码器，将多任务信息统一到同一表示空间，避免了任务专属参数选择。  
  - 同时利用文本和图像适配，通过联合优化提升性能。  
  - 分布保持训练（GMM增强原型）在少量原型下即可有效保持旧知识分布。  
- **实验方面**：  
  - 基准全面，涵盖小样本和全量数据、多种任务顺序。  
  - 消融和分析实验扎实，清晰展示了各模块的作用和超参数鲁棒性。  
  - 与最新方法公平对比，并有清晰的性能上界分析（如超越零样本CLIP的合理性）。

### 8. 不足与局限

- **实验覆盖**：  
  - 仅在X-TAIL基准上测试，未在其他持续学习基准（如CIL、MTIL）或更多样化的模态组合上验证，泛化性有待进一步评估。  
  - 使用的数据集类型为图像分类，未延伸到更复杂的视觉任务（如检测、分割）。  
- **偏差风险**：  
  - 实验顺序虽包含随机顺序，但未报告多随机种子的平均和方差，可能受到任务顺序随机性的影响。  
  - 超参数λ₁和λ₂虽然进行了分析，但报告中并未明确是否在测试集上调整过，需关注潜在的微调偏差。  
- **应用限制**：  
  - 方法依赖于预训练的CLIP模型，无法应用于无视觉-语言对齐的纯视觉模型。  
  - 记忆单元随任务线性增长，虽然效率较高，但极端大量任务下存储和计算成本仍需考量。  
  - 推理时需要对已见类进行文本和LADA logits加权，超参数可能需根据任务调整。

（完）
