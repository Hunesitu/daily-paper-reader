---
title: Vision Foundation Models as Effective Visual Tokenizers for Autoregressive Generation
title_zh: 视觉基础模型作为自回归生成的有效视觉分词器
authors: "Anlin Zheng, Xin Wen, Xuanyang Zhang, Chuofan Ma, Tiancai Wang, Gang YU, Xiangyu Zhang, XIAOJUAN QI"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=PESrAH82Zh"
tags: ["query:ce"]
score: 7.0
evidence: 视觉基础模型作为自回归生成的分词器
tldr: 本文提出基于冻结视觉基础模型的图像分词器，用于自回归图像生成。通过区域自适应量化减少冗余，并引入语义重建目标保持语义保真度。实验表明该方法在图像重建和生成质量上取得显著提升，为自回归生成提供了更好的视觉表示。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-pesrah82zh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-pesrah82zh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1456, \"height\": 596, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-pesrah82zh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 922, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pesrah82zh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 956, \"height\": 764, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pesrah82zh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1448, \"height\": 1273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-pesrah82zh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 907, \"height\": 405, \"label\": \"Table\"}]"
motivation: 现有图像分词器无法充分利用视觉基础模型的强大表示能力，限制了自回归生成模型的表现。
method: 使用冻结视觉基础模型作为分词器编码器，引入区域自适应量化和语义重建目标。
result: 在图像重建和生成质量上显著优于现有分词器，提升了自回归生成的效果。
conclusion: 该工作展示了视觉基础模型在自回归生成分词中的巨大潜力。
---

## Abstract
In this work, we present a novel direction to build an image tokenizer directly on top of a frozen vision foundation model, which is a largely underexplored area. Specifically, we employ a frozen vision foundation model as the encoder of our tokenizer. To enhance its effectiveness, we introduce two key components: (1) a region-adaptive quantization framework that reduces redundancy in the pre-trained features on regular 2D grids, and (2) a semantic reconstruction objective that aligns the tokenizer’s outputs with the foundation model’s representations to preserve semantic fidelity. Based on these designs, our proposed image tokenizer, \textbf{\ours}, achieves substantial improvements in image reconstruction and generation quality, while also enhancing token efficiency. It further boosts autoregressive (AR) generation---achieving a gFID of \textbf{1.36} on ImageNet benchmarks, while accelerating model convergence by \textbf{three times}, and enabling high-fidelity class-conditional synthesis without the need for classifier-free guidance (CFG). The code is available at \href{https://github.com/CVMI-Lab/VFMTok}{https://github.com/CVMI-Lab/VFMTok}.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：GPT在语言生成上的成功激发了自回归（AR）图像生成的研究，其关键依赖于视觉分词器（如VQGAN）将图像映射为离散的潜在表示。然而，现有分词器通常从头训练、仅优化重建，导致潜在空间富含低级细节但缺乏高级语义，且存在冗余。这样的潜在空间会延长AR模型训练时间，且需要无分类器指导（CFG）才能实现高保真类别条件生成，增加了推理成本。
- **背景**：另一方面，预训练的视觉基础模型（VFM，如DINOv2、CLIP、SigLIP2）展现了提取丰富语义和可泛化视觉特征的能力。早期探索（如REPA）表明这些语义表示有助于生成模型训练。因此提出自然问题：原本用于视觉理解的VFM特征能否作为图像重建和生成的稳健结构化表示？
- **核心问题**：如何将冻结的VFM直接用作图像分词器的编码器，以充分发挥其语义先验，同时解决特征网格冗余问题，实现高效高质量的自回归生成。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程

- **核心思想**：利用冻结的预训练VFM作为分词器编码器，通过区域自适应量化（region-adaptive quantization）和语义重建目标（semantic reconstruction objective）来构建高效、语义丰富的潜在空间，并用于自回归生成。

- **关键技术细节**：
  - **编码器**：直接使用冻结的VFM（如DINOv2-L）提取多层级特征（第6、12、18、24层），投影到统一维度。
  - **区域自适应分词生成**：采用可变形交叉注意力（deformable cross-attention），将一组可学习锚点查询（初始化为2D网格）通过迭代细化，在每个VFM特征层预测采样偏移，从语义相似的不规则区域采样特征，聚合后得到区域自适应令牌（region-adaptive tokens），数量固定为256（比VQGAN的576个更少）。
  - **向量量化**：对区域自适应令牌进行ℓ2归一化，使用低维（12维）大码本（16384）进行量化，提高码本利用率和重建质量。
  - **解码器**：量化后的令牌与可学习掩码令牌（mask tokens）拼接，经过轻量ViT（共享Transformer EViT）处理，输出规则2D特征图，再经VQGAN解码器重建图像。
  - **语义重建目标**：除了标准图像重建损失（像素损失、感知损失、对抗损失），额外添加特征重建损失，即重建VFM最后一层的高层特征，并通过余弦相似度损失约束，确保潜在令牌保持语义保真度。该目标仅在分词器训练时使用。
  - **对抗判别器**：用预训练的DINOv1-S替代PatchGAN，提供语义更丰富的对抗训练信号。
  - **自回归生成**：训练好的分词器结合LLaMA式AR Transformer，以类别嵌入为条件，自回归生成区域自适应令牌序列，再经共享ViT和解码器生成图像。使用2D旋转位置编码（RoPE）。

- **算法流程（文字说明）**：
  1. 输入图像I，经冻结VFM提取多级特征F_m。
  2. 可变形注意力层利用锚点查询对F_m进行不规则采样，得到区域自适应令牌Z_r。
  3. 量化器将Z_r离散化为Z̃_r。
  4. 解码阶段：Z̃_r与掩码令牌M_I拼接，经共享ViT得到规则特征图F_I，再经解码器D重建图像。
  5. 同时，Z̃_r与另一组掩码令牌M_F拼接，经同一共享ViT得到重建的VFM特征F_P，计算与原始VFM特征的余弦相似度损失。
  6. 总体损失：L = α·L_AE + λ·L_sim，其中L_AE包含L2、LPIPS、GAN损失，L_sim为特征重建损失。

## 3. 实验设计

- **数据集**：ImageNet（ILSVRC 2012）训练集用于训练，验证集用于评估。
- **任务**：
  - 图像重建（Image Reconstruction）：评估rFID、rIS、码本利用率等。
  - 类别条件图像生成（Class-conditional Image Generation）：评估gFID、sFID、gIS、Precision、Recall等。
- **基准与对比方法**：
  - **图像重建**：对比VQGAN（多种变体）、MaskGiT、ViT-VQGAN、TiTok、ImageFolder等1D/2D分词器。
  - **图像生成**：对比扩散模型（DiT、SiT、MaskDiT、FasterDIT）、BERT式掩码预测模型（MaskGiT）、自回归模型（VAR、TiTok、LlamaGen、RAR等）。包括给基线加上CFG和不加CFG两种情况。
- **评估指标**：FID、IS、sFID、Precision、Recall、rFID、rIS、码本使用率等。

## 4. 资源与算力

- 正文未明确说明GPU型号、数量及总训练时长。仅提到：
  - 分词器训练50个epoch（VQGAN基线也是50 epoch）。
  - AR模型：小于1B参数训练300 epoch，大于等于1B参数训练200 epoch。
  - 生成模型训练基于LLaMA框架，与LlamaGen设置相同。
- 附录（未提供）可能包含更详细计算资源信息。按照论文惯例，需后续查看附录。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 分词器对比表（Table 2）：包含多种分词器的重建结果，以及VFMTok的对比。
  - 图像生成主表（Table 3）：包含多种生成方法（扩散、BERT、AR、VAR等）在带CFG和不带CFG下的结果，以及VFMTok在不同规模模型（B/L/XXL/3B）上的表现，以及结合RAR框架的结果。
  - 消融实验（Table 4）：逐步添加组件（冻结VFM、区域自适应、多级特征、特征重建），记录重建和生成指标。
  - 其他消融（附录）：如码本大小、锚点查询数量、VFM选择等。
- **充分性与公平性**：
  - 实验覆盖了图像重建和生成的多个维度，与主流方法进行了公平比较（相同数据集、相似参数规模、相同训练epoch等）。
  - 消融实验系统性地验证了每个组件的贡献。
  - 提供了带CFG和不带CFG的比较，显示了其CFG-free能力。
  - 但未提供误差棒或多次重复实验，统计显著性未明确。此外，部分基线（如TiTok）由作者复现（标注†），可能存在复现偏差。

## 6. 论文的主要结论与发现

- 冻结的预训练VFM（自监督或语言监督）可以直接作为有效的图像分词器编码器，在图像重建和生成中达到甚至超越从头训练的VQGAN。
- 提出的区域自适应分词框架（VFMTok）能够利用语义区域的冗余性，用更少的令牌（256 vs 576）实现更优的重建质量和语义保真度。
- VFMTok产生的紧凑、语义丰富的潜在空间显著加速了AR模型的训练收敛（3倍加速），并实现了无需CFG的高保真类别条件生成，降低了推理时间。
- 在ImageNet 256×256上，结合RAR框架的VFMTok达到gFID 1.36，超越主流扩散模型，成为新的SOTA。

## 7. 优点（方法或实验设计上的亮点）

- **方法创新**：
  - 首次系统验证了冻结VFM直接作为分词器编码器的可行性，提供了简单有效的基线。
  - 区域自适应量化利用可变形注意力实现不规则语义区域采样，巧妙减少冗余，提升效率。
  - 特征重建目标保持语义保真度，结合多级特征提取，兼顾低级细节和高级语义。
- **实验设计**：
  - 对比全面：涵盖了主流分词器和生成模型，包括扩散、BERT、AR多种范式。
  - 消融实验清晰，逐步揭示各组件贡献。
  - 同时报告带CFG和不带CFG的结果，突出了CFG-free能力。
  - 代码开源，便于复现。

## 8. 不足与局限

- **实验覆盖不足**：
  - 仅基于ImageNet一个数据集，未涉及更大规模或更多样化数据集（如LAION、COCO等），泛化性待验证。
  - 未在文本到图像生成任务上验证，仅做类别条件生成。
  - 缺少对更高分辨率（如512×512）的实验。
- **偏差风险**：
  - 所有结果基于单次训练，未提供误差棒或统计显著性检验，可能受随机波动影响。
  - 部分基线（TiTok）为作者复现，可能与原论文最佳结果有差距（例如TiTok在无CFG下gFID为19.6，远高于VFMTok的2.04，但原TiTok论文宣称CFG-free能力，此处复现可能不准确）。
- **应用限制**：
  - 依赖特定VFM（DINOv2-L）的固定架构，更换VFM需要重新提取特征，灵活性受限。
  - 区域自适应分词依赖于可变形注意力，可能引入额外计算开销，未与最简方案（如直接下采样）对比效率。
  - 缺少对模型可解释性、模式坍缩、公平性等问题的讨论。
- **未明确说明算力消耗**，不利于他人复现时估计成本。

（完）
