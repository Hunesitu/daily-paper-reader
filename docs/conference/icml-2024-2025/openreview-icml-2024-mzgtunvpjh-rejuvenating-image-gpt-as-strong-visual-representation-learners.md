---
title: Rejuvenating image-GPT as Strong Visual Representation Learners
title_zh: 复兴image-GPT作为强大的视觉表示学习器
authors: "Sucheng Ren, Zeyu Wang, Hongru Zhu, Junfei Xiao, Alan Yuille, Cihang Xie"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=mzGtunvpJH"
tags: ["query:ce"]
score: 6.0
evidence: 增强iGPT自回归预训练用于视觉表示，与自回归图像生成相关
tldr: 针对自回归图像预训练iGPT预测原始像素导致语义层次不足的问题，提出D-iGPT，将预测目标改为语义token并补充可见token预测，利用CLIP编码语义，显著提升了视觉表示学习能力，在多项任务上达到领先性能，展示了自回归模型在图像理解中的潜力。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-mzgtunvpjh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 849, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mzgtunvpjh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1721, \"height\": 634, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mzgtunvpjh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 770, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-mzgtunvpjh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1393, \"height\": 478, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1625, \"height\": 1459, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 727, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1802, \"height\": 732, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 883, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 887, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 843, \"height\": 464, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 727, \"height\": 361, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 844, \"height\": 318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 843, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-mzgtunvpjh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 858, \"height\": 341, \"label\": \"Table\"}]"
motivation: 原始iGPT预测原始像素，语义层次低，表示能力有限。
method: 提出D-iGPT，将预测目标改为语义token，并同时预测可见token。
result: 在多个视觉表示学习基准上取得了领先性能。
conclusion: 该工作复兴了自回归图像预训练，展示了其强大的表示学习能力。
---

## Abstract
This paper enhances image-GPT (iGPT), one of the pioneering works that introduce autoregressive pretraining to predict the next pixels for visual representation learning. Two simple yet essential changes are made. First, we shift the prediction target from raw pixels to semantic tokens, enabling a higher-level understanding of visual content. Second, we supplement the autoregressive modeling by instructing the model to predict not only the next tokens but also the visible tokens. This pipeline is particularly effective when semantic tokens are encoded by discriminatively trained models, such as CLIP. We introduce this novel approach as D-iGPT. Extensive experiments showcase that D-iGPT excels as a strong learner of visual representations: A notable achievement is its compelling performance on the ImageNet-1K dataset --- by training on publicly available datasets, D-iGPT unprecedentedly achieves **90.0%** top-1 accuracy with a vanilla ViT-H. Additionally, D-iGPT shows strong generalization on the downstream task. Code is available at https://github.com/OliverRensu/D-iGPT.

---

## 论文详细总结（自动生成）

# 论文总结：Rejuvenating image-GPT as Strong Visual Representation Learners

## 1. 核心问题与整体含义（研究动机和背景）

**研究动机**：  
- 自回归预训练在NLP中取得了巨大成功（如GPT系列），但在计算机视觉领域，自回归预训练（如iGPT、PixelCNN）的发展落后于BERT风格的掩码图像建模（如MAE、BEiT）。  
- 原始iGPT直接预测原始像素，像素层次低、冗余且缺乏语义，导致视觉表示学习能力有限，且计算复杂度高，难以扩展到高分辨率图像。  
- 近期趋势偏向掩码图像建模（MIM），自回归方法几乎被忽视。作者质疑：自回归预训练是否真的不能构建强大的视觉表示学习器？

**整体含义**：  
- 作者通过两项简单但关键的改进，复兴了自回归预训练在视觉领域的潜力，提出了 **D-iGPT**，在ImageNet-1K上达到90.0%的top-1准确率，超越了所有基于公开数据训练的模型，证明了自回归方法同样可以成为强大的视觉表示学习器。

## 2. 方法论：核心思想、关键技术细节

**核心思想**：  
将自回归预训练的目标从原始像素改为**语义token**，并同时增加**可见token的预测**（作为监督信号），从而提升表示学习能力。

**关键技术细节**：  
- **图像分簇（Cluster）**：将图像划分为多个等大的、不重叠的区域（默认4个簇，每个簇包含7×7个patch），作为自回归序列的基本单元，替代iGPT中以像素为单元的序列，降低计算复杂度并增强区域间交互。
- **修改一：预测目标从像素变为语义token**：  
  - 使用预训练的CLIP模型（或其他判别模型）提取图像的语义token作为监督信号。  
  - 自回归预测第i个簇的语义token，损失采用余弦相似度：  
    \[
    L_G = -\sum_{i=1}^n \cos\big(G(f(x_{s_1:s_{i-1}}); \theta_G), \, f_\phi(x)_{s_i}\big)
    \]  
    其中 \(f\) 是编码器，\(G\) 是生成解码器，\(f_\phi\) 是CLIP编码器。
- **修改二：增加可见簇的监督**：  
  - 除了预测下一个簇，还让模型预测已见簇的语义token（相当于对可见部分也做预测/蒸馏）。  
  - 损失为：  
    \[
    L_D = -\sum_{i=1}^n \cos\big(D(f(x_{s_1:s_{i-1}}); \theta_D), \, f_\phi(x)_{s_1:s_{i-1}}\big)
    \]  
    其中 \(D\) 是判别解码器。
- **序列随机排列**：随机打乱簇的顺序，增强灵活性。
- **架构**：编码器为标准ViT；两个轻量解码器（生成式和判别式）各为2层Transformer，查询是随机初始化的[Dis]或[Gen] token，键/值来自编码器输出。推理时仅使用编码器。
- **注意力掩码**：采用GPT中的因果掩码，一次前向即可处理所有长度的子序列。

## 3. 实验设计：数据集、benchmark、对比方法

**数据集**：  
- 预训练：ImageNet-1K（约1.2M图像）、ImageNet-21K（约14M图像）  
- 下游微调：ImageNet-1K分类、ADE20K语义分割  
- 零样本：LAION-400M（图文对）  
- 鲁棒性评估：ImageNet-V2、ImageNet-Real、ImageNet-A、ImageNet-R、ImageNet-C、ImageNet-S、ImageNet-Hard

**Benchmark**：  
- 分类：ImageNet top-1准确率  
- 分割：ADE20K mIoU  
- 鲁棒性：各out-of-domain数据集上的表现  
- 零样本：ImageNet zero-shot分类

**对比方法**：  
- 自监督：MAE、BEiT、BEiTv2、EVA、iBOT、MaskFeat、MILAN、DeepMIM、TinyMIM、data2vec、PeCo、SAIM、RandSac等  
- 监督：DeiT  
- 大模型方案：SwinV2、CoAtNet、Lion、OpenCLIP、BEiT-3、One-Peace等（部分使用私有数据）  
- 零样本：CLIPA、OpenCLIP

## 4. 资源与算力

论文中明确说明：  
- 默认预训练：ImageNet-1K，300 epochs，batch size 4096，学习率 \(1.5\times10^{-4} \times \text{batchsize}/256\)，AdamW优化器。  
- 使用 TPU Research Cloud (TRC) 和 Google Cloud Research Credits。  
- 未明确列出GPU型号、数量、具体训练时长（但消融实验提到D-iGPT在300 epoch下训练时间159小时，而MAE 1600 epoch需要666小时，即D-iGPT训练成本减少了约77%）。  
- 扩展至ImageNet-21K时：150 epochs，batch size 4096，学习率 \(1.5\times10^{-3}\)。  
- 未报告具体GPU/TPU数量。

## 5. 实验数量与充分性

**实验数量**：  
- 主实验（表1）：分类+分割，ViT-B和ViT-L，对比12+种方法。  
- 鲁棒性实验（表2）：7个out-of-domain数据集。  
- 大尺度扩展（表3）：ImageNet-21K预训练，ViT-L/ViT-H，对比8种公开/私有方法。  
- 零样本（表4）：2种对比方法。  
- 消融实验（表5-10）共6组：  
  - 不同类型语义token（像素、VQVAE、DINO、CLIP变体）  
  - 不同tokenizer模型（CLIP-B/L、OpenCLIP-L/H、DINO-L）  
  - 不同簇数量（1~196）  
  - 不同预训练范式（MAE、EVA、KD vs D-iGPT）  
  - 解码器深度/维度  
  - 判别解码器的必要性  

**充分性评价**：  
- 实验覆盖了分类、分割、鲁棒性、零样本、模型扩展、数据扩展，消融全面。  
- 对比方法广泛，包含主流自监督方法及大模型基线。  
- 公平性：所有模型均使用相同backbone（ViT）和输入分辨率（224×224），微调设置尽量统一。  
- 不足：零样本实验仅对比了两个方法，且LAION-400M预训练细节较少；未见检测/实例分割等任务；部分消融（如CLIP-L@336）性能下降的解释较简略。

## 6. 论文的主要结论与发现

- **自回归预训练经过简单改进（语义token+可见token监督）即可成为强大的视觉表示学习器**，在ImageNet-1K上ViT-B达到86.2%（超过先前SOTA 0.6%），ViT-L达到87.8%。  
- **扩展性良好**：使用ImageNet-21K预训练，ViT-H达到90.0% top-1，超越所有基于公开数据训练的模型，与使用私有数据的模型性能相当。  
- **语义token的来源**：来自判别模型（如CLIP）的token效果最好，优于像素、VQVAE、DINO等。  
- **可见token监督（判别解码器）至关重要**：移除后性能下降1.5%。  
- **D-iGPT在鲁棒性和泛化性上显著优于对比方法**，尤其在ImageNet-A、R、Sketch等困难数据集上提升明显。  
- **自回归预训练比掩码预训练更高效**：仅需300 epoch即可超越1600 epoch的MAE。

## 7. 优点

1. **方法论简洁有效**：仅修改预测目标和增加额外监督，无需复杂架构。  
2. **高效训练**：300 epoch即可达到甚至超过1600 epoch的MAE，训练成本降低77%。  
3. **强大的可扩展性**：模型和数据规模增大时性能持续提升。  
4. **通用性**：分类、分割、鲁棒性、零样本任务均表现优异。  
5. **实验设计严谨**：对比方法涵盖广泛，消融全面，控制变量合理。  
6. **代码公开**，促进复现和后续研究。

## 8. 不足与局限

1. **依赖外部语义tokenizer**：需要使用CLIP等预训练模型，并非完全端到端自监督。  
2. **仅探索了图像域**：未涉及视频、多模态等场景。  
3. **实验覆盖有限**：缺少目标检测、实例分割、人体姿态估计等密集预测任务的评估。  
4. **零样本实验比较不充分**：仅对比了CLIPA和OpenCLIP，且LAION-400M上的微调细节未详细说明。  
5. **簇数量选择缺乏理论解释**：最优簇数为4，但未深入分析原因。  
6. **潜在偏差**：CLIP本身是从图文对训练得到，可能包含数据偏差，从而影响D-iGPT的表示。

（完）
