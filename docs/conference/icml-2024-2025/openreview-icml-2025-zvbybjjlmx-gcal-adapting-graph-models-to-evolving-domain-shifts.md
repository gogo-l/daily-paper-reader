---
title: "GCAL: Adapting Graph Models to Evolving Domain Shifts"
title_zh: "GCAL: 适应图模型以应对持续领域漂移"
authors: "Ziyue Qiao, Qianyi Cai, Hao Dong, Jiawei Gu, Pengyang Wang, Meng Xiao, Xiao Luo, Hui Xiong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zVBYbjjlMX"
tags: ["query:continual"]
score: 9.0
evidence: 图持续自适应学习方法，用双层优化使模型适应持续域漂移
tldr: 针对图域适应中连续域漂移导致的灾难性遗忘问题，提出GCAL方法，通过双层优化，上层适应阶段利用信息最大化微调模型，下层记忆生成阶段依据理论下界生成记忆以重新适应旧域。实验证明GCAL在多个图基准上有效增强了模型可持续性和适应性。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1715, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1773, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1782, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 812, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1756, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1783, \"height\": 332, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zvbybjjlmx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 870, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zvbybjjlmx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1647, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zvbybjjlmx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 222, \"label\": \"Table\"}]"
motivation: 图域适应仅考虑单步偏移，无法处理连续域漂移且会遗忘旧域。
method: 采用双层优化，适应阶段最大化信息，记忆生成阶段基于理论下界生成记忆。
result: 在图分类等任务上展现出持续的适应能力和稳定的抗遗忘性。
conclusion: GCAL为图上的持续自适应学习提供了有效方案。
---

## Abstract
This paper addresses the challenge of graph domain adaptation on evolving, multiple out-of-distribution (OOD) graphs.
Conventional graph domain adaptation methods are confined to single-step adaptation, making them ineffective in handling continuous domain shifts and prone to catastrophic forgetting. This paper introduces the Graph Continual Adaptive Learning (GCAL) method, designed to enhance model sustainability and adaptability across various graph domains. GCAL employs a bilevel optimization strategy. The "adapt" phase uses an information maximization approach to fine-tune the model with new graph domains while re-adapting past memories to mitigate forgetting. Concurrently, the "generate memory" phase, guided by a theoretical lower bound derived from information bottleneck theory, involves a variational memory graph generation module to condense original graphs into memories. Extensive experimental evaluations demonstrate that GCAL substantially outperforms existing methods in terms of adaptability and knowledge retention.

---

## 论文详细总结（自动生成）

# 论文总结：GCAL: Adapting Graph Models to Evolving Domain Shifts

## 1. 研究动机与核心问题
图数据普遍存在于现实世界，但传统图模型在应对**持续演变的域漂移**（即序列到达的多个不同分布的图）时面临两大挑战：
* **单步域适应局限**：现有方法（如基于MMD或对抗学习）只能处理固定的源域-目标域对，无法应付连续到达的新图。
* **灾难性遗忘**：模型在适应新图时会丧失对先前图的知识记忆，导致整体性能持续下降（如Figure 1所示）。
因此，本文旨在解决**图上的无监督持续自适应学习**问题，使模型能依次适应多个未见过的目标图，并同时保留对历史图的判别能力。

## 2. 方法论：GCAL框架
GCAL提出一种**双层优化策略**，当每个新图`G_t`到来时，交替执行两个阶段：

### 2.1 适应与记忆重放阶段（Adaptation with Memory Replay）
* **核心思想**：基于信息最大化（Information Maximization）损失，同时在新图和历史记忆图上微调模型。
* **目标**：`L_AMR = L_Adp(G_t; Θ_{t-1}) + Σ_i L_Adp(Ĝ_i; Θ_{t-1})`
* **信息最大化损失**：鼓励模型输出高置信度（如one-hot向量）且多样化的预测，防止过拟合到少数类别。

### 2.2 变分记忆图生成阶段（Variational Memory Graph Generation）
* **目标**：从当前原始图`G_t`生成一个小型但信息丰富、可泛化的记忆图`Ĝ_t`，存入记忆池供未来重放。
* **理论依据**：基于**信息瓶颈理论**推导出生成记忆图的下界优化目标（定理3.1），包含三项：
    1. 预测对数似然项 → **记忆图学习损失（L_MGL）**：采用梯度匹配，使记忆图模型梯度与原始图模型梯度一致。
    2. KL散度项 → **正则化损失（L_Reg）**：约束生成图的节点特征分布（高斯先验）和边分布（伯努利先验）。
    3. 生成对数似然项 → **生成损失（L_Gen）**：通过节点表征的L2距离最小化记忆图与原始图的分布差异。
* **生成器结构**：使用变分GNN编码出节点均值`μ`和方差`logσ`，通过TopKSelector选出重要节点，利用重参数化技巧和Gumbel-Softmax生成节点特征和邻接矩阵，确保可微。

### 2.3 整体优化
以端到端双层优化形式更新模型参数`Θ`和生成器参数`Φ`：
```
min L_MGL + λ1 L_Reg + λ2 L_Gen   (外层)
s.t. Θ_t = argmin L_AMR           (内层)
```
采用指数移动平均（EMA）平滑参数更新。

## 3. 实验设计

### 3.1 数据集
* **区域漂移**：**Twitch-Explicit**（7个不同国家的社交网络，ROC-AUC评估）和**Facebook-100**（12个美国大学网络，准确率评估）。
* **时间漂移**：**Elliptic**（41个连续的比特币交易图，F1分数评估）和**OGB-Arxiv**（11个按时间划分的引文网络，准确率评估）。

### 3.2 对比基准
分为三类：
* **无适应下界**：Test（直接推理）。
* **单步测试时适应**（No Rehearsal）：DANN, Tent, BN Stats Adapt, EERM, GTRANS。
* **持续测试时适应**（Continual TTA）：CoTTA, EATA。
所有非图原生方法均替换为GCN骨干以保证公平。

### 3.3 评估指标
* **平均性能（AP）**：最后模型在所有历史域上的平均表现，衡量适应能力。
* **平均遗忘（AF）**：最终性能与学习该域时性能的平均差值，衡量记忆保持。

## 4. 资源与算力
论文正文**未明确说明**GPU型号、数量或训练具体时长的算力信息。致谢部分提及使用大湾区大学松山湖HPC中心资源，但未给出详细规格。代码已开源，可从仓库推断大致需求。

## 5. 实验体量与充分性
实验设计全面且客观：
* **主实验**：在4个数据集上与8个基线对比，重复5次报告均值和标准差（Table 2）。
* **动态分析**：可视化AP随域数量增加的变化曲线（Figure 3）和性能矩阵热力图（Figure 4, 7），细致展示遗忘过程。
* **消融研究**：移除`L_Reg`、`L_Gen`、所有正则项、EMA共4种变体（Table 3），验证各组件贡献。
* **超参数分析**：探究合成图节点比率的影响（Figure 5）。
* **可视化**：对比原始图与生成记忆图的结构（Figure 6）。
* **骨干网络泛化**：测试GCN、GSAGE、GAT、GIN等不同骨干下的效果（Figure 8）。 实验对比公平，充分证明GCAL的有效性和稳健性。

## 6. 主要结论与发现
GCAL在所有数据集上**AP和AF均显著超越**现有方法，有效缓解了图上的灾难性遗忘。其双层优化和基于信息瓶颈的记忆生成能够浓缩并复用关键历史知识，使模型在持续适应新图时维持高性能，实现了图模型的可持续复用。

## 7. 方法优点
* **问题新颖**：首次系统提出并解决了**无监督图持续域适应**问题。
* **理论支撑**：通过信息瓶颈理论推导记忆生成目标，并设计具体的可优化下界。
* **结构轻量**：生成的小型记忆图显著降低了重放开销，同时保留关键信息。
* **性能卓越**：在多个跨域、跨时间的图任务上大幅领先最先进的持续适应基线。

## 8. 不足与局限
* **模型架构未改进**：GCAL聚焦于适应策略，未调整图分类器架构本身，若预训练的骨干网络对复杂图表达能力不足，可能形成瓶颈。
* **无监督生成局限**：记忆生成完全依赖模型预测信号（伪标签），可能受到噪声标签和错误累积的影响，在极端不平衡或高风险场景可靠性需验证。
* **计算效率未详述**：尽管生成小图可节省重放成本，但生成过程本身涉及双层梯度和变分推断，其在大规模图上的实时性未充分讨论。
* **实验边界**：仅考虑了节点分类任务，未扩展到图分类或链接预测等更广泛的图学习场景。

（完）
