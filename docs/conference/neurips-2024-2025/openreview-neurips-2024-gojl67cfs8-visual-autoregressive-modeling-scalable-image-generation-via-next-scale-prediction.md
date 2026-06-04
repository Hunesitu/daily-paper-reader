---
title: "Visual Autoregressive Modeling: Scalable Image Generation via Next-Scale Prediction"
title_zh: 视觉自回归建模：通过下一尺度预测实现可扩展图像生成
authors: "Keyu Tian, Yi Jiang, Zehuan Yuan, BINGYUE PENG, Liwei Wang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=gojL67CfS8"
tags: ["query:ce"]
score: 8.0
evidence: 自回归图像生成
tldr: 自回归图像生成通常按逐令牌方式生成，VAR提出按从粗到细的尺度预测，使GPT风格的自回归模型在ImageNet上首次超越扩散模型，FID从18.65降至1.73。该方法简单、高效，且具有强大的泛化能力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1273, \"height\": 666, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1401, \"height\": 489, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 723, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 723, \"height\": 353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 679, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 421, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1443, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1350, \"height\": 1720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1380, \"height\": 1119, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1328, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1363, \"height\": 2086, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gojl67cfs8/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1448, \"height\": 1509, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-gojl67cfs8/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 665, \"height\": 426, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gojl67cfs8/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 632, \"height\": 432, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gojl67cfs8/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1283, \"height\": 1066, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gojl67cfs8/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 724, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gojl67cfs8/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1435, \"height\": 409, \"label\": \"Table\"}]"
motivation: 标准自回归图像生成采用逐令牌预测，未能利用图像的多尺度结构。
method: 将自回归学习定义为从粗到细的“下一尺度预测”或“下一分辨率预测”。
result: 在ImageNet 256x256上，VAR取得了1.73的FID，推理速度比扩散模型快约20倍。
conclusion: VAR为自回归图像生成提供了新范式，性能强大且可扩展。
---

## Abstract
We present Visual AutoRegressive modeling (VAR), a new generation paradigm that redefines the autoregressive learning on images as coarse-to-fine "next-scale prediction" or "next-resolution prediction", diverging from the standard raster-scan "next-token prediction". This simple, intuitive methodology allows autoregressive (AR) transformers to learn visual distributions fast and generalize well: VAR, for the first time, makes GPT-style AR models surpass diffusion transformers in image generation. On ImageNet 256x256 benchmark, VAR significantly improve AR baseline by improving Frechet inception distance (FID) from 18.65 to 1.73, inception score (IS) from 80.4 to 350.2, with around 20x faster inference speed. It is also empirically verified that VAR outperforms the Diffusion Transformer (DiT) in multiple dimensions including image quality, inference speed, data efficiency, and scalability. Scaling up VAR models exhibits clear power-law scaling laws similar to those observed in LLMs, with linear correlation coefficients near -0.998 as solid evidence. VAR further showcases zero-shot generalization ability in downstream tasks including image in-painting, out-painting, and editing. These results suggest VAR has initially emulated the two important properties of LLMs: Scaling Laws and zero-shot task generalization. We have released all models and codes to promote the exploration of AR/VAR models for visual generation and unified learning.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：传统的自回归（AR）图像生成模型（如 VQGAN）采用逐像素或逐 Token 的栅格扫描顺序（raster-scan），将二维图像展平为一维序列进行“下一 Token 预测”。但这种方式存在三个主要问题：(1) **数学前提违背**——VQVAE 编码器的特征图本身具有双向依赖，而自回归假设要求单向依赖；(2) **空间结构性退化**——展平操作破坏了图像中邻近 Token 的空间局部性；(3) **推理效率低下**——生成一张 n×n 的潜变量图需要 O(n²) 次自回归迭代和 O(n⁶) 的计算复杂度。此外，传统 AR 模型的性能远落后于扩散模型（如 DiT），且其 scaling law 尚未得到充分验证。
- **核心含义**：本文提出一种全新的视觉自回归建模范式 —— **Visual AutoRegressive (VAR)**，将自回归学习从“下一 Token 预测”重新定义为“下一尺度预测”（next-scale prediction），即从粗到细地逐级生成多尺度 Token 图。该方法在 ImageNet 256×256 上首次使 GPT 风格的自回归模型超越扩散变压器（Diffusion Transformer），并展现出与 LLM 相似的幂律缩放定律和零样本泛化能力。

## 2. 论文提出的方法论

### 核心思想
- 不再将图像展平为一维序列逐 Token 预测，而是将图像编码为 **K 个多尺度 Token 图** (r₁, r₂, …, r_K)，分辨率逐级递增，最终与原始特征图大小一致。
- 自回归过程从最小的 1×1 Token 图开始，每一步预测下一个更高分辨率的 Token 图，条件为前面所有低分辨率图。同一尺度内的 Token 并行生成。
- **概率建模**：`p(r₁, r₂, ..., r_K) = Π_{k=1}^K p(r_k | r₁, ..., r_{k-1})`

### 关键技术细节
- **多尺度 VQVAE**：在标准 VQGAN 架构基础上，修改量化层以支持多尺度输出。通过残差方式设计，使每个尺度的 Token 图仅依赖于其前缀（粗尺度）。使用共享大小为 4096 的码书，并添加 K 个额外的卷积层（仅 0.03M 参数）用于上采样时的信息补偿。
- **VAR Transformer**：采用 GPT-2 风格的仅解码器 Transformer，配合自适应层归一化（AdaLN）和注意力中 Q/K 的归一化以稳定训练。模型宽度、头数、丢弃率随深度线性缩放：`w = 64d, h = d, dr = 0.1·d/24`，参数量 `N(d) = 73728d³`。
- **训练**：两阶段训练。第一阶段训练多尺度 VQVAE（在 OpenImages 上，损失函数含重建、感知、对抗损失）。第二阶段训练 VAR Transformer，使用块状因果注意力掩码，输入为开始标记 [s] 和前缀 Token 图，输出预测下一尺度 Token 图，优化交叉熵损失。

## 3. 实验设计

- **数据集**：
  - 图像生成：**ImageNet 256×256 和 512×512** 条件生成。
  - 零样本下游任务：图像修补（in-painting）、外扩（out-painting）、类别条件编辑（class-conditional editing）。
- **Benchmark**：标准 FID、IS、Precision、Recall。同时报告了推理步数和时间（相对时间）。
- **对比方法**：
  - GAN：BigGAN, GigaGAN, StyleGAN-XL
  - 扩散模型：ADM, CDM, LDM-4-G, DiT (XL/2), L-DiT-3B, L-DiT-7B
  - 掩码预测模型：MaskGIT, RCG
  - AR 模型：VQVAE-2, VQGAN, ViT-VQGAN, RQ-Transformer
- **公平性**：所有对比均引用已发表结果或基于同一 baseline（VQGAN）如实报告。VAR 的 tokenizer 与 VQGAN 使用相同的架构和训练数据（OpenImages），确保对比公平。

## 4. 资源与算力

- 文中明确提到：
  - 训练时使用 **Batch size 768~1024**，训练 **200~350 epoch**。
  - 学习率 `1e-4` per 256 batch，AdamW 优化器。
  - 模型从 **18M 到 2B 参数**共训练了 12 个不同尺寸的模型。
  - 最大训练 Token 数达到 **3050亿**。
  - 计算量用 PFlops 衡量，在图 6 中展示了与最优训练计算量的关系。
- **未明确说明**：使用的 GPU 型号、数量、具体训练时长（小时/天）。论文只提到推理速度相对 AR 快 20 倍，以及 DiT 推理慢若干倍，但未给出绝对 GPU 天数。

## 5. 实验数量与充分性

- **实验数量**：
  - 图像生成：在 256×256 和 512×512 上各一个主表，包含 14 种对比方法，VAR 报告了 4 个不同规模（d16, d20, d24, d30）的结果。
  - 缩放定律：训练了 12 个不同尺寸的模型，从 18M 到 2B，验证了测试损失和 Token 错误率与参数/计算量的幂律关系。
  - 消融实验：在表 3 中做了 5 步消融（AR→VAR、+AdaLN、+Top-k、+CFG、+Attention Norm、+Scale up），每步 FID 变化显著。
  - 零样本泛化：展示了修补、外扩、编辑的定性结果（图 8）。
- **充分性与公平性**：
  - 实验覆盖了主流生成范式，对比全面。VAR 的 baseline 与 VQGAN 一致，组件逐步叠加，消融清晰。
  - 缩放定律实验使用了多组幂律拟合，相关系数接近 -0.998，统计证据充分。
  - 但未提供误差线（因资源限制未重复多次实验），可能对统计显著性有影响。
  - 零样本实验仅定性展示，缺少定量指标（如 FID 或用户研究），说服力稍弱。

## 6. 论文的主要结论与发现

1. **性能突破**：VAR 在 ImageNet 256×256 上取得 **FID 1.73**（2B 模型 + 拒绝采样），显著优于传统 AR（18.65）和当时最强的扩散模型 DiT（2.27）和 L-DiT-7B（2.28）。**推理速度约比 DiT 快 20 倍**。
2. **缩放定律**：VAR 模型展现出与 LLM 一致的清晰幂律缩放关系（测试损失与参数/计算量的 Pearson 相关系数 > -0.998），这是视觉生成模型中首次严格验证。
3. **零样本泛化**：VAR 在图像修补、外扩、类别条件编辑等下游任务上表现出合理的零样本能力，无需微调或架构修改。
4. **效率与可扩展性**：VAR 在数据效率（更少 epoch 达到更好性能）、推理速度、参数扩展上均优于 DiT，为视觉生成提供了新的高效范式。

## 7. 优点

- **方法创新性**：将自回归从逐 Token 预测改为逐尺度预测，直观且符合人类从粗到细的感知过程，同时巧妙地解决了传统 AR 的数学和效率问题。
- **理论严谨性**：分析了传统 AR 的三个缺陷并一一对应解法，数学上证明了 VAR 的时间复杂度降至 O(n⁴)（附录 D），并通过注意力可视化验证了 VQVAE 中的双向依赖（附录 C）。
- **实验全面性**：覆盖主基准、缩放定律、消融、零样本，对比方法包含 GAN、扩散、掩码、自回归四大类，结论可信度高。
- **开源贡献**：公开了所有代码和模型，推动社区发展。
- **实用性**：推理速度快、效果好，可直接用于实际生成任务，且易与 LLM 集成进行文本到图像生成。

## 8. 不足与局限

- **Tokenizer 限制**：论文强调主要贡献在范式，使用的 VQVAE 与 baseline 相同（CNN 架构、OpenImages 训练），未采用更先进的 tokenizer（如 MoVQ、FSQ），限制了生成质量的进一步提升。作者自己也指出这是正交方向。
- **未涉及文本提示生成**：论文仅在类条件生成上实验，未探索文本到图像。虽然提到是 ongoing 方向，但本篇缺乏相关实验。
- **视频生成仅作展望**：未实际实现视频生成，但文中提出可扩展为“3D 下一尺度预测”，缺乏实证。
- **零样本泛化缺乏定量指标**：仅展示定性结果，未提供 FID、LPIPS 等量化评价，难以严格比较。
- **算力和错误报告缺失**：未给出 GPU 型号、数量、训练总时长，也未报告误差棒（error bars），可能影响复现和统计公平性。
- **应用限制**：实验仅在 ImageNet 上进行，未在更通用的自然图像或跨域场景测试；模型参数已达 2B，对资源要求较高。

（完）
