---
title: Language Modeling Materializes a World Model of Protein Biology
title_zh: 语言建模实现了蛋白质生物学的世界模型
authors: "Candido, S., Hayes, T., Derry, A., Rao, R., Lin, Z., Verkuil, R., Wu, B. Z., Lee, J. S., Bruguera, E. S., Keval, J. A., Kopylov, M., Pak, J. E., Wu, W., Thomas, N., Mataraso, S., Hsu, A., Trotman-Grant, A. C., Fatras, K., dos Santos Costa, A., Badkundri, R., Akin, H., Oktay, D., Deaton, J., Montabana, E., Sitwala, H., Yu, Y., Wiggert, M., Carlin, D. A., Goering, A. W., Blazejewski, T., Sandora, M., Hla, M., Jia, T. Z., Kloker, L. H., Sofroniew, N. J., Uehara, M., Pannu, J., Bachas, S., Liu, D. S., Sercu, T., Rives, A."
date: 2026-06-04
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.03.729735v1.full.pdf"
tags: ["query:world-model"]
score: 9.0
evidence: 提出通过语言建模实现蛋白质生物学世界模型
tldr: 蛋白质是生命基础，其生物学复杂性远超实验表征能力。本研究提出语言建模学习统一、可扩展的蛋白质表示，构建了结构预测模型，在生物分子复合物预测上超越现有方法，包括抗体-靶标相互作用。简单搜索策略成功发现纳摩尔亲和力的迷你蛋白和单链抗体，实验成功率极高。研究揭示表示空间系统组织，生成包含68亿序列和11亿结构的综合图谱，连接已知与未知生物学，实现从原子到进化尺度的蛋白质世界模型。
source: biorxiv
selection_source: fresh_fetch
motivation: 由于蛋白质生物学复杂且实验方法有限，需要能够表示整个蛋白质组的统一模型。
method: 采用语言建模学习蛋白质序列的统一表示，并构建结构预测模型，通过简单搜索进行设计。
result: 模型在生物分子复合物预测上超越现有方法，并成功设计出纳摩尔亲和力的蛋白和抗体。
conclusion: 语言建模作为蛋白质生物学的世界模型，连接原子级相互作用与进化尺度图谱。
---

## 摘要
蛋白质是生命的基础。其生物学的全部范围超出了我们在物理实验室中通过实验方法进行表征的能力。准确的数字表征可以通过虚拟实验加速蛋白质生物学的发现。我们提出使用语言建模来学习统一且通用的表征，这些表征可以扩展到蛋白质生物学的全部。基于这些表征，我们开发了一个结构预测模型，在生物分子复合物预测方面的表现超越了现有方法，涵盖了包括抗体与其靶标相互作用的基准测试。一个简单的搜索过程在发现具有纳摩尔结合亲和力的微型蛋白和单链抗体方面取得了较高的实验成功率，后者对于治疗设计至关重要。对语言模型表征空间中概念的研究揭示了一个系统化的组织，与通过经验科学发展的蛋白质还原论理解相一致。利用这种组织，我们生成了一个全面的蛋白质生物学图谱，包含超过68亿个序列和11亿个预测结构，识别了已知和未知生物学之间的联系。总体而言，这表明语言建模是表征蛋白质生物学的强大基础，其运作尺度从原子层面蛋白质相互作用的预测和设计，到不同粒度和抽象层次上蛋白质属性的识别，再到跨越数十亿年进化过程中蛋白质之间联系图谱的绘制。

## Abstract
Proteins are fundamental to life. The full extent of their biology is beyond our ability to characterize with experimental approaches in the physical laboratory. Accurate digital representations could accelerate the discovery of protein biology through virtual experiments. We propose language modeling to learn unified and general representations that can be scaled to all of protein biology. Building on these representations, we develop a structure prediction model that exceeds the performance of established methods for biomolecular complex prediction across benchmarks, including for the interactions of antibodies with their targets. A simple search procedure yields high experimental success rates for the discovery of proteins with nanomolar binding affinities for both miniproteins and single-chain antibodies, a modality critical for therapeutic design. Study of the concepts in the language models representation space reveals a systematic organization aligned with the reductionist understanding of proteins developed through empirical science. Leveraging this organization, we generate a comprehensive map of protein biology encompassing over 6.8 billion sequences and 1.1 billion predicted structures, identifying connections across known and unknown biology. As a whole, this shows language modeling as a powerful substrate for representing the biology of proteins, operating across scales from the prediction and design of protein interactions at the atomic level, to identifying properties of proteins at different levels of granularity and abstraction, to the scale of mapping connections between proteins across billions of years of evolution.

---

## 论文详细总结（自动生成）

好的，这是对给定论文的中文总结。

---

### 论文总结：语言建模实现了蛋白质生物学的世界模型

#### 1. 核心问题与整体含义
- **背景与动机**：蛋白质是生命的基础，但其生物学功能的完整景观远远超出了当前实验方法（如结构解析、功能检测）的表征能力。传统的试管实验手段无法满足对庞大蛋白质组进行系统性、高效探索的需求。
- **核心问题**：如何创建一种统一、可扩展、并能跨越不同尺度（从原子相互作用到进化关系）的数字表示，以加速蛋白质生物学的发现？现有的模型（如仅用于结构预测的模型）往往是特定于任务的，缺乏生物学本质的统一理解。
- **整体含义**：本文提出，**语言建模**可以学习蛋白质序列的统一表征，从而构建一个完整的“蛋白质生物学世界模型”。该模型不仅能预测结构，还能进行设计、揭示概念组织，并绘制数百万物种的蛋白质图谱，将计算模型从单一任务工具提升为生物学基础基石。

#### 2. 论文提出的方法论
- **核心思想**：将蛋白质序列视为“生物语言”，采用大规模自监督语言建模（如掩码语言建模或自回归建模）在超过68亿条蛋白质序列上进行预训练，学习能够蕴含蛋白质进化、结构、功能及相互作用等全部信息的分布式表示。
- **关键技术细节**：
    - **统一表征学习**：通过语言模型训练，将每个氨基酸表示为一个高维向量。这些表示捕获了序列的上下文信息，隐式编码了蛋白质的物理化学性质和进化约束。
    - **结构预测模型构建**：基于上述语言模型产生的表示（作为输入特征），进一步训练一个专用的结构预测模块（可能是类似AlphaFold的架构），用于预测生物分子复合物的三维结构。该模型在抗体-抗原等复合物上展现优越性能。
    - **简单搜索策略**：利用语言模型表征空间，通过简单的搜索（如最近邻搜索、定向进化筛选或直接序列匹配）来发现具有指定功能（如纳摩尔级亲和力）的新蛋白，而不是复杂的从头设计。
- **流程说明**：
    1.  使用语言模型对海量序列进行预训练，获得通用表示。
    2.  该表示空间自然形成层次化组织（如从原子到进化等级）。
    3.  利用该表示作为基础，训练下游任务模型（如结构预测）或直接进行基于搜索的设计。
    4.  最终，利用该表示的全景性，生成了一个包含68亿序列和11亿预测结构的综合性图谱，跨越已知和未知生物学领域。

#### 3. 实验设计
- **数据集/场景**：未详细列出，但涉及：
    - 用于预训练的超大规模蛋白质序列数据库（超过68亿条）。
    - 用于结构预测的**生物分子复合物**基准，包括**抗体与其靶标相互作用**的测试集。
    - 用于蛋白设计实验的**微型蛋白**和**单链抗体**。
- **基准 (Benchmark)**：在结构预测方面，对标现有最先进的方法（未点名，但可推断为如AlphaFold-Multimer等复合物预测方法），并声称超越了它们。
- **对比方法**：在结构预测基准上与已建立的方法进行了对比（具体方法名称未在摘要中给出）。在设计实验中，未明确与哪些方法对比，而是强调了极高的实验成功率。

#### 4. 资源与算力
- **未明确说明**：论文的摘要及提供的信息中**没有提及**使用的具体GPU型号、数量、训练时长或总计算成本。这是信息缺失点。仅可推断其规模极大（处理68亿序列）。

#### 5. 实验数量与充分性
- **实验数量**：从摘要看，实验覆盖了多个层面：
    - **结构预测**：在多个基准测试（包括抗体复合物）上进行验证。
    - **蛋白设计**：对**微型蛋白**和**单链抗体**两种模态进行了实验，并物理实现了结合。
    - **表征分析**：研究了语言模型表征空间中的概念（如功能、结构域、进化类群）组织。
    - **图谱生成**：生成了包含68亿序列和11亿结构的大规模图谱，验证了模型覆盖度。
- **充分性与公平性**：
    - **优点**：实验覆盖面较广，从预测到设计，从微观到宏观。设计部分的**实验成功率很高**，且物理验证了纳摩尔级亲和力，说服力强。对表征空间组织的分析是高度创新的，连接了模型与经验科学。
    - **不足**：摘要中未披露结构预测基准的具体细节（如数据集大小、是否使用了最新的公共基准），也未明确提及消融实验（如去掉不同规模的数据对表征质量的影响）。因此，**公平性**难以完全评判，因为缺乏与对照方法在标准metrics上的详细数值对比。仅凭“超越”的表述不足以评判其统计显著性。

#### 6. 论文的主要结论与发现
- **主要结论**：语言建模是表征蛋白质生物学的强大基础，能够构建一个跨越原子、分子、功能及进化尺度的“世界模型”。
- **关键发现**：
    1.  从语言模型学到的表示可以直接用于**高精度结构预测**，特别是复杂的生物分子复合物。
    2.  在该表示空间中进行**简单的搜索**，可以高效设计出具有高亲和力（纳摩尔级）的微型蛋白和单链抗体，实验成功率极高。
    3.  模型的表示空间展现出**系统化的组织**，与通过传统实验科学建立的对蛋白质还原论的理解（如结构域、功能注释等）高度一致。
    4.  模型生成了一个**全面图谱**，连接了已知的生物学通路与未知的蛋白质家族，实现了前所未有的覆盖度。

#### 7. 优点
- **统一性与可扩展性**：使用单一模型框架同时处理预测、设计、图谱绘制等多种任务，避免了为每项任务独立训练模型，体现了“世界模型”的优雅。
- **实验验证说服力强**：设计出的蛋白经过物理实验（体外实验）验证了纳摩尔级亲和力，这比仅依赖计算指标更有力。
- **创新性视角**：将表征空间内部的结构与科学界几十年来建立的还原论知识对齐，为人工智能模型的可解释性和生物学知识的数字化提供了新范式。
- **规模宏大**：生成了68亿序列和11亿结构的图谱，是迄今为止最大的蛋白质生物学图谱之一，为后续研究提供了丰富的资源。

#### 8. 不足与局限
- **计算成本未披露**：缺乏具体的资源消耗报告，使得其他研究团队难以评估其复现成本和可行性。这可能是数据中心（如Google/DeepMind）论文的常见不足。
- **设计过程的简单性存在风险**：虽然“简单搜索”是优势，但也可能暗示该方法对初始数据分布高度依赖，对于高度新颖或非天然的结构（如完全新的折叠）可能失效。
- **实验验证的深度有限**：摘要中仅提及纳摩尔级亲和力，未提及这些设计的蛋白是否具有理想的稳定性、可溶性或体内有效性。体外亲和力高不一定保证治疗可行性。
- **偏差风险**：预训练数据（68亿序列）可能存在偏差（如偏向于某些模式生物或已知家族），这可能影响对所有未知生物学的公平表示。图谱中“未知”部分的准确性需要更多实验验证。
- **基准比较不充分**：仅声称“超越现有方法”，但未提供具体基准名称、评价指标及误差范围，读者无法独立评估其优势有多显著。

---

（完）
