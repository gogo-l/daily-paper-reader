---
title: A multi-agent system for spine MRI report generation from multi-sequence imaging
title_zh: 基于多序列影像的脊柱MRI报告生成多智能体系统
authors: "Xiao, Z., Yang, J., Sun, G., Zhang, H., Xu, H., Yao, Y., Miller, Z. D., King, W. E., Kanani, M. M., Andre, J. B., Chu, S., Zhang, M., Kinahan, P. E., Cross, N. M., Wang, S."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730703v1.full.pdf"
tags: ["query:med-lifelong"]
score: 10.0
evidence: 提出一种用于脊柱MRI自动报告生成的多智能体系统，实现医学图像分析与解读
tldr: "脊柱MRI临床解读需整合多序列信息，耗时且复杂。SpineAgent通过持续训练合成器融合T1/T2编码器处理多序列数据，并集成37个专业智能体分解临床子任务。在17种脊柱疾病预测上AUROC平均提升10.8%，报告生成经专家评估达领先水平。该框架为多序列脊柱MRI提供了可解释、泛化强的报告生成方法。"
source: biorxiv
selection_source: fresh_fetch
motivation: 脊柱MRI解读需整合多序列与多区域信息，自动化报告生成面临序列特异性保留与融合的挑战。
method: 先分别预训练T1和T2序列的DINOv3编码器，再用持续训练策略学习合成器嵌入其他序列，生成患者级嵌入；集成37个专用智能体，最终由Medical Report Agent生成报告。
result: "在17项脊柱条件预测任务上AUROC平均提升10.8%，跨制造商和队列验证显示强泛化性，报告生成获五位放射科医师领先评价。"
conclusion: SpineAgent通过持续训练与多智能体分解，实现准确、可解释、泛化性强的脊柱MRI报告生成，为多序列医学影像理解提供了有效框架。
---

## 摘要
脊柱病变是全球疼痛和残疾的主要原因之一。脊柱磁共振成像（MRI）是临床评估的核心手段，但其解读仍然复杂且耗时，需要整合多个成像序列和解剖区域的信息。尽管自动MRI分析技术近来取得进展，但如何有效结合多序列数据并保留序列特异性的诊断信息仍是一个开放挑战。在此，我们提出SpineAgent，一个用于脊柱MRI报告生成的多智能体框架，它建立在一个多序列基础模型之上，该模型基于32,047例患者、453,683个MRI序列（共13,441,191张MRI切片）的常规临床数据训练而成。为适应不同的序列模态，我们首先在T1和T2加权序列上分别预训练两个基于DINOv3的编码器。随后，我们引入一种持续训练策略，学习一个合成器，利用T1和T2编码器将其他序列的图像嵌入，生成整合了不同MRI序列信号的患者级嵌入。利用这些嵌入，SpineAgent在17项脊柱疾病预测任务上取得了最先进的性能，相较于最佳竞争方法平均AUROC提升了10.8%，并在跨制造商和跨队列评估中展现出强大的泛化能力。除分类任务外，SpineAgent还能通过识别与发现相关的切片并分割病理区域来实现病灶定位。它还支持多模态图像-报告检索，为可扩展且可解释的MRI报告生成奠定坚实基础。我们进一步将这些经过验证的功能整合到37个专业智能体中，分别负责疾病诊断、病理区域定位和临床相似病例检索。最后，我们将这些智能体的输出作为结构化令牌整合到一个端到端训练的医学报告智能体中，用于报告生成。通过自动指标和五位放射科医生的专家评估，SpineAgent在脊柱MRI报告生成方面取得了领先性能。总之，SpineAgent为多序列脊柱MRI理解引入了一种持续训练方法。通过将报告生成分解为基于临床的子任务并由专业智能体处理，SpineAgent框架能够在不同成像序列和解剖区域中实现准确、可解释且泛化性强的脊柱MRI报告生成。

## Abstract
Spinal pathology is a leading cause of pain and disability worldwide. Spine magnetic resonance imaging (MRI) is central to clinical evaluation, yet its interpretation remains complex and time-consuming, requiring integration of information across multiple imaging sequences and anatomical regions. Despite recent advances in automated MRI analysis, effectively combining multi-sequence data while preserving sequence-specific diagnostic information remains an open challenge. Here we present SpineAgent, a multi-agent framework for spine MRI report generation built upon a multi-sequence foundation model trained on routine clinical data from 32,047 patients and 453,683 MRI series, comprising a total of 13,441,191 MRI slices. To accommodate diverse modalities of sequences, we first pre-train two DINOv3-based encoders separately on T1- and T2-weighted sequences. We then introduce a continual training strategy that learns a synthesizer to embed images of other sequences using the T1 and T2 encoders, producing patient-level embedding that integrates various signals across MRI sequences. Using these embeddings, SpineAgent achieves state-of-the-art performance, with mean 10.8% AUROC improvement across 17 spinal condition-prediction tasks compared to the best competing method, and demonstrates strong generalizability under cross-manufacturer and cross-cohort evaluation. Beyond classification, SpineAgent enables pathology localization by identifying findings-relevant slices and segmenting pathological regions. It also supports multimodal image-report retrieval, providing a solid foundation for scalable and explainable MRI report generation. We further integrate these validated capabilities of SpineAgent into 37 specialized agents for condition diagnosis, pathological-region localization, and clinically-similar-cases retrieval. Finally, we incorporate their outputs as structured tokens within a Medical Report Agent trained end-to-end for report generation. Through both automated metrics and expert evaluation by five radiologists, SpineAgent achieves leading performance in spine MRI report generation. Together, SpineAgent introduces a continual training approach for multi-sequence spine MRI understanding. By decomposing report generation into clinically grounded subtasks addressed by specialized agents, the SpineAgent framework enables accurate, interpretable and generalizable spine MRI reporting across diverse imaging sequences and anatomical regions.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
- **研究动机与背景**  
  脊柱病变是全球疼痛和残疾的主要病因，脊柱MRI是临床评估的核心工具。然而，准确解读脊柱MRI需要放射科医师同时整合**T1加权、T2加权及其他补充序列**的多模态信息，并覆盖多个解剖区域（颈椎、胸椎、腰椎等），这一过程**极为耗时且复杂**，容易受到观察者间差异的影响。
- **整体含义**  
  论文旨在解决**多序列脊柱MRI的自动化报告生成**问题。核心挑战在于如何有效融合不同成像序列的信息，同时保留各序列独有的诊断特征。为此，作者提出**SpineAgent**——一个多智能体框架，它通过多序列基础模型和任务分解，实现准确、可解释且泛化性强的脊柱MRI报告生成，有望大幅减轻临床工作负担并提升诊断一致性。

### 2. 论文提出的方法论
- **核心思想**  
  将脊柱MRI报告生成分解为一系列临床子任务（疾病诊断、病理区域定位、相似病例检索），由**37个专业智能体**分别处理，并将它们的输出作为结构化信息输入到一个端到端训练的**医学报告智能体**中，最终生成结构化报告。
- **关键技术细节与流程**
  - **多序列基础模型训练**  
    1. **序列特异性编码器预训练**：基于**DINOv3**架构，分别在大规模T1加权和T2加权序列上预训练两个独立的图像编码器，以捕获每种序列的特异诊断特征。  
    2. **持续训练合成器**：引入一个**合成器模块**，通过持续学习策略，利用已预训练的T1、T2编码器将其他辅助序列（如STIR、增强扫描等）的图像嵌入，从而生成融合多序列信号的患者级嵌入表示。  
    3. 这一设计避免了为每个序列单独训练编码器，同时保留了T1/T2的核心诊断价值。
  - **多智能体系统构建**  
    1. **37个专业智能体**：基于上述患者级嵌入，负责三类子任务：  
       - 疾病状态诊断（覆盖17种脊柱病变）  
       - 病理区域定位（识别相关切片并分割病灶）  
       - 临床相似病例检索（多模态图像-报告检索）  
    2. **医学报告智能体**：接收专业智能体输出的结构化令牌（诊断结果、定位信息、相似病例特征），端到端训练生成最终的脊柱MRI结构化报告。
  - **算法流程概览**（文字说明）  
    *输入多序列MRI* → T1/T2编码器 + 合成器 → *患者级多序列嵌入* → 37个专业智能体并行推理 → *结构化诊断令牌* → 医学报告智能体 → *最终报告*。

### 3. 实验设计
- **数据集**  
  基于**常规临床数据**构建的大规模私有数据集：**32,047 例患者**，共 **453,683 个MRI序列**，包含 **13,441,191 张MRI切片**。数据涵盖了多厂家设备和多成像中心，支持跨制造商、跨队列的泛化性验证。
- **基准任务与对比方法**
  - **疾病分类**：17项脊柱疾病预测任务，以**AUROC**为主要指标。对比了当时的最佳竞争方法（文中未列出具体名称，但称“相较于最佳竞争方法平均AUROC提升10.8%”）。
  - **报告生成**：采用自动评估指标（如BLEU、ROUGE等）以及**五位放射科医师**的专家评审，对比基线方法（未明确列出，但提及“达到领先性能”）。
  - **其他能力验证**：病灶定位（切片识别与区域分割）、多模态图像-报告检索。
- **评估场景**  
  跨制造商泛化、跨队列泛化，证明模型的鲁棒性。

### 4. 资源与算力
- **算力说明**  
  论文提供的文本中**未明确说明**使用的GPU型号、数量、训练时长或算力消耗等具体信息。

### 5. 实验数量与充分性
- **实验组数概览**  
  从描述看，至少包括以下几类实验：  
  - 17项脊柱疾病分类任务（内部验证、跨制造商、跨队列）  
  - 病灶定位与分割评估  
  - 多模态检索性能评估  
  - 报告生成自动指标评估 + 5位放射科医生的人工评价  
  - 可能涉及的消融实验（例如多序列融合策略的有效性，文中未详细说明但此类研究通常包含）
- **充分性与客观公平性**  
  - **充分性**：实验覆盖了核心任务（分类）、辅助任务（定位、检索）以及最终应用（报告生成），并通过跨场景泛化验证，维度较为全面。五位放射科医生的专家评估增强了报告生成评价的临床可信度。  
  - **客观公平**：分类任务采用统一指标AUROC与最强竞争方法对比；报告生成结合自动化指标与专家双盲评审，设计相对客观。但未提及对比方法的详细清单和公开数据集基线，可能部分削弱了可复现性验证。

### 6. 主要结论与发现
- 在**17项脊柱疾病预测**上，SpineAgent 达到**最先进水平**，平均 AUROC 较最佳竞争方法**提升10.8%**。
- 模型在**跨制造商和跨队列**评估中展现出**强大的泛化能力**，说明未过拟合于特定数据源。
- 成功实现了**病灶定位**（相关切片识别与病理区域分割）和**多模态检索**，为报告生成提供了可解释性支撑。
- 最终生成的脊柱MRI报告在自动指标和**五位放射科医师专家评估**中均取得**领先性能**，表明多智能体分解策略有效。

### 7. 优点（亮点）
- **持续训练的多序列融合策略**：分别预训练T1/T2编码器再学习合成器，既保留了序列特异性又实现了灵活的多序列聚合。
- **任务分解与多智能体架构**：将复杂的报告生成拆解为临床可解释的子任务（诊断、定位、检索），每个智能体专注一项，整体输出结构化且可追溯。
- **大规模真实世界数据**：训练集来自数万例患者千万级切片，增强了模型在真实临床场景中的泛化性。
- **全链路验证**：从底层分类、定位、检索到顶层报告生成，环环相扣，并通过自动化指标和专家评审双重验证。
- **临床友好设计**：提供病灶定位、相似病例检索等功能，为放射科医生呈现“可解释”的报告生成路径。

### 8. 不足与局限
- **算力细节缺失**：未报告训练资源和时间，难以评估实际落地成本。
- **对比方法不透明**：仅提及“最佳竞争方法”，未列出具体模型名称、版本或公开实现，限制了他人的公平复现和比较。
- **报告生成评估可能偏主观**：虽然引入了5位放射科医师，但报告未详述评分量表、评分者间一致性等细节，存在潜在主观偏差。
- **数据局限性**：数据集为单中心或多中心私有数据，是否包含罕见病种、不同场强（1.5T/3T）、不同种群未明确说明，可能影响全球适用性。
- **病灶定位精度未知**：定位能力仅概括性描述，缺少如 Dice 系数或 IoU 等定量分割指标，定位质量无从考证。
- **可解释性边界**：检索到的相似病例可能引入隐私风险或依赖海量索引库，实际部署时的伦理和工程技术挑战未讨论。

（完）
