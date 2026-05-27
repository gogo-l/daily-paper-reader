---
title: Bayesian Adaptation of Network Depth and Width for Continual Learning
title_zh: 面向持续学习的网络深度与宽度贝叶斯自适应
authors: "Jeevan Thapa, Rui Li"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=c9HddKGiYk"
tags: ["query:continual"]
score: 9.0
evidence: 贝叶斯方法自适应网络深度和宽度以减少遗忘
tldr: 针对现有动态架构持续学习忽略网络深度扩展的问题，提出一种非参数贝叶斯方法，利用贝塔过程建模深度增长、Bernoulli过程正则化宽度，动态扩展网络以保留旧知识并学习新任务。实验在多种基准上取得领先性能，并可扩展至无监督学习，为可扩展持续学习提供了新途径。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1002, \"height\": 719, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 602, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1236, \"height\": 472, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1745, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1764, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1600, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1770, \"height\": 439, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1664, \"height\": 2243, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1210, \"height\": 1186, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c9hddkgiyk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1677, \"height\": 2293, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 502, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1560, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 877, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 858, \"height\": 247, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 832, \"height\": 204, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1594, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1777, \"height\": 376, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 911, \"height\": 199, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1536, \"height\": 238, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c9hddkgiyk/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 923, \"height\": 199, \"label\": \"Table\"}]"
motivation: 现有动态架构方法忽略网络深度扩展，导致持续学习中容量不足。
method: 利用贝塔过程和共轭伯努利过程分别建模深度增长与宽度正则化。
result: 在多个基准上性能与最优方法相当或更优，且可扩展至无监督场景。
conclusion: 提出的贝叶斯自适应方法为持续学习提供了灵活的架构扩展方案。
---

## Abstract
While existing dynamic architecture-based continual learning methods adapt network width by growing new branches, they overlook the critical aspect of network depth. We propose a novel non-parametric Bayesian approach to infer network depth and adapt network width while maintaining model performance across tasks. Specifically, we model the growth of network depth with a beta process and apply drop-connect regularization to network width using a conjugate Bernoulli process. Our results show that our proposed method achieves superior or comparable performance with state-of-the-art methods across various continual learning benchmarks. Moreover, our approach can be readily extended to unsupervised continual learning, showcasing competitive performance compared to existing techniques.

---

## 论文详细总结（自动生成）

## 一、论文核心问题与整体含义

- 研究背景：持续学习要求模型在依次学习新任务的同时，不灾难性地遗忘旧知识。现有的动态架构方法大多只能自适应网络宽度（增加新分支），但忽视了网络深度的调整，而深度对模型性能至关重要。
- 核心问题：如何在持续学习中同时自适应网络的深度和宽度，以在容量扩展与知识保留之间取得更好的平衡。
- 整体含义：提出一种非参数贝叶斯方法，将深度增长建模为贝塔过程，宽度正则化建模为伯努利过程，实现任务驱动下的网络结构渐进式生长，提升模型在多种持续学习场景下的表现。

## 二、方法论

- 核心思想：将神经网络视为具有无限深度的结构，通过贝塔过程的stick-breaking构造控制逐层激活概率，利用共轭伯努利过程为每层权重施加二元掩码，实现动态宽度调整。同时引入跳跃连接，允许模型跳过未激活层直接与输出头相连。
- 关键技术细节：
  - 贝塔过程建模深度：每一层激活概率 \( v_l \sim \text{Beta}(\alpha, \beta) \)，层激活概率 \( \pi_l = \prod_{i=1}^l v_i \)。
  - 伯努利过程建模宽度：权重激活掩码 \( z^{(l)}_{m,n} \sim \text{Ber}(\pi_l) \)，对权重 \( W^{(l)} \) 施加逐元素乘法，实现drop-connect。
  - 变分推断：采用截断式结构化变分分布 \( q(v,Z,W) \) 近似后验，使用具体伯努利松弛处理离散掩码，并利用重参数化技巧进行梯度估计。
  - 顺序贝叶斯框架：将上一任务的后验作为当前任务的先验，ELBO包含对数似然项以及结构（深度、宽度）和权重的KL散度正则化项，实现新旧知识的折衷。
  - 任务增量学习扩展：引入权重重要性参数 \(\gamma\) 到变分分布中，生成任务专属的二元掩码，并允许对掩码微调。
  - 无监督扩展：将结构推断集成到VAE的解码器中，通过ELBO正则化解码器结构与权重，保留生成能力。
- 公式或算法流程（文字说明）：
  - 前向传播时，每层输出为 \( h_l = \sigma((W^{(l)} \odot Z^{(l)})h_{l-1}) + h_{l-1} \)。
  - 变分下界 L(t) 包含期望似然、结构变量 v 的 KL 散度、掩码 Z 的 KL 散度和权重 W 的 KL 散度。
  - 训练阶段使用 Concrete Bernoulli 采样掩码，测试阶段用离散伯努利。

## 三、实验设计

- 数据集与场景：
  - 全连接网络（Fully-connected）：Permuted MNIST、Split MNIST、Split Fashion MNIST（各含5个任务）。
  - 卷积网络：CIFAR10-5, CIFAR100-10, CIFAR100-20, TinyImageNet-10。
  - 无监督学习：one-MNIST 和 not-MNIST 图像序列生成。
  - 类增量学习：CIFAR10-5 结合 ER-ACE 框架。
- Benchmark 对比方法：
  - 正则化方法：EWC、VCL、UCL、SFSVI。
  - 动态架构方法：DEN、HAT、HIBNN、IBPCL、SPG。
  - 无监督方法：Naive、EWC、VCL、IBPCL。
- 评价指标：最终平均准确率（监督任务）、测试对数似然（无监督任务）。

## 四、资源与算力

- 论文中提到“We trained and evaluated our models in NVIDIA A100 GPUs.” 但未明确给出GPU数量、单次实验训练耗时等具体算力细节。

## 五、实验数量与充分性

- 实验组数：
  - 全连接网络：分别在3个MNIST变种上与11种方法比较。
  - CNN（AlexNet 和全卷积）：与7种方法在4个视觉数据集上比较。
  - 消融实验：比较结构适应、贝叶斯权重推断、任务专属掩码的组合效果（AlexNet 和 fullyConv-7）。
  - 深度适应分析：对比不同截断层数下自身及HAT、IBPCL的稳健性。
  - 无监督生成实验：定性生成结果和定量对数似然比较。
  - 类增量学习案例：与ER-ACE结合，验证结构适应的增益。
  - 额外分析：最大宽度、截断层数对推断深度的影响，各层掩码IoU，任务间性能保留曲线等。
- 充分性与公平性：
  - 对比方法涵盖主流基线，超参数按原文最佳设置。自身方法选参通过网格搜索。每个实验重复5次汇报均值和标准差。实验设计考虑多维度（监督/无监督、任务增量/类增量、不同网络结构），总体较为充分客观。

## 六、主要结论与发现

- 所提方法在多种基准上达到或超越最优水平，尤其在 Split Fashion MNIST、CIFAR100-20、TinyImageNet-10 等较复杂任务上表现最佳。
- 网络深度和宽度均能根据任务复杂度自适应增长，深层网络结构变化不会导致性能崩溃（得益于跳跃连接和贝叶斯推断）。
- 顺序贝叶斯权重推断和任务专属掩码对性能均有显著贡献，组合使用效果最优。
- 在无监督持续生成任务中，方法优于VCL且与IBPCL相当或更优，尤其在长任务序列中保持优势。
- 可灵活扩展至类增量学习，进一步改善代表性变化和忘记问题。

## 七、优点

- 方法创新：首次在持续学习中同时自适应深度和宽度，利用贝塔-伯努利过程统一建模。
- 灵活可扩展：兼容全连接、卷积等不同骨干网络，可应用于监督、无监督和类增量学习。
- 实验全面：涵盖多种数据集、任务类型和对比方法，包含消融和深度分析，验证各部分贡献。
- 实现细节：结合跳跃连接、具体分布松弛、结构化变分推断等实用技巧，保证训练稳定性。

## 八、不足与局限

- 未提供计算开销详细对比，仅给出个别案例的训练时间，无法完整评估效率。
- 池化层导致的维度变化限制了卷积层深度推断的灵活性，文中仅在部分设计上避免或绕过该问题。
- 类增量学习实验仅在一个数据集上与单一基线结合，未能展示更广泛类增量设定下的竞争力。
- 无监督实验固定截断层数为2，未展示更复杂生成模型（如更宽或更深的VAE）的表现。
- 消融实验限于CIFAR10-5，未涵盖所有数据集，可能低估部分组件在其他场景的作用。
- 没有讨论超参数（如 \(\alpha,\beta\)）的敏感性以及不同任务顺序下的影响。

（完）
