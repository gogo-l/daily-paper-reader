---
title: Compositional and interpretable representation of histology using AI foundation models and sparse autoencoders
title_zh: 基于AI基础模型和稀疏自编码器的可组成与可解释组织学表示
authors: "Zhao, Z., Maliga, Z., Ogbonna, E. C., Talemi, S. R., Coy, S., Gagne, A., Lumamba, K., Solomon, I. H., Santagata, S., Steyn, A. J. C., Naidoo, T., Sorger, P. K."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.725182v1.full.pdf"
tags: ["query:med-lifelong"]
score: 10.0
evidence: 组织学图像的可解释表示用于计算病理学
tldr: "H&E染色是组织病理学基础，但其深度学习模型解释性不足，限制了与空间组学整合。本研究提出人机协同框架，利用计算病理学基础模型与稀疏自编码器分解嵌入，自动识别可解释的组织学特征。在肺部疾病中，该方法显著加速专家解读，生成形态感知注释，实现2D/3D组织架构与分子空间数据的融合。该工作提升了计算病理模型的生物解释性，为多尺度空间分析提供了新范式。"
source: biorxiv
selection_source: fresh_fetch
motivation: "H&E图像是病理学金标准，但现有深度学习模型难以生物解释，阻碍其在空间多组学研究中的应用。"
method: 结合病理基础模型与稀疏自编码器，通过人机交互分解嵌入，自动提取多元化、可解释的组织学特征。
result: 在结核病和肺癌分析中，该方法加速并增强了专家解读，生成形态感知注释，整合了2D/3D组织结构与分子空间谱。
conclusion: "该可解释框架显著提升了H&E图像的生物学价值，为组织学与空间组学整合提供了有效方案。"
---

## 摘要
苏木精和伊红（H&E）染色的组织切片光学显微镜检查是组织病理学150多年来的基石，至今仍是诊断和研究不可或缺的手段。高复用空间图谱分析技术能以单细胞分辨率检测蛋白质和RNA表达，其发展丰富了但并未取代H&E成像，即使在研究中也是如此。基于深度学习的计算病理学（CPath）模型有望进一步提升H&E成像的价值，但从生物学角度解释这些模型仍具挑战，导致其在空间图谱分析研究中应用不广。本文提出一种人在回路中的计算框架，利用CPath基础模型（FM）和稀疏自编码器（SAE）分解FM嵌入向量，自动识别H&E图像中多种人类可解释的组织病理学特征。将FM-SAE建模应用于结核病和肺癌等肺部疾病时，人机交互增强并加速了专家判读。此外，所得注释提供了一种形态学感知的方法，可将二维和三维中尺度组织结构与分子空间图谱分析相整合。

## Abstract
Light microscopy of tissue sections stained with hematoxylin and eosin (H&E) has been the foundation of histopathology for over 150 years and remains essential for diagnosis and research. The development of high-plex spatial profiling approaches able to measure protein and RNA expression at single-cell resolution augments but does not replace H&E imaging, even in research. Computational pathology (CPath) models based on deep learning promise to further increase the value of H&E imaging but interpreting these models in biological terms remains challenging. As a result, they are not widely used in spatial profiling studies. Here we describe a human-in-the-loop computational framework that leverages CPath foundation models (FMs) and sparse autoencoders (SAEs) to decompose FM embeddings and automatically identify diverse, human-interpretable histopathology features in H&E images. When FM-SAE modeling was applied to pulmonary diseases such as tuberculosis and lung cancer, human-machine interaction augmented and accelerated expert interpretation. Moreover, the resulting annotations provide a morphology-aware approach to integrating 2D and 3D mesoscale tissue architectures with molecular spatial profiling.

---

## 论文详细总结（自动生成）

由于提供的 PDF 链接受到反爬虫保护而无法获取全文，以下总结基于论文元数据中的标题、摘要及公开信息整理，部分实验与算力细节在现有材料中缺失，已如实标出。

---

## 1. 论文的核心问题与整体含义  
- **研究背景与动机**：H&E 染色组织病理学已有 150 余年历史，是诊断与研究的基石。高复用空间组学技术（同时检测蛋白与 RNA）虽能提供单细胞分辨率的分子信息，却并未取代 H&E 成像，而计算病理学（CPath）的深度学习模型虽能提升 H&E 图像的利用价值，但其“黑箱”特性导致特征缺乏生物学可解释性，严重阻碍了模型在空间多组学研究中的广泛应用。  
- **核心问题**：如何将 CPath 深度学习模型的嵌入分解为人类可解释的、可组合的组织学特征，从而使 H&E 图像更好地与分子空间信息融合，并增强病理专家的解释效率。  

## 2. 论文提出的方法论  
- **整体框架**：一种人在回路（human-in-the-loop）的计算框架，命名为 **FM‑SAE**。  
- **核心技术要素**：  
  - **CPath 基础模型（Foundation Models, FMs）**：对 H&E 整切片图像进行深度特征提取，获得高维嵌入向量。  
  - **稀疏自编码器（Sparse Autoencoders, SAEs）**：对 FM 嵌入进行分解，强制学习可分离、稀疏的潜在特征，使得每个维度对应一种具有明确生物学或形态学意义的组织学特征（如坏死、炎症、纤维化区域等）。  
  - **人机协同交互**：专家可对自动提取的特征进行审核、修正或赋予标签，模型通过迭代优化不断增强特征的可解释性和覆盖面。  
- **关键流程**：H&E 图像 → 基础模型嵌入 → SAE 解耦 → 多特征图谱 → 专家在回路标注/确认 → 形态感知的二维/三维组织注释 → 与分子空间数据整合。  

## 3. 实验设计  
- **数据与应用场景**：聚焦于肺部疾病，具体包括 **结核病** 和 **肺癌** 的人体组织样本，同时涉及 H&E 全切片图像和对应的空间蛋白/RNA 表达图谱。  
- **对比基准**：摘要未详细列明对比方法，但从动机看，其间接对比对象是缺乏可解释性的传统 CPath 模型和单纯依靠专家人工注释的工作流。  
- **评估维度**：  
  - 特征的人类可解释性（专家评估）  
  - 专家解读效率的加速程度（人在回路验证）  
  - 与分子空间图谱的整合能力（2D/3D 组织架构匹配）  

## 4. 资源与算力  
- 提供的摘要及元数据中 **未提及** 所使用 GPU 的型号、数量、训练耗时等算力细节。  
- 鉴于应用基础模型处理全切片图像，预计需较高计算资源，但无法从有限文本中确认具体配置。  

## 5. 实验数量与充分性  
- 根据目前信息，仅能确认进行了 **两类肺部疾病（结核病、肺癌）** 的应用验证，生成了形态感知注释并实现了与空间组学的集成。  
- **无法评估详细实验规模**：不知晓切片数量、来自多少患者、是否包含独立验证集、有无消融实验（如仅用 FM 不加 SAE、无人在回路等对照设置）。  
- 现有摘要足以支撑方法可行性的初步证明，但实验的 **统计学充分性和外部泛化性** 尚需阅读全文判断。  

## 6. 论文的主要结论与发现  
- FM‑SAE 框架能够从 H&E 图像中自动提取出 **多种人类可解释的组织病理学特征**，无需依赖密集的人工标注。  
- 在肺部疾病诊断场景下，该方法 **显著增强并加速了病理专家的解读过程**，体现了人机协同增益。  
- 生成的注释具有 **形态学感知能力**，可无缝桥接传统组织学二维/三维结构信息与分子空间组学数据，为多尺度空间分析提供了新范式。  
- 整体上，该工作提高了计算病理模型的 **生物学解释性**，为 H&E 图像在空间多组学时代的价值再提升提供了可行方案。  

## 7. 优点  
- **可解释性设计**：利用稀疏自编码器自然赋予特征维度以可解释性，克服了深度学习“黑箱”难题，对临床应用和生物学发现至关重要。  
- **人在回路机制**：融合专家知识，既能校正模型输出，又使注释工作本身被加速，具有良好的实用性和灵活性。  
- **形态学与分子数据融合**：提出了一条形态引导的空间组学对齐路径，有助于挖掘组织结构与分子表达之间的潜在关系。  
- **模型通用性潜力**：框架基于基础模型嵌入，未来或可相对容易地迁移至其他器官或疾病类型。  

## 8. 不足与局限  
- **实验范围较窄**：目前仅公开了肺部结核病与肺癌两类疾病的结果，在其它器官、其它病理类型上的泛化能力尚未验证。  
- **算力与模型开销未知**：基础模型推理与 SAE 训练的计算成本、部署可行性在现有材料中未被讨论。  
- **人在回路依赖性**：虽然加速了专家解读，但对专家先验知识仍有一定依赖，在不同标注质量标准环境下效果可能波动。  
- **对比基线不明确**：摘要未提供与现有可解释性方法（如注意力热图、概念象形等方法）的定量比较，难以判断相对优劣。  
- **全文信息缺失**：由于 PDF 无法获取，许多关键细节（如 SAE 架构、损失函数设计、空间组学整合算法、样本量、统计检验）尚不可知，以上局限分析有待完整论文补充。  

（完）
