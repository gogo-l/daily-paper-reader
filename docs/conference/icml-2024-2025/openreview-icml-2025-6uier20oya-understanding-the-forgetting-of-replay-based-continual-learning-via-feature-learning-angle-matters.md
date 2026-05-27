---
title: "Understanding the Forgetting of (Replay-based) Continual Learning via Feature Learning: Angle Matters"
title_zh: 理解基于重放的持续学习中遗忘：角度至关重要
authors: "Hongyi Wan, Shiyuan Ren, Wei Huang, Miao Zhang, Xiang Deng, Yixin Bao, Liqiang Nie"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6UIer20oYA"
tags: ["query:continual"]
score: 10.0
evidence: 特征学习理论揭示任务信号角度如何影响基于重放的持续学习遗忘
tldr: 持续学习的理论理解仍有限，尤其对遗忘的影响因素。本文通过特征学习理论，分析两层卷积神经网络在顺序任务中的遗忘机制，发现任务信号向量间的角度是关键因素：锐角或小钝角导致良性遗忘，其他角度引发灾难性遗忘。理论结果加深了对重放式持续学习中遗忘本质的理解，为设计更优的持续学习算法提供了指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6uier20oya/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uier20oya/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1769, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uier20oya/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 763, \"height\": 538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6uier20oya/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1092, \"height\": 713, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6uier20oya/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 683, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6uier20oya/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 680, \"height\": 282, \"label\": \"Table\"}]"
motivation: 缺乏对持续学习中遗忘因素的理论理解，制约算法设计。
method: 利用特征学习理论，在两层CNN上分析任务信号向量角度对遗忘的影响。
result: 揭示任务信号角度关系决定了遗忘程度，锐角/小钝角导致良性遗忘。
conclusion: 角度是理解持续学习遗忘的关键，为设计抗遗忘算法提供理论依据。
---

## Abstract
Continual learning (CL) is crucial for advancing human-level intelligence, but its theoretical understanding, especially regarding factors influencing forgetting, is still relatively limited. This work aims to build a unified theoretical framework for understanding CL using feature learning theory. Different from most existing studies that analyze forgetting under linear regression model or lazy training, we focus on a more practical two-layer convolutional neural network (CNN) with polynomial ReLU activation for sequential tasks within a signal-noise data model. Specifically, we theoretically reveal how the angle between task signal vectors influences forgetting that: *acute or small obtuse angles lead to benign forgetting, whereas larger obtuse angles result in harmful forgetting*. Furthermore, we demonstrate that the replay method alleviates forgetting by expanding the range of angles corresponding to benign forgetting. Our theoretical results suggest that mid-angle sampling, which selects examples with moderate angles to the prototype, can enhance the replay method's ability to mitigate forgetting. Experiments on synthetic and real-world datasets confirm our theoretical results and highlight the effectiveness of our mid-angle sampling strategy.

---

## 论文详细总结（自动生成）

# 论文总结：理解基于重放的持续学习中遗忘——角度至关重要

## 1. 研究动机与核心问题
- **核心问题**：持续学习中的灾难性遗忘现象严重制约模型在序列任务上的表现，但关于遗忘因素的理论理解仍然有限，尤其缺少对实际神经网络（而非简化的线性模型或无限宽网络）的深入分析。
- **研究目标**：利用特征学习理论，建立一个统一的理论框架，揭示两层卷积神经网络（CNN）在持续学习过程中遗忘的关键影响因素，并为重放（replay）类方法如何缓解遗忘提供理论解释。
- **整体含义**：从几何角度（任务信号向量之间的夹角）出发，阐明遗忘程度取决于任务相似度的内在机制，为设计更有效的持续学习算法提供理论指导。

## 2. 方法论
### 2.1 核心思想
- 采用 **信号-噪声数据模型**：每个任务的数据包含一个固定的任务信号向量 \(\mu_k\) 和正交的高斯噪声向量 \(\xi\)。
- 分析 **两层多项式ReLU激活的CNN**（激活函数为 \(\sigma(z)=(\max\{0,z\})^q,\; q>2\)），使用梯度下降最小化交叉熵损失。
- 将网络权重分解为信号成分与噪声成分的线性组合，通过分析这些系数的动态变化来追踪学习与遗忘过程。

### 2.2 关键技术细节
- **信号-噪声分解**：
  \[
  w_{j,r}^{(T_k,t)} = w_{j,r}^{(T_k,0)} + j\cdot \gamma_{j,r}^{(\mu_k)(T_k,t)}\frac{\mu_k}{\|\mu_k\|_2^2} + \sum_{i} \rho_{j,r,i}^{(\xi_k)(T_k,t)}\frac{\xi_{k,i}}{\|\xi_{k,i}\|_2^2}
  \]
  其中 \(\gamma\) 代表对信号的学习强度，\(\rho\) 代表对噪声的记忆强度。
- **角度定义**：任务 \(T_1\) 与 \(T_2\) 的信号向量夹角余弦 \(\cos\theta_{1,2} = \langle \mu_1,\mu_2\rangle / (\|\mu_1\|\|\mu_2\|)\)。
- **理论结果**：
  - 当 \(-C_1 \le \cos\theta_{1,2} \le 1\) (锐角或小钝角) 时，遗忘为良性（旧任务测试误差很小）。
  - 当 \(-1 \le \cos\theta_{1,2} < -C_2\) (大钝角) 时，遗忘为有害（旧任务测试误差趋近于1）。
  - 使用重放方法可将良性遗忘的夹角范围扩展到 \(-\frac{C_2+1}{2} \le \cos\theta_{1,2} \le 1\)。
- **中角度采样策略**：基于理论结果，建议选择与类原型具有中等余弦相似度的样本存入重放缓冲区，以更经济有效地缓解遗忘。

### 2.3 公式与算法流程（文字说明）
1. **初始化**：第一任务随机初始化网络权重，第二任务继承第一任务收敛后的权重。
2. **训练**：对当前任务数据执行全批量梯度下降，更新信号系数 \(\gamma\) 和噪声系数 \(\rho\)。
3. **信号学习阶段**：
   - 第一类神经元（初始与 \(\mu_1\) 正相关）在第一任务中学习 \(\mu_1\)；在第二任务中，由于信号向量夹角导致的正交分量，这些神经元对 \(\mu_2\) 的学习减弱甚至消失。
   - 第二类神经元（初始与 \(\mu_1\) 负相关但与 \(\mu_1^\perp\) 正相关）在第二任务中负责学习 \(\mu_2\)。
4. **遗忘判定**：通过比较学习 \(\mu_1\) 的神经元与学习 \(\mu_2\) 的神经元在旧任务测试样本上的输出，若前者输出显著大于后者则良性遗忘，反之为有害遗忘。

## 3. 实验设计
### 3.1 合成数据实验
- **数据集**：根据信号-噪声模型生成，\(n_k=100\), \(d=100\), \(\|\mu_1\|=8\), 通过旋转 \(\mu_1\) 得到 \(\mu_2\) 以模拟不同夹角。
- **模型**：两层ReLU³ CNN，宽度 \(m=10\)。
- **对比场景**：标准持续学习与带重放的持续学习。
- **评估指标**：旧任务测试误差（遗忘程度）。

### 3.2 真实数据集实验（MNIST）
- **任务构造**：二分类任务，分别用不同数字对（如5vs.反转5, 8vs.反转8）构造夹角不同的任务序列（30.19°, 102.97°, 140.26°, 153.90°）。
- **对比方法**：不同重放缓冲区大小下的标准持续学习。
- **中角度采样验证**：在MNIST上用两层CNN比较随机采样、小角度采样、中角度采样、大角度采样的效果。

### 3.3 CIFAR-100实验（mid-angle sampling扩展）
- **框架**：基于iCaRL，使用CBAM-ResNet18作为特征提取器。
- **采样策略对比**：随机采样、小角度采样、中角度采样、大角度采样、herding。
- **数据划分**：CIFAR100-10 (10 tasks, 每task 10类) 和 CIFAR100-5 (20 tasks)。
- **评估指标**：旧类别平均准确率及平均遗忘率。

## 4. 资源与算力
- 论文**未明确说明**使用的GPU型号、数量或具体训练时长。
- 所有实验（合成数据、MNIST、CIFAR-100）规模相对较小，算力需求不高；训练在PyTorch上完成，但无详细硬件配置记录。

## 5. 实验数量与充分性
- **合成实验**：覆盖了从0°到近180°的多种夹角，持续学习与重放持续学习两个场景，并可视化神经元行为以支持理论。
- **MNIST实验**：4组不同夹角的真实任务序列，验证重放缓冲区大小对遗忘的影响。
- **CIFAR-100实验**：两种任务划分（10-task和20-task），5种采样策略对比，每种重复多次并汇报均值和标准差。
- **充分性评估**：实验覆盖了合成与真实数据，从理论验证到方法验证，消融了角度大小、重放规模、采样策略，实验设计较为全面，结果一致性强，客观性和公平性较好。但仅涉及二分类和简单的CNN结构，任务规模有限。

## 6. 主要结论与发现
1. **角度决定遗忘类型**：在两层CNN中，任务信号向量间的夹角是决定良性遗忘或有害遗忘的关键几何因素。
2. **重放机制的几何解释**：重放方法通过扩大良性遗忘的角度范围而缓解遗忘，其效能受缓冲区大小和样本选择策略影响。
3. **中角度采样有效性**：选择与类原型具有中等相似度的样本（而非最相似或最不相似的样本）存入缓冲区，能在相同存储成本下达到更好的抗遗忘效果，在CIFAR-100上超越传统随机采样和herding。
4. **理论预测与实验吻合**：合成与真实数据集实验均证实了理论分析，验证了角度-遗忘关系的普遍性。

## 7. 优点
- **理论创新**：首次利用特征学习理论严格分析两层CNN在持续学习中的遗忘现象，突破了以往线性模型或NTK无限宽假设的限制。
- **清晰的几何直觉**：将遗忘归因于任务空间夹角，提供了可解释的几何图景，易于理解和推广。
- **指导性强**：基于理论导出中角度采样策略，具有直接的实际应用价值。
- **实验验证全面**：从合成到真实数据，从理论验证到benchmark比较，验证链完整。

## 8. 不足与局限
- **模型和任务设定较简单**：仅研究两层CNN和两个二分类任务，未扩展到多任务、多分类或更深的架构。
- **中角度采样效果提升有限**：在CIFAR-100上，mid-angle sampling相比随机采样或herding准确率提升幅度不大（约1-2%），实际增益可能有限。
- **缺乏大规模验证**：未在更大规模数据集（如ImageNet）或更复杂的CL benchmark（如CORe50、DomainNet）上测试。
- **依赖精确夹角计算**：真实场景中任务信号向量需要从数据中估计，夹角准确度可能影响采样策略效果。
- **计算资源未报告**：无法评估该方法在大规模设定下的计算成本。

（完）
