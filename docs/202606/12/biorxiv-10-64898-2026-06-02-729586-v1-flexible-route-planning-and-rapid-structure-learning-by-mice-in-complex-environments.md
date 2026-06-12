---
title: Flexible route planning and rapid structure learning by mice in complex environments
title_zh: 小鼠在复杂环境中的灵活路线规划与快速结构学习
authors: "Pereira, M., Godinho, B. S., Machens, C. K., Costa, R. M., Akam, T."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729586v1.full.pdf"
tags: ["query:world-model"]
score: 8.0
evidence: 关于世界模型指导小鼠空间导航的研究
tldr: 空间导航中世界模型如何指导行动选择尚不清楚。研究者开发了优化的行为测定，让小鼠在复杂迷宫中导航至视觉提示目标，随机化起点和终点以分离控制系统。小鼠优先选择最短路径，表现出高效导航和快速学习迷宫结构。该测定有助于揭示世界模型支撑灵活行为的神经机制。
source: biorxiv
selection_source: fresh_fetch
motivation: 世界模型在灵活行为中的作用机制不明，需行为测定分离多种导航控制系统。
method: 优化行为测定，小鼠在复杂迷宫随机起点和终点导航至视觉提示目标，记录数千非重复轨迹。
result: 小鼠高效选择最短路径，从首次进入新环境即展示迷宫结构知识，学习迅速。
conclusion: 该测定可量化灵活导航与结构知识，为研究世界模型支持灵活行为提供范式。
---

## 摘要
利用环境预测模型进行行动选择是人类和动物行为的基础，然而在回路和算法层面上仍知之甚少。空间导航是描述世界模型如何指导行动选择的一个有吸引力的领域。然而，空间行为由多种控制系统塑造，包括习惯、使用空间关系的欧几里得模型进行向量导航，以及利用环境结构模型进行路线规划。理解世界模型如何支持导航需要能够分离控制系统并去相关行为变量，同时生成允许精确量化脑-行为关系的大数据集。在这里，我们开发并计算优化了一种行为测试，以量化利用环境结构知识的灵活导航。小鼠在复杂迷宫中导航至视觉提示的目标，每次试验中起始位置和目标位置随机，生成了数千条非重复的目标导向的导航轨迹。它们高效导航——强烈倾向于最短路径目标的选择，并且快速学习——在进入新环境的首次会话中就展示了迷宫结构的知识。我们预计该测试将有助于描述世界模型如何支持灵活行为。

## Abstract
Action selection using predictive models of the environment plays a fundamental role in human and animal behaviour, yet is poorly understood at circuit and algorithmic levels. Spatial navigation is an attractive domain for characterising how world models guide action selection. However spatial behaviours are shaped by multiple control systems including habits, vector-navigation using a Euclidean model of spatial relationships, and route planning using models of environment structure. Understanding how world models support navigation requires assays that dissociate control systems and decorrelate behavioural variables, while generating large datasets that allow precise quantification of brain-behaviour relationships. Here we developed and computationally optimised a behavioural assay to quantify flexible navigation using knowledge of environment structure. Mice navigated to visually cued goals in complex mazes, with randomised start and goal locations on each trial, generating thousands of non-repetitive goal-directed navigation trajectories. They navigated efficiently - strongly favouring options on the shortest path-to-goal, and learnt rapidly - demonstrating knowledge of maze structure from their first sessions in new environments. We anticipate the assay will be useful for characterising how world models support flexible behaviour.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：动物如何利用环境的世界模型（world model）进行灵活的路线规划和行动选择？该问题在神经回路和算法层面上尚未明确。
- **背景**：空间导航是研究世界模型如何指导行动选择的理想领域，但空间行为受多种控制系统影响，包括习惯、基于欧几里得空间关系的向量导航、以及基于环境结构模型的路线规划。现有行为测试难以分离这些控制系统，且通常变量相关性强、数据量不足，无法精确量化脑-行为关系。
- **整体含义**：理解世界模型支持灵活行为的神经机制，需要一种能够解耦控制变量、生成大规模非重复轨迹的行为范式。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：开发并计算优化一种行为测定（assay），让小鼠在复杂迷宫中导航至视觉提示的目标，每轮试验随机化起始位置和目标位置，从而分离习惯、向量导航与结构规划系统，并产生大量非重复的目标导向轨迹。
- **关键技术细节**：
  - 使用复杂迷宫结构（未具体说明拓扑），随机化起点和终点。
  - 视觉提示目标位置，鼓励动物灵活规划。
  - 通过计算机视觉或跟踪系统记录轨迹（文中未详细说明设备）。
  - 计算优化：可能包括迷宫设计优化（如确保路径多样性、最短路径的明确性）、试验参数随机化策略等，但文中未给出具体公式或算法流程。
- **公式或算法**：未提供具体数学表达，仅描述行为范式设计原则。

## 3. 实验设计：使用了哪些数据集/场景，它的 benchmark 是什么，对比了哪些方法
- **数据集/场景**：
  - 自定义复杂迷宫环境（未说明具体形状或尺寸）。
  - 每轮试验随机起始位置和目标位置（视觉提示），小鼠需导航至目标。
  - 记录数千条非重复的目标导向轨迹。
- **Benchmark**：未明确指定外部基准。内部比较可能为：小鼠是否选择最短路径 vs. 随机或较长路径；学习速度（从首次进入新环境的会话表现）。
- **对比方法**：未涉及与其他算法或动物模型的对比。论文仅描述该行为测定的自身表现。

## 4. 资源与算力
- 文中未提及任何计算资源（GPU型号、数量、训练时长等）。该研究可能主要依赖行为实验设备（迷宫、追踪系统）和基本数据分析，未涉及大规模深度学习训练。因此没有相关算力信息。

## 5. 实验数量与充分性
- **实验数量**：仅描述了一个行为范式，未列出具体组数。可能包括：
  - 不同迷宫结构（至少一种“复杂迷宫”）。
  - 多次会话（从首次到后续，观察学习）。
  - 若干只小鼠（数量未说明）。
- **充分性评估**：摘要未提供统计学细节（如动物数量、试验次数、数据变异性），但声称生成了“数千条非重复轨迹”，样本量应足够。然而，缺乏消融实验、控制条件（如移除视觉提示、随机化起始但固定目标等对照组）的描述。因此，充分性证据不足，需查看全文。
- **客观性**：行为范式设计合理（随机化起始和目标），有助于分离控制系统，但未报告潜在混淆因素（如环境气味、奖励位置偏差）。需要更多细节评估公平性。

## 6. 论文的主要结论与发现
- **高效导航**：小鼠强烈倾向于选择最短路径目标，表现出高效的路线规划。
- **快速学习**：在进入新环境的首次会话中，小鼠就展现了对迷宫结构的知识（即能快速找到最短路径）。
- **行为测定有效**：该测试可量化基于环境结构知识的灵活导航，有望用于揭示世界模型支撑灵活行为的神经机制。

## 7. 优点：方法或实验设计上的亮点
- **解耦控制系统**：通过随机化起始和目标位置，克服了以往实验中习惯与规划系统混杂的问题。
- **大规模非重复数据**：生成数千条轨迹，有助于高精度量化脑-行为关系（如神经群体编码分析）。
- **快速学习验证**：首次会话即显示结构知识，说明小鼠能快速内化环境拓扑，符合世界模型理论。
- **行为范式可推广**：可能适用于其他啮齿类动物研究，且易于与神经生理记录（如钙成像、电生理）结合。

## 8. 不足与局限
- **实验细节缺失**：摘要未提供迷宫具体结构（如分支数量、有无死胡同）、动物数量、训练轮次、统计指标（如最短路径选择概率的显著性）。无法全面评估实验覆盖率。
- **缺少控制条件**：未对比纯随机运动、去价值引导（如奖励固定但目标随机）、无视觉提示等条件，无法彻底排除其他导航策略（如知识梯度、嗅迹）。
- **偏差风险**：仅依赖视觉提示目标，可能引入视觉线索干扰；未讨论动物个体差异（如性别、年龄）对结果的影响。
- **应用限制**：该测定为行为层面，无法直接解释世界模型的内部表征；与神经记录的同步分析尚未在本摘要中呈现。
- **可重复性**：未提供公开数据或代码，其他实验室难以直接复现。

（完）
