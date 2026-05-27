---
title: "GCAL: Adapting Graph Models to Evolving Domain Shifts"
title_zh: GCAL：使图模型适应不断演变的领域漂移
authors: "Ziyue Qiao, Qianyi Cai, Hao Dong, Jiawei Gu, Pengyang Wang, Meng Xiao, Xiao Luo, Hui Xiong"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=zVBYbjjlMX"
tags: ["query:continual"]
score: 9.0
evidence: 图域持续适应克服灾难性遗忘
tldr: 传统图域适应方法仅限于单步迁移，无法处理域连续漂移并导致灾难性遗忘。该工作提出图持续自适应学习（GCAL），采用双层优化：适应阶段利用信息最大化微调模型并重放历史记忆，记忆生成阶段基于信息瓶颈理论下界构建代表性记忆，理论推导与实验表明GCAL能有效应对多域漂移，实现模型持续适应。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 404, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1715, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1773, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1782, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 812, \"height\": 668, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1756, \"height\": 692, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1778, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-zvbybjjlmx/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1783, \"height\": 332, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-zvbybjjlmx/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 870, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zvbybjjlmx/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1647, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-zvbybjjlmx/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 859, \"height\": 222, \"label\": \"Table\"}]"
motivation: 图域适应中连续漂移导致灾难性遗忘。
method: 双层优化结合信息最大化和记忆重放，理论下界指导。
result: 在多域漂移图数据上实现可持续适应，超越单步方法。
conclusion: 为图数据提供可抵抗遗忘的持续域适应方案。
---

## Abstract
This paper addresses the challenge of graph domain adaptation on evolving, multiple out-of-distribution (OOD) graphs.
Conventional graph domain adaptation methods are confined to single-step adaptation, making them ineffective in handling continuous domain shifts and prone to catastrophic forgetting. This paper introduces the Graph Continual Adaptive Learning (GCAL) method, designed to enhance model sustainability and adaptability across various graph domains. GCAL employs a bilevel optimization strategy. The "adapt" phase uses an information maximization approach to fine-tune the model with new graph domains while re-adapting past memories to mitigate forgetting. Concurrently, the "generate memory" phase, guided by a theoretical lower bound derived from information bottleneck theory, involves a variational memory graph generation module to condense original graphs into memories. Extensive experimental evaluations demonstrate that GCAL substantially outperforms existing methods in terms of adaptability and knowledge retention.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
本文关注图模型在多域连续漂移下的适应问题。传统图域适应方法仅支持单步迁移，无法应对域分布随时间/地域持续变化的情形，且极易发生灾难性遗忘（模型在新图上适应后旧图性能骤降）。为此，论文提出**图持续自适应学习（GCAL）**，旨在实现模型在连续到来的、无标签的、分布外（OOD）图序列上进行持续适应和稳定推理，同时保留对历史图的知识。整体含义是：赋予图模型持续演进的能力，确保其在不断变化的真实世界图数据中可持续复用。

### 2. 论文提出的方法论
GCAL采用双层优化：“适应（adapt）”阶段和“生成记忆（generate memory）”阶段，二者交替执行。
- **适应与记忆重放**：对新到图 \(G_t\)，用信息最大化损失（熵最小化+多样性正则）微调模型；同时重放之前存储的小型记忆图 \(\{\hat{G}_i\}_{i=1}^{t-1}\) 上的相同损失，以抵抗遗忘。总适应目标定义为：
  \[
  \mathcal{L}_{AMR} = \mathcal{L}_{Adp}(G_t; \Theta_{t-1}) + \sum_{i=1}^{t-1} \mathcal{L}_{Adp}(\hat{G}_i; \Theta_{t-1})
  \]
- **变分记忆图生成**：基于**信息瓶颈理论**推导出记忆图应保留任务相关信息、压缩无关信息的下界：
  \[
  \mathcal{L}(\Phi) \ge \mathbb{E}[\log P_f(\hat{Y}_t|\hat{G}_t)] - \beta \mathbb{E}[KL(P_g(\hat{G}_t|G_t,Z_t)\| Q(\hat{G}_t))] + \beta \mathbb{E}[\log(P_g(\hat{G}_t|G_t,Z_t))]
  \]
  据此设计记忆图生成器，包含：
  - **变分GNN编码器**：输出节点均值、方差，经TopK选择得到K个关键节点，通过重参数采样生成节点特征。
  - **图结构学习**：利用节点特征和Gumbel重参数生成边权重。
  - **三个损失**：`LMGL` (梯度匹配的压缩损失，使记忆图梯度与原图梯度一致)； `LReg` (KL正则，使记忆图分布接近先验)； `LGen` (分布差异损失，最小化记忆图与原图在模型隐藏表示上的L2距离)。
最终目标为：
\[
\min_{\hat{G}_t,\Phi} \mathcal{L}_{MGL} + \lambda_1 \mathcal{L}_{Reg} + \lambda_2 \mathcal{L}_{Gen} \quad \text{s.t.} \quad \Theta_t = \arg\min_{\Theta} \mathcal{L}_{AMR}
\]
模型参数更新使用指数移动平均（EMA）平滑。

### 3. 实验设计
- **数据集**：
  - 区域漂移：**Facebook-100**（12个大学社交网）、**Twitch-Explicit**（7个地区网络）。
  - 时间漂移：**OGB-Arxiv**（论文引用，11个时间段）、**Elliptic**（比特币交易，41个快照）。
  选取部分域预训练，其余域按序进行无监督持续适应。
- **基线方法**：
  - 无适应下限：Test。
  - 单步域适应：DANN (对抗)、Tent (熵最小化)、BN Stats Adapt、EERM (图特化风险最大化)、GTrans (图变换)。
  - 持续测试时适应：CoTTA (权重平均+神经元重置)、EATA (高效适应+Fisher正则)。
- **评估指标**：平均性能(AP)和平均遗忘(AF)。AP为最终模型在所有域上的平均指标，AF衡量最终相对初见时的性能下降。

### 4. 资源与算力
论文正文及附录中未明确提供GPU型号、数量、训练时长等算力信息。仅在致谢中感谢松山湖HPC中心提供算力支持。因此，无法得知具体使用的硬件资源。

### 5. 实验数量与充分性
- 4个数据集×9种方法（含GCAL）的完整对比，给出AP和AF标准差。
- 动态性能曲线（图3）展示域数递增时的AP变化。
- 性能矩阵对比GCAL与CoTTA在个别数据集上的热力图。
- 消融实验：去掉`LReg`&`LGen`、单独去掉`LReg`、去掉`LGen`、去掉EMA，四组变体。
- 超参数实验：考察合成节点比例对性能的影响。
- 可视化记忆图结构对比原图。
- 不同GNN骨干（GCN、GraphSAGE、GAT、GIN）的实验。
实验数量较丰富，涵盖多种漂移类型和模型变体，对比基线全面，评估维度包括适应能力和遗忘，较为充分和公平。

### 6. 论文的主要结论与发现
- GCAL在所有数据集上均显著优于现有方法，AP更高且AF为正（即甚至对旧域有知识增强），有效缓解了灾难性遗忘。
- 仅靠单步适应的方法（如EERM、Tent）在持续漂移下迅速崩溃；即使最接近的持续方法CoTTA也有遗忘现象。
- 生成的记忆图大幅压缩了图规模，但仍然保持信息性结构。
- 各组件（正则项、生成损失、EMA）均对性能有贡献，表明记忆生成和重放机制的重要性。

### 7. 优点
- 首次在无监督设定下解决图持续域适应问题，提出“适应-生成记忆”双层框架。
- 从信息瓶颈理论导出下界，为记忆图生成提供理论支撑。
- 设计了轻量级的变分记忆图生成器，能够生成远小于原图的代表性图。
- 多样实验证明了方法的有效性和鲁棒性。

### 8. 不足与局限
- 论文指出方法未改进图模型架构本身，当基模型能力不足时可能限制性能。
- 实验仅针对图分类/节点分类任务，未涉及链接预测等其他图任务。
- 未提供计算开销分析，不清楚记忆生成和重放带来的额外时间、内存代价。
- 域序列与类别的平衡性未深入探讨（如Elliptic数据早期类不平衡被刻意避开）。
- 数据集规模相对较小，未在更大规模动态图上验证。
（完）
