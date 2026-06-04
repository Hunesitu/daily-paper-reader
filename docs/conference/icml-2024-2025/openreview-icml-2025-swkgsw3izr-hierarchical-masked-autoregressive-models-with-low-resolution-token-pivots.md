---
title: Hierarchical Masked Autoregressive Models with Low-Resolution Token Pivots
title_zh: 基于低分辨率令牌枢轴的分层掩码自回归模型
authors: "Guangting Zheng, Yehao Li, Yingwei Pan, Jiajun Deng, Ting Yao, Yanyong Zhang, Tao Mei"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=swkgSw3IzR"
tags: ["query:ce"]
score: 7.0
evidence: 用于视觉生成的分层掩码自回归模型
tldr: 针对现有自回归模型仅单尺度预测缺乏全局上下文利用的问题，提出Hi-MAR，引入多阶段分层建模，以低分辨率令牌为枢轴触发层次依赖，在视觉生成任务上取得了改进的性能，为自回归视觉生成提供了有效的层次化设计方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-swkgsw3izr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 451, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-swkgsw3izr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1756, \"height\": 741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-swkgsw3izr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 828, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-swkgsw3izr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 864, \"height\": 321, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-swkgsw3izr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1772, \"height\": 1585, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-swkgsw3izr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 838, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-swkgsw3izr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1644, \"height\": 1105, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-swkgsw3izr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 722, \"height\": 543, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-swkgsw3izr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 880, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-swkgsw3izr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 900, \"height\": 269, \"label\": \"Table\"}]"
motivation: 现有自回归模型仅单尺度预测，缺乏全局上下文利用。
method: 引入多阶段分层建模，以低分辨率令牌为枢轴触发层次依赖。
result: 在视觉生成任务上取得了改进的性能。
conclusion: 为自回归视觉生成提供了有效的层次化设计方案。
---

## Abstract
Autoregressive models have emerged as a powerful generative paradigm for visual generation. The current de-facto standard of next token prediction commonly operates over a single-scale sequence of dense image tokens, and is incapable of utilizing global context especially for early tokens prediction. In this paper, we introduce a new autoregressive design to model a hierarchy from a few low-resolution image tokens to the typical dense image tokens, and delve into a thorough hierarchical dependency across multi-scale image tokens. Technically, we present a Hierarchical Masked Autoregressive models (Hi-MAR) that pivot on low-resolution image tokens to trigger hierarchical autoregressive modeling in a multi-phase manner. Hi-MAR learns to predict a few image tokens in low resolution, functioning as intermediary pivots to reflect global structure, in the first phase. Such pivots act as the additional guidance to strengthen the next autoregressive modeling phase by shaping global structural awareness of typical dense image tokens. A new Diffusion Transformer head is further devised to amplify the global context among all tokens for mask token prediction. Extensive evaluations on both class-conditional and text-to-image generation tasks demonstrate that Hi-MAR outperforms typical AR baselines, while requiring fewer computational costs.

---

## 论文详细总结（自动生成）

# 论文详细中文总结：Hi-MAR — 基于低分辨率令牌枢轴的分层掩码自回归模型

## 1. 论文的核心问题与整体含义

- **研究动机**：当前视觉自回归（AR）生成模型（如GPT-style、BERT-style MAR）普遍采用**单尺度**的密集图像令牌序列进行下一令牌预测，缺乏对**全局上下文**的有效利用，尤其在早期（低序）令牌预测时，只能依赖前几个令牌，导致结构信息不足，生成质量受限。此外，传统AR模型依赖向量量化（VQ）离散化图像令牌，引入信息损失。
- **核心挑战**：如何在保持自回归生成框架优势（如良好的缩放性）的同时，融入全局结构信息，缓解早期预测的“盲区”问题。
- **整体含义**：本文提出了一种**分层自回归设计**——Hi-MAR，将生成过程拆解为**从低分辨率（全局）到高分辨率（局部）** 的两个阶段，以低分辨率令牌作为“枢轴”传递全局语义，实现了更优的视觉生成质量和更低的计算成本。

## 2. 论文提出的方法论

### 核心思想
- 构建**自上而下的层次结构**：第一阶段生成少量低分辨率图像令牌（反映全局结构），第二阶段以这些令牌作为条件引导，生成典型的高分辨率密集令牌。
- **连续值自回归**：采用MAR的连续令牌范式（基于VAE编码），避免离散化信息损失。
- **全局上下文增强**：第二阶段使用**Diffusion Transformer（DiT）头**，通过自注意力建模所有令牌之间的依赖关系，替代MAR中独立的MLP扩散头。

### 关键技术细节

#### （1）分层掩码自回归Transformer（Hi-MAR Transformer）
- **第一阶段（低分辨率）**：
  - 输入：低分辨率图像令牌（如128×128 → 4×4令牌网格），加上类标签/文本条件。
  - 采用随机掩码策略（mask ratio ∈ [0.7, 1.0]），通过双向Transformer编码后输出**条件令牌**（conditional tokens）Zs。
  - 使用MLP扩散头对低分辨率令牌进行去噪预测（损失同MAR公式）。
- **第二阶段（高分辨率）**：
  - 输入：高分辨率图像令牌（如256×256 → 16×16令牌网格）+ 第一阶段的**条件令牌Zs**（作为额外引导） + 上下文条件。
  - 掩码策略采用余弦调度（cosine masking）。
  - Transformer输出高分辨率条件令牌Zl，送入**Diffusion Transformer头**进行并行预测。
- **训练-推理一致性**：不同于常见方法（直接使用ground truth低分辨率令牌作为条件导致训练推理不匹配），Hi-MAR使用**预测出的条件令牌**（而非原始低分辨率令牌）作为第二阶段的引导，避免偏差。

#### （2）尺度感知Transformer块（Scale-aware Transformer Block）
- 为每个分辨率（低/高）引入可学习的**尺度向量**v（基于正弦位置编码 + MLP）。
- 通过**adaLN-Zero**操作，用尺度向量v生成 scale & shift 参数，注入到LayerNorm和残差连接中，使Transformer能区分不同分辨率阶段的特征。

#### （3）Diffusion Transformer头（Diffusion Transformer Head）
- 替代MAR中独立的MLP扩散头：输入为噪声扰动的令牌+条件令牌（所有令牌的上下文向量），通过**堆叠的Transformer块**进行自注意力处理，建模令牌间的全局依赖。
- 仅在第二阶段使用（第一阶段仍用MLP头，因其主要提供全局条件）。

### 公式流程（文字说明）
1. 第一阶段：`Masked Low-Res Tokens → Hi-MAR Transformer → Low-Res Conditional Tokens Zs → MLP Diff. Head → 去噪重建低分辨率令牌`。
2. 第二阶段：`Masked High-Res Tokens + Zs + Context → Hi-MAR Transformer → High-Res Conditional Tokens Zl → DiT Head (自注意力) → 去噪重建高分辨率令牌`。
3. 损失函数：每阶段均采用扩散损失（L2噪声预测误差），总损失为两阶段损失之和。

## 3. 实验设计

### 数据集与场景
- **ImageNet 256×256**：类条件图像生成（1,281,167张训练图，1K类）。
- **MS-COCO 256×256**：文生图任务（82,783训练图，40,504验证图，每图5句描述）。
- **评估指标**：FID（主指标）、IS、Precision/Recall（ImageNet）；FID（MS-COCO）；T2I-CompBench（细粒度组合理解）。

### 对比方法
- **GAN**：BigGAN、GigaGAN、StyleGAN-XL
- **扩散模型**：ADM、CDM、LDM-4-G、U-ViT、DiT-XL/2
- **离散AR模型**：VQGAN、RQTran.、GIVT、LlamaGen、VAR
- **掩码AR模型**：MaskGIT、AutoNAT、MAR（最直接基线）
- **本文方法**：Hi-MAR-B/L/H（Base/Large/Huge，与MAR同配置对比）

### 实验数量与充分性
- **主要结果**：两个数据集、三个模型规模，报告了有无CFG下的FID/IS/Precision/Recall，共计约15组对比。
- **消融实验**：5组消融（逐步添加pivot类型、conditional tokens、DiT头、尺度向量），清晰量化每个组件贡献。
- **附加分析**：
  - 速度/精度权衡曲线（与MAR、DiT对比）。
  - 两阶段步数影响（低分辨率32步+高分辨率4步最优）。
  - T2I-CompBench细粒度评估（颜色、形状、纹理、空间/非空间关系、复杂组合）。
  - 定性结果展示（8类类条件+8句文本生成示例）。
- **充分性评估**：实验设计系统全面，消融验证了每个设计点的必要性；对比方法涵盖主流范式，公平性较好（同规模、同设置）。但缺少跨分辨率（如512×512）的扩展实验。

## 4. 资源与算力

- 论文明确提及：使用**80GB H100 GPU**进行训练，未指定具体卡数。
- **ImageNet训练**：800 epochs，AdamW优化器（β1=0.9, β2=0.95），weight decay 0.02，学习率1e-4，100 epoch线性warmup。
- **MS-COCO训练**：AdamW，lr 8e-4，weight decay 0.03，8K步线性warmup，EMA动量0.9999。
- **推理速度**：使用单张H100，batch size 128，测速对比Hi-MAR-B与MAR-B、DiT-XL/2。
- 计算总量未直接给出，但考虑到模型规模（244M~1090M参数）及800 epoch，资源需求较大。作者未提供具体GPU小时数。

## 5. 实验数量与充分性

- **数量**：主表（表2）包含12种方法+3种规模Hi-MAR；表3（MS-COCO）6种方法+本文；消融表（表5）5行；附加分析图3-4；定性图5。
- **公正性**：紧密对标MAR（同VAE、同训练策略、同评估协议）；对比方法选择全面，且注明有无CFG设置差异。Hi-MAR在无CFG下也优于有CFG的MAR（如Hi-MAR-B无CFG FID 2.11 vs MAR-B有CFG 2.31）。
- **不足**：仅在256分辨率下测试；未在高分辨率（如512）或多尺度更高阶段（如4阶段）验证；未对比最新扩散模型（如SD3、Flux）；消融中“visual tokens”作为pivot的效果差，解释清晰，但未深入分析为何条件令牌更好。

## 6. 论文的主要结论与发现

1. **分层自回归优于单尺度**：Hi-MAR在ImageNet和MS-COCO上均超越MAR，例如Hi-MAR-B（有CFG）FID=1.93，比MAR-B的2.31绝对提升0.38，且模型参数仅增加36M（244M vs 208M）。
2. **低分辨率令牌作为全局枢轴有效**：提供全局结构后，第二阶段仅需4步即可达到饱和性能，总步数大幅减少（32+4=36步 vs MAR的64-256步），推理速度提升约2-3倍。
3. **Diffusion Transformer头优于MLP头**：引入自注意力建模令牌间依赖，FID进一步降低，且消除了MLP头可能产生的异常亮点问题。
4. **尺度感知设计提升建模能力**：可学习尺度向量让Transformer区分不同分辨率阶段，相比共享参数的方法效果更好。
5. **训练-推理一致性重要**：使用预测的条件令牌而非ground truth低分辨率令牌，避免了偏差，FID提升0.21。

## 7. 优点

- **高屋建瓴的层次化视角**：受人类先看全局后看局部的认知启发，设计自然。
- **连续令牌 + 扩散损失**：避免离散化损失，提升生成上限。
- **高效推理**：层次化设计使高分辨率阶段大步数减少，计算成本显著低于MAR和DiT。
- **创新性组件**：Scale-aware Transformer Block和Diffusion Transformer Head设计精巧，可推广至其他多尺度生成模型。
- **实验充分且对比公平**：复现MAR代码，在同一框架下做消融；报告了无CFG和有CFG结果，避免CFG带来的不公平优势。

## 8. 不足与局限

- **复杂度增加**：两阶段训练与推理、两个不同头（MLP + DiT）增加工程实现难度。
- **仅在256分辨率评估**：未证明在更高分辨率（如512×512、1024×1024）下的泛化能力，层次化可能对更大尺度更重要。
- **第一阶段仍使用MLP头**：未统一为DiT头，作者解释为“第一阶段主要提供全局条件”，但可能仍有优化空间。
- **超参数敏感**：两阶段步数、掩码分布、尺度向量维度等需精心调整，论文仅给出最终设置，缺乏鲁棒性分析。
- **文本到图像能力有限**：MS-COCO上仅比较了较小模型（Hi-MAR-S），未与当前SOTA扩散模型（如DALL-E 3、SDXL）对比，T2I-CompBench分数虽高但绝对数值仍较低。
- **潜在偏差风险**：使用预训练VAE（来自MAR），可能继承其偏差；ImageNet类条件生成结果中回忆（Recall）略低于一些方法（如DiT），表明多样性可能略受制约。

（完）
