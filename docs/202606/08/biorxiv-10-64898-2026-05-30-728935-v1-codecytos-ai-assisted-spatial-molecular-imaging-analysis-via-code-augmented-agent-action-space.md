---
title: "CodeCytos: AI-assisted spatial molecular imaging analysis via code-augmented agent action space"
title_zh: CodeCytos：通过代码增强的智能体动作空间实现AI辅助的空间分子成像分析
authors: "Vo, H. Q., Ly, S. T., Wan, Z., Nguyen, A.-V., Zhao, H., Sheng, J., Wong, S. T. C., Nguyen, H. V."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.30.728935v1.full.pdf"
tags: ["query:med-lifelong"]
score: 10.0
evidence: AI辅助空间分子成像分析
tldr: 传统组织图像分析软件需大量手动操作，难以无缝集成代码自动化，且仅支持预定义特征，限制了复杂空间组织研究的效率与灵活性。为此，我们提出CodeCytos——一个基于编码的推理代理框架，通过自然语言指令生成并执行代码，实现对空间分子成像数据的动态、可编程交互，突破定制分析瓶颈。在额叶皮层、非小细胞肺癌、胰腺和扁桃体四个专家标注数据集上，模拟生物学家仅给出简单提问的无指令场景，并引入领域无关的少量编码示例，显著提升性能。同时，基准测试多种强编码大语言模型，结果表明CodeCytos优于基线，展示出代码代理在自定义特征探索中的潜力，有望加速生物标志物发现与分析自动化。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统软件手动依赖强、代码集成差且特征固定，制约了大规模空间组织研究的可扩展性与定制化分析。
method: 提出CodeCytos框架，通过代码增强推理代理实现自然语言驱动的动态可编程空间分子数据交互。
result: 在四种组织数据集上，以最小提示和领域无关编码示例显著超越基线，并验证了强编码LLM的有效性。
conclusion: CodeCytos展现了代码代理在空间分子成像分析中的自动化与定制潜力，可加速生物标志物发现。
---

## 摘要
传统的组织图像分析软件为细胞分析提供了基础能力，包括分割、基本形态特征提取和空间组织分析。然而，这些工具通常需要人工干预，并且与代码驱动的自动化集成不足，限制了复杂空间组织研究的效率和可扩展性。此外，它们在自定义分析方面灵活性有限，通常只支持一组固定的预实现空间细胞特征。为了解决这些限制，我们提出了CodeCytos，一个基于编码的推理智能体框架，能够动态、可编程地与空间分子成像数据进行交互，以提高自动化和定制化程度。CodeCytos旨在简化自定义空间细胞特征的探索，并适应多样化的研究需求。我们通过四个由专家整理的不同组织类型数据集（额叶皮层、非小细胞肺癌、胰腺和扁桃体）的案例研究展示了其实用性。我们在一个现实的最小提示设置下评估CodeCytos，生物科学家提出简单问题，没有特定任务的指令或空间细胞分析的背景信息，并对多个具有强大编码能力的LLM主干进行基准测试。我们进一步表明，结合定制的、领域无关的少样本上下文编码推理示例（从空间分析领域外随机抽取的演示）可以显著提高性能，而无需昂贵的专家制定的领域内演示。总体而言，CodeCytos优于基线方法，突显了代码操作智能体在协助空间分子成像中的自定义特征探索和加速生物标志物发现方面的潜力。

## Abstract
Conventional tissue image analysis software provides foundational capabilities for cellular analysis, including segmentation, basic morphological feature extraction, and spatial organization analysis. However, these tools often require manual intervention and are not well integrated with code-driven automation, limiting efficiency and scalability for complex spatial tissue studies. In addition, they offer limited flexibility for custom analyses, as they typically support only a fixed set of pre-implemented spatial cellular features. To address these limitations, we propose CodeCytos, a coding-based reasoning agent framework that enables dynamic, programmable interaction with spatial molecular imaging data, to improve automation and customization. CodeCytos is designed to streamline the exploration of custom spatial cellular features and adapt to diverse research needs. We demonstrate its utility through case studies on four expert-curated datasets from distinct tissue types: frontal cortex, non-small-cell lung cancer, pancreas, and tonsil. We evaluate CodeCytos under a realistic minimal prompt setting, where bioscientists pose simple questions without task-specific instructions or contextual information about spatial cellular analysis, and benchmark multiple LLM backbones with strong coding capabilities. We further show that incorporating tailored, domain-agnostic few-shot in-context coding-reasoning examples (randomly sampled demonstrations outside the spatial analysis domain) can substantially improve performance without requiring costly, expert-crafted in-domain demonstrations. Overall, CodeCytos outperforms baseline approaches, highlighting the potential of code-action agents to assist with custom feature exploration in spatial molecular imaging and to accelerate biomarker discovery.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

- **研究背景**：空间分子成像技术可同时捕捉组织内细胞的空间分布和分子特征，是理解肿瘤微环境、神经环路等复杂生物学问题的重要工具。
- **传统工具的痛点**：
  - 分析软件（如QuPath、ImageJ等）依赖大量手动操作，难以无缝集成编程自动化。
  - 仅提供预定义的固定空间特征（如最近邻距离、聚类系数等），无法灵活支持研究者自定义的新型空间指标。
  - 扩展性差，面对大规模、高通量图像时效率低下。
- **整体含义**：论文旨在打破“手动操作—固定特征”的瓶颈，提出一种基于代码生成与执行的智能体框架 **CodeCytos**，让生物学家通过自然语言就能自动完成高度定制化的空间分析，从而加速生物标志物发现与空间组织研究。

### 2. 方法论

- **核心思想**：将空间分子成像分析转化为“自然语言问题 → 代码生成与执行 → 结果返回”的闭环。智能体以代码为行动工具（code-augmented agent action space），动态生成并运行数据分析代码，实现对数据的可编程交互。
- **关键技术细节**：
  - **输入**：用户用自然语言提出简单问题（如“肿瘤区域中 CD8+ T 细胞与癌细胞的平均距离是多少？”），无需提供任务说明或领域背景。
  - **代码生成**：底层大语言模型（LLM）接收到问题后，生成一段可直接执行的代码（如Python脚本），用于从数据中提取、计算所需的空间特征。
  - **代码执行**：智能体在安全的执行环境中运行代码，获取中间或最终结果。
  - **上下文增强**：通过加入 **领域无关的少样本示例**（从空间分析领域外随机抽取的代码-推理对），在不依赖昂贵专家标注的情况下显著提升推理与代码生成的正确性。
- **算法流程**（文字描述）：
  1. 用户提问 → 2. 拼接最小提示（prompt）与少量非领域示例 → 3. LLM生成代码 → 4. 执行代码操作结构化数据 → 5. 若出错或需要多步推理，智能体可在代码中嵌入自省与纠错循环 → 6. 返回最终答案。
- **公式/技术细节**：论文原文未给出具体数学公式，主要创新在于框架设计和人机交互范式。

### 3. 实验设计

- **数据集与场景**：
  - 四种不同组织类型的数据集：额叶皮层（神经）、非小细胞肺癌（肿瘤）、胰腺、扁桃体（淋巴）。
  - 所有数据集均有专家整理和标注，确保评估的可靠性。
- **Benchmark 与对比方法**：
  - **基准方法**：未在摘要中具体命名，推测为传统图像分析软件的手动操作或基于固定特征的预置分析流程。
  - **LLM backbone 对比**：评估了多种具有强编码能力的大语言模型作为 CodeCytos 的推理核心，以考察不同模型对任务效果的影响。
  - **消融实验**：对比了是否加入“领域无关的少样本上下文示例”的性能，验证该策略的有效性。
- **评估设置**：采用“最小提示”设定，即生物科学家仅给出简单问题，不提供任何任务特定指引或空间细胞分析的上下文，仿真真实使用场景。

### 4. 资源与算力

- 文中 **未明确提及** 具体的 GPU 型号、数量、训练时长或推理成本。
- 可能的原因：本文主要着眼于框架设计与应用验证，且摘要篇幅有限；若需详细信息，应查看论文全文。

### 5. 实验数量与充分性

- **实验组数**（基于摘要推断）：
  - 在 4 个不同组织数据集上分别进行验证。
  - 对多个 LLM backbone 进行基准测试（数量未具体说明，至少2种以上）。
  - 是否加入少样本示例的消融实验（2种设置）。
- **充分性分析**：
  - 覆盖了神经、肿瘤、消化和淋巴等关键组织类型，具有一定的生物学多样性。
  - 对比了不同的底层 LLM，体现了方法的可插拔性。
  - 消融实验验证了核心增强策略的作用。
  - 局限性：摘要未报告具体指标、统计检验方法以及误差范围；基线方法的具体实现也未详述，因此从摘要难以判断实验是否完全客观、公平。若要对实验充分性做严谨判断，需查阅原文全部实验细节。

### 6. 主要结论与发现

- CodeCytos 在所有评估设定下 **均优于基线方法**，证明了代码增强的智能体在自定义空间特征探索中的有效性。
- 引入 **随机采样的、领域无关的少样本代码推理示例** 可大幅提升性能，避免了对昂贵的专家手工演示的依赖。
- 强编码能力的大语言模型作为 backbone 时，CodeCytos 表现出色，说明工具的健壮性依赖于底层代码生成模型的品质。
- 整体而言，代码操作代理有望自动化并加速空间分子成像中的生物标志物发现和定制化分析流程。

### 7. 优点（亮点）

- **动态可编程性**：突破传统软件仅支持固定特征的局限，用户可通过自然语言自由定义任意空间特征。
- **低使用门槛**：最小提示设置使生物学家无需编程背景或空间分析先验知识即可使用。
- **高效的少样本策略**：用领域外示例替代昂贵的领域内专家演示，大幅降低构建成本，同时保持高性能。
- **模型无关性**：框架可搭配多种强编码 LLM，适应快速迭代的模型生态。
- **真实场景贴近**：以简单自然语言提问作为输入，仿真实际生物学家的工作方式。

### 8. 不足与局限

- **组织类型覆盖有限**：仅在四种组织上验证，可能缺乏对其他复杂组织（如骨、脂肪、胚胎等）的普适性论证。
- **方法描述不完整**：摘要未给出具体的评价指标、基线方法名称、统计检验等，难以独立判断实验的严谨性。
- **对 LLM 编码能力的依赖**：若底层模型生成的代码存在逻辑错误或安全性风险，可能影响分析结果的可靠性。
- **无错误处理细节**：未知代码执行失败时的重试机制或人工介入方式，实际落地可能存在鲁棒性问题。
- **资源与效率未量化**：未说明运行时间、计算成本，对于大规模数据集的可扩展性有待验证。

（完）
