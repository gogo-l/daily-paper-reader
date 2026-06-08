---
title: Supervised Domain Adaptation Mitigates Cross-Ethnicity Prediction Error in Neuroimaging Based Cognitive Prediction
title_zh: 监督域自适应减轻基于神经影像的认知预测中的跨种族预测误差
authors: "Lal Khakpoor, F., van der Vliet, W., Deng, J., Wang, Y., Pat, N."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.25.727742v2.full.pdf"
tags: ["query:med-lifelong"]
score: 9.0
evidence: 有监督域自适应缓解跨种族神经影像预测误差
tldr: 大规模神经影像数据集种族不平衡，导致机器学习模型对少数族裔认知预测性能下降。本研究评估监督域适应方法在减轻跨民族预测偏差上的效果。所有方法均降低预测误差，其中balanced weighting最优，仅需少量目标域样本即可有效适应。这些简单策略为提升神经影像预测公平性和泛化性提供了可行路径。
source: biorxiv
selection_source: fresh_fetch
motivation: 神经影像数据集种族失衡使模型对代表性不足群体预测性能差，需探索公平性提升方法。
method: 使用ABCD数据集的80个MRI指标，评估balanced weighting、TrAdaBoost等四种监督域适应方法将模型从白人群体迁移到非裔美国人。
result: 所有域适应方法降低交叉民族预测误差，balanced weighting表现最优，且仅需10个目标域个体即显著改善。
conclusion: 简单低成本的监督域适应策略可有效减少神经影像预测中的种族性能鸿沟，提升模型公平性和泛化能力。
---

## 摘要
机器学习模型越来越多地被用于从神经影像数据预测认知和临床结果，但公平性和泛化性方面的挑战依然存在。大规模数据集通常在种族和民族上不平衡，导致系统性的性能差异，模型通常在训练数据中代表的多数群体上取得更高的准确率。在本研究中，我们评估了监督域自适应方法——包括平衡加权、两阶段TrAdaBoost、结合仅源预测的特征增强以及线性插值——能否减轻这些偏差。利用ABCD数据集，我们检验了基于80项MRI指标、使用美国白人参与者训练的模型能否更有效地泛化到非裔美国参与者。所有域自适应方法都减少了非裔美国参与者的预测误差，特别是在基线差异较大的MRI模态（如结构MRI）上，而在初始差距较小的模态（如功能连接）上改善有限。在这些方法中，平衡加权表现最佳，即使仅使用10名非裔美国参与者来调整最初仅在美国白人参与者上训练的模型，也能保持稳定和有益。这些发现表明，简单、低成本的策略可以有效减少跨种族性能差距，提高预测神经影像的公平性，为未来的神经影像预测生物标志物提供了一条切实可行的前进道路。

重要声明：大规模神经影像数据集日益使机器学习模型能够预测认知和临床结果；然而，这些数据集往往在民族/种族上不平衡。因此，预测模型往往对代表性不足的人群泛化能力较差。我们证明，在80种MRI表型中，一类统称为监督域自适应的机器学习方法可以大幅减少基于神经影像的认知预测中的跨种族差异，即使只有有限数量的代表性不足群体数据可用。在评估的方法中，平衡加权取得了最佳性能，同时保持较低的计算成本。总之，这些发现为在现实世界的民族/种族不平衡条件下提高基于神经影像的机器学习的公平性和泛化能力提供了一个实用且可扩展的框架。

## Abstract
Machine-learning models are increasingly used to predict cognitive and clinical outcomes from neuroimaging data, yet challenges in fairness and generalizability remain. Large-scale datasets are often racially and ethnically imbalanced, leading to systematic performance disparities, with models typically achieving higher accuracy for majority populations represented in the training data. In this study, we evaluated whether supervised domain adaptation methods--including balanced weighting, two-stage TrAdaBoost, feature augmentation with SrcOnly prediction, and linear interpolation--can mitigate these biases. Using the ABCD dataset, we assessed whether models trained on 80 MRI measures from White American participants could generalize more effectively to African American participants. All domain adaptation methods reduced prediction error for African American participants, particularly for MRI modalities with large baseline disparities (e.g., structural MRI), while offering limited improvements where initial gaps were smaller (e.g., functional connectivity). Among the approaches, balanced weighting performed best and remained stable and beneficial even when only 10 African American participants were used to adapt the original model trained exclusively on White American participants. These findings suggest that simple, low-cost strategies can effectively reduce cross-ethnic performance gaps and improve equity in predictive neuroimaging, offering a practical path forward for future neuroimaging predictive biomarkers.

Significant StatementLarge-scale neuroimaging datasets increasingly enable machine-learning models to predict cognitive and clinical outcomes; however, these datasets are often ethnically/racially imbalanced. As a result, predictive models tend to generalize poorly to underrepresented populations. We demonstrate that, across 80 MRI phenotypes, a class of machine-learning approaches collectively known as supervised domain adaptation can substantially reduce cross-ethnicity disparities in neuroimaging-based cognitive prediction, even when only limited data from underrepresented groups are available. Among the methods evaluated, balanced weighting achieved the best performance while maintaining low computational cost. Together, these findings provide a practical and scalable framework for improving fairness and generalizability in neuroimaging-based machine learning under realistic conditions of ethnic/racial imbalance.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **研究动机与背景**：基于神经影像（MRI）的机器学习模型在预测认知与临床结局方面展现潜力，但大规模训练数据集常在民族/种族上严重失衡。这导致模型对多数群体（如白人）预测准确，对代表性不足的少数群体（如非裔美国人）泛化性能骤降，产生系统性公平性鸿沟。
*   **核心问题**：如何以低成本、易实施的方式，缓解因数据种族不平衡造成的跨民族预测误差，使预测模型在少数族裔上也能保持较高效用。
*   **整体含义**：验证了**监督域自适应**方法能够在仅有极少量目标人群数据的情况下，有效减轻神经影像认知预测中的种族偏差，为构建更公平、泛化性更强的神经影像预测标志物提供了务实路径。

### 2. 论文提出的方法论
*   **核心思想**：利用少量带标签的**目标域**（非裔美国人群体）样本，对已在大量**源域**（美国白人群体）数据上预训练的模型进行迁移调整，最小化域偏移带来的性能损失。论文并非提出全新方法，而是**系统评估**四类可行的监督域自适应策略。
*   **关键技术方法**：
    *   **平衡加权**：对训练样本（源域与目标域）施加重加权，调整域间分布差异，使损失函数更关注目标域或域间平衡。
    *   **两阶段 TrAdaBoost**：基于实例迁移的集成方法，通过迭代调整样本权重，强化对目标域有帮助的源域样本，抑制有害样本。
    *   **结合仅源预测的特征增强**：将源域模型对目标样本的预测结果作为额外的特征拼接到原始特征空间，辅助模型学习跨域关系。
    *   **线性插值**：在源域模型参数与仅用少量目标域数据训练的模型参数之间进行线性组合，求得一种折中的参数解。
*   **未公开细节**：论文摘要未给出各方法的数学公式或具体算法流程，仅从概念层面描述了这些策略。从实验结论看，**平衡加权**因其简洁与稳健性被重点推荐。

### 3. 实验设计
*   **使用数据集**：**ABCD (Adolescent Brain Cognitive Development) 研究**数据集。
*   **预测变量与模态**：基于 **80 项 MRI 指标**，覆盖多种影像模态（文中明确对比了基线差距较大的**结构磁共振成像**与差距较小的**功能连接**等）。
*   **场景与基准**：
    *   **源域**：美国白人参与者数据训练的预测模型。
    *   **目标域**：非裔美国参与者。
    *   **对比基准**：模型在无任何自适应处理下，直接对非裔美国人进行预测的误差（即直接迁移）。
*   **对比方法**：上述四种监督域自适应方法相互对比，并与不做自适应的基准对比。同时评估了**目标域可用样本数量极度受限**（如仅 10 人）条件下的性能变化。

### 4. 资源与算力
*   所提供的元数据与摘要文本中**未明确提及 GPU 型号、数量、训练总时长或具体硬件配置**。仅定性指出平衡加权等最佳方法具备**低计算成本**的特性，表明其训练开销可控，无需大规模算力支撑。

### 5. 实验数量与充分性
*   **实验覆盖范围**：实验覆盖 **80 种 MRI 表型**，且明确区分了不同模态特性（如结构像与功能连接）下的效果差异，构成了很大的测试集合。
*   **灵敏度测试**：专门设计了**目标域样本量敏感性实验**（考察仅使用 10 个目标个体进行自适应的效果），检验方法在数据极度稀缺下的鲁棒性。
*   **充分性与客观性评估**：从摘要展示的框架看，实验设计逻辑闭环（覆盖多模态、多方法、变化数据量），选取的数据集（ABCD）和问题（种族迁移）具有公认的社区关注度，评价指标明确（预测误差），实验具备较好的**客观性与充分性**。但受限于当前为摘要信息，无法判定是否存在详细的消融实验（如剥离各模块）或统计显著性检验细节。

### 6. 论文的主要结论与发现
*   **一致改善**：所有监督域自适应方法均能降低对非裔美国参与者的预测误差。
*   **模态差异化**：在初始种族预测差距较大的模态（如结构 MRI）上，改善效果尤为显著；而在初始差距较小的模态（如功能连接）上，提升空间有限。
*   **最佳策略**：**平衡加权**在各项评估中表现最优，仅需极少量目标个体（如 10 人）即可稳定且有效地缩小跨种族性能差距。
*   **现实意义**：低成本、易部署的域适应技术足以成为解决神经影像公平性危机的有效途径，无需翻天覆地的算法变革。

### 7. 优点
*   **实用导向极强**：聚焦于**数据极度匮乏**的真实世界困境，验证了仅需 10 个目标样本即能带来提升，打破了“少数群体数据太少无法建模”的悲观假设。
*   **方案可复现、低成本**：推荐的平衡加权方法计算开销小，易于其他研究者快速复现和部署。
*   **模态层面细粒度分析**：并非笼统给出结论，而是区分结构像与功能连接，揭示了域适应疗效与**基线偏差大小**的相关性，为针对性优化提供了依据。
*   **框架式对比**：系统化地比较了四类具有代表性的实例/特征/参数自适应方法，为领域提供了清晰的方法选择基准。

### 8. 不足与局限
*   **人群与任务泛化性未验证**：仅在 ABCD 青少年队列上测试了白人至非裔的单一迁移路径，结论向其他年龄层、其他少数族裔或临床疾病预测任务的推广性存疑。
*   **方法细节透明性不足**：当前文本缺失各方法的具体实现细节、超参数设置和公式推导，不利于完全复现。
*   **公平性度量单一**：仅以预测误差（准确率）作为衡量标准，未联合使用如机会均等、人口平等、校准度等多维度算法公平性指标，可能掩盖残存的系统性偏差。
*   **认知结局的限定**：未明确认知功能的具体评分标准（如流体智力、晶体智力或总分），不同认知域的迁移难度可能存在差异。
*   **源域局限**：仅以“白人”作为源域，未探讨混合多族裔源域或者从少数族裔向白人迁移的场景。

（完）
