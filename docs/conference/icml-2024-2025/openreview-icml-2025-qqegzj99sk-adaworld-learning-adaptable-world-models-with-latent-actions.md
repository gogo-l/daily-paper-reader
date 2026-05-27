---
title: "AdaWorld: Learning Adaptable World Models with Latent Actions"
title_zh: AdaWorld：利用潜在动作学习可适应世界模型
authors: "Shenyuan Gao, Siyuan Zhou, Yilun Du, Jun Zhang, Chuang Gan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=QQegZj99sk"
tags: ["query:continual"]
score: 5.0
evidence: 可适应世界模型以实现高效跨域适应
tldr: 针对现有世界模型依赖大量动作标注数据且难以高效适应新环境的问题，该研究提出AdaWorld，一种可适应世界模型学习方法。核心是通过自监督方式从视频中提取潜在动作，捕捉关键状态转移，使世界模型在有限交互下快速适应新领域。实验表明方法有效提升了世界模型的泛化适应性，为智能体在动态环境中的自主学习提供了基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 843, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1674, \"height\": 1705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1745, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1753, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 851, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1566, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1757, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1742, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1549, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1738, \"height\": 2262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1740, \"height\": 2257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1739, \"height\": 2250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1741, \"height\": 2248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1740, \"height\": 2248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1302, \"height\": 1081, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1300, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1301, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1298, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1748, \"height\": 1773, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1673, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1307, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1784, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 609, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 691, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1380, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1719, \"height\": 1574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1700, \"height\": 184, \"label\": \"Table\"}]"
motivation: 现有世界模型依赖大量标注动作数据且难以适应新环境。
method: 通过自监督方式从视频中提取潜在动作，使世界模型能高效适应。
result: 实现世界模型对新环境的有效适应，无需昂贵重训练。
conclusion: 为构建能跨域适应的世界模型提供了新方法。
---

## Abstract
World models aim to learn action-controlled future prediction and have proven essential for the development of intelligent agents. However, most existing world models rely heavily on substantial action-labeled data and costly training, making it challenging to adapt to novel environments with heterogeneous actions through limited interactions. This limitation can hinder their applicability across broader domains. To overcome this limitation, we propose AdaWorld, an innovative world model learning approach that enables efficient adaptation. The key idea is to incorporate action information during the pretraining of world models. This is achieved by extracting latent actions from videos in a self-supervised manner, capturing the most critical transitions between frames. We then develop an autoregressive world model that conditions on these latent actions. This learning paradigm enables highly adaptable world models, facilitating efficient transfer and learning of new actions even with limited interactions and finetuning. Our comprehensive experiments across multiple environments demonstrate that AdaWorld achieves superior performance in both simulation quality and visual planning.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

*   **核心问题**：当前世界模型（World Models）在进行动作控制下的未来预测时，严重依赖大量带有动作标签的数据和昂贵的训练，这导致它们难以通过少量交互就适应具有不同动作空间的新环境，限制了其在更广泛领域的应用。
*   **研究动机**：人类能够通过有限的经验估计新动作的效果，这种能力可能源于从大量观察中学习到的、可跨场景迁移的内部动作表征。论文旨在让世界模型也具备类似人类的这种高效适应性。
*   **整体含义**：提出一种名为 **AdaWorld** 的创新世界模型预训练方法，其核心是在预训练阶段就通过自监督方式从视频中自动提取并融入“潜在动作”（latent actions）信息，从而学习到一个高度可适应的世界模型，使其能够快速迁移和学会新环境下的动作控制。

### 2. 论文提出的方法论

AdaWorld 的核心思想是在世界模型预训练时，用从无标签视频中自监督提取的“潜在动作”作为统一的条件，从而学习可迁移的动作控制能力。该方法主要包含两个关键组件：

*   **潜在动作自编码器 (Latent Action Autoencoder)**
    *   **核心思想**：从连续的视频帧中自动提取最关键、与上下文解耦的动作信息。
    *   **架构**：基于 Transformer，由一个时空编码器和一个空间解码器组成。
        *   **编码器**：输入连续两帧视频，通过时空注意力机制提取帧间动态变化，并生成一个极低维度的、连续的潜在动作向量 \(\tilde{\mathbf{a}}\)。该向量服从 VAE 的后验分布。
        *   **解码器**：基于前一帧和从编码器获取的潜在动作 \(\tilde{\mathbf{a}}\)，尽可能重建后一帧。
    *   **关键技术：信息瓶颈 (Information Bottleneck)**：通过将潜在动作的维度压缩至极低（如32维），强制自编码器只编码帧间最关键的变化（即动作本身），从而实现动作与其场景上下文的高度解耦，使提取出的潜在动作具有上下文不变性，可以跨场景迁移。
    *   **损失函数优化**：采用 β-VAE 损失函数进行训练：
        \[
        \mathcal{L}_{\text{pred}}^{\theta,\phi}(f_{t+1}) = -\mathbb{E}_{q_\phi(\tilde{\mathbf{a}}|f_{t:t+1})} \log p_\theta(f_{t+1} | \tilde{\mathbf{a}}, f_t) + \beta D_{KL}(q_\phi(\tilde{\mathbf{a}}|f_{t:t+1}) || p(\tilde{\mathbf{a}}))
        \]
        通过调整超参数 \(\beta\)，可在潜在动作的表达能力和上下文解耦能力之间取得平衡。

*   **动作感知预训练 (Action-Aware Pretraining)**
    *   **世界模型架构**：一个基于扩散模型（Stable Video Diffusion）的自回归世界模型。
    *   **训练过程**：使用训练好的潜在动作编码器，从海量无标签视频中提取帧间潜在动作序列。然后，训练世界模型以历史帧和当前帧的潜在动作 \(\tilde{\mathbf{a}}\) 为条件，预测下一帧画面。
    *   **推理过程**：模型可以自回归地进行长序列未来帧预测。它将预测出的帧不断加入历史记忆（short-term memory），并以此为基础进行下一步预测。

*   **高度可适应世界建模**
    *   **动作迁移**：给定一个包含某种动作的演示视频，提取其潜在动作序列，即可将该动作迁移到任何新的初始帧场景中，无需任何训练。
    *   **高效微调**：对于有明确动作空间（离散或连续）的新环境，只需少量交互样本，即可通过平均同类动作的潜在动作来初始化世界模型的控制接口，经过极少的微调步骤即可获得精准的动作控制能力。
    *   **动作组合与创造**：在连续的潜在空间中，通过平均两个潜在动作，可以生成组合新动作（如“跳跃+右移”）。通过对潜在动作进行聚类，可以创造出任意数量的、功能各异的控制选项。

### 3. 实验设计

论文设计了多维度的实验来验证 AdaWorld 的优越性，对比了以下三种基线方法：
*   **动作无关预训练 (Action-agnostic)**：预训练时始终输入零向量作为动作条件，模拟主流预训练范式。
*   **光流作为条件 (Flow cond.)**：使用UniMatch从视频中提取光流图，作为动作条件。
*   **离散潜在动作作为条件 (Discrete cond.)**：基于VQ-VAE实现，使用8个离散码作为潜在动作（类似Genie方法），以对比连续潜在动作空间的优势。

实验围绕以下方面展开：

*   **动作迁移评估 (Sec. 3.1)**
    *   **数据集/场景**：来自未见过的 LIBERO 和 Something-Something V2 (SSv2) 数据集。选取了包含相似动作但上下文不同的视频对进行评估（LIBERO 1300对，SSv2 1300对）。
    *   **评估方式**：从源视频提取动作，在新视频的初始帧上生成20帧未来序列，并与真实视频对比。
    *   **评估指标**：FVD (Fréchet Video Distance)、ECS (Embedding Cosine Similarity) 和人类主观评价。

*   **世界模型适应性与规划性能 (Sec. 3.2)**
    *   **模拟质量评估**：在四个全新环境（Habitat, Minecraft, DMLab, nuScenes）中使用少量样本（每个离散动作仅100个样本）微调世界模型800步，然后评估其根据动作指令生成未来帧的保真度。
        *   **指标**：PSNR 和 LPIPS。
    *   **视觉规划评估**：
        *   **游戏场景**：在 Procgen 基准（Heist, Jumper, Maze, CaveFlyer四个环境）中进行目标导向的视觉规划任务。规划策略采用基于交叉熵方法优化的模型预测控制 (MPC)。
        *   **机器人场景**：在 VP² 基准上评估，包括 Robosuite 和 RoboDesk 任务，使用 MPPI 进行规划。
        *   **评估指标**：任务成功率。

*   **消融与分析 (Sec. 3.3)**
    *   **接口初始化**：对比了使用潜在动作初始化和随机初始化控制接口的微调效率。
    *   **数据多样性**：研究了增加训练数据（结合Open X-Embodiment机器人数据）对在Procgen上泛化能力的影响。
    *   **方法通用性**：将提出的动作感知预训练范式应用到另一个世界模型 iVideoGPT 上，并在 BAIR 机器人推送数据集上测试适应性。

### 4. 资源与算力

论文在附录 B.2 中明确提到了以下算力使用情况：
*   世界模型的动作感知预训练使用了 **16块NVIDIA A100 GPU**。
*   自编码器的训练参数和算力细节未明确在单句中与A100关联，但其世界模型的预训练计算资源有明确提及。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了相当全面的实验，涵盖了**动作迁移、环境适应、视觉规划等至少3个主要任务**，并在**至少8个不同的数据集/基准**（LIBERO, SSv2, Habitat, Minecraft, DMLab, nuScenes, Procgen, VP²）上进行了验证。
*   **消融实验**：包含了**至少3组消融研究**，分别验证了关键设计（连续潜在动作 vs. 离散/光流）、接口初始化方法、数据多样性和方法通用性的影响。
*   **充分性、客观性与公平性**：
    *   **充分性**：实验维度丰富，从定性的动作迁移可视化到定量的保真度、相似度和规划成功率均有涉及，并包含了人类评估，论证较为完整。
    *   **客观性与公平性**：选择了多个具有代表性的强基线（动作无关、光流、离散潜在动作）进行比较，并在多个实验中都尽可能地控制了训练步骤、计算量等变量，保证了对比的相对公平性。

### 6. 论文的主要结论与发现

*   **动作迁移能力突出**：AdaWorld 能高效地将演示视频中的动作提取为上下文无关的潜在动作，并成功迁移到全新的、视觉不同的场景中，显著优于所有基线方法。
*   **高效的世界模型适应**：在仅需极少动作标签样本和极少微调步数的条件下，AdaWorld 能够快速掌握新环境的动作控制能力，其模拟质量和微调效率远超基于动作无关视频预训练的基线。
*   **提升视觉规划性能**：在经过高效适应后，AdaWorld 在游戏和机器人任务中的视觉规划成功率均大幅领先于基线方法，甚至在不微调的情况下也能取得较好成绩。
*   **连续潜在空间带来灵活性**：与离散动作表征相比，连续的潜在动作空间不仅表达力更强，还能支持动作组合与动作创造等独特应用，具有更高的灵活性和可控性。

### 7. 优点

*   **新颖的预训练范式**：首次提出在大型世界模型预训练阶段就通过自监督方式融入“潜在动作”信息，从根本上改变了对动作标注的依赖。
*   **方法设计与实现精妙**：通过 β-VAE 和信息瓶颈成功实现动作与场景的解耦，连续的潜在动作空间设计相比离散方案具有更高的表达力和灵活性。
*   **实验设计全面扎实**：实验覆盖了从基础的动作迁移到复杂的视觉规划等多个层面，与多种强基线进行了对比，并辅以充分的消融实验，论证有力。
*   **泛化能力与可扩展性强**：方法通过在超大规模、多样化的数据集上预训练，展现出了向未见域的强大泛化能力，且架构兼容其他世界模型。

### 8. 不足与局限

*   **推理速度非实时**：当前模型本质上是一个扩散模型，在单个帧的生成上无法达到实时交互的频率。
*   **长期生成能力有限**：
    *   在预测步数超出初始场景范围时，模型难以创造全新内容。
    *   在长期自回归生成过程中，存在着质量下降和难以模拟复杂物理/动力学的问题。
*   **鲁棒性存在短板**：在面对剧烈的视角变化、长期推演以及复杂动态场景时，模型可能会出现失效的情况（论文附录C也给出了一些失败案例）。
*   **应用限制**：虽然声称高效，但其适应新环境仍需要收集少量交互样本并进行几步模型微调（finetuning），并非完全的零样本泛化。

（完）
