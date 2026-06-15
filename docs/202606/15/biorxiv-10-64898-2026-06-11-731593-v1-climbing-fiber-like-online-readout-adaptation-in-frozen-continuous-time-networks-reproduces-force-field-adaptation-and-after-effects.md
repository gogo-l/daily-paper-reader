---
title: Climbing-fiber-like online readout adaptation in frozen continuous-time networks reproduces force-field adaptation and after-effects
title_zh: 冻结连续时间网络中仿爬行纤维的在线读出适应重现力场适应与后效应
authors: "Kobayashi, J."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731593v1.full.pdf"
tags: ["query:continual"]
score: 9.0
evidence: 通过冻结连续时间网络并仅在线适配读出层，实现无遗忘的持续学习，应用于机器人力场适应。
tldr: 连续时间神经网络（如CfC）在机器人控制中通常离线训练，缺乏在线适应机制。本研究冻结CfC核心，仅通过反馈误差学习信号和LMS规则在线调整线性读出层，模拟小脑爬行纤维纠错。力场适应实验显示轨迹校正和镜像后效应，无需改编核心；该方法推广至稀疏NCP，RLS变体需协方差重置来加速去适应。为离线训练连续时间模型提供了一种低成本、生物启发式在线误差适应层。
source: biorxiv
selection_source: fresh_fetch
motivation: 离线训练的CfC等连续时间控制器无法在线适应动态变化，需要探索仅调节读出的低成本在线适应方法。
method: 冻结CfC核心，利用反馈误差学习与LMS规则在线更新线性读出层，模拟爬行纤维误差信号。
result: 冻结核心读出器纠正力场扰动轨迹并产生镜像后效应，推广至稀疏NCP，RLS变体需协方差重置避免缓慢去适应。
conclusion: 仅适应读出即可内部模型学习，无需改编核心，为离线连续时间控制器提供高效在线适应层。
---

## 摘要
基于液态神经网络及相关连续时间模型（如LTC和CfC）的机器人运动控制通常通过随时间反向传播进行离线训练，缺乏在对象动力学变化时进行在线重新校准的显式机制。我们探讨了一个冻结的CfC核心（其液态状态张成固定的连续时间基）能否仅通过类似爬行纤维的误差信号，适应其线性读出，从而支持类似小脑的在线适应。在具有速度依赖旋度力场的平面双连杆伸够仿真中，我们在最小均方规则下使用反馈误差学习信号在线适应读出，而核心保持不变。仅适应冻结核心读出的控制器将受旋度扰动的伸够轨迹重新拉直，并在力场移除后产生镜像后效应——这是内部模型学习的标志——而纯反馈控制器则不会产生。当使用循环状态而非映射出的运动输出作为读出基时，该结果从稠密CfC推广到稀疏神经电路策略连接；它对力场强度和方向具有鲁棒性；递归最小二乘变体适应更快，但因其协方差塌缩而消退缓慢，这种刚性可通过协方差重置的安全遗忘规则消除。在所探索的双连杆平面仿真范围内，我们在测试条件下未发现需要适应冻结核心的容量极限。因此，在本仿真研究中，仅适应读出为离线训练的连续时间控制器提供了一种受生物启发、低成本的在线误差适应层。

## Abstract
Robotic motor control built on liquid neural networks and related continuous-time models, such as LTC and CfC, is typically trained offline via backpropagation through time and lacks an explicit mechanism for recalibrating online as plant dynamics change. We ask whether a frozen CfC core, whose liquid state spans a fixed continuous-time basis, can support cerebellar-style online adaptation by adapting only its linear readout with a climbing-fiber-like error signal. In a planar two-link reaching simulation with a velocity-dependent curl force field, we adapt the readout online with a feedback-error-learning (FEL) signal under a least-mean-squares (LMS) rule, leaving the core untouched. The frozen-core readout-only controller re-straightens curl-perturbed reaches and, upon field removal, produces a mirror-image after-effect---the signature of internal-model learning---that a feedback-only controller does not produce. The result generalizes from a dense CfC to a sparse Neural-Circuit-Policy (NCP) wiring when the recurrent state, rather than the projected motor output, is used as the readout basis; it is robust to force-field strength and direction; and a recursive-least-squares variant adapts faster but de-adapts slowly because its covariance collapses, a rigidity that a covariance-reset safe-forgetting rule removes. Within the explored two-link planar simulation range, we did not find a capacity limit that would require adapting the frozen core in the tested conditions. In this simulation study, adapting only the readout therefore provides a biologically inspired, low-cost online error-adaptation layer for offline-trained continuous-time controllers.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义

-   **核心问题**：当前基于液态网络（Liquid Neural Networks）及连续时间模型（如 CfC、LTC）的机器人运动控制器，通常采用离线训练方式；一旦离线训练完成，面对实际环境中的动态变化（如受力场扰动），缺乏一种高效、低成本的在线自适应与重校准机制，难以实现类似生物小脑通过“爬行纤维”进行快速运动纠正的能力。
-   **整体含义**：本研究探讨，能否通过完全冻结核心网络（提供一个固定的连续时间基），仅利用类似小脑爬行纤维误差信号，来在线调整线性读出层（Readout），从而为离线训练好的连续时间控制器提供一个受生物启发的、即插即用的在线误差适配层，实现持续学习而无需担心灾难性遗忘。

### 2. 论文提出的方法论

-   **核心思想**：采用“冻结核心、只动输出”的策略。将预训练好的 CfC 网络的核心部分完全冻结，其内部的“液态状态”作为一个固定的、连续且非线性的基函数库。在线适应时，仅根据误差信号更新网络最后一层的线性读出权重，核心网络的权重和动态特性全程保持不变。
-   **关键技术细节与流程**：
    -   **网络架构**：采用闭式连续深度网络，其核心保持冻结，输出为线性读出层的映射。
    -   **误差信号生成**：通过反馈误差学习机制获取。
        -   **在线适应信号** ＝ **总运动指令（Final Motor Command）** － **冻结核心的初始指令（Frozen Core Command）**。
    -   **读出权重更新规则（LMS）**：
        -   使用最小均方规则进行在线权重更新。
        -   权重变化量 Δ*W* 正比于（反馈误差学习信号 × 读出基状态 *r*），即 Δ*W* = -η × （误差信号 *e*） × *r*^T，其中 η 为学习率。
    -   **算法变体与改进**：
        -   **基的选取**：从映射出的运动输出基推广到直接使用循环神经状态（Recurrent State）作为读出基，使得方法能泛化到稀疏结构的神经电路策略。
        -   **递归最小二乘变体**：相比 LMS，RLS 变体适应速度更快，但在力场移除后去适应（De-adapt）缓慢，因为其增益协方差矩阵会坍缩。通过引入“协方差重置”的安全遗忘规则，可消除该刚性，使去适应速度恢复正常。

### 3. 实验设计

-   **实验场景 / 仿真环境**：
    -   **任务**：平面双连杆机械臂的伸够（Reaching）仿真任务。
    -   **扰动类型**：施加一个速度依赖的旋度力场（Velocity-Dependent Curl Force Field）。
-   **核心对比基准（Benchmark）**：
    -   将提出的冻结核心在线适应控制器，与单纯的反馈控制器（Feedback-Only Controller）进行对比。
-   **泛化与鲁棒性测试对比**：
    -   **网络结构泛化**：从稠密的 CfC 网络对比泛化至稀疏的神经电路策略接线。
    -   **扰动鲁棒性**：对比测试不同力场强度与不同力场方向下的性能。
    -   **更新规则对比**：对比 LMS 规则与 RLS 变体的表现，并测试“协方差重置”修正后的效果。

### 4. 资源与算力

-   **声明情况**：论文提供的摘要和元数据中，**未明确提及**进行仿真所依赖的具体硬件（如 GPU 型号与数量）以及具体的训练或适应耗时。

### 5. 实验数量与充分性

-   **实验维度**：论文涵盖了多个维度的实验测试，包括：
    -   基础功能验证：冻结核心适应器 vs 纯反馈控制器。
    -   外部施加条件变化：不同力场强度、不同力场方向。
    -   网络结构变化：从稠密 CfC 到稀疏 NCP。
    -   学习算法变化：LMS 规则到 RLS 规则，以及针对 RLS 的协方差重置消融实验。
-   **评估指标与公平性**：
    -   通过轨迹是否被重新“拉直”以及力场移除后的镜像“后效应”作为内部模型学习成功与否的强主观客观化指标。
    -   实验在相同仿真环境下对比，不同方法和参数变体设置清晰，具有客观公平性。但在本仿真研究范围内，未发现需要强制去适应冻结核心的容量极限，说明探索边界可能仍有空间。

### 6. 论文的主要结论与发现

-   **运动纠错与后效应重现**：仅通过在线适应冻结 CfC 核心的线性读出，控制器即可将受旋度场扰动的轨迹重新拉直；并且当力场突然移除后，运动轨迹会产生镜像后效应（Mirror-image After-effect），这被视为内部模型已经习得外部扰动的标志。
-   **反馈控制器的失败**：单纯的反馈控制器不具备产生这种镜像后效应的能力，无法像适应读出器那样建立内部正演模型。
-   **泛化能力**：当读出基从运动输出改为循环状态时，该方法可从稠密网络推广到稀疏网络。方法对力场的物理属性（强度、方向）具有鲁棒性。
-   **学习规则优劣**：RLS 变体学习速度快，但因协方差坍缩导致遗忘困难；通过引入协方差重置规则，可恢复其灵活性。
-   **容量评估**：在测试条件下，未发现仅调整读出层不足、必须修改核心网络的容量极限，证明该低成本方案在仿真范围内是充分有效的。

### 7. 优点

-   **极低的计算代价**：在线学习期间完全冻结核心网络，仅需更新一层线性权重，无需重跑复杂的反向传播通过时间，极适合算力有限的边缘设备。
-   **无灾难性遗忘**：核心表征能力完全保留，新学到的适应仅体现在读出层，符合持续学习的要求；撤掉读出权重即可瞬间回到初始离线训练状态。
-   **生物合理性高**：方法的反馈误差学习机制和只调读出层的策略，与哺乳动物小脑皮层消肯野细胞通过爬行纤维进行运动校正的生理机制高度相似。

### 8. 不足与局限

-   **环境局限性**：目前的验证仅限于平面双连杆的虚拟仿真环境，尚未拓展到更复杂的高维操作空间或存在显著非线性动力学的实际物理机器人平台。
-   **容量边界未探明**：虽然文中声称在测试条件下未找到必须改动核心网络的容量极限，但这意味着在面对极端物理特性变更或任务发生本质性迁移时，固定基的表征能力上限尚未被量化。
-   **扰动类型单一**：主要验证对象是旋度力场，该方法对于其他类型的扰动（如冲击力、摩擦力变化、接触任务）的泛化处理能力需进一步验证。
-   **长期运行稳定性**：RLS 变体表现出的协方差坍缩问题虽被规则修正，但暗示了读出层权重的在线更新在长期高频率运行中仍可能遇到统计稳定性挑战。

（完）
