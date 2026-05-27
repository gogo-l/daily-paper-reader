---
title: Gated Integration of Low-Rank Adaptation for Continual Learning of Language Models
title_zh: 门控集成低秩适配用于语言模型持续学习
authors: "Yan-Shuo Liang, Wu-Jun Li"
date: 2025-01-22
pdf: "https://openreview.net/pdf?id=vmfRdANa6a"
tags: ["query:continual"]
score: 10.0
evidence: 门控集成低秩适配以缓解语言模型持续学习中的遗忘
tldr: 现有基于LoRA的持续学习方法在扩展新分支时强制新旧分支等贡献，可能导致遗忘。本文提出GainLoRA，为每个新任务扩展LoRA分支并引入门控模块，自适应整合新旧分支的贡献。实验表明该方法在语言模型持续学习任务中有效减少遗忘，优于先前方法。GainLoRA为参数高效持续学习提供了更平衡的知识整合方案。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1656, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 777, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 778, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1748, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 882, \"height\": 502, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1505, \"height\": 616, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1496, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1483, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 886, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1241, \"height\": 885, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1689, \"height\": 559, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1340, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1585, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1543, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1589, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1507, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1241, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1230, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1315, \"height\": 886, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1294, \"height\": 296, \"label\": \"Table\"}]"
motivation: LoRA扩展方法在持续学习中新旧分支贡献不等可能加剧遗忘。
method: 提出GainLoRA，通过门控模块自适应融合新老LoRA分支，平衡任务知识。
result: 在语言模型持续学习基准上，GainLoRA显著降低遗忘，性能优于现有方法。
conclusion: 门控集成机制有效协调新旧知识，为低秩适配下的持续学习提供新途径。
---

## Abstract
Continual learning, which requires the model to learn multiple tasks sequentially, is crucial for language models (LMs). Recently, low-rank adaptation (LoRA), one of the most representative parameter-efficient fine-tuning (PEFT) methods, has gained increasing attention in continual learning of LMs. However, most existing continual learning methods based on LoRA typically expand a new LoRA branch to learn each new task and force the new and old LoRA branches to contribute equally to old tasks, potentially leading to forgetting. In this work, we propose a new method, called gated integration of low-rank adaptation (GainLoRA), for continual learning of LMs. GainLoRA expands a new LoRA branch for each new task and introduces gating modules to integrate the new and old LoRA branches. Furthermore, GainLoRA leverages the new gating module to minimize the contribution from the new LoRA branch to old tasks, effectively mitigating forgetting and improving the model's overall performance. Experimental results on continual learning benchmarks demonstrate that GainLoRA outperforms existing state-of-the-art methods.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
*   **研究背景**：语言模型（LM）在顺序学习多个任务时会出现灾难性遗忘，即在学习新任务时严重丧失对旧任务的知识。
*   **现有方法局限**：目前主流的基于 LoRA 的持续学习方法会为每个新任务扩展一个新的 LoRA 分支，但在推理时，新旧 LoRA 分支的输出通过简单相加进行整合，这强制新旧分支对旧任务做出相等贡献。新分支的输出会给旧任务带来较大偏差，导致遗忘。
*   **论文核心**：提出 **GainLoRA (Gated Integration of Low-Rank Adaptation)**，通过引入可学习的门控模块，动态调节新旧 LoRA 分支对输入的贡献，从而最小化新分支对旧任务的干扰，更有效地缓解遗忘并提升整体性能。

## 2. 方法论
*   **可扩展架构**：为每个新任务 $t$ 添加新的 LoRA 分支 $A_t, B_t$，同时为每个任务 $i$ 维护一个独立的门控模块 $g_i(\cdot)$。各分支的加权和通过 $e = (W + \sum_{i} a_i A_i B_i)h$ 实现，其中 $a_i = g_i(x)$ 为整合系数，$x$ 为原始输入。
*   **门控模块设计**：门控模块 $g_i(x) = f(W_{i,L+1} p_L)$，中间层 $p_l = \sigma(W_{i,l} p_{l-1})$，输入 $p_0$ 是对输入句子 token 嵌入的平均池化。$f(\cdot)$ 将输出映射到 $[0,1]$，文中选用 $f(b)=|2\cdot\text{sigmoid}(b)-1|$ 以保证 $f(0)=0$。
*   **约束机制（核心）**：在无法访问旧任务样本的场景下，通过正交约束使新门控模块对旧任务输入输出 $0$，从而完全屏蔽新 LoRA 分支的影响。
    *   **初始化约束**：将新门控模块最后一层权重初始化为与旧任务输入子空间正交（$W_{t,L+1} \perp \mathcal{M}_{t,L+1}$），结合 $f(0)=0$，使得初始时对旧任务 $a_t=0$。
    *   **更新约束**：在训练第 $t$ 个任务时，强制门控模块的梯度更新与旧任务输入子空间正交（$\Delta W_{t,l} \perp \mathcal{M}_{t,l}$），从而保证 $g_t(x)$ 在旧任务上始终为 $0$。
*   **约束实现**：利用梯度投影记忆（GPM）技术，通过 SVD 迭代构建并维护各层输入子空间的正交基 $\mathbf{M}_{t,l}$。权重初始化和梯度更新时，将权重或梯度投影到正交补空间上。
*   **兼容性**：GainLoRA 不规定新 LoRA 分支的具体更新策略，可直接与 O-LoRA、InfLoRA 等方法结合。

## 3. 实验设计
*   **数据集与场景**：
    *   **SuperNI 基准**：包含对话、信息抽取、问答、摘要、情感分析等 5 类 15 个任务，组成两种任务序列（Order 1, Order 2）。
    *   **Long Sequence 基准**：包含 15 个分类任务，组成两种序列（Order 3, Order 4）。
    *   设置挑战：无任务标识、无旧任务真实或合成样本回放。
*   **评估指标**：平均性能 (AP) 与遗忘量 (FT)。
*   **基线方法**：包括 L2P、LFPT5、EPI、MIGU+FT、IncLoRA、C-LoRA、O-LoRA、InfLoRA 及基础的 SeqLoRA。
*   **模型主链**：T5-Large、T5-XL、Llama-2-7B、Llama-2-13B。

## 4. 资源与算力
*   **硬件与框架**：使用 NVIDIA RTX A6000 GPU。对于 T5 模型用单卡 + 梯度累积；对于 Llama 模型采用多卡数据并行（DeepSpeed ZeRO-2，长序列时用 ZeRO-3），配合 FlashAttention-2 降低显存占用。
*   **训练细节**：T5 模型训练 100 epochs，Llama 模型训练 50 epochs。全局批大小为 32。

## 5. 实验数量与充分性
论文进行了较为充分的对比和消融实验，覆盖多维度：
*   **主体实验**：在 4 个序列 × 4 种模型主链（T5-L/T5-XL/Llama-2-7B/13B）上对比 10 余种基线方法，并在表中给出标准差。
*   **消融实验**：验证初始化约束、更新约束各自的重要性（移除单一约束及全部移除），分析新门控模块的输出分布以验证其屏蔽效果。
*   **架构敏感性**：测试门控模块中映射函数 $f$、隐藏层维度、层数、LoRA 秩等超参数变化的影响。
*   **扩展性验证**：将 GainLoRA 与 IncLoRA、C-LoRA 结合，证明其通用性；亦扩展至有回放样本的设置，与 SAPT-LoRA 比较。
实验设计客观公平，对比全面，结果具有说服力。

## 6. 主要结论与发现
*   GainLoRA 在各种模型规模和任务序列上，AP 和 FT 均显著优于 O-LoRA、InfLoRA 等基于固定系数的 LoRA 方法，尤其在遗忘指标上大幅降低。
*   门控模块能够有效学习到对新旧任务的分化响应：对旧任务输出接近 0，对新任务输出接近 1，从而精准调控各分支贡献。
*   方法具有良好的即插即用性，可与多种 LoRA 分支更新策略结合并带来稳定提升。
*   引入的额外参数和计算量相对模型整体而言较小，保持了参数效率。

## 7. 优点
*   **创新性强**：首次将门控机制引入可扩展 LoRA 的集成过程，从“强制等贡献”转向“自适应调节”。
*   **理论基础扎实**：通过子空间正交约束严格保证新分支对旧任务无干扰，而非仅依赖正则化。
*   **兼容与灵活性**：能够无缝衔接多种现有 LoRA 持续学习算法，可视为一种通用的遗忘缓解策略。
*   **实验扎实**：在多个主流基准、多种模型规模上进行了系统评估，包含丰富的消融和超参数分析，对方法的内在机理做了可视化验证。

## 8. 不足与局限
*   **额外模块开销**：虽然相对较小，但每个任务引入的门控模块仍增加了参数量和无法与预训练权重合并的推理计算。
*   **依赖 GPM 近似**：子空间基矩阵通过 GPM 近似构建，超参数（如阈值 $\epsilon_{th}$）需根据任务设定，可能影响正交约束的精确性。
*   **实验泛化性**：未在更大规模模型（如 70B）或更多样化的任务序列上进行测试；基准任务数量为 15 个，更长的任务流场景有待验证。
*   **训练效率**：训练过程中需要对门控模块进行额外的正交投影操作，带来一定的计算开销，文中未详细对比训练速度。
（完）
