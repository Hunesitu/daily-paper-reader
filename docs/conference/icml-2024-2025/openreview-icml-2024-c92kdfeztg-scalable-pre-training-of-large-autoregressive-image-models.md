---
title: Scalable Pre-training of Large Autoregressive Image Models
title_zh: 大规模自回归图像模型的可扩展预训练
authors: "Alaaeldin El-Nouby, Michal Klein, Shuangfei Zhai, Miguel Ángel Bautista, Vaishaal Shankar, Alexander T Toshev, Joshua M. Susskind, Armand Joulin"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=c92KDfEZTg"
tags: ["query:ce"]
score: 7.0
evidence: 自回归图像生成模型
tldr: "现有自回归图像模型大多受限于小规模训练。本文提出AIM模型族，采用自回归目标预训练大规模视觉模型，并系统研究了模型容量与数据量对性能的影响。实验表明，70亿参数的AIM在冻结主干的情况下在ImageNet-1k上达到84.0%的准确率，且未出现性能饱和迹象，证明自回归图像模型具有良好的可扩展性，为后续概念擦除等工作提供了基础模型。"
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 482, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 721, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 747, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1748, \"height\": 476, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 871, \"height\": 473, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 854, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 833, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 813, \"height\": 873, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 818, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-c92kdfeztg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1726, \"height\": 483, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 855, \"height\": 217, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 775, \"height\": 104, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1752, \"height\": 429, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 851, \"height\": 196, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 790, \"height\": 157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1770, \"height\": 598, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 860, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 856, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 878, \"height\": 610, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 853, \"height\": 837, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-c92kdfeztg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 848, \"height\": 825, \"label\": \"Table\"}]"
motivation: 探索自回归目标预训练视觉模型的可扩展性，验证模型容量和数据量对性能的影响。
method: 提出AIM模型，采用纯自回归目标在大规模图像数据集上预训练视觉Transformer。
result: "70亿参数模型在ImageNet-1k上冻结主干达到84.0%准确率，性能尚未饱和。"
conclusion: 自回归图像模型具有与语言模型类似的扩展规律，可作为通用视觉基础模型。
---

## Abstract
This paper introduces AIM, a collection of vision models pre-trained with an autoregressive objective. These models are inspired by their textual counterparts, i.e., Large Language Models (LLMs), and exhibit similar scaling properties. Specifically, we highlight two key findings: (1) the performance of the visual features scale with both the model capacity and the quantity of data, (2) the value of the objective function correlates with the performance of the model on downstream tasks. We illustrate the practical implication of these findings by pre-training a 7 billion parameter AIM on 2 billion images, that achieves 84.0% on ImageNet-1k with a frozen trunk. Interestingly, even at this scale, we observe no sign of saturation in performance, suggesting that AIM potentially represents a new frontier for training large-scale vision models. The pre-training of AIM is similar to the pre-training of LLMs, and does not require any image-specific strategy to stabilize the training at scale.

---

## 论文详细总结（自动生成）

好的，以下是对论文《Scalable Pre-training of Large Autoregressive Image Models》的详细中文总结：

### 1. 论文的核心问题与整体含义（研究动机和背景）

*   **核心问题**：探索自回归（Autoregressive）预训练目标在视觉领域（特别是图像）的可扩展性，即验证其能否像在大语言模型（LLMs）中那样，在模型参数和数据量增加时，实现性能的持续且可预测的提升。
*   **研究背景**：大语言模型（LLMs）的成功很大程度上归功于其简单的自回归目标（预测下一个词）与Transformer架构相结合时所展现出的强大缩放能力。一个自然的问题是，这种成功的组合是否仅限于文本领域。尽管已有工作将自回归模型应用于图像（如iGPT），但其潜力尚未在超大规模数据集和现代训练框架下得到充分验证。
*   **整体含义**：本文旨在证明，通过采用类似LLM的预训练方式，视觉模型也能获得类似的缩放特性，从而开辟一种简单、高效且可扩展的大规模视觉模型训练新范式。

### 2. 论文提出的方法论：核心思想、关键技术细节

*   **核心思想**：将图像视为像素序列，使用**自回归目标**进行预训练。具体来说，将一张图像分割成不重叠的块（patch），并按光栅扫描顺序（raster order）排列。模型的任务是基于已见的所有前面的块（context）来预测下一个块。
*   **关键技术细节**：
    *   **架构**：采用Vision Transformer (ViT)作为骨干网络，并遵循LLM的缩放惯例，优先增加宽度而非深度。
    *   **目标函数与损失**：核心目标是最小化负对数似然。具体实现中，采用**像素级别的均方误差（MSE）回归损失**，预测的是归一化后的像素值，这比离散化token或原始像素值效果更好。
    *   **Prefix Attention（前缀注意力）**：这是本文的关键修改之一。传统自回归使用因果掩码（causal mask），这在迁移到下游任务时会导致性能下降。AIM采用PrefixLM的变体，**随机选择一个前缀长度S**，允许前S个块进行**双向自注意力**（作为上下文），仅对剩余块施加因果约束。这使得模型在迁移到下游任务时可以无缝移除因果掩码，使用全局双向注意力，从而显著提升性能。
    *   **重参数化的MLP预测头**：在Transformer顶部添加一个**重参数化（heavy-parameterized）的多层感知机（MLP）**，每个块独立处理。这个头专用于像素级预测，防止主干网络的特征过于“专一化”于低层次信号。在下游任务时，这个头被丢弃。
    *   **训练稳定性**：AIM的预训练极为稳定，**不需要**任何图像特定的稳定技术，如LayerScale、Stochastic Depth、QK-Norm或冻结patch投影层，只需使用标准的优化器（AdamW）和超参数即可成功训练从6亿到70亿参数的模型。
*   **算法流程**：输入图像 → 切割为patch并线性嵌入 → 应用ViT（带有Prefix注意力掩码） → 通过MLP预测头 → 计算每个patch预测值与其归一化像素值的MSE损失 → 反向传播优化。

### 3. 实验设计：数据集、基准、对比方法

*   **数据集**：
    *   **预训练**：主要使用 **DFN-2B+** 数据集。它是从DataComp 12.8B数据集中，通过数据过滤网络（DFN）选出与文本描述最“对齐”的20亿个图像-文本对，并额外以0.2的概率混合了ImageNet-1k训练集。
*   **基准（Benchmarks）**：在 **15个** 多样化的图像识别基准上进行评估，包括ImageNet-1k、iNaturalist 2018、CIFAR-10/100、Food-101、DTD、Pets、Cars、iWildCam、Camelyon17、PCAM、RxRx1、EuroSAT、fMoW和Infographic。涵盖了细粒度分类、医学影像、卫星图像、自然场景等。
*   **对比方法**：
    *   **生成式方法**：MAE (各版本)、BEiT、ViT-2B。
    *   **联合嵌入方法（Joint-embedding）**：DINO、iBOT、DINOv2。
    *   **下游适应方法**：主要评估**冻结主干 + 注意力探针（Attentive Probe）** 的性能。这是一种轻量级的评估方式，仅训练一个可学习的注意力池化头和线性分类器，以评估预训练特征的质量。同时，也测试了**LoRA（低秩适配）** 微调的效果。

### 4. 资源与算力

*   论文**没有明确说明**所使用的具体GPU型号（如A100或H100）、总GPU数量以及具体的训练时长。
*   论文提到了模型规模和迭代次数：对于AIM-1B及以上模型，进行了**1.2百万次迭代**，批次大小为4096，相当于模型在预训练过程中“看到”了**5B**张图像（或1.2万亿个patches）。论文仅暗示训练在苹果公司的内部集群上完成。

### 5. 实验数量与充分性

*   **实验数量**：非常充分。论文进行了系列实验：
    *   **缩放实验**：训练了0.6B、1B、3B、7B四种不同规模的模型，并绘制了损失与迭代次数及下游性能的关系图（图4）。
    *   **数据影响实验**：对比了在IN-1k、DFN-2B和DFN-2B+上预训练的效果（图5, 表2）。
    *   **计算最优实验**：探索了延长训练步数（图6）。
    *   **消融实验**：系统性地研究了预训练目标（像素vs离散）、自回归模式（光栅vs螺旋vs棋盘vs随机）、注意力结构（因果vs前缀）、预测头设计（无vs MLP vs Transformer）、架构（宽vs深）、裁剪尺度、MLP设计（宽度与深度）等多个方面（表3, 4, 5）。
    *   **特征提取层实验**：验证了从中间层提取特征往往比最后一层效果更好（表7, 图10）。
*   **充分性与公平性**：
    *   **充分**：实验覆盖了从模型设计到数据规模的多个维度，结论支撑有力。
    *   **公平**：对比实验在相同条件下进行。例如，与掩码目标（Masking）的对比中，控制了所有其他架构和优化因素。对基线方法也进行了超参数搜索。评估指标和协议（如Attentive Probe）对所有方法一致。

### 6. 论文的主要结论与发现

1.  **缩放定律成立**：AIM展现出类似LLM的缩放特性。增加模型参数或数据量能持续降低预训练损失，并直接带来下游性能的提升。即便在70亿参数和20亿图像规模下，也未观察到性能饱和迹象。
2.  **损失与下游性能强相关**：预训练验证损失的值与模型在下游任务上的准确性之间存在强烈的正相关性。这意味着通过追踪预训练损失即可预估模型质量。
3.  **Prefix Attention是关键**：在预训练中使用Prefix Attention，使得模型可以在下游任务中无缝切换到全局双向注意力，这是提升下游性能的重要设计。
4.  **性能超越同类**：在15个基准的平均准确率上，AIM-7B显著超越了其他生成式方法（如MAE）和联合嵌入方法（如DINO、iBOT），迫近DINOv2的水平。特别是，从模型中间层提取特征可以进一步提升性能（AIM-7B在IN-1k上达到了84.0%）。
5.  **训练简单稳定**：AIM的预训练流程非常简单，不需要任何特殊的稳定技巧，这为其大规模扩展提供了巨大便利。

### 7. 优点

*   **简单性与可扩展性**：训练流程与LLM高度相似，极其简单且稳定，从6亿参数扩展到70亿参数无需调整超参数或添加特殊技巧，这在计算机视觉领域是很大的亮点。
*   **清晰的缩放特性**：成功地将语言模型领域的“缩放定律”移植到了视觉领域，为未来构建更大、更强的视觉模型提供了坚实理论和实验基础。
*   **客观的性能提升**：在多个基准上的实验结果有力证明了自回归目标在视觉表征学习中的有效性，并为生成式方法正名，证明其可以媲美甚至超越当时最先进的联合嵌入方法。
*   **损失函数的可解释性**：预训练损失与下游性能直接挂钩，使得训练过程中的监控和模型选择变得更容易。

### 8. 不足与局限

*   **样本效率较低**：与MAE等掩码自编码方法相比，AIM的样本效率不高。它需要在**极大量**的数据上训练才能达到良好性能，在小数据集上容易过拟合。这对计算资源有限的研究团队构成挑战。
*   **计算成本高**：虽然训练算法简单，但其达到SOTA所需的总计算量（FLOPs）仍然很大，特别是MLP头非常重（12层），增加了预训练成本。
*   **性能差距依然存在**：在单模型大小对比下，AIM的性能仍落后于DINOv2。论文将部分差距归因于DINOv2使用了更高分辨率输入和更复杂的微调策略。
*   **数据偏差风险**：预训练数据DFN基于图像-文本对齐分数进行过滤，这可能**引入了偏见**（例如，偏好有明确文字描述的物体，而可能忽略某些场景或概念）。作者未充分考虑和讨论这种数据预处理方式可能造成的潜在偏差。
*   **下游任务覆盖不全面**：评估集中在图像分类任务上，没有在更先进的视觉任务如目标检测、语义分割上进行评估，限制了其作为通用视觉基础模型结论的普适性。

（完）
