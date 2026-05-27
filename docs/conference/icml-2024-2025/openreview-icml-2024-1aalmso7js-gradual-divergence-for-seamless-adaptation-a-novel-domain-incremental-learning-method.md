---
title: "Gradual Divergence for Seamless Adaptation: A Novel Domain Incremental Learning Method"
title_zh: 渐进式分歧实现无缝适应：一种新型领域增量学习方法
authors: "Kishaan Jeeveswaran, Elahe Arani, Bahram Zonooz"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=1AAlMSo7Js"
tags: ["query:continual"]
score: 9.0
evidence: 领域增量学习方法，通过渐进式分歧避免遗忘
tldr: 针对领域增量学习中的灾难性遗忘，提出DARE方法，通过发散、适应和精炼三阶段训练，逐步将新任务表示融入到先前任务的特征空间中，并整合决策边界。实验结果表明DARE在多个领域增量学习基准上显著优于现有方法，有效缓解了表示漂移。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 846, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1720, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1563, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1598, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1521, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 852, \"height\": 1226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1675, \"height\": 531, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 878, \"height\": 1983, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1538, \"height\": 981, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 772, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1480, \"height\": 782, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1273, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1318, \"height\": 1504, \"label\": \"Table\"}]"
motivation: 领域增量学习中表示漂移导致灾难性遗忘。
method: 提出DARE三阶段训练：发散、适应和精炼，逐步融合表示。
result: 在多个基准上超越现有领域增量学习方法，遗忘率大幅降低。
conclusion: 渐进式表示适应有效缓解了领域变化时的遗忘问题。
---

## Abstract
Domain incremental learning (DIL) poses a significant challenge in real-world scenarios, as models need to be sequentially trained on diverse domains over time, all the while avoiding catastrophic forgetting. Mitigating representation drift, which refers to the phenomenon of learned representations undergoing changes as the model adapts to new tasks, can help alleviate catastrophic forgetting. In this study, we propose a novel DIL method named *DARE*, featuring a three-stage training process: Divergence, Adaptation, and REfinement. This process gradually adapts the representations associated with new tasks into the feature space spanned by samples from previous tasks, simultaneously integrating task-specific decision boundaries. Additionally, we introduce a novel strategy for buffer sampling and demonstrate the effectiveness of our proposed method, combined with this sampling strategy, in reducing representation drift within the feature encoder. This contribution effectively alleviates catastrophic forgetting across multiple DIL benchmarks. Furthermore, our approach prevents sudden representation drift at task boundaries, resulting in a well-calibrated DIL model that maintains the performance on previous tasks.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **问题背景**：领域增量学习（Domain Incremental Learning, DIL）要求模型在连续变化的领域上顺序学习，同时避免灾难性遗忘。
- **核心痛点**：随着新领域学习，旧知识的表示发生剧烈漂移（representation drift），导致旧任务性能急剧下降，这是遗忘的主要诱因。
- **整体含义**：本文提出一种名为 DARE 的方法，通过“发散-适应-精炼”三阶段训练，逐步将新领域样本的表示融入旧领域张成的特征空间，从而抑制表示漂移，实现无缝适应。

## 2. 方法论：核心思想、关键技术细节与流程
- **模型结构**：共享编码器 \(g\)，两个分类器 \(f_1\)（交叉熵损失）与 \(f_2\)（监督对比损失），提供多视角学习。
- **三阶段训练过程**（每个任务内按轮次交替进行）：
  1. **发散阶段（Divergence）**：冻结编码器，最大化两个分类器对新任务样本预测的差异（差距损失），使分类器学会“认出”新领域样本；同时用缓冲区样本进行一致性蒸馏。
  2. **适应阶段（Adaptation）**：冻结分类器，最小化它们对新任务样本预测的差异，迫使编码器将新样本表示拉入旧任务表示空间内，抑制表示漂移。
  3. **精炼阶段（Refinement）**：全部参数放开，同时使用新任务损失与缓冲区一致性损失，巩固新旧知识。
- **缓冲区采样策略**：提出“中介蓄水池采样（IRS）”，以正态分布侧重于训练中和阶段的样本，保存含有丰富“暗知识”的logits，提升蒸馏质量。
- **损失函数**：涉及交叉熵、监督对比损失、一致性损失（MSE）以及分类器差异损失（使用基于距离分布的二进制交叉熵形式），相互协作。

## 3. 实验设计
- **数据集**：
  - DN4IL：由DomainNet构造的DIL基准，6个高度多样的域（如素描、真实、快速绘制等），100个类别，约67k训练/19k测试图像。
  - iCIFAR-20：CIFAR-100的DIL版本，20个超类视为真实标签，每个超类下的5个子类视为不同域，约50k训练/10k测试图像。
- **上下界**：联合训练（Joint）作为上界，无缓冲的SGD作为下界。
- **对比方法**：
  - 单模型重放：ER、DER++
  - 多模型重放：CLS-ER、DUCA
  - 本文方法：DARE（单模型）、DARE++（简单指数移动平均双记忆版本）
  - 额外对比：oEWC、SI、A-GEM、FDR（见于附录）
- **评价指标**：最后平均精度（Last Accuracy）、后向迁移（BWT）、校准误差、logits范数等。
- **设置**：ResNet-18骨干，缓冲大小50/100/200，批大小32，SGD优化器，每任务50轮次。

## 4. 资源与算力
- 论文未明确给出所用 GPU 型号、数量、训练时长等算力信息。实验在标准持续学习框架（mammoth）上进行，但硬件配置未披露。

## 5. 实验数量与充分性
- **主要实验组数**：
  - 2个数据集 × 3种缓冲大小 × 所有对比方法，总计多组实验。
  - 消融研究：去除各损失分量（L1-L4）的影响验证。
  - 缓冲区采样策略对比（Reservoir vs IRS）。
  - 表示漂移可视化、任务准确率矩阵图、校准误差分析、logits范数分析。
  - 附录中额外与oEWC、SI、A-GEM、FDR对比。
- **充分性与公平性**：实验覆盖面广，对比方法选择具有代表性，均采用统一数据流和训练框架，随机种子取平均，参数通过网格搜索选择，公平合理。消融分析确保了各组件的贡献可解释。

## 6. 主要结论与发现
- DARE 在所有缓冲大小和数据集上均显著优于 ER、DER++ 等单模型方法，在 DN4IL 缓冲大小50时精度提升约15.1%（vs DER++）。
- DARE++ 以显著更少的参数实现了与多记忆系统（CLS-ER、DUCA）相当或更优的性能。
- 表示漂移在任务边界被有效抑制，旧任务准确率保持平稳，模型校准误差更低，对近期任务的过自信偏向减轻。
- IRS 采样策略进一步提升 DER++ 和 DARE 的表现，缓冲大小50时提升近12%。

## 7. 优点
- **创新性**：首次将表示漂移缓解思路引入 DIL，通过三阶段对抗式适应实现增量与保存的平衡。
- **有效性**：性能大幅领先，尤其在表示漂移剧烈的低缓冲设置下。
- **轻量化**：单模型版本参数几乎无增加，双记忆版本也远低于 CLS-ER 等。
- **全面分析**：从准确率、遗忘度、漂移量、校准等多个角度评估，论证充分。

## 8. 不足与局限
- **依赖任务边界**：IRS 策略需要已知任务ID来定义训练中的“中间阶段”，虽然可能通过损失监测自动检测，但当前实现依赖任务ID，与严格的无任务增量场景有距离。
- **数据集限制**：只在图像分类的两个构造数据集上评估，未涉及其他模态或更真实的流式数据（如在线学习）。
- **算力与效率**：三阶段需要交替进行，训练流程更复杂，文中未分析额外的时间开销。
- **超参数敏感性**：虽在附录给出了稳定超参数，但不同数据集的个别参数（如学习率等）仍需调整，可能存在一定敏感性。

（完）
