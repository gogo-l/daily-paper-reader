---
title: Precision Functional Parcellation of the Human Cortex via Rest-Task fMRI Fusion
title_zh: 基于静息态与任务态fMRI融合的人脑皮层精准功能分区
authors: "Zhi, D., Du, J., Whitfield-Gabrieli, S., Diedrichsen, J., Ge, T."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731643v2.full.pdf"
tags: ["query:med-lifelong"]
score: 9.0
evidence: 提出一种利用静息-任务态 fMRI 融合进行人脑皮层精准功能分割的框架，属于医学图像分析。
tldr: 个体化皮层分割对揭示脑网络组织至关重要，但现有方法主要依赖静息态fMRI，未能有效利用任务态数据提供的互补功能信息，且面临跨异构数据集整合的挑战。本文提出mRBM-HBP框架，通过多项受限玻尔兹曼机建模空间依赖，实现静息态与任务态fMRI的高效灵活融合，推断组水平与个体水平分割。结果显示，该方法性能与现有最佳静息态方法相当且计算成本显著降低，融合后的图谱提高了分割的准确性、可靠性和个体特异性，尤其在个体数据有限时。该工作证明融合多模态fMRI能增强功能性脑组织的精准映射。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有个体化脑区分割依赖静息态fMRI，未充分利用任务态数据中互补的功能边界信息，且难以整合设计、样本量、覆盖度各异的任务态数据集。
method: 提出可扩展的分层贝叶斯框架mRBM-HBP，利用多项受限玻尔兹曼机建模空间依赖，灵活融合异质静息态与任务态fMRI数据，推断组级和个体级皮层分割。
result: mRBM-HBP分割性能媲美顶尖静息态方法，计算开销更低；融合静息-任务图谱提升了分割的准确性与个体特异性，任务数据细化了功能边界。
conclusion: 融合静息态与任务态fMRI可提升功能脑组织映射的精度，对基础研究和临床应用具有广泛意义。
---

## 摘要
个体特异性皮层分区能够刻画通常被群体水平图谱掩盖的大脑网络组织，对基础神经科学和转化应用具有广泛意义。然而，现有方法主要依赖静息态fMRI，未充分利用任务诱发数据，后者提供了关于功能特化的补充信息。这一局限性部分源于整合异质性数据集的挑战，这些数据集在任务设计、样本量和皮层覆盖范围上各不相同。在此，我们提出mRBM-HBP，一个可扩展的层级贝叶斯框架，它结合多项受限玻尔兹曼机来建模空间依赖关系，实现了跨多样化数据集高效灵活地整合静息态和任务态fMRI，并推断群体水平和个体水平皮层分区。我们展示了mRBM-HBP实现了与最先进的基于静息态的分区方法相当的性能，同时显著降低了计算成本。通过整合大规模任务态fMRI数据集，我们推导出一个基于任务的分区，并证明静息态和任务条件揭示出大体一致的宏观网络，而任务数据提供了功能边界的状态特异性细化。此外，融合静息-任务的群体水平图谱提升了推断分区的准确性、可靠性和个体特异性，尤其是当个体水平数据有限时。这些结果表明，整合静息态和任务态fMRI增强了对功能性大脑组织的精准映射。

## Abstract
Individual-specific cortical parcellations enable the characterization of brain network organization that is often obscured by population-level atlases, with broad implications for both basic neuroscience and translational applications. However, existing methods rely primarily on resting-state fMRI and underutilize task-evoked data, which provide complementary information about functional specialization. This limitation partly reflects the challenge of integrating heterogeneous datasets that differ in task design, sample size, and cortical coverage. Here, we present mRBM-HBP, a scalable hierarchical Bayesian framework that incorporates a multinomial restricted Boltzmann machine to model spatial dependencies, enabling efficient and flexible integration of resting-state and task fMRI across diverse datasets and inference of both group-level and individual-level cortical parcellations. We show that mRBM-HBP achieves performance comparable to state-of-the-art resting-state-based parcellation methods while substantially reducing computational cost. By integrating large-scale task-fMRI datasets, we derive a task-based parcellation and demonstrate that resting-state and task conditions reveal largely consistent macroscopic networks, while task data provide state-specific refinements of functional boundaries. Moreover, a fused rest-task group-level atlas improves the accuracy, reliability, and individual specificity of inferred parcellations, particularly when individual-level data are limited. These results indicate that integrating resting-state and task fMRI enhances precision mapping of functional brain organization.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

本研究聚焦于个体化人脑皮层功能分区这一前沿课题。传统群体水平图谱会掩盖个体间脑网络组织的差异，而现有精准功能映射方法主要依赖**静息态fMRI**，**未能充分利用任务态数据**中关于功能特化的互补信息。此外，不同任务态数据集在实验设计、样本量、皮层覆盖范围上高度异质，整合这些数据存在巨大挑战。因此，论文的核心问题是：**如何高效、灵活地融合静息态与异质任务态fMRI数据，以构建更精准、可靠的群体与个体化皮层功能分区。**

### 2. 方法论核心思路

论文提出 **mRBM‑HBP**——一个结合多项受限玻尔兹曼机（mRBM）的层级贝叶斯分区框架，主要包括两大组件：

- **空间排布模型（mRBM）**
  * 采用一个三层的生成模型：**输入层（观测数据）→ 分区层（隐变量网络标签）→ 隐藏层**。
  * 分区层与隐藏层之间通过**连接权重 \(\omega_{i,j}\)** 交互，并由温度参数 \(\theta_T\) 控制平滑程度；没有层内连接。
  * 该结构**隐式地捕捉皮层顶点间的空间依赖关系**，避免传统马尔可夫随机场（MRF）的逐顶点串行更新，从而实现**并行逐层更新**，大幅提升计算效率。
  
- **层级贝叶斯分区（HBP）框架**
  * 包含**组水平空间排布模型** \(p(\mathbf{U}; \theta_A)\)（先验）和**数据集专属发射模型** \(p(\mathbf{Y}_{s,n}|\mathbf{U}_s; \theta_{E_n})\)（似然）。
  * 通过**期望最大化（EM）算法**，联合学习组级别与个体级别的概率分区；在推断阶段，固定已学得的组水平图谱，仅用新个体的静息态数据估计其个体化分区。
  * 训练时可同时摄入多数据集、多模态（静息态联结组、任务激活图），并通过**内部加权平衡静息与任务贡献**。

该方法本质上以“mRBM作为空间先验”替代了 MS‑HBM 中的 MRF，并在贝叶斯框架中实现了多数据融合。

### 3. 实验设计与对比方法

- **主要数据集**：
  * **HCP-YA**（静息态 4×15 min，7个任务域 86 张 contrast maps）——用于基准测试和融合验证。
  * 三个任务态数据集用于构建任务分区：**MDTB**（24人，47任务条件）、**Nakai & Nishimoto**（6人，103条件）、**IBC**（12人，208条件）。
  * **HPN**（Harvard Precision Neuroimaging）数据集（15个被试，密集采样，7个任务域）——用于复现验证。

- **基准与方法对比**：
  * 主要与**MS‑HBM**（Kong 2019）对比组水平分区相似性（Dice）、个体水平分区在任务 inhomogeneity、DCBC、静息态同质性上的表现。
  * 对比静息态先验、任务先验、**融合静息‑任务先验**在个体推断中的效果。

- **评估指标**：
  * **任务 inhomogeneity**（越低越好）
  * **DCBC** 边界系数（越高越好，控制空间距离）
  * **静息态同质性**（越高越好）
  * **Dice 系数**（相似性与可靠性）
  * **个体识别准确率**（基于独立 run 的分区匹配）

- **关键实验场景**：
  * 用 HCP-YA 比较 mRBM‑HBP 与 MS‑HBM（相同训练集、测试集）。
  * 构建纯任务分区并与静息态分区进行 Dice 对比、网络分析。
  * 在 HCP‑YA 测试集上比较**静息态先验 vs. 融合先验**，并变化可用静息态 run 数（1 run vs. 2 runs）。
  * 在 HPN 数据集上，重复比较两种先验，并变化 run 数（1 → 24），考察任务 inhomogeneity、DCBC、静息态同质性。

### 4. 资源与算力

- 训练和推断使用了 **NVIDIA RTX 6000 Ada Generation GPU**，搭配 Python 3.10、CUDA 12.0、PyTorch 2.5.1。
- 在 GPU 加速下，**为 10 个个体生成分区仅需 1.54 秒**，而 MS‑HBM 单 CPU 需 273 秒（约 180 倍加速）；CPU 实现也只需 16.3 秒。
- 此外，部分计算在“配备了 GPU 资源的高性能计算环境”中进行，但未给出更多集群细节。

### 5. 实验数量与充分性

- **仿真实验**：使用 MRF 生成合成数据，验证 mRBM 捕捉空间依赖以及组先验的优势（见补充材料）。
- **基准对比**：一组完整的 HCP‑YA 基准，包括组水平与个体水平，与 MS‑HBM 全面对比（Dice、任务 inhomogeneity、DCBC、静息同质性、计算时间）。
- **任务分区构建与比较**：融合三个任务数据集，系统比较 17 个网络与静息态分区的重叠（每个网络都有 Dice 值），并按单模态/异模态网络分组分析。
- **融合先验评估**：
  * HCP‑YA：1 run 和 2 runs 下两种先验在三个指标上的配对比较，以及按任务域的详细分析，加上个体内可靠性和个体识别分析。
  * HPN：15 网络模型，在多个 run 数（1,5,10,15,all）下评估任务 inhomogeneity、DCBC、静息同质性；并进行单 run 的个体内/个体间相似性、语言和运动等任务激活边界放大分析。
- **消融/补充分析**：网络对应表格、不同平滑度的选择、多种指标的组合评估、任务选择的空间覆盖检查等。
- 总的来看，实验覆盖了**合成数据、主流公开数据集（HCP）和深层采样数据集（HPN）**，比较了最先进的基线方法，并对关键设计选择（K=15,17，先验类型，数据量）进行了系统探索，实验设计较为充分、客观、公平。

### 6. 主要结论与发现

1. **mRBM‑HBP 性能可比肩 MS‑HBM，但计算成本大幅降低**（GPU 上快约 180 倍）。
2. **静息态和任务态分区高度一致**（16/17 网络显著重叠），但**任务数据提供了功能边界的状态特异性细化**，尤其如边缘网络在任务状态下分解为多个系统。
3. **融合静息‑任务组图谱显著提高个体分区的准确性、可靠性和个体特定性**，尤其在**个体静息态数据有限**（如单个 run）时，提升更加明显。
4. 在 HPN 数据的复现中，融合先验同样提高了任务 inhomogeneity 和 DCBC，且在语言、躯体运动等特定任务中提供了更精细的功能定位。
5. 即使在融合先验下，个体的分区仍保持较高“指纹”特性，**个体识别准确率提升**（HCP：95.5% vs. 90.7%）。

### 7. 优点

- **方法学创新**：将 mRBM 引入贝叶斯分区框架，用隐藏层隐式建模空间依赖，打破 MRF 串行更新瓶颈，实现高效并行化。
- **灵活的数据融合**：HBP 框架天然支持跨数据集、跨模态（静息‑任务）的联合学习，并可容纳不同数据量、场强、任务。
- **实验严谨**：与主流方法进行公平对比，使用独立验证集调参，多数据集复现，多种指标互补评估，并进行了详细的个体特异性分析。
- **现实意义强**：针对个体数据稀少（如临床场景）给出明确优势，提供了一种可行的“群体任务信息反哺个体静息态分区”路径。
- **开源与可复现**：代码、预处理流程均公开在 GitHub，使用了公开数据集。

### 8. 不足与局限

- **任务选择的潜在偏差**：构建任务分区时虽已整合三个多域数据集，但未系统评估特定任务或数据集的移除对分区质量的影响；存在网络或区域覆盖冗余/不足的可能。
- **网络数目 K 的选择**：作者承认 K 的选取尚无客观标准，文中固定 15/17 网络，未提供数据驱动的 K 选择方案或稳定性分析。
- **评价指标的局限性**：任务 inhomogeneity 和 DCBC 各自侧重不同侧面，且可能受平滑、噪声等影响；平均 z 值可能偏向高激活区，忽略分布式功能脑区。
- **个体推断仅用静息态**：尽管构建了融合先验，个体推断仍未直接利用个体自己的任务数据，这可能限制了最优分区的达成。
- **训练数据的代表性**：组级别训练限于 HCP‑YA 的 40 人（静息）和多任务数据集较小样本（N=6~24），可能影响跨人群泛化能力。
- **大脑皮层覆盖**：文中主要关注皮层，未涉及皮层下结构或小脑，且边缘网络等低信噪比区域的处理依然存在挑战。
- **预印本**：论文尚未经过同行评审，方法和结论可能需要进一步验证。

（完）
