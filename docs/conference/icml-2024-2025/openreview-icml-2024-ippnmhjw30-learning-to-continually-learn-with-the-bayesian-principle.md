---
title: Learning to Continually Learn with the Bayesian Principle
title_zh: 学习持续学习：贝叶斯原理的方法
authors: "Soochan Lee, Hyeonseong Jeon, Jaehyeon Son, Gunhee Kim"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=IpPnmhjw30"
tags: ["query:continual"]
score: 9.0
evidence: 元持续学习框架以防止灾难性遗忘
tldr: 针对深度学习中持续学习的灾难性遗忘问题，提出一种元持续学习框架，通过元学习将神经网络与贝叶斯更新规则结合，使模型能够学习如何持续学习并完全免受遗忘影响。该方法在非平稳数据流上训练时，能有效缓解遗忘，且保持了神经网络的强表征能力。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 854, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 861, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 1392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1141, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1787, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1781, \"height\": 491, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1771, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1359, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1425, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1349, \"height\": 136, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1350, \"height\": 137, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 822, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 681, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 681, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ippnmhjw30/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 676, \"height\": 715, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1575, \"height\": 263, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 746, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 860, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 808, \"height\": 346, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 868, \"height\": 292, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 664, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1328, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1152, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1239, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1068, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1322, \"height\": 459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1150, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1341, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1169, \"height\": 460, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1322, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1151, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1503, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ippnmhjw30/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1302, \"height\": 384, \"label\": \"Table\"}]"
motivation: 深度学习模型在连续任务流上训练时容易发生灾难性遗忘，经典贝叶斯方法虽能避免遗忘但表达力不足，需融合二者优势。
method: 采用元学习范式，构建元持续学习框架，结合神经网络的强大表征能力和贝叶斯模型对遗忘的鲁棒性，让模型学习如何持续学习。
result: 在持续学习基准上，该方法有效缓解了遗忘，并保持对复杂数据的建模能力，优于传统方法。
conclusion: 元持续学习框架证明了结合贝叶斯原则与神经网络可以消除灾难性遗忘，为持续学习提供了新方向。
---

## Abstract
In the present era of deep learning, continual learning research is mainly focused on mitigating forgetting when training a neural network with stochastic gradient descent on a non-stationary stream of data. On the other hand, in the more classical literature of statistical machine learning, many models have sequential Bayesian update rules that yield the same learning outcome as the batch training, i.e., they are completely immune to catastrophic forgetting. However, they are often overly simple to model complex real-world data. In this work, we adopt the meta-learning paradigm to combine the strong representational power of neural networks and simple statistical models' robustness to forgetting. In our novel meta-continual learning framework, continual learning takes place only in statistical models via ideal sequential Bayesian update rules, while neural networks are meta-learned to bridge the raw data and the statistical models. Since the neural networks remain fixed during continual learning, they are protected from catastrophic forgetting. This approach not only achieves significantly improved performance but also exhibits excellent scalability. Since our approach is domain-agnostic and model-agnostic, it can be applied to a wide range of problems and easily integrated with existing model architectures.

---

## 论文详细总结（自动生成）

### 1. 核心问题与研究动机
- **背景与挑战**：在深度学习时代，持续学习（Continual Learning, CL）的核心挑战是灾难性遗忘——模型在非平稳数据流上训练时会覆盖旧知识。
- **传统方法的局限**：经典统计机器学习中的序列贝叶斯更新规则可实现理想的持续学习，完全避免遗忘，但其模型过于简单，无法建模复杂现实数据。
- **核心思想**：本文提出结合**神经网络强大的表征能力**与**指数族分布贝叶斯更新的抗遗忘特性**，通过元学习范式（meta-continual learning, MCL）赋予模型“学会如何持续学习”的能力。

### 2. 方法论：顺序贝叶斯元持续学习（SB-MCL）
- **整体框架**：将持续学习过程完全抽象为在简单统计模型上的**理想序列贝叶斯更新**，而神经网络则作为连接原始数据与统计模型的“桥梁”。
- **关键机制**：
  - 假设每个持续学习片段存在一个隐变量 `z`，持续学习被形式化为对 `q(z|数据流)` 的顺序贝叶斯更新。
  - 根据 Fisher-Darmois-Koopman-Pitman 定理，**指数族分布**是唯一能保持固定维度充分统计量的分布族，可实现无信息损失的顺序更新。框架采用如**因子化高斯分布**作为变分后验。
  - 更新规则：以高斯后验为例，学习器对每个新样本输出一个含噪声观测 `ẑ_t` 及其精度 `P_t`，后验的参数按以下规则更新（公式5）：
    ```
    Λ_t = Λ_{t-1} + P_t
    μ_t = Λ_t^{-1} (Λ_{t-1} μ_{t-1} + P_t ẑ_t)
    ```
  - **神经网络的作用**：在元训练阶段，通过 SGD 优化一个“学习器”网络（产生变分似然）和一个“模型”网络（在给定 z 后输出最终预测）。在持续学习内环中，**所有神经网络参数保持固定**，因此完全不受遗忘影响。
- **元训练目标**：最大化变分下界（ELBO），鼓励模型与学习器协作提升数据似然，同时通过 KL 散度正则化后验。因后验与先验均为指数族，KL 项可解析计算。
- **与现有工作的关系**：统一了 GeMCL、原型网络（Prototypical Networks）、ALPaCA 等方法为 SB-MCL 的特例，并支持监督和无监督学习，可适配任意模型架构。

### 3. 实验设计
- **数据集与场景**：
  - **图像分类**：Omniglot、CASIA（中文手写，390万图像）、MS-Celeb-1M（1千万人脸）。
  - **回归任务**：正弦函数回归、图像补全（预测下半部分）、旋转角度预测。
  - **深度生成模型**：变分自编码器（VAE）和去噪扩散概率模型（DDPM）的生成任务。
  - **跨数据集泛化**：在 CASIA 上用元训练后的模型直接测试 Omniglot 上的性能。
- **Baseline 方法**：
  - SGD-based MCL：OML（在线元学习）及其一阶近似 OML-Reptile。
  - 序列模型持续学习：Transformer (TF) 和 Linear Transformer。
  - 离线/在线学习上界：在整个训练集上全量 SGD（离线）或单轮随机打乱训练（在线）。
  - SB-MCL 实例：分类用 GeMCL，回归用 ALPaCA，其他任务用通用因子化高斯变体。
- **评估设定**：主要采用 10-task 10-shot 设定，同时测试更多任务（最多 500）和更多样本（最多 200-shot）下的泛化能力。

### 4. 资源与算力
- 文中明确给出**部分元训练时间**对比（Table 6）：
  - 使用单块 **A40 GPU** 训练 **5万步** 的时间：
    - 图像分类：OML 6.5 小时，TF 1.2 小时，**SB-MCL 40 分钟**。
    - 图像补全：OML 16.5 小时，TF 1.4 小时，**SB-MCL 1.2 小时**。
    - VAE：OML 19 小时，**SB-MCL 1.2 小时**。
    - DDPM：OML 5 天，**SB-MCL 8 小时**。
  - SB-MCL 显著快于 OML（因内环无梯度，元训练可完全并行），也快于需要维护超长序列的 TF。

### 5. 实验数量与充分性
- **实验矩阵极为庞大**：
  - 3类监督任务 × 3种数据集（其中分类覆盖3个数据集）+ 两种无监督生成模型。
  - 每个 benchmark 均提供与 6 种以上 baseline 的对比。
  - 每个设置均给出了 5 次独立运行的平均值±标准差，确保统计可靠性。
  - 进一步包含：**跨域泛化**（CASIA 到 Omniglot）、**任务量扩展**（10→500 任务）、**样本量扩展**（10→200 shot）的大量实验。
  - 消融验证了 MAP 近似与蒙特卡洛估计的性能几乎一致。
- **公平性**：所有方法共享相同编码器架构，超参数调至同等最优，且在完全相同的训练流设定下比较，实验设计全面、客观且公平。

### 6. 主要结论与发现
- SB-MCL 在几乎所有任务上**大幅优于**基于 SGD 的 OML 和 Linear Transformer，性能与计算代价更高的 TF 相当甚至更优。
- 在 **长序列泛化**（更多任务/更多样本）中，SB-MCL 表现出极强的鲁棒性，性能几乎不下降甚至略有提升（符合固定充分统计量的理论预期），而 TF 和 OML 性能崩溃。
- 由于内环无需梯度反向传播，SB-MCL 的**元训练效率极高**（并行批量推理），支持大规模训练。
- 将遗忘问题转化为表征容量问题：只要网络表征足够强，SB-MCL 可达到近乎完美的持续学习。

### 7. 方法优点
- **抗遗忘的数学保证**：后验完全由指数族分布的理想贝叶斯更新得出，理论上可等价于批量学习，无灾难性遗忘。
- **域无关与模型无关**：可轻松嵌入任意编解码架构，覆盖监督、无监督及生成任务。
- **训练高效**：元训练阶段所有样本可并行处理，无需计算高阶梯度，极大降低训练时间。
- **强泛化能力**：在元测试中面对更长的任务序列或更多的样本时，依旧保持稳健性能。
- **理论扎实**：将 Fisher-Darmois-Koopman-Pitman 定理引入持续学习，为方法提供了坚实的统计基础。

### 8. 不足与局限
- **忽略数据顺序**：指数族后验的批处理等价性导致模型完全忽视训练数据的次序，无法利用课程学习等依赖顺序的场景。
- **表征容量的瓶颈**：性能最终受限于神经网络将原始数据映射到指数族后验的能力，对复杂任务可能需要更大规模的架构与数据。
- **非参数扩展受限**：框架依赖于恒定大小的后验，无法动态扩展存储；若要处理非平稳且不断新增任务，可能需要突破固定维度后验的假设。
- **实验局限**：当前实验主要基于图像基准（分类、补全、生成），缺乏自然语言处理、强化学习等更多领域的验证。
- **数据集假设**：MCL 需要大量元训练片段，目前此类大规模数据集仍然稀缺。

（完）
