---
title: An Effective Dynamic Gradient Calibration Method for Continual Learning
title_zh: 面向持续学习的有效动态梯度校准方法
authors: "Weichen Lin, Jiaxiang Chen, Ruomin Huang, Hu Ding"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=q14AbM4kdv"
tags: ["query:continual"]
score: 9.0
evidence: 提出梯度校准方法防止持续学习中的灾难性遗忘
tldr: 持续学习面临灾难性遗忘挑战，本文从梯度角度出发，提出一种动态梯度校准算法。在每个模型更新步骤中，该方法校准梯度方向以引导模型在吸收新知识的同时保留旧任务信息。实验表明，该算法能有效降低遗忘程度，在多个标准数据集上取得先进的性能，为持续学习提供了一种简单高效的优化视角。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-q14abm4kdv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 605, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-q14abm4kdv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1679, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-q14abm4kdv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 682, \"height\": 531, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1654, \"height\": 833, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 711, \"height\": 745, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 997, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1219, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1549, \"height\": 740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1560, \"height\": 740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1046, \"height\": 567, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1608, \"height\": 217, \"label\": \"Table\"}]"
motivation: 持续学习中存储受限导致灾难性遗忘，现有方法仍未完全避免。
method: 提出动态梯度校准方法，在模型更新时校准梯度以保留旧知识。
result: 实验表明该方法显著降低遗忘率，在基准测试中取得有竞争力的表现。
conclusion: 梯度校准是抑制灾难性遗忘的有效途径，为持续学习提供新视角。
---

## Abstract
Continual learning (CL) is a fundamental topic in machine learning, where the goal is to train a model with continuously incoming data and tasks. Due to the memory limit, we cannot store all the historical data, and therefore confront the ``catastrophic forgetting'' problem, i.e., the performance on the previous tasks can substantially decrease because of the missing information in the latter period. Though a number of elegant methods have been proposed, the catastrophic forgetting phenomenon still cannot be well avoided in practice. In this paper, we study the problem from the gradient perspective, where our aim is to develop an effective algorithm to calibrate the gradient in each updating step of the model; namely, our goal is to guide the model to be updated in the right direction under the situation that a large amount of historical data are unavailable. Our idea is partly inspired by the seminal stochastic variance reduction methods (e.g., SVRG and SAGA) for reducing the variance of gradient estimation in stochastic gradient descent algorithms. Another benefit is that our approach can be used as a general tool, which is able to be incorporated with several existing popular CL methods to achieve better performance. We also conduct a set of experiments on several benchmark datasets to evaluate the performance in practice.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究背景**：持续学习（Continual Learning, CL）要求模型在新任务或新数据流不断到达时顺序学习，但由于存储限制无法保存所有历史数据，导致模型在旧任务上的性能大幅下降，即**灾难性遗忘**（catastrophic forgetting）。
- **现有问题**：已有的许多方法（如经验回放、知识蒸馏、参数正则化等）虽能缓解遗忘，但在实际场景中仍未完全解决该问题，尤其是当缓冲区容量有限时，历史梯度估计不准确。
- **本文动机**：作者从**梯度视角**重新审视持续学习，指出所有缓解遗忘的方法最终都体现为对模型更新梯度的修正。若历史数据完整，随机梯度下降（SGD）不存在遗忘问题；而遗忘的本质在于缓冲区限制导致的梯度估计偏差。因此，本文旨在设计一种**动态梯度校准算法**，在每个更新步骤中更精确地估计历史梯度，从而引导模型向正确方向更新，减轻遗忘。

## 2. 论文提出的方法论

### 2.1 核心思想

- 借鉴随机方差缩减方法（SVRG、SAGA）的思路：利用额外存储的全梯度信息来校正当前步的梯度，以降低梯度估计方差。
- 类比关系：SGD 的“批量大小限制” → 方差大 → SVRG 通过校准项降方差；CL 的“缓冲区大小限制” → 历史梯度估计不准 → 提出类似的**动态梯度校准**机制。
- **动态梯度校准（DGC）** 的目标：在无法访问全部历史数据的情况下，逐步维护一个对历史全梯度的无偏估计，并用其修正当前梯度。

### 2.2 关键技术细节与算法流程

#### 2.2.1 经验回放（ER）与直接 SVRG 结合的局限性

- ER 通过蓄水池采样维护缓冲区 `M_t`，更新时混合当前任务梯度与缓冲区梯度（公式 7）。
- 若直接将 SVRG 应用于 ER（公式 9），只能利用缓冲区内的数据计算校准项 `μ̃` 和 `ṽ`，依然丢失了大量历史数据信息，效果不佳。

#### 2.2.2 两阶段动态梯度校准（DGC）

算法分为**训练阶段内**和**任务切换时**两级更新：

1. **训练阶段内（每个任务 `t` 内）**
   - 将当前任务训练过程分为多个阶段（stage），每个阶段开始时记录参数 `θ̃_t`。
   - 理想校准梯度（公式 10）需使用全部历史数据 `T_{[1:t)}` 的全梯度 `G(T_{[1:t)}, θ̃_t)`，但实际不可得。
   - **近似策略**：用递归函数 `Γ'_DGC(t)` 替代 `G(T_{[1:t)}, θ̃_t)`。
   - 定义 `Γ_DGC(t, k)`（公式 11）：用当前缓冲区样本 `(x̄_t, ȳ_t)` 和辅助项 `Γ'_DGC(t)` 构造校准项。
   - 阶段结束时更新 `Γ'_DGC(t)`（公式 12）使其等于该阶段最后一步的 `Γ_DGC(t, m+1)`。
   - 引理 3.2 证明：`Γ'_DGC(t)` 是历史全梯度 `G(T_{[1:t)}, θ̃_t)` 的无偏估计。

2. **任务切换时（从 t 到 t+1）**
   - 一个任务训练完成后，将新任务数据整合进历史：
     - `Γ'_DGC(t+1) = (1/t) * ((t-1) * Γ'_DGC(t) + G(T_t, θ̃_t))`（公式 14）。
   - 这将第 t 个任务的全梯度信息以无偏方式融合进校准项。

#### 2.2.3 理论保证

- 在损失函数 `L`–光滑且 `γ`–强凸等假设下，**定理 3.3** 证明 DGC 在每个任务时间点 `t` 上具有**线性收敛速率**，期望误差以 `(1/2)^{s}` 倍数衰减，其中 `s` 为当前阶段数。这表明 DGC 与 SVRG 类似，可加快优化且使损失下降更平滑。

#### 2.2.4 与其他 CL 方法的结合

- DGC 可方便地与任何基于蓄水池采样的 CL 方法（如 DER++、XDER）结合：在原有梯度基础上加入 DGC 校准项 `Γ_DGC(t, k)`，并通过参数 `α` 控制二者的混合比例（公式 15）。
- 作者建议 `α ≈ 1/L`（`L` 为光滑系数）。

### 2.3 算法伪代码（Algorithm 1 要点）

- 输入：任务流 `{T_1, ..., T_T}`，每阶段步数 `m`，阶段数 `S`，批大小 `b`，学习率 `η`。
- 初始化模型参数 `θ̃_0`，`Γ'_DGC(1) = 0`，空缓冲区 `M_1`。
- 对每个任务 `t`：
  - 执行 `S` 个阶段，每阶段 `m` 步，利用 `Γ'_DGC(t)` 计算校准梯度并更新参数；
  - 阶段结束时更新 `Γ'_DGC(t)`；
  - 任务结束时通过蓄水池更新缓冲区 `M_{t+1}`，并按公式 14 计算 `Γ'_DGC(t+1)`。

## 3. 实验设计

### 3.1 数据集与场景

- **数据集**：S-CIFAR10（10 类分 5 任务）、S-CIFAR100（100 类分 10 任务）、S-TinyImageNet（200 类分 10 任务）。
- **持续学习场景**：
  - **类增量学习（CIL）**：任务序列标签空间不重叠，训练和测试时已知任务边界。
  - **无任务边界持续学习（TFCL）**：任务边界未知，算法无法依赖任务 ID。

### 3.2 基准方法（Baselines）

- **重放类**：ER、DER++、XDER、MOCA、GSS、GCR、HAL、ICARL。
- **优化类**：AGEM、AOP、SSVRG（流式 SVRG）。
- **动态架构类**：Dynamic ER。
- 将 DGC 与 ER、DER++、XDER、Dynamic ER 结合（标记为 DGC-Y），评估提升效果。

### 3.3 评估指标

- **最终平均增量准确率（FAIA）**：`FAIA = (1/T) Σ_{i=1}^T AA_i`，其中 `AA_i` 为前 i 个任务测试精度的平均。
- **最终平均准确率（FAA）** 和 **最终遗忘率（FF）**（见附录）。
- 所有实验重复 10 次，报告平均值和标准差。

### 3.4 参数设置

- 网络：ResNet-18，从头训练。
- 优化器：普通 SGD（无 DGC 方法），DGC 方法按阶段更新。
- 固定训练总步数（epochs 和 batch size 固定），`m` 设为 200（即每阶段 200 步）。
- 缓冲区大小：S-CIFAR10 用 500/2000；S-CIFAR100 用 500/2000；S-TinyImageNet 用 2000/5000。
- `α` 固定为 `1e-3`。

## 4. 资源与算力

- 论文正文及附录**未明确提及**使用的 GPU 型号、数量、具体训练耗时（仅表 8 在附录中给出部分 CL 方法在 S-CIFAR100 上前三个任务的训练时间，用于相对比较）。因此，算力信息不足，无法评估资源开销绝对值。

## 5. 实验数量与充分性

- **实验量**：
  - 3 个数据集 × 2 种缓冲大小 × 十余种基线方法，CIL 下组合比较。
  - 额外实验：不同任务数量（5 任务 vs 20 任务）、TFCL 场景、消融对 `α` 和 `m` 的选择。
  - 附录包含 FAA、FF、TFCL 详细数据及训练时间对比。
- **客观性与公平性**：
  - 统一使用开源框架（Mammoth、PyCIL），沿用原超参数。
  - 所有方法基于相同网络架构、数据增强及训练 epoch 数，公平参照。
  - 对比了有/无 DGC 的同一基线，控制变量。
- **充分性评价**：实验覆盖多种数据集、缓冲容量、任务数量、CL 场景，以及超参数敏感性，**整体较为充分**。但训练时间对比仅限 3 个任务，缺乏完整端到端时间开销分析。

## 6. 论文的主要结论与发现

- DGC 可有效提升多种 CL 方法（ER、DER++、XDER、Dynamic ER）的最终准确率，**最高提升超过 6%**。
- 在任务数量更多的情况下（如 20 任务），DGC 带来的改善更显著，表明其能更好地利用历史信息缓解遗忘。
- DGC 基于方差缩减思想，使**训练损失下降更平滑、波动更小**（图 3）。
- TFCL 场景下 DGC 同样有效，且优于 SSVRG、GCR 等依赖缓冲区估计全梯度的方法。
- 相比单纯增大缓冲区存储更多样本，DGC 所消耗的额外存储用于维护梯度校准器能带来**更大的边际收益**（图 1）。

## 7. 优点

- **新颖的梯度视角**：将 CL 问题类比 SGD 的方差问题，引入 SVRG 思想，逻辑清晰。
- **方法通用性强**：可插拔式结合现有大多数基于蓄水池的 CL 方法，不会改变原有算法流程。
- **理论支持**：在强凸假设下提供线性收敛证明，增加方法可信度。
- **有效且稳定**：实验显示准确率和遗忘率双改善，训练损失更平滑，利于实际调优。
- **对任务数增加更鲁棒**：任务越多，遗忘越严重，DGC 的优势越突出。

## 8. 不足与局限

- **理论假设较强**：要求损失函数 L–光滑且 γ–强凸，而深度网络通常非凸，理论拓展受限。
- **额外存储开销**：需存储 `Γ'_DGC(t)`（大小等同于模型参数量），对极大规模模型可能代价较高，但实验表明该存储的边际收益优于直接存更多样本。
- **训练时间未充分量化**：仅给出前三任务部分时间，缺少整体端到端时间比较。
- **缓冲区选择机制单一**：蓄水池采样为被动保留策略，未与主动样本选择方法深度结合，可能在存储效率上仍有改善空间。
- **未知任务边界依赖**：CIL 模式下任务边界已知，TFCL 虽可处理但算法需将每批数据视为“微任务”，增加了计算频次，对长序列的实际开销有待检验。

（完）
