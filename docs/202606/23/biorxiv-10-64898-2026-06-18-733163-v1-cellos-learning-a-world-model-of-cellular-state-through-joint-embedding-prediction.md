---
title: "CellOS: Learning a World Model of Cellular State through Joint Embedding Prediction"
title_zh: "CellOS: 通过联合嵌入预测学习细胞状态的世界模型"
authors: "Zhou, Q., Le, Y., Qi, X., Chang, S., Lu, H., Wu, Y., Wang, H., Ran, R., li, x."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733163v1.full.pdf"
tags: ["query:world-model"]
score: 9.0
evidence: 世界模型概念应用于细胞状态
tldr: 现有单细胞基础模型多从单一基因表达视图学习，无法显式协调互补视图。CellOS提出多视图基础模型，通过三阶段训练（因果细胞句子建模、密集到专家混合扩展、LLM-JEPA对齐）学习配对表达与感知视图。在3.905亿单细胞转录组上训练120亿参数模型，在细胞状态注释、批次整合和扰动响应预测等基准上超越现有方法。结果表明，互补视图的预测对齐为实现可扩展的表征中心细胞世界模型和可迁移AI虚拟细胞提供了可行路径。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞基础模型局限于单一基因表达视图，无法兼容和协调互补的细胞状态视图。
method: CellOS采用三阶段训练：因果细胞句子语言建模、函数保持的密集到专家混合扩展、LLM-JEPA潜空间对齐。
result: 120亿参数模型在3.905亿单细胞转录组上训练，在细胞状态注释和扰动响应预测上超越SOTA，并保持鲁棒批次整合。
conclusion: 互补细胞视图的预测对齐为表征中心细胞世界模型和可迁移AI虚拟细胞提供了可扩展路径。
---

## 摘要
从单细胞转录组学中学习的基础模型是AI虚拟细胞前景的核心，能够表示、查询和预测细胞状态。然而，当前大多数单细胞基础模型从单一基因表达视角学习，并主要通过重建或下一个标记预测进行优化。结果，它们捕获了表达丰度，但无法明确协调细胞状态的互补视图。在这里，我们提出CellOS，一个多视图基础模型，从配对的表达和感知视图中学习细胞表示。CellOS通过可扩展的三阶段训练策略整合互补视图，该策略结合了因果细胞语句语言建模、功能保持的密集到混合专家扩展以及通过LLM-JEPA目标的潜在空间对齐。利用这一框架，我们在3.905亿个单细胞转录组上训练了一个120亿参数的模型。在跨越细胞状态注释、批次整合和扰动响应预测的多个基准测试中，CellOS在细胞状态注释和扰动响应预测上始终优于最先进的单细胞基础模型，同时保持稳健的批次整合。综合来看，这些结果表明，互补细胞视图之间的预测对齐为以表示为中心的细胞世界模型和可迁移的AI虚拟细胞提供了一条可扩展的路径。

## Abstract
Foundation models learned from single-cell transcriptomes are central to the prospect of AI virtual cell that can represent, query and predict cellular state. However, most current single-cell foundation models learn from a single view of gene expression and are optimized primarily through reconstruction or next-token prediction. As a result, they capture expression abundance but can-not explicitly reconcile complementary views of cellular state. Here we present CellOS, a multi-view foundation model that learns cellular representations from paired expression and perception views. CellOS integrates complementary views through a scalable three-stage training strategy that combines causal cell-sentence language modelling, function-preserving dense-to-mixture-of-experts expansion and latent-space alignment via an LLM-JEPA objective. Using this framework, we trained a 12-billion-parameter model on 390.5 million single-cell transcriptomes. Across diverse benchmarks spanning cell-state annotation, batch integration and perturbation-response prediction, CellOS consistently outperformed state-of-the-art single-cell foundation models in cell-state annotation and perturbation-response prediction while preserving robust batch integration. Together, these results suggest that predictive alignment between complementary cellular views provides a scalable path toward representation-centric cellular world models and transferable AI virtual cells.

---

## 论文详细总结（自动生成）

# 论文总结：CellOS——通过联合嵌入预测学习细胞状态的世界模型

## 1. 核心问题与整体含义

- **研究动机**：单细胞转录组学基础模型是构建“AI虚拟细胞”的核心，但当前主流模型（如 scGPT、Geneformer、TranscriptFormer）均从单一视图（基因表达丰度排序）学习，并采用重建或下一个token预测进行优化。这种方式仅捕获了表达丰度，却无法显式利用群体层面的信息含量（如基因在全局分布中的稀有程度），导致对细胞状态的表征不够全面。
- **整体含义**：CellOS 提出一种多视图（multi-view）基础模型范式，将转录组同时表示为“表达视图”（按丰度排序）和“感知视图”（按群体相对惊喜度排序），并通过联合嵌入预测架构（LLM-JEPA）在潜在空间对齐二者，从而生成更丰富、可迁移的细胞状态表示。这项工作为构建以表征为中心的细胞世界模型和可泛化的AI虚拟细胞提供了新路径。

## 2. 方法论

### 核心思想
- 将单细胞转录组转化为两种互补的“细胞句子”（cell sentences）：
  - **表达视图**：基因按标准化表达丰度降序排列，对应句子 \( S_c^{\text{expr}} \)。
  - **感知视图**：基因按“群体相对惊喜度”（surprisal）降序排列，惊喜度定义为 \( I_{cg} = -\log(1 - q_g(e_{cg}) + \epsilon) \)，其中 \( q_g \) 是基因 \( g \) 在训练语料中非零表达值的经验分位数。该视图强调哪些基因值在群体分布中异常高，从而携带更多状态判别信息。
- 通过三阶段训练整合互补视图：
  1. **阶段1——因果细胞句子建模**：在表达视图上训练密集（dense）因果Transformer，学习细胞表达的语言规律（仅使用语言模型损失）。
  2. **阶段2——函数保持的密集到MoE扩展**：将密集前馈层替换为混合专家（MoE）层（1个共享专家 + 32个路由专家），采用 top-1 路由，并通过零初始化路由专家和近似均匀初始化的路由器保持预训练行为，然后继续预训练（添加MoE辅助损失）。
  3. **阶段3——LLM-JEPA跨视图对齐**：引入感知视图，使用共享Transformer编码器分别处理两个视图，提取表示token的最终隐藏状态作为细胞表示。设计一个预测器 \( q_\phi \) 将表达视图表示映射到感知视图表示空间，对齐损失采用余弦距离：\( L_{\text{JEPA}} = 1 - \cos(\hat{z}_c^{\text{perc}}, z_c^{\text{perc}}) \)。与语言模型损失和MoE辅助损失联合优化。
- 总损失函数：\( L = \lambda_{\text{LM}} L_{\text{LM}} + \lambda_{\text{JEPA}} L_{\text{JEPA}} + \lambda_{\text{MoE}} L_{\text{aux}} \)。

### 关键技术细节
- 基因词汇由标准基因符号加上保留控制token构成；每个基因分配唯一token ID。
- 表达归一化采用库大小缩放：\( e_{cg} = 10^4 \cdot x_{cg} / \sum_g x_{cg} \)。
- 感知视图的惊喜度基于基因特异经验分位数，选择上尾概率对数形式，确保跨基因尺度恒定。
- MoE层中的共享专家从密集前馈权重初始化；路由专家近零初始化；路由器近均匀初始化，保证转换后模型行为接近原密集模型。
- 模型使用一个专用的表示token（如<cls>）嵌入到每个句子开头，其最终隐藏状态作为细胞级嵌入。

## 3. 实验设计

### 数据集与场景
- **注释基准**：6个数据集，涵盖免疫细胞（PBMC老化）、iPSC分化（细胞类型和时间历程）、T细胞精细亚群、人类肺、IFN-β刺激PBMC。
- **批次整合基准**：2个数据集——人类肺图谱（107个文库）和嗅皮质数据集（2个样本），评估批效应校正同时保持生物结构。
- **扰动响应预测基准**：5个保持的细胞上下文——H1、HepG2、Jurkat、K562、RPE1（来自Perturb-seq数据，通过Virtual Cell Challenge资源），使用STATE框架中的共享转换模型。

### 对比方法
UCE、State、scGPT、TranscriptFormer、STACK、C2S-2B。所有扰动实验中仅替换嵌入，下游模型、训练协议一致。

### 评估指标
- 注释：ARI、NMI、ASW（先数据集内min-max归一化再平均，得到综合生物保守得分）。
- 批次整合：sil_batch、图连通性（GC）、iLISI（平均得综合批效应得分）。
- 扰动：DE Spearman相关性、Pearson e距离、聚类一致性、DE方向匹配、Pearson Δ。

### 消融实验
在T细胞亚群上比较0.2B、2B单视图预训练模型与12B MoE/多视图JEPA对齐后的模型，验证缩放和多视图对齐的增益。

## 4. 资源与算力

- 论文中未明确说明使用的GPU型号、数量及训练时长。
- 仅提及模型规模：12B参数（通过MoE扩展），训练数据量3.905亿单细胞转录组。提交者应指出文献未提供详细算力信息。

## 5. 实验数量与充分性

- **数量充分**：覆盖注释（6个不同场景）、批次整合（2个）、扰动预测（5个细胞上下文），并包含消融实验（3个模型规模/阶段）。
- **公平性设计**：扰动预测实验中，下游模型、训练程序、评估协议完全共享，仅替换嵌入，确保比较公正。
- **客观性**：采用多个成熟指标（ARI/NMI/ASW、sil_batch/GC/iLISI），并分别计算归一化聚合得分，减少了单指标偏差。

## 6. 主要结论与发现

1. CellOS在注释基准上获得最高的综合生物保守得分（0.792），在6个数据集中总体优于所有对比模型。
2. 在批次整合基准中，CellOS获得最高图连通性（0.964），综合批效应得分（0.771）仅次于STACK（0.801），但STACK的生物保守得分明显较弱（0.474 vs 0.792），表明CellOS在不牺牲生物结构的前提下实现良好整合。
3. 在扰动响应预测的5个场景中，CellOS在DE Spearman（0.590）、Pearson e距离（0.619）和聚类一致性（0.633）上排名第一，在DE方向匹配上与UCE并列（0.623），说明其嵌入捕捉了细胞状态转换所需的信息。
4. 消融实验显示：从0.2B→2B→12B+JEPA，ARI和NMI单调提升（+36%和+19%），表明缩放和多视图对齐都有贡献，且JEPA提供了超越参数量的额外增益。

## 7. 优点

- **创新性**：首次将联合嵌入预测架构（JEPA）应用于单细胞转录组学；提出“感知视图”这一群体惊喜度排序，将统计显著性显式作为训练信号。
- **方法论完备**：三阶段训练策略（因果语言模型→MoE扩展→跨视图对齐）设计合理，既利用了传统语言模型的知识，又扩展了容量并引入多视图对齐，且过渡函数保持。
- **大规模验证**：在3.905亿细胞上训练12B参数模型，是目前最大的单细胞基础模型之一。
- **跨任务泛化**：在注释、批次整合和扰动预测上均表现优异，表示质量高且可迁移。

## 8. 不足与局限

- **感知视图的局限性**：当前惊喜度基于整个训练语料的经验分位数，未考虑组织、谱系或条件特异性背景；未来需引入上下文感知的惊喜度。
- **模态单一**：仅使用转录组数据，未整合染色质可及性、蛋白质丰度、空间信息或扰动读数；多模态数据可能进一步提升表示质量。
- **因果性不足**：CellOS并未直接预训练于扰动轨迹或时间序列数据，其扰动预测依赖下游转换模型；尚不能称为完整的细胞因果世界模型。
- **算力细节缺失**：论文未报告训练所使用的GPU型号、数量和训练时长，限制了可复现性评估。
- **欠消融分析**：消融实验仅比较了模型规模与阶段（单视图 vs. 多视图），但未对感知视图的不同定义（如其他信息度量）进行消融，也未对比不同对齐损失函数。

（完）
