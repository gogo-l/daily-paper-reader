---
title: "LVentiView: An Open-Source Software for Automated 3D Left Ventricular Mesh Reconstruction and Analysis from Cardiac MRI"
title_zh: LVentiView：一款用于心脏MRI自动三维左心室网格重建与分析的开源软件
authors: "Braun, I., Wang, Y., Ecker, A. S., Bodenschatz, E."
date: 2026-05-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.22.727166v1.full.pdf"
tags: ["query:med-lifelong"]
score: 9.0
evidence: 心脏MRI自动分割和三维网格重建，用于患者特异性左心室分析
tldr: 患者特异性心脏建模需要精确的左心室三维表示，但手工处理耗时、依赖专家且缺乏自动化流程。LVentiView开源软件实现了从心脏MRI分割到仿真网格的全自动化，并在Sunnybrook数据集上验证，分割达专家水平，网格体积与手动标注一致，厚度图能捕捉病理特异性增厚，处理速度极快。该工具为心脏模拟提供了易用、可靠、可重复的基础，显著降低了技术门槛。
source: biorxiv
selection_source: fresh_fetch
motivation: 手动从心脏MRI重建左心室仿真网格繁琐、费时且依赖专业经验，缺乏一体化的开源自动化工具。
method: LVentiView自动化完成MRI分割、仿真就绪体积网格生成及区域壁厚分析，无需人工干预。
result: 分割精度与专家相当，网格体积偏差在专家间变异内，厚度图区分正常与肥厚等病理，分割每切片0.07秒，网格每帧<3分钟。
conclusion: LVentiView为患者特异性心脏建模提供了免费、易用且经过验证的自动化方案，推动心脏模拟的临床可及性。
---

## 摘要
患者特异性心脏建模需要从心脏磁共振成像（MRI）重建精确的左心室（LV）三维表示。在此，我们介绍LVentiView，一款开源软件，它通过自动化从MRI分割到可仿真体积网格的完整流程，桥接了医学影像与心脏模拟，并集成了体积分析和区域心肌厚度计算工具。我们在包含健康受试者和三种心脏病变的Sunnybrook心脏数据集上验证了LVentiView。LVentiView的血池分割达到了专家间水平。生成的网格通过与专家手动分割掩膜计算出的LV体积进行比较进行验证，在所有四种心脏病理中，体积和心脏参数均在专家间变异性范围内一致。此外，基于网格的区域厚度图捕捉了病理特异性模式，包括肥厚型病例中的壁增厚。LVentiView在GitHub上免费提供，为患者特异性心脏建模提供了可访问且经过验证的基础。

亮点O_LILVentiView自动化了从MRI分割到可仿真网格的完整流程。
C_LIO_LI基于网格的心脏体积和参数与专家手动分割精度相匹配。
C_LIO_LI厚度图捕捉病理特异性模式，验证了几何保真度。
C_LIO_LI分割速度约为每层0.07秒；网格生成每帧不到3分钟。
C_LI

图形摘要

O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=72 SRC="FIGDIR/small/727166v1_ufig1.gif" ALT="图1">
查看大图 (22K)：
org.highwire.dtl.DTLVardef@f10d08org.highwire.dtl.DTLVardef@18eab94org.highwire.dtl.DTLVardef@1a298e9org.highwire.dtl.DTLVardef@1e52347_HPS_FORMAT_FIGEXP  M_FIG C_FIG

## Abstract
Patient-specific cardiac modeling requires accurate three-dimensional representations of the left ventricle (LV) reconstructed from cardiac magnetic resonance imaging (MRI). Here, we present LVentiView, an open-source software that bridges medical imaging and cardiac simulation by automating the full pipeline from MRI segmentation to simulation-ready volumetric meshes, with integrated tools for volumetric analysis and regional myocardial thickness calculation. We validate LVentiView on the Sunnybrook Cardiac Dataset, comprising healthy subjects and three cardiac pathologies. LVentiView achieves blood pool segmentation at the inter-expert level. The generated meshes are verified by comparing LV volumes extracted from the meshes to those computed from expert manual segmentation masks, with volumes and cardiac parameters agreeing within inter-expert variability across all four cardiac pathologies. In addition, mesh-derived regional thickness maps capture pathology-specific patterns, including wall thickening in hypertrophic cases. LVentiView is freely available on GitHub and provides an accessible, validated foundation for patient-specific cardiac modeling.

HighlightsO_LILVentiView automates the full pipeline from MRI segmentation to simulation-ready meshes.
C_LIO_LIMesh-derived cardiac volumes and parameters match expert manual segmentation accuracy.
C_LIO_LIThickness maps capture pathology-specific patterns, validating geometrical fidelity.
C_LIO_LISegmentation runs at {approx} 0.07 s per slice; meshing under 3 min per frame.
C_LI

Graphical Abstract

O_FIG O_LINKSMALLFIG WIDTH=200 HEIGHT=72 SRC="FIGDIR/small/727166v1_ufig1.gif" ALT="Figure 1">
View larger version (22K):
org.highwire.dtl.DTLVardef@f10d08org.highwire.dtl.DTLVardef@18eab94org.highwire.dtl.DTLVardef@1a298e9org.highwire.dtl.DTLVardef@1e52347_HPS_FORMAT_FIGEXP  M_FIG C_FIG

---

## 论文详细总结（自动生成）

## 一、研究动机与核心问题

- 患者特异性心脏建模依赖于从心脏磁共振成像（MRI）重建精确的左心室三维几何，但传统手工分割、表面重建与网格生成流程极为繁琐，耗时且高度依赖专家经验，严重制约了心脏仿真在临床研究中的应用。
- 目前缺乏一体化的开源自动化工具，能直接从心脏MRI完成从分割到可仿真体积网格的全流程，并集成心室体积和区域壁厚分析。该研究的核心问题是：能否构建一个全自动、经验证且易于获取的软件，从而降低患者特异性左心室建模的技术门槛。

## 二、方法论

- **核心思路**：开发LVentiView开源软件，实现“MRI分割 → 可仿真体积网格 → 心腔体积计算 → 区域厚度图”的端到端自动化流水线，无需人工干预。
- **关键技术**（根据摘要和描述推断）：
    - 自动分割左心室血池，达到专家间水平；具体分割模型未在提供文本中详细说明，可能采用深度学习模型。
    - 从分割掩膜中重建三维表面，并生成适合有限元仿真的体积网格（仿真就绪网格）。
    - 基于网格计算左心室腔体体积、射血分数等心脏参数，并绘制左心室壁的区域厚度图，用于捕捉病理特征（如肥厚性增厚）。
- **公式或算法细节**：提供的文本未包含具体公式、网络结构或网格生成算法。仅知分割速度约为每层0.07秒，网格生成每帧不足3分钟。

## 三、实验设计

- **数据集**：使用Sunnybrook心脏数据集，包含健康受试者及三种心脏病变（如肥厚型等，共四种心脏病理状态）。
- **基准与对比**：
    - 将LVentiView的血池分割结果与专家手动分割进行对比，评价是否达到专家间变异水平。
    - 将网格推导出的左心室体积和心脏参数与基于专家手动分割掩膜计算出的结果进行对比，验证是否落在专家间变异性范围内。
    - 通过网格生成的区域厚度图定性或半定量地展示病理特异性模式（如肥厚患者的壁增厚）。
    - 文中未提及与其他自动化分割或网格重建方法（如nnU-Net、其他心脏分割工具）的直接定量对比。

## 四、资源与算力

- 提供的文本中**未明确说明**所使用的GPU型号、数量、训练显存消耗或训练总时长。仅给出了推理速度（分割约0.07秒/层，网格生成<3分钟/帧），但未涉及模型训练阶段的算力需求。

## 五、实验数量与充分性

- 实验规模与评估维度可推断如下：
    - 至少在四种心脏病理条件下进行了分割精度和体积一致性验证，每种病理包含多个受试者，但未给出具体样本量。
    - 进行了分割精度（与专家对比）、网格体积一致性、厚度图定性评估三类实验。
    - **消融实验、跨扫描仪/跨中心泛化实验、与现有自动化工具的横向对比、统计显著性检验等**在现有摘要中未见提及。实验设计主要依赖专家间变异作为接受标准，缺乏多方法对比和更细致的误差分析，整体实验广度有限，但核心验证逻辑（与专家水平对齐）是客观且合理的。

## 六、主要结论与发现

- LVentiView的血池分割精度达到专家间水平。
- 由网格计算的心室体积和心脏参数在所有四种病理中均与专家手动分割结果一致，偏差落在专家间变异性内。
- 网格导出的区域壁厚图能够捕捉肥厚型等病变的特异性增厚模式，证明了几何重建的保真度。
- 软件运行高效：分割约0.07秒/切片，网格生成每时间帧<3分钟。
- 整体上，LVentiView为患者特异性心脏建模提供了一个免费、经过验证且可复现的自动化基础。

## 七、优点

- **完整流水线**：从MRI分割到仿真网格生成、体积分析与厚度图，一站式自动化，显著减少人工参与。
- **开源可及**：在GitHub免费发布，推动心脏模拟技术的民主化。
- **临床相关验证**：选用公开数据集，并以专家间变异性为接受标准，评估方式贴近临床应用需求。
- **速度优势**：推理速度快，适合批量处理或临床快速反馈场景。
- **多病理覆盖**：验证包括正常和三种心脏病理，初步展示泛化潜力。

## 八、不足与局限

- **实验对比有限**：未与其他自动化左心室分割或网格重建方法进行直接定量比较（如Dice系数、Hausdorff距离的对比表格），缺乏与现有工具的优劣分析。
- **数据集单一**：仅在Sunnybrook心脏数据集上进行验证，未在多个中心、不同磁场强度或不同序列的数据上测试，泛化性待进一步证实。
- **网格质量评估不充分**：厚度图捕捉病理模式属于定性验证，缺乏网格对仿真结果（如应力分布、血流动力学）影响的敏感性分析。
- **技术细节缺失**：摘要未提供分割网络架构、网格生成算法、训练细节等，复现的透明度有限（虽已开源，但论文本身未阐述）。
- **偏差风险**：Sunnybrook数据集为公开老数据集，可能存在选择偏倚；且仅在四种病理上验证，不包括缺血性心脏病、左心室致密化不全等其他常见病变。
- **应用限制**：仅处理左心室，未涉及右心室、心房或大血管，限制了整体心脏建模的扩展性。

（完）
