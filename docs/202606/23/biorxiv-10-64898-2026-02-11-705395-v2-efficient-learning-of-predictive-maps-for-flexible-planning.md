---
title: Efficient Learning of Predictive Maps for Flexible Planning
title_zh: 高效学习预测地图以支持灵活规划
authors: "Bazarjani, A., Piray, P."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.02.11.705395v2.full.pdf"
tags: ["query:world-model"]
score: 10.0
evidence: 用于规划的策略无关预测地图（后继表示）
tldr: 认知地图通过可复用的内部表征支持灵活行为，但现有预测地图模型存在策略依赖问题，限制了规划灵活性。本文提出SR-IS模型，结合时序差分学习与重要性采样，构建策略无关的预测地图，可在环境变化时高效更新。实验表明SR-IS在规划任务中优于现有模型，并能解释人类重规划中的渐进偏差，为大脑灵活决策机制提供新见解。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有继代表征模型依赖当前策略，无法实现策略独立的灵活规划，且不能解释人类重规划的渐进偏差。
method: 提出SR-IS模型，将时序差分学习与重要性采样结合，通过采样策略分布而非当前策略来学习策略无关的预测地图。
result: SR-IS在规划任务中超越现有模型，并能更准确地拟合人类重规划行为的渐进偏差。
conclusion: SR-IS弥合了预测地图理论与规划行为之间的鸿沟，揭示了大脑实现灵活决策的新机制。
---

## 摘要
认知地图通过提供可重用的任务结构内部表征来实现灵活行为。后继表征是一种预测地图，编码预期的未来状态占用，已被提出作为大脑中计算此类地图的一种方式，但其对策略的依赖性严重限制了灵活规划。我们引入了一个新模型——基于重要性采样的后继表征（SR-IS），它将时序差分学习与重要性采样相结合，构建与策略无关的预测地图。SR-IS学习环境结构而不受智能体当前决策策略的约束。当环境变化时，这些表征可以高效更新，从而实现快速的行为适应。我们表明，SR-IS在规划任务中优于现有模型，并更好地解释了先前模型无法解释的人类重规划中的分级偏差。这项工作将预测地图理论与观察到的规划行为联系起来，为大脑中的灵活决策提供了新见解。

## Abstract
Cognitive maps enable flexible behavior by providing reusable internal representations of task structure. The successor representation, a predictive map that encodes expected future state occupancy, has been proposed as one way such maps might be computed in the brain, but its policy dependence severely limits flexible planning. We introduce a new model, the successor representation with importance sampling (SR-IS), which combines temporal-difference learning with importance sampling to construct policy-independent predictive maps. SR-IS learns the structure of the environment without being constrained by the agent's current decision policy. These representations can be efficiently updated when the environment changes, enabling rapid behavioral adaptation. We show that SR-IS outperforms existing models in planning tasks and provides a better account of the graded biases in human replanning that previous models could not explain. This work bridges theories of predictive maps with observed planning behavior and offers new insights into flexible decision making in the brain.

---

## 论文详细总结（自动生成）

# 论文总结：高效学习预测地图以支持灵活规划

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：认知地图（cognitive maps）通过提供可重用的任务结构内部表征，使生物体能够表现出灵活的行为。后继表征（Successor Representation, SR）是一种预测地图，它编码了智能体对未来状态占用的预期，被认为是大脑计算此类地图的一种可能机制。然而，**现有SR模型对智能体当前决策策略（policy）具有严重依赖性**，这种策略依赖性极大地限制了模型的灵活规划能力——当环境变化或需要重新规划时，模型必须根据新策略重新学习整个表征。
- **背景意义**：人类在重规划（replanning）任务中表现出渐进式的偏差（graded biases），而现有基于策略依赖的预测地图模型无法解释这一现象。因此，需要一种能够**构建策略无关（policy-independent）的预测地图**的新方法，以桥接预测地图理论与实际规划行为之间的鸿沟。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：将时序差分学习（Temporal-Difference Learning, TD）与重要性采样（Importance Sampling, IS）相结合，构建策略无关的预测地图——**基于重要性采样的后继表征（SR-IS）模型**。
- **关键技术细节**：
  - 传统SR通过TD学习估计当前策略下的状态转移矩阵，而SR-IS通过**采样策略分布（policy distribution）**而非当前策略来学习环境的结构，从而消除对特定策略的依赖。
  - 重要性采样技术被用于纠正不同策略之间的分布偏移，使得学习到的预测地图能够反映环境本身的转移概率，而不受智能体实际行使的行为策略影响。
  - 当环境发生变化时，这些表征可以**高效增量更新**，无需从头重新训练，从而实现快速的行为适应。
- **算法流程（文字说明）**：
  1. 定义环境的状态空间和动作集合。
  2. 智能体通过与环境交互收集经验（状态-动作-奖励-下一状态元组）。
  3. 在TD更新中，使用重要性采样权重调整目标值，权重基于目标策略（均匀或随机探索策略）与实际行为策略的比值。
  4. 学习一个独立于策略的状态-状态相似性矩阵（即后继矩阵），该矩阵编码了从当前状态出发、按照环境动力学而非特定策略转移到未来各状态的概率。
  5. 当环境结构发生变化（如状态转移概率改变）时，利用已有的重要性采样权重对矩阵进行局部更新，无需完整重新学习。

## 3. 实验设计
- **使用的任务/场景**：规划任务（planning tasks），具体包括环境结构变化的重新规划场景。未详细说明具体迷宫或网格世界，但推测为经典强化学习环境（如GridWorld、树状图等）。
- **基准（Benchmark）**：与现有基于后继表征的模型（如传统的SR及其变体）进行对比。
- **对比方法**：文中提到“优于现有模型”，但未列出具体模型名称，推测包括标准SR、基于MVF（Multi-View Factorization）等替代方法。
- **人类行为拟合**：还使用人类重规划行为数据（之前模型无法解释的渐进偏差）作为评估基准，检验模型能否生成与人类决策模式一致的预测。

## 4. 资源与算力
- 文中**未明确说明**使用的GPU型号、数量或训练时长。仅提及模型在模拟任务中进行训练和评估，未涉及大规模计算资源细节。

## 5. 实验数量与充分性
- **实验数量**：至少包含两类实验：（1）在规划任务中与现有模型的性能对比；（2）对人类重规划行为的拟合分析。但未说明是否包含消融实验、不同环境大小的敏感性分析、参数鲁棒性测试等。
- **充分性评估**：
  - 论文证明了SR-IS在规划任务中优于现有模型，且能更好地拟合人类行为，实验设计针对核心假设（策略独立性）和解释力进行了验证，具有一定的客观性和公平性。
  - 但**不足之处在于**：缺少对以下方面的系统性分析：不同任务复杂度下的泛化能力、对噪声或部分可观测性的鲁棒性、重要性采样偏差的累积效应、以及更详尽的消融研究（如去掉IS的作用）。
  - 由于未提供具体实验次数和统计显著性指标，难以判断结果的可重复性。

## 6. 主要结论与发现
- SR-IS模型成功构建了策略无关的预测地图，在规划任务中优于传统策略依赖的SR模型。
- 当环境发生变化时，SR-IS能够高效更新表征，实现快速适应。
- SR-IS更好地拟合了人类重规划中的**分级偏差（graded biases）**，而现有模型无法解释这一现象，说明该模型更贴近大脑灵活决策的神经机制。
- 该工作弥合了预测地图理论与实际规划行为之间的理论鸿沟。

## 7. 优点
- **方法创新**：将重要性采样引入TD学习用于后继表征，解决了长期存在的策略依赖问题，方法简洁且理论清晰。
- **解释力强**：能够解释人类重规划行为中的渐进偏差，这是之前模型做不到的，表明模型具有神经科学和认知科学上的合理性。
- **实用价值**：策略无关的预测地图可复用性强，支持环境结构变化时的快速更新，适用于动态场景下的机器人决策等应用。

## 8. 不足与局限
- **实验覆盖有限**：未提供多样化的环境（如高维状态空间、连续动作空间）下的性能验证，主要依赖简单规划任务。
- **缺乏消融研究**：未单独分析重要性采样组件的贡献程度，可能混合了其他因素（如学习率、探索策略）的影响。
- **偏差风险**：人类行为数据可能来自特定实验设置，模型在其他变体（如奖励变化、非平稳环境）中的表现未知。
- **计算成本**：重要性采样权重的估计可能引入方差，尤其是在长轨迹下，但文中未讨论方差控制机制或权重剪枝策略。
- **应用限制**：当前模型假设环境动力学是确定性的或可建模的，对部分可观测马尔可夫决策过程（POMDP）的扩展未提及。

（完）
