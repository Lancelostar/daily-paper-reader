---
title: "Susagi: A Microbiome World Model"
title_zh: Susagi：一个微生物组世界模型
authors: "Peluso, M., Tackmann, J., von Mering, C."
date: 2026-05-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.07.723428v1.full.pdf"
tags: ["query:world-model"]
score: 9.0
evidence: 将世界模型概念应用于微生物组群落动态
tldr: 准确建模微生物群落动态对分析和干预至关重要。我们提出Susagi，一种排列不变的去噪变换器，直接操作SSU rRNA基因嵌入集学习成员稳定性。模型零样本预测群落组成动态，在挑战性数据上超越随机；稳定性分数反映生物结构，与高均匀度和大规模相关，且无需丰度信息。该模型参数高效，与大型模型竞争，促进微生物过程假设生成。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以捕捉微生物群落组装的通用结构，需一种能直接学习成员稳定性的模型。
method: 构建排列不变的去噪变换器，以细菌SSU rRNA基因嵌入集为输入，训练成员级稳定性函数。
result: 零样本预测群落动态，在三个挑战性数据中超越随机；稳定性分数与农业土壤等环境正相关，且与均匀度和群落大小相关，无需丰度。
conclusion: Susagi以参数高效、无需微调的方式实现了通用微生物建模，促进确定性组装和相互作用等过程的研究。
---

## 摘要
动机：准确模拟微生物群落如何在宿主和环境中组装和变化对于分析和干预至关重要。典型的流程捕获有限的泛化结构，并且通常依赖于固定的生态单元定义。

结果：我们提出了Susagi（Set Unsupervised Assessment of Genetic Imposters，遗传冒充者集无监督评估），这是一种排列不变的去噪变换器，直接对细菌SSU rRNA基因嵌入集进行操作，学习成员级别的稳定性函数。

该模型在约2×10^6个细菌群落样本上进行了训练。我们展示了它能够在零样本（无训练）设置下可靠预测群落组成动态，在三个具有挑战性的微生物组上进行了验证，这些微生物组中传统机器学习方法未能超过随机预期。模型的稳定性分数捕捉了生物结构：跨数据集，较高分数富集于农业、农田和土壤相关栖息地，这与这些环境中的微生物群落支持正多样性-稳定性关系一致。最高稳定性分数仅由具有高Pielou均匀度和大型群落大小达到，尽管模型从未见过丰度数据，这表明它能够仅从存在/缺失中识别群落失调。此外，它们还跟踪了诸如受试者年龄等生物梯度。

Susagi在多种分类任务上与另一个大型微生物组模型（微生物通用模型，MGM）具有竞争力，无需任务特定微调，且参数效率更高。

最终，我们的模型将有助于复杂微生物过程（包括确定性组装和微生物相互作用）的假设生成，例如在计算机设计群落中至关重要。

可用性和实现：评估代码和模型权重可在https://github.com/the-puzzler/Microbiome-Modelling找到。模型权重也可直接从https://huggingface.co/basilboy/microbiome-model下载。交互式演示可在此处找到：https://huggingface.co/spaces/basilboy/microbiome-space。

## Abstract
MotivationAccurately modelling how microbial communities assemble and change across hosts and environments is essential for analysis and intervention. Typical pipelines capture limited generalisable structure and often depend on fixed ecological unit definitions.

ResultsWe present Susagi (Set Unsupervised Assessment of Genetic Imposters), a permutation-invariant denoising transformer that operates directly on sets of bacterial SSU rRNA gene embeddings to learn a member-level stability function.

The model was trained on [~] 2 x 106 bacterial community samples. We show that it reliably predicts community composition dynamics in a zero-shot (no training) setting, demonstrated here across three challenging microbiomes for which traditional ML methods do not exceed random expectation. The models stability scores capture biological structure: across datasets, higher scores are enriched for agricultural, cropland, and soil-associated habitats, consistent with microbial communities in these environments supporting positive diversity-stability relationships. The highest stability scores are only attained by communities with high Pielou evenness and large size, despite the fact that the model has never seen abundances suggesting it can recognise community dysbiosis from presence absence alone. Furthermore, they also track biological gradients such as subject age.

Susagi is competitive with another Large Microbiome Model (Microbial General Model, MGM) on diverse classification tasks, without task-specific fine-tuning and with an increased parameter efficiency.

Ultimately, our model will facilitate hypothesis generation for complex microbial processes, including deterministic assembly and microbial interactions, crucial for instance in the design of communities in silico.

Availability and implementationEvaluation code and model weights can be found from https://github.com/the-puzzler/Microbiome-Modelling. Model weights can also be downloaded directly from https://huggingface.co/basilboy/microbiome-model. Interactive demo can be found here: https://huggingface.co/spaces/basilboy/microbiome-space.