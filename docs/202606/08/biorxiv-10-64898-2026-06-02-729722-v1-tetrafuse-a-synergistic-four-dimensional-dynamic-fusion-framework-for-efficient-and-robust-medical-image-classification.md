---
title: "TetraFuse: A Synergistic Four-Dimensional Dynamic Fusion Framework for Efficient and Robust Medical Image Classification"
title_zh: "TetraFuse: 一种高效鲁棒医学图像分类的协同四维动态融合框架"
authors: "Gao, Y., Li, J., Xu, J., Li, Q., Li, Z., Shi, Y., ZHao, G., Wu, X., Zhang, Y."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729722v1.full.pdf"
tags: ["query:med-lifelong"]
score: 9.0
evidence: 用于高效鲁棒医学病理图像分类的框架
tldr: "医学病理图像分类需兼顾准确与效率，现有轻量模型分组卷积导致通道信息隔离。TetraFuse创新性地协同融合空间、通道、统计与频率四域特征，设计跨通道动态聚合和阶段感知局部增强，突破表达瓶颈。在保持极低计算开销下，TetraFuse-Tiny仅0.345G FLOPs在Kvasir上取得0.926准确率、0.994 AUC，比ResNet50减少91.53% FLOPs，为大规模医学图像分析提供高效稳健方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 解决轻量模型分组卷积造成的跨通道信息隔离，同时兼顾诊断准确性与计算效率，满足高通量临床筛查需求。
method: 提出TetraFuse框架，融合空间、通道、统计和频率四域特征，引入跨通道动态聚合CCDA重构全局通道拓扑，并设计阶段感知局部增强：浅层LVGE降噪、深层HFBI强化边缘。
result: "在多个数据集上超越SOTA，Tiny版本减少91.53% FLOPs，Kvasir准确率0.926/AUC 0.994仅需0.345G FLOPs。"
conclusion: TetraFuse以极低计算代价实现高表达力，为资源受限临床环境的大规模医学图像分析提供了可扩展方案。
---

## 摘要
医学病理图像的准确鲁棒分类对计算机辅助诊断至关重要。然而，深度学习模型在高通量临床筛查中的部署面临一个根本性挑战：诊断准确性与计算效率之间的权衡。当前轻量级架构虽通过分组卷积降低参数复杂度，但常导致跨通道信息隔离和表征能力下降。本文提出TetraFuse，一个新颖的框架，系统性地融合来自空间、通道、统计和频率四个互补领域的特征。TetraFuse引入了一种新颖的跨通道动态聚合（CCDA）范式，以可忽略的计算开销重建全局通道拓扑，解决了分组间的隔离问题。为平衡感知保真度和效率，我们设计了一种阶段感知的局部增强机制：浅层阶段使用局部方差引导增强器（LVGE）滤除背景噪声，而高频边界注入（HFBI）则强化深层病理轮廓，防止空间过度平滑。在COVID-19、ISIC 2018和Kvasir数据集上的实验结果表明，TetraFuse优于最先进（SOTA）方法。值得注意的是，TetraFuse-Tiny与ResNet50相比，FLOPs降低了91.53%；在Kvasir数据集上，仅用0.345G FLOPs即达到了0.926的准确率和0.994的AUC。通过结合高表征能力和极低计算需求，TetraFuse为大规模医学图像分析提供了一种可扩展的解决方案，尤其适用于资源受限的临床环境。

## Abstract
Accurate and robust classification of medical pathology images is pivotal for computer-aided diagnosis. However, the deployment of deep learning models in high-throughput clinical screening faces a fundamental challenge: the trade-off between diagnostic accuracy and computational efficiency. Current lightweight architectures, while reducing parameter complexity through grouped convolutions, often lead to cross-channel information isolation and diminished representational capacity. In this paper, we propose TetraFuse, a novel framework that systematically integrates features from four complementary domains: space, channel, statistics, and frequency. TetraFuse introduces a novel Cross-Channel Dynamic Aggregation (CCDA) paradigm that reconstructs global channel topology with negligible computational overhead, resolving the inter-group isolation issue. To balance perceptual fidelity and efficiency, we design a stage-aware local enhancement mechanism: Local Variance-Guided Enhancer (LVGE) is employed to filter out shallow-stage background noise, while High-Frequency Boundary Injection (HFBI) reinforces deep-stage pathological contours, preventing spatial over-smoothing. Experimental results on the COVID-19, ISIC 2018, and Kvasir datasets confirm that TetraFuse outperforms state-of-the-art (SOTA) methods. Notably, TetraFuse-Tiny achieves a transformative 91.53% reduction in FLOPs compared to ResNet50; on the Kvasir dataset, it achieved an accuracy of 0.926 and an AUC of 0.994 with only 0.345G FLOPs. By combining high representational power with minimal computational demand, TetraFuse offers a scalable solution for large-scale medical image analysis, especially in resource-constrained clinical environments.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）  
- **核心问题**：医学病理图像分类需要在诊断准确性与计算效率之间取得平衡，但现有轻量级模型大量采用分组卷积，导致**跨通道信息隔离**，表征能力下降，难以满足高通量临床筛查的需求。  
- **整体含义**：提出 **TetraFuse** 框架，通过系统性地融合空间、通道、统计和频率四域特征，以极低计算代价打破通道隔离、增强病理表征，为资源受限环境下的高效、鲁棒分类提供可扩展的解决方案。

### 2. 论文提出的方法论  
- **整体思想**：协同融合**空间、通道、统计、频率**四个互补域的特征，在轻量级架构下恢复全局信息交互，同时根据网络深度进行阶段感知的局部增强，兼顾感知保真度和计算效率。  
- **关键技术细节**：  
  - **跨通道动态聚合（CCDA）**：以可忽略的计算开销重建全局通道拓扑，解决分组卷积导致的分组间信息隔离。  
  - **阶段感知局部增强**：  
    - **浅层——局部方差引导增强器（LVGE）**：过滤背景噪声，增强前景特征的方差响应。  
    - **深层——高频边界注入（HFBI）**：强化病理轮廓的高频信息，防止空间过度平滑。  
- **整体流程**：TetraFuse 以轻量级骨干为基础，插入 CCDA 模块实现跨组通道交互，并在不同阶段嵌入 LVGE 和 HFBI，最后进行分类。

### 3. 实验设计  
- **数据集/场景**：  
  - COVID‑19 胸部影像  
  - ISIC 2018 皮肤镜图像  
  - Kvasir 胃肠道内窥镜图像  
- **Benchmark 与对比方法**：与当前最先进的（SOTA）方法进行比较（论文摘要中未列出具体对比模型名称，但提及优于 SOTA）。特别对照 **ResNet50**，展示 TetraFuse-Tiny 在 FLOPs 上的巨大缩减。

### 4. 资源与算力  
- **文中信息**：未明确提及 GPU 型号、数量及训练时长。在提供的摘要和元数据中无法获取硬件配置与算力细节。

### 5. 实验数量与充分性  
- **实验组数**：至少涵盖三个不同模态的医学图像数据集（COVID‑19、ISIC 2018、Kvasir），并与多个 SOTA 方法进行对比，同时提供了 Tiny 版本的效率对比。从摘要推断，可能包含消融实验以验证各模块贡献，但具体组数未详述。  
- **充分性评估**：使用多领域数据集验证泛化性，并设置效率与精度的双维度基准，较为全面。但缺少对统计、频率分支独立贡献的详细消融呈现（仅在摘要中提及协同作用），若正文未展开则说服力稍弱。整体实验设计具有较强的客观性和公平性。

### 6. 论文的主要结论与发现  
- TetraFuse 在多数据集上均优于现有 SOTA 方法。  
- **TetraFuse-Tiny 与 ResNet50 相比，FLOPs 降低 91.53%**；在 Kvasir 数据集上仅用 0.345G FLOPs 达到 0.926 准确率、0.994 AUC，证明了极高的效率‑精度综合优势。  
- 四域协同融合结合阶段感知增强，能够有效克服分组卷积的信息隔离问题，同时抑制噪声、强化边界。

### 7. 优点：方法或实验设计上的亮点  
- **创新性强**：首次将空间、通道、统计、频率四域特征在轻量级医学分类中进行系统融合，视角新颖。  
- **轻量高效**：CCDA 以极低开销重建全局通道关系，避免增加沉重计算负担，实现极高 FLOPs 压缩比。  
- **阶段感知设计**：根据浅、深层不同特性定制增强策略，既降噪又锐化边界，设计细腻。  
- **实验多样性强**：覆盖放射、皮肤镜、内窥镜三种模态，验证了方法的鲁棒性与可迁移性。  
- **对比突出**：与经典 ResNet50 的直接效率对比极具冲击力，量化展示实际部署价值。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等  
- **算力信息缺失**：摘要及元数据未报告训练硬件、时间等资源开销，影响对实际部署“效率”的完整评估。  
- **消融实验详尽度待考**：虽提到四域融合，但未展示各域单独贡献的定量消融，无法判断是否所有域均不可或缺。  
- **数据集规模与外部验证**: COVID‑19、ISIC 2018、Kvasir 均为中等规模公开集，缺少大规模多中心外部验证，临床泛化性仍需进一步检验。  
- **实时性指标未提**：仅有 FLOPs，未给推理延迟或吞吐量，资源受限场景下实时性判断不完整。  
- **对比方法列表不明**：摘要称“优于 SOTA”，但未列出具体对比模型名称和版本，无法确认基准强度。  

（完）
