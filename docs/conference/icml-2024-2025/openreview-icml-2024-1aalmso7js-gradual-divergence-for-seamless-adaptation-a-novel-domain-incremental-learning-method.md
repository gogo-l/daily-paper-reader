---
title: "Gradual Divergence for Seamless Adaptation: A Novel Domain Incremental Learning Method"
title_zh: 渐进分歧实现无缝适应：一种新颖的领域增量学习方法
authors: "Kishaan Jeeveswaran, Elahe Arani, Bahram Zonooz"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=1AAlMSo7Js"
tags: ["query:continual"]
score: 9.0
evidence: 新颖的领域增量学习方法缓解表示漂移和灾难性遗忘
tldr: 针对领域增量学习中因表示漂移导致的灾难性遗忘，提出DARE方法，包含发散、适配和精炼三个阶段，逐步将新任务表示适配到先前任务的样本特征空间中，并集成任务特定决策边界，从而有效缓解遗忘。实验证明该方法在多个领域增量学习场景中表现优异。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 846, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1720, \"height\": 501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1563, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1598, \"height\": 497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1521, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 852, \"height\": 1226, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-1aalmso7js/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1675, \"height\": 531, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 878, \"height\": 1983, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1538, \"height\": 981, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 772, \"height\": 243, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1480, \"height\": 782, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1273, \"height\": 497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-1aalmso7js/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1318, \"height\": 1504, \"label\": \"Table\"}]"
motivation: 领域增量学习面临连续不同域训练时的灾难性遗忘，缓解表示漂移是减轻遗忘的关键。
method: 提出三阶段训练方法DARE（发散、适配、精炼），逐步将新任务表示对齐到先前任务的特征空间，并集成决策边界。
result: 实验显示DARE显著降低了表示漂移和遗忘，在领域增量学习基准上取得了领先性能。
conclusion: DARE通过渐进适应策略有效解决了领域增量学习中的遗忘问题，为动态环境下的模型更新提供了新思路。
---

## Abstract
Domain incremental learning (DIL) poses a significant challenge in real-world scenarios, as models need to be sequentially trained on diverse domains over time, all the while avoiding catastrophic forgetting. Mitigating representation drift, which refers to the phenomenon of learned representations undergoing changes as the model adapts to new tasks, can help alleviate catastrophic forgetting. In this study, we propose a novel DIL method named *DARE*, featuring a three-stage training process: Divergence, Adaptation, and REfinement. This process gradually adapts the representations associated with new tasks into the feature space spanned by samples from previous tasks, simultaneously integrating task-specific decision boundaries. Additionally, we introduce a novel strategy for buffer sampling and demonstrate the effectiveness of our proposed method, combined with this sampling strategy, in reducing representation drift within the feature encoder. This contribution effectively alleviates catastrophic forgetting across multiple DIL benchmarks. Furthermore, our approach prevents sudden representation drift at task boundaries, resulting in a well-calibrated DIL model that maintains the performance on previous tasks.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究动机**：领域增量学习（DIL）要求模型在时序上连续学习多个不同分布的新领域，同时不能遗忘已学会的旧领域知识。这种场景下的核心难题是灾难性遗忘，而现有研究表明，表示漂移（representation drift）——即旧任务对应的特征表示在学习新任务时发生剧烈变化——是导致遗忘的关键因素。
- **整体含义**：现有方法（如经验回放）未显式解决表示漂移，尤其在领域变化剧烈的DIL中更为突出。本文旨在直接缓解表示漂移，提出一种三阶段渐进式训练方法 **DARE**（Divergence, Adaptation, REfinement），通过将新领域样本的表示逐步“融入”旧领域形成的特征空间，而非反向干扰旧表示，从根本上抑制遗忘，同时提升模型在所有已见领域上的整体性能。

## 2. 论文提出的方法论
- **核心思想**：使用一个特征编码器 \(g\) 和两个独立的分类器 \(f_1, f_2\)。\(f_1\) 采用交叉熵损失，\(f_2\) 采用监督对比损失，以保证两个分类器有不同的决策视角。对于后续新任务，以循环迭代的方式交替执行以下三阶段：
  - **发散阶段（Divergence）**：冻结编码器，最大化两个分类器对新任务样本预测（经过 L2 归一化）的差异，同时利用回放缓冲区中的旧样本施加一致性正则化（含分类损失和 logits 蒸馏损失），让分类器学会区分“属于旧表示空间”和“来自全新领域”的样本。
  - **适配阶段（Adaptation）**：冻结分类器，最小化它们对新任务样本预测的差异，迫使编码器将新领域样本的表示映射到旧表示空间内，使新旧表示共存于一个一致的特征空间中。
  - **精炼阶段（Refinement）**：同时更新编码器和两个分类器，使用新任务样本的分类损失和缓冲区样本的一致性损失，以巩固所学的新旧知识并形成统一的决策边界。
- **关键技术细节**：
  - 第一任务仅使用 \(L_{\text{ce}} + L_{\text{sup}}\) 进行训练。
  - 发散与适配采用基于成对距离分布的差异损失（discrepancy loss），并通过正负向优化实现对抗式训练效果。
  - 缓冲区采样提出 **中间蓄水池采样（IRS）**，使用以任务学习轨迹中期为均值的高斯分布采样样本与 logits，以保留更多蕴含类别间关系的“暗知识”，提高蒸馏质量。
  - 算法整体见原文 Algorithm 1 及 Algorithm 2。

## 3. 实验设计
- **数据集与场景**：
  - **DN4IL**：基于 DomainNet 构建，包含 6 个视觉分布差异极大的领域（sketch、real、quickdraw、painting、infograph、clipart），共 100 类，是极具挑战的 DIL 基准。
  - **iCIFAR-20**：CIFAR-100 的 DIL 版本，将 20 个超类视为真实类别，将每超类下的 5 个子类视为 5 个新领域。
- **基准对比方法**：
  - 无回放下限 **SGD**、联合训练上限 **Joint**。
  - 单模型回放方法：**ER**、**DER++**（均含残差采样变体）。
  - 多记忆系统方法：**CLS-ER**、**DUCA**（均具备指数移动平均或双记忆结构）。
  - 额外对比了正则化方法 oEWC、SI 以及带有约束或蒸馏的回放方法 A-GEM、FDR。
- **评价指标**：采用 **Last Accuracy**（最终在所有已见任务上的平均准确率）和 **Backward Transfer (BWT)**（新任务对旧任务的影响）。
- **实现细节**：基于 Mammoth 框架，使用 ResNet-18 作为编码器，分类器为线性层；批量大小 32，每个任务训练 50 个 epoch；缓冲区大小分别设为 50、100、200。所有方法均保持公平统一的环境。

## 4. 资源与算力
- 原文未明确提及所使用的 GPU 型号、数量及训练时长等具体算力信息。文中仅交代了实验基于 ResNet-18 并训练 50 epochs/task，且所有对比方法在相同条件下复现。

## 5. 实验数量与充分性
- **多组对比实验**：
  - 两个数据集 × 三种缓冲大小（50、100、200），与至少 6 种主要方法及若干附加方法进行对比，包含多记忆模型的 DARE++。
  - 提供消融实验：依次移除三个阶段的损失函数（\(L_1\)、\(L_2\)、\(L_3\)、\(L_4\)），分析各组件的贡献。
  - 缓冲区采样策略消融：对比传统的蓄水池采样与所提出的 IRS，验证有效性和稳定性。
- **深度分析实验**：
  - 任务级准确率演化（任务边界表现）。
  - 表示漂移量化：绘制旧任务准确率曲线和缓冲区样本逐迭代的 MSE 漂移。
  - 任务近期偏置与模型校准：分析预测 logits 范数分布和期望校准误差（ECE）。
- 这些实验设计覆盖了主要性能、遗忘程度、特征稳定性、公平概率校准等多个维度，且对比条件统一（相同架构、学习率搜索等），因此**实验充分、客观且可复现**。

## 6. 论文的主要结论与发现
- DARE 通过“发散–适配–精炼”三阶段训练，有效抑制了新任务学习时旧任务表示的突然漂移，从而**显著减轻灾难性遗忘**。
- 在低缓冲（50 样本）的极端条件下，DARE 在 DN4IL 上相较于 DER++ 提升 15.1%，相较于 ER 提升 33.3%，并展现出**优越的向后迁移**能力。
- DARE++ 以更少的参数量达到甚至超越 CLS-ER、DUCA 等需要多记忆系统的方法，体现了更高的参数效率。
- 方法显著减弱了模型对近期任务的过信偏置，使模型在旧任务上的校准误差更低，预测置信度更均衡。
- 所提出的**中间蓄水池采样（IRS）**策略能够捕捉更多中间阶段的暗知识，进一步提升知识蒸馏效果，降低遗忘。

## 7. 优点
- **新颖性与针对性**：首次将“将新表示拉入旧空间”的对抗式适配思想系统化地应用于 DIL，直接针对表示漂移的根源。
- **设计精细**：三阶段协同工作，配合双分类器差异损失、一致性正则化与监督对比损失，形成渐进、稳定的适应机制。
- **效果显著**：在多个困难基准和大域迁下大幅领先同类方法，尤其在小缓冲设定下优势突出，且 DARE++ 在参数量和性能之间取得良好平衡。
- **分析深入**：除了最终精度，还从表示漂移、任务级演化、模型校准等角度的进行剖析，增强了结论的可信度。
- **IRS 采样思路巧妙**：基于知识蒸馏中期模型更具信息量的结论，设计正态分布采样，提升回放 logits 质量，开销小且有效。

## 8. 不足与局限
- **依赖任务边界**：IRS 采样策略需要知晓任务 ID，该假设在某些无任务边界的在线学习中不成立。文中虽提出可借助损失变化自动检测任务转换，但仍未在实验中实现或验证。
- **基准范围有限**：仅测试了 ResNet-18 和两个数据集；未在更大型数据集或 Transformer 架构上验证，迁移到其他骨干网络的普适性有待考察。
- **计算开销未量化**：虽然参数量与 DER++ 相当，但三阶段循环训练可能增加每个任务内的迭代次数，文中未报告训练时间或 FLOPs 对比。
- **细粒度消融的耦合性**：文中指出三阶段高度耦合，单独移除某阶段可能导致训练崩溃或严重遗忘，但这种强依赖也可能限制方法在极度受限下的灵活性。
- **超参数敏感性**：虽给出了较稳定的参数范围，但实际部署时仍需针对学习率、损失权重和温度等进行调整，且未讨论超参数对不同数据集/任务数的鲁棒性。
- **类别共享假设**：DIL 设定中所有任务共享相同类别集合，实际应用中可能不完全满足，方法对类别变动的适应性尚未探讨。

（完）
