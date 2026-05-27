---
title: Gated Integration of Low-Rank Adaptation for Continual Learning of Language Models
title_zh: 用于语言模型持续学习的低秩适配门控集成方法
authors: "Yan-Shuo Liang, Wu-Jun Li"
date: 2025-01-22
pdf: "https://openreview.net/pdf?id=vmfRdANa6a"
tags: ["query:continual"]
score: 9.0
evidence: 通过门控低秩适配融合防止语言模型持续学习中的遗忘
tldr: 现有基于LoRA的持续学习方法为每个新任务扩展分支，但对旧任务强制新旧分支等权重贡献，导致遗忘。本文提出GainLoRA，在扩展新LoRA分支的同时引入门控模块自适应整合。该方法使模型在顺序学习语言任务时能有效保留先前知识，实验表明在多个基准上优于现有方法，显著缓解了语言模型持续学习中的灾难性遗忘。
source: ICML-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 856, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 850, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1656, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 777, \"height\": 433, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 778, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1748, \"height\": 459, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vmfrdana6a/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 882, \"height\": 502, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1505, \"height\": 616, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1444, \"height\": 314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1496, \"height\": 357, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1483, \"height\": 548, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1451, \"height\": 886, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1241, \"height\": 885, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1689, \"height\": 559, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1340, \"height\": 581, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1585, \"height\": 416, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1543, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1589, \"height\": 309, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1507, \"height\": 511, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1241, \"height\": 345, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1230, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1315, \"height\": 886, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vmfrdana6a/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1294, \"height\": 296, \"label\": \"Table\"}]"
motivation: 现有基于LoRA的持续学习方法在处理旧任务时固定新旧分支贡献，导致遗忘。
method: 提出GainLoRA，为每个新任务扩展LoRA分支并通过门控模块自适应集成。
result: 实验表明在多个语言模型持续学习基准上性能优于已有方法。
conclusion: GainLoRA通过门控机制有效缓解了语言模型持续学习中的遗忘问题。
---

## Abstract
Continual learning, which requires the model to learn multiple tasks sequentially, is crucial for language models (LMs). Recently, low-rank adaptation (LoRA), one of the most representative parameter-efficient fine-tuning (PEFT) methods, has gained increasing attention in continual learning of LMs. However, most existing continual learning methods based on LoRA typically expand a new LoRA branch to learn each new task and force the new and old LoRA branches to contribute equally to old tasks, potentially leading to forgetting. In this work, we propose a new method, called gated integration of low-rank adaptation (GainLoRA), for continual learning of LMs. GainLoRA expands a new LoRA branch for each new task and introduces gating modules to integrate the new and old LoRA branches. Furthermore, GainLoRA leverages the new gating module to minimize the contribution from the new LoRA branch to old tasks, effectively mitigating forgetting and improving the model's overall performance. Experimental results on continual learning benchmarks demonstrate that GainLoRA outperforms existing state-of-the-art methods.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义
- **研究背景**：语言模型在顺序学习多个任务时会出现“灾难性遗忘”，即学习新任务后，旧任务性能显著下降。持续学习旨在解决这一问题。
- **现存问题**：目前主流的基于低秩适配（LoRA）的持续学习方法通常为每个新任务扩展一个新的LoRA分支，并冻结旧分支以防止参数被覆盖。然而，这些方法在整合新旧分支时大多采用简单相加，强制新旧分支对旧任务的贡献权重相等。这种无差别的整合方式会使新分支对旧任务输出产生较大干扰，从而加剧遗忘，限制了模型整体性能。
- **本文动机**：提出一种名为“门控低秩适配集成”（GainLoRA）的新方法，通过引入可学习的门控模块，自适应地调节每个LoRA分支对不同样本的贡献，从而有效降低新任务分支对旧任务的负面影响，缓解灾难性遗忘。

## 2. 方法论
### 核心思想
- GainLoRA 为每一个任务 $T_i$ 维护一个独立的 LoRA 分支 $(A_i, B_i)$ 和一个独立的门控模块 $g_i(\cdot)$。
- 对于输入样本 $x$，门控模块 $g_i(x)$ 输出一个介于$[0,1]$ 之间的标量系数 $a_i$，用于控制第 $i$ 个 LoRA 分支在当前样本上的贡献。
- 前向传播时，各分支的加权和 $\sum_i a_i A_i B_i$ 叠加到原始预训练权重上，实现动态整合。

### 关键技术细节与约束
1. **门控模块结构**：
   - 输入为样本经 Tokenizer 和平均池化后的向量 $p_0$。
   - 经过多层非线性变换（SiLU 激活）得到 $p_L$，最后一层映射为标量 $b$。
   - 最终输出 $a_i = f(b)$，文中选择 $f(b)=|2\cdot\text{sigmoid}(b)-1|$，保证 $f(0)=0$ 且输出范围 $[0,1]$。

2. **遗忘抑制策略——逼近零贡献**：
   - 目标：对于旧任务样本，新门控模块 $g_t(x)$ 的输出应尽可能为 $0$，使得新 LoRA 分支对旧任务无干扰。
   - 由于旧任务样本不可访问，GainLoRA 通过对 $g_t(\cdot)$ 施加约束来实现。

3. **初始化约束**：
   - 将新门控模块最后一层权重 $W_{t,L+1}$ 初始化为与旧任务输入子空间 $M_{t,L+1}$ 正交的方向，结合 $f(0)=0$，使得旧任务样本经过门控输出严格为 $0$。
   - 前 $L$ 层权重继承自上一任务的门控模块 $g_{t-1}$，以便利用梯度投影记忆（GPM）维护旧任务子空间的正交基。

4. **更新约束**：
   - 在学习新任务时，要求门控模块每层的更新量 $\Delta W_{t,l}$ 与旧任务在该层的输入子空间 $M_{t,l}$ 正交。
   - 该约束确保旧任务样本的门控输出在学习新任务过程中保持不变，始终为 $0$。
   - 实际实现中，借助 GPM 预计算的正交基矩阵 $M_{t,l}$，将梯度投影到正交方向（$\Delta W_{t,l} \leftarrow \Delta W_{t,l} - M_{t,l}M_{t,l}^T\Delta W_{t,l}$）。

5. **整体流程**（对应算法1）：
   - 对每个新任务 $t$：扩展 $A_t, B_t$ 和门控模块 $g_t$；施加初始化约束；在训练集上优化任务损失，同时用正交投影保证更新约束。旧分支和旧门控模块完全冻结。

## 3. 实验设计
### 数据集与场景
- **SuperNI 基准**：包含对话生成、信息抽取、问答、摘要、情感分析等 15 个自然语言处理任务，按两种不同顺序（Order 1、Order 2）组织。
- **Long Sequence 基准**：包含 15 个不同的文本分类任务，按两种顺序（Order 3、Order 4）组织。
- **评估设定**：任务身份未知（无任务ID）、无旧任务真实或合成样本回放。

### 评估指标
- **平均性能（AP）**：学习完所有任务后，模型在每个任务上的最终性能平均值。
- **遗忘率（FT）**：学习新任务后，旧任务最大性能与最终性能之差在所有旧任务上的平均。

### 对比方法
- 基于提示的方法：L2P、LFPT5、EPI。
- 基于 LoRA 的方法：SeqLoRA（连续微调）、IncLoRA、C-LoRA、O-LoRA、InfLoRA。
- 其他：MIGU+FT。
- GainLoRA 分别与 O-LoRA 和 InfLoRA 结合，记为 GainLoRA (O-LoRA) 和 GainLoRA (InfLoRA)。

### 基础模型
- T5-Large、T5-XL、Llama-2-7B、Llama-2-13B。
- 统一使用指令微调，AdamW 优化器，LoRA 添加于 query 和 value 注意力矩阵。每个实验随机重复 3 次。

## 4. 资源与算力
- 训练使用 **NVIDIA RTX A6000 GPU**。
- 对于 T5-Large/XL，可在单张 A6000 上配合梯度累积完成。
- 对于 Llama-2-7B/13B，采用多张 A6000 进行数据并行，配合 **DeepSpeed ZeRO-2**，必要时使用 ZeRO-3。
- 采用了 **FlashAttention-2** 降低显存占用。
- **未提供**具体 GPU 数量、每任务训练时间或总训练时长。

## 5. 实验数量与充分性
### 实验分组
1. **主实验**：在 4 种任务序列（Order 1-4）上对比多种基线，提供标准差。
2. **模型缩放实验**：在 T5-XL、Llama-2-7B、Llama-2-13B 上重复验证。
3. **消融实验**：
   - 移除初始化约束、移除更新约束、同时移除两种约束（共 3 种变体），分别在 T5-Large 和 Llama-2-7B 上测试。
4. **门控模块结构分析**：
   - 改变输出映射函数 $f(\cdot)$ 的三种形式。
   - 改变隐藏层维度（50/100/200）和网络层数（1/3/5 层）。
5. **LoRA 秩的影响**：测试秩为 2、4、8。
6. **与其他 LoRA 方法结合**：将 GainLoRA 与 IncLoRA、C-LoRA 结合。
7. **重演设定扩展**：与 SAPT-LoRA 在可访问旧任务样本的场景下对比。
8. **未见过任务泛化**：在 SuperNI 的剩余未训练任务上测试跨任务迁移能力。
9. **计算开销分析**：对比不同模型引入 GainLoRA 后的 FLOPs 和 MACs。
10. **输出分布可视化**：展示新门控模块对旧/新任务样本的输出分布。

### 充分性与公平性
- 实验覆盖全面，包含多个基准、多种模型规模、丰富的消融和扩展研究，且报告了标准差，可靠性较高。
- 与基线方法的对比均遵循统一框架（相同LoRA结构、相同训练策略），并说明了超参数搜索过程，保证了公平性。
- 额外分析了参数量和计算开销，证明增益模块引入的额外开销极小。

## 6. 主要结论与发现
- GainLoRA 在所有任务序列上均优于 O-LoRA 和 InfLoRA，平均性能显著提升，遗忘率大幅降低。
- 在 T5-XL、Llama-2-7B/13B 等更大模型上优势依然保持，方法具有良好的可扩展性。
- 消融实验证明，初始化约束和更新约束缺一不可，两者协同才能实现最佳遗忘抑制。
- 门控输出分布显示，旧任务样本的系数集中在 0 附近，新任务样本集中在 1 附近，验证了方法的设计目标。
- GainLoRA 额外增加的可训练参数和计算量（FLOPs）相对基模型极小，性价比高。

## 7. 优点
- **创新性强**：首次将门控机制引入 LoRA 分支集成，用动态权重替代固定相加，巧妙地解决了新分支对旧任务的干扰。
- **理论约束清晰**：通过子空间正交约束保证旧任务上系数恒为零，遗忘抑制机制严谨且可证明。
- **即插即用**：不限定新 LoRA 分支的更新方式，可直接与 O-LoRA、InfLoRA、IncLoRA 等现有方法结合，通用性好。
- **实验充分**：多基准、多模型、多视角消融，分析细致，结论可信度高。
- **资源友好**：额外参数量很少，计算开销低，适合实际部署。

## 8. 不足与局限
- **推理时无法合并**：由于引入输入依赖的门控系数，LoRA 分支无法像固定相加方法那样在推理前合并到原有权重中，从而增加了少量推理延迟（文中给出了 FLOPs 对比，增幅很小）。
- **依赖子空间维护**：需要 GPM 来近似旧任务输入子空间，其准确性依赖于先前任务输入的充分覆盖，如果任务差异极大，子空间估计可能不准。
- **重演设定下并非最优**：在允许重放旧样本的设定中，GainLoRA 仅达到与专门设计方法（SAPT-LoRA）相当的性能，并未展现出显著优势。
- **仅测试 NLP 任务**：实验限于文本分类和生成，未涉及其他模态（如视觉）的持续学习。
- **门控模块设计较基础**：门控网络为简单全连接结构，且映射函数 $f$ 的选择可能影响性能（文中有部分对比但未深入优化）。
- **资源细节不详**：未提供具体的训练时间或 GPU 总使用量，对复现成本估计不利。

（完）
