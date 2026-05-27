---
title: Bayesian Adaptation of Network Depth and Width for Continual Learning
title_zh: 面向持续学习的网络深度与宽度贝叶斯自适应方法
authors: "Jeevan Thapa, Rui Li"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=c9HddKGiYk"
tags: ["query:continual"]
score: 9.0
evidence: 贝叶斯方法自适应网络深度和宽度以防止持续学习中的遗忘
tldr: 现有动态架构持续学习方法多扩展网络宽度但忽略深度，本文提出非参数贝叶斯方法同时推断网络深度并自适应宽度，利用Beta过程建模深度增长，共轭伯努利过程正则化宽度。在多个持续学习基准上达到或超越最先进水平，且可扩展至无监督持续学习，展示了贝叶斯方法在平衡记忆与可塑性方面的优势。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1002, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 602, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1236, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1745, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1600, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1770, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1664, \"height\": 2243, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1210, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1677, \"height\": 2293, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1560, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 877, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 858, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 832, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1594, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1777, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 911, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1536, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 923, \"height\": 199, \"label\": \"Table\"}]"
motivation: 现有动态架构方法仅扩展网络宽度，未充分利用深度维度的自适应能力。
method: 非参数贝叶斯方法同时推断深度和宽度，用Beta过程和共轭伯努利过程建模与正则化。
result: 在持续学习基准上性能优于或可比肩现有方法，且支持无监督学习。
conclusion: 该方法提供了一种灵活有效的持续学习架构自适应方案。
---

## Abstract
While existing dynamic architecture-based continual learning methods adapt network width by growing new branches, they overlook the critical aspect of network depth. We propose a novel non-parametric Bayesian approach to infer network depth and adapt network width while maintaining model performance across tasks. Specifically, we model the growth of network depth with a beta process and apply drop-connect regularization to network width using a conjugate Bernoulli process. Our results show that our proposed method achieves superior or comparable performance with state-of-the-art methods across various continual learning benchmarks. Moreover, our approach can be readily extended to unsupervised continual learning, showcasing competitive performance compared to existing techniques.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景**：持续学习（continual learning）要求模型顺序学习多个任务，并保持对旧任务的知识，避免灾难性遗忘。
- **现有方法的局限**：动态架构扩展可以增加模型容量，但绝大多数方法仅扩展网络**宽度**（即隐藏层神经元数量），固定网络**深度**（层数）。然而，深度对神经网络表示能力和性能至关重要。
- **本文目标**：提出一种非参数贝叶斯方法，使网络在持续学习过程中能够**同时自适应深度和宽度**，既能根据任务复杂性增长结构，又能通过正则化保留旧知识。

### 2. 方法论

- **整体思路**：利用顺序贝叶斯推断（Sequential Bayes），将前一个任务的后验作为当前任务的先验，同时对网络结构（深度与宽度）和权重实施变分推断。
- **深度建模**：
    - 使用Beta过程（stick-breaking构造）生成每一层的激活概率 `π_l`：`π_l = ∏_{i=1}^l v_i`，其中 `v_l ~ Beta(α, β)`。
    - 该概率控制该层是否被激活及激活程度，理论上有无限深度的可能性（实践中设置截断层数K）。
- **宽度建模**：
    - 在给定层激活概率 `π_l` 下，通过共轭伯努利过程生成权重激活掩码 `Z^{(l)}`（0/1），对权重矩阵 `W^{(l)}` 进行元素级drop-connect正则化。
    - 每层的有效连接由 `W^{(l)} ⊙ Z^{(l)}`，并引入跳跃连接以跳过未激活层。
- **任务增量学习扩展**：
    - 引入权重重要性参数 `γ^{(k)}_{m,n}`，在变分分布中融合 `π_k` 与重要性，训练后生成**任务特定的固定掩码** `Z̄_t`，以进一步隔离任务间干扰。
- **变分目标**：ELBO包含三项KL散度，分别对层激活变量 `v`、权重掩码 `Z` 和权重 `W` 进行从先验（前一任务后验）到后验的约束，平衡新任务适应与旧知识保留。
- **无监督扩展**：将结构推断应用于VAE的解码器，同时使用任务特定编码器，ELBO加入潜在变量KL项。

### 3. 实验设计

- **数据集与场景**：
    - 全连接网络：permuted MNIST、split MNIST、split fashion MNIST（均为5个任务）。
    - 卷积网络（AlexNet backbone）：CIFAR10-5、CIFAR100-10、CIFAR100-20、TinyImagenet-10。
    - 全卷积网络（以实验不同截断深度）。
    - 无监督图像生成：one-MNIST、not-MNIST（10个任务逐类别生成）。
    - 类增量学习（无需任务ID）：CIFAR10-5结合ER-ACE框架与记忆重放。
- **对比基准**：
    - 正则化方法：EWC、VCL、UCL、SFSVI。
    - 动态架构方法：DEN、HAT、SPG、UCB。
    - 贝叶斯结构适应方法：HIBNN、IBPCL。
    - 无监督对比：EWC、VCL、IBPCL及朴素微调。
- **评价指标**：多任务最终平均准确率（任务增量）、测试对数似然（无监督）、类增量准确率。

### 4. 资源与算力

- 论文明确提到训练与评估使用 **NVIDIA A100 GPU**，但未给出具体GPU数量或总训练时长。
- 超参数搜索提到采用网格搜索，并指出使用验证集选择模型权重，计算量中等，但未量化具体开销。

### 5. 实验数量与充分性

- **主要实验表**：
    - 表1：3个MNIST变种数据集，对比9个方法（含本文）。
    - 表2：AlexNet在4个视觉数据集上，对比7个方法。
    - 图4：动态架构方法在不同深度下的性能对比（3个数据集 × 多种K值）。
    - 无监督实验（图5）：两种数据集，与4个方法比较生成质量及对数似然。
    - 消融实验（表3）：两种CNN架构上，对比4种配置（结构适应 + MAP/Bayes权重 + 是否任务掩码）。
    - 类增量案例（表4）：单架构下4种配置。
    - 附录提供宽度M和截断K对性能与推断深度的影响分析、训练时间对比等。
- **公平性**：所有对比方法均使用原论文最佳默认设置或经合理调参，本文超参数经网格搜索确定，任务特定掩码微调与基线保持相同epoch数或合理设计，较为公平。
- **充分性**：覆盖全连接、卷积、全卷积三种骨干，监督/无监督/类增量三种范式，消融验证各个组件的贡献，结构演化可视化，实验充分。

### 6. 主要结论与发现

- 提出的非参数贝叶斯方法在多个基准上取得**超越或匹配SOTA**的性能，尤其在复杂数据集（CIFAR100-20，TinyImagenet）和较长任务链上优势明显。
- 深度和宽度能够**根据任务复杂度自适应演化**：深度随任务增加而增加，浅层激活更密集，深层激活稀疏，结构保持稳定。
- 与其他动态架构相比，本方法对不同截断深度**更鲁棒**，不易因网络层数增加而性能骤降（得益于跳跃连接）。
- 顺序贝叶斯权重推断与任务特定掩码**联合贡献**最大，消融实验证明缺少任何一部分都会导致性能下降。
- 无监督生成场景下，本方法在长期任务链中优于VCL，并在后段任务上超越IBPCL。

### 7. 优点

- **创新性强**：首次在持续学习框架下同时建模网络深度与宽度的非参数贝叶斯自适应，填补动态架构方法的空白。
- **方法统一且可扩展**：一个贝叶斯框架同时支持全连接、CNN、VAE，及监督、无监督、类增量学习。
- **结构演化的可解释性**：可视化展示深度和激活程度随任务增加的自然增长。
- **鲁棒性**：对截断层数K和最大宽度M不敏感，性能在较大范围内保持稳定。
- **消融实验扎实**：分别验证了贝叶斯权重推断与任务特定掩码的作用。

### 8. 不足与局限

- **池化层兼容性问题**：由于推断层数可变，池化层的维度不可预测，作者不得不限定前3层有池化，后续层不使用池化，限制了直接在标准CNN架构上的无缝应用。
- **依赖截断近似**：尽管理论上可无限深，实际依赖截断K，且未强制实施 Russian Roulette 放松截断，可能偏离真实后验。
- **计算开销**：变分推断与多重采样增加训练时间（文中表10显示训练时间相比IBPCL略高或相当，但比VCL显著少），增量微调任务特定掩码也需要额外epoch。
- **元学习或超参敏感度未深入分析**：α、β、温度τ、KL系数等对性能影响未系统报告。
- **类增量场景探索有限**：只在CIFAR10-5的小规模重放场景下测试，未在更大规模或更复杂类增量基准上验证，且记忆重放容量影响未分析。
- **缺乏与最新重放或正则化方法对比**：如DER++、Co2L等近年强基线未纳入对比，比较范围集中在2023年前方法。

（完）
