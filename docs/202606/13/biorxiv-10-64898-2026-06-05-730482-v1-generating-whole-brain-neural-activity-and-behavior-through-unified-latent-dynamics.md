---
title: Generating whole-brain neural activity and behavior through unified latent dynamics
title_zh: 通过统一潜在动力学生成全脑神经活动与行为
authors: "Nuzzi, D., Mattia, M., Pezzulo, G."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730482v1.full.pdf"
tags: ["query:world-model"]
score: 7.0
evidence: 构建全脑动力学生成模型，作为神经与行为数据的世界模型
tldr: 高维神经活动与行为如何从共享底层动力学涌现是神经科学的根本难题。本文提出NEBULA生成框架，利用线虫全脑记录构建统一潜在动力学模型，实现神经与行为轨迹的长时程生成和逼真行为模拟。对动力学的扰动揭示行为转变关键点，无重训练干预可操控神经行为状态。该方法为建立大脑-行为数字孪生及虚拟实验提供可扩展平台。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以同时高保真生成神经活动和行为的长期轨迹，缺乏统一建模框架。
method: 提出NEBULA，基于循环神经网络学习线虫全脑记录的统一潜在动力学。
result: 实现长时程神经行为生成、逼真模拟和虚拟干预，扰动揭示行为转变点。
conclusion: 为连接脑动力学与行为提供框架，支持大规模虚拟神经科学实验。
---

## 摘要
理解高维神经活动与行为如何从共享的底层动力学中涌现仍是神经科学的一个基本挑战。解决这一问题对于构建能够忠实再现并预测生命系统多尺度脑-行为动力学的数字孪生体至关重要。在此，我们提出NEBULA（通过统一潜在动力学进行神经与行为建模），这是一个联合建模全脑神经活动与行为的生成框架。利用秀丽隐杆线虫的全脑记录，该模型学习了一个统一的潜在动力学结构，支持神经与行为轨迹的长程生成、行为的逼真模拟以及定向虚拟干预。对学习到的动力学进行扰动揭示了行为相关的转变点，而引导干预则无需重新训练即可实现对神经和行为状态的可控操纵。这些结果为将脑动力学与生物体行为联系起来建立了一个框架，并为神经科学中可扩展的虚拟实验奠定了基础。

## Abstract
Understanding how high-dimensional neural activity and behavior emerge from shared underlying dynamics remains a fundamental challenge in neuroscience. Addressing this problem is key to enabling digital twins that can faithfully reproduce and predict the multiscale brain-behavior dynamics of living systems. Here we present NEBULA (NEural and Behavioral modeling through Unified LAtent dynamics), a generative framework that jointly models whole-brain neural activity and behavior. Using brain-wide recordings from C. elegans, the model learns a unified latent dynamical structure that supports long-horizon generation of neural and behavioral trajectories, realistic simulations of behavior, and targeted virtual interventions. Perturbations of the learned dynamics reveal behaviorally relevant transition points, whereas steering interventions enable controlled manipulation of neural and behavioral states without retraining. These results establish a framework for linking brain dynamics to behavior in a living organism and provide a foundation for scalable virtual experimentation in neuroscience.