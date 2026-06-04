---
title: "ZipAR: Parallel Autoregressive Image Generation through Spatial Locality"
title_zh: ZipAR：通过空间局部性实现并行自回归图像生成
authors: "Yefei He, Feng Chen, Yuanyu He, Shaoxuan He, Hong Zhou, Kaipeng Zhang, Bohan Zhuang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=S09B5wNa6J"
tags: ["query:ce"]
score: 6.0
evidence: 并行自回归图像生成
tldr: 自回归图像生成解码速度慢是实际应用的瓶颈。本文提出ZipAR，一种无需训练、即插即用的并行解码框架，利用图像的空间局部性，在单次前向传播中并行解码多个视觉token。通过自适应局部窗口分配和拒绝采样保证生成质量，显著加速自回归图像生成过程。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-s09b5wna6j/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1592, \"height\": 988, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s09b5wna6j/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1751, \"height\": 1130, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s09b5wna6j/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1595, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s09b5wna6j/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1586, \"height\": 475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s09b5wna6j/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 780, \"height\": 636, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s09b5wna6j/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 791, \"height\": 660, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-s09b5wna6j/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1411, \"height\": 418, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-s09b5wna6j/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1297, \"height\": 461, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s09b5wna6j/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1467, \"height\": 650, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s09b5wna6j/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1386, \"height\": 536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s09b5wna6j/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 633, \"height\": 343, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-s09b5wna6j/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 551, \"height\": 385, \"label\": \"Table\"}]"
motivation: 加速自回归图像生成，利用图像的空间局部性进行并行解码。
method: 提出ZipAR框架，基于自适应局部窗口和拒绝采样并行解码多个token。
result: 在保持生成质量的同时显著减少解码步数。
conclusion: 空间局部性可有效用于自回归图像生成的加速。
---

## Abstract
In this paper, we propose ZipAR, a training-free, plug-and-play parallel decoding framework for accelerating autoregressive (AR) visual generation. The motivation stems from the observation that images exhibit local structures, and spatially distant regions tend to have minimal interdependence. Given a partially decoded set of visual tokens, in addition to the original next-token prediction scheme in the row dimension, the tokens corresponding to spatially adjacent regions in the column dimension can be decoded in parallel. To ensure alignment with the contextual requirements of each token, we employ an adaptive local window assignment scheme with rejection sampling analogous to speculative decoding. By decoding multiple tokens in a single forward pass, the number of forward passes required to generate an image is significantly reduced, resulting in a substantial improvement in generation efficiency. Experiments demonstrate that ZipAR can reduce the number of model forward passes by up to 91% on the Emu3-Gen model without requiring any additional retraining.

---

## 论文详细总结（自动生成）

# ZipAR: Parallel Autoregressive Image Generation through Spatial Locality 论文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：自回归（AR）视觉生成模型（如LlamaGen、Lumina-mGPT、Emu3-Gen）在生成图像时需按光栅顺序逐token预测，导致生成高分辨率图像时需要数千次前向传播，推理延迟高，成为实际部署的主要瓶颈。
- **研究背景**：现有加速方法（如Medusa、Jacobi解码、推测解码）针对大语言模型设计，未利用视觉内容的固有特性（如空间局部性），且往往需要额外训练或附加模型。视觉token在空间上相邻区域具有强相关性，而光栅顺序下远距离token依赖弱，这为并行解码提供了机会。
- **整体含义**：提出ZipAR，一种无需训练、即插即用的并行解码框架，通过利用视觉token的空间局部性，在单次前向传播中并行解码多个空间相邻token，显著减少生成所需的前向传播步数，最高可减少91%的步数。

## 2. 论文提出的方法论：核心思想、关键技术细节

### 核心思想
- 在光栅顺序AR生成中，当前行的token与上一行同列附近的token具有强注意力依赖，而与上一行末尾的token依赖弱。因此，当当前行已解码的token数超过某个窗口大小后，下一行的对应token即可与当前行剩余token并行解码。
- 采用自适应局部窗口分配方案，结合拒绝采样（类似推测解码），动态调整每个token的上下文窗口大小，保证生成质量。

### 关键技术细节
1. **并行解码条件**：定义局部窗口大小 \( s \)。token \( x_{i,j} \)（第 \( i \) 行第 \( j \) 列）可开始解码的条件是：上一行 \( i-1 \) 中从列 \( j \) 开始的连续 \( s \) 个token均已生成。即 \( C(i,j)=1 \) 当且仅当 \( \{x_{i-1,k} \mid j \le k < j + s\} \subseteq D \)（\( D \) 为已解码token集）。
2. **行首token处理**：对于每行第一个token \( x_{i,0} \)，需要上一行末尾token作为输入。解决方案：
   - 对于支持动态分辨率的模型（如Lumina-mGPT），预先插入行尾特殊token（end-of-row）。
   - 对于缺少行尾token的模型（如LlamaGen），将上一行末尾token临时赋值为最近已解码空间相邻token的值。
3. **自适应窗口大小**：固定窗口大小需手动调参且不适用于所有token。提出自适应方案：
   - 设定最小窗口大小 \( s_{\min} \)。
   - 当生成 \( x_{i,s_{\min}-1} \) 后，尝试生成 \( x_{i+1,0} \)。
   - 每次新增一个上一行token后，用更大窗口重新生成该候选token，并计算前后预测的比值 \( r \)。
   - 若 \( r < \min(1, p(x|x_{0,0},...,x_{i,k}) / p(x|x_{0,0},...,x_{i,k-1})) \) 则接受；否则拒绝并从校正分布中重采样。该机制类似推测解码，确保窗口足够提供上下文。
4. **无需训练**：所有并行生成的token均使用原始模型头，无额外参数或训练。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - ImageNet 256×256（类条件生成）：使用50k生成图像评估FID。
  - MS-COCO（文本引导生成）：评估CLIP Score。
  - Parti数据集（用于分析注意力分布）。
- **基准模型**：
  - LlamaGen（类条件与文本引导）、Lumina-mGPT-7B（文本引导）、Emu3-Gen（文本引导）。
- **对比方法**：
  - 基线：原始NTP（Next-Token Prediction）范式。
  - 其他加速方法：SJD（Speculative Jacobi Decoding，Teng et al. 2024）。
- **评估指标**：
  - FID（ImageNet类条件）、VQAScore、HPSv2、ImageReward、Aesthetic Score、CLIP Score。

## 4. 资源与算力

- 论文未明确说明训练需要多少算力，因为ZipAR是无需训练的推理加速方法。
- 实验环境：Nvidia A100 GPU，PyTorch框架。
- 推理时测量了延迟（秒），但未提供具体GPU数量和型号细节。

## 5. 实验数量与充分性

- 主要实验涵盖四个场景：
  1. ImageNet类条件生成（LlamaGen-L/XL）：不同窗口大小对比（ZipAR-16/14/12等），与SJD及NTP对比，报告FID和延迟。
  2. MS-COCO文本引导生成（LlamaGen-XL-512、Lumina-mGPT-7B-768）：多种窗口大小，对比CLIP Score和延迟。
  3. 多指标评估（VQAScore、HPSv2等）：三个模型上多个窗口大小。
  4. 消融实验：自适应窗口 vs 固定窗口，以及采样超参数（温度、无分类器引导）的影响。
- 实验数量较为充分：涵盖了主流AR视觉生成模型、不同分辨率、不同评估指标，并对比了当时最相关的并行加速方法SJD。消融实验验证了自适应窗口的有效性。
- 公平性：所有实验采用相同硬件、相同采样配置，且明确指出ZipAR不改变最优超参数（温度、引导尺度）。然而，SJD方法的对比仅在部分模型和指标上给出，且未报告所有模型的FID等细节，略显不足。

## 6. 论文的主要结论与发现

- ZipAR可在几乎不损失图像质量的前提下，大幅减少前向传播步数：
  - Emu3-Gen：最多减少91%步数（从8190步降至713步）。
  - Lumina-mGPT-7B-768：减少75%步数（从2352步降至588步）。
  - LlamaGen-XL-512：减少81.9%步数（从1024步降至185步）。
- 自适应窗口方案比固定窗口方案在相同步数下获得更低FID，说明动态调整窗口能更好平衡质量和效率。
- ZipAR的加速比随图像分辨率提高而增大，因为更高分辨率下空间局部性更明显。
- ZipAR与现有并行解码方法（如Medusa、Jacobi解码）正交，可进一步结合实现更大加速。

## 7. 优点

- **无需训练**：直接应用于预训练模型，无需微调或附加模块，即插即用，降低部署成本。
- **利用视觉先验**：巧妙利用空间局部性这一视觉领域广泛验证的归纳偏置，设计简洁有效。
- **自适应机制**：通过拒绝采样动态调整窗口，避免手动调参，鲁棒性强。
- **显著加速**：在主流模型上实现数十倍步数减少，且质量下降极小。
- **兼容性**：可与推测解码、Medusa等方法结合，有进一步加速潜力。

## 8. 不足与局限

- **实验公平性**：与SJD的对比仅在LlamaGen和Lumina-mGPT的部分设置下进行，未在Emu3-Gen上对比，且未报告所有模型行尾token处理细节，影响全面性。
- **评估指标覆盖**：缺失一些常用指标（如LPIPS、CLIP多样性等），且未进行人类评估。
- **注意力分析依赖**：自适应窗口依赖于从单次生成的注意力图统计，可能对模型架构或输入分布敏感，缺乏跨不同模型的泛化分析。
- **行首token处理可能引入误差**：对于无行尾token的模型，临时赋值可能引入误差，尤其在长序列中误差可能累积。
- **应用限制**：仅适用于光栅顺序自回归模型，不适用于next-scale预测（如VAR）或BERT式掩码预测模型。
- **未讨论长视频生成**：论文仅讨论图像，但视频生成可能因时序维度引入更复杂依赖，ZipAR是否适用未验证。
- **碳减排声明**：虽提及可减少碳排放，但无定量分析。

（完）
