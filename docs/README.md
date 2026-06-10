<div class="dpr-home-notice-card">
  <h3 class="dpr-home-notice-title">🚀 Start Here</h3>
  <ul class="dpr-home-notice-list">
    <li><a href="#/tutorial/README">使用教程</a></li>
  </ul>
</div>

## 每次日报
- 最新运行日期：2026-05-12 ~ 2026-06-10
- 运行时间：2026-06-10 07:41:35 UTC
- 运行状态：成功
- 本次总论文数：42
- 精读区：0
- 速读区：42

### 今日简报（AI）
日报速览：聚焦 42 篇前沿速递，重点挖掘机器遗忘与代码隐私新风险。

最值得关注：实验证明“门控激活重定向”可实现推理阶段高效遗忘，而测试生成技术能精准探测大模型代码生成源的隐私泄露。

下步可优先复现这两种轻量防御方案，检视自家模型在遗忘与隐私边界上的真实表现。
- 详情：[/20260512-20260610/README](/20260512-20260610/README)

### 精读区论文标签
- 本次无精读推荐。

### 速读区论文标签
1. [Inference-Time Machine Unlearning via Gated Activation Redirection](/20260512-20260610/2605.12765v1-inference-time-machine-unlearning-via-gated-activation-redirection)  
   标签：评分：10.0/10、query:llm-anonym
   evidence：通过门控激活重定向在推理时实现遗忘，用于机器遗忘学习
2. [Probing Privacy Leaks in LLM-based Code Generation via Test Generation](/20260512-20260610/2605.15248v1-probing-privacy-leaks-in-llm-based-code-generation-via-test-generation)  
   标签：评分：10.0/10、query:llm-anonym
   evidence：直接处理代码生成大语言模型训练数据中个人身份信息的隐私泄露问题，提出测试驱动方法提取记忆化PII。
3. [Interference-Aware Multi-Task Unlearning](/20260512-20260610/2605.19042v1-interference-aware-multi-task-unlearning)  
   标签：评分：10.0/10、query:llm-anonym
   evidence：处理机器遗忘学习中的多任务干扰
4. [LLM Anonymization Against Agentic Re-Identificatio](/20260512-20260610/2605.30848v1-llm-anonymization-against-agentic-re-identificatio)  
   标签：评分：10.0/10、query:llm-anonym
   evidence：基于大模型的匿名化方法，抵御智能体网络搜索重新识别，兼顾隐私与效用
5. [LLM Anonymization Against Agentic Re-Identification](/20260512-20260610/2605.30848v2-llm-anonymization-against-agentic-re-identification)  
   标签：评分：10.0/10、query:llm-anonym
   evidence：基于LLM的文本匿名化抵御智能体再识别
6. [De-attribute to Forget for LLM Unlearning](/20260512-20260610/2605.30919v1-de-attribute-to-forget-for-llm-unlearning)  
   标签：评分：10.0/10、query:llm-anonym
   evidence：通过强化学习去归因遗忘数据来实现LLM遗忘
7. [Forgetting Has Neighbors: Localized Collateral Forgetting in Machine Unlearning](/20260512-20260610/2605.31317v1-forgetting-has-neighbors-localized-collateral-forgetting-in-machine-unlearning)  
   标签：评分：10.0/10、query:llm-anonym
   evidence：直接研究机器遗忘学习在实例层面的附带损害
8. [Fast Unlearning at Scale via Margin Self-Correction](/20260512-20260610/2606.02920v1-fast-unlearning-at-scale-via-margin-self-correction)  
   标签：评分：10.0/10、query:llm-anonym
   evidence：通过边缘自校正实现快速遗忘，高效移除训练示例
9. [PURGE: Projected Unlearning via Retain-Guided Erasure](/20260512-20260610/2606.03808v1-purge-projected-unlearning-via-retain-guided-erasure)  
   标签：评分：10.0/10、query:llm-anonym
   evidence：提出PURGE机器遗忘算法，选择性地擦除特定数据点并保持模型性能，直接实现了机器遗忘技术。
10. [KAN-CL: Per-Knot Importance Regularization for Continual Learning with Kolmogorov-Arnold Networks](/20260512-20260610/2605.12306v1-kan-cl-per-knot-importance-regularization-for-continual-learning-with-kolmogorov-arnold-networks)  
   标签：评分：9.0/10、query:continual
   evidence：使用KANs进行持续学习以防止灾难性遗忘
11. [Inference-Time Machine Unlearning via Gated Activation Redirection](/20260512-20260610/2605.12765v2-inference-time-machine-unlearning-via-gated-activation-redirection)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：通过门控激活重定向实现LLM推理时机器遗忘
12. [Locale-Conditioned Few-Shot Prompting Mitigates Demonstration Regurgitation in On-Device PII Substitution with Small Language Models](/20260512-20260610/2605.13538v1-locale-conditioned-few-shot-prompting-mitigates-demonstration-regurgitation-in-on-device-pii-substitution-with-small-language-models)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：端侧 PII 替换流程，结合区域条件少样本提示保持文本效用
13. [MetaMoE: Diversity-Aware Proxy Selection for Privacy-Preserving Mixture-of-Experts Unification](/20260512-20260610/2605.14289v1-metamoe-diversity-aware-proxy-selection-for-privacy-preserving-mixture-of-experts-unification)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：无需共享私密数据的隐私保护专家混合模型融合
14. [DP-SelFT: Differentially Private Selective Fine-Tuning for Large Language Models](/20260512-20260610/2605.17432v1-dp-selft-differentially-private-selective-fine-tuning-for-large-language-models)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：差分隐私选择性微调大语言模型，限制更新位置以改善隐私-效用权衡
15. [CATA: Continual Machine Unlearning via Conflict-Averse Task Arithmetic](/20260512-20260610/2605.18610v1-cata-continual-machine-unlearning-via-conflict-averse-task-arithmetic)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：通过冲突规避任务算术实现视觉语言模型的持续机器遗忘，支持序列化移除
16. [Causal Unlearning in Collaborative Optimization: Exact and Approximate Influence Reversal under Adversarial Contributions](/20260512-20260610/2605.20341v1-causal-unlearning-in-collaborative-optimization-exact-and-approximate-influence-reversal-under-adversarial-contributions)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：联邦学习中的因果遗忘以移除客户端数据，满足合规要求
17. [Approximate Machine Unlearning through Manifold Representation Forgetting Guided by Self Mode Connectivity](/20260512-20260610/2605.22871v1-approximate-machine-unlearning-through-manifold-representation-forgetting-guided-by-self-mode-connectivity)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：通过流形表征遗忘实现机器忘却，旨在执行被遗忘权。
18. [Kernel-Based ReLU Approximation for Homomorphic Encryption-Compatible Privacy-preserving Deep Learning Models](/20260512-20260610/2605.23641v1-kernel-based-relu-approximation-for-homomorphic-encryption-compatible-privacy-preserving-deep-learning-models)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：通过近似ReLU实现同态加密兼容的隐私保护深度学习，适用于大语言模型。
19. [Efficient DP-SGD for LLMs with Randomized Clipping](/20260512-20260610/2605.24879v1-efficient-dp-sgd-for-llms-with-randomized-clipping)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：利用随机裁剪的高效 DP-SGD 降低了大语言模型差分隐私训练的内存与计算开销
20. [SAE-FD: Sparse Autoencoder Feature Distillation for Continual Learning of Large Language Models](/20260512-20260610/2605.25525v1-sae-fd-sparse-autoencoder-feature-distillation-for-continual-learning-of-large-language-models)  
   标签：评分：9.0/10、query:continual
   evidence：稀疏自编码器特征蒸馏实现大语言模型的持续学习
21. [ICCU: In-Context Continual Unlearning via Pattern-Induced Refusal Rules](/20260512-20260610/2605.27138v1-iccu-in-context-continual-unlearning-via-pattern-induced-refusal-rules)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：基于上下文持续忘却的大语言模型框架，通过学习拒绝规则实现数据删除。
22. [Mask the Target: A Plug-and-Play Regularizer Against LoRA Forgetting](/20260512-20260610/2605.29498v1-mask-the-target-a-plug-and-play-regularizer-against-lora-forgetting)  
   标签：评分：9.0/10、query:continual
   evidence：即插即用正则化器防止LoRA微调中的灾难性遗忘
23. [Foundation-Preserving Adaptation via Generalized Rayleigh-Quotient Optimization](/20260512-20260610/2606.00132v1-foundation-preserving-adaptation-via-generalized-rayleigh-quotient-optimization)  
   标签：评分：9.0/10、query:continual
   evidence：通过广义瑞利商优化的遗忘记感知LoRA微调
24. [Multi-Objective Reference-Aligned Machine Unlearning](/20260512-20260610/2606.00399v1-multi-objective-reference-aligned-machine-unlearning)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：多目标机器遗忘框架，在保持效用的同时删除训练样本。
25. [Turning Back Without Forgetting: Selective Backward Refinement for Parameter-Efficient Continual Learning](/20260512-20260610/2606.01379v1-turning-back-without-forgetting-selective-backward-refinement-for-parameter-efficient-continual-learning)  
   标签：评分：9.0/10、query:continual
   evidence：参数高效持续学习的选择性反向精炼，实现反向知识迁移
26. [Turning Back Without Forgetting: Selective Backward Refinement for Parameter-Efficient Continual Learning](/20260512-20260610/2606.01379v2-turning-back-without-forgetting-selective-backward-refinement-for-parameter-efficient-continual-learning)  
   标签：评分：9.0/10、query:continual
   evidence：面向持续学习的向后知识迁移，避免灾难性遗忘
27. [Selective Token-Level Cryptographic Redaction for Privacy-Preserving Clinical Deployment of Large Language Models](/20260512-20260610/2606.03399v1-selective-token-level-cryptographic-redaction-for-privacy-preserving-clinical-deployment-of-large-language-models)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：通过令牌级加密编辑保护大模型临床部署中的敏感健康信息。
28. [Don't Forget Your Embeddings: Robust Knowledge Erasure via Precise Editing of Embeddings](/20260512-20260610/2606.03695v1-dont-forget-your-embeddings-robust-knowledge-erasure-via-precise-editing-of-embeddings)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：通过精确编辑词嵌入实现LLM知识擦除
29. [SharedRequest: Privacy-Preserving Model-Agnostic Inference for Large Language Models](/20260512-20260610/2606.05004v1-sharedrequest-privacy-preserving-model-agnostic-inference-for-large-language-models)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：通过批处理级混合与噪声实现LLM隐私保护推理
30. [Learning What to Forget: Improving LLM Unlearning via Learned Token-Level Importance](/20260512-20260610/2606.06320v1-learning-what-to-forget-improving-llm-unlearning-via-learned-token-level-importance)  
   标签：评分：9.0/10、query:llm-anonym
   evidence：提出针对大语言模型遗忘的令牌级重要性学习方法，直接处理目标知识删除问题。
31. [Reconstruction of Personally Identifiable Information from Supervised Finetuned Models](/20260512-20260610/2605.12264v1-reconstruction-of-personally-identifiable-information-from-supervised-finetuned-models)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：从监督微调的大语言模型中重建个人身份信息
32. [ICED: Concept-level Machine Unlearning via Interpretable Concept Decomposition](/20260512-20260610/2605.14309v1-iced-concept-level-machine-unlearning-via-interpretable-concept-decomposition)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：通过可解释概念分解实现视觉语言模型的概念级机器遗忘
33. [ICED: Concept-level Machine Unlearning via Interpretable Concept Decomposition](/20260512-20260610/2605.14309v2-iced-concept-level-machine-unlearning-via-interpretable-concept-decomposition)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：视觉语言模型的概念级机器遗忘
34. [Privacy Policy Enforcement Guardrails for Data-Sensitive Retrieval-Augmented Generation](/20260512-20260610/2605.17034v1-privacy-policy-enforcement-guardrails-for-data-sensitive-retrieval-augmented-generation)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：基于隐私策略的执行护栏，防止RAG系统中的上下文数据泄露
35. [Revisiting ML Training under Fully Homomorphic Encryption: Convergence Guarantees, Differential Privacy, and Efficient Algorithms](/20260512-20260610/2605.27782v1-revisiting-ml-training-under-fully-homomorphic-encryption-convergence-guarantees-differential-privacy-and-efficient-algorithms)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：全同态加密下的差分隐私训练，实现可扩展的隐私保护机器学习
36. [Private Embedding Lookup with Encrypted Compact Queries under Fully Homomorphic Encryption](/20260512-20260610/2606.03191v3-private-embedding-lookup-with-encrypted-compact-queries-under-fully-homomorphic-encryption)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：使用全同态加密实现嵌入查找的隐私保护，适用于大模型推理阶段隐私保护。
37. [Need to Know: Contextual-Integrity-Grounded Query Rewriting for Privacy-Conscious LLM Delegation](/20260512-20260610/2606.04067v1-need-to-know-contextual-integrity-grounded-query-rewriting-for-privacy-conscious-llm-delegation)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：基于情境完整性的查询重写，移除不必要的敏感信息以保护隐私
38. [Seeing Without Exposing: Adaptive Privacy Control for Open-World, Context-Hungry MLLMs](/20260512-20260610/2606.07175v1-seeing-without-exposing-adaptive-privacy-control-for-open-world-context-hungry-mllms)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：通过漂移敏感元素实现多模态大模型的自适应隐私控制
39. [Unveiling Privacy Risks in Multi-modal Large Language Models: Task-specific Vulnerabilities and Mitigation Challenges](/20260512-20260610/2606.09125v1-unveiling-privacy-risks-in-multi-modal-large-language-models-task-specific-vulnerabilities-and-mitigation-challenges)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：识别多模态大语言模型泄漏敏感图像数据的隐私漏洞
40. [Vision Language Model Helps Private Information De-Identification in Vision Data](/20260512-20260610/2606.09132v1-vision-language-model-helps-private-information-de-identification-in-vision-data)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：基于视觉语言模型的视觉数据中敏感文本去标识化
41. [Benchmarking Empirical Privacy Protection for Adaptations of Large Language Models](/20260512-20260610/2606.09401v1-benchmarking-empirical-privacy-protection-for-adaptations-of-large-language-models)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：对大语言模型适配中差分隐私保护的实证基准测试
42. [Clinically Grounded Privacy Evaluation of Medical LMs](/20260512-20260610/2606.09590v1-clinically-grounded-privacy-evaluation-of-medical-lms)  
   标签：评分：8.0/10、query:llm-anonym
   evidence：基于临床的医疗语言模型患者信息泄漏评估


<div class="dpr-home-promo-card">
  <h3 class="dpr-home-promo-title">💬 社区与支持</h3>
  <ul class="dpr-home-promo-list">
    <li>欢迎 Star / Fork / Issue / PR</li>
    <li>QQ群：583867967（欢迎交流，已有：1151人）</li>
  </ul>
</div>
