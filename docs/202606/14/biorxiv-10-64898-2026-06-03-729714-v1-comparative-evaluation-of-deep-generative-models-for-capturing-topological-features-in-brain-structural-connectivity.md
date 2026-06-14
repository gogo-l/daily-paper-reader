---
title: Comparative Evaluation of Deep Generative Models for Capturing Topological Features in Brain Structural Connectivity
title_zh: 深度学习生成模型捕捉脑结构连接拓扑特征的比较评估
authors: "Kumada, C., Hiroyasu, T., Hiwa, S."
date: 2026-06-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729714v1.full.pdf"
tags: ["query:med-lifelong"]
score: 8.0
evidence: 评估生成模型用于大脑结构连接（源自MRI）
tldr: 结构性连接（SC）数据对脑网络分析至关重要，但其有限样本量妨碍机器学习模型泛化，深度生成模型虽用于数据增强，捕获复杂拓扑特征的能力仍待澄清。本研究比较VAE、WGAN-GP和DDPM三种模型在合成与真实SC数据上的表现，以图论指标评估生成质量。结果显示WGAN-GP在不同数据集和指标上表现最稳定，未出现严重性能退化；VAE和DDPM虽在特定方面优异却对数据特性敏感。此外所有模型难以完全复原平面性等全局约束，凸显标准生成模型不足，需将所需结构特性融入生成过程。
source: biorxiv
selection_source: fresh_fetch
motivation: 脑结构连接数据稀缺，阻碍模型泛化，而深度生成模型捕获其复杂拓扑特征的能力不明确。
method: 以VAE、WGAN-GP和DDPM为对象，在合成与真实SC数据上生成，采用图论指标和视觉检查比较生成质量。
result: WGAN-GP在各数据集上表现稳定，VAE与DDPM受数据特性影响大，所有模型均难完全复现平面性等全局约束。
conclusion: WGAN-GP可作为未来SC数据增强研究的平衡基线，标准模型无法完全捕获复杂拓扑，强调须将结构约束融入生成过程。
---

## 摘要
结构连接（SC）数据对脑网络分析至关重要，但基于SC的机器学习常因数据有限而影响模型泛化性和鲁棒性。尽管利用深度生成模型进行数据增强日益受到关注，不同模型如何捕捉SC数据中复杂的拓扑特征仍不明确。为阐明深度生成模型在生成SC时的学习特性，本研究比较了三种代表性模型：变分自编码器（VAE）、带梯度惩罚的Wasserstein生成对抗网络（WGAN-GP）和去噪扩散概率模型（DDPM）。我们使用具有已知特征的合成数据集与真实世界SC数据，对这些模型进行了系统评估。生成质量通过图论指标比较和生成邻接矩阵的可视化检查来评定。WGAN-GP在不同数据集和指标上表现相对稳定，未出现严重的性能衰减。相比之下，VAE和DDPM在特定方面表现良好，但对数据特性更敏感。这些发现提示，WGAN-GP可作为未来SC数据增强研究中最均衡的基线模型，而VAE和DDPM则可根据目标应用及所关注的结构特性灵活选用。此外，由于所有模型都难以完全复现平面性等严格的全局约束，我们的结果表明标准生成模型可能不足以捕捉SC数据复杂的拓扑特征，这凸显了将所需结构特性融入训练或生成过程的重要性。

## Abstract
Structural connectivity (SC) data are crucial for brain network analysis, but SC-based machine learning often suffers from limited data availability, hindering model generalization and robustness. Although data augmentation using deep generative models has attracted increasing attention, it remains unclear how different models capture the complex topological features of SC data. To clarify the learning characteristics of deep generative models for SC generation, this study compares three representative models: variational autoencoder (VAE), Wasserstein GAN with gradient penalty (WGAN-GP), and denoising diffusion probabilistic models (DDPM). We systematically evaluated these models using both synthetic datasets with known characteristics and real-world SC data. Generation quality was assessed using graph-theoretic metric comparisons and visual inspection of the generated adjacency matrices. WGAN-GP showed relatively stable performance across datasets and metrics, without severe performance degradation across evaluation settings. In contrast, VAE and DDPM performed well in specific aspects but were more sensitive to data characteristics. These findings suggest that WGAN-GP may serve as the most balanced baseline for future SC data augmentation studies, whereas VAE and DDPM may be useful depending on the target application and structural properties of interest. Furthermore, because all models struggled to fully reproduce strict global constraints such as planarity, our results suggest that standard generative models may be insufficient to capture the complex topological features of SC data. This highlights the importance of incorporating the desired structural properties into the training or generation process.