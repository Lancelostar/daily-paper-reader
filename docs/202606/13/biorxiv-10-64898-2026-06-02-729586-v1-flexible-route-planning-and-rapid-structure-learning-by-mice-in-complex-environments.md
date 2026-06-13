---
title: Flexible route planning and rapid structure learning by mice in complex environments
title_zh: 小鼠在复杂环境中的灵活路径规划与快速结构学习
authors: "Pereira, M., Godinho, B. S., Machens, C. K., Costa, R. M., Akam, T."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729586v1.full.pdf"
tags: ["query:world-model"]
score: 9.0
evidence: 直接研究空间导航中的世界模型和结构学习
tldr: 空间导航依赖多种控制系统，包括习惯、向量导航和路线规划。本研究开发了计算优化的行为检测方法，让小鼠在复杂迷宫中随机起始和目标位置导航，生成数千条非重复轨迹。小鼠高效选择最短路径，并在首次遇到新环境时快速学习迷宫结构。该平台有望揭示世界模型支持灵活行为的神经机制。
source: biorxiv
selection_source: fresh_fetch
motivation: 理解世界模型如何指导动作选择，尤其在空间导航中路线规划的算法和神经回路。
method: 开发并计算优化行为检测，让小鼠在复杂迷宫随机起始和终点，记录数千条导航轨迹。
result: 小鼠高效偏好最短路径，从首次会话即快速习得迷宫结构。
conclusion: 该方法有助于揭示世界模型支持灵活行为的神经机制。
---

## 摘要
利用环境预测模型进行行动选择在人类和动物行为中扮演基础角色，但在回路和算法层面上仍知之甚少。空间导航是描述世界模型如何指导行动选择的一个有吸引力的领域。然而，空间行为受到多种控制系统的塑造，包括习惯、使用欧几里得空间关系模型的向量导航，以及使用环境结构模型的路径规划。理解世界模型如何支持导航需要能够分离控制系统并去相关行为变量的实验范式，同时生成允许精确量化脑-行为关系的大数据集。我们在此开发并计算优化了一种行为范式，以量化利用环境结构知识的灵活导航。小鼠在复杂迷宫中导航至视觉提示的目标，每次试验中目标和起始位置随机化，生成了数千条非重复的目标导向导航轨迹。它们高效导航——强烈倾向于最短路径至目标的选择，且学习迅速——在新环境中的首次经历即展示出对迷宫结构的认知。我们预期该范式将有助于描述世界模型如何支持灵活行为。

## Abstract
Action selection using predictive models of the environment plays a fundamental role in human and animal behaviour, yet is poorly understood at circuit and algorithmic levels. Spatial navigation is an attractive domain for characterising how world models guide action selection. However spatial behaviours are shaped by multiple control systems including habits, vector-navigation using a Euclidean model of spatial relationships, and route planning using models of environment structure. Understanding how world models support navigation requires assays that dissociate control systems and decorrelate behavioural variables, while generating large datasets that allow precise quantification of brain-behaviour relationships. Here we developed and computationally optimised a behavioural assay to quantify flexible navigation using knowledge of environment structure. Mice navigated to visually cued goals in complex mazes, with randomised start and goal locations on each trial, generating thousands of non-repetitive goal-directed navigation trajectories. They navigated efficiently - strongly favouring options on the shortest path-to-goal, and learnt rapidly - demonstrating knowledge of maze structure from their first sessions in new environments. We anticipate the assay will be useful for characterising how world models support flexible behaviour.

---

## 论文详细总结（自动生成）

好的，以下是根据您提供的论文内容生成的详细中文总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：动物如何利用对环境内部结构（即“世界模型”）的认知进行灵活的空间导航与路径规划？其背后的神经回路和计算算法尚不明确。
- **研究背景**：
  - 空间行为受多种控制系统驱动：习惯（刺激-反应）、基于欧几里得距离的向量导航（向量路标）以及基于环境拓扑结构的路线规划（世界模型）。
  - 现有行为范式难以有效分离上述控制系统，且行为变量间存在相关性，限制了脑-行为关系的精确量化。
  - 需要一个能生成大规模、非重复轨迹，且能独立操控起始点和目标点的实验平台，以分离不同导航策略，进而研究世界模型的作用。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过设计一个高度灵活的复杂迷宫导航任务，使小鼠必须在每次试验中根据随机的起点和终点规划新路线，从而迫使其使用环境结构知识（世界模型）而非习惯化或简单向量导航。
- **关键技术细节**：
  - **行为范式**：让小鼠在含有多个岔路和连接通道的复杂迷宫中导航至一个以视觉提示标记的目标位置。每次试验中，小鼠的起始位置和提示目标的位置都随机变动。
  - **数据生成**：通过实验优化，使小鼠在多次试验中产生数千条非重复的、目标导向的导航轨迹。
  - **分析指标**：量化小鼠路径选择与最短路径之间的偏离程度（路径效率）、学习速度（首次接触新环境后轨迹的变化）等。

### 3. 实验设计：使用的数据集/场景、基准测试、对比方法

- **数据集/场景**：复杂迷宫环境（具体结构未详述，但包含多个可能路径）。小鼠从随机起始点导航至随机视觉目标点。每个试验独立，不重复。
- **基准测试（Benchmark）**：未明确指定外部基准。论文通过将小鼠的实际轨迹与**理论最短路径**进行比较来评估效率。
- **对比方法**：文中未提及与其他导航模型或算法的对比。核心是展示小鼠在上述范式下的表现本身，以证明该范式能有效揭示结构学习与路径规划能力。

### 4. 资源与算力

- 论文摘要及元数据中**未明确说明**所使用的计算资源（如GPU型号、数量、训练时长等）。推测主要工作集中于行为学实验设计、数据收集与分析，可能使用了标准实验室计算设备（如用于数据分析的CPU/GPU工作站），但无具体细节。

### 5. 实验数量与充分性

- **实验数量**：从摘要可推断，实验在小鼠上进行了多次会话（sessions），在新环境中的首次会话（first sessions）就观察到了学习现象。但**未给出具体的小鼠数量、迷宫类型数量或总试验次数**。
- **充分性评价**：
  - **客观性**：路径选择效率（最短路径偏好）的度量客观。
  - **公平性**：由于未与其他方法对比，其作为新范式的验证尚可；但缺乏不同范式间的直接比较（例如与线性轨道或T迷宫对比）来证明其优越性。
  - **充分性**：仅用小鼠和单个复杂迷宫范式（可能）不足以完全排除习惯或向量导航的混杂作用。需更多控制条件（如移除视觉提示、改变拓扑结构等）才能全面证明其专门测试了世界模型。

### 6. 论文的主要结论与发现

- **高效导航**：小鼠在复杂迷宫中导航时，**强烈倾向于选择通往目标的最短路径**，表明它们并非依靠随机搜索或固定习惯。
- **快速结构学习**：小鼠在**首次进入新迷宫环境的会话中，就表现出了对迷宫结构的知识**（即快速学会了哪条路通向目标），无需长时间试错。这证明其具备快速构建世界模型的能力。
- **范式有效性**：该行为范式能够有效生成大量、多样化的目标导向轨迹，为后续研究世界模型的神经机制提供了工具。

### 7. 优点：方法或实验设计上的亮点

- **分离不同控制系统**：通过随机化起始点和目标点，打破了简单习惯（固定起点-终点重复）和向量导航（需保持方向一致性）的依赖，迫使小鼠使用**环境拓扑结构知识**。
- **大样本数据**：成功生成了数千条非重复轨迹，为高信噪比的神经行为和计算建模分析提供了数据基础。
- **去相关变量**：随机化操作降低了不同行为变量（如运动方向、距离、任务阶段等）之间的共线性，有助于后续神经数据分析。
- **行为易量化**：路径效率和学习速率等指标清晰、客观，易于直接计算。

### 8. 不足与局限

- **实验覆盖不足**：仅在一个（或少量）复杂迷宫上测试。不同复杂程度、不同拓扑结构的迷宫是否依然成立？未验证。
- **缺乏对比基准**：未与经典空间导航任务（如水迷宫、T迷宫）的优势进行量化比较，直接证明该范式在解开世界模型方面更优。
- **未排除其他策略**：虽然随机化减少了习惯和向量导航影响，但仍不能完全排除小鼠使用某种**局部视觉路标**或**地标排序**（Landmark sequence）策略，不一定需要全局拓扑模型。
- **计算资源未说明**：对于论文的方法论部分，缺少算力信息不利于其他人复现完整的优化过程。
- **仅涉及行为水平**：论文目前仅报告行为数据，未采集神经记录（如钙成像、电生理），因此其结论仅停留在行为层面，神经机制尚未验证。
- **样本局限性**：仅在小鼠中验证，推广到其他物种（如人类、大鼠）需进一步实验。

（完）
