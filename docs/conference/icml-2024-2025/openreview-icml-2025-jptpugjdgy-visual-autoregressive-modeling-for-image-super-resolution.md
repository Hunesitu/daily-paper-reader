---
title: Visual Autoregressive Modeling for Image Super-Resolution
title_zh: 面向图像超分辨率的视觉自回归建模
authors: "Yunpeng Qu, Kun Yuan, Jinhua Hao, Kai Zhao, Qizhi Xie, Ming Sun, Chao Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JPTpUGJDGY"
tags: ["query:ce"]
score: 5.0
evidence: 提出用于图像超分辨率的视觉自回归建模，与自回归图像生成相关
tldr: 针对图像超分辨率中保真度与真实感权衡及计算复杂性问题，提出基于自回归建模的VARSR框架，采用下一尺度预测形式，并引入前缀token和尺度对齐旋转位置编码，利用扩散精炼器提升质量，实验表明在超分辨率任务上取得优异性能，展示了自回归建模在图像任务中的潜力。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1662, \"height\": 573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 773, \"height\": 696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 850, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 811, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1639, \"height\": 1254, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 756, \"height\": 329, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 763, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 756, \"height\": 346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 767, \"height\": 356, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1167, \"height\": 427, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1566, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1043, \"height\": 745, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1037, \"height\": 557, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1565, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1532, \"height\": 2284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1517, \"height\": 2280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jptpugjdgy/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1511, \"height\": 2276, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1727, \"height\": 845, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 658, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1569, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 861, \"height\": 320, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 807, \"height\": 260, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 708, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1783, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1469, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1644, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1066, \"height\": 210, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1317, \"height\": 137, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1781, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1788, \"height\": 494, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1547, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1027, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1102, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jptpugjdgy/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 949, \"height\": 313, \"label\": \"Table\"}]"
motivation: 现有生成模型在图像超分辨率中存在保真度与真实感权衡及计算复杂性问题。
method: 提出VARSR框架，采用下一尺度预测的自回归建模，引入前缀token和尺度对齐旋转位置编码。
result: 在多个超分辨率基准上取得了优越的定量和定性结果。
conclusion: 该工作展示了自回归建模在图像超分辨率任务中的有效性，扩展了自回归图像模型的应用。
---

## Abstract
Image Super-Resolution (ISR) has seen significant progress with the introduction of remarkable generative models.
However, challenges such as the trade-off issues between fidelity and realism, as well as computational complexity, have also posed limitations on their application.
Building upon the tremendous success of autoregressive models in the language domain, we propose \textbf{VARSR}, a novel visual autoregressive modeling for ISR framework with the form of next-scale prediction.
To effectively integrate and preserve semantic information in low-resolution images, we propose using prefix tokens to incorporate the condition.
Scale-aligned Rotary Positional Encodings are introduced to capture spatial structures and the diffusion refiner is utilized for modeling quantization residual loss to achieve pixel-level fidelity.
Image-based Classifier-free Guidance is proposed to guide the generation of more realistic images.
Furthermore, we collect large-scale data and design a training process to obtain robust generative priors.
Quantitative and qualitative results show that VARSR is capable of generating high-fidelity and high-realism images with more efficiency than diffusion-based methods.
Our codes are released at \url{https://github.com/quyp2000/VARSR}.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
图像超分辨率（ISR）旨在从低分辨率（LR）图像恢复高分辨率（HR）图像，是一个病态问题。现有方法面临**保真度（fidelity）与真实感（realism）的权衡**以及**高计算复杂度**两大挑战：
- **GAN-based方法**：在保真度指标（如PSNR）上表现较好，但生成能力有限，难以产生生动、真实的纹理。
- **扩散模型方法**：能生成丰富细节，但由于随机噪声采样和生成先验与LR分布之间的差距，像素级保真度不足，且迭代推理计算开销大。
受语言领域自回归（AR）模型巨大成功的启发（如LLMs），视觉自回归模型（VAR，通过下一尺度预测生成图像）提供了新的可能。本文首次将VAR引入ISR任务，提出**VARSR框架**，旨在利用自回归的粗到细预测优势，在保持结构保真度的同时降低计算量，并解决条件注入、空间表示、量化损失、真实性引导等关键问题。

### 2. 论文提出的方法论：核心思想、关键技术细节
**核心思想**：采用**下一尺度预测（next-scale prediction）** 的视觉自回归建模，将图像量化为多尺度token maps，从粗到细逐步预测，并引入扩散精炼器处理量化残差，最终通过图像级无分类器指导（Image-based CFG）提升真实感。

**关键技术细节**：
- **条件控制（Conditional Control）**：使用**Prefix Tokens**将LR图像编码后的特征作为初始尺度，放置在所有token序列之前，使后续预测能够以全局方式整合LR语义信息。
- **尺度对齐旋转位置编码（Scale-aligned RoPE, SA-RoPE）**：在Transformer中将2D旋转位置编码扩展到多尺度，对齐LR条件与各尺度token的二维空间结构，增强结构保真度。
- **扩散精炼器（Diffusion Refiner）**：利用轻量级MLP（6层）对量化残差（连续token）进行扩散建模，弥补离散量化造成的细节损失，提升像素级保真度。
- **图像级无分类器指导（Image-based CFG）**：在训练时将HR图像分为高质量和低质量两类，分别对应正、负嵌入；推理时通过引导尺度 \(\lambda_s\) 在正负条件之间插值，使生成分布偏向更真实、纹理更丰富的方向。
- **损失函数**：结合交叉熵损失（token预测）和扩散损失（残差预测），用系数 \(\lambda=2.0\) 平衡。

### 3. 实验设计
- **数据集**：
  - **训练**：使用自建大规模数据集（4M张高质量、高分辨率图像，覆盖3000+类别），并加入从IQA/IAA数据集中选取的50k低质量负样本。
  - **合成验证集**：从DIV2K验证集中随机裁剪3k张32×32 patch（HR为512×512，LR为128×128）。
  - **真实世界测试集**：DRealSR和RealSR（中心裁剪后测试）。
  - **额外真实场景**：RealLR200（无参考HR）。
- **对比方法**：包括GAN-based (BSRGAN, Real-ESRGAN, SwinIR-GAN, DASR)、扩散模型 (LDM, StableSR, DiffBIR, SinSR, PASD, SeeSR) 等10种SOTA。
- **评估指标**：
  - 保真度：PSNR, SSIM, LPIPS, DISTS。
  - 分布距离：FID。
  - 无参考质量：MANIQA, MUSIQ, CLIPIQA。
  - 额外无参考：CNNIQA, HyperIQA, TOPIQ。

### 4. 资源与算力
论文明确指出：实验在 **32块 NVIDIA V100 GPU** 上完成。训练过程分三阶段：VQVAE训练10k iterations，C2I预训练40k iterations，ISR微调20k iterations。batch size=128，学习率5e-5，优化器AdamW，权重衰减5e-2。推理时VARSR生成一张图像仅需 **0.59秒**（10步），是第二名DiffBIR的10.1%。

### 5. 实验数量与充分性
论文进行了**大量实验**：
- **主表对比**：在三个数据集（DIV2K-Val, RealSR, DRealSR）上，使用11个指标，对比10种方法，结果全面。
- **消融实验**：逐个验证LR条件模式（Prefix Tokens vs Directly Add, ControlNet, ControlNet+CA）、SA-RoPE（有无、是否用于条件token）、扩散精炼器、Image-based CFG、训练数据集规模、图像预处理策略、VQVAE尺度随机丢失策略。
- **额外实验**：
  - 用户研究（20位视觉研究者，100张真实LR图像）。
  - 与其他无参考指标（CNNIQA, HyperIQA, TOPIQ）对比。
  - 更小数据集微调（LSDIR+FFHQ共95k图像）验证泛化性。
- **定性可视化**：多张对比图展示细节恢复能力。
**充分性**：实验覆盖合成和真实场景、多种指标、多角度消融，对比方法全面，用户研究增强可信度。但无参考指标存在一定偏差风险（作者已讨论），实验设计客观公平。

### 6. 论文的主要结论与发现
1. **VARSR在无参考IQA指标上全面领先**（MANIQA, CLIPIQA, MUSIQ），生成图像具有更高人眼感知质量。
2. 在保真度指标上接近扩散模型，但略逊于GAN方法，符合保真度-真实感权衡的固有矛盾（图4给出实例）。
3. 推理速度显著优于扩散模型（0.59s vs 5.85~18.70s），效率提升约10倍。
4. 自回归的下一尺度预测方式能更好地保留空间结构，适合ISR任务。
5. 扩散精炼器和Image-based CFG有效提升细节质量和真实性。

### 7. 优点（方法或实验设计亮点）
- **方法创新**：
  - 首次将VAR应用于超分辨率，提出Prefix Tokens、SA-RoPE、扩散精炼器、Image-based CFG等针对性设计。
  - 利用扩散精炼器弥补量化损失，而非使用更复杂的额外超分网络。
  - Image-based CFG从图像质量角度引导生成，比文本prompt更直接。
- **实验设计**：
  - 自建4M大规模高质量数据集，含负面样本，并采用渐进式过滤和语义平衡策略。
  - 用户研究增强主观评估可信度。
  - 消融实验全面，覆盖各个关键组件。
- **效率**：推理步骤少、早期尺度复杂度低，具有实际部署潜力。

### 8. 不足与局限
- **语义覆盖局限**：训练数据4M张对比Stable Diffusion的数十亿仍显不足，罕见语义或极端退化场景可能无法正确恢复（图14示例）。
- **保真度指标未达最优**：在PSNR/SSIM上低于GAN方法，某些应用场景对保真度要求高时可能不适用。
- **量化误差的依赖性**：扩散精炼器虽能缓解量化损失，但轻量MLP的建模能力有限，更复杂的残差建模可能带来进一步提升。
- **无参考指标偏差**：虽然使用了多种无参考指标，但指标本身可能存在与人类感知不完全一致的风险（作者已提及）。
- **计算资源**：需要32块V100进行训练，对一般团队门槛较高。
- **未在更高分辨率（如4K）上测试**：当前实验以512×512 HR为主，更高分辨率下的扩展性未充分验证。

（完）
