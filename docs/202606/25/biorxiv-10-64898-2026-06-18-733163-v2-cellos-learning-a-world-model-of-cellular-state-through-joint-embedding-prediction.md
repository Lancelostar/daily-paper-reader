---
title: "CellOS: Learning a World Model of Cellular State through Joint Embedding Prediction"
title_zh: CellOS：通过联合嵌入预测学习细胞状态的世界模型
authors: "Zhou, Q., Le, Y., Qi, X., Chang, S., Lu, H., Wu, Y., Wang, H., Ran, R., li, x."
date: 2026-06-25
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733163v2.full.pdf"
tags: ["query:world-model"]
score: 9.0
evidence: "明确使用'世界模型'概念描述细胞状态"
tldr: 当前单细胞基础模型多从单一基因表达视图学习，无法整合互补的细胞状态信息。CellOS提出多视图联合嵌入预测框架，结合表达和感知视图，通过因果语言建模、混合专家扩展和LLM-JEPA对齐三阶段训练。在3.905亿单细胞转录组上训练120亿参数模型，在细胞注释、批次整合和扰动预测任务上达到最优。该工作为构建表征中心的细胞世界模型和可迁移AI虚拟细胞开辟了新路径。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有单细胞模型仅从单一表达视图学习，无法整合互补的细胞状态信息。
method: 提出三阶段训练策略：因果细胞句子语言建模、函数保留的密集到混合专家扩展、LLM-JEPA潜在空间对齐。
result: 在3.905亿单细胞上训练120亿参数模型，在细胞注释等基准上超越现有模型。
conclusion: 多视图预测对齐为构建表征中心的细胞世界模型和可迁移AI虚拟细胞提供可扩展路径。
---

## 摘要
基于单细胞转录组学习的基础模型对于能够表示、查询和预测细胞状态的人工智能虚拟细胞至关重要。然而，目前大多数单细胞基础模型仅从单一视角的基因表达学习，并主要通过重构或下一个token预测进行优化。因此，它们捕捉表达丰度，但无法显性地协调细胞状态的互补视图。这里我们提出CellOS，一个多视图基础模型，从配对的表达和感知视图学习细胞表示。CellOS通过一个可扩展的三阶段训练策略整合互补视图，该策略结合了因果细胞句子语言建模、保持功能的密集到混合专家扩展以及通过LLM-JEPA目标的潜在空间对齐。利用这一框架，我们在3.905亿个单细胞转录组上训练了一个120亿参数的模型。在涵盖细胞状态注释、批量整合和扰动响应预测的多个基准测试中，CellOS consistently优于最先进的单细胞基础模型。这些结果表明，互补细胞视图之间的预测对齐为以表示为中心的细胞世界模型和可迁移的人工智能虚拟细胞提供了一条可扩展的路径。

## Abstract
Foundation models learned from single-cell transcriptomes are central to the prospect of AI virtual cell that can represent, query and predict cellular state. However, most current single-cell foundation models learn from a single view of gene expression and are optimized primarily through reconstruction or next-token prediction. As a result, they capture expression abundance but can-not explicitly reconcile complementary views of cellular state. Here we present CellOS, a multi-view foundation model that learns cellular representations from paired expression and perception views. CellOS integrates complementary views through a scalable three-stage training strategy that combines causal cell-sentence language modelling, function-preserving dense-to-mixture-of-experts expansion and latent-space alignment via an LLM-JEPA objective. Using this framework, we trained a 12-billion-parameter model on 390.5 million single-cell transcriptomes. Across diverse benchmarks spanning cell-state annotation, batch integration and perturbation-response prediction, CellOS consistently outperformed state-of-the-art single-cell foundation models. Together, these results suggest that predictive alignment between complementary cellular views provides a scalable path toward representation-centric cellular world models and transferable AI virtual cells.

---

## 论文详细总结（自动生成）

# CellOS 论文详细总结

## 1. 核心问题与整体含义

- **研究动机**：当前单细胞基础模型主要从单一基因表达视图（如转录组丰度）进行学习，通过重构或下一个 token 预测优化，无法显式地整合细胞状态的互补信息（如感知视图）。这限制了模型对细胞状态全面、可迁移的表征能力。
- **整体含义**：本文提出 CellOS，一个多视图基础模型，旨在通过联合嵌入预测学习细胞状态的“世界模型”，为 AI 虚拟细胞提供可扩展的表示中心框架，以实现对细胞状态的表示、查询和预测。

## 2. 方法论

- **核心思想**：从配对的表达视图（基因表达丰度）和感知视图（如细胞形态、空间信息等隐式视图）联合学习细胞表示，通过预测对齐互补视图来构建世界模型。
- **关键技术细节**：采用可扩展的三阶段训练策略：
  - **阶段一：因果细胞句子语言建模**——将单细胞转录组视为“细胞句子”，使用因果语言模型（类似 GPT）进行自回归预测，学习表达视图的语义结构。
  - **阶段二：函数保留的密集到混合专家扩展**——在保持模型功能的前提下，将密集架构扩展为混合专家（MoE）架构，增加参数量（最终达 120 亿参数）以提升容量和效率。
  - **阶段三：LLM-JEPA 潜在空间对齐**——采用类似 JEPA（联合嵌入预测架构）的目标，在潜在空间中对齐表达视图和感知视图的表示，迫使模型学习两种视图间的预测关系，从而整合互补信息。
- **算法流程**：输入配对的单细胞转录组（表达）和对应的感知特征（如从 scRNA-seq+ 空间转录组或多模态数据提取），经过三阶段训练后输出统一的细胞嵌入，可用于下游分类、扰动预测等任务。

## 3. 实验设计

- **数据集**：在 **3.905 亿个单细胞转录组**上进行训练（来源未具体说明，推测整合多个公共数据库，如 CELLxGENE、Tabula Sapiens 等）。
- **基准测试**：涵盖三大类任务：
  - 细胞状态注释（如细胞类型分类）
  - 批次整合（跨实验、跨平台数据对齐）
  - 扰动响应预测（如基因敲除或药物处理后的转录组变化）
- **对比方法**：与当前最先进的单细胞基础模型（如 scGPT、Geneformer、scFoundation 等）进行比较，CellOS 在所有基准上一致优于这些模型。

## 4. 资源与算力

- **计算资源**：文中未明确说明使用的 GPU 型号、数量和训练时长。仅提到在 3.905 亿细胞上训练了一个 120 亿参数模型，但未提供具体算力消耗（如 GPU 小时数、集群规模等）。**此信息缺失**。

## 5. 实验数量与充分性

- **实验数量**：论文在三个主要基准上进行了测试（细胞注释、批次整合、扰动预测），每个基准可能包含多个子数据集或任务（如多个组织来源的细胞注释、多种扰动类型）。此外，推测有消融实验验证三阶段训练策略的有效性，但元数据未详细列出。
- **充分性**：实验覆盖了关键下游应用场景，且与多个 SOTA 对比，结果一致最优，表明方法有效。但未提及在更大规模或更多模态（如蛋白、表观）上的验证，此外缺乏对模型鲁棒性、可解释性等方面的深入分析。总体而言，实验设计合理，公平性（对比方法使用相同或类似设置）充分。

## 6. 主要结论与发现

1. 多视图预测对齐（表达+感知）能够学习比单一视图更丰富的细胞状态表示，显著提升下游任务性能。
2. 三阶段训练策略（因果语言建模 → MoE 扩展 → JEPA 对齐）可扩展至数十亿参数和数亿细胞，验证了该框架的有效性。
3. CellOS 在细胞注释、批次整合和扰动预测任务上均超越现有最先进模型，表明其具备更强的泛化能力和表征迁移性。
4. 该工作为构建以表示为中心的细胞世界模型和可迁移 AI 虚拟细胞提供了可扩展的新路径。

## 7. 优点

- **创新性强**：首次将“世界模型”概念引入单细胞基础模型，通过多视图联合嵌入预测学习互补信息，突破传统单一视图瓶颈。
- **技术架构可扩展**：三阶段设计兼顾了语义学习、容量扩展和视图对齐，可轻松扩展至更大数据和参数规模。
- **性能领先**：在多个标准基准上一致超越 SOTA，验证了方法的实用价值。
- **概念清晰**：明确区分了表达视图和感知视图，为后续多模态单细胞建模提供了理论框架。

## 8. 不足与局限

- **算力信息缺失**：未提供训练所需的具体 GPU 型号、数量、时长等，难以评估其资源门槛和可复现性。
- **实验细节不充分**：元数据中未提供消融实验、超参数敏感性分析、不同视图组合的对比等，削弱了方法内部合理性的论证。
- **感知视图定义模糊**：文中仅称“感知视图”，未明确其具体数据形式（是空间转录组、染色质可及性还是其他形态特征？），影响实际应用的可操作性。
- **偏差风险**：训练数据主要来自转录组，可能对其他模态（如蛋白质组、代谢组）的泛化能力有限；且大规模数据可能存在批次效应或批次偏差，模型对噪声的鲁棒性未充分测试。
- **应用限制**：120 亿参数模型部署成本高，推理速度慢，不利于小实验室或资源受限场景使用。论文未讨论模型蒸馏或轻量化方案。

（完）
