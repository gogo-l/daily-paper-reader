---
title: A Selective Learning Method for Temporal Graph Continual Learning
title_zh: 面向时序图持续学习的选择性学习方法
authors: "Hanmo Liu, Shimin Di, Haoyang LI, Xun Jian, Yue Wang, Lei Chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=BKnssDRh7d"
tags: ["query:continual"]
score: 8.0
evidence: 提出选择性学习框架以防止时序图持续学习中的遗忘
tldr: 针对时序图中新类别不断出现、现有方法在更新模型时遗忘旧类别的问题，定义时序图持续学习，并提出选择性学习框架LTF，动态选择旧类数据子集，面向未来维持知识。在多个时序图节点分类任务上显著减轻灾难性遗忘，高效适应图演化。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 828, \"height\": 653, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1781, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1753, \"height\": 351, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 823, \"height\": 248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 862, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 862, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-bknssdrh7d/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1752, \"height\": 354, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 868, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1765, \"height\": 894, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1765, \"height\": 301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 853, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 669, \"height\": 557, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 703, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 832, \"height\": 295, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 853, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1764, \"height\": 441, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1760, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 680, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1767, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-bknssdrh7d/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1766, \"height\": 253, \"label\": \"Table\"}]"
motivation: 时序图新增节点类别导致模型遗忘旧类别，且全面重训代价高。
method: 设计面向未来的选择性学习框架LTF，动态选择旧类数据子集。
result: 在多个时序图上实现了高效、低遗忘的持续节点分类。
conclusion: 为图持续学习中的时序演化提供了一种有效解决方案。
---

## Abstract
Node classification is a key task in temporal graph learning (TGL). Real-life temporal graphs often introduce new node classes over time, but existing TGL methods assume a fixed set of classes. This assumption brings limitations, as updating models with full data is costly, while focusing only on new classes results in forgetting old ones. Graph continual learning (GCL) methods mitigate forgetting using old-class subsets but fail to account for their evolution. We define this novel problem as temporal graph continual learning (TGCL), which focuses on efficiently maintaining up-to-date knowledge of old classes. To tackle TGCL, we propose a selective learning framework that substitutes the old-class data with its subsets, Learning Towards the Future (LTF). We derive an upper bound on the error caused by such replacement and transform it into objectives for selecting and learning subsets that minimize classification error while preserving the distribution of the full old-class data. Experiments on three real-world datasets show that LTF effectively addresses the TGCL challenge.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- 时序图（temporal graph）在真实场景中随着时间推移会不断出现新的节点类别，现有方法存在两个极端：
  - **时序图学习（TGL）方法**假设类别集合固定，无法处理开放类别。
  - **图持续学习（GCL）方法**虽用旧类样本回放抑制遗忘，但假设旧类数据不再演化，不适用于动态变化的旧类分布。
- 论文将这一新问题定义为 **时序图持续学习（TGCL）**：在新时期既要学习新类别，又要高效地保持旧类别的最新知识，避免因完全微调新数据而遗忘旧类，或因用全部数据重训而效率低下。
- 整体目标：在效率和有效性之间取得平衡，使模型能够“面向未来”地选择性保留和更新旧类知识。

## 2. 方法论：Learning Towards the Future（LTF）框架
### 2.1 核心思想
- 用旧类的代表性子集近似完整旧类数据，基于**领域适配理论**推导出用子集替代全量数据所带来的分类误差上界，并将上界转化为可优化的子集选择和模型学习目标。

### 2.2 误差上界与选择目标
- **定理3.1**给出在旧类分布 \(G^{old}_N\) 上的分类误差上界：
  \[
  \min_h \epsilon(h|G^{old}_N) \le \min_{h, G^{sub}_N} \big[
  \underbrace{\epsilon(\tilde{h}^{sub}_N|G^{old}_N)}_{\text{子集模型的泛化误差}} + \tfrac12 d_{\mathcal{H}\Delta\mathcal{H}}(G^{old}_N, G^{sub}_N) + \underbrace{\epsilon(h,\tilde{h}^{sub}_N|G^{sub}_N)}_{\text{知识迁移误差}}
  \big].
  \]
- 选择子集时，忽略未知 \(h\) 的项，将目标近似为：
  \[
  \tilde{G}^{sub}_N = \arg\min_{G^{sub}_N} \left[ \alpha \hat{\epsilon}(\tilde{h}_{N-1}|G^{sub}_N) + \hat{d}^2_{MMD}(G^{old}_N, G^{sub}_N|\tilde{h}_{N-1}) \right],
  \]
  其中第一项用历史模型 \(\tilde{h}_{N-1}\) 近似子集损失，第二项用最大均值差异（MMD）衡量分布差异。

### 2.3 子集选择与学习
- **贪婪选择**：证明该目标为单调次模函数，可通过贪婪算法以 \(1-1/e\) 近似最优。为每个候选点定义 **witness function** \(j(v) = \alpha j_{cls}(v) + j_{MMD}(v)\)，选择函数值最小的点。
- **计算加速**：将 \(G^{old}_N\) 随机划分为 \(W\) 组，每组独立选取子集，将复杂度从 \(O((r+m)^2)\) 降至 \(O((r+m)^2/W^2)\)。
- **分布对齐学习**：训练时额外引入一个模拟分布的子集 \(G^{sim}_N\)（仅最小化 MMD 选出），在模型 \(h\) 上对齐该子集与 \(G^{sub}_N\) 的嵌入分布，损失项为：
  \[
  l_{dst}(G^{sub}_N, G^{sim}_N|h) = -\frac{2}{|G^{sub}_N||G^{sim}_N|} \sum_{v\in G^{sub}_N, u\in G^{sim}_N} k(v, \text{sg}(u)|h).
  \]
  通过停止梯度回传简化计算。

### 2.4 总体流程
1. 将旧类数据随机分组，每组贪婪选出 \(m/W\) 个样本构成 \(G^{sub}_N\) 和 \(G^{sim}_N\)。
2. 合并子集，联合新类数据 \(G^{new}_N\) 训练模型：
   \[
   l_{tot} = \hat{\epsilon}(h|G^{new}_N) + \hat{\epsilon}(h|G^{sub}_N) + \beta\, l_{dst}(G^{sim}_N, G^{sub}_N|h).
   \]

## 3. 实验设计
### 3.1 数据集
- **Yelp**：2014–2019年，5个时期，每期新增3个类别，约2万节点、232万事件。
- **Reddit**：20天为一期，共3期，每期新增5个类别，约1.3万节点、31万事件。
- **Amazon**：类似Yelp构造，24天一期，共3期，每期新增3个类别，约8.5万节点、87万事件。

### 3.2 对比方法
- **朴素基线**：Joint（全量重训，性能上界但效率低）、Finetune（仅新数据微调）。
- **经典持续学习方法**：EWC、LwF（正则化）；iCaRL（基于嵌入均值的回放）。
- **图持续学习方法**：ER（随机回放）、SSM（结构依赖回放）、OTGNet（重要与多样性三元组回放）、URCL（统一回放框架）。
- 骨干网络：**TGAT** 与 **DyGFormer**。

### 3.3 评价指标
- **AP（平均精度）**：当前时期所有已见类别精度的均值。
- **AF（平均遗忘）**：相对于 Joint 的精度下降，越小越好。
- **Time**：最新时期每轮训练平均时间。

## 4. 资源与算力
- 实验使用 **Nvidia A30 GPU**（24GB显存），未提及多卡并行。
- 训练配置：每个时期训练 **100** epochs，batch size = 600，早停 patience = 20。
- 为适应显存限制，选择子集时对旧类数据进行了随机分区（每个分区约1万样本）。
- 未明确报告总训练时长，仅对比了各类方法的每轮耗时。

## 5. 实验数量与充分性
- **主实验**：3个数据集 × 2种骨干 × 约10种方法，全面对比 AP、AF、Time。
- **消融实验**：分析选择目标中的误差项和分布项、训练中加入分布对齐损失的影响；对比随机/聚类分区方式。
- **超参数敏感性**：调节 \(\alpha\)、\(\beta\)、子集大小 \(m\)、模拟集大小 \(m'\)，考察对 AP 的影响。
- **效率‑性能权衡**：改变 \(m\) 和 \(m'\) 观察 Time 与 AP 变化。
- **额外验证**：MLP 替代图神经网络说明拓扑必要性；构建更大规模的 Reddit‑Large/Long 数据集测试可扩展性。
- **综合评估**：实验设计丰富、对比公平，消融和敏感性分析较完整，整体论证充分。

## 6. 主要结论与发现
- LTF 在所有数据集和骨干下均取得**最高的 AP 和最低的 AF**，效率优于多数 GCL 方法，明显优于 OTGNet 且耗时更低。
- 子集选择时**同时考虑分类误差和分布相似性**至关重要，单一因素效果显著下降。
- 训练中引入分布对齐损失（\(l_{dst}\)）能进一步提升性能。
- **随机分区**简单且有效，k‑means 或层次聚类分区反而可能破坏原始分布，降低效果。
- LTF 对子集大小鲁棒性良好，适当增大 \(m\) 可稳定提升精度。

## 7. 优点
- **第一篇**系统定义并解决时序图持续学习问题，融合开放类别和旧类演化两个现实挑战。
- 提供**理论支撑**：从领域适配角度导出误差上界，指导子集选择和学习。
- 方法**与模型无关**，可灵活适配 TGAT、DyGFormer 等不同时序图神经网络。
- 计算上利用**贪婪次模优化**和**随机分区**大幅降低子集选择复杂度，兼具效率和有效性。
- 实验**全面扎实**，涵盖多种基线、消融、超参数分析及更大规模场景。

## 8. 不足与局限
- 仅探索**节点分类**任务，未在链接预测等更复杂的时序图任务上验证。
- 子集选择依赖**历史模型** \(\tilde{h}_{N-1}\) 作为近似，若历史模型质量差可能影响选择效果。
- 分布对齐使用简单**随机分区**，虽实验证明有效，但在极端分布差异下可能不足。
- 训练中仍需存储和回放部分旧数据（子集），隐私敏感场景可能受限。
- 在极端长序列或类增量剧烈的场景下，子集选择与正则化的长期稳定性未作深入讨论。
- 未对比某些最新的持续学习方法（如基于生成重放的 GCL 方法）。

（完）
