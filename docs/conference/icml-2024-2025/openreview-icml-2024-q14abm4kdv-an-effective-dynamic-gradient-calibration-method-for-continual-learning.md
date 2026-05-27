---
title: An Effective Dynamic Gradient Calibration Method for Continual Learning
title_zh: 一种有效的持续学习动态梯度校准方法
authors: "Weichen Lin, Jiaxiang Chen, Ruomin Huang, Hu Ding"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=q14AbM4kdv"
tags: ["query:continual"]
score: 9.0
evidence: 梯度校准方法缓解灾难性遗忘
tldr: 本文提出一种有效的动态梯度校准方法，用于解决持续学习中的灾难性遗忘问题。从梯度视角出发，校准每个模型更新步骤中的梯度，引导模型在吸收新知识的同时保护旧任务信息。实验表明，该方法在多个持续学习数据集上显著降低了遗忘，提升了整体性能。该工作为通过梯度调控实现持续学习提供了简单而有效的解决方案。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-q14abm4kdv/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 605, \"height\": 456, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-q14abm4kdv/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1679, \"height\": 665, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-q14abm4kdv/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 682, \"height\": 531, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1654, \"height\": 833, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 711, \"height\": 745, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 997, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1219, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1549, \"height\": 740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1560, \"height\": 740, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1046, \"height\": 567, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-q14abm4kdv/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1608, \"height\": 217, \"label\": \"Table\"}]"
motivation: 灾难性遗忘是持续学习中的核心挑战，现有方法仍难以完全避免。
method: 提出动态梯度校准算法，通过校准每次更新的梯度来保护历史知识。
result: 在多个基准上有效降低遗忘，提升持续学习性能。
conclusion: 为通过梯度操作缓解遗忘提供了新思路。
---

## Abstract
Continual learning (CL) is a fundamental topic in machine learning, where the goal is to train a model with continuously incoming data and tasks. Due to the memory limit, we cannot store all the historical data, and therefore confront the ``catastrophic forgetting'' problem, i.e., the performance on the previous tasks can substantially decrease because of the missing information in the latter period. Though a number of elegant methods have been proposed, the catastrophic forgetting phenomenon still cannot be well avoided in practice. In this paper, we study the problem from the gradient perspective, where our aim is to develop an effective algorithm to calibrate the gradient in each updating step of the model; namely, our goal is to guide the model to be updated in the right direction under the situation that a large amount of historical data are unavailable. Our idea is partly inspired by the seminal stochastic variance reduction methods (e.g., SVRG and SAGA) for reducing the variance of gradient estimation in stochastic gradient descent algorithms. Another benefit is that our approach can be used as a general tool, which is able to be incorporated with several existing popular CL methods to achieve better performance. We also conduct a set of experiments on several benchmark datasets to evaluate the performance in practice.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义
- **研究动机**：持续学习（Continual Learning, CL）要求模型在连续到来的任务流中学习，但由于无法存储全部历史数据，会出现灾难性遗忘（catastrophic forgetting），即模型对旧任务的性能大幅下降。
- **整体含义**：现有方法虽多，但遗忘问题在实践中仍难以完全避免。本文从梯度视角出发，旨在设计一种有效的梯度校准算法，引导模型在历史数据缺失的情况下向正确方向更新，从而减缓遗忘。方法受随机方差缩减技术（如 SVRG、SAGA）的启发，将“批大小限制”下的梯度校准思路迁移到“缓冲区大小限制”的持续学习场景。

## 方法论：动态梯度校准（DGC）
- **核心思想**：维护一个梯度校准项，通过递归方式利用整个历史数据的信息来估计更精确的梯度，降低梯度估计方差，从而在更新时更好地保留旧知识。
- **关键技术细节**：
  - **两级动态更新机制**：
    - **任务内训练阶段**：将当前任务训练过程划分为多个阶段，在每个阶段开始时记录模型参数 \(\tilde{\theta}_t\)。利用缓冲区 \(M_t\) 和历史校准项 \(\Gamma'_{\mathrm{DGC}}(t)\) 计算校准梯度：
      \[
      v_k^t = \frac{1}{t}[\nabla_\theta\ell(x_t,y_t,\theta_k^t) - \nabla_\theta\ell(\dot{x}_t,\dot{y}_t,\tilde{\theta}_t) + G(\mathcal{T}_t,\tilde{\theta}_t)] + \frac{t-1}{t}\Gamma_{\mathrm{DGC}}(t,k)
      \]
      其中 \(\Gamma_{\mathrm{DGC}}(t,k)\) 由递归式 \(\Gamma_{\mathrm{DGC}}(t,k) = \nabla_\theta\ell(\bar{x}_t,\bar{y}_t,\theta_k^t) - (\nabla_\theta\ell(\ddot{x}_t,\ddot{y}_t,\tilde{\theta}_t) - \Gamma'_{\mathrm{DGC}}(t))\) 给出，\(\Gamma'_{\mathrm{DGC}}(t)\) 在每阶段结束后更新为 \(\Gamma_{\mathrm{DGC}}(t,m+1)\)。
    - **任务转换阶段**：将 \(\Gamma'_{\mathrm{DGC}}(t)\) 与新任务的梯度信息融合：
      \[
      \Gamma'_{\mathrm{DGC}}(t+1) = \frac{1}{t}[(t-1)\cdot\Gamma'_{\mathrm{DGC}}(t) + G(\mathcal{T}_t,\tilde{\theta}_t)]
      \]
  - **可与现有方法结合**：DGC 能够灵活嵌入到基于经验回放的方法（如 ER、DER++、XDER、Dynamic ER）中，通过调节参数 \(\alpha\) 混合校准梯度与原方法梯度。
  - **理论保证**：在 \(f(x;\theta)\) 为 \(L\)-光滑且 \(\gamma\)-强凸的假设下，DGC 在任务 \(t\) 内具有线性收敛速率（定理 3.3）。
- **算法流程**：整体采用任务循环，每个任务内进行多阶段迭代，每阶段执行 \(m\) 步动量更新，然后更新 \(\Gamma'_{\mathrm{DGC}}\)；任务结束时通过 reservoir sampling 更新缓冲区，并修正 \(\Gamma'_{\mathrm{DGC}}\)。

## 实验设计
- **数据集与场景**：
  - **CIL（类增量学习）**：S-CIFAR10（5任务/各2类）、S-CIFAR100（10任务/各10类）、S-TinyImageNet（10任务/各20类）。
  - **TFCL（无任务边界）**：S-CIFAR100，将每个数据批次视为微任务，不依赖任务身份信息。
- **对比方法**：
  - 回放方法：ER、DER++、XDER、MOCA、GSS、GCR、HAL、iCARL。
  - 优化方法：AGEM、AOP、SSVRG。
  - 动态结构方法：Dynamic ER。
  - 本文提出的 DGC 与上述部分方法的结合（DGC-ER、DGC-DER++、DGC-XDER、DGC-Dynamic ER）。
- **评价指标**：最终平均增量精度（FAIA）、平均准确率（AA）、最终遗忘（FF）。
- **实现细节**：使用 ResNet18 作为基础网络，基于 Mammoth/PyCIL 等开源框架，重复 10 次实验取均值和标准误差。固定 DGC 的超参数 \(m=200\)、\(\alpha=1e-3\)。

## 资源与算力
- 论文未明确说明所使用的 GPU 型号、数量或总训练时长。
- 仅在附录表 8 中给出了在 S-CIFAR100 上前三个任务（每任务）的训练时间示例（如 DGC 任务1 约 218 秒，任务2 约 666 秒），但未提及硬件环境。这是实验报告中的一个缺失信息。

## 实验数量与充分性
- **实验组数**：在 3 个数据集上，针对不同缓冲区大小（500/2000/2000-5000）进行了全面测试；增设了任务数为 5 和 20 的对比实验；进行了 TFCL 场景的评估；对关键超参数 \(\alpha\) 和 \(m\) 进行了消融研究；还分析了训练损失的平滑性。
- **充分性与公平性**：实验覆盖了多种主流 CL 方法和不同设定，对比时使用了基线方法的原始超参数和统一网络架构，重复实验并报告标准差，具有较强的客观性和公平性。消融实验验证了 DGC 在不同 \(\alpha\) 和 \(m\) 下的鲁棒性及其边际效益。

## 论文的主要结论与发现
- DGC 能够普遍提升现有 CL 方法的性能，尤其在 CIFAR100 和 TinyImageNet 上，结合 DynER 后可获得超过 6% 的 FAIA 提升。
- 随着任务数量增加（如 20 任务 vs 5 任务），DGC 带来的相对改善更为显著，表明其在严重遗忘情境下效果更好。
- 在同等内存占用下，DGC 的额外梯度校准存储比单纯增加回放样本能带来更大的边际收益。
- DGC 不仅提升最终精度，还使训练过程中的损失下降更为平滑，有助于实际调参和稳定训练。

## 优点
- **新颖的视角**：从梯度方差缩减角度解决持续学习中的灾难性遗忘，将 SVRG 思想适配到“缓冲区限制”场景，具有理论分析支撑。
- **即插即用**：可以作为一个通用模块，方便地与现有多种基于回放的 CL 方法结合，而无需大幅改动原算法。
- **性能提升稳定**：在多个基准数据集和不同设置下均表现出对基线的稳健提升，并降低了训练波动。
- **边际效益证明**：通过内存-精度曲线直观展示了 DGC 比单纯增大回放缓冲区更具成本效益。

## 不足与局限
- **额外内存开销**：存储梯度校准项会增加显存消耗；虽然实验表明其边际效益优于同内存下增加样本，但在极端内存受限的场景下可能受一定限制。
- **理论假设较强**：线性收敛率依赖于强凸和光滑假设，而实际深度网络非凸，理论指导价值大于直接应用。
- **任务边界依赖**：原方法主要针对 CIL 设计，对 TFCL 的适配通过将每个 batch 作为微任务实现，可能对超参数较敏感。
- **实验局限性**：仅在分类任务上验证，未涉及回归、生成或强化学习等场景；对比方法集中在经典基线，未包含最新的一些大模型或参数隔离类方法。
- **硬件信息缺失**：未提供训练所用 GPU 型号等算力详情，可能影响复现的参考性。

（完）
