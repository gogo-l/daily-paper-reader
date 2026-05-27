---
title: Rethinking Momentum Knowledge Distillation in Online Continual Learning
title_zh: 重新思考在线持续学习中的动量知识蒸馏
authors: "Nicolas Michel, Maorong Wang, Ling Xiao, Toshihiko Yamasaki"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=UW5nO9NGjt"
tags: ["query:continual"]
score: 10.0
evidence: 分析在线持续学习中知识蒸馏的挑战，提出动量知识蒸馏以防止遗忘
tldr: 针对在线持续学习中知识蒸馏应用不足且面临挑战的问题，本文通过分析其难点，提出基于动量的知识蒸馏方法MKD。在多个在线学习基准上，MKD在不使用回放内存的情况下有效缓解灾难性遗忘，性能超越现有方法。该工作拓展了知识蒸馏在在线持续学习中的应用，为无回放持续学习提供了新工具。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 615, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 528, \"height\": 384, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 553, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 551, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 666, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 860, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 778, \"height\": 399, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1748, \"height\": 619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1579, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1682, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-uw5no9ngjt/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 909, \"height\": 535, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 627, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 614, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1776, \"height\": 592, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1775, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 776, \"height\": 232, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 537, \"height\": 275, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 539, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 891, \"height\": 630, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 625, \"height\": 518, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-uw5no9ngjt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1081, \"height\": 2217, \"label\": \"Table\"}]"
motivation: 知识蒸馏在离线持续学习中广泛使用，但在在线场景中探索不足，存在应用挑战。
method: 提出动量知识蒸馏（MKD），通过动量更新教师模型来稳定蒸馏过程。
result: 在标准在线持续学习基准上，MKD性能超越主流回放方法，且无需存储旧样本。
conclusion: 动量知识蒸馏是解决在线持续遗忘问题的有效且直接的手段。
---

## Abstract
Online Continual Learning (OCL) addresses the problem of training neural networks on a continuous data stream where multiple classification tasks emerge in sequence. In contrast to offline Continual Learning, data can be seen only once in OCL, which is a very severe constraint. In this context, replay-based strategies have achieved impressive results and most state-of-the-art approaches heavily depend on them. While Knowledge Distillation (KD) has been extensively used in offline Continual Learning, it remains under-exploited in OCL, despite its high potential. In this paper, we analyze the challenges in applying KD to OCL and give empirical justifications. We introduce a direct yet effective methodology for applying Momentum Knowledge Distillation (MKD) to many flagship OCL methods and demonstrate its capabilities to enhance existing approaches. In addition to improving existing state-of-the-art accuracy by more than $10\%$ points on ImageNet100, we shed light on MKD internal mechanics and impacts during training in OCL. We argue that similar to replay, MKD should be considered a central component of OCL. The code is available at https://github.com/Nicolas1203/mkd_ocl.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **核心问题**：在在线持续学习（Online Continual Learning, OCL）场景中，数据流只能被模型学习一次（单次通过），这带来了严峻的灾难性遗忘（Catastrophic Forgetting）挑战。尽管经验回放（Experience Replay）已成为主流且有效的方法，但知识蒸馏（Knowledge Distillation, KD）这一在离线持续学习中广泛使用的技术，在OCL中却未被充分挖掘和应用。
- **研究动机**：
    - 作者认为，KD在OCL中被忽视的主要原因是其面临三个独特且严峻的挑战：**教师模型质量低**（因数据仅见一次，模型未充分训练）、**教师模型数量随任务增长**（存储多个教师快照违背OCL的存储约束）以及**任务边界模糊或未知**（难以在合适时机获取教师快照）。
    - 本文旨在重新思考并有效应用KD于OCL，提出一种简单而高效的**动量知识蒸馏（Momentum Knowledge Distillation, MKD）** 方法，使其成为OCL的核心组件，以显著提升现有方法的性能。

### 2. 方法论
- **核心思想**：使用一个通过指数移动平均（Exponential Moving Average, EMA）不断更新的进化型教师模型，替代传统的、在任务结束时冻结的静态快照教师。这可以有效应对教师质量、数量和未知任务边界的问题。
- **关键技术细节与公式**：
    - **教师模型更新**：教师模型参数 $\theta_{\alpha}$ 在每个训练步通过EMA从学生模型参数 $\theta$ 更新：
        $$\theta_{\alpha}(t) = \alpha \cdot \theta(t) + (1 - \alpha) \cdot \theta_{\alpha}(t-1)$$
        其中 $\alpha$ 是动量参数，控制教师的更新速度。
    - **蒸馏损失函数**：总体损失结合了交叉熵损失和动量知识蒸馏损失。动量知识蒸馏采用多视图（multiview）策略，通过数据增强 $Aug(.)$ 来增强鲁棒性，损失函数 $L_{MKD}$ 定义如下：
        $$L_{MKD}(X, Y) = L_{CE}(\hat{X}, Y) + \frac{\lambda_{\alpha}}{2} KL(T_{\alpha}(X), S(\hat{X})) + \frac{\lambda_{\alpha}}{2} KL(T_{\alpha}(\hat{X}), S(\hat{X}))$$
        其中，$X, Y$ 为原始数据与标签，$\hat{X}$ 为增强后的数据，$S$ 和 $T_{\alpha}$ 分别为学生和教师模型，$KL$ 为Kullback-Leibler散度，$\tau$ 为蒸馏温度。
    - **塑性-稳定性权衡控制**：动量参数 $\alpha$ 提供了一个精确控制模型塑性与稳定性的机制。较小的 $\alpha$ 让教师更新更慢，更关注旧任务稳定性；较大的 $\alpha$ 则让教师更关注新任务塑性。
    - **模型推理**：推理时，使用学生和教师模型参数的平均值作为最终模型，以获得更优性能。
- **算法流程**：该方法可作为一个即插即用的模块，无缝集成到现有的OCL方法中。算法伪代码清晰展示了如何将MKD损失与基线方法（如ER）的损失结合进行训练。

### 3. 实验设计
- **数据集与场景**：
    - **数据集**：CIFAR-10、CIFAR-100、Tiny-ImageNet、ImageNet-100。
    - **场景**：类增量学习（Class Incremental Learning）场景，分为**清晰任务边界（Clear Boundary）** 和**模糊任务边界（Blurry Boundary）** 两种设定。
- **Benchmark与对比方法**：
    - **基线方法**：作者将所提出的MKD模块集成到多种代表性OCL方法中，包括ER、DER++、ER-ACE、DVC、OCM、GSA、PCR等。
    - **对比方法**：除了与原始基线方法对比，还与其他蒸馏或EMA相关策略进行了对比，如**SDP**（使用超指数型进化教师）和**Temp. Ens.**（仅使用EMA模型进行推理）。
- **评估指标**：主要采用训练结束后的最终平均准确率（Final Average Accuracy），同时辅以反向迁移（Backward Transfer, BT）等指标来评估方法对过往知识的保持能力。

### 4. 资源与算力
- **硬件**：文中在“B.5. Hardware and computation”部分提到，实验使用了**RTX A5000 和 V100 型号的GPU**进行训练。
- **训练时长**：文中未明确给出每个实验的精确小时数，但提供了图12展示在CIFAR-100, M=5k设定下各方法的**训练时间消耗（分钟）** 对比。结果表明，所提出的MKD方法在增加性能的同时，其计算开销相比SDP等方法更小。

### 5. 实验数量与充分性
- **实验组数**：
    1. **主实验（表3、4）**：在4个数据集、多种记忆体大小（M）设定下，对7种基线方法及其+MKD的版本进行了性能测试。总计包含了清晰和模糊任务边界两种场景。
    2. **消融实验（5.4节，表5）**：研究了最终模型估计方式（学生/教师/平均值）、多视图蒸馏策略对性能的影响。
    3. **深入分析实验（6节，图4-8，表6-7）**：系统地分析了超参数 $\alpha$ 和 $\lambda_{\alpha}$ 的关系与选择（图4，5）；通过混淆矩阵、NCM分类器、特征漂移图、t-SNE可视化和反向迁移指标，验证了MKD在缓解任务近因偏差、最后一层偏差、特征漂移以及提升特征判别力和反向迁移方面的作用。
    4. **附录实验**：提供了更全面的混淆矩阵（图9）、特征漂移（图10）、t-SNE（图11）和反向迁移（表9）实验，覆盖所有对比基线。
- **充分性与公平性**：实验设计非常全面且系统。不仅在多个标准基准和不同规模的数据集上进行了验证，还深入剖析了方法的内在机理。所有对比方法均经过统一的小规模超参数搜索，确保了比较的公平性。消融和深入分析实验逻辑清晰，为其核心论点提供了有力支撑。

### 6. 主要结论与发现
- **性能大幅提升**：MKD作为一个即插即用模块，能够显著且稳定地提升几乎所有主流OCL方法的性能。例如，在ImageNet-100上，结合MKD的方法将现有最高准确率提升了超过10个百分点。
- **解决核心OCL难题**：MKD能有效缓解OCL中的多个已知问题：**任务近因偏差、最后一层偏差、特征漂移**，同时能**增强特征判别力**并**促进正向反向迁移**。
- **成为核心组件**：作者主张，MKD应和经验回放一样，被视为OCL的标准核心组件。

### 7. 优点
- **方法简洁高效**：MKD基于成熟的EMA技术，实现简单，计算开销小，易于集成，是一种“直接而有效”的方法。
- **机理分析透彻**：论文不仅展示了“是什么”（性能提升），更通过大量详实的实验深入解释了“为什么”（内部作用机理），如对塑性-稳定性权衡的精确控制、对各类偏差和漂移的缓解，大大提升了论文的洞见和深度。
- **实验证据充分**：在多种数据设定、多个基线方法和多维度评估指标下，提供了一致的、令人信服的实验结果。与SDP等同类技术的对比也证明了其优越性。
- **即插即用特性**：能够与多种现有OCL方法无缝结合，显示出强大的通用性和适应性。

### 8. 不足与局限
- **对记忆库的依赖**：虽然MKD本身不依赖回放，但论文中的所有实验均是与基于回放（replay-based）的基线方法结合进行的。方法在无记忆库的纯蒸馏类OCL方法中的效果和潜力未被探索。
- **超参数敏感性讨论有限**：尽管分析了 $\alpha$ 和 $\lambda_{\alpha}$ 的关系，并给出它们之间的经验公式，但其他可能的关键超参数（如蒸馏温度 $\tau$）的讨论缺失，且该经验公式在不同网络架构和数据集上的通用性未得到验证。
- **局限性场景**：所有实验均针对标准的类增量场景。在更复杂的设定，如数据流中含有噪声或域偏移的场景下的有效性有待验证。

（完）
