---
title: Agent Workflow Memory
title_zh: 智能体工作流记忆
authors: "Zora Zhiruo Wang, Jiayuan Mao, Daniel Fried, Graham Neubig"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=NTAhi2JEEE"
tags: ["query:continual"]
score: 7.0
evidence: AWM从过往经验中归纳可复用工作流，使智能体在长期任务中持续适应和改进。
tldr: 面对语言智能体在长时程任务中表现不佳的问题，Agent Workflow Memory (AWM) 提出了一种从过去经验中学习可重用工作流并选择性提供给智能体以指导后续行动的方法。AWM 在离线预训练和在线推理中均有效，显著提升了在网页导航等长序列任务上的成功率。该工作为增强智能体持续学习和适应能力提供了实用的记忆机制。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 867, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 860, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 703, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 864, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-ntahi2jeee/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1417, \"height\": 709, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1485, \"height\": 425, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1247, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 841, \"height\": 330, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1422, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 512, \"height\": 169, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 883, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 797, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 834, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1058, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1594, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1592, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 890, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-ntahi2jeee/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 791, \"height\": 206, \"label\": \"Table\"}]"
motivation: 现有语言智能体在处理长时程复杂任务时缺乏有效利用过往经验的能力。
method: 提出AWM方法，从训练示例或在线查询中归纳常用工作流，并在生成时选择性地提供给智能体。
result: 在两个网页导航基准测试上，AWM显著提高了长序列任务的成功率。
conclusion: 工作流记忆机制有效促进了智能体的持续学习和长期任务解决能力。
---

## Abstract
Despite the potential of language model-based agents to solve real-world tasks such as web navigation, current methods still struggle with long-horizon tasks with complex action trajectories. In contrast, humans can flexibly solve complex tasks by learning reusable task workflows from past experiences and using them to guide future actions. To build agents that can similarly benefit from this process, we introduce Agent Workflow Memory (AWM), a method for inducing commonly reused routines, i.e., workflows, and selectively providing workflows to the agent to guide subsequent generations. AWM flexibly applies to both offline and online scenarios, where agents induce workflows from training examples beforehand or from test queries on the fly. We experiment on two major web navigation benchmarks — Mind2Web and WebArena — that collectively cover 1000+ tasks from 200+ domains across travel, shopping, and social media, among others. AWM substantially improves the baseline results by 24.6% and 51.1% relative success rate on Mind2Web and WebArena while reducing the number of steps taken to solve WebArena tasks successfully. Furthermore, online AWM robustly generalizes in cross-task, website, and domain evaluations, surpassing baselines from 8.9 to 14.0 absolute points as train-test task distribution gaps widen.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将基于您提供的论文内容，使用中文并以 Markdown 格式对该论文进行结构化、深入、客观的总结。

### **论文核心问题与整体含义**

*   **研究动机**：当前基于语言模型的智能体在解决如网页导航等现实世界任务时潜力巨大，但在处理具有复杂动作轨迹的长时程任务时仍表现不佳。它们通常孤立地解决每个任务，无法从过去的成功或失败经验中学习并适应。
*   **核心问题**：人类能通过从过往经验中学习可复用的任务“工作流”来灵活解决复杂问题，而现有智能体缺乏这种提取和应用可复用例程的能力。这导致其缺乏鲁棒性，无法有效应对任务上下文或环境的变化。
*   **整体含义**：论文旨在赋予语言智能体类似于人类的学习能力，即从经验中抽象出通用的、可复用的工作流，并以此指导未来的行动，从而提升其在长时程、复杂任务上的表现和持续适应能力。

### **论文提出的方法论：Agent Workflow Memory (AWM)**

*   **核心思想**：AWM 是一种让智能体归纳并提供“工作流”的记忆机制。一个“工作流”代表一个带有通用例程的子目标，它从可用的动作轨迹中提取，捕捉了解决任务所需的最核心、最可复用的技能。
*   **工作流表示**: 一个工作流包含两部分：
    *   **工作流描述**: 一个自然语言句子，概括工作流的高级目标或功能（例如：“通过名称查找一个地点”）。
    *   **工作流轨迹**: 一系列完成该目标的步骤。每个步骤包含环境状态的自然语言描述、推理过程和可执行的动作。工作流设计强调**细粒度**（提取的是子任务，而非完整任务）和**抽象性**（将具体值如“干猫粮”替换为通用变量如 `{product-name}`），以增强其通用性。
*   **工作流归纳**: 使用语言模型从一组经验中提取常见的子程序。通过提示工程，模型被引导提取精细的子任务并抽象化具体语境。
*   **两种应用场景**:
    *   **离线场景**: 当存在高质量标注示例时，预先从这些示例中归纳出一组工作流，并在推理时将其静态地整合到智能体的记忆中，用于指导所有测试任务的解决。
    *   **在线场景**: 在无监督的情况下，以流式方式处理测试查询。智能体解决一个任务后，会由一个评估模块判断其是否成功。如果成功，就从该任务的经验中归纳出工作流，并动态地添加到记忆中，供后续任务使用。此过程循环进行，实现边推理边学习。
*   **算法流程**:
    1.  智能体接收自然语言指令。
    2.  结合基础记忆（内置动作文档）和当前的工作流记忆，生成动作序列。
    3.  执行动作，与环境交互。
    4.  完成任务后形成“经验”。
    5.  (在线模式) 评估经验是否成功。
    6.  若成功，归纳模块 `I(experience) → workflow` 提取工作流。
    7.  更新智能体记忆 `M_t + {workflow_t} → M_{t+1}`。

### **实验设计**

*   **数据集/场景**:
    *   **WebArena**: 提供 812 个网页导航任务，跨 5 个网站和 4 个领域（电商、社交、开发、内容管理）。支持基于功能正确性的严格评估。
    *   **Mind2Web**: 强调跨任务、跨网站、跨域的通用性。包含多个测试集，用于评估代理在不同迁移场景下的表现。
*   **基准方法**:
    *   **WebArena**:
        *   **自主智能体方法**：`BrowserGym`（当时的顶尖方法）和 `AutoEval`。
        *   **人工工程工作流方法**：`SteP`（使用专家为 WebArena 量身定制的14个工作流）。
    *   **Mind2Web**:
        *   `MindAct`: 通过元素过滤和多选格式来处理观测。
        *   `Synapse`: 采用轨迹式格式，并增强检索相关的完整示例作为上下文。
*   **评估指标**:
    *   **WebArena**: 任务成功率，以及完成任务的步数。
    *   **Mind2Web**: 元素准确率、动作 F1 值、步骤成功率，以及所有步骤都成功的任务级成功率。
*   **语言模型**: 使用 GPT-4o 和 GPT-3.5-turbo 作为骨干模型。

### **资源与算力**

*   论文中**未明确提及**所使用的 GPU 型号、数量及具体的训练或推理时长。论文的方法是基于对 GPT-3.5 和 GPT-4 等大型语言模型的 API 调用，因此主要算力消耗是 API 调用产生的费用和网络延迟，而非本地 GPU 计算。论文在附录 D 中对计算开销进行了分析，指出 AWM 引入的轨迹评估和流程归纳模块相较于基础的动作生成步骤，仅增加了约 10.8% 的计算量。

### **实验数量与充分性**

*   **主要实验**: 在 WebArena 和 Mind2Web 两个基准上，分别在在线、离线以及跨任务、跨模板、跨网站、跨域等多种场景下进行了评估，实验组数丰富。
*   **消融研究与分析**:
    *   **工作流表示**: 对比了抽象子程序格式与基于规则的非抽象格式、代码与文本描述的工作流表示、以及不同的环境状态抽象（自然语言描述 vs. 过滤后的 HTML）。
    *   **场景集成**: 探索了离线与在线工作流结合使用的效果。
    *   **动作空间**: 尝试了将工作流作为高级动作集成到智能体的动作空间中。
    *   **鲁棒性**: 分析了 AWM 对示例输入顺序的敏感度，并进行了工作流质量分析（数量、覆盖率、功能重叠、使用率）。
*   **公平性**: 实验采用相同的语言模型（GPT-4o 或 GPT-3.5），并复现或直接引用公开的基线结果进行比较，例如在 WebArena 上将 BrowserGym 统一到只用无障碍树的环境表示，确保了对比的公平性。
*   **充分性**: 实验设计全面，覆盖了主要结果、泛化能力、效率、表示形式等多个维度，分析深入，对方法的有效性和局限性进行了充分探讨。

### **论文的主要结论与发现**

1.  **显著提升任务成功率**: AWM 在两个基准上都取得了实质性提升。在 WebArena 上，相对成功率提升 51.1%，甚至超越了使用人工设计工作流的方法。在 Mind2Web 上，步骤成功率相对提升 24.6%。
2.  **强大的泛化能力**: 在线 AWM 在跨任务、跨网站和跨域评估中表现出强大的泛化性，且当训练-测试任务分布差异越大时，其相对于无需自适应的基线的优势越明显。
3.  **持续学习与效率**: AWM 展示出从少量数据（几十个例子）中快速学习并持续构建更复杂工作流的“滚雪球”效应。同时，AWM 完成任务所需步数更少，比基线方法更高效。
4.  **抽象子程序优于具体经验**: 对比实验表明，AWM 诱导的抽象、可复用的工作流比检索到的完整示例轨迹更有效，因为它能减少对元素选择的偏差，并具备更灵活的适应性。

### **优点**

*   **机制创新**: 模拟人类从经验中抽象例程的学习方式，为智能体引入了一种新颖、有效的动态记忆机制。
*   **场景灵活**: 既能用于有标注数据的离线预训练，也能用于无监督的在线持续学习，适应性强。
*   **泛化能力强**: 证明了学习可复用工作流是实现跨任务、跨域迁移的有效途径，方法具有很强的鲁棒性。
*   **性能优异且高效**: 不仅大幅超越所有基线，甚至优于使用人类专家知识的方法，并且模型推理效率更高。
*   **实验设计扎实**: 在多个权威基准上进行评估，包含详尽的消融实验和深入的结果分析，结论可靠。

### **不足与局限**

*   **依赖评估模块**: 在线 AWM 的性能严重依赖于任务成功与否的自动评估模块，错误判断的成功经验会引入“噪音”工作流，误导后续学习。
*   **工作流执行僵化**: 工作流一旦被定义为固定的动作序列，在面对动态变化的环境时（如网页弹出不同的选项）可能会失效。尽管可以将其作为高级动作调用，但智能体可能无法灵活处理执行过程中的意外情况。
*   **离线训练数据偏差**: 当离线训练数据与测试任务分布存在较大差异时，离线 AWM 的性能会受到影响，效果不如完全从测试数据中自举的在线方法。
*   **模型依赖**: 方法效果与骨干语言模型的归纳和推理能力紧密相关，文中仅使用了 GPT 系列模型进行验证。
*   **泛化边界未探明**: 虽然展示了在网页导航上的跨域泛化，但对于更广泛的数字任务（如操作系统、专业软件操作）的泛化能力还有待进一步研究。

（完）
