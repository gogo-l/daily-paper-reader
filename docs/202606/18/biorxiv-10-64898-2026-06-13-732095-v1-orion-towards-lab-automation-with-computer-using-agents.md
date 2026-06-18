---
title: "Orion: Towards Lab Automation with Computer-Using Agents"
title_zh: Orion：迈向实验室自动化的计算机使用智能体
authors: "Ma, C., Trinh, L., Bucci, M., Regev, A., Wang, H."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.13.732095v1.full.pdf"
tags: ["query:med-lifelong"]
score: 8.0
evidence: 用于生物医学图像分析和解释的AI智能体
tldr: "生物医学图像分析依赖繁琐的人工软件操作与知识整合，限制了实验室自动化。Orion代理结合大语言模型、终端执行与GUI控制，实现多步推理的端到端分析。在检索任务中准确率超90%，学会使用CellProfiler和QuPath，并在100小时自主探索中生成22个合理机制假说。该工作展示了计算机使用代理可扩展实验室自动化，提供从实验数据到定量报告与假说的审计路线。"
source: biorxiv
selection_source: fresh_fetch
motivation: 生物医学实验室的计算工作流仍依赖人工操作专业软件与跨源知识整合，效率低且难以扩展。
method: Orion代理融合大语言模型、终端执行、GUI操作与自适应多步推理，在共享环境中自动化图像分析解释。
result: "Orion在数据库和文献检索中准确率超90%，掌握CellProfiler与QuPath工具，并自主产出22个合理生物学假说。"
conclusion: 计算机使用代理能实现端到端实验室自动化，为从实验图像到假说的过程提供可扩展、可审计的路径。
---

## 摘要
实验室发现越来越依赖将实验数据连接到分析、解释和后续假设的计算工作流。然而，这些工作流仍受到劳动密集型专用软件使用、通过图形用户界面进行视觉检查以及跨多个来源的知识整合的限制。在此，我们介绍Orion，一种用于生物医学图像分析和解释的计算机使用人工智能智能体，它通过自动化实验室工作的这一计算层，向实验室自动化迈进。Orion将大型语言模型与终端执行、GUI控制和共享计算环境中的自适应多步推理相结合。它可以检查视觉数据，操作标准科学软件，挖掘网络资源，并进行端到端的分析和解释工作流，无需定制的软件集成。在一系列基准测试中，Orion在生物医学数据库和文献检索任务上实现了超过90%的准确率，学会了使用流行工具CellProfiler和QuPath分别进行细胞和组织图像的定量分析，并促进了实验成像数据的自主发现。在对大规模扰动成像数据集进行100小时的自主探索中，Orion生成了52份研究报告，其中人类科学家评审优先选出了22个合理的机制假设。这些结果表明，计算机使用的人工智能智能体可以大幅扩展实验室自动化的范围，提供一条从实验成像数据到定量分析、报告和生物学合理假设的可扩展且可审计的途径。

## Abstract
Laboratory discovery increasingly depends on computational workflows that connect experimental data to analysis, interpretation and follow-up hypotheses. Yet these workflows remain constrained by labor-intensive use of specialized software, visual inspection through graphical user interfaces, and integration of knowledge across multiple sources. Here, we present Orion, a computer-using AI agent for biomedical image analysis and interpretation that moves towards lab automation by automating this computational layer of laboratory work. Orion combines large language models with terminal execution, GUI control and adaptive multi-step reasoning in a shared computing environment. It can inspect visual data, operate standard scientific software, mine web resources and conduct end-to-end analysis and interpretation workflows without requiring bespoke software integrations. Across benchmarks, Orion achieved over 90% accuracy on biomedical database and literature retrieval tasks, learned to use the popular tools CellProfiler and QuPath for quantitative analysis of cellular and tissue images, respectively, and facilitated autonomous discovery in experimental imaging data. In 100 hours of autonomous exploration of a large-scale perturbation imaging dataset, Orion generated 52 research reports, of which human scientist review prioritized 22 plausible mechanistic hypotheses. These results show that computer-using AI agents can substantially expand the reach of laboratory automation, providing a scalable and auditable route from experimental imaging data to quantitative analysis, reports and biologically grounded hypotheses.