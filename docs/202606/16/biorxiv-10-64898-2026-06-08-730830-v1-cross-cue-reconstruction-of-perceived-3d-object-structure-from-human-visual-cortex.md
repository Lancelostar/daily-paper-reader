---
title: Cross-cue reconstruction of perceived 3D object structure from human visual cortex
title_zh: 从人类视觉皮层跨线索重建感知的三维物体结构
authors: "Aoki, S. C., Tsukasa, R., Yang, S., Tanaka, M., Doi, E., Nakamura, T., Ho, J.-K., Kamitani, Y."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.08.730830v1.full.pdf"
tags: ["query:d-gen"]
score: 7.0
evidence: 通过自编码器从脑活动解码3D点云
tldr: 大脑从不同深度线索构建统一3D感知，但难以直接测量。利用fMRI解码到预训练3D点云自编码器的潜在特征，再生成点云重构3D结构。仅用2D图像训练的解码器成功泛化到新类别和随机点立体图，并跟踪深度定义的3D倾斜。跨线索泛化在高级视觉区最强，为外化感知3D结构和读取内部世界模型提供了新标准。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法难以直接测量大脑中跨深度线索共享的3D感知结构。
method: 使用fMRI响应解码到预训练3D点云自编码器的潜在特征，再由生成器重构3D点云，解码器仅用2D渲染物体训练。
result: 解码器成功泛化到新类别、跨线索的随机点立体图，准确跟踪3D倾斜，跨线索泛化在高级视觉区最强。
conclusion: 跨线索泛化可作为外化感知3D结构的标准，读取内部3D表示，支持不同视角下的世界预测。
---

## 摘要
人脑从性质不同的深度线索中组装三维（3D）感知，然而大脑构建的感知三维结构——一种跨线索共享的表征——一直难以直接测量。在这里，我们展示这种线索不变的三维结构可以从人脑活动外化为显式的三维物体：将fMRI反应解码为预训练的三维点云自编码器的潜在特征，然后生成器将这些特征映射回点云。一个仅针对二维渲染物体反应训练的解码器通过了三项越来越严格的测试：（i）它泛化到新的物体类别；（ii）它跨深度线索泛化到随机点立体图（RDS），这些图通过双眼视差引发三维感知，但与训练图像不共享任何图形形状信息；（iii）它跟踪了轮廓匹配的RDS的三维倾斜度，这些RDS的二维轮廓相同但视差定义的倾斜度不同，表明重建反映的是深度定义的几何结构，而非物体类别或图像轮廓。跨线索泛化在高级视觉区域最强，尤其是沿着背侧通路。这些结果表明，跨线索泛化可以作为外化感知三维结构的标准，并开辟了一条读取内部三维表征的途径，这些表征超越了即时的视网膜输入，并可能支持对世界在不同视角下如何呈现的预测——朝着外化大脑内部世界模型迈出的一步。

## Abstract
The human brain assembles three-dimensional (3D) percepts from qualitatively different depth cues, yet the perceived 3D structure that the brain builds---a representation shared across cues---has remained difficult to measure directly. Here, we show that this cue-invariant 3D structure can be externalized as explicit 3D objects from human brain activity: fMRI responses are decoded into the latent features of a pretrained 3D point-cloud autoencoder, and a generator then maps these features back to a point cloud. A decoder trained exclusively on responses to 2D rendered objects passed three increasingly stringent tests: (i) it generalized to novel object categories; (ii) it generalized across depth cues to random dot stereograms (RDSs), which evoke 3D percepts through binocular disparity but share no pictorial shape information with the training images; and (iii) it tracked the 3D slant of contour-matched RDSs whose 2D outlines were held identical but whose disparity-defined slants varied, indicating that the reconstruction reflected depth-defined geometry rather than object category or image outline. Cross-cue generalization was strongest in higher visual areas, particularly along the dorsal stream. These results indicate that cross-cue generalization can serve as a criterion for externalizing perceived 3D structure and open a route toward reading out internal 3D representations that go beyond the momentary retinal input and could support predictions of how the world would appear under different viewpoints---a step toward externalizing the brain's internal world model.