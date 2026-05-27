---
title: "ZeroFlow: Overcoming Catastrophic Forgetting is Easier than You Think"
title_zh: "ZeroFlow: 克服灾难性遗忘比你想象的更简单"
authors: "Tao Feng, Wei Li, Didi Zhu, Hangjie Yuan, Wendi Zheng, Dan Zhang, Jie Tang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=iPDw3O6u3T"
tags: ["query:continual"]
score: 9.0
evidence: ZeroFlow是一个评估无梯度优化算法以克服灾难性遗忘的基准。
tldr: ZeroFlow针对梯度不可用场景（如黑盒API、硬件限制）下的灾难性遗忘问题，提出了首个无梯度持续学习基准。该基准评估了一系列仅使用前向传播的优化算法，在多种遗忘场景和数据集上实验表明，仅靠前向传播即可有效缓解遗忘。这一发现为无法获取梯度信息的实际应用提供了简单高效的方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 858, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 730, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1717, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 879, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 850, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1784, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 836, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 847, \"height\": 562, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ipdw3o6u3t/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1762, \"height\": 1763, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ipdw3o6u3t/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1768, \"height\": 873, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ipdw3o6u3t/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 867, \"height\": 310, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ipdw3o6u3t/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 855, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ipdw3o6u3t/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1391, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ipdw3o6u3t/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1173, \"height\": 385, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ipdw3o6u3t/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1049, \"height\": 569, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ipdw3o6u3t/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1484, \"height\": 408, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ipdw3o6u3t/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1059, \"height\": 525, \"label\": \"Table\"}]"
motivation: 实际应用中常因黑盒API或硬件限制无法获取梯度，导致现有持续学习方法失效。
method: 设计首个无梯度优化基准ZeroFlow，评估多种仅基于前向传播的算法在克服遗忘上的表现。
result: 实验表明，仅使用前向传播的算法足以在多个数据集和遗忘场景中缓解灾难性遗忘。
conclusion: 揭示了无梯度方法在持续学习中的有效性，为受限环境下的应用提供了新方向。
---

## Abstract
Backpropagation provides a generalized configuration for overcoming catastrophic forgetting. Optimizers such as SGD and Adam are commonly used for weight updates in continual learning and continual pre-training. However, access to gradient information is not always feasible in practice due to black-box APIs, hardware constraints, or non-differentiable systems, a challenge we refer to as the gradient bans. To bridge this gap, we introduce ZeroFlow, the first benchmark designed to evaluate gradient-free optimization algorithms for overcoming forgetting. ZeroFlow examines a suite of forward pass-based methods across various algorithms, forgetting scenarios, and datasets. Our results show that forward passes alone can be sufficient to mitigate forgetting. We uncover novel optimization principles that highlight the potential of forward pass-based methods in mitigating forgetting, managing task conflicts, and reducing memory demands. Additionally, we propose new enhancements that further improve forgetting resistance using only forward passes. This work provides essential tools and insights to advance the development of forward-pass-based methods for continual learning.

---

## 论文详细总结（自动生成）

## 论文核心问题与整体含义
- **研究动机**：在持续学习和持续预训练场景中，反向传播及其变体（SGD、Adam）依赖梯度信息来克服灾难性遗忘。然而，现实应用中常因黑盒API、硬件约束、不可微系统等原因无法获取梯度，本文将该困境称为“梯度禁令（gradient bans）”。
- **核心问题**：能否在梯度不可用的情况下，仅依靠前向传播（无梯度）来有效缓解灾难性遗忘？据此，论文构建了首个无梯度持续遗忘基准——ZeroFlow，旨在系统评估仅利用函数值（零阶信息）的优化算法在多种遗忘场景下的表现。
- **整体含义**：本文试图证明克服灾难性遗忘其实比想象中简单，前向传播本身已蕴含足够的优化信号，从而为受限环境（如模型即服务、神经形态硬件、科学计算）提供高效、低成本的解决方案。

## 方法体系
- **整体思路**：将零阶优化（Zeroth-Order Optimization）引入到遗忘问题中，利用参数扰动后的损失变化估计梯度方向，全程无需反向传播。理论依据是零阶方法只需函数值，天然规避梯度禁令。
- **核心算法框架**（算法1）：
  - 步骤1：零阶梯度估计。主要采用对称扰动的SPSA，$\hat{\nabla} L(\theta,\xi;B)=\frac{L(\theta+\epsilon\xi;B)-L(\theta-\epsilon\xi;B)}{2\epsilon} \xi^{-1}$，其中$\xi$通常服从Rademacher分布，仅需两次前向传播。
  - 步骤2：下降方向计算。多种变体如直接使用估计梯度（ZO-SGD）、取其符号（ZO-SGD-Sign）、保守选择局部最优候选点（ZO-SGD-Conserve）等。
  - 步骤3：参数更新。支持SGD和Adam族优化器，如ZO-Adam等。此外，引入Forward-Grad（基于前向自动微分的雅可比向量积）作为另一条技术路径。
- **关键技术细节**：
  - 查询预算 $q$ 可控，$q=1$ 为默认高效设定，增加查询数量可稳定梯度估计但增加耗时。
  - 提出三项增强措施以进一步提升遗忘抵抗能力：
    - **混合零阶优化（Hybrid ZO）**：先用一阶粗调至局部极值，再切换零阶探索平坦区域。
    - **历史梯度重加权**：在新任务优化时，将新老梯度按比例混合 $g_{\text{old}}=(1-\alpha)g_{\text{old}}+\alpha g_{\text{historical}}$，稳定扰动。
    - **稀疏诱导估计**：随机掩码部分梯度分量置零，降低噪声方差。

## 实验设计
- **遗忘场景**：类增量学习（Class-Incremental Learning），每个任务引入新的类别，不存储历史样本。
- **模型与预训练**：使用ViT-B/16预训练于ImageNet-1K，在其上微调两种前沿的持续学习方法——EASE和APER。
- **数据集**：CIFAR-100、CUB、ImageNet-A、OmniBenchmark，难度覆盖标准基准到与预训练分布差异大的数据集。每个数据集均被划分为10个增量任务。
- **对比方法**：
  - 一阶方法：FO-SGD、FO-Adam（需要反向传播）。
  - 零阶方法：ZO-SGD、ZO-SGD-Sign、ZO-SGD-Conserve、ZO-Adam、ZO-Adam-Sign、ZO-Adam-Conserve、Forward-Grad。此外评估不同查询预算（$q=1,2,4,8,16,32$）的影响。
- **评价指标**：平均准确率、最后任务准确率、遗忘量（BWT），以及内存占用和运行时间。
- **扩展实验**：增加至20个任务的长序列测试、用记忆回放方法（MEMO）检验零阶方法的兼容性、在更大模型（ViT-L/16、ViT-H/14）上验证资源效率。

## 资源与算力
- 文中在内存效率部分指出：FO-SGD在CIFAR-100上，batch size 64~512下，随着任务进行内存需求急剧增加（例如batch size=512时，第五阶段内存比初始增加30.08 GB），而ZO-SGD仅增加3.92 GB，始终只需单张24 GB GPU。ZO方法内存占用约为FO的1/5。
- 运行时间上，ZO-SGD单epoch耗时约为FO的50%~70%（取决于batch size和数据集），但增加查询预算会延长运行时间（如$q=4$时增加约3倍）。
- 论文未提供训练所用GPU型号、总训练时长或总GPU小时数等完整算力清单。

## 实验数量与充分性
- 实验覆盖了：
  - 2个模型（EASE、APER）× 4个数据集 × 多种优化器变体，形成主要对比表（表1）。
  - 效率对比（表2）包括大batch size下的内存增长曲线（图9）。
  - 不同查询预算的性能曲线（图5）。
  - 优化轨迹可视化（图4、图10），直观比较一阶与不同零阶变体。
  - 三项增强技术各自的消融实验（表3、表4、表5），以及组合增强的效果。
  - 扩展到记忆回放方法（表6）、更大模型（表7）、更长任务序列（表8）等场景。
- 实验规模较大，多维度对比确保了结论的客观性和公平性。基线清晰（一阶方法作为上界对照），评估指标全面，消融分析充分。唯一小缺憾是部分实验（如增强方法组合）仅在ImageNet-A上展示，未覆盖所有数据集。

## 主要结论与发现
- **仅前向传播足以克服遗忘**：在多数设定下，零阶方法的性能接近甚至偶尔超越一阶方法，尤其在内存受限环境中优势明显。
- **零阶优化能有效管理新旧任务冲突**：其梯度估计的天然随机性有助于探索平坦区域，平衡学习与遗忘。
- **内存与运行时间优势**：零阶方法内存占用约为反向传播的1/5，运行时间降低约一半，对大规模模型或长序列扩展友好。
- **三项增强进一步提升了仅用前向传播的抗遗忘能力**，且彼此正交可叠加。

## 优点
- **问题导向明确**：首次针对“梯度不可用”的实际困境提出系统性的无梯度遗忘基准，填补了研究空白。
- **方法体系简洁**：仅利用前向传播，无需存储中间激活，天然降低资源要求，易于在受限环境中部署。
- **评估全面扎实**：涵盖多种零阶优化变体、不同复杂度的数据集、多种遗忘模型，配有丰富的轨迹可视化和效率分析。
- **实践指导性强**：提出的增强技术（混合优化、历史加权、稀疏化）简单有效，可直接集成到现有零阶优化框架中。

## 不足与局限
- **未涵盖从零训练**：实验基于强预训练模型进行微调，零阶方法在从随机初始化训练时收敛慢的固有缺陷未得到根本解决，可能限制其在无预训练场景下的应用。
- **超参数敏感性**：增强技术引入了新的比例或稀疏度等超参数，文中未深入讨论其对不同任务的敏感性及调参成本。
- **任务类型单一**：主要集中在图像分类的类增量学习，未探索任务增量、域增量或其他模态（如NLP）的遗忘问题。
- **算力报告不完整**：缺少训练总时长、GPU具体型号等细节，难以精确评估其实际资源开销。
- **可扩展性的进一步测试**：虽在更大Vision Transformer上验证了资源效率，但未涉及当前规模巨大的语言模型，其实用上限有待明晰。

（完）
