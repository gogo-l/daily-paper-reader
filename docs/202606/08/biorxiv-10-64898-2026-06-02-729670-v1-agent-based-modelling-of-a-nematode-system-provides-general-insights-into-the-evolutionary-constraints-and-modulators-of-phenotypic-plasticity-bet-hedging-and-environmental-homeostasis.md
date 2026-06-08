---
title: "Agent-based modelling of a nematode system provides general insights into the evolutionary constraints and modulators of phenotypic plasticity, bet-hedging, and environmental homeostasis"
title_zh: 基于主体的线虫系统建模为表型可塑性、赌注对冲和环境内稳态的进化约束与调节因子提供一般性见解
authors: "Tarantino, R."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729670v1.full.pdf"
tags: ["query:continual"]
score: 9.0
evidence: 基于主体的模型使用进化算法研究波动环境中可塑基因型的适应性。
tldr: 生物体在波动环境中选择表型可塑性还是bet-hedging是进化生物学核心难题。本研究利用基于代理的模型，以线虫Pristionchus pacificus为对象，模拟在周期性食物波动下塑性基因型与非塑性基因型的竞争，探索内在成本、环境波动时间尺度和塑性程度的影响。结果显示，无成本时中长环境稳定期和高塑性水平有利于塑性演化，但引入成本后纯bet-hedging更优，塑性频率骤降至平台期，且适应不对称是塑性入侵的必要条件。这些发现揭示了混合策略系统对微小变量变化的敏感性，表明存在进化相变和关键约束，为理解表型可塑性演化提供了一般性见解。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究波动环境下生物表型可塑性与bet-hedging策略的进化权衡与调节机制。
method: 采用代理模型模拟线虫P. pacificus嘴型二态性系统，调节塑性成本、环境波动周期和塑性程度，追踪eud-1基因频率。
result: 无成本时中长环境稳定期和高塑性促进塑性进化；成本引入使bet-hedging占优，引发塑性频率崩溃和相变现象；适应不对称是塑性入侵非塑性群体的条件。
conclusion: 该研究证实混合策略系统对关键参数敏感，揭示进化相变和约束，深化了对可塑性、bet-hedging和环境稳态演化的理解。
---

## 摘要
在本研究中，我实现了一个基于主体的模型，旨在探索在食物资源周期性波动的数字环境中可塑性与非可塑性基因型之间的竞争，利用二态性线虫Pristionchus pacificus作为混合策略系统的代理，该系统表现出随机性和条件性表型生产的组合。监测了响应三个主要变量变化而产生的新兴行为，即i）可塑性的内在成本，ii）环境波动的时间尺度，以及iii）可塑性程度，涉及发育开关基因eud-1的两个等位基因的固定频率和时间，一个等位基因能够实现口型二态性和捕食，另一个导致组成型表达单一、细菌食性的形态。有趣的是，虽然在无成本条件下中等至长期的环境稳定性（以世代计）和更高水平的可塑性可能有利于可塑性策略的进化，但可塑性的内在成本的引入和增加可能使纯赌注对冲更加有利，诱导可塑性菌株固定频率和菌株共存时间的连续崩溃，并使非可塑性突变体的入侵更可能发生，直到达到一个平台期。此外，两种形态之间的适合度不对称性可能是使可塑性基因型得以入侵非可塑性种群的近乎必要条件。总的来说，在确认一些先前的理论发现的同时，这些结果可能揭示了混合策略系统对关键变量的即使微小变化的敏感性，暗示了相变和关键进化约束的存在。

## Abstract
In this study, I implemented an agent-based model aimed at exploring the competition between plastic and non-plastic genotypes in a digital environment with periodic fluctuations in food resources, using the dimorphic nematode Pristionchus pacificus as a proxy for mixed-strategy systems showing a combination of stochastic and conditional phenotype production. Emerging behaviours generated in response to variation in three main variables, that is, i) intrinsic cost of plasticity, ii) timescale of environmental fluctuation, and iii) degree of plasticity, were monitored in terms of frequency and time to fixation of two alleles of the developmental switch gene eud-1, one enabling mouth-form dimorphism and predation, the other leading to the constitutive expression of a single, bacterivorous morph. Interestingly, while intermediate-to-long periods of environmental stability (in terms of generations) and a higher level of plasticity might favour the evolution of plastic strategies in a cost-free condition, the introduction and increase of inherent costs of plasticity could make pure bet-hedging more advantageous, induce a sequential collapse in the frequency of fixation of plastic strains and time of coexistence between strains, and make the invasion by non-plastic mutants more likely until a plateau is reached. In addition, asymmetries in fitness between the two morphs might be an almost necessary condition to enable the invasion of a non-plastic population by plastic genotypes. Collectively, while confirming some previous theoretical findings, these outcomes could uncover the sensitivity of a mixed-strategy system to even small changes in key variables, suggesting the existence of phase transitions and critical evolutionary constraints.

---

## 论文详细总结（自动生成）

好的，以下是对这篇论文的结构化中文总结。

### 1. 论文的核心问题与整体含义

*   **核心问题**：本研究旨在探究在环境波动（特别是周期性食物资源变化）下，生物体的表型可塑性（Phenotypic Plasticity）、赌注对冲（Bet-hedging）和环境稳态（Environmental Homeostasis）三种策略的进化权衡、约束条件及调节因子。具体聚焦于一个同时具备随机性（赌注对冲）和条件性（可塑性）表型产生的混合策略系统。
*   **研究动机与背景**：理解基因型与表型的关系是生物学的基石。已有众多分析模型和数字进化研究探讨了可塑性进化的条件（如环境异质性、线索可靠性、成本），但本研究试图更进一步，通过构建一个基于真实生物系统（线虫 *Pristionchus pacificus* 的口型二态性）参数的代理模型，整合随机性和条件性两种策略，系统性地探索内在成本、环境波动时间尺度和可塑性程度这三个关键变量如何影响可塑与非可塑基因型间的竞争。
*   **整体含义**：研究发现混合策略系统的进化结果对关键参数的微小变化极为敏感，可能存在进化上的“相变”和“关键约束”。这不仅验证了部分已有理论，还为理解可塑性、赌注对冲等策略的演化提供了更精细、更具动态性的新见解，并可潜在地推广到具有相似结构特征的其他物种。

### 2. 方法论

*   **核心思想**：采用**基于主体的模型（Agent-Based Model, ABM）**，通过模拟大量遵循简单规则的独立个体（线虫）在特定虚拟环境中的互动与繁衍，观察系统层面涌现出的宏观进化模式（等位基因的固定频率和时间）。
*   **关键技术细节**：模型名为 **PhePlastiComp**，使用 **NetLogo 6.2.0** 平台实现。
    *   **主体与环境**：模型包含*P. pacificus* 线虫、作为猎物的*C. elegans* 线虫、作为食物的*E. coli* 细菌，以及代表培养皿的二维网格环境。环境变量（食物）可固定或周期性波动。
    *   **生物过程模拟**：每个时间步模拟1小时生命。线虫在820个时间步（约82小时，即实际寿命）内完成一个非重叠世代，期间经历移动、取食、发育、繁殖和死亡。
    *   **核心决策模拟**：关键发育决策是口型（Eurystomatous (EU，捕食型） vs Stenostomatous (ST，细菌食性)）的不可逆选择。该决策由基因型、环境和随机性共同决定。基因型由X染色体上的开关基因*eud-1*决定（‘+’等位基因为可塑，‘e’为组成型ST）。不同基因型在不同环境下的EU/ST表达比率（包括随机性和条件性响应）在文中表1中给出。
    *   **适合度计算**：繁殖通过自交（主要）或偶尔异交进行，遵循孟德尔分离定律。最终的子代数量由一个核心公式（1）计算：
        `no = 100 - [(1-iab) * Cs] - (ipl * CP) + (iEU * Bpr * nk) + (iST * Bfd * iab)`
        该公式从基线100个子代出发，根据个体是否经历饥饿（Cs）、是否携带可塑基因型（Cp）、是否表现出EU或ST形态并因此获得捕食（Bpr）或快速发育（Bfd）的收益等进行加减。每个世代的亲本根据此公式计算产生的子代数量。

### 3. 实验设计

实验并未使用外部数据集，而是通过设定不同参数组合来构建模拟场景。

*   **实验场景**：主要有两大类：
    1.  **对称性分析（SAs）**：初始状态为可塑菌株（`++`）与非可塑菌株（`ee`）个体数相等（各150只），用于观察竞争动态。
    2.  **可入侵性分析（IAs）**：模拟更现实的场景，如99%的非可塑种群中出现1个突变/迁入的可塑个体（或反之），以测试菌株从稀有中建立起来的能力。
*   **评估基准**：未设置外部基准，而是通过回答不同参数组合下，哪个等位基因（`+`或`e`）最终被固定（以及固定的频率和时间）来评估策略的成功。
*   **参数对比**：主要操纵和对比以下关键参数：
    *   **环境变化时间尺度**（`Environmental-Cycles`）：1， 5， 10， 15， 20代
    *   **可塑性程度**（`Degree-of-Plasticity-%`）：0， 10， 20
    *   **内在可塑性成本**（`Cost-of-Plasticity-%`）：0， 1, 2， 3
    *   **两种口型间的适合度收益差**（`Benefit-of-Predation-%` vs `Benefit-of-Faster-Development-%`）：组合成0%、1%、2%的差值。

### 4. 资源与算力

*   **算力说明**：论文中**未明确提及**使用任何特定类型的GPU或大规模计算集群，也未提及具体的模型训练时长。由于这是基于主体的模拟，其计算负载主要取决于代理数量和模拟步数，通常在普通个人电脑上即可完成，但论文未就此提供细节。

### 5. 实验数量与充分性

*   **实验数量**：论文进行了大量的模拟运行以确保统计稳健性。
    *   每个SA场景的每种参数配置执行100次独立运行。
    *   每个IA场景的每种参数配置执行1000次独立运行。
    *   从表3B看，总计有数十种参数组合，因此总模拟次数超过十万次。
*   **充分性与客观性**：通过高重复次数，作者有效降低了随机性带来的影响，使观察到的模式具有统计意义。实验系统地探索了多个关键变量的参数空间，并设计了从“公平竞争”（SA）到“稀有入侵”（IA）的不同生态现实度场景，设计是严谨和充分的。此外，还对部分参数进行了敏感性分析，以验证模型的鲁棒性。

### 6. 主要结论与发现

*   **无成本条件下可塑性的优势**：在无内在可塑性成本（Cost = 0）时，可塑性策略总是优于非可塑性策略。中等至长期的环境稳定性（10-15代）和更高的可塑性水平对可塑基因型更有利。
*   **内在成本的关键作用**：内在成本是系统行为的关键调节器。即使引入极小的成本（1%），也会导致可塑性菌株的固定频率急剧下降。当成本≥2%时，可塑性菌株可能完全无法固定，揭示了从“并存”到“非塑固定”的相变。
*   **混合策略的选择**：如果高可塑性伴随着成本，一种可能的进化路径是保留纯粹的随机（赌注对冲）策略，因为它可能无需付出维持复杂感应机制的成本。任何介于纯随机和纯高可塑性之间的中间状态都可能遭受更大的选择惩罚。
*   **入侵的困难与条件**：非可塑性突变体在内部，甚至在波动环境中入侵可塑性种群是可能的，只要有内在成本存在。相反，可塑性基因型要入侵非可塑性种群极其困难，即使环境波动。**关键条件是**：可塑性必须无内在成本，且可塑性基因型独有的形态（EU型）需要有明显更高的适合度收益（收益差≥2%）。

### 7. 优点

*   **真实的代理模型设计**：模型参数和规则高度依托于一个真实的模型生物系统（*P. pacificus*）的经验数据，增强了模拟结果与现实生物的关联性，超越了纯理论模型。
*   **整合混合策略**：巧妙地模拟了“条件可塑性”和“随机赌注对冲”共存这一复杂但在自然界真实存在的策略，并对其不同组合进行了分析。
*   **对相变现象的揭示**：通过系统改变参数，清晰地展示了内在成本增加时，系统从一种状态到另一种状态的**跃变和不连续性**，深化了对进化动力学中非线性特征的理解。
*   **全面的实验设计**：对称性分析（SA）和可入侵性分析（IA）的结合，从“优势竞争”和“稀有建立”两个不同但关键的进化视角审视了问题。

### 8. 不足与局限

*   **物种特异性与泛化性**：模型参数是基于 *P. pacificus* 的特定生物学细节（如遗传细节、特定基线表型比率、主要为自交等）构建的。尽管作者认为定性模式可能在具有相似特征的物种中保留，但结论的直接外推需谨慎。
*   **环境模式的简化**：模拟中假设的是规律的、周期性的环境波动。然而，自然界的环境波动往往是随机的和不可预测的。模型未探索“不可预测波动”这一条件下混合策略的表现，而这对赌注对冲理论至关重要。
*   **忽略的生物学细节**：模型未考虑可能的突变累积、基因多效性（一个基因影响多个性状）、复杂的空间异质性或更精细的表观遗传调控，这些在真实进化过程中可能扮演重要角色。
*   **成本的简化假设**：假设内在可塑性成本在杂合子（`+e`）上完全体现，而在纯合突变体（`ee`）上完全消失。这是一个关键但简化的假设，实际情况可能更复杂。

（完）
