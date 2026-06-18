---
title: Dissecting and directing pathology foundation models
title_zh: 解析和引导病理学基础模型
authors: "Kim, C., Kaczmarzyk, J., Savant, D., Zhao, Z., Koo, P., Lee, S.-I."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731496v1.full.pdf"
tags: ["query:med-lifelong"]
score: 9.0
evidence: 解释并控制用于医学图像分析的病理基础模型
tldr: 病理基础模型嵌入不透明，阻碍临床信任与科学发现。PICASSO框架通过稀疏自编码器将嵌入分解为人类可解释的视觉概念，基于超1.2亿组织块训练出首个全癌种组织形态学概念图谱。该框架能审计模型行为、发现新生物标志物（如EGFR突变相关的网格状上皮形态），并支持概念操控，如抑制伪影、生成反事实嵌入。PICASSO将病理FM转化为可解释、可控的发现平台，推动机制研究。
source: biorxiv
selection_source: fresh_fetch
motivation: 病理基础模型的嵌入黑箱问题限制了其临床可信度与科学探索价值。
method: 采用稀疏自编码器将FM嵌入分解为可解释概念，并利用120M+多癌种组织块训练。
result: 构建了全癌种形态概念图谱，揭示了预测驱动特征，鉴定出网格状上皮为EGFR突变新标志物，并实现概念级干预。
conclusion: PICASSO为病理FM提供了可解释与可控框架，赋能从审计到生物发现的多元应用。
---

## 摘要
基础模型是数字病理学的核心，能将组织学图像编码为稠密嵌入，从而辅助诊断分类、分子改变预测和临床结局建模。然而，这些嵌入的不透明性使得基于基础模型的系统成为“黑箱”，限制了它们在临床转化中的可信度以及在科学发现中的效用。在此，我们提出了PICASSO（基于稀疏字典学习构建的病理图像概念图谱），一个使病理学基础模型变得可解释和可控的框架。PICASSO利用稀疏自编码器将基础模型嵌入分解为人类可解释的视觉概念。该框架在32种癌症类型的超过1.2亿个组织块上进行训练，生成了首个泛癌组织形态学概念图谱。我们证明，PICASSO通过暴露学习表示中的可解释结构并支持概念层面的干预，使得基础模型嵌入的多种下游应用成为可能。它能够通过揭示驱动预测的形态学特征来审计临床模型行为。除了透明度和验证，PICASSO还促进了新生物学见解的发现；例如，它识别出鞋钉样上皮形态作为肺腺癌中EGFR突变的一个此前未被认识的生物标志物。通过将PICASSO衍生的概念与空间转录组学联系起来，我们揭示了形态学模式与基因表达程序之间的关联。此外，PICASSO允许抑制与技术伪影相关的概念，从而减少模型对虚假信号的依赖。最后，PICASSO能够受控地操纵学习到的概念，生成反事实嵌入，用于探索性治疗分析，例如调节肿瘤浸润淋巴细胞密度以评估其对预测生存结局的影响。总体而言，PICASSO提供了一个原则性框架，将病理学基础模型转化为机制洞察和发现的平台。

## Abstract
Foundation models (FMs) are central to digital pathology, encoding histology images into dense embeddings for facilitating diagnostic classification, molecular alteration prediction, and clinical outcome modeling. However, the opacity of these embeddings renders FM-based systems "black boxes," limiting their trustworthiness for clinical translation and utility for scientific discovery. Here, we introduce PICASSO (Pathology Image Concept Atlas built via SparSe dictiOnary learning), a framework that makes pathology FMs interpretable and controllable. PICASSO decomposes FM embeddings into human-interpretable visual concepts using a sparse autoencoder. It is trained on more than 120 million tissue patches across 32 cancer types, producing the first pan-cancer atlas of histomorphological concepts. We demonstrate that PICASSO enables diverse downstream applications of FM embeddings by exposing interpretable structure within learned representations and supporting concept-level intervention. It enables auditing of clinical model behavior by revealing the morphological features driving predictions. Beyond transparency and validation, PICASSO enables the discovery of new biological insights; for example, it identified hobnailing epithelial morphology as a previously unrecognized biomarker of EGFR mutations in lung adenocarcinoma. By linking PICASSO-derived concepts with spatial transcriptomics, we uncover associations between morphological patterns and gene expression programs. Furthermore, PICASSO allows suppression of concepts associated with technical artifacts, thereby reducing model reliance on spurious signals. Finally, PICASSO enables controlled manipulation of learned concepts to generate counterfactual embeddings for exploratory therapeutic analysis, such as modulating tumour-infiltrating lymphocyte density to assess impacts on predict survival outcomes. Together, PICASSO provides a principled framework for transforming pathology FMs into platforms for mechanistic insight and discovery.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：病理学基础模型（Foundation Models, FMs）能将组织学图像压缩为稠密嵌入，支撑诊断、突变预测等任务，但这些嵌入本身高度不透明，构成“黑箱”，严重削弱了其在临床转化中的可信度和科学发现上的解释力。
- **整体含义**：PICASSO 框架旨在为病理 FM 嵌入赋予可解释性与可控性，将其从一个数值表征空间转化为可审计、可干预、可发现生物学新知的透明平台，从而弥合模型性能与人类理解之间的鸿沟。

## 2. 论文提出的方法论

- **核心思想**：利用**稀疏自编码器（Sparse Autoencoder）** 将 FM 产生的稠密嵌入分解为一组稀疏激活的、人类可解释的视觉概念，实现从“黑箱嵌入”到“概念字典”的映射。
- **关键技术细节与流程**：
  - **输入**：病理 FM 在全切片图像上提取的组织块（tissue patch）嵌入。
  - **分解结构**：通过一个带有稀疏性约束的自动编码器，将每个嵌入重构为一组概念激活值的线性组合，瓶颈层的每个维度对应一个可解释的概念。
  - **概念解释**：对于每个概念，选择在该概念上激活最强的组织块进行可视化，辅以人工标注或比对已知形态模式，赋予语义标签（如某种上皮形态、淋巴细胞浸润密度、技术伪影等）。
  - **训练规模**：在跨越 32 种癌症类型、总计超过 **1.2 亿个组织块**（120M+ patches）的超大数据集上训练该稀疏自编码器。
  - **产出物**：首个泛癌种组织形态学概念图谱（concept atlas），即一个结构化、可浏览的形态学概念空间。
- **算法流程简述**（文字描述）：给定 FM 嵌入向量 \( \mathbf{z} \)，稀疏自编码器输出重构嵌入 \( \hat{\mathbf{z}} = \mathbf{D}\mathbf{c} \)（\( \mathbf{D} \) 为概念字典，\( \mathbf{c} \) 为稀疏激活），同时约束 \( \mathbf{c} \) 的 \( L_1 \) 范数以实现稀疏性；训练完成后，每个字典基元即对应一个可解释概念。

## 3. 实验设计

- **数据集与场景**：
  - 多癌种组织病理图像，覆盖 **32 种癌症类型**，组织块数目超过 1.2 亿，规模上确保概念字典的丰富性与泛化性。
  - 下游验证场景包括：临床模型行为审计、新生物标志物发现、空间转录组学关联、伪影抑制、治疗相关的反事实分析。
- **Benchmark 与对比方法**：
  - 摘要及可用信息中**未明确提及与其他可解释性方法的定量对比或特定基准测试**，主要侧重于展示 PICASSO 的多种新颖应用以及对已有 FM 的增强能力，而非在标准可解释性排行榜上进行竞赛。
  - 对比的逻辑更多是“使用 FM 嵌入 vs. 经 PICASSO 分解后的可解释概念”在不同下游任务中的表现差异（例如能否审计出模型依赖的形态特征），从而达到自我验证。

## 4. 资源与算力

- **文中明确信息**：仅提到训练数据量（120M+ 组织块，32 癌种），未披露 GPU 型号、数量、训练时长等具体算力配比。
- **推断**：该规模处理必然需要大型 GPU 集群或长时训练，但确切资源细节在提供的材料中**未被说明**。

## 5. 实验数量与充分性

- **实验组类**（从摘要可归纳至少 6 类不同性质的应用性实验）：
  1. 构建全癌种概念图谱并验证其可解释性。
  2. 审计临床预测模型，揭示驱动预测的形态特征。
  3. 发现新的生物标志物（EGFR 突变相关的鞋钉样上皮）。
  4. 将概念与空间转录组数据关联，探索形态-基因表达联系。
  5. 抑制技术伪影相关概念，减少虚假相关性。
  6. 操控概念（如调节肿瘤浸润淋巴细胞密度）生成反事实嵌入进行生存分析。
- **充分性与客观性评价**：
  - 实验覆盖了从**表征解构、生物学发现、去偏置到因果干预**等多个层次，较为全面。
  - 每组实验对应的自身验证方法（如生物标志物的统计关联、伪影抑制后的性能变化等）在摘要中有体现，但具体指标和严格消融实验的细节（例如控制概念数量、稀疏度等参数的敏感性）未能从现有信息获知。
  - 缺乏与其他可解释性方法的横向比较，因此方法间的相对优劣尚不明确。

## 6. 论文的主要结论与发现

- **可解释性突破**：PICASSO 成功将病理 FM 嵌入分解为可解释的概念字典，使下游模型的行为可以通过概念激活进行审计。
- **新生物标志物**：识别出“鞋钉样上皮形态（hobnailing epithelial morphology）”与肺腺癌 EGFR 突变显著相关，此前未被描述为组织形态学标志物。
- **跨模态关联**：PICASSO 概念与空间转录组学程序相关联，为形态-分子机制建立桥梁。
- **可控伪影抑制**：通过关闭特定概念，能够有效降低模型对切片染色变异、模糊等伪影的依赖。
- **概念级干预**：可对外部已知形态概念（如肿瘤浸润淋巴细胞密度）进行受控操纵，生成反事实样本，用于因果效应探索（如生存预后影响）。

## 7. 优点：方法或实验设计上的亮点

- **大规模概念图谱**：首次在 1.2 亿组织块、32 癌种规模上训练概念字典，覆盖面与代表性突出。
- **稀疏性与可解释性兼顾**：通过稀疏自编码器自然获得离散、可分离的概念，避免了后验归因方法的模糊性。
- **“使用即可解释”**：无需改变 FM 本身，仅对嵌入进行后置分解，可适配多种现有病理 FM。
- **多用途验证**：不限于单一的模型解释，而是将可解释性延伸至科学发现、伪影去除和假设生成，展现了强大的平台潜力。
- **发现全新生物标志物**：鞋钉样上皮与 EGFR 突变的关联是原创性发现，提升了工作的生物学价值。

## 8. 不足与局限

- **缺乏与其他可解释性方法的直接比较**：未提供与基于热图、注意力归因等方法在定量审计、鲁棒性等维度的对比实验，PICASSO 的相对优势更多为定性展示。
- **概念的人工定义与覆盖面**：概念的解释仍需依赖人工审查激活样本，可能存在主观性，且概念字典可能未穷尽所有有意义的组织形态。
- **跨模型泛化性未验证**：训练均建立在某一（或某几个）特定病理 FM 之上，是否对其他架构、预训练策略的 FM 同样适用，尚不明确。
- **算力与实施门槛**：训练如此规模的稀疏自编码器本身需要可观的计算资源，未见提供轻量版或迁移学习方案。
- **临床验证的深度**：反事实分析、生物标志物发现的结论仍需独立临床队列的前瞻性验证，当前仍停留于回顾性/相关性层面。

（完）
