---
title: Rethinking the Stability-Plasticity Trade-off in Continual Learning from an Architectural Perspective
title_zh: 从架构视角反思持续学习的稳定性-可塑性权衡
authors: "Aojun Lu, Hangjie Yuan, Tao Feng, Yanan Sun"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=yO95ALeoGw"
tags: ["query:continual"]
score: 10.0
evidence: 架构因素影响持续学习的稳定性-可塑性权衡
tldr: 持续学习中稳定性-可塑性权衡通常仅在参数层面考虑，忽略网络架构影响。该工作在等参数约束下探究深度与宽度对稳定性和可塑性的作用，发现深度网络可塑性更强，宽度网络稳定性更强，提出在架构层面解耦双目标以平衡权衡，为设计持续学习网络架构提供新方向。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1702, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1692, \"height\": 828, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1773, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 863, \"height\": 932, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-yo95aleogw/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1786, \"height\": 1239, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1737, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 856, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1766, \"height\": 1045, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1695, \"height\": 421, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 171, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 812, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1072, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1505, \"height\": 298, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-yo95aleogw/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1061, \"height\": 299, \"label\": \"Table\"}]"
motivation: 网络架构对持续学习稳定性和可塑性的影响被忽视。
method: 在等参数量下分析深度与宽度对稳定性和可塑性的影响。
result: 深度网络可塑性更好，宽度网络稳定性更好。
conclusion: 架构层面的解耦设计可为持续学习带来更好平衡。
---

## Abstract
The quest for Continual Learning (CL) seeks to empower neural networks with the ability to learn and adapt incrementally. Central to this pursuit is addressing the stability-plasticity dilemma, which involves striking a balance between two conflicting objectives: preserving previously learned knowledge and acquiring new knowledge. While numerous CL methods aim to achieve this trade-off, they often overlook the impact of network architecture on stability and plasticity, restricting the trade-off to the parameter level. In this paper, we delve into the conflict between stability and plasticity at the architectural level. We reveal that under an equal parameter constraint, deeper networks exhibit better plasticity, while wider networks are characterized by superior stability. To address this architectural-level dilemma, we introduce a novel framework denoted Dual-Arch, which serves as a plug-in component for CL. This framework leverages the complementary strengths of two distinct and independent networks: one dedicated to plasticity and the other to stability. Each network is designed with a specialized and lightweight architecture, tailored to its respective objective. Extensive experiments demonstrate that Dual-Arch enhances the performance of existing CL methods while being up to 87% more compact in terms of parameters.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- 持续学习（CL）的核心挑战是灾难性遗忘，表现为稳定性（保留旧知识）与可塑性（获取新知识）之间的权衡（稳定性‑可塑性困境）。
- 过往研究主要在参数层面（如添加损失项、记忆重放、动态扩展参数）缓解这一困境，而对网络架构本身如何影响稳定性与可塑性的关注不足。
- 很少有工作探究在相等参数量约束下，网络的深度与宽度究竟如何分别作用于稳定性和可塑性，这导致已有方法采用的统一架构可能隐含了架构层面的冲突。

### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**
  - 将稳定性与可塑性在架构层面解耦，使用两个互补的专用网络，分别负责可塑性和稳定性，再通过蒸馏融合新知与旧识。
- **架构设计**
  - **可塑性学习者（Pla‑Net）**：保持 ResNet‑18 的深度，大幅收窄宽度（基宽从 64 减为 42），以提升新任务学习能力。
  - **稳定性学习者（Sta‑Net）**：保持 ResNet‑18 的宽度，大幅减少残差块数量（深度减半），并增大分类器前的池化特征图尺寸（`2×2` 替代 `1×1`），以提升抗遗忘能力。
  - 这两个网络在总参数量上基本相当，且均小于原始 ResNet‑18。
- **训练流程（算法1）**
  - 对每个新任务 \(k\)：
    1. 训练可塑性学习者 \(\phi_k\)，仅用当前任务的交叉熵损失 \(L_{CE}\) 直至收敛，冻结后作为教师模型。
    2. 训练稳定性学习者 \(\theta_k\)，损失函数为：
       \[
       L_{\mathrm{stable}} = \alpha L_{CE} + (1-\alpha) L_{KD} + L_{CL}
       \]
       其中 \(L_{KD}\) 为教师‑学生间的 KL 散度蒸馏损失（带温度系数 \(t\)），帮助稳定性学习者从可塑性模型吸收新知识；\(L_{CL}\) 为所集成的持续学习方法（如 iCaRL、DER 等）原有的损失项；\(\alpha\) 默认取 0.5。
  - 最终仅使用稳定性学习者进行推理与评估。
- **即插即用特性**
  - Dual‑Arch 可自然地与基于重放、正则化、动态架构等各类 CL 方法结合，在训练稳定学习者时直接施加相应方法的原始约束。

### 3. 实验设计：数据集/场景、基准方法与对比方案
- **数据集与划分**
  - CIFAR‑100：10 任务/10 类（CIFAR100/10）和 20 任务/5 类（CIFAR100/20）。
  - ImageNet‑100：10 任务/10 类（ImageNet100/10）和 20 任务/5 类（ImageNet100/20）。
  - 所有划分均为无重复类的类别增量学习（Class‑IL）设定，推理时任务标识未知。
- **基准方法与对比对象**
  - 五种代表性 CL 方法：iCaRL（重放+蒸馏）、WA（规范化）、DER（动态扩展）、Foster（特征压缩）、MEMO（记忆高效）。
  - 每种方法均使用原始 ResNet‑18 作为单一学习器，与插入 Dual‑Arch 的版本进行比较。
  - 同时对比了单架构优化方案 ArchCraft。
- **评估指标**
  - Last Accuracy（LA，最终任务准确率）、Average Incremental Accuracy（AIA，所有步骤平均准确率）、Final‑task Average Forgetting（FAF，最终遗忘量）。
- **额外验证**
  - 参数效率分析（调整宽度）、计算效率分析（FLOPs）、偏差校正分析（混淆矩阵）、向 Vision Transformer（SepViT）的迁移、长序列（CIFAR100/50）和模糊任务边界（GCIL‑CIFAR‑100）场景测试。

### 4. 资源与算力
- 文中**未明确说明**使用的 GPU 型号、数量和训练时的显存占用。
- 仅提供了**计算量对比**（FLOPs）：例如在 CIFAR‑100 上，Sta‑Net 与 Pla‑Net 总和约 496M FLOPs，低于 ResNet‑18 的 558M。
- **训练时间对比**（表4）：以分钟为单位给出，反映 Dual‑Arch 训练时长约为原始方法的 1.39× 至 1.77×，但未关联具体硬件配置。

### 5. 实验数量与充分性
- **实验规模很可观**，涵盖：
  - 4 种数据集×划分组合 × 5 种 CL 方法 × 多项指标的主实验（表2）。
  - 消融实验：逐一移除塑料学习者、互换架构设计等（表3）。
  - 参数效率实验：对 Dual‑Arch 和 ResNet‑18 分别缩窄宽度，对比性能‑参数量曲线（图3）。
  - 架构维度探查：ResNet、MLP、Vision Transformer 上比较不同深宽配比对 AAN/FAF 的影响。
  - 偏差分析：绘制多组混淆矩阵（图5、图6）。
  - 长任务序列（50 任务）、模糊任务边界（GCIL）、Vision Transformer 验证。
- **公平性保障**：超参数沿用开源库 PyCIL 的默认设置，固定随机种子，数据增强一致；比较时均控制参数量在同类方法中可比较。
- 综合来看，实验**设计全面、重复充分、对比客观**。

### 6. 论文的主要结论与发现
- 网络架构的深度和宽度分别倾向于提升**可塑性**和**稳定性**，在相等参数量下存在明显的架构层面权衡。
- 提出的 Dual‑Arch 框架用两个专用架构分别承担可塑性与稳定性角色，可以有效缓解架构级冲突，显著提高多种 CL 方法的性能。
- Dual‑Arch 在多数设置下**结果优于**单一 ResNet‑18 基线以及架构优化方案 ArchCraft，同时可最大减少 **87% 的参数**。
- 消融实验表明，移除塑料学习者或互换架构均导致性能下降，验证了双专用架构的必要性。
- Dual‑Arch 还能有效减轻任务最近偏差（task‑recency bias），使模型更准确地将旧任务样本分类到正确的任务 ID。

### 7. 优点：方法或实验设计上的亮点
- **视角新颖**：首次明确在架构层面解耦稳定性与可塑性，补充了以往仅从参数优化思考的不足。
- **即插即用**：可无缝嵌入多种已有 CL 方法，不改变原有学习范式，泛用性强。
- **参数高效**：在提升准确率的同时大幅压缩总参数量，有利于边缘或存储受限的场景。
- **实验扎实**：覆盖多个数据集、多种 CL 方法、不同任务数和场景，消融与分析全面，且有可复现的代码与固定超参设置。
- **理论见解清晰**：通过先导实验明确深度‑可塑性、宽度‑稳定性的关联，为方法设计提供了扎实依据。

### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
- **训练时间增加**：需要顺序训练两个模型（无法并行），训练时间开销约为原始方法的 1.4~1.8 倍，对实时性或快速迭代环境不友好。
- **主要基于 ResNet 设计**：塑料/稳定架构的修改方式是为 ResNet‑18 手工定制的，虽然验证了 ViT 的可迁移性，但面向更多元网络（如 MobileNet、EfficientNet）的设计通用性尚待检验。
- **未讨论内存与通信开销**：虽强调了参数效率，但双模型的中间激活、教师模型存储、蒸馏过程的额外计算等可能影响实际部署效率，缺乏更细致的内存占用分析。
- **任务增量的场景较常规**：实验主要基于类别增量学习，虽测试了模糊边界等扩展，但在更复杂的在线流式学习、多模态持续学习等场景的适用性尚不明朗。

（完）
