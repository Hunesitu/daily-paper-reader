---
title: "Hawk: Leveraging Spatial Context for Faster Autoregressive Text-to-Image Generation"
title_zh: Hawk：利用空间上下文加速自回归文本到图像生成
authors: "Zhi-Kai Chen, Jun-Peng Jiang, Han-Jia Ye, De-Chuan Zhan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=NMQUvjAY5x"
tags: ["query:ce"]
score: 8.0
evidence: 自回归文本到图像生成加速
tldr: 自回归图像生成推理速度慢，本文引入投机解码，利用空间上下文设计轻量草稿模型，加速生成过程。实验表明，Hawk在保持图像质量的同时显著减少了推理时间。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nmquvjay5x/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 715, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nmquvjay5x/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nmquvjay5x/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nmquvjay5x/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 717, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nmquvjay5x/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 707, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nmquvjay5x/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 765, \"height\": 543, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nmquvjay5x/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 731, \"height\": 775, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nmquvjay5x/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1446, \"height\": 1093, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nmquvjay5x/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1447, \"height\": 917, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nmquvjay5x/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1452, \"height\": 554, \"label\": \"Table\"}]"
motivation: 自回归图像生成推理速度慢，而投机解码在文本生成中有效，但应用于图像生成面临采样空间大等挑战。
method: 设计轻量级草稿模型，利用二维空间结构建模局部依赖，使草稿输出与目标模型对齐。
result: 在多个基准上，Hawk将推理速度提高了数倍，同时保持了图像质量。
conclusion: 投机解码可有效加速自回归图像生成，空间上下文是关键。
---

## Abstract
Autoregressive (AR) image generation models are capable of producing high-fidelity images but often suffer from slow inference due to their inherently sequential, token-by-token decoding process. Speculative decoding, which employs a lightweight draft model to approximate the output of a larger AR model, has shown promise in accelerating text generation without compromising quality. However, its application to image generation remains largely underexplored. The challenges stem from a significantly larger sampling space, which complicates the alignment between the draft and target model outputs, coupled with the inadequate use of the two-dimensional spatial structure inherent in images, thereby limiting the modeling of local dependencies. To overcome these challenges, we introduce Hawk, a new approach that harnesses the spatial structure of images to guide the speculative model toward more accurate and efficient predictions. Experimental results on multiple text-to-image benchmarks demonstrate a 1.71× speedup over standard AR models, while preserving both image fidelity and diversity.

---

## 论文详细总结（自动生成）

# Hawk：利用空间上下文加速自回归文本到图像生成 —— 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：自回归（AR）图像生成模型虽然生成图像质量高，但由于其逐 token 的顺序解码特性，推理速度慢，难以满足实际部署的实时性需求。现有加速方法（如非自回归生成、模型压缩）往往以牺牲图像质量为代价。
- **研究动机**：投机解码（Speculative Decoding）在文本生成中已证明能无损加速，但直接迁移到图像生成面临两个挑战：
  1. 图像生成的采样空间远大于文本（词汇表大小大20-400倍），导致草稿模型难以与目标模型对齐。
  2. 图像具有天然的二维空间结构，局部依赖不仅包括水平相邻，还包括垂直方向依赖，而现有投机解码方法仅考虑水平（一维）信息，未充分利用空间上下文。
- **整体含义**：本文提出 Hawk，通过引入空间投机解码（Spatial Speculative Decoding），利用图像的二维空间结构来引导草稿模型更准确高效地预测，在不牺牲图像保真度和多样性的前提下实现加速。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将投机解码与图像的空间信息结合。通过注意力下沉（Attention Sinking）实验发现，图像生成时模型注意力不仅集中在当前行附近，还显著关注上一行（空间相邻点）。因此，利用水平和垂直两个方向的草稿头（Draft Heads）分别进行预测，并将两者结果融合成统一的采样空间，提高草稿与目标模型分布的对齐程度。
- **关键技术细节**：
  1. **双方向草稿头（Dual Direction Drafting Heads）**：
     - 水平草稿头预测当前位置右侧的 token（如 T+1, T+2, ...）。
     - 垂直草稿头预测下方行对应位置的 token（如 T + ImageWidth × VerticalDepth）。
     - 垂直预测结果被缓存（缓存大小为 IW × VSD×(VSD+1)/2），供后续行推理时使用。
  2. **空间采样池（Spatial Sampling Pool）**：
     - 在每个推测点 T+n，将当前水平草稿分布和缓存的垂直草稿分布合并，形成二维空间采样池。
     - 基于该采样池，使用树状解码（tree-structured decoding）生成多个候选序列。
  3. **采样与验证**：
     - 采用顺序验证策略：依次尝试每个候选 token，若接受则继续下一个深度，否则更新目标分布并重新采样。
     - 公式 (7) 给出了最终分布近似表达式：融合两个空间（水平和垂直）的草稿分布，通过多次减法更新残余分布，减少残余概率，提高采样效率。
     - 附录A提供了理论证明，表明该方法保持原始模型分布不变。

- **公式说明（文字版）**：
  - 最终采样概率 p(x) = 所有候选被接受的概率之和 + 所有候选被拒绝后的残余分布概率。
  - 残余分布 p_resid 通过递归减去当前草稿分布得到，多个不同草稿分布（水平、垂直）可进一步降低残余质量。

## 3. 实验设计

- **数据集与场景**：
  - COCO 2017 验证集（500张采样）
  - Flickr30K 验证集（500张采样）
- **基准模型**：Lumina-mGPT（768×768图像生成）。
- **对比方法**：
  - Vanilla AR（标准自回归解码）
  - Medusa（水平方向草稿头）
  - Hawk（仅垂直方向草稿头）
  - LANTERN++（基于Medusa的多草稿图像投机解码加速策略）
  - Hawk（空间草稿头，即水平+垂直）
- **评估指标**：
  - 加速比（原推理时间/加速后推理时间）
  - 接受长度（平均每步接受 token 数）
  - FID（越低越好）
  - CLIP Score（越高越好）

## 4. 资源与算力

- **训练**：使用单张 RTX 3090 GPU，训练约 8-12 小时达到收敛。训练数据来自 LAION aesthetic 训练集的 6000 张图像。仅训练草稿头，冻结基模型。使用 AdamW 优化器，学习率 2e-5，权重衰减 0.1，β=(0.9,0.95)。
- **推理测试**：在单张 RTX 3090 GPU 上进行，采用 top-k=2000，温度=1.0，无分类器引导尺度 3.0。论文明确说明了硬件环境。

## 5. 实验数量与充分性

- **实验数量**：
  - 在两个数据集上（COCO2017、Flickr30K）进行了四类方法的对比（共5种设置）。
  - 消融实验：比较了仅水平草稿头（Medusa）、仅垂直草稿头、空间草稿头（Hawk）的效果。
  - 额外分析：对比了与 LANTERN++ 的结合；进行了训练损失分析（不同位置的草稿头损失比较）；KL散度分析（水平与垂直草稿头在生成不同区域时的差异）；理论 rejection 概率分析（图6）。
  - 注意力下沉实验（图1、图7）验证了空间依赖现象。
- **充分性判断**：实验较为充分，涵盖了主要基线、消融、理论分析。但只测试了单一基模型（Lumina-mGPT），未在不同规模模型（如 Chameleon）上验证泛化性。数据集仅两个（COCO和Flickr30K），规模中等。整体合理，但可进一步拓展。

## 6. 论文的主要结论与发现

- **主要结论**：Hawk 通过引入空间投机解码，在保持图像质量（FID和CLIP Score几乎无退化）的同时，实现了 1.71× 的加速比，优于传统 Medusa（1.58×）和 LANTERN++（1.69×但质量退化）。
- **关键发现**：
  - 垂直方向草稿头在训练损失上比水平方向衰减更慢（3.90% vs 4.88%），说明垂直空间信息更具预测性。
  - 水平与垂直草稿头的 KL 差异在生成图像边缘、眼睛等精细区域时更大，表明双方向补充了不同的采样空间，提高了接受率。
  - 双方向空间采样池能有效降低残余概率，提升理论加速上限。

## 7. 优点

- **方法创新**：首次将空间信息（二维结构）显式引入投机解码用于图像生成，针对图像生成的特殊性提出双方向草稿头和缓存机制，具有原创性。
- **理论严谨**：提供了完整的形式化证明，表明方法保持目标模型的分布不变（附录A）。
- **实验设计合理**：进行了注意力下沉实验以验证动机，消融实验对比了不同方向草稿头的作用，并与现有加速方法（LANTERN++）进行了公平比较。
- **效率与质量平衡**：在加速的同时未牺牲生成质量，FID和CLIP Score几乎与基线持平，优于放松验证阈值的 LANTERN++。

## 8. 不足与局限

- **实验覆盖局限**：
  - 仅基于 Lumina-mGPT 模型，未在其他自回归图像生成模型（如 Chameleon、VQ-GAN）上验证，泛化性存疑。
  - 只测试了 768×768 分辨率，未涉及更高分辨率或不同图像尺寸。
  - 数据集仅两个（COCO、Flickr），样本量 500，规模偏小，且未使用更广泛领域的评估。
- **加速效果有限**：实际加速比仅 1.71×，相比文本领域的投机解码（可达2-3×）仍有差距，部分原因是双方向草稿头增加了计算开销。
- **训练数据依赖**：只在 LAION aesthetic 6000 张图像上微调草稿头，可能对特定数据分布敏感。
- **资源与复现**：论文未提供代码或模型权重，实验细节中未报告误差棒或统计显著性（通常LLM论文不做，但可补充）。
- **局限声明**：作者在附录E指出，当前基于 Medusa 的实现可能不是最优的投机解码基线，未来可集成 Eagle/Hydra 等更先进方法，说明当前结果可能低估了潜力。

（完）
