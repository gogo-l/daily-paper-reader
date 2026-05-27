---
title: "Understanding the Forgetting of (Replay-based) Continual Learning via Feature Learning: Angle Matters"
title_zh: 理解（基于回放的）持续学习中的遗忘：角度至关重要
authors: "Hongyi Wan, Shiyuan Ren, Wei Huang, Miao Zhang, Xiang Deng, Yixin Bao, Liqiang Nie"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6UIer20oYA"
tags: ["query:continual"]
score: 8.0
evidence: 通过特征学习理论分析持续学习中的遗忘，任务信号向量夹角影响遗忘程度
tldr: 针对持续学习中遗忘因素的理论理解不足，本文基于两层卷积神经网络与信号噪声数据模型，利用特征学习理论揭示了任务信号向量夹角对遗忘的影响：锐角或小钝角导致良性遗忘，大钝角导致灾难性遗忘，为遗忘机理提供了新见解。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6uier20oya/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uier20oya/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uier20oya/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 763, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uier20oya/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1092, \"height\": 713, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6uier20oya/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 683, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uier20oya/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 680, \"height\": 282, \"label\": \"Table\"}]"
motivation: 现有持续学习遗忘分析多基于线性回归或惰性训练，缺乏在实用CNN下的特征学习视角。
method: 采用两层CNN与多项式ReLU激活，在信号噪声模型下分析任务信号向量的夹角与遗忘的理论关系。
result: 理论证明并实验验证了任务向量夹角是影响遗忘的关键因素，锐角/小钝角下遗忘较轻。
conclusion: 该工作为持续学习中的遗忘现象提供了基于特征学习的统一理论框架。
---

## Abstract
Continual learning (CL) is crucial for advancing human-level intelligence, but its theoretical understanding, especially regarding factors influencing forgetting, is still relatively limited. This work aims to build a unified theoretical framework for understanding CL using feature learning theory. Different from most existing studies that analyze forgetting under linear regression model or lazy training, we focus on a more practical two-layer convolutional neural network (CNN) with polynomial ReLU activation for sequential tasks within a signal-noise data model. Specifically, we theoretically reveal how the angle between task signal vectors influences forgetting that: *acute or small obtuse angles lead to benign forgetting, whereas larger obtuse angles result in harmful forgetting*. Furthermore, we demonstrate that the replay method alleviates forgetting by expanding the range of angles corresponding to benign forgetting. Our theoretical results suggest that mid-angle sampling, which selects examples with moderate angles to the prototype, can enhance the replay method's ability to mitigate forgetting. Experiments on synthetic and real-world datasets confirm our theoretical results and highlight the effectiveness of our mid-angle sampling strategy.

---

## 论文详细总结（自动生成）

好的，这是基于提供的论文内容生成的结构化中文总结。

### 论文核心问题与整体含义
本篇论文旨在解决**持续学习**领域中的一个核心理论空白：即在非线性的、实际应用的神经网络模型下,究竟是什么因素导致了**灾难性遗忘**。
*   **研究动机**：现有的遗忘理论分析大多局限于线性模型或神经正切核的“惰性”训练机制，这些强假设无法完全捕捉实际深度学习中发生“特征学习”时的遗忘动态。因此，建立一个更贴近现实的统一理论框架至关重要。
*   **整体含义**：该工作首次将**特征学习理论**应用于持续学习的遗忘分析，在一个具体的两层卷积神经网络和信号-噪声数据模型中,揭示了**任务信号向量之间的“角度”是决定遗忘性质（良性或有害）的关键因素**。这不仅加深了对遗忘机理的理解，还为改进基于回放的持续学习方法提供了理论指导。

### 论文提出的方法论
论文的核心方法是通过特征学习理论，在一个受控的理论环境下，严密分析神经网络在学习连续两个任务时的动态过程。

*   **核心思想**：将遗忘归因于代表不同任务类别的**信号向量**（即原型）之间的几何关系，特别是它们之间的夹角。关键在于分析网络中不同神经元群组在任务切换时的行为拮抗。
*   **关键技术细节**：
    *   **问题设定**：研究两个序列二分类任务，数据模型为“信号+噪声”，其中信号向量\( \mu_k \)代表任务\( T_k \)的核心特征，噪声向量与所有信号正交。
    *   **模型**：采用一个两层、具有多项式ReLU (\( ReLU^q, q>2 \))激活函数的卷积神经网络，并通过梯度下降来最小化交叉熵损失。
    *   **理论分析工具 - 信号-噪声分解**：将网络的权重向量动态分解为信号学习系数 \( \gamma \) 和噪声记忆系数 \( \rho \)。通过分析这些系数的迭代更新，简化了对复杂学习动态的理解。
    *   **关键理论发现 (Theorem 3.2 & 3.3)**:
        *   **锐角与小钝角 (\( -C_1 \le \cos\theta_{1,2} \le 1 \))**：导致**良性遗忘**，即模型在学习新任务后，对旧任务的测试误差依然很小。原因是负责学习任务1信号的神经元群组占主导地位。
        *   **大钝角 (\( -1 \le \cos\theta_{1,2} < -C_2 \))**：导致**有害遗忘**，即模型在旧任务上的表现严重下降。这是因为学习任务2信号的另一组神经元在学习过程中，其对任务1信号的拮抗作用超过了原有神经元群组。
        *   **回放机制**：理论证明，回放方法通过增加旧任务数据的训练，能够**扩大良性遗忘对应的角度范围**（将下界从\( -C_1 \)扩展到\( -\frac{C_2+1}{2} \)），从而有效缓解遗忘。
*   **“中角采样”策略**：基于理论发现，论文提出了一种**中角采样**策略，即从旧任务中选择与原型（信号向量）具有**中等余弦相似度**的样本存入回放缓冲区。其理论依据是，相似度过高或过低的样本分别对应过低或过高的遗忘程度，而选择中等遗忘度的样本是更具效益的平衡策略。

### 实验设计
为了验证理论并展示所提策略的有效性，论文设计了合成数据实验和真实世界数据实验。
*   **合成数据实验**：
    *   **数据集/场景**：严格按照论文定义1.1生成信号-噪声数据，通过旋转信号向量来控制两任务间的角度 \( \theta_{1,2} \)。
    *   **Benchmark与对比**：主要通过变化 \( \theta_{1,2} \) (从\( 0^\circ \)到\( 175^\circ \))，比较标准持续学习与带随机回放的持续学习在任务1上的遗忘程度（测试错误率）。
*   **真实世界数据实验**：
    *   **数据集/场景**：使用 **MNIST** 和 **CIFAR-100** 数据集。
    *   **MNIST实验**：构建了四个不同角度（\( 30.19^\circ \), \( 102.97^\circ \), \( 140.26^\circ \), \( 153.90^\circ \)）的二分类任务对，比较了不同回放缓冲区大小下的旧任务准确率。
    *   **CIFAR-100实验**：在iCaRL框架下，将CIFAR-100分割为10个或5个任务。核心是**对比多种回放缓冲区的采样策略**：随机采样、Small-angle采样、Mid-angle（中角）采样、Big-angle采样以及Herding算法。评估指标为“先前学习类别的测试准确率”和“平均遗忘指标”。

### 资源与算力
在所给文本中，**没有明确提到**进行实验所使用的具体硬件资源，如GPU型号、数量或总训练时长。

### 实验数量与充分性
从提供的文本看，实验设计系统且具有针对性，能够较好地支撑理论主张。
*   **实验组数**：
    1.  **合成数据**：一组全面的角度扫描实验，覆盖了从锐角到大钝角的完整范围。
    2.  **MNIST**：共4组不同角度的任务对实验，并在每组下评估不同回放大小的影响。
    3.  **CIFAR-100**：2种任务划分（CIFAR100-10, CIFAR100-5），并对比5种不同的采样策略。
*   **充分性与客观性**：
    *   **充分性**：实验从理论验证（合成数据、MNIST角度实验）到方法应用（CIFAR-100采样策略实验）层层递进，论证链条完整。
    *   **客观/公平性**：在CIFAR-100对比实验中，将提出的“中角采样”与随机采样、Herding（一种经典方法）、以及同为角度启发的Small/Big-angle采样进行了直接比较，对比维度公平。结果通过均值和标准差（ ±）的形式报告，增加了结果的可信度。

### 论文的主要结论与发现
1.  **角度是遗忘的决定性因素**：在两层CNN的持续学习中，任务信号向量间的夹角是划分良性遗忘与有害遗忘的关键。锐角和小钝角对应良性遗忘，大钝角导致灾难性遗忘。
2.  **回放机制的理论解释**：回放方法通过扩大良性遗忘的允许角度范围来缓解遗忘。
3.  **中角采样策略有效性**：理论和实验均表明，选择与原型具有中等相似度的旧样本来进行回放（中角采样），比随机采样或选择极端相似度样本（小角/大角采样）更能有效地降低遗忘，性能也优于经典的Herding方法。

### 优点
*   **理论创新性强**：首次在特征学习框架下，为持续学习中的遗忘现象提供了一个严谨、统一的理论解释，超越了线性模型的局限。
*   **理论指导实践**：理论分析直接催生了“中角采样”这一新颖且有实效的回放策略，是理论指导算法设计的典范。
*   **分析深刻具体**：通过神经元分类（第一、二、三类神经元）和行为拮抗分析，细致刻画了任务切换时网络内部的变化，为理解遗忘提供了微观视角。
*   **实验验证完备**：从合成数据到多个真实世界数据集，从理论现象验证到新策略的Benchmark对比，实验体系完整，说服力强。

### 不足与局限
*   **问题设定相对简化**：理论框架目前局限于两个任务、二分类、且任务共享同一个输出头的设定，这是学术理论研究的常见简化，但距离现实世界中复杂的、多任务、多分类的类增量或任务增量学习场景仍有差距。
*   **模型结构特定**：理论分析严格依赖于两层多项式ReLU CNN和特定的信号-噪声数据模型，结论推广到更深的网络（如ResNet）、其他激活函数或更复杂的注意力机制时，其有效性有待验证。
*   **方法贡献度相对有限**：论文本身也指出，“中角采样”策略带来的性能提升相对有限（在CIFAR-100上提升约1-2个百分点）。
*   **计算资源信息缺失**：论文未报告实验所消耗的计算资源，这使得其他研究者难以评估其方法的计算效率和实际落地成本。

（完）
