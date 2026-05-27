---
title: "Online Curvature-Aware Replay: Leveraging $\\mathbf{2^{nd}}$ Order Information for Online Continual Learning"
title_zh: 在线曲率感知回放：利用二阶信息进行在线持续学习
authors: "Edoardo Urettini, Antonio Carta"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=ek5a5WC4TW"
tags: ["query:continual"]
score: 9.0
evidence: 在线持续学习方法利用二阶曲率信息实现稳定适应
tldr: 针对在线连续学习中的数据非稳态和任务信息缺失问题，提出OCAR方法，将基于回放的OCL形式化为带KL约束的二阶在线联合优化，并利用K-FAC近似的Fisher信息矩阵预条件梯度，作为稳定器防止遗忘并加速适应。实验表明其优于现有在线连续学习方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 796, \"height\": 245, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 776, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 808, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1756, \"height\": 592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1620, \"height\": 1097, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1216, \"height\": 729, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1214, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1217, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 874, \"height\": 529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1053, \"height\": 525, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ek5a5wc4tw/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1719, \"height\": 483, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ek5a5wc4tw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 670, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ek5a5wc4tw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 269, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ek5a5wc4tw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 651, \"height\": 516, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ek5a5wc4tw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 643, \"height\": 517, \"label\": \"Table\"}]"
motivation: 在线连续学习面临数据流非稳态和任务边界不明确，传统方法和回放方法在任务转换后不稳定，需要更鲁棒的优化策略。
method: 提出OCAR，将回放式OCL建模为二阶在线联合优化，用K-FAC近似费舍尔信息矩阵对梯度预条件，利用曲率信息稳定学习过程。
result: 在多个在线连续学习基准上，OCAR显著降低了遗忘，提高了稳定性和性能。
conclusion: OCAR表明二阶信息可以有效稳定在线连续学习，为实时数据流学习提供了强有力的方法。
---

## Abstract
Online Continual Learning (OCL) models continuously adapt to nonstationary data streams, usually without task information. These settings are complex and many traditional CL methods fail, while online methods (mainly replay-based) suffer from instabilities after the task shift. To address this issue, we formalize replay-based OCL as a second-order online joint optimization with explicit KL-divergence constraints on replay data. We propose Online Curvature-Aware Replay (OCAR) to solve the problem: a method that leverages second-order information of the loss using a K-FAC approximation of the Fisher Information Matrix (FIM) to precondition the gradient. The FIM acts as a stabilizer to prevent forgetting while also accelerating the optimization in non-interfering directions. We show how to adapt the estimation of the FIM to a continual setting, stabilizing second-order optimization for non-iid data, uncovering the role of the Tikhonov damping in the stability-plasticity tradeoff.
  Empirical results show that OCAR outperforms state-of-the-art methods in continual metrics, achieving higher average accuracy throughout the training process in three different benchmarks.

---

## 论文详细总结（自动生成）

### 论文总结：Online Curvature-Aware Replay

#### 1. 论文核心问题与研究动机
*   **核心问题**：在线持续学习（Online Continual Learning, OCL）要求模型在非稳态数据流（nonstationary data streams）上连续适应，过程中不提供任务边界、身份等先验信息。
*   **研究动机与背景**：
    *   传统持续学习方法在此设定下经常失效，而主流基于经验回放（Experience Replay, ER）的在线方法在任务切换后易出现性能急剧下降（即“稳定性鸿沟”，stability gap）和塑性丧失（loss of plasticity）。
    *   现有方法多将稳定性优化建立在对塑性的牺牲之上，且通常在任务结束时才评估防遗忘效果，未能保证整个训练流程的稳定。
    *   本研究旨在设计一种在每一步都能同时优化稳定性与可塑性、将OCL视为连续滤波过程的优化器。

#### 2. 方法论：OCAR（Online Curvature-Aware Replay）
*   **核心思想**：将基于回放的OCL形式化为一个带显式KL散度约束的二阶在线联合优化问题。利用损失函数曲率（即二阶信息）来预条件梯度，既作为稳定器防止遗忘旧知识，又在非干扰方向上加速新知识的学习。
*   **关键技术细节与算法流程**：
    **a. 优化问题形式化**：在每一步更新δ时，不仅最小化新数据（\(N_t\)）和回放缓冲数据（\(B_t\)）上的KL散度，还加入两项约束：
        *   **硬稳定性约束**：限制模型在回放数据上预测分布的KL散度变化，即 \(\hat{KL}(f_{w_{t-1}}(x_{B_t}) || f_{w_t}(x_{B_t})) \le \rho\)。
        *   **L2正则化约束**：限制参数更新幅度 \( \frac{1}{2}||\delta||_2^2 \le \epsilon \)。
    **b. 二阶近似与Fisher信息矩阵**：
        *   对损失和稳定性约束进行二阶泰勒展开，优化问题的解变为 \(\delta_t^* = -(H_{N_t} + H_{B_t} + \lambda F_{B_t} + \tau I)^{-1}(\nabla_{N_t} + \nabla_{B_t})\)，其中\(H\)为Hessian矩阵，\(F_{B_t}\)为Fisher信息矩阵（FIM），\(\lambda\)和\(\tau\)为拉格朗日乘子。
        *   利用FIM与广义高斯-牛顿矩阵（GGN）的等价性，将Hessians近似为FIM，最终更新简化为 \(\delta_t^* = -\alpha(F_{N_t} + (1+\lambda)F_{B_t} + \tau I)^{-1}(\nabla_{N_t} + \nabla_{B_t})\)。
    **c. K-FAC高效近似**：采用Kronecker-factored Approximate Curvature (K-FAC) 的块对角形式来近似庞大的FIM，使其求逆在计算上可行。FIM由每层激活和梯度的外积期望组成，并通过指数移动平均（EMA）持续更新。
    **d. OCL场景关键调整**：
        *   **Tikhonov阻尼\(\tau\)调度**：初始化为学习率\(\alpha\)，并在每一步增加，以应对引入新类时带来的不稳定性，控制了稳定性-可塑性权衡。
        *   **K-FAC因子在任务边界重置**：当分类器（最后一层）形状因新类增加而变化时，重置与该层梯度相关的因子\(G\)，但保留与激活相关的因子\(\bar{A}\)。
        *   **稳定性约束强度\(\lambda\)调度**：在类增量场景下，\(\lambda\)随遇到的类别数增加；在域增量场景下，\(\lambda\)随时间增长。

#### 3. 实验设计
*   **数据集/场景**：
    *   **类增量（Task-Incremental）**：Split-CIFAR100 (20任务)，Split-TinyImageNet (20任务)。
    *   **域增量（Domain-Incremental）**：Online CLEAR (10任务)。
*   **基准对比方法**：与大量基线方法对比，包括 i.i.d. 训练、ER、GDumb、AGEM、ER+LwF、MIR、RAR、DER++、ER-ACE、SCR、OnPro、OCM，以及当时SOTA的LPR。
*   **评价指标**：聚焦于OCL的核心度量。
    *   **WC-Acc (Worst-Case Accuracy)**：衡量模型稳定性，惩罚“稳定性鸿沟”。
    *   **AAA (Average Anytime Accuracy)**：衡量模型在整个训练过程中的平均准确率。
    *   **Acc (Final Average Accuracy)**：训练结束时的快照准确率。
    *   **Probed Acc (Linear Probing Accuracy)**：冻结特征提取器后重训线性分类器，衡量表征质量。

#### 4. 资源与算力
*   **硬件**：实验在一台配备Nvidia Tesla V100 (16GB) GPU和Intel Xeon Gold 6140M CPU的Linux集群上进行，训练未进行多GPU并行化。
*   **训练时长**：论文报告了在Split-CIFAR100上首个任务的训练时间。OCAR耗时38秒，约为标准ER（14秒）的3倍，但快于其他复杂方法如SCR（131秒）和LPR（213秒）。

#### 5. 实验数量与充分性
*   **实验组数**：在3个不同的基准数据集上进行了评估，对比了超过10种基线方法。所有实验重复5次（LPR为10次）以确保统计稳定性。
*   **超参数搜索**：采用与基线方法（LPR除外）一致的公平搜索策略，基于前4个任务的验证集性能选择超参数（共100次尝试），这对OCAR的长期稳定性提出了挑战。
*   **消融与分析实验**：
    *   **定性实验**：在Split MNIST上可视化模型训练轨迹和损失曲面（图1），直观展示OCAR比ER更平滑的优化路径。
    *   **凸设定对比实验**：在一个小规模凸问题中，专门对比了ER、EWC（使用二次惩罚）、Natural Gradient Descent（NGD）和OCAR（图3），分析它们在适应性和稳定性上的差异。
    *   **超参数分析**：在网格搜索中，深入分析了学习率α、阻尼\(\tau\)及二者比值\(\alpha/\tau\)如何影响稳定性（遗忘）和可塑性（新任务准确率）（图2）。
*   **公平性与客观性**：实验复用了(L Soutif-Cormerais et al., 2023)和(Yoo et al., 2024)的公开代码与设置，直接与已发表结果进行比较，最大程度保证了对比的公平性和客观性。

#### 6. 主要结论与发现
*   **性能优越**：OCAR在多个基准的持续学习关键指标（AAA, WC-Acc）上取得了SOTA性能，尤其在任务边界后表现更稳定，无显著“稳定性鸿沟”。
*   **表征学习能力强**：在线性探测（Probed Acc）准确率上，OCAR全面优于其他方法，甚至超过i.i.d.训练基准，说明其学得了更优的特征表示。
*   **可组合性**：OCAR可与ER-ACE等方法结合（OCAR-ACE），取得更强的效果，在Split-CIFAR100上几乎追平i.i.d.训练的最终准确率。
*   **超参数可解释性**：揭示了Tikhonov阻尼\(\tau\)与学习率\(\alpha\)的比值在稳定性-可塑性权衡中的关键作用：该比值有效控制了在曲率较小（不稳定）方向上的更新步长。

#### 7. 优点
*   **理论驱动**：基于信息几何和二阶优化的清晰理论框架，将OCL问题形式化为一个带约束的优化问题，有别于传统的启发式正则化方法。
*   **创新性应用**：创造性地将K-FAC高效二阶优化器应用于非i.i.d.的在线持续学习场景，并解决了其在任务边界不稳定的关键难题。
*   **全面的性能提升**：不仅在最终准确率上有竞争力，更在衡量学习过程的AA和WC-Acc等指标上显著领先，直击“稳定性鸿沟”要害。
*   **良好的可解释性**：对超参数\(\alpha\), \(\tau\)和\(\lambda\)的作用给出了清晰的物理解释，指导了实际应用中的调优。

#### 8. 不足与局限
*   **计算开销**：相比简单的ER基线，OCAR的训练时间大约是其3倍，虽然快于一些SOTA方法，但仍是一个额外的成本。
*   **损失函数兼容性**：与DER++等方法结合时表现不稳定，论文推测是因其损失函数与KL散度差异过大，破坏了FIM的近似前提。这表明方法的通用性可能限于使用KL散度衍生损失（如交叉熵）的场景。
*   **超参数搜索挑战**：超参数选择基于短期流（4个任务）的验证性能，这对追求长期稳定性的OCAR是次优的，虽然采用了\(\tau\)增量设计来缓解，但本质上仍是挑战。
*   **对类别信息的依赖**：\(\lambda\)的调度需要已知每批数据的新类别数量，这在完全无任务信息的极端OCL设定下可能无法获取。

（完）
