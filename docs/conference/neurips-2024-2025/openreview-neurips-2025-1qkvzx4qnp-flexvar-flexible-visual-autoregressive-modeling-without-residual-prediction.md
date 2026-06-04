---
title: "FlexVAR: Flexible Visual Autoregressive Modeling without Residual Prediction"
title_zh: FlexVAR：无需残差预测的灵活视觉自回归建模
authors: "Siyu Jiao, Gengwei Zhang, Yinlong Qian, Jiancheng Huang, Yao Zhao, Humphrey Shi, Lin Ma, Yunchao Wei, ZEQUN JIE"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=1qKvZX4qnp"
tags: ["query:ce"]
score: 9.0
evidence: 无需残差预测的自回归图像生成
tldr: 现有视觉自回归模型依赖于残差预测范式，限制了生成灵活性和效率。本文提出FlexVAR，一种新型灵活视觉自回归范式，通过真实值预测替代残差预测，每步独立生成合理图像。仅用低分辨率图像训练，即可生成多种分辨率和长宽比的图像，并支持图像修复、外绘等任务。实验表明FlexVAR在多种任务上取得优异性能，是一种高效的通用图像生成框架。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1376, \"height\": 753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 765, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 685, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 744, \"height\": 331, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 609, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 784, \"height\": 349, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 710, \"height\": 312, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 820, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 996, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1009, \"height\": 386, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 730, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 751, \"height\": 780, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 757, \"height\": 925, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 775, \"height\": 773, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-1qkvzx4qnp/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1544, \"height\": 2088, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-1qkvzx4qnp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 870, \"height\": 189, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1qkvzx4qnp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1201, \"height\": 1157, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1qkvzx4qnp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1qkvzx4qnp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 691, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1qkvzx4qnp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 697, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1qkvzx4qnp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 697, \"height\": 187, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1qkvzx4qnp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 724, \"height\": 143, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-1qkvzx4qnp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1010, \"height\": 570, \"label\": \"Table\"}]"
motivation: 传统的残差预测范式限制了自回归图像生成的灵活性和扩展性。
method: 提出FlexVAR，使用真实值预测代替残差预测，每步独立生成图像，支持灵活分辨率和多任务。
result: 仅用低分辨率训练即可生成高分辨率图像，并在多种图像到图像任务中表现优异。
conclusion: FlexVAR提供了一种更灵活高效的自回归图像生成新范式。
---

## Abstract
This work challenges the residual prediction paradigm in visual autoregressive modeling and presents FlexVAR, a new Flexible Visual AutoRegressive image generation paradigm. FlexVAR facilitates autoregressive learning with ground-truth prediction, enabling each step to independently produce plausible images. This simple, intuitive approach swiftly learns visual distributions and makes the generation process more flexible and adaptable. Trained solely on low-resolution images (< 256px), FlexVAR can: (1) Generate images of various resolutions and aspect ratios, even exceeding the resolution of the training images. (2) Support various image-to-image tasks, including image refinement, in/out-painting, and image expansion. (3) Adapt to various autoregressive steps, allowing for faster inference with fewer steps or enhancing image quality with more steps. Our 1.0B model outperforms its VAR counterpart on the ImageNet 256 × 256 benchmark. Moreover, when zero-shot transfer the image generation process with 13 steps, the performance further improves to 2.08 FID, outperforming state-of-the-art autoregressive models AiM/VAR by 0.25/0.28 FID and popular diffusion models LDM/DiT by 1.52/0.19 FID, respectively. When transferring our 1.0B model to the ImageNet 512 × 512 benchmark in a zero-shot manner, FlexVAR achieves competitive results compared to the VAR 2.3B model, which is a fully supervised model trained at 512 × 512 resolution.

---

## 论文详细总结（自动生成）

# FlexVAR 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **背景**：当前视觉自回归模型（如VAR）采用尺度自回归范式，通过预测残差（residual）来建模下一个尺度的图像特征。虽然性能不错，但残差预测依赖于固定的步数设计，导致生成图像的分辨率和长宽比受限，无法灵活适应不同场景。
- **核心问题**：残差预测范式是否必要？研究者认为，相邻尺度间的语义信息可以通过直接预测真实值（ground-truth）来建模，这能打破固定步数的束缚，赋予自回归模型更大的灵活性。
- **研究目标**：提出一种无需残差预测的灵活视觉自回归范式FlexVAR，使模型仅用低分辨率图像训练即可生成任意分辨率、长宽比的图像，并支持多种图像到图像任务，同时可灵活调整推理步数。

## 2. 方法论：核心思想与关键技术

- **核心思想**：在尺度自回归中，每一步直接预测当前尺度的真实值（ground-truth latent feature），而非与上一步的残差。每步都能独立生成合理的图像，从而避免固定步数设计，提升灵活性。
- **关键技术细节**：
  - **可扩展VQVAE tokenizer**：训练时对潜特征进行多尺度随机采样（K=5），使tokenizer能够鲁棒地编码/重建不同尺度的潜特征，支持任意分辨率图像的重建。
  - **FlexVAR Transformer**：学习多尺度离散token map序列的概率分布，每一步并行生成当前尺度的所有token，条件为前面所有尺度。
  - **可扩展2D位置嵌入（Scalable Position Embedding）**：由2×最大潜空间大小的可学习查询组成，初始化使用2D sin-cos，可线性插值到任意尺度；同时移除步数嵌入，使模型对推理步数不敏感。
  - **训练时步数采样**：随机选择中间步数的尺度大小（最大步数10，末步固定16×16），每一步有5%概率被丢弃（最多丢弃4步），从而训练模型适应不同步数。推理时默认10步，也可零样本迁移到13步等。

## 3. 实验设计

- **数据集与场景**：
  - 训练：ImageNet-1K 256×256（类别条件生成），tokenizer在OpenImages上预训练。
  - 评估：ImageNet 256×256（主benchmark），零样本迁移到ImageNet 512×512。
- **对比方法**：
  - GAN：BigGAN, GigaGAN, StyleGAN-XL
  - 扩散模型：ADM, CDM, LDM-4-G, DiT系列
  - 随机扫描自回归：MaskGIT, RCG（cond.）
  - 光栅扫描自回归：VQGAN, RQ-Transformer, LlamaGen, AiM
  - 尺度扫描自回归：VAR系列（d16, d20, d24, d36）
- **评估指标**：FID（越低越好）、IS（越高越好）、Precision、Recall、推理步数、相对推理时间。

## 4. 资源与算力

- **Tokenizer训练**：OpenImages数据集，20 epoch，batch size 128，学习率1e-4，AdamW优化器。GPU数量未明确说明。
- **Transformer训练**：ImageNet-1K 256×256，使用80GB A100 GPU（具体数量未说明），训练epoch随模型规模变化：FlexVAR-d16 180 epoch，d20 250 epoch，d24 350 epoch。小规模消融实验训练40 epoch（约70K迭代）。
- **推理时间**：与VAR相近，如FlexVAR-d24 10步推理时间0.5（以VAR-d30为基准1）。

## 5. 实验数量与充分性

- **主要对比实验**：在ImageNet 256×256上，与多个SOTA方法（GAN、扩散、自回归）全面对比，报告了FID、IS等，模型参数≤1B，且与VAR同规模对比。
- **零样本实验**：
  - 使用13步（训练最多10步）在256×256上评估，FID提升至2.08。
  - 直接迁移到512×512（模型仅训练在≤256px），与全监督的VAR 2.3B对比，FID 4.43 vs 2.63，具有竞争力。
- **消融实验**：
  - 组件消融：预测类型（残差/真实值）、不同VQVAE（VAR、Llamagen、Ours）、位置嵌入类型。
  - 不同步数消融（6~13步），结果显示更多步数性能更好。
  - 不同分辨率生成（80~512px）及不同长宽比可视化。
  - Mamba架构迁移实验。
  - 位置嵌入类型（步数嵌入、坐标嵌入等）消融。
- **下游任务零样本**：图像细化（低分辨率输入生成高分辨率）、内外绘画、图像扩展，均展示了定性结果。
- **充分性**：实验覆盖了主要指标、多种模型规模、多种灵活性场景，消融设计合理，结果客观，但缺少统计显著性报告（如误差棒）。

## 6. 主要结论与发现

- FlexVAR在相同模型规模下优于VAR（FID: d16-3.05 vs 3.55, d20-2.41 vs 2.95, d24-2.21 vs 2.33），且零样本使用更多步数（13步）进一步改善到2.08 FID，超越同类自回归和扩散模型。
- 仅训练在≤256px，即可生成384px、512px等更高分辨率图像，且保持语义一致性；也能生成多种长宽比图像。
- 无需微调即可实现图像精细化、内外绘画、图像扩展等任务，展现强泛化能力。
- 训练时采用随机步数采样和步骤丢弃策略，使模型自然适应不同推理步数，可灵活权衡速度与质量。

## 7. 优点

- **简单有效**：去掉残差预测，直接预测真实值，设计直觉清晰，训练简便。
- **高灵活性**：支持任意分辨率、长宽比、推理步数，这是以往自回归模型难以做到的。
- **强零样本迁移能力**：在更高分辨率、更多步数、多种下游任务上均表现出色，无需额外微调。
- **可扩展性**：提出的可扩展位置嵌入和随机步数训练策略具有通用性，可适用于其他尺度自回归框架。
- **计算效率**：生成速度与VAR相当（10步推理），同时具备更优性能。

## 8. 不足与局限

- **高分辨率生成失败**：当生成分辨率超过训练分辨率3倍以上（如768px、1024px）时，出现波浪纹理和模糊细节。作者推测是由于ImageNet-1K训练集缺乏细粒度多尺度对象，导致模型在高分辨率下细节生成不佳。
- **VAE重构质量**：FlexVAR的VQVAE tokenizer重构FID（3.79）不如VAR的VAE（1.92），但最终生成质量仍优于VAR，说明改进主要来自自回归建模部分，若进一步改善tokenizer可能带来更大提升。
- **实验统计性**：未报告误差棒或统计显著性，虽然这是该领域常见做法，但对鲁棒性验证略有不足。
- **应用限制**：当前仅验证了类条件生成，对于更复杂的文本条件生成未涉及；模型可能继承训练数据的偏差，需谨慎部署。

（完）
