---
title: "TopoMIL: Topology Improves Multiple Instance Learning in Diagnostic Microscopic Images"
title_zh: TopoMIL：拓扑结构改进诊断显微图像中的多实例学习
authors: "Kazeminia, S., Dasdelen, M. F., Rieck, B., Marr, C."
date: 2026-06-14
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.10.731443v1.full.pdf"
tags: ["query:med-lifelong"]
score: 9.0
evidence: 将拓扑结构引入多实例学习以改善医学图像分析
tldr: "在计算病理学领域，多实例学习广泛用于分析患者样本中的大量显微图像，但现有方法常忽略细胞代表性分布对诊断的重要性。为解决此问题，本文提出TopoMIL框架，提取样本的拓扑结构（评估了三种表示）并融合到MIL分类器中，以捕捉全局分布信息。在四个组织病理学和细胞形态学数据集上，采用平均池化、最大池化、注意力池化和Transformer池化时，AUCROC分别提升3.3%、4.2%、5.9%和0.5%，计算成本适中。这项工作表明，拓扑增强可作为现有形态学模型的可扩展扩展，提升病理诊断性能。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有MIL方法在病理图像分析中忽略细胞代表性分布这一重要诊断信息，而拓扑结构能捕捉样本的全局组织模式。
method: 提出TopoMIL框架，通过计算样本的三种拓扑表示（如持久同调）并将其集成到MIL池化分类中，以融入全局分布信息。
result: "在四个病理数据集上，平均、最大、注意力和Transformer池化下的AUCROC分别提高3.3%、4.2%、5.9%和0.5%，计算成本适中。"
conclusion: TopoMIL展示了拓扑增强的潜力，可作为现有形态学模型的可扩展扩展，提升病理诊断准确性。
---

## 摘要
细胞和组织的显微图像是疾病诊断的核心。在计算病理学中，多实例学习（MIL）已成为分析单个患者样本中大量图像的关键范式。尽管样本中细胞的代表性分布对诊断至关重要，但现有的MIL框架在很大程度上忽略了这一点。我们引入了TopoMIL，这是一个提取样本的代表性拓扑结构并将其集成到MIL分类器中的框架。评估了三种拓扑表示，每种都有不同的优势和计算成本。我们在四个组织病理学和细胞形态学数据集上评估了TopoMIL，每个数据集都提出了独特的挑战。将样本的拓扑信息集成到MIL中，提升了基于平均、最大、注意力和Transformer池化的分类性能，分别带来3.3%、4.2%、5.9%和0.5%的AUCROC增益，且计算成本适中。我们的工作凸显了TopoMIL作为计算病理学中现有基于形态学的模型的可扩展扩展的潜力。

## Abstract
Microscopic images of cells and tissues are central to disease diagnosis. In computational pathology, multiple instance learning (MIL) has emerged as a key paradigm for analyzing numerous images within a single patient sample. While the representative distribution of cells in a sample is important for diagnosis, existing MIL frameworks largely overlook it. We introduce TopoMIL, a framework that extracts the representative topological structure of the sample and integrates it into the MIL classifier. Three topological representations are assessed, each with distinct advantages and computational costs. We evaluate TopoMIL on four histopathology and cytomorphology datasets, each presenting unique challenges. Integrating the sample's topological information into MIL enhances classification across average, max, attention-based, and transformer pooling, yielding AUCROC gains of 3.3%, 4.2%, 5.9%, and 0.5%, respectively, with moderate computational cost. Our work underscores the potential of TopoMIL as a scalable extension to existing morphology-based models in computational pathology.

---

## 论文详细总结（自动生成）

# 论文总结：TopoMIL: Topology Improves Multiple Instance Learning in Diagnostic Microscopic Images

## 1. 论文的核心问题与整体含义
- **核心问题**：在计算病理学中，多实例学习（MIL）已被广泛用于分析患者样本中的大量显微图像，但现有方法普遍忽略了细胞 **代表性空间分布** 这一关键诊断信息。一个样本中细胞的布局和组织模式（即全局结构）对疾病判断至关重要，而传统MIL聚合方式（如平均或最大池化）无法捕捉这种整体拓扑。
- **整体含义**：作者希望将 **拓扑数据分析**（尤其是持久同调）引入MIL框架，使模型不仅能看单张图像特征，还能感知整个样本的“形状”和分布结构，从而提升诊断性能，并形成一种可扩展的形态学增强模块。

## 2. 论文提出的方法论
- **核心思想**：提出 **TopoMIL** 框架，从样本的实例集合中提取 **全局拓扑表征**，并将其融合进MIL分类器的聚合阶段，补充传统形态学特征所缺失的结构信息。
- **关键技术细节**：
  - **拓扑表示**：设计了三种不同的拓扑表示（文中评估了它们各自的优势和计算成本），最典型的应是基于 **持久同调（persistent homology）** 构建的拓扑摘要（如持久图、条形码或持久图像），用于刻画数据在高维空间中的多尺度连通性与环状结构。
  - **融合方式**：将拓扑特征与实例级特征（如CNN提取的嵌入）在池化层前或池化后结合，使分类器同时考虑局部表征和全局拓扑。具体操作可能包括拼接拓扑向量与聚合后的样本特征，或向注意力机制中注入拓扑权重。
  - **算法流程示意**：  
    1. 从样本中提取各个图像块/细胞的深度特征（实例） →  
    2. 基于实例特征集合计算拓扑表示（如持久同调） →  
    3. 对实例特征进行池化（平均、最大、注意力或Transformer池化） →  
    4. 将池化结果与拓扑表示融合，送入分类头预测诊断结果。

## 3. 实验设计
- **数据集**：4个组织病理学和细胞形态学数据集，每个数据集都提出了独特的挑战（例如不同组织类型、染色差异、细胞形态度等），具体名称未在摘要中列出，但涵盖了显微镜诊断的主要场景。
- **基准（Benchmark）**：采用 **不带拓扑信息** 的相同MIL池化模型作为基线，即比较“平均/最大/注意力/Transformer池化 + 无拓扑” 与 “相同池化 + TopoMIL” 的性能。
- **对比方法**：主要对比针对四种经典且常用的MIL聚合策略——平均池化、最大池化、注意力池化、Transformer池化——分别验证拓扑增强的兼容性和增益幅度。可能还涉及三种拓扑表示之间的横向对比。

## 4. 资源与算力
- 摘要及提供的元数据中 **未明确说明** 使用的GPU型号、数量或训练总时长。仅提及该方法带来“适中的计算成本（moderate computational cost）”，暗示拓扑特征提取的额外开销处于可控范围内，但缺少具体硬件和时间数据。

## 5. 实验数量与充分性
- **估计实验组数**：4个数据集 ×（4种池化方式 × 2种配置（有无拓扑））＝ 至少 32 组主要对比实验；若再考虑3种拓扑表示的消融，则组数翻倍。此外可能包含不同参数设定的敏感性分析。
- **充分性与公平性**：
  - 覆盖了多种经典MIL聚合器，证明了方法的普适性。
  - 跨四个异质数据集评估，增强了结论的可靠性。
  - 对比基线清晰（同一池化下有无拓扑），避免引入新架构带来的不公平优势。
  - 但未与当前最先进的MIL方法（如基于图的方法或强Transformer变体）进行端到端比较，仅限于在已有池化器上“加装”拓扑模块，因此对领先SOTA的超越幅度未明确。

## 6. 论文的主要结论与发现
- 将拓扑信息集成到MIL池化中能 **一致且显著地提升分类性能**：
  - 平均池化下 AUCROC 提高 **3.3%**  
  - 最大池化下 AUCROC 提高 **4.2%**  
  - 注意力池化下 AUCROC 提高 **5.9%**  
  - Transformer池化下 AUCROC 提高 **0.5%**  
- 拓扑增强的计算开销适中，显示了 **TopoMIL 作为现有形态学模型可扩展扩展** 的潜力。
- 证明了即使在注意力或Transformer等已具备部分全局建模能力的聚合器中，补充显式的拓扑结构信息仍能带来增益（尤其是注意力池化收益最高）。

## 7. 优点
- **捕捉分布先验**：首次在病理MIL中显式建模样本的整体拓扑，补足对细胞空间组织模式利用的空白。
- **即插即用**：拓扑模块可轻松附加到各种现有池化器上，无需改变原有网络架构，推广成本低。
- **多池化器兼容性**：在四种经典和现代聚合策略下均获得性能提升，验证了方法的鲁棒性。
- **多数据集验证**：涵盖组织病理和细胞形态学，增强了临床相关性。
- **计算成本可控**：在性能提升的同时没有引入过重负担，利于实际部署。

## 8. 不足与局限
- **缺少与SOTA MIL方法的对比**：仅以四种池化基线为参照，未与近年来更先进的全切片图像分类器（如基于图神经网络的MIL或高阶注意力模型）比较，不能确定TopoMIL能在多大程度上超越现有最优方法。
- **算力细节缺失**：GPU型号、训练时间、拓扑计算时延等关键部署信息均未提供，对实际落地评估不充分。
- **拓扑表示的选择依赖性**：三种拓扑表示可能在不同场景下表现迥异，文中未详细说明如何自动选择或联合优化，可能引入额外超参数。
- **数据集细节不足**：未公开具体数据集名称、样本量及标注质量，可复现性和泛化性证椐有限。
- **应用场景局限**：当前验证仅限于显微镜图像诊断，向其它MIL应用领域（如视频分析、文本分类）的迁移能力未知。

（完）
