---
title: Climbing-fiber-like online readout adaptation in frozen continuous-time networks reproduces force-field adaptation and after-effects
title_zh: 冻结连续时间网络中类似爬纤维的在线读出适应复现力场适应与后效应
authors: "Kobayashi, J."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.11.731593v2.full.pdf"
tags: ["query:continual"]
score: 7.0
evidence: 冷冻连续时间网络中的在线读出自适应实现无需遗忘的持续电机控制
tldr: 连续时间网络离线训练后缺乏在线校准机制，难以应对受控对象动态变化。本研究冻结CfC核心，仅在线适应线性读出层，使用类似攀爬纤维的反馈误差学习信号和LMS规则。结果显示，该方案能校正旋度力场下的弯曲轨迹，并在力场移除后产生镜像后效应，且推广至稀疏NCP结构。这为离线训练控制器提供了一种生物启发的低成本在线适应层。
source: biorxiv
selection_source: fresh_fetch
motivation: 连续时间模型缺乏在线重校准机制，需一种低成本、生物启发方法应对动态环境变化。
method: 冻结CfC网络核心，基于反馈误差学习信号和LMS规则在线适应线性读出层，模拟小脑攀爬纤维学习。
result: 力场中轨迹重新变直，移除后出现镜像后效应；方案推广至稀疏NCP，对力场强度和方向鲁棒；RLS变体需安全遗忘规则避免去适应缓慢。
conclusion: 仅适应读出层即可实现有效的在线误差校准，无需改变冻结核心，为离线训练的连续时间控制器提供低成本适应方案。
---

## 摘要
基于液体神经网络及相关连续时间模型（如LTC和CfC）的机器人运动控制通常通过随时间反向传播离线训练，并且缺乏在机械臂动力学变化时进行在线重校准的显式机制。我们探讨一个冻结的CfC核心，其液体状态跨越固定的连续时间基，能否通过仅用类似爬纤维的错误信号适应其线性读出，来支持小脑风格的在线适应。在一个具有速度依赖的旋度力场的平面双连杆到达仿真中，我们在最小均方规则下使用反馈误差学习信号在线适应读出，而保持核心不变。只有读出层可调的冻结核心控制器重新拉直了被旋度力扰动的到达轨迹，并且在撤除力场后产生了镜像后效应——这一内部模型学习的标志——而纯反馈控制器则不会产生。当使用递归状态而非投射的运动输出作为读出基时，该结果从密集CfC推广到稀疏神经电路策略（NCP）布线；它对力场强度和方向具有鲁棒性；递归最小二乘变体适应更快，但因协方差坍缩导致去适应缓慢，而一种协方差重置安全遗忘规则可消除这种刚性。在我们探索的双连杆平面仿真范围内，未发现在测试条件下需要适应冻结核心的容量极限。因此，在本仿真研究中，仅适应读出为离线训练的连续时间控制器提供了一个生物启发且低成本的在线误差适应层。

## Abstract
Robotic motor control built on liquid neural networks and related continuous-time models, such as LTC and CfC, is typically trained offline via backpropagation through time and lacks an explicit mechanism for recalibrating online as plant dynamics change. We ask whether a frozen CfC core, whose liquid state spans a fixed continuous-time basis, can support cerebellar-style online adaptation by adapting only its linear read-out with a climbing-fiber-like error signal. In a planar two-link reaching simulation with a velocity-dependent curl force field, we adapt the readout online with a feedback-error-learning (FEL) signal under a least-mean-squares (LMS) rule, leaving the core untouched. The frozen-core readout-only controller re-straightens curl-perturbed reaches and, upon field removal, produces a mirror-image after-effect--the signature of internal-model learning--that a feedback-only controller does not produce. The result generalizes from a dense CfC to a sparse Neural-Circuit-Policy (NCP) wiring when the recurrent state, rather than the projected motor output, is used as the readout basis; it is robust to force-field strength and direction; and a recursive-least-squares variant adapts faster but de-adapts slowly because its covariance collapses, a rigidity that a covariance-reset safe-forgetting rule removes. Within the explored two-link planar simulation range, we did not find a capacity limit that would require adapting the frozen core in the tested conditions. In this simulation study, adapting only the readout therefore provides a biologically inspired, low-cost online error-adaptation layer for offline-trained continuous-time controllers.