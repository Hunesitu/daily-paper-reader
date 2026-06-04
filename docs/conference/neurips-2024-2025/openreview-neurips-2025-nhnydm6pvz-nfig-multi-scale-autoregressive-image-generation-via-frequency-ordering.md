---
title: "NFIG: Multi-Scale Autoregressive Image Generation via Frequency Ordering"
title_zh: NFIG：通过频率排序实现多尺度自回归图像生成
authors: "Zhihao Huang, Xi Qiu, Yukuo Ma, Yifu Zhou, Junjie Chen, Hongyuan Zhang, Chi Zhang, Xuelong Li"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=nHNYDM6PVz"
tags: ["query:ce"]
score: 8.0
evidence: 基于频率排序的自回归图像生成
tldr: 自回归图像生成通常按固定空间顺序生成像素，忽略了图像的频谱层次结构。NFIG提出按频率顺序生成，先低频后高频，有效捕捉全局结构并减少令牌数量。实验表明，该方法在保持生成质量的同时提高了效率。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhnydm6pvz/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1438, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhnydm6pvz/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1181, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhnydm6pvz/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1300, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhnydm6pvz/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1302, \"height\": 676, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhnydm6pvz/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 664, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-nhnydm6pvz/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1308, \"height\": 339, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhnydm6pvz/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1274, \"height\": 503, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhnydm6pvz/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 1002, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhnydm6pvz/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1352, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhnydm6pvz/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1249, \"height\": 356, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhnydm6pvz/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 658, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhnydm6pvz/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 935, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-nhnydm6pvz/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1481, \"height\": 141, \"label\": \"Table\"}]"
motivation: 标准自回归方法按固定空间顺序生成像素，未能利用图像在频谱域中的层次结构。
method: 将图像生成分解为多个频率指导的阶段，首先生成低频成分，然后逐步添加高频细节。
result: 在多个图像生成基准上，NFIG以更少的令牌实现了有竞争力的生成质量。
conclusion: 频率感知的自回归生成是一种有效的范式，可推广到其他视觉生成任务。
---

## Abstract
Autoregressive models have achieved significant success in image generation. However, unlike the inherent hierarchical structure of image information in the spectral domain, standard autoregressive methods typically generate pixels sequentially in a fixed spatial order. To better leverage this spectral hierarchy, we introduce Next-Frequency Image Generation (NFIG). NFIG is a novel framework that decomposes the image generation process into multiple frequency-guided stages. NFIG aligns the generation process with the natural image structure. It does this by first generating low-frequency components, which efficiently capture global structure with significantly fewer tokens, and then progressively adding higher-frequency details. This frequency-aware paradigm offers substantial advantages: it not only improves the quality of generated images but crucially reduces inference cost by efficiently establishing global structure early on. Extensive experiments on the ImageNet-256 benchmark validate NFIG's effectiveness, demonstrating superior performance (FID: 2.81) and a notable 1.25x speedup compared to the strong baseline VAR-d20.

---

## 论文详细总结（自动生成）

# 论文详细总结：NFIG：通过频率排序实现多尺度自回归图像生成

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：标准自回归图像生成方法（如PixelCNN、VQGAN等）通常采用固定的空间顺序（如光栅扫描）逐像素或逐块生成图像，忽略了图像信息在频谱域中天然的层次结构——低频分量编码全局结构，高频分量蕴含局部细节。这种顺序设计导致两个主要缺陷：一是难以有效捕获长距离依赖和全局结构；二是生成过程计算密集、耗时，因为每个新元素都需基于所有已生成内容计算条件概率。
- **研究动机**：受扩散模型中从低频基础逐步添加高频细节的成功启发，以及自然图像功率谱遵循1/f²分布（低频能量更高）的特性，作者提出将生成过程与频率层次对齐：先以少量令牌生成低频全局结构，再逐步增加高频细节，从而在保持质量的同时提升效率。
- **整体含义**：NFIG是首个将频率分析显式融入自回归图像生成的框架，为自回归模型提供了一种更符合自然图像结构的序列设计范式。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将图像生成分解为多个频率引导的阶段，按“从低频到高频”的顺序进行自回归预测。低频分量用更少的令牌表示，高频分量用更多令牌表示，实现“粗到细”的生成。
- **关键技术细节**：
  - **频率引导残差量化变分自编码器（FR-VAE）**：作为图像分词器，通过快速傅里叶变换（FFT）将编码器输出的特征图分解为多个频带分量，再通过残差量化学习不同频率的离散表示。低频率使用小尺寸特征图（少令牌），高频率使用大尺寸特征图（多令牌）。具体公式包括频率分解 `ˆfi = F^{-1}(F(f) ⊙ Mi)` 和频率合成 `˜f = Σ I(ˆfi, H', W')` 等。
  - **频率引导残差量化**：通过残差学习逐级捕获频率分量，公式中 `Ri` 表示累计信号残差，`vi` 是每级可学习表示，通过向量量化（码本大小4096）获得离散令牌。
  - **Next-Frequency 自回归预测**：采用解码器-only Transformer（类似VAR的架构）和分块因果注意力，按频率带顺序生成令牌序列，条件概率建模为 `p(T1,T2,…,Tn) = Π p(Ti|T1,…,T_{i-1})`。频率带根据分辨率占比划分：`σi = σ_{i-1} + (hi·wi / Σ hj·wj) × σ_max`。
- **算法流程**（文字描述）：
  1. 训练FR-VAE：输入图像x→编码成特征图f→FFT+频率掩码分解为多频分量→插值到统一大小→残差量化获得离散令牌→解码器重建图像。损失包括重建损失、感知损失、GAN损失。
  2. 训练Transformer：使用FR-VAE提取的离散令牌，按低频到高频顺序，以分段自回归方式预测每个频率带的令牌索引，损失为交叉熵。
  3. 推理：从随机或条件令牌开始，逐步生成低频到高频的令牌序列，通过解码器合成最终图像。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：ImageNet ILSVRC 2012子集（约120万训练图像、5万验证图像、10万测试图像，1000类）。
- **评估指标**：FID（弗雷歇初始距离）、IS（初始分数）、Precision（精度）、Recall（召回率）。并报告重建FID（rFID）和生成FID（gFID）。
- **对比方法**：覆盖GAN（BigGAN、GigaGAN、StyleGAN-XL）、扩散模型（ADM、CDM、LDM-4、DiT系列、L-DiT）、掩码扩散（MaskGIT、RCG）、自回归模型（VQVAE-2、VQGAN、ViTVQ、RQTran.、FAR、XQGAN、VAR-d16/d20等）。特别与VAR-d16和VAR-d20进行关键对比。
- **基准**：ImageNet 256×256条件图像生成任务。

## 4. 资源与算力

- **明确说明**：模型使用PyTorch框架，在NVIDIA H100显卡上训练。FR-VAE编码器初始化为DINOv2-base预训练权重。图像生成器（Transformer）深度16（310M参数）。采用Adam优化器，学习率8×10⁻⁵，批量大小768，训练350 epoch。代码将开源（https://github.com/Pride-Huang/NFIG）。
- **未明确说明具体GPU数量和总训练时长**，仅提及“constrained by computational resources”限于310M模型训练。

## 5. 实验数量与充分性

- **实验数量**：
  - 主干结果（表2）：对比16种以上方法，在AR模型类别中取得了最佳gFID（2.81）和IS（332.42）。
  - 缩放实验（表3）：310M和600M模型在55 epoch下的表现验证扩展性。
  - 不同时期性能（表4）：NFIG-310M在200/250/300/350 epoch下的FID/IS/Pre/Rec，并与VAR-d16/d20对比。
  - 消融实验（表5）：逐步添加FR量化器、DINO判别器、AdaLN、Top_k采样、CFG，观察rFID和gFID变化。
  - 动机验证（图4、图5）：频率分布可视化、向量量化损失比较（NFIG vs VAR）。
  - 附录实验：频率保持能力（PSD、FKS），多种图像类型重建FID（DTD、QRCODE、图表、X射线、人脸等）。
  - 失败案例展示（图6）。
- **充分性与公平性**：实验设计较为全面，对比了同类AR方法和跨族方法，消融实验覆盖了Token和Transformer的关键组件。但缺少误差条（单次运行），且仅训练了310M模型（受限于计算资源），未完全验证更大模型（如1B、2B）的扩展规律。对比基线VAR的公开结果，可能因不同批次和随机种子存在偏差。总体客观，但可重复性验证不足（代码未公开）。

## 6. 论文的主要结论与发现

1. **频率引导自回归生成有效**：NFIG在ImageNet 256×256上达到gFID 2.81，IS 332.42，优于同等参数量的AR模型（如VAR-d16 FID 3.55），甚至超越更大模型VAR-d20（FID 2.95）达25%速度提升。
2. **FR-VAE重建质量高**：重建FID 0.85，优于VQGAN（7.94）和接近ViTVQ（1.28）等，验证了频率分解和残差量化的有效性。
3. **计算效率提升**：由于低频只用少量令牌捕获全局结构，推理步数仅10步，且速度比VAR-d20快1.25倍。
4. **频率保持能力强**：NFIG在高、中频段的FKS得分显著高于VAR，表明更好地保留了细节信息。
5. **损失平衡优势**：与VAR相比，NFIG在各分辨率上的向量量化损失更均衡，表明频率引导学习更稳定。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：首次将频率分析（FFT）引入自回归生成序列设计，利用自然图像频谱先验实现“粗到细”生成，思路新颖。
- **高效性**：低频使用少令牌，高频使用多令牌，符合信息论，在保持质量的同时减少计算量。
- **模块化设计**：FR-VAE与Transformer分离，便于替换或扩展；消融实验清晰展示了各组件的贡献。
- **实验透彻**：不仅报告主结果，还分析了不同epoch、不同模型大小、频率保持能力、失败案例等，对动机进行了充分验证。
- **公平对比**：与VAR在同一实验平台（H100）上比较时间，并给出相对速度倍数。

## 8. 不足与局限

- **频率分解简单**：仅根据分辨率比例划分频带，未采用统计或物理驱动的更精细策略，可能导致第一频带信息捕获不足。
- **实验覆盖面有限**：仅在ImageNet 256×256上做生成评估，未验证更高分辨率（如512×512）或其他数据集，也缺少对文本条件生成的探索。
- **资源受限**：未训练更大模型（1B/2B）以充分验证扩展规律，且只进行单次运行，无误差棒报告。
- **失败案例仍存在**：存在解剖错误（额外鸟腿）、纹理异常（金鱼图案）、细节丢失（鸟爪）等伪影，表明跨频率语义一致性有待提升。
- **代码未开源**：虽声明代码将开源，但目前无法复现，削弱了可重复性。
- **隐私和社会影响未讨论**：未涉及深度伪造、公平性等潜在伦理风险。

（完）
