---
title: Cross-cue reconstruction of perceived 3D object structure from human visual cortex
title_zh: 从人类视觉皮层重建感知的三维物体结构的跨线索重构
authors: "Aoki, S. C., Tsukasa, R., Yang, S., Tanaka, M., Doi, E., Nakamura, T., Ho, J.-K., Kamitani, Y."
date: 2026-06-15
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.730830v2.full.pdf"
tags: ["query:d-gen"]
score: 6.0
evidence: 使用预训练3D点云自编码器从脑活动重建，与生成式3D模型相关
tldr: 大脑如何从不同深度线索构建一致的三维感知一直难以直接测量。本研究通过fMRI响应解码到预训练3D点云自编码器的潜在特征，再生成点云来外化感知结构。仅用2D渲染图像训练的模型成功泛化到新类别和随机点立体图，并能追踪由视差定义的3D倾斜。结果表明跨线索泛化可作为外化感知3D结构的标准，为读取大脑内部世界模型开辟新途径。
source: biorxiv
selection_source: fresh_fetch
motivation: 从大脑活动中直接测量跨线索共享的3D物体结构，以揭示内部感知表征。
method: 基于fMRI响应，使用预训练3D点云自编码器解码潜在特征并生成点云。
result: 解码器泛化到新类别和随机点立体图，并准确追踪3D倾斜，高级视觉区跨线索泛化最强。
conclusion: 跨线索泛化可作为外化感知3D结构的有效标准，有助于理解大脑内部世界模型。
---

## 摘要
人类大脑从性质不同的深度线索中整合出三维（3D）感知，然而大脑构建的感知三维结构——一种跨线索共享的表征——一直难以直接测量。在这里，我们展示了这种线索不变的三维结构可以从人类大脑活动中外化为明确的三维物体：fMRI响应被解码为预训练的三维点云自编码器的潜在特征，然后生成器将这些特征映射回点云。一个仅针对二维渲染物体的响应训练的解码器通过了三项日益严格的测试：（i）它泛化到了新的物体类别；（ii）它跨越深度线索泛化到了随机点立体图（RDSs），这些立体图通过双眼视差引发三维感知，但与训练图像没有任何图形形状信息；（iii）它跟踪了轮廓匹配的RDSs的三维倾斜度，这些RDSs的二维轮廓保持不变，但视差定义的倾斜度变化，表明重建反映的是深度定义的几何结构，而不是物体类别或图像轮廓。跨线索泛化在高级视觉区域最强，特别是沿背侧流。这些结果表明，跨线索泛化可以作为外化感知三维结构的一个标准，并为读出超越瞬时视网膜输入的内部三维表征开辟了一条途径，这种表征可以支持在不同视角下世界将如何呈现的预测——这是迈向外化大脑内部世界模型的一步。

## Abstract
The human brain assembles three-dimensional (3D) percepts from qualitatively different depth cues, yet the perceived 3D structure that the brain builds--a representation shared across cues--has remained difficult to measure directly. Here, we show that this cue-invariant 3D structure can be externalized as explicit 3D objects from human brain activity: fMRI responses are decoded into the latent features of a pretrained 3D point-cloud autoencoder, and a generator then maps these features back to a point cloud. A decoder trained exclusively on responses to 2D rendered objects passed three increasingly stringent tests: (i) it generalized to novel object categories; (ii) it generalized across depth cues to random dot stereograms (RDSs), which evoke 3D percepts through binocular disparity but share no pictorial shape information with the training images; and (iii) it tracked the 3D slant of contour-matched RDSs whose 2D outlines were held identical but whose disparity-defined slants varied, indicating that the reconstruction reflected depth-defined geometry rather than object category or image outline. Cross-cue generalization was strongest in higher visual areas, particularly along the dorsal stream. These results indicate that cross-cue generalization can serve as a criterion for externalizing perceived 3D structure and open a route toward reading out internal 3D representations that go beyond the momentary retinal input and could support predictions of how the world would appear under different viewpoints--a step toward externalizing the brains internal world model.