---
title: World Model Implanting for Test-time Adaptation of Embodied Agents
title_zh: 世界模型植入：具身智能体的测试时适应
authors: "Minjong Yoo, Jinwoo Jang, Sihyung Yoon, Honguk Woo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=tpbtodnI1p"
tags: ["query:continual"]
score: 5.0
evidence: 动态环境中智能体的测试时适应框架
tldr: 该研究解决具身智能体在无需大量数据或重新训练的情况下适应新领域的挑战。提出世界模型植入框架WorMI，结合大语言模型的推理能力与领域特定的世界模型，通过测试时组合实现跨域适应。方法采用基于原型的检索方式匹配相关模型，从而使智能体策略在新环境下维持适应性。实验验证了框架的有效性，为动态环境中的智能体适应提供了新方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 852, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1631, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 832, \"height\": 959, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 832, \"height\": 373, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 829, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1760, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1590, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-tpbtodni1p/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1748, \"height\": 299, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1520, \"height\": 603, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 501, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 694, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 436, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 677, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 861, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 832, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1109, \"height\": 586, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 967, \"height\": 496, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1001, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1195, \"height\": 395, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1029, \"height\": 1011, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 610, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 756, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 487, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 579, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 704, \"height\": 174, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-tpbtodni1p/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 533, \"height\": 422, \"label\": \"Table\"}]"
motivation: 具身智能体在无需大量数据或重新训练下适应新领域存在挑战。
method: 提出WorMI框架，结合大语言模型推理与领域特定世界模型进行测试时组合。
result: 实现跨领域适应性，并开发了基于原型的世界模型检索方法。
conclusion: 通过可植入的世界模型，使智能体策略在测试时维持适应能力。
---

## Abstract
In embodied AI, a persistent challenge is enabling agents to robustly adapt to novel domains without requiring extensive data collection or retraining. To address this, we present a world model implanting framework (WorMI) that combines the reasoning capabilities of large language models (LLMs) with independently learned, domain-specific world models through test-time composition. By allowing seamless implantation and removal of the world models, the embodied agent's policy achieves and maintains cross-domain adaptability. In the WorMI framework, we employ a prototype-based world model retrieval approach, utilizing efficient trajectory-based abstract representation matching, to incorporate relevant models into test-time composition. We also develop a world-wise compound attention method that not only integrates the knowledge from the retrieved world models but also aligns their intermediate representations with the reasoning model's representation within the agent's policy. This framework design effectively fuses domain-specific knowledge from multiple world models, ensuring robust adaptation to unseen domains. We evaluate our WorMI on the VirtualHome and ALFWorld benchmarks, demonstrating superior zero-shot and few-shot performance compared to several LLM-based approaches across a range of unseen domains. These results highlight the framework’s potential for scalable, real-world deployment in embodied agent scenarios where adaptability and data efficiency are essential.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义
*   **核心问题**：具身智能体（Embodied Agents）在部署到与训练环境不同的全新领域（Unseen Domains）时，普遍面临性能急剧下降的挑战。传统的解决方案，如微调（需要大量数据）或上下文学习（推理开销大、效率低），在数据效率和适应性上存在局限。
*   **整体含义**：本文旨在提出一种**测试时适应（Test-time Adaptation）** 框架，使智能体能够**在不重新训练的前提下**，动态地、灵活地组合来自多个不同领域的先验知识，从而实现对未知环境的鲁棒且高效的适应。

### 2. 论文提出的方法论
论文提出了**世界模型植入框架 (WorMI)**，其核心思想是像“即插即用”的模块一样，在测试时动态地向一个固定的基础大语言模型 (LLM) 推理器中“植入”或“移除”领域特定的世界模型。

*   **核心思想与流程**：
    1.  **模型准备**：预先独立训练多个领域特定的“世界模型”，每个模型封装了某一领域的动态、可供性和行为策略。
    2.  **测试时组合**：面对新任务时，通过一个可训练的“组合模块”，动态地选择和融合相关的世界模型，并将其知识与LLM推理器对齐，形成最终的决策策略。

*   **关键技术细节**：
    *   **原型化世界模型检索 (Prototype-based World Model Retrieval)**：
        *   **目的**：从一组可用世界模型中，快速、准确地选出与当前任务最相关的 `K` 个。
        *   **方法**：为每个世界模型的训练数据集构建一个“原型”集合。具体是提取所有状态的物体级嵌入，并用 k-center 算法聚类出 `k` 个中心点作为原型。通过计算当前任务状态的嵌入原型与世界模型原型的Wasserstein距离来评估相关性。该方法极大降低了检索的计算成本。
    *   **世界级复合注意力 (World-wise Compound Attention)**：
        *   **目的**：将检索到的多个世界模型的中间层知识有效融合，并与LLM推理器的知识表示对齐。
        *   **结构**：一个层次化的交叉注意力模块。
            1.  **线性投影**：将不同世界模型的表示映射到与推理模型相同的维度。
            2.  **世界级交叉注意力**：以推理模型的当前状态为查询，融合多个世界模型的表示，动态分配对不同世界模型的关注度。
            3.  **推理级交叉注意力**：将上一步融合后的世界知识表示，对齐并注入到LLM推理模型的表示中。
    *   **元学习训练 (Meta-Learning)**：
        *   **目的**：训练复合注意力模块，使其学会如何快速泛化并组合任意未见过的世界模型子集。
        *   **方法**：采用 MAML 风格的元学习。内循环在随机采样的世界模型子集上对组合模块进行少量梯度更新，外循环则更新元参数，以学习一个通用的组合与对齐策略。

### 3. 实验设计
*   **数据集与基准**：
    *   **VirtualHome**：一个3D室内模拟环境。任务包含78种（如开关电器、取放物品），场景包含20个不同的房屋布局。任务和场景被划分为已见和未见两部分。
    *   **ALFWorld**：一个基于文本的室内任务模拟环境。包含6种任务类型和4种场景类型，同样划分已见/未见。
*   **对比方法**：
    *   **ZSP (零样本规划)**：直接使用预训练LLM进行规划，不做任何适应。
    *   **LLM+FT (微调LLM)**：在目标域少量数据上微调LLM。
    *   **LLM-Planner**：利用上下文学习，从示例库中检索相似经验来规划的高级方法。
    *   **SayCanPay**：当前最先进的模型集成方法，结合了LLM推理、技能可供性和启发式成本函数。
*   **评估指标**：
    *   **成功率 (SR)**：完成任务或子目标的比例。
    *   **待完成步骤 (PS)**：完成任务所需的平均时间步数，衡量效率。

### 4. 资源与算力
*   论文未明确提及训练所使用的**GPU型号、数量或总训练时长**。但提到了所用模型的具体规格：
    *   固定的LLM推理模型：Llama-3.2-3B。
    *   可训练的世界模型和部分基线模型：Llama-3.2-1B。
    *   消融实验中，LLM规模扩展到了11B（Llama-3.2-11B）。

### 5. 实验数量与充分性
*   **实验组数**：实验设计较为全面，包含以下几类：
    1.  **主要结果**：在两个数据集（VirtualHome, ALFWorld）上，针对零样本和少样本（1-shot, 5-shot, 10-shot）设置，与4个基线方法进行全面比较。
    2.  **消融研究**：针对两个核心组件（原型检索、复合注意力）分别进行了消融实验，验证其有效性。
    3.  **模型分析**：分析了LLM规模、植入世界模型数量、持续植入/移除、复杂指令处理等对性能的影响。
*   **充分性与公平性**：实验覆盖了不同场景和任务难度，对比了不同技术路线的方法，消融实验清晰，且所有模型的基础LLM保持一致，确保了比较的公平性和分析的客观性。

### 6. 论文的主要结论与发现
WorMI框架在具身智能体的跨域适应任务上表现出显著的优越性和数据效率。

*   **性能显著提升**：在零样本场景下，WorMI在VirtualHome和ALFWorld上的成功率全面超越所有基线，尤其在未见领域上远超此前最优的SayCanPay方法（例如在VirtualHome上SR提升20.41%）。
*   **高效少样本适应**：在少样本场景下，WorMI同样表现最佳，且仅需极少样本即可快速适应新域。
*   **动态知识融合**：通过世界级注意力可视化证明，WorMI能根据当前任务上下文，动态地选择和关注最相关的领域知识。
*   **可扩展与可插拔**：验证了框架支持动态增添或移除世界模型，具备持续学习和知识遗忘的能力。
*   **LLM规模正相关**：框架性能随基础LLM规模增大而提升，能更好地利用大模型的推理能力。

### 7. 优点
*   **框架新颖且灵活**：首次提出了“世界模型植入”的概念，将模型集成与上下文学习的优点相结合，实现了模块化、可插拔的知识组合。
*   **方法高效**：原型化检索方法显著降低了测试时选择模型的计算开销；通过元学习的复合注意力模块能实现参数高效的知识融合与快速适应。
*   **解释性强**：复合注意力机制提供了世界模型级和推理级的注意力权重，能清晰展示模型是如何动态组合不同来源知识的。
*   **问题导向明确**：直接解决了具身AI领域中一个关键且实际的挑战——在数据稀缺下实现鲁棒的跨域泛化。

### 8. 不足与局限
*   **计算开销**：推理时需并行运行多个世界模型，计算资源消耗仍高于单模型方法，可能不适合资源极端受限的场景。
*   **依赖底层LLM**：框架的整体推理能力受限于所选LLM的性能，其固有缺陷（如幻觉）可能会被继承。
*   **世界模型训练成本**：前提是需要为每个领域预先训练好专用的世界模型，对训练数据和流程有额外要求。
*   **对抗鲁棒性**：论文提到，若大部分被检索的模型都是对抗性或无关的，性能会急剧下降，表明检索系统对模型质量有一定的脆弱性。

（完）
