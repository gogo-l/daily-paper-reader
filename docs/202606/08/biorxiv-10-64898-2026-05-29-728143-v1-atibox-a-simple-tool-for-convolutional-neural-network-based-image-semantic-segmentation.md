---
title: "ATI_Box: A Simple tool for convolutional neural network-based image semantic segmentation"
title_zh: ATI_Box：一个基于卷积神经网络的图像语义分割简易工具
authors: "Przygodzki, T."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.29.728143v1.full.pdf"
tags: ["query:med-lifelong"]
score: 6.0
evidence: 为生物医学研究中的显微图像分析提供基于CNN的语义分割工具
tldr: 显微图像定量分析依赖深度学习，但非编码人员难以应用CNN。ATI_Box平台集成标注、存储、训练、评估与批量分析，基于U-Net（ResNet编码器）实现端到端语义分割，无需编码即可完成全流程。在实验室案例中成功验证，简化了训练过程，兼具教育功能，为生物医学研究者提供实用工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 生物医学研究者缺乏编码技能，难以运用卷积神经网络进行图像语义分割。
method: ATI_Box整合Label Studio标注、MinIO存储、U-Net（ResNet编码器）训练、像素与对象级评估及批量分析。
result: 平台在实验室实例中展示了自动化对象计数和覆盖面积量化等实用功能。
conclusion: 该工具有效降低技术门槛，可作为语义分割分析工具和教学平台。
---

## 摘要
显微图像的定量分析已成为基础生物学和生物医学研究的标准方法。深度学习为此提供了强大的工具，促进了这一过程。然而，对于缺乏基本编程技能的研究人员来说，将深度学习实际应用于图像分析可能较为困难。这主要是由于非编码解决方案数量有限，尤其是在卷积神经网络（CNN）领域。这种稀缺性可以用以下悖论来解释：CNN的训练是一个相对复杂的过程。熟悉这一过程的研究人员也具备足够的技能来编写CNN实现的完整流水线，从标注、模型训练、评估到实验室实践中的使用。任何能被更广泛的、不熟悉CNN概念的研究人员接受的替代方案，都不可避免地导致整个过程的简化，尤其是训练步骤。这种简化反过来又可能限制该工具解决特定问题的能力。然而，作者认为，可以在复杂性和简单性之间找到某种折衷，足以解决基础生物学和生物医学研究领域的一些基本问题。为了应对这一挑战，作者提出了ATI_Box（Annotation, Training, Inference in One Box），一个统一的、面向用户的端到端图像语义分割平台。该系统将数据标注、存储、模型训练、评估和定量分析整合到一个工作流程中，显著简化了模型开发过程。图像和标注数据通过兼容S3的对象存储系统（MinIO）进行管理，实现了可扩展且透明的数据处理。标注过程通过Label Studio实现。模型训练基于卷积神经网络U-Net架构，以ResNet作为编码器。模型评估在训练时保留的真实标注数据集上进行，提供像素级和对象级的评估指标。批处理分析模式能够自动量化模型预测结果，如对象计数和覆盖面积。该平台的可用性通过实验室实践中的示例进行了展示。该平台有意去除了模型调优功能，因为它面向的是不熟悉深层机器学习概念的用户。同时，模型训练的基本功能（如定义训练轮数、保存和部署训练好的模型版本）易于使用，使用户能够进行一些基础的分析实验。因此，该平台不仅可作为分析工具，还可作为解释语义分割过程实践基础的教育解决方案。

## Abstract
Quantitative analysis of microscopic images has become a standard in basic biological and biomedical research. Deep machine learning provided a powerful tool facilitating this process. However, practical adoption of deep machine learning to image analysis may be difficult for a researcher who lacks basic coding skills. This is caused by a limited number of non-coding solutions, specifically in the domain of convolutional neural networks (CNNs). This scarcity may be explained by the following paradox. Training of CNNs is a relatively complex process. Researchers who are familiar with this process are also skilled enough to code the full pipeline of CNN implementation from annotation, through model training and evaluation to its usage in laboratory practice. Any kind of an alternative solution, acceptable by a broader group of researchers who are unfamiliar with CNN concepts, must inevitably result in simplification of the entire process, specifically the training step. Such simplification in turn may lead to limitation to solve specific problems by such a tool. Author believes however, that some compromise may be found between complexity and simplicity that would be sufficient to solve some basic problems in the field of basic biological and biomedical research.

To address this challenge, author proposes ATI_Box (Annotation, Training, Inference in One Box), a unified, user-oriented platform for end-to-end image semantic segmentation. The system integrates data annotation, storage, model training, evaluation, and quantitative analysis into a single workflow, significantly simplifying the model development process. Image and annotation data are managed through an S3-compatible object storage system (MinIO), enabling scalable and transparent data handling. Annotation process is implemented through Label Studio. Model training is based on convolutional neural network U-Net architecture with ResNet as an encoder. Model evaluation is performed on ground-truth dataset held-out during training and provides pixel-level and object-level evaluation metrics. Batch analysis mode enables automated quantification of model predictions such as object counts and coverage areas. The usability of the platform was presented on examples from laboratory practice.

The platform is intentionally devoid of model-tuning capabilities as it is addressed to users unfamiliar with profound machine learning concepts. At the same time, accessibility of such basic features of model training as definition of epochs number or saving and implementing of trained model versions enables one to perform some basic analytical experiments. As such, the platform may serve not only as an analytical tool but also as an educational solution to explain practical basics of semantic segmentation process.