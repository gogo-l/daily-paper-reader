---
title: Batch Effect Correction for Neuroimaging Data with Heterogeneous Spatial Correlations
title_zh: 具有异质空间相关性的神经影像数据批次效应校正
authors: "Xie, R., Srinivasan, D., Harman, G. A., Davatzikos, C., Shinohara, R. T., Shou, H."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729396v1.full.pdf"
tags: ["query:med-lifelong"]
score: 8.0
evidence: 解决神经影像MRI数据中的批次效应，直接提升医学图像分析的可靠性。
tldr: 多中心神经影像研究因采集批次不同引入非生物变异，现有校正方法常忽视脑区间的空间相关性，可能导致偏差。本文提出协方差感知多元ComBat (CAM-ComBat)，直接建模高维特征之间的空间相关性，并允许批次间异质；为进一步提升大规模数据的可扩展性，设计了空间信息迭代分块ComBat (SIB-ComBat)。模拟和真实数据均显示，CAM-ComBat和SIB-ComBat在批次校正和保留生物信号方面显著优于传统方法。该工作为多中心脑影像分析的批次效应校正提供了更准确且高效的解决方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有批次校正方法未充分利用脑影像中丰富的空间相关结构，限制了校正精度。
method: 提出CAM-ComBat，整合高维特征的空间协方差，并衍生计算高效的SIB-ComBat。
result: 模拟和真实数据表明，所提方法在批次校正和生物信号保留上均优于现有技术。
conclusion: CAM-ComBat系列方法能更准确地处理脑影像的空间异质性，提升多中心研究可靠性。
---

## 摘要
磁共振成像扫描是揭示大脑结构和理解复杂神经发育与衰老过程病理的有效工具。不同脑区之间的空间相关性揭示了大脑功能机制及其与认知能力关联的关键信息和见解。从多个站点获取或聚合成像扫描的大规模神经影像学研究日益流行。这样做可以增强研究样本的多样性和研究结果的稳健性，并提高针对感兴趣的生物学假设进行的任何分析的统计效力。然而，在不同站点收集图像会引入非生物学变异，这归因于成像协议和配置的差异，称为批次效应。尽管存在执行批次效应校正的方法，但直接考虑大脑图像中空间模式的方法有限。我们开发了协方差感知多变量（CAM）ComBat，该方法考虑了高维特征间的这种空间相关性，且相关性在不同批次中可能是异质的。我们还提出了CAM-ComBat的一种计算高效替代方案，即空间信息迭代块（SIB）ComBat，它可扩展至非常高维度的特征。通过模拟研究和对真实神经影像数据的应用，我们表明这些方法优于现有的批次效应校正方法。

## Abstract
Magnetic resonance imaging scans are effective tools for unveiling brain structures and understanding pathology for complex neurodevelopmental and aging processes. The spatial correlations among various brain regions reveal critical information and insights into the mechanisms of brain functions and their associations with cognitive abilities. Large-scale neuroimaging studies that acquire or aggregate imaging scans from multiple sites have become increasingly popular. Doing so enhances the diversity of study samples and robustness of study findings, and increases the statistical power of any analysis conducted for the biological hypotheses of interest. However, collecting images across different sites introduces non-biological variability attributed to differences in imaging protocol and configurations, known as batch effects. While there are methods to perform this batch effect correction, there are limited methods that directly account for the spatial patterns found in images of the brain. We develop Covariance-Aware Multivariate (CAM) ComBat that accounts for such spatial correlation across high-dimensional features, which could be heterogeneous across batches. We also propose a computationally efficient alternative of CAM-ComBat, Spatially-Informed Iterative Block (SIB) ComBat, that is scalable for very high dimension of features. We show that these methods outperform existing batch effect correction methods through simulation studies and an application to real neuroimaging data.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：在大规模、多中心的神经影像学研究中，由于不同成像站点在扫描仪、成像协议与参数配置上的差异，会引入非生物学的系统性偏差，即**批次效应**。这些效应会掩盖真实的生物学信号，降低研究结果的可靠性与可重复性。
*   **现有方法的局限**：现有的数据协调方法大多基于ComBat模型，它们通常假设各脑区特征是相互独立的，忽略了大脑影像中固有的、对理解脑功能至关重要的**空间相关性结构**。部分改进方法虽尝试捕捉这种相关性，但假设所有批次的协方差结构源自同一个主成分空间，在处理高度异质的空间相关性时效果不佳，且计算上难以扩展到高维特征。
*   **整体含义**：本研究旨在开发新一代的批次效应校正方法，能够更精确地建模并去除多中心神经影像数据中**异质的空间相关性批次效应**，同时保留与生物学变量（如年龄、性别）的真实关联，从而提高大规模脑影像分析的准确性。

### 2. 论文提出的方法论

论文提出了两种递进式的方法：**协方差感知多变量ComBat (CAM-ComBat)** 及其计算高效的替代方案 **空间信息迭代分块ComBat (SIB-ComBat)**。

*   **CAM-ComBat**
    *   **核心思想**：直接建模高维特征间的协方差结构，并**允许不同批次具有高度异质的协方差矩阵**。其核心假设是，每个批次的协方差矩阵（Σ_i）可以通过一个批次特定的旋转矩阵（A_i）和一个共享的基础协方差矩阵（Σ）来表示，即 Σ_i = A_i Σ A_i^T。
    *   **关键步骤**：
        1.  **数据标准化**：首先使用标准ComBat模型的步骤，移除生物学协变量效应，并对残差进行缩放，得到标准化数据 Z_ij。
        2.  **均值效应调整**：假设标准化数据服从多元正态分布，并为批次特定的均值效应向量γ_i引入一个多元正态先验。通过计算其后验均值γ*_i来估计并移除批次的**加性效应**。
        3.  **协方差效应调整**：分别计算每个批次的样本协方差矩阵（Σ_i）和总体的样本协方差矩阵（Σ）。通过对两者的特征分解，计算出能够将总体协方差“旋转”到各批次协方差的矩阵A_i的估计值 Â_i。
        4.  **最终协调**：将移除均值效应的残差乘以旋转矩阵的逆（Â_i^{-1}），从而将数据标准化到一个共同的协方差空间，最后加回移除的生物学效应，得到协调后的数据 M_ij。

*   **SIB-ComBat**
    *   **核心思想**：为解决CAM-ComBat在处理数十万级别的高维体素特征时的计算瓶颈，提出了**“分而治之”的迭代策略**。将全脑特征划分为多个空间簇，在簇内独立应用CAM-ComBat，并通过多轮迭代和不同的分区方案，近似实现全局的协方差校正。
    *   **算法流程（见原文算法1）**：
        1.  用标准ComBat初始化协调数据。
        2.  将特征分为k1个簇（如基于某个脑图谱），对每个簇内的特征**并行**执行CAM-ComBat，然后组合结果。
        3.  将特征重新分配至k2个不同的簇（如使用另一个脑图谱），再次对每个新簇执行CAM-ComBat。
        4.  重复上述“重新分区-簇内协调”步骤`m`次，以充分考虑到更多不同特征间的相关性。最后将生物学协变量效应加回。

### 3. 实验设计

论文通过模拟数据和真实数据应用验证了所提方法的有效性，并与其他主流方法进行了对比。

*   **模拟实验**
    *   **数据生成**：根据设定模型生成了具有100个特征、来自2个批次的样本。设计的关键变量包括：**总样本量**（N=100和N=200）和**批次间协方差矩阵的差异程度**（通过Frobenius距离衡量，分为小、中、大三个等级）。数据中还包含一个随机的二值生物学协变量。
    *   **对比基准与方法**：将**CAM-ComBat**和**SIB-ComBat**（固定为2次迭代）与**未协调数据 (Unharm)**、**标准ComBat**以及可进行协方差校正的**CovBat**进行了比较。
    *   **评估指标**：通过训练随机森林模型来检测批次标签，并计算其在验证集上的**AUC**来评估批次效应的去除效果（AUC越低越好）。同时，通过检测二值协变量的AUC来评估方法对**生物学信号的保留能力**（AUC不变或提高为优）。

*   **真实数据应用**
    *   **数据集**：使用了来自iSTAGING联盟的两个不同研究站点的结构磁共振数据：哈佛老化脑研究（HABS）和开放获取成像研究系列数据集（OASIS），合计500名被试（每站点250人）。
    *   **特征**：处理后的RAVENS灰质密度图，特征维度高达**641,838个体素**。
    *   **对比方法**：在此超高维场景下，CAM-ComBat已不可行，因此将**SIB-ComBat**（使用MuSIC 512和256脑图谱进行两次迭代）与**标准ComBat**和**CovBat**进行了对比。
    *   **评估指标**：
        1.  类似模拟实验，使用AUC评估**站点检测**（去除批次效应）和**性别分类**（保留生物信号）的性能。
        2.  执行基于体素的形态学分析（VBM），分析与年龄关联的t统计量，并比较协调前后脑图的一致性。
        3.  **一致性图**：计算HABS和OASIS两个站点内部关于年龄的t统计量之间的一致性。

### 4. 资源与算力

*   **算力描述**：论文明确提到，SIB-ComBat在处理真实数据（约64万特征）时计算成本很高。具体而言，在使用**8个CPU核心**并行计算的实现下，整个协调过程耗时**超过36小时**，内存占用**超过120 GB**。
*   **瓶颈分析**：这表明即使采用了分块策略，高维协方差矩阵的估计和特征分解仍然非常消耗计算资源和时间。

### 5. 实验数量与充分性

*   **实验数量**：实验设计相对全面。模拟实验部分涵盖了**2种样本量 × 3种协方差差异程度**共6种场景，并对每种场景进行了**100次模拟重复**，每次重复内又用**10次随机划分**的训练/验证集来评估AUC，确保了结果的统计稳健性。真实数据应用部分提供了一个高维度的现实世界案例。
*   **实验充分性与公平性**：
    *   **充分性**：模拟实验系统性地探查了影响方法性能的关键因素（样本量、效应异质性），结果清晰。真实数据应用验证了方法在极端高维场景下的实用价值和优越性。
    *   **公平性**：所有方法都在相同的模拟或真实数据上，采用完全一致的评估流程（相同的训练/测试集划分、相同的随机森林模型和AUC指标）进行比较，确保了对比的公平性。

### 6. 论文的主要结论与发现

*   **CAM-ComBat的性能**：在模拟实验中，当批次间协方差差异较大时，CAM-ComBat始终能有效去除批次效应（AUC降至0.7以下），显著优于ComBat和CovBat，并且这种优势在样本量较大时更为明显。
*   **SIB-ComBat的性能**：SIB-ComBat在模拟实验中表现出与CAM-ComBat不相上下的批次效应去除能力，同时还能**放大与生物学协变量的关联信号**（检测协变量的AUC更高）。
*   **真实数据优势**：在64万维真实数据的应用中，SIB-ComBat是唯一能将站点检测AUC降至0.7以下的方法，并且很好地保留了与性别的关联。VBM分析显示，SIB-ComBat协调后的年龄效应脑图与原始数据相似，且两站点间关于年龄的t统计量一致性最高，优于ComBat和CovBat。
*   **总体结论**：所提出的CAM-ComBat和SIB-ComBat框架，是能够处理异质空间相关性的有效批次效应校正工具，尤其适用于大规模、多中心的神经影像研究。

### 7. 优点

*   **方法学创新**：
    *   **更灵活的协方差建模**：CAM-ComBat允许批次间协方差结构高度异质，突破了CovBat等方法假设共享主成分空间的限制，更加符合真实脑影像的复杂情况。
    *   **实用的问题解决方案**：SIB-ComBat通过“迭代分块”思想，巧妙解决了全局协方差建模的计算难题，使得先进的方法能够应用于数十万特征的超高维体素数据，具有很强的实践价值。
*   **验证框架高效**：使用随机森林AUC作为评估标准，直接量化了数据中残余的批次信息和生物信号，比仅看协调后脑图更客观、可量化。
*   **生物学信号保留与放大**：特别是在SIB-ComBat上观察到的信号放大效应，表明该方法不仅去除噪声，还可能增强了数据的信噪比，这是一个非常理想的性质。

### 8. 不足与局限

*   **计算成本依然高昂**：SIB-ComBat虽然比CAM-ComBat高效，但在处理高维数据时仍需要极大的计算资源（>36小时，>120GB内存），这限制了其在普通计算环境下的普及应用。
*   **对空间分区的依赖**：SIB-ComBat的性能可能对特征分簇的策略（如脑图谱的选择）和迭代次数敏感。当缺乏像MuSIC这样的优质空间先验信息时，如何确定最优分区和迭代次数仍是一个待解问题。
*   **结果的不一致性**：VBM分析显示，协调后部分体素的统计显著性会改变。虽然大部分关联得以保持，但这种改变是否总是正向的，以及如何解释其潜在的假阳性/假阴性风险，尚未深入探讨。
*   **真实数据应用场景单一**：真实数据仅测试了两个站点且均为横断面数据。该方法在更多站点（>2）、纵向研究数据以及其他类型的神经影像数据（如功能磁共振fMRI、弥散张量成像DTI）上的泛化能力有待进一步验证。
*   **对强分布差异的敏感性**：研究发现ComBat和CovBat在站点间强度分布差异较大时表现不佳。虽然CAM/SIB-ComBat有所改进，但在极端分布差异下，所有方法的局限性仍需更系统性的评估。

（完）
