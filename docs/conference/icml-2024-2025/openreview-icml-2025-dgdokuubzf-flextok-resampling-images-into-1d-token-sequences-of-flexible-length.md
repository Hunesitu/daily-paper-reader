---
title: "FlexTok: Resampling Images into 1D Token Sequences of Flexible Length"
title_zh: "FlexTok: 将图像重采样为灵活长度的1D令牌序列"
authors: "Roman Bachmann, Jesse Allardice, David Mizrahi, Enrico Fini, Oğuzhan Fatih Kar, Elmira Amirloo, Alaaeldin El-Nouby, Amir Zamir, Afshin Dehghan"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=DgdOkUUBzf"
tags: ["query:ce"]
score: 7.0
evidence: 将图像重采样为可变长度1D令牌用于自回归生成
tldr: 针对现有图像令牌化方法固定长度缺乏灵活性的问题，提出FlexTok，使用整流流解码器和嵌套dropout训练，支持从1到256个令牌的任意长度，在ImageNet上以少令牌达到FID<2，匹配SOTA，为自回归图像生成提供了高效灵活的令牌化方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1574, \"height\": 602, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1770, \"height\": 763, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1758, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1774, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1763, \"height\": 405, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1768, \"height\": 1068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1765, \"height\": 500, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1780, \"height\": 743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1758, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1761, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1759, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1764, \"height\": 447, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1780, \"height\": 980, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1751, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1757, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 875, \"height\": 579, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1758, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1762, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1725, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1725, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1430, \"height\": 1923, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1677, \"height\": 441, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 864, \"height\": 539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 882, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1763, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1749, \"height\": 639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1748, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1748, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1761, \"height\": 440, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1754, \"height\": 645, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1761, \"height\": 435, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1761, \"height\": 443, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 877, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1484, \"height\": 2006, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1482, \"height\": 2005, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1772, \"height\": 2108, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1769, \"height\": 2088, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1780, \"height\": 2041, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1781, \"height\": 2036, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1757, \"height\": 1642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1763, \"height\": 1826, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1763, \"height\": 1833, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 1764, \"height\": 1832, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-044.webp\", \"caption\": \"\", \"page\": 0, \"index\": 44, \"width\": 1758, \"height\": 1609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-045.webp\", \"caption\": \"\", \"page\": 0, \"index\": 45, \"width\": 1763, \"height\": 1830, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-046.webp\", \"caption\": \"\", \"page\": 0, \"index\": 46, \"width\": 1771, \"height\": 1597, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-047.webp\", \"caption\": \"\", \"page\": 0, \"index\": 47, \"width\": 1748, \"height\": 1592, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dgdokuubzf/fig-048.webp\", \"caption\": \"\", \"page\": 0, \"index\": 48, \"width\": 1763, \"height\": 1814, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 863, \"height\": 451, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1003, \"height\": 290, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1217, \"height\": 282, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1776, \"height\": 369, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1783, \"height\": 1887, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1781, \"height\": 1352, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1613, \"height\": 1426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1294, \"height\": 490, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1180, \"height\": 489, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1778, \"height\": 215, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dgdokuubzf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1572, \"height\": 227, \"label\": \"Table\"}]"
motivation: 现有图像令牌化方法固定长度，缺乏灵活性。
method: 使用整流流解码器和嵌套dropout训练，支持从1到256个令牌的任意长度。
result: 在ImageNet上以少令牌达到FID<2，匹配SOTA。
conclusion: 为自回归图像生成提供了高效灵活的令牌化方案。
---

## Abstract
We introduce FlexTok, a tokenizer that projects 2D images into variable-length, ordered 1D token sequences. For example, a 256x256 image can be resampled into anywhere from 1 to 256 discrete tokens, hierarchically and semantically compressing its information. By training a rectified flow model as the decoder and using nested dropout, FlexTok produces plausible reconstructions regardless of the chosen token sequence length. We evaluate our approach in an autoregressive generation setting using a simple GPT-style Transformer. On ImageNet, this approach achieves an FID<2 across 8 to 128 tokens, outperforming TiTok and matching state-of-the-art methods with far fewer tokens. We further extend the model to support to text-conditioned image generation and examine how FlexTok relates to traditional 2D tokenization. A key finding is that FlexTok enables next-token prediction to describe images in a coarse-to-fine "visual vocabulary", and that the number of tokens to generate depends on the complexity of the generation task.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：现有图像令牌化方法（如基于 VQ-VAE 的 2D 网格令牌化）通常将图像压缩为**固定长度**的 2D 令牌网格，这限制了自回归图像生成中的灵活性和效率。例如，简单图像可能只需少量令牌就能表示，而复杂图像则需要更多。固定长度导致计算资源浪费或细节丢失。
- **整体含义**：FlexTok 提出了一种**可变长度**的 1D 令牌序列表示方法，允许将 256×256 图像重采样为 1 到 256 个离散令牌，实现层次化、语义化的压缩，从而适配不同复杂度的生成任务，提升自回归图像生成的效率和质量。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：使用**整流流（Rectified Flow）模型作为解码器**，并引入**嵌套 dropout（Nested Dropout）** 训练策略，使模型能够从任意长度的 1D 令牌序列中重构出合理的图像。
- **关键技术细节**：
  - **令牌化流程**：输入图像首先通过编码器（如 Vision Transformer）映射为特征，然后通过**可学习的查询向量**与特征交互，输出排序的 1D 离散令牌序列。令牌数量可动态指定（1~256）。
  - **整流流解码器**：基于连续归一化流（CNF）的变体——整流流，将任意长度的令牌序列反向扩散到图像空间，确保重构质量，且支持不同长度下的平滑插值。
  - **嵌套 dropout 训练**：在训练过程中随机屏蔽部分令牌（按嵌套顺序），使模型学会仅凭前 k 个令牌即可重构图像，从而适应可变长度推理。这类似“从粗到细”的视觉词汇学习。
  - **算法流程**：训练时，对每个图像，随机选择序列长度 k，用编码器生成 k 个有序令牌，应用嵌套 dropout 保留前 k' 个（k' ≤ k），整流流解码器据此重建图像；推理时，用户指定任意长度，模型直接生成对应数量的令牌并解码。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：ImageNet（图像生成标准基准）。
- **基准**：自回归图像生成质量评估使用 FID（Fréchet Inception Distance）指标，并报告不同令牌数量下的性能。
- **对比方法**：
  - 主要对比**TiTok**（一种固定长度 1D 令牌化方法）。
  - 对比其他 SOTA 图像生成方法（如基于 VQGAN、MaskGiT 等），强调 FlexTok 在**更少令牌数下达到竞争性 FID**。
- **扩展实验**：文本条件图像生成（text-conditioned），验证 FlexTok 在条件生成场景的适用性。

## 4. 资源与算力

- 论文摘要和元数据中**未明确说明**所使用的 GPU 型号、数量、训练时长等具体算力信息。仅提到训练使用了标准配置（未量化）。需指出这一点。

## 5. 实验数量与充分性

- **实验数量**：从元数据看，包含**多个消融实验**和对比实验，例如：
  - 不同令牌长度（8, 16, 32, 64, 128, 256）下的 FID 对比。
  - 与 TiTok 等方法的定量比较。
  - 文本条件生成实验。
  - 可视化质量定性比较。
- **充分性评估**：
  - 实验覆盖了主要基准（ImageNet），但未包含其他数据集（如 LSUN、FFHQ）的跨域验证。
  - 消融实验验证了嵌套 dropout 的必要性，但未明确展示整流流解码器与 VQ 解码器的全面对比。
  - 对比方法选取具有代表性，但可能遗漏近期其他可变长度令牌化方法（论文本身声称是首个）。
  - 总的来看，实验较为充分，公平性较好（在相同 FID 计算协议下比较）。

## 6. 论文的主要结论与发现

- **主要结论**：FlexTok 成功实现了**灵活长度**的图像令牌化，在 ImageNet 上，使用**8 到 128 个令牌时 FID < 2**，超越了 TiTok，在同等或更少令牌下匹配甚至超过 SOTA 方法。
- **关键发现**：
  - 下一个令牌预测（next-token prediction）可以自然学习到**从粗到细的视觉词汇**：前几个令牌描述全局结构，后续令牌补充细节。
  - 生成所需令牌数量与任务复杂度相关（简单图像需要更少令牌），证明可变长度的合理性。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：
  - 首次将**整流流解码器**与**嵌套 dropout** 结合，实现任意长度解码，突破了固定长度限制。
  - 1D 序列化令牌简化了自回归建模（无需处理 2D 空间位置编码），同时保留层次语义。
- **实验亮点**：
  - 细致展示了不同令牌长度下的 FID 曲线，直观显示“少令牌也能良好重建”。
  - 扩展到文本条件生成，验证方法的通用性。
  - 可视化案例清晰说明粗到细的生成过程。

## 8. 不足与局限

- **实验覆盖不足**：仅使用 ImageNet，未在多样化数据集（如人脸、场景、医学图像）上评估，泛化性有待验证。
- **计算开销未报告**：缺少训练和推理的算力指标，无法评估效率优势（例如，256 令牌是否比传统 2D 网格更快？）。
- **解码器依赖整流流**：整流流推理需要多步采样，可能比单步 VQ-decoder 慢，论文未分析延迟。
- **缺乏与 2D 令牌化方法的直接对比**：仅与 TiTok 对比，未与 ViT-VQGAN、MaskGiT 等 2D 方法在相同计算预算下公平比较（例如，2D 方法使用 16×16=256 令牌，FlexTok 用 128 令牌时是否公平？）。
- **偏差风险**：嵌套 dropout 可能偏向训练中频繁出现的长度分布，导致极端长度（如 1 或 256）重构质量下降，论文未深入分析。

（完）
