---
title: Agent Workflow Memory
title_zh: 智能体工作流记忆
authors: "Zora Zhiruo Wang, Jiayuan Mao, Daniel Fried, Graham Neubig"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NTAhi2JEEE"
tags: ["query:continual"]
score: 7.0
evidence: 从过去经验中学习可重用任务工作流以指导未来行动
tldr: 本文提出Agent Workflow Memory (AWM) 方法，使语言智能体能从过去经验中归纳出常用工作流，并在后续任务中利用这些工作流指导行动。AWM支持离线从训练示例归纳或在线从测试查询中即时构建。在Mind2Web和WebArena等网页导航基准上，AWM显著提升了长时程任务的完成率。该工作为智能体通过累积经验实现自我进化提供了有效记忆机制。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 703, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 864, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1417, \"height\": 709, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1485, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1247, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 841, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 512, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 883, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 797, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 834, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1058, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1594, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1592, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 890, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 791, \"height\": 206, \"label\": \"Table\"}]"
motivation: 现有语言智能体在长时程复杂任务中表现不佳。
method: 提出AWM，从历史经验中归纳可重用工作流，为智能体提供行动指导。
result: 在网页导航基准上显著提升长时程任务的成功率。
conclusion: 为智能体积累和利用经验实现自我改进开辟了新方向。
---

## Abstract
Despite the potential of language model-based agents to solve real-world tasks such as web navigation, current methods still struggle with long-horizon tasks with complex action trajectories. In contrast, humans can flexibly solve complex tasks by learning reusable task workflows from past experiences and using them to guide future actions. To build agents that can similarly benefit from this process, we introduce Agent Workflow Memory (AWM), a method for inducing commonly reused routines, i.e., workflows, and selectively providing workflows to the agent to guide subsequent generations. AWM flexibly applies to both offline and online scenarios, where agents induce workflows from training examples beforehand or from test queries on the fly. We experiment on two major web navigation benchmarks — Mind2Web and WebArena — that collectively cover 1000+ tasks from 200+ domains across travel, shopping, and social media, among others. AWM substantially improves the baseline results by 24.6% and 51.1% relative success rate on Mind2Web and WebArena while reducing the number of steps taken to solve WebArena tasks successfully. Furthermore, online AWM robustly generalizes in cross-task, website, and domain evaluations, surpassing baselines from 8.9 to 14.0 absolute points as train-test task distribution gaps widen.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义

- **研究动机**：当前基于语言模型（LM）的智能体在完成长时程、动作轨迹复杂的真实世界任务（如网页导航）时，仍面临成功率低、泛化能力差的问题。
- **核心思想**：模仿人类从过往经历中抽象出可复用的任务流程（workflow）并以此指导未来行动的能力，提出“智能体工作流记忆”机制，使智能体也能从历史经验中提取高频子程序（即工作流），并在后续任务中调用这些工作流来提升决策效率与准确率。
- **整体含义**：赋予智能体一个可动态增长、自我进化的记忆模块，实现持续学习与跨任务泛化，而不仅仅是依赖固定示例的静态提示。

## 2. 论文提出的方法论

- **工作流表示**：每个工作流包含两部分：  
  - **工作流描述**：用自然语言概括该子程序的目标（例如“按名称查找地点”）。  
  - **工作流轨迹**：一系列步骤，每步包含环境状态的自然语言描述、推理过程和可执行动作（如`click(id)`），其中具体实体被替换为变量名（如`{product-name}`）以提升抽象性和通用性。
- **工作流归纳**：  
  - 借助语言模型（如GPT-4o）从若干条成功完成任务的经验中抽取共同子程序，生成抽象工作流。  
  - 支持**离线**和**在线**两种模式：  
    - **离线模式**：利用标柱好的一组示例预先归纳工作流，推理时统一注入记忆。  
    - **在线模式**：无需标注数据，按顺序处理测试查询，对每次的预测轨迹用独立评估器（基于LM）判断是否成功，若成功则即时归纳成工作流并加入记忆，供后续任务使用。
- **记忆集成**：将工作流追加到智能体原有的动作空间记忆（系统提示）中，在每一步决策时作为上下文指导。

## 3. 实验设计

- **数据集与基准**：  
  - **WebArena**：812个网页导航任务，涉及购物、社交论坛、代码协作、内容管理等5个网站，支持基于客观执行结果的评价。  
  - **Mind2Web**：包含1000+任务和200+领域，提供跨任务、跨网站、跨域的泛化测试分割。
- **对比方法**：  
  - WebArena：BrowserGym（当时最佳无人工知识方法）、SteP（利用人工编写的工作流）、AutoEval、WebArena原始基线等。  
  - Mind2Web：MindAct、Synapse（基于轨迹示例的方法）等。
- **评测指标**：任务成功率（成功完成的任务比例）、执行步数、元素选择准确率、动作F1、步级成功率等。

## 4. 资源与算力

- 文中未明确提及使用的GPU型号、数量或训练时长。  
- 所有实验均基于API调用大语言模型（GPT-4o、GPT-3.5-turbo），不涉及模型微调，主要计算开销来自推理时的API请求。论文汇报了AWM额外引入的评估与归纳模块仅增加约10.8%的token消耗，但未给出硬件的详细说明。

## 5. 实验数量与充分性

- 实验覆盖充分且多样：  
  - 在两大主流基准上，分别运行了主实验（表1/表3）以及多组泛化实验（跨模板、跨网站、跨域）。  
  - 进行了大量消融与对比分析：规则诱导 vs. LM诱导工作流；代码 vs. 自然语言工作流格式；环境状态用描述 vs. 过滤HTML；在线与离线混合模式；示例排序影响；工作流作为动作扩展（AWM​AS）等。  
- 实验设计客观、公平：所有基线均使用相同模型及同等元素过滤设置；AWM无论在线还是离线均未使用任何人工设计的工作流，真正实现了零人工监督学习。

## 6. 论文的主要结论与发现

- AWM显著提升长时程任务的成功率：在Mind2Web上相对提升24.6%，在WebArena上提升51.1%（绝对值从23.5%提高到35.5%），同时平均执行步数减少。
- 在线AWM无需任何训练数据，仅靠即时归纳即可达到与离线版相当的甚至更优的泛化能力，尤其在训练‑测试分布差异加大时（跨域场景）优势更明显（提升8.9‑14.0个百分点）。
- 抽象的子程序工作流比检索完整示例轨迹更有效，因为它避免了绑定实例细节，减少了元素选择的偏差。
- 即使面对非重叠任务模板（跨模板泛化），AWM也能可靠地提升性能，说明工作流具有跨任务的通用性。

## 7. 优点

- **灵活性与通用性**：同一框架同时支持离线与在线，无需标注数据即可运行在线持续学习。
- **高效学习**：仅需数十个示例（如图4所示）就能快速收敛，形成“雪球效应”，随记忆增长持续提升。
- **可解释与可组合**：工作流以自然语言描述，可逐步组合成更复杂的流程（如从“查找地点”到“获取邮编”），清晰展示技能堆叠过程。
- **实验扎实**：在两个高影响力基准上进行了全面的对比和消融，分析了多种变体，结论可信。

## 8. 不足与局限

- **依赖评估器**：在线模式需要一个可靠的自动评估模块来判断任务成功与否，若评估器失效可能引入错误工作流。
- **动作执行灵活性不足**：工作流被抽象为固定步骤序列，面对动态环境（如弹出下拉选项）时无法实时应变，影响某些任务的成功率。
- **语言模型自身限制**：工作流归纳质量受限于底层LM，有时仍会产生过于具体或重叠的工作流。
- **计算开销**：虽然增量成本不大（约10.8%），但对于大规模实时系统仍可能增加延迟。
- **领域覆盖**：仅在网页导航任务上验证，扩展到其它数字环境（如移动APP、机器人）的效果尚待检验。

（完）
