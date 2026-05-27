---
title: "AdaWorld: Learning Adaptable World Models with Latent Actions"
title_zh: AdaWorld：通过潜在动作学习自适应世界模型
authors: "Shenyuan Gao, Siyuan Zhou, Yilun Du, Jun Zhang, Chuang Gan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=QQegZj99sk"
tags: ["query:continual"]
score: 4.0
evidence: 具备潜在动作的自适应世界模型，实现对新环境的高效适应
tldr: 世界模型依赖大量动作标注数据，难以快速适应新环境。本文提出AdaWorld，通过自监督方式从视频中提取潜在动作，融合动作信息预训练世界模型，实现有限交互下的高效适应。实验表明该方法显著提升世界模型在异构动作环境中的适应速度。AdaWorld为构建灵活自适应的智能体提供了可迁移的世界模型学习框架。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 853, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 337, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 843, \"height\": 486, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1674, \"height\": 1705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1745, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1753, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 851, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1566, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1757, \"height\": 717, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1742, \"height\": 902, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1549, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1738, \"height\": 2262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1740, \"height\": 2257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1739, \"height\": 2250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1741, \"height\": 2248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1740, \"height\": 2248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1302, \"height\": 1081, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1300, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1301, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1298, \"height\": 1078, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-qqegzj99sk/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1748, \"height\": 1773, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1673, \"height\": 256, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1307, \"height\": 391, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1784, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 609, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 691, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1380, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1719, \"height\": 1574, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-qqegzj99sk/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1700, \"height\": 184, \"label\": \"Table\"}]"
motivation: 现有世界模型难以在有限交互下适应新环境和异构动作空间。
method: 提出AdaWorld，通过自监督提取潜在动作并融入世界模型预训练，实现高效适应。
result: 实验显示AdaWorld在多样化新环境中能够快速适应，优于传统世界模型。
conclusion: 潜在动作增强的世界模型预训练显著提升了跨环境适应效率，助力智能体进化。
---

## Abstract
World models aim to learn action-controlled future prediction and have proven essential for the development of intelligent agents. However, most existing world models rely heavily on substantial action-labeled data and costly training, making it challenging to adapt to novel environments with heterogeneous actions through limited interactions. This limitation can hinder their applicability across broader domains. To overcome this limitation, we propose AdaWorld, an innovative world model learning approach that enables efficient adaptation. The key idea is to incorporate action information during the pretraining of world models. This is achieved by extracting latent actions from videos in a self-supervised manner, capturing the most critical transitions between frames. We then develop an autoregressive world model that conditions on these latent actions. This learning paradigm enables highly adaptable world models, facilitating efficient transfer and learning of new actions even with limited interactions and finetuning. Our comprehensive experiments across multiple environments demonstrate that AdaWorld achieves superior performance in both simulation quality and visual planning.

---

## 论文详细总结（自动生成）

# AdaWorld: 通过潜在动作学习自适应世界模型

## 1. 论文的核心问题与整体含义
- **核心问题**：现有世界模型通常依赖大量动作标注数据进行训练，且在面对具有异构动作空间的新环境时，需要高昂的标注和微调成本，难以在有限交互下快速适应。
- **研究动机**：人类能够通过对观察的泛化，仅通过少量经验便估计不同动作的效果并迁移至新场景。受此启发，论文旨在赋予世界模型类似的快速适应能力。
- **整体含义**：提出一种新的世界模型预训练范式——将动作信息以自监督方式融入预训练，使模型具备“先天”的动作控制知识，从而在新环境中仅需极少量交互与微调即可高效工作。

## 2. 方法论：核心思想与关键技术细节
### 2.1 潜在动作自编码器（Latent Action Autoencoder）
- **核心思想**：从无标签视频中以连续潜在变量形式提取帧间最关键的变化（即“动作”），作为统一的条件接口。
- **信息瓶颈设计**：基于 Transformer 架构，编码器将连续两帧 \( f_{t}, f_{t+1} \) 映射为紧凑的潜在动作 \(\tilde{a}\)；解码器利用该动作与前一帧 \( f_t \) 重建后一帧 \( f_{t+1} \)。
- **\(\beta\)-VAE 目标**：通过损失函数  
  \[
  L_{\text{pred}} = \mathbb{E}_{q_\phi(\tilde{a}|f_{t:t+1})} \log p_\theta(f_{t+1}|\tilde{a}, f_t) - \beta D_{\text{KL}}(q_\phi(\tilde{a}|f_{t:t+1})\| p(\tilde{a}))
  \]
  并调节 \(\beta\) 以平衡表示能力与上下文解耦，使潜在动作具有上下文不变性，可跨场景迁移。

### 2.2 动作感知世界模型预训练（Action-Aware Pretraining）
- **世界模型架构**：在 Stable Video Diffusion（SVD）的基础上改进，添加短时记忆（支持最多 6 帧历史），以潜在动作和当前帧为条件，通过扩散模型预测下一帧。
- **训练目标**：标准扩散去噪损失  
  \[
  L_{\text{pretrain}} = \mathbb{E}_{x_0,\epsilon,t} \left[ \| x_0 - \hat{x}_0(x_t, t, c) \|^2 \right],
  \]
  其中条件 \(c\) 包含历史帧及潜在动作 \(\tilde{a}\)。

### 2.3 高效自适应的世界模型应用
- **动作迁移**：从演示视频中提取潜在动作序列，直接注入到不同场景的初始帧中，实现零训练的动作迁移。
- **世界模型适配**：在新环境中仅需少量交互数据（例如每动作 100 个样本），通过平均同类动作的潜在动作初始化控制接口，微调极少量步数即可获得专用世界模型。
- **动作组合与创建**：连续潜在空间支持对潜在动作的插值（产生复合动作）和聚类（创建任意数量的控制选项）。

## 3. 实验设计
### 3.1 数据集与规模
- 训练数据来自：Open X-Embodiment（机器人）、Gym Retro（1000 个 2D 游戏环境）、Procgen Benchmark（16 个环境）、Ego4D、Something-Something V2、MiraData，总计约 **2000 万帧**。

### 3.2 Benchmark 与任务
- **动作迁移评估**：在 LIBERO（未见机器人任务）和 Something-Something V2（人类动作）上，通过 FVD、嵌入余弦相似度（ECS）和人类评估衡量动作复现质量。
- **世界模型适配仿真质量**：在未见的 Habitat、Minecraft、DMLab（离散动作）和 nuScenes（连续动作）上，用 PSNR 和 LPIPS 评估微调后的预测保真度。
- **视觉规划**：
  - **2D 游戏**（Procgen 的 Heist、Jumper、Maze、CaveFlyer）：使用 CEM 规划，通过成功率比较。
  - **机器人规划**（VP² 基准中的 Robosuite 和 RoboDesk）：使用 MPPI 规划，评估成功率。

### 3.3 对比方法
- **Action-agnostic pretraining**：世界模型预训练时不使用任何动作信息（零动作条件）。
- **Optical flow condition**：用 UniMatch 估计的光流作为动作条件。
- **Discrete condition (VQ-VAE)**：类似 Genie 的离散码本（8 个动作）潜在动作。

## 4. 资源与算力
- **潜在动作自编码器**：参数量 500M，训练 200K 步，batch size 960（未明确 GPU 数量，但应为多卡集群）。
- **扩散世界模型**：基于 SVD 的 UNet，1.5B 参数，在 **16 块 NVIDIA A100 GPU** 上训练 80K 步，batch size 64。
- **微调与环境适配**：通常在单 GPU 上完成，例如 Minecraft/nuScenes 仅需 800 步微调；机器人控制接口的 MLP 在 30 秒内可完成 3K 步训练。

## 5. 实验数量与充分性
- **实验丰富度**：至少包含 3 大类任务（动作迁移、模型适配、视觉规划）共 12 组以上的对比表格，覆盖从 2D 游戏到真实机器人、从离散到连续动作等多种场景。
- **消融与分析**：
  - 初始化方法对比（随机初始化 vs 潜在动作初始化）
  - 数据多样性影响（仅 OpenX、仅 Retro、混合）
  - 方法通用性（将动作感知预训练适配到 iVideoGPT）
  - 超参数 \(\beta\) 对动作解耦与表达能力的影响（通过 UMAP 可视化）
- **评估客观性**：使用了自动指标（FVD、PSNR、LPIPS）与人工评估，以及与 Q-learning 等传统 RL 方法的对比，多组随机种子，确保统计可信度。

## 6. 主要结论与发现
- AdaWorld 能够从无标签视频中学习上下文无关的可迁移动作表示。
- 通过动作感知预训练，世界模型在新环境中的适应速度与最终性能均显著优于传统的无动作预训练及基于光流或离散动作的替代方案。
- 在仅 50 次交互、几百步微调的条件下，AdaWorld 即可在多个游戏中实现超越随机规划甚至 Q-learning 的视觉规划成功率，并在机器人操作任务中大幅领先基线。

## 7. 优点
- **自监督动作提取**：无需显式动作标注，利用信息瓶颈自动分离动作与场景，形成可迁移的连续潜在动作空间。
- **高效适应**：零训练即可迁移动作；极少交互与微调即可获得精准可控的专用世界模型。
- **灵活的动作接口**：连续空间支持动作组合与按需创建控制选项，克服了离散方法的能力上限。
- **大规模实验验证**：在极多样化的数据（2000 万帧，逾千环境）上训练，并在多种未见领域验证泛化性。
- **方法论通用性**：提出的动作感知预训练对基于 Transformer 的 iVideoGPT 同样有效，证明其可推广至不同世界模型架构。

## 8. 不足与局限
- **推理速度**：扩散模型推理尚未达到实时频率，限制在线交互应用。
- **长时域漂移**：自回归预测在超出初始场景的范围时会出现质量下降和内容劣化。
- **物理与动态对象模拟**：模型对复杂物理交互、快速视角变化及长期动态演化的模拟仍存在缺陷，文中展示了相应失败案例。
- **数据与规模约束**：尽管数据规模大，但进一步提升模型容量和数据集多样性或可解决部分问题，当前尚未彻底解决“全新内容生成”挑战。
- **环境覆盖**：机器人评测仅限低分辨率变体，真实机器人的多样化长程任务有待进一步验证。

（完）
