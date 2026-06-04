---
title: "Vector Grimoire: Codebook-based Shape Generation under Raster Image Supervision"
title_zh: "Vector Grimoire: 基于码本的光栅图像监督形状生成"
authors: "Marco Cipriano, Moritz Feuerpfeil, Gerard de Melo"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=xYtLsWiUli"
tags: ["query:ce"]
score: 6.0
evidence: 用于文本引导SVG生成的自回归变换器
tldr: 针对SVG生成欠探索的问题，提出GRIMOIRE模型，包含Visual Shape Quantizer和Auto-Regressive Transformer，在无直接SVG监督下从自然语言生成矢量图形，填补了该领域空白。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 864, \"height\": 327, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1743, \"height\": 924, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 853, \"height\": 965, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 871, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 855, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 787, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 801, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 717, \"height\": 418, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 724, \"height\": 760, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 806, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 214, \"height\": 217, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 155, \"height\": 179, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 215, \"height\": 216, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 176, \"height\": 170, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1410, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1643, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1708, \"height\": 937, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 374, \"height\": 377, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 373, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 663, \"height\": 387, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 375, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 374, \"height\": 376, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 433, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1689, \"height\": 2279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1689, \"height\": 2270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1525, \"height\": 1712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1305, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1555, \"height\": 1696, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-xytlswiuli/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1721, \"height\": 1184, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1771, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1773, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1762, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 536, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 669, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1077, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1025, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 747, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 873, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 303, \"height\": 321, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1763, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 998, \"height\": 344, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-xytlswiuli/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1755, \"height\": 247, \"label\": \"Table\"}]"
motivation: SVG生成领域欠探索，现有方法依赖直接SVG监督。
method: 提出Visual Shape Quantizer学习光栅到码本的映射，Auto-Regressive Transformer建模形状、位置和文本的联合分布。
result: 在无直接SVG监督下成功生成矢量图形。
conclusion: 为文本引导矢量图形生成提供了新范式。
---

## Abstract
Scalable Vector Graphics (SVG) is a popular format on the web and in the design industry. However, despite the great strides made in generative modeling, SVG has remained underexplored due to the discrete and complex nature of such data. We introduce GRIMOIRE, a text-guided SVG generative model that is comprised of two modules: A Visual Shape Quantizer (VSQ) learns to map raster images onto a discrete codebook by reconstructing them as vector shapes, and an Auto-Regressive Transformer (ART) models the joint probability distribution over shape tokens, positions and textual descriptions, allowing us to generate vector graphics from natural language. Unlike existing models that require direct supervision from SVG data, GRIMOIRE learns shape image patches using only raster image supervision which opens up vector generative modeling to significantly more data. We demonstrate the effectiveness of our method by fitting GRIMOIRE for closed filled shapes on the MNIST and Emoji, and for outline strokes on icon and font data, surpassing previous image-supervised methods in generative quality and vector-supervised approach in flexibility.

---

## 论文详细总结（自动生成）

# 论文《Vector Grimoire: Codebook-based Shape Generation under Raster Image Supervision》中文总结

## 1. 核心问题与整体含义（研究动机和背景）

可缩放矢量图形（SVG）是一种在网页和设计行业中广泛应用的格式，具有精确和可缩放的特点。然而，尽管生成式模型在光栅图像领域取得了巨大进步，SVG的生成仍然是一个较少被探索的领域。主要原因在于SVG数据的离散性和复杂性：SVG文件由多种基本图元（如圆、线段、矩形等）组成，每种图元有不同的属性，且可以相互重叠和遮挡。现有的生成模型主要存在两大局限：一是需要直接使用SVG数据进行监督训练，这限制了可用数据量并增加了预处理负担；二是难以扩展至颜色、描边宽度等视觉属性。因此，本文旨在提出一种仅需光栅图像监督即可生成SVG的模型，从而利用更丰富的图像数据资源。

## 2. 方法论：核心思想、关键技术细节

- **整体架构**：GRIMOIRE由两个模块组成——**Visual Shape Quantizer（VSQ）** 和 **Auto-Regressive Transformer（ART）**。训练分两阶段进行。
- **第一阶段：Visual Shape Quantizer（VSQ）**
  - 采用**向量量化自编码器（VQ-VAE）**，但使用**有限标量量化（FSQ）** 代替传统码本。FSQ将编码后的表示投影到低维超立方体上最近的格点，隐式定义码本，简化损失函数。超立方体维度 \( q = 5 \)，每维取值数 \( L = [7, 5, 5, 5, 5] \)，总码本大小 \( |V| = 4375 \)。
  - 输入图像 \( I \) 被划分为 \( n \) 个 \( 128 \times 128 \) 的斑块 \( s_i \)。每个斑块经过 ResNet-18 编码器得到 \( \xi \) 个潜在编码，再经线性映射和量化得到 \( \xi \) 个离散码 \( v_i \)。
  - 解码器 \( D_{VSQ} \) 包含投影层和轻量网络 \( \Phi_{\text{points}} \)，后者预测 \( \nu \) 条三次贝塞尔曲线的控制点，构成一条连续路径。路径经由**可微分光栅化器 DiffVG** 得到重建光栅输出 \( \hat{s}_i \)。
  - 损失函数：重建损失采用均方误差 \( \mathcal{L}_{\text{recons}} = (s - \hat{s})^2 \)；此外提出**几何约束损失** \( \mathcal{L}_{\text{geom}} \)，惩罚控制点间距离的不均匀性，避免退化路径。总损失 \( \mathcal{L}_{VSQ} = \mathcal{L}_{\text{recons}} + \alpha \mathcal{L}_{\text{geom}} \)（默认 \( \alpha = 0.4 \)）。
  - 支持可选的额外预测头：\( \Phi_{\text{width}} \) 预测描边宽度，\( \Phi_{\text{color}} \) 预测描边或填充颜色。
- **第二阶段：Auto-Regressive Transformer（ART）**
  - 训练好的VSQ编码器将图像斑块映射为码序列；同时记录每个斑块在原图中的中心位置 \( \theta_i \)，离散化为 \( 256 \times 256 \) 网格的位置令牌。
  - 输入序列为：`<SOS>, 文本令牌, <BOS>, 位置令牌1, 码令牌1, ..., 位置令牌n, 码令牌n, <EOS>`。文本令牌由预训练BERT编码后经线性映射投影到d维空间。其他令牌使用可学习的嵌入矩阵。
  - ART为标准的因果Transformer解码器（字体数据集12层，图标数据集16层，8个注意力头），通过自回归方式学习联合分布，损失为因果交叉熵。
  - 推理时：仅提供`<SOS> + 文本 + <BOS>`，自回归生成后续令牌直至`<EOS>`，解码得到SVG。

## 3. 实验设计

- **数据集**：
  - **MNIST**：手写数字，每个图像上采样至128×128，以6×6网格切分成斑块。仅用于封闭形状实验。
  - **Emoji**：表情符号，使用 SAM（Segment Anything）模型生成掩膜，每个掩膜对应一个图层斑块。用于封闭形状+颜色实验。
  - **FIGR-8**：图标数据集，选取75个主流类别（427K样本）。使用轮廓查找算法提取外轮廓并分段。用于描边形状实验。
  - **Fonts**：SVG-Fonts 子集，包含大写/小写字母和数字（约200万样本）。直接使用矢量格式提取分段。
- **对比方法**：
  - **Im2Vec**：仅基于光栅监督的SVG生成模型（VAE+RNN），不支持文本条件。
  - **DeepSVG**：矢量监督的层级生成网络。
  - **IconShop**：基于LLM的矢量监督模型，通过令牌化SVG路径进行条件生成。
  - **Llama 3.2**：微调的通用语言模型（最小预处理）。
  - **SDS-based 方法**：CLIPDraw、VectorFusion、SVGDreamer（用于定性对比和速度/PSNR对比）。
- **评估指标**：MSE（重建损失）、FID（Fréchet Inception Distance）、CLIPScore（CLIP图像-文本相似度）、PSNR（峰值信噪比，仅用于SDS对比）。
- **场景**：
  - 重建（VSQ模块 vs Im2Vec 在不同数据集/类别的比较）
  - 文本条件生成（GRIMOIRE vs Im2Vec vs 矢量监督方法）
  - SVG完成（给定部分上下文的补全）
  - 跨域迁移（VSQ在一个数据集训练后在另一个数据集上重建）
  - 码本分析、消融实验（参数、几何损失、后处理等）

## 4. 资源与算力

论文明确提到了计算资源：
- VSQ模块训练：6块NVIDIA H100 GPU，MNIST约48小时，FIGR-8约15小时，Fonts约12小时。
- ART模块训练：约8小时（根据配置不同）。
- Im2Vec训练：单块GPU（原文未明确型号，但提及使用AdamW优化器，训练105个epoch）。
- Llama 3.2微调：8块H100 GPU，训练3天。
- SDS方法对比实验在单块H100上运行（生成时间测量）。

文中未提供总GPU小时的精确汇总，但各实验资源均有提及。

## 5. 实验数量与充分性

- **实验数量**：论文报告了大量实验，覆盖4个数据集、多种配置（不同斑块大小、码本大小、分段数量、码字数、几何损失权重、后处理方式等）。消融实验包括：码本大小分析（8个不同设置）、斑块/网格影响（3×3配置）、描边长度影响（3种长度×2种分段数）、几何损失权重（3个值）、后处理对比（3种方法）。
- **充分性**：实验设计较为全面，涵盖了重建、生成、完成、迁移、码本可视化、推理速度对比等。但部分比较（如与SDS方法）仅为定性且有量度（PSNR）但样本量较少（20个样本）。与矢量监督方法的对比（DeepSVG、IconShop、Llama）限于FIGR-8数据集，且未在Fonts上对比。整体来说实验是充分的，但与真实应用场景的泛化能力可能还需更多验证。
- **客观性与公平性**：作者对Im2Vec进行了复现和调参（替换优化器、启用KL权重等），尽量保证公平。但Im2Vec不支持文本条件，因此纹理条件生成对比中Im2Vec仅在单一类上训练，而GRIMOIRE在全数据集上训练，这种比较存在一定不公平性，作者也承认了这一点。指标选择上，FID在低分辨率图像上可能不稳定，作者用CLIPScore作为补充。

## 6. 主要结论与发现

- GRIMOIRE是首个仅通过光栅图像监督实现文本条件SVG生成的模型，无需原始SVG数据。
- VSQ模块在重建精度上全面优于Im2Vec（更低MSE，更高CLIPScore），尤其是在复杂图标和字体上。
- ART模块生成的文本条件SVG在CLIPScore上优于Im2Vec（即使Im2Vec只在单类上训练），且生成的图形更干净、冗余形状更少。
- GRIMOIRE支持自动SVG完成，可部分上下文补全未见过图标。
- VSQ易于扩展至颜色、宽度等属性，无需修改码本或架构。
- 与SDS方法相比，GRIMOIRE生成速度快2个数量级（约2.34秒 vs 100-380秒），且生成的SVG更贴合训练数据分布（PSNR更高）。
- 与矢量监督方法（IconShop）相比，GRIMOIRE性能略低但灵活性更高（无需SVG预处理管线）。

## 7. 优点

- **仅需光栅监督**：规避了SVG数据稀缺和预处理复杂的问题，可扩展至更大规模数据。
- **灵活的架构**：两阶段设计解耦了视觉量化与序列生成，ART可独立于VSQ的属性扩展。
- **可扩展性**：可通过增加VSQ预测头（颜色、宽度等）支持新属性，无需重新设计。
- **推理效率高**：一次前向传播即可生成，远快于迭代优化的SDS方法。
- **支持多种下游任务**：文本到SVG、SVG完成、插值等。
- **代码开源**：便于复现和社区改进。

## 8. 不足与局限

- **依赖DiffVG**：可微分光栅化器本身有局限性（如抗锯齿、梯度传回等），可能影响复杂形状的生成质量。
- **码本容量固定**：FSQ码本大小由超立方体维度和取值数决定，不能动态调整。文中实验显示4375大小已足够，但可能不适用于更丰富形状数据集。
- **后处理需求**：由于分段和位置离散化，最终SVG常有断开片段，需要路径裁剪/插值等后处理，引入额外步骤和不确定因素。
- **实验覆盖**：
  - 与SDS方法的对比样本量较小（20个），且仅针对单个图标类别，不够全面。
  - 与矢量监督方法（IconShop）的对比仅在FIGR-8上，未在Fonts或Emoji上验证。
  - 跨域迁移仅展示定性结果，没有量化指标。
- **文本条件能力有限**：使用BERT编码文本，并未进行细粒度的文本-形状对齐（如特定位置的描述），生成多样性和复杂指令遵循能力未评估。
- **应用限制**：目前仅限于封闭形状和简单描边，对复杂填充、渐变、透明等矢量常见特性未涉及。Emoji实验仅为初步结果，训练样本很少（107个），泛化性未知。
- **计算资源**：VSQ训练需要多GPU较长时间，可能限制小型团队复现。

（完）
