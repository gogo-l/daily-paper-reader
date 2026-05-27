---
title: On the Diminishing Returns of Width for Continual Learning
title_zh: 持续学习中宽度的收益递减效应研究
authors: "Etash Kumar Guha, Vihan Lakshman"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=Ld255Mbx9F"
tags: ["query:continual"]
score: 9.0
evidence: 宽度在减少灾难性遗忘中收益递减的理论分析
tldr: 针对宽度对持续学习中灾难性遗忘的影响，首次构建理论框架分析前馈网络中宽度与遗忘的直接关系，证明增加宽度带来的遗忘减少呈收益递减。实验在以往未探索的超大宽度上验证了这一理论。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1680, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1736, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1624, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1696, \"height\": 638, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 752, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 747, \"height\": 595, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1680, \"height\": 1325, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1696, \"height\": 1365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-ld255mbx9f/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1180, \"height\": 904, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1280, \"height\": 678, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1286, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1625, \"height\": 761, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 682, \"height\": 1286, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1281, \"height\": 641, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1383, \"height\": 1910, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-ld255mbx9f/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1282, \"height\": 1933, \"label\": \"Table\"}]"
motivation: 尽管经验表明增加网络宽度能减少灾难性遗忘，但宽度与遗忘的精确关系尚不明朗，缺乏理论刻画。
method: 构建持续学习理论框架，推导前馈网络中宽度与遗忘的解析关系，揭示增加宽度的收益递减规律。
result: 理论证明并实验验证了宽度的收益递减效应，在大宽度范围内符合预测。
conclusion: 该工作为理解网络架构与遗忘的关系提供了理论基础，有助于设计更高效的持续学习模型。
---

## Abstract
While deep neural networks have demonstrated groundbreaking performance in various settings, these models often suffer from *catastrophic forgetting* when trained on new tasks in sequence. Several works have empirically demonstrated that increasing the width of a neural network leads to a decrease in catastrophic forgetting but have yet to characterize the exact relationship between width and continual learning. We design one of the first frameworks to analyze Continual Learning Theory and prove that width is directly related to forgetting in Feed-Forward Networks (FFN), demonstrating that the diminishing returns of increasing widths to reduce forgetting. We empirically verify our claims at widths hitherto unexplored in prior studies where the diminishing returns are clearly observed as predicted by our theory.

---

## 论文详细总结（自动生成）

好的，以下是对论文《On the Diminishing Returns of Width for Continual Learning》的详细结构化总结。

### 1. 论文的核心问题与整体含义
- **研究动机与背景**：深度神经网络在处理序列任务时，容易遭受“灾难性遗忘”，即学习新任务后，在旧任务上的性能急剧下降。
- **核心问题**：尽管经验表明，增加网络宽度（隐藏层神经元数量）能减轻遗忘，但宽度与持续学习能力之间的精确函数关系尚不清晰，尤其是在有限宽度的实际网络中。
- **整体含义**：本文旨在从理论和实验上严格刻画这一关系，揭示增加宽度带来的遗忘减少存在**收益递减**现象，即单纯扩大模型规模以解决灾难性遗忘并非可持续的良策。

### 2. 论文提出的方法论
- **核心思想**：建立一个分析前馈网络(FFN)持续学习误差的理论框架，并利用“宽网络在训练过程中距离初始化更近”（惰性训练）这一经验观察作为关键假设，将宽度建模为一种对模型功能距离的正则化器。
- **理论关键点**：
    - **关键假设( Assumption 4.3)**：模型在训练新任务后，其权重相对初始化的变化量（矩阵范数）与宽度 \(W\) 的 \(-\beta\) 次方成正比（\(\beta>0\)），且这一现象被广泛经验验证。
    - **推导过程简述**：首先计算顺序训练模型中共享活跃行（考虑行稀疏性）的期望数量；然后结合惰性训练假设，推导出权重变化的边界；最后通过扰动分析，将权重的微小变化传播至输出层，得出最终输出误差的边界。
- **核心公式与结论**：
    - **主要定理 (Theorem 4.1)**：对于任意深度的非线性FFN，连续学习误差 \(\epsilon_{t,t'}\) 的期望上界为 \(O\left((t'-t) L^{2L} W^{-\beta} \alpha^{\frac{1-2\beta}{2}}\right)\)。该公式揭示了：
        - **收益递减**：误差随宽度 \(W\) 的增大而减小，但减小速率由 \(W^{-\beta}\) 决定，呈现收益递减。
        - **线性任务累积**：误差随中间训练的任务数量 \((t'-t)\) 线性增加。
        - **深度负作用**：误差与深度 \(L\) 呈指数级依赖关系，增加深度会恶化遗忘。
        - **行稀疏性正作用**：适当的行稀疏性（减小 \(\alpha\)）可以降低误差。
    - **扩展：噪声稳定性**：通过引入层缓冲和激活收缩等数据依赖常数，进一步去除了对权重范数 |At,l| 的悲观依赖。

### 3. 实验设计
- **数据集与场景**：使用四个标准的持续学习基准数据集：**Rotated MNIST、Rotated Fashion MNIST、Rotated SVHN 和 Rotated GTSRB**。每个数据集构建5个任务，分别为原始图像旋转0°、22.5°、45°、67.5°和90°，并按顺序训练。
- **评估指标**：沿袭先前工作，使用**平均准确率(AA)、平均遗忘(AF)、学习准确率(LA) 和 联合准确率(JA)** 四个指标来衡量持续学习能力。
- **对比维度**：本项工作核心是验证宽度与遗忘的关系，并非对比不同方法。因此，其对比主要体现在：
    - **宽度范围**：测试了从32到**65536**（216）的极宽隐藏层，远超先前文献中常见的最大宽度2048，以清晰捕捉收益递减的现象。
    - **网络架构**：主要针对1层、2层、3层的前馈网络。同时，也在Wide ResNet架构上进行了初步实验。
    - **优化器**：验证了随机梯度下降(SGD)和Adam两种优化器。
    - **其他正则化**：探索了**行稀疏（Row-wise Sparsity）** 和 **Dropout** 对距离初始化及遗忘的影响。

### 4. 资源与算力
- 论文中明确指出，所有实验均在配备 **单个 NVIDIA A10 GPU** 的 **AWS g5g.8xlarge实例** 上进行。未提及具体的总训练时长。

### 5. 实验数量与充分性
- **实验组数**：实验覆盖度较高，具体包括：
    - **4个数据集** × **多种宽度**（通常从32到65536的十几个级别） × **3种深度（1-3层，附录中甚至扩展到6层）**，构成了主体实验矩阵。
    - 切换**优化器（SGD vs Adam）** 的对比实验。
    - **行稀疏度（α=0.1）** 和 **Dropout概率** 的消融研究。
    - 在**Wide ResNet**架构上的验证性实验。
    - 对**距离初始化、遗忘随时间变化、遗忘与深度/稀疏度关系**等进行了多维度绘图分析。
- **充分性与客观性**：实验设计较为全面和客观。为验证理论预测的收益递减，特意选择了极大的宽度范围，这是其关键亮点。对比公平，所有模型在相同设置下训练，验证了多个理论预言（如深度、任务数、稀疏度的影响）。

### 6. 论文的主要结论与发现
- **宽度的收益递减得到验证**：实验清楚观察到，随着宽度增加，遗忘起初快速下降，但在宽度达到约 2048 后，遗忘的减少趋于平缓甚至停滞，证实了理论预测的 \(W^{-\beta}\) 关系。
- **深度与遗忘正相关**：在合理深度内（如1至3层），增加网络深度确实会增加平均遗忘，与理论预测一致（深度过大时因梯度消失导致整体精度下降，从而干扰该规律）。
- **任务数与遗忘线性相关**：最终模型对更早期任务的遗忘量更大，且遗忘与任务索引大致呈线性关系，且该关系在不同宽度下似乎保持一致，符合理论。
- **行稀疏性有效对抗遗忘**：引入行稀疏（α=0.1）能显著降低平均遗忘，同时基本不损伤学习准确率，验证了理论中关于 \(\alpha\) 项的作用。

### 7. 优点
- **理论贡献显著**：为该领域提供了**首批量化分析前馈网络持续学习误差的理论框架之一**，推导出宽度、深度、任务数和稀疏度与遗忘的明确函数关系。
- **现象解释深刻**：理论预言并实验证实了**收益递减**这一新见解，修正了先前可能认为宽度与遗忘呈近似线性关系的观点。
- **实验规模宏大**：将网络宽度推至**65536**进行测试，清晰地展现了在常规宽度下难以观察到的收益递减现象，支撑了理论的可靠性。
- **分析维度全面**：不仅关注宽度，还从深度、任务数、稀疏性等多角度进行了理论推导和实验验证，构建了更完整的认知。

### 8. 不足与局限
- **理论依赖关键假设**：核心理论建立在“距离初始化”的幂律衰减假设（Assumption 4.3）上，而该假设本身未被严格证明，仅通过经验观察支撑。
- **模型类型局限**：理论分析严格限于**前馈网络(FFN)**。实验虽在Wide ResNet上做了初步探索，但尚未将理论扩展至卷积网络、残差网络或注意力机制等更复杂和主流的架构。
- **任务设定简单**：实验仅使用了图像旋转的简单任务，未在更复杂、更现实的持续学习场景（如任务增量学习、类增量学习）和更大规模的数据集上进行充分验证。
- **分析不完全**：作者也承认，该理论框架并不能完美捕捉关于灾难性遗忘的所有信息，是一个有价值的初步步骤。

（完）
