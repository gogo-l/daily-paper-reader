---
title: "Benchmarking attention-based methods for vision transformers' interpretability in retinal fundus imaging"
title_zh: 在视网膜眼底成像中基于注意力方法的视觉Transformer可解释性基准测试
authors: "Bors, S., Beyeler, M., Trofimova, O., VascX Consortium,, Presby, D., Bontempi, D., Bergmann, S."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732470v1.full.pdf"
tags: ["query:med-lifelong"]
score: 9.0
evidence: 基准评估视网膜眼底图像分析中基于注意力的可解释性方法
tldr: 该研究系统评估了视网膜基础模型在眼底图像上微调后的四种注意力可解释性方法，比较其忠实度和生物学相关性。实验利用UK Biobank数据预测血管表型，为医学图像分析中Vision Transformer模型的解释提供了基准。
source: biorxiv
selection_source: fresh_fetch
motivation: 基准评估视网膜眼底图像分析中基于注意力的可解释性方法。
method: 方法与实现细节请参考摘要与正文。
result: 结果与对比结论请参考摘要与正文。
conclusion: 总体而言，该工作在所述任务上展示了有效性，并提供了可复用的思路或工具。
---

## 摘要
基于视觉Transformer（ViT）的深度学习模型在视网膜眼底成像中展现出强大的性能，但其可解释性仍知之甚少。特别是，基于注意力的归因方法被广泛用于解释ViT的预测，尽管在医学成像中对其忠实度和生物学相关性的评估有限。在此，我们系统地基准测试了四种基于注意力的可解释性方法，用于RETFound——一个基于视网膜ViT的基础模型，我们之前对其进行了微调，以从英国生物银行眼底图像中预测17种视网膜血管表型。我们使用定性的可视化和定量的评估框架，比较了原始注意力、注意力传播、梯度加权注意力传播以及Chefer的混合相关性方法。为了评估归因的忠实度，我们进行了基于扰动的删除和插入实验，量化了当高度关注的图像区域被逐步移除或恢复时模型预测的变化。为了评估生物学特异性，我们运行了结构感知分析，通过注意力强度相对比率（RAI）指标，将归因图与血管分割和动静脉标签相结合。在各模型中，根据所选的可解释性方法，归因图存在显著差异，这突显了进行严格定量评估的必要性。在评估的方法中，梯度加权注意力传播始终取得了最强的扰动性能，并产生了与预测的视网膜特征解剖定义最一致的归因图。此外，特定血管类型的模型系统性地将注意力集中在相应的血管结构上，尽管训练时每张图像仅使用单个标量值作为监督。这些发现表明，基于注意力的归因方法能够捕获具有生物学意义的血管表征，同时也揭示了归因行为中依赖于方法的变化性。这项工作为在具有标注分割的医学成像中评估可解释性方法提供了一个定量框架，并有助于构建更透明和更具生物学基础的医学人工智能系统。

## Abstract
Deep learning models based on Vision Transformers (ViTs) have shown strong performance in retinal fundus imaging, but their interpretability remains poorly understood. In particular, attention-based attribution methods are widely used to explain ViT predictions, despite limited evaluation of their faithfulness and biological relevance in medical imaging. Here, we systematically benchmark four attention-based interpretability methods for RETFound, a retinal ViT-based foundation model, that we previously fine-tuned to predict 17 retinal vascular phenotypes from UK Biobank fundus images1. We compare raw attention, attention rollout, gradient-weighted attention rollout, and Chefer's hybrid relevance-based method using both qualitative visualisation and quantitative evaluation frameworks. To assess attribution faithfulness, we perform perturbation-based deletion and insertion experiments, quantifying changes in model predictions as highly attended image regions are progressively removed or restored. To evaluate biological specificity, we run structure-aware analyses combining attribution maps with vessel segmentation and artery-vein labels through the Relative ratio of Attention Intensity (RAI) metric. Across models, attribution maps differed substantially depending on the selected interpretability method, highlighting the need for rigorous quantitative evaluation. Among the evaluated approaches, gradient-weighted attention rollout consistently achieved the strongest perturbation performance and produced attribution maps most closely aligned with the anatomical definition of the predicted retinal traits. Furthermore, vessel-type specific models systematically concentrate attention on the corresponding vascular structures despite being trained using only a single scalar value per image as supervision. These findings demonstrate that attention-based attribution methods capture biologically meaningful vascular representations, while also revealing method-dependent variability in attribution behaviour. This work provides a quantitative framework for evaluating interpretability methods in medical imaging with annotated segmentation and contributes toward more transparent and biologically grounded medical AI systems.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将使用中文、以 Markdown 格式，对给定的论文进行结构化、深入且客观的总结。

### 1. 论文核心问题与整体含义

这篇论文的核心问题是：**在医学影像（特别是视网膜眼底图像）分析中，用于解释视觉Transformer (ViT) 模型预测的基于注意力的可解释性方法，其忠实度和生物学特异性究竟如何？**

*   **研究动机与背景**：
    *   **应用广泛但理解不足**：基于 ViT 的深度学习模型（如 RETFound）在眼科疾病和血管健康预测中表现出色，但它们是“黑箱”模型。其决策过程不透明，阻碍了临床应用信任度和生物学发现。
    *   **方法多样但缺乏基准**：研究者经常使用基于注意力的可视化方法来解释这些模型，如原始注意力、注意力传播等。然而，这些方法在医学领域的可靠性和生物学关联性缺乏系统性的定量评估和基准测试。多数研究仅依赖少数精选案例的定性观察。
    *   **研究目标**：该研究旨在填补这一空白，通过在预测明确的视网膜血管表型的任务上，系统地比较和评估四种流行的注意力归因方法，不仅评估它们是否忠实反映模型决策，还评估它们能否捕捉到有意义的血管生物学结构。

### 2. 方法论

论文提出了一个结合定性和定量的评估框架，用于基准测试四种注意力归因方法。

*   **核心思想**：利用一个已经微调好、用于预测特定血管表型的视网膜基础模型（RETFound），生成并比较不同解释方法产生的热力图，并从“忠实度”和“生物学相关性”两个维度进行量化评估。

*   **关键技术细节**：
    1.  **基础模型与任务**：使用预训练并微调过的 RETFound (ViT-L/16) 模型，该模型被训练用于从英国生物银行（UK Biobank）眼底图像中，根据图像级的单个标量值（如血管密度、弯曲度）预测17种视网膜血管表型。
    2.  **评估的四种归因方法**：
        *   **原始注意力 (Raw Attention)**：提取最终 Transformer 层的注意力矩阵，并使用**头部敏感性分析**（通过逐一屏蔽注意力头，观察预测变化来加权平均各头，而非简单平均）进行聚合，得到类别标记到图像块的注意力图。
        *   **注意力传播 (Attention Rollout)**：从输入层到输出层，递归地将所有层的注意力矩阵与残差连接相结合，以模拟信息流动。
        *   **梯度加权注意力传播 (Gradient-Weighted Attention Rollout)**：在注意力传播的基础上，使用注意力矩阵相对于模型输出的梯度来调整每层的注意力权重，突出对预测更有影响力的信息流。
        *   **Chefer 的混合方法 (Chefer’s Hybrid Method)**：结合了层级相关性传播（LRP）和注意力梯度。通过为 Transformer 各层定制 LRP 规则，将相关性从输出反向传播到输入层，并与注意力梯度相乘，最终通过传播机制生成归因图。
    3.  **定量评估指标**：
        *   **忠实度**：通过**扰动实验**（删除/插入）来衡量。根据归因图分数从高到低移除（删除）或恢复（插入）图像块，观察模型预测值的变化曲线。曲线下面积（或面积上/下）用于量化影响，变化越剧烈，表示归因方法越忠实。
        *   **生物学特异性**：使用**注意力强度相对比率 (RAI)** 指标进行分析。RAI 计算了在特定结构（如所有血管、动脉、静脉）内部的平均注意力强度与其外部平均注意力强度的比值。RAI > 1 表示模型更关注该结构。通过比较动、静脉的 RAI 分布（使用 Cohen's d 效应量），评估模型是否学到了血管类型的特异性。

### 3. 实验设计

*   **数据集**：
    *   **图像数据**：UK Biobank 的眼底图像（仅限右眼，黄斑居中、视盘偏右对齐），输入尺寸调整为 224×224 像素。
    *   **预测目标**：17种由自动化管线测量得到的视网膜血管表型特征（如动脉/静脉血管密度、弯曲度、分叉计数、颞侧角度等）。
    *   **血管标注**：使用 SOTA 自动分割管线生成的血管分割掩码和动/静脉标签，用于 RAI 计算。

*   **基准 (Benchmark)**：
    *   **主要对比**：四种基于注意力的可解释性方法（原始注意力、注意力传播、梯度加权注意力传播、Chefer 混合方法）之间的性能比较。
    *   **对照模型**：使用一个参数完全随机初始化、未经任何训练的 RETFound 模型作为**控制组**，以验证归因图中的模式是“学到的”而不是方法的伪影。

*   **评估维度**：
    1.  **定性评估**：可视化个体图像和群体平均的归因图。
    2.  **定量-忠实度评估**：通过删除/插入扰动实验，绘制预测值保留/恢复曲线，计算曲线面积。
    3.  **定量-生物学特异性评估**：计算 RAI 和 Cohen's d 效应量，分析注意力与血管结构的对齐程度。

### 4. 资源与算力

*   **论文中未明确说明**：文中未提及执行这些分析所使用的具体 GPU 型号、数量、以及生成归因图或运行扰动实验所需的计算时间。
*   **推断**：鉴于其任务的复杂性和规模，可以推断该研究需要中等到大量的 GPU 算力，特别是为了对全队列数千张图像进行逐张的扰动实验和反向传播计算。

### 5. 实验数量与充分性

*   **实验规模**：实验覆盖了17个不同的预测任务（模型），每个模型都应用了4种归因方法，并进行了2种扰动实验（删除/插入）。此外，还对所有模型进行了血管特异性分析。
*   **充分性分析**：
    *   **全面性**：实验设计非常全面，覆盖了多种模型、多种解释方法、两种定量评估范式和一种强对照（随机模型）。
    *   **客观性与公平性**：
        *   采用了**5折交叉验证**，并报告了均值±标准误（SEM），增加了统计严谨性。
        *   引入了**头部敏感性分析**来改进原始注意力方法，避免了简单平均的主观性，使比较更公平。
        *   **控制模型**的运用是关键的“健全性检查”，有效排除了归因图是方法无关伪影的可能性，使得对于已训练模型的结论更加可靠。
        *   使用统一的预处理、可视化和评估流程，保证了方法间的可比性。
    *   **总体评价**：实验数量充足，设计周密、客观且公平，对于得出可靠结论提供了坚实的基础。

### 6. 主要结论与发现

1.  **方法间存在巨大差异**：不同的归因方法会产生显著不同的热力图，即便应用于同一模型和同一输入。这强调了不能仅凭可视化进行判断，必须进行定量评估。
2.  **最优方法**：**梯度加权注意力传播在忠实度方面整体表现最佳**，平均排名最高，尤其是在预测性能高的模型上。它能更准确地识别出对模型预测至关重要的图像区域。
3.  **忠实度与模型性能相关**：对于预测性能好（R²值高）的模型，不同归因方法的忠实度排序和差异性更加一致和明显；对于性能差的模型，不同方法的表现趋同，更难区分优劣。
4.  **模型学到了生物学知识**：尽管训练时只使用了一个标量值作为监督，微调后的模型能够**隐式地学到血管类型的特异性**。例如，预测“动脉血管密度”的模型会系统性地关注动脉，而预测“静脉”相关特征的模型则更关注静脉。随机模型无此现象。
5.  **归因图具有生物学意义**：所有模型的注意力的RAI均值都大于1，即普遍集中在血管区域而非背景组织，证明其预测主要基于血管信息。

### 7. 优点

*   **系统性基准测试**：首次在医学影像的视网膜任务上，对 ViT 模型的注意力解释方法进行了系统、多维度（忠实度+生物学特异性）的量化基准测试。
*   **评估框架严谨**：将扰动实验和带有解剖学标注的结构分析相结合，超越了单纯的视觉检查。引入“随机模型对照”增强了结论的可信度。
*   **方法学贡献**：证明了结合梯度信息的注意力传播（梯度加权）能更忠实、更符合生物学特征地反映模型决策过程。
*   **生物学洞察**：揭示了深度学习模型即使在没有明确监督的情况下，也能学习到如“动脉/静脉”区分等高级、具有生物学意义的概念，为使用此类模型生成生物学假设提供了支持。
*   **可复用性**：所提出的评估框架和流程可直接应用于其他医学影像模态、任务和 Transformer 模型。

### 8. 不足与局限

*   **评估方法限制**：仅关注了“基于注意力”的方法，未与其它家族的解释技术（如基于遮挡的、基于梯度的 Grad-CAM 等）进行对比。
*   **鲁棒性未评估**：论文未评估这些归因图在输入图像受到扰动时（如图像质量变化、亮度、几何变换等）的稳定性，而这对临床应用至关重要。
*   **任务泛化性待验证**：研究局限于预测已知的、血管相关的视网膜表型。这些结论能否直接推广到更复杂的临床任务，如疾病分类或死亡率风险预测，尚不明确。
*   **计算资源不透明**：论文没有提及具体的算力需求和计算成本，这给希望复现或应用该流程的研究者带来了不确定性。

（完）
