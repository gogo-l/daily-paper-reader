---
title: A Selective Learning Method for Temporal Graph Continual Learning
title_zh: 面向时序图持续学习的选择性学习方法
authors: "Hanmo Liu, Shimin Di, Haoyang LI, Xun Jian, Yue Wang, Lei Chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=BKnssDRh7d"
tags: ["query:continual"]
score: 9.0
evidence: 时序图持续学习的选择性学习方法
tldr: 针对时序图学习中节点类不断新增导致遗忘旧类的问题，该研究定义时序图持续学习新问题，并提出选择性学习框架LTF。方法通过用旧类子集替换全部旧数据并进行面向未来的学习，有效平衡新旧知识。实验证明LTF能高效维护旧类知识并适应新类，为动态图数据上的持续学习提供了新思路。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 828, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1753, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 823, \"height\": 248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 862, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1752, \"height\": 354, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 894, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1765, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 853, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 669, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 703, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 832, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 853, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1764, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1760, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 680, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1767, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1766, \"height\": 253, \"label\": \"Table\"}]"
motivation: 时序图中新节点类不断涌现，需要高效维护旧类知识。
method: 提出LTF框架，通过选择旧类子集学习以维持面向未来的知识。
result: 实现了对新旧类知识的平衡更新，避免遗忘。
conclusion: 为时序图持续学习提供了有效方案。
---

## Abstract
Node classification is a key task in temporal graph learning (TGL). Real-life temporal graphs often introduce new node classes over time, but existing TGL methods assume a fixed set of classes. This assumption brings limitations, as updating models with full data is costly, while focusing only on new classes results in forgetting old ones. Graph continual learning (GCL) methods mitigate forgetting using old-class subsets but fail to account for their evolution. We define this novel problem as temporal graph continual learning (TGCL), which focuses on efficiently maintaining up-to-date knowledge of old classes. To tackle TGCL, we propose a selective learning framework that substitutes the old-class data with its subsets, Learning Towards the Future (LTF). We derive an upper bound on the error caused by such replacement and transform it into objectives for selecting and learning subsets that minimize classification error while preserving the distribution of the full old-class data. Experiments on three real-world datasets show that LTF effectively addresses the TGCL challenge.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **问题定义**：真实世界的时序图（Temporal Graph）不断引入新的节点类别，且旧类数据随时间演化。现有时序图学习方法（TGL）假设类别固定，无法适应这种开放类动态；而图持续学习方法（GCL）虽能缓解灾难性遗忘，却假定旧类数据是静态的，导致模型在未来的时序图上过时。
- **研究动机**：需要一种既能高效学习新类，又能持续更新旧知识以跟上数据演化的方法。
- **核心贡献**：首次定义 **时序图持续学习（TGCL）** 问题，提出 **面向未来的学习框架（Learning Towards the Future, LTF）**，通过选择代表性旧类子集进行学习，并给出理论误差上界，将子集选择转化为可优化的目标。

## 2. 论文提出的方法论
### 核心思想
- 在每一个新时间周期 \(T_N\)，从旧类数据 \(G^{old}_N\) 中选取一个小子集 \(G^{sub}_N\) 来近似整个旧类分布，从而高效地更新模型，使其同时具备对新类的分类能力和对演化后的旧类的判别力。

### 误差上界与选择准则
- 利用域适应理论，推导出用子集学习时在完整旧类数据上的分类误差上界（定理3.1）：
  \[
  \min_{h} \epsilon(h|G^{old}_N) \le \min_{h, G^{sub}_N} \left[ \epsilon(\tilde{h}^{sub}_N|G^{old}_N) + \frac12 d_{\mathcal{H}\Delta\mathcal{H}}(G^{old}_N, G^{sub}_N) + \epsilon(h, \tilde{h}^{sub}_N|G^{sub}_N) \right]
  \]
- 基于该上界，选择目标转化为同时最小化子集的分类误差和分布差异：
  \[
  \tilde{G}^{sub}_N = \arg\min_{G^{sub}_N} \left[ \alpha \hat{\epsilon}(\tilde{h}_{N-1}|G^{sub}_N) + \hat{d}^2_{MMD}(G^{old}_N, G^{sub}_N|\tilde{h}_{N-1}) \right]
  \]

### 子集选择算法
- 使用上一周期模型 \(\tilde{h}_{N-1}\) 来近似当前周期的子集误差和提取嵌入。
- 分类误差项天然是单调次模的，MMD平方项在适当核函数下也被证明是单调次模函数（参见Kim et al., 2016）。因此整体选择目标为单调次模，可用贪心算法近似，保证 \((1-1/e)\) 的近似比。
- 定义节点级别的 **witness function** \(j(v_t) = \alpha j_{cls}(v_t) + j_{MMD}(v_t)\)，每次选择使该值最小的节点加入子集。
- 为降低计算复杂度，将 \(G^{old}_N\) 随机划分为多个分区，在每个分区内贪心选取子集再合并。

### 模型优化
- 学习阶段，除了用 \(G^{sub}_N\) 的分类损失，还额外引入一个 **分布对齐损失**：选取另一个仅最小化 MMD 的子集 \(G^{sim}_N\)，令 \(G^{sub}_N\) 的嵌入分布向 \(G^{sim}_N\) 对齐（使用带停止梯度的简化 MMD）。
- 最终训练目标：
  \[
  l_{tot} = \hat{\epsilon}(h|G^{new}_N) + \hat{\epsilon}(h|G^{sub}_N) + \beta l_{dst}(G^{sim}_N, G^{sub}_N|h)
  \]

## 3. 实验设计
### 数据集
- **Yelp**：2014–2019年，5个周期，每周期引入3个新类别，共15类。
- **Reddit**：20天为一周期，共3个周期，每周期引入5个新类别，共15类。
- **Amazon**：24天为一周期，共3个周期，每周期引入3个新类别，共9类。
- 数据集统计信息见表1，构建方式类似OTGNet但适配TGCL定义。

### 基准模型与对比方法
- **主干模型**：经典 TGAT 和最新 DyGFormer。
- **对比方法**：
  - 联合训练（Joint，上限）与仅微调（Finetune，下限）。
  - 经典持续学习：EWC、LwF、iCaRL。
  - 图持续学习：ER、SSM、OTGNet、URCL。
- **评价指标**：平均精度（AP）、平均遗忘（AF）、每周期平均训练时间（Time）。

## 4. 资源与算力
- **硬件**：Nvidia A30 GPU（24 GB显存）。
- 训练配置：每周期训练 100 epoch，批大小 600，学习率 \(1\times10^{-5}\)，dropout 0.4，早停机制。
- 文中报告的 Time 为最后一个周期（数据量最大）的平均每轮训练时间（秒），未明确给出整体训练时长或GPU数量。

## 5. 实验数量与充分性
实验设计丰富，涵盖：
- **主实验**（表2）：3个数据集 × 2种骨干网络，对比10种方法（含Joint/Finetune），展示AP、AF、Time及标准差。
- **消融实验**（表3）：考察选择中的误差项、分布项以及学习中的分布对齐损失分别的作用。
- **分区方法对比**（表4）：随机、K-means、层次聚类分区的影响。
- **超参数敏感性分析**（图5）：α、β、子集大小 m 和 m' 对 AP 的影响。
- **效率-性能权衡**（表5）：改变m与m'观察AP和时间变化。
- **案例研究**：
  - 使用MLP替代TGNN（表6），证明图结构的必要性。
  - 构建更大规模数据 Reddit-Large（32类，16周期）和 Reddit-Long（24类，4周期）测试 scalability（表7）。
- 所有实验均报告多次随机种子的均值和标准差，与基线的超参搜索也保持公平，实验充分且客观。

## 6. 论文的主要结论与发现
- LTF 在所有数据集和骨干模型上均取得了最优平均精度和最低遗忘，同时维持了合理的训练效率。
- 选择子集时同时考虑分类误差和分布相似性缺一不可，加入分布对齐损失可进一步提升。
- 随机分区即可较好地保留原始数据分布，聚类方法反而破坏分布导致性能下降。
- LTF 对超参具备一定鲁棒性，且在更大规模场景下仍优于基线方法。

## 7. 优点
- **理论驱动**：首次给出 TGCL 问题中子集选择的误差上界，并将子集选择问题转化为单调次模优化，具有理论保证。
- **模块化与通用性**：框架与具体骨干TGL模型解耦，可适配TGAT、DyGFormer等。
- **实用效率**：通过分区和简化MMD计算大幅降低复杂度，在效果和效率间取得良好平衡。
- **实验全面**：覆盖多种数据集、骨干、基线，并设计了充分的消融和 scalability 测试。

## 8. 不足与局限
- **内存与计算开销**：仍然需要存储 \(G^{sub}\) 和 \(G^{sim}\) 两个子集，且分布对齐损失的计算复杂度为 \(O(m m')\)，当子集增大时成本上升较快。
- **依赖于历史模型**：选择阶段利用上一周期的模型 \(\tilde{h}_{N-1}\) 来近似评估，若历史模型与当前数据分布差异较大，可能影响选择质量。
- **任务限制**：本文仅聚焦于节点分类任务，未涉及链路预测等其他重要时序图任务。
- **真实大规模应用**：虽然测试了 Reddit-Large 和 Long，但节点规模仍有限，在超大规模图（如数十亿边）上的适用性有待验证。
（完）
