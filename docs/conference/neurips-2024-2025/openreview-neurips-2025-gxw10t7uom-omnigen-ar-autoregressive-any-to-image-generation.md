---
title: "OmniGen-AR: AutoRegressive Any-to-Image Generation"
title_zh: OmniGen-AR：自回归任意到图像生成
authors: "Junke Wang, Xun Wang, Qiushan Guo, Peize Sun, Weilin Huang, Zuxuan Wu, Yu-Gang Jiang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Gxw10T7uOm"
tags: ["query:ce"]
score: 8.0
evidence: 自回归任意到图像生成，包括文本到图像
tldr: 现有自回归视觉生成模型通常只支持单一模态条件。OmniGen-AR通过共享视觉分词器和文本分词器，将多种视觉条件和文本提示离散化，首次实现统一的任意到图像生成框架。实验表明，该模型在多种条件输入下均能生成高质量图像。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 774, \"height\": 570, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1433, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1442, \"height\": 442, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 827, \"height\": 414, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 892, \"height\": 379, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1408, \"height\": 295, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 288, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 292, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 280, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1414, \"height\": 299, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1414, \"height\": 298, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1438, \"height\": 896, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gxw10t7uom/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1443, \"height\": 533, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 670, \"height\": 512, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 794, \"height\": 676, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1455, \"height\": 438, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 643, \"height\": 725, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 538, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gxw10t7uom/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 588, \"height\": 342, \"label\": \"Table\"}]"
motivation: 现有自回归模型局限于单一模态条件，无法满足多条件输入的实际需求。
method: 通过共享视觉分词器离散化各种视觉条件，结合文本分词器，在单一模型中支持文本、分割图等多种条件。
result: 在多个文本到图像和条件图像生成任务上表现优异。
conclusion: 统一的任意到图像生成为实际应用提供了更灵活的解决方案。
---

## Abstract
Autoregressive (AR) models have demonstrated strong potential in visual generation, offering competitive performance with simple architectures and optimization objectives. However, existing methods are typically limited to single-modality conditions, \eg, text or category labels, restricting their applicability in real-world scenarios that demand image synthesis from diverse forms of controls. In this work, we present \system, the first unified autoregressive framework for Any-to-Image generation. By discretizing various visual conditions through a shared visual tokenizer and text prompts with a text tokenizer, \system supports a broad spectrum of conditional inputs within a single model, including text (text-to-image generation), spatial signals (segmentation-to-image and depth-to-image), and visual context (image editing, frame prediction, and text-to-video generation). To mitigate the risk of information leakage from condition tokens to content tokens, we introduce Disentangled Causal Attention (DCA), which separates the full-sequence causal mask into condition causal attention and content causal attention. It serves as a training-time regularizer without affecting the standard next-token prediction during inference. With this design, \system achieves new state-of-the-art results across a range of benchmark, \eg, 0.63 on GenEval and 80.02 on VBench, demonstrating its effectiveness in flexible and high-fidelity visual generation.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机与背景）

- **研究动机**：现有自回归（AR）视觉生成模型通常只支持单一模态条件输入（如文本标签、类别标签），无法满足实际应用中需要从多种条件（如文本、分割图、深度图、参考图像、历史帧等）生成图像的需求。
- **整体含义**：本文首次提出统一的任意到图像生成（Any-to-Image）自回归框架 **OmniGen-AR**，在一个模型中同时支持文本到图像、文本到视频、帧预测、图像编辑、深度图到图像、分割图到图像等多种生成任务，填补了现有AR模型在多功能性上的空白。

## 2. 方法论

### 2.1 核心思想
通过共享的视觉分词器（Cosmos-DV8×16×16）将各种视觉条件（分割图、深度图、参考图像）离散化为统一格式的视觉token序列，同时使用文本分词器（Qwen2.5）处理文本提示。将条件token和内容token按任务格式拼接，用解码器-仅Transformer进行自回归下一token预测。

### 2.2 关键技术细节
- **视觉与文本分词**：图像/视频/条件都使用同一视觉tokenizer编码为离散token序列，文本使用语言模型tokenizer。
- **序列构造**：空间/图像条件任务：`[t, v, x]`；文本条件任务：`[t, x]`。
- **自回归Transformer**：采用因果注意力掩码（下三角矩阵）保持左到右生成顺序。
- **解耦因果注意力（DCA）**：针对信息泄露问题，将注意力掩码分为条件因果注意力和内容因果注意力，阻止内容token关注条件token，但保留位置信息。训练时以10%概率随机替换标准因果注意力，推理时仍用标准自回归预测。

### 2.3 算法流程（文字说明）
1. 对于每种任务，构造token序列：文本+条件（若有）+待生成内容。
2. 训练时，随机应用DCA或标准因果注意力，用语言建模损失（交叉熵）优化。
3. 推理时，按概率采样下一token（使用分类器自由引导CFG，比例6.0），解码为图像。

## 3. 实验设计

### 3.1 使用的数据集（三阶段训练）
- **第一阶段（单图像）**：CC3M、CC12M、OpenImages、SAM1B、Megalith-huggingface；以及来自Panda70M和HD-VILA-100M的视频数据（每视频采样1帧）。
- **第二阶段（图像-视频联合）**：同上，但视频采样9帧。
- **第三阶段（多任务）**：文本到图像（JourneyDB、合成数据集、10M内部数据）、图像编辑（MagicBrush、Instruct-Pix2Pix、SEED-Edit）、深度到图像（MultiGen-Depth）、分割到图像（MultiGen-ADE20k、MultiGen-COCOStuff）、文本到视频（OpenSora-pexels-45k、OpenVid-1M、0.5M内部数据）。所有图像/视频使用Qwen2-VL重新描述。

### 3.2 Benchmark
- **文本到图像**：GenEval（评估多物体、位置、颜色等对齐）。
- **文本到视频**：VBench（评估质量和语义一致性）。
- **帧预测**：Kinetics-600（FVD指标）。
- **图像编辑**：Emu-Edit测试集（CLIP文本相似度CT、CLIP图像相似度CI）。
- **空间条件生成**：ADE20K（分割到图像mIoU）、MultiGen-Depth-Eval（深度到图像RMSE）。

### 3.3 对比方法
- 文本到图像：SDv1.5/2.1、PixArt-alpha、LLamaGen、SimpleAR、DALL-E 2、Show-o、Infinity、Janus、Emu3等。
- 文本到视频：CogVideo、LaVie、OpenSora、CogVideoX、Hunyuan、Mira、TF-T2V、AniDiff、VidCrafter、Wan2.1等。
- 图像编辑：Instruct-Pix2Pix、MagicBrush、PnP、Null-Text、Emu-Edit、OmniGen。
- 空间条件：Uni-ControlNet、GLIGEN、EditAR、ControlNet、ControlAR、OmniGen。

## 4. 资源与算力

- **GPU型号与数量**：64张A100 GPU。
- **训练时长**：三阶段训练，未明确各阶段具体时长，但全局批大小256，学习率第一、二阶段1e-4（分辨率512），第三阶段2e-5（分辨率1024）。使用AdamW优化器，无预热和学习率衰减。
- **说明**：文中未给出总训练天数/小时数，但提到了训练配置细节。

## 5. 实验数量与充分性

- **实验组数**：文中报告了6个主要任务的定量结果，包括T2I、T2V、帧预测、图像编辑、分割到图像、深度到图像。此外还进行了消融实验：
  - DCA替换概率的影响（0%、5%、10%、20%、30%）。
  - 联合训练 vs 单独训练（对比T2I、T2V、编辑、分割任务）。
  - 模型规模缩放（0.5B vs 1.5B定性对比）。
- **充分性与公平性**：实验覆盖了多个主流基准，对比方法包括当前SOTA的扩散模型和自回归模型，指标标准（GenEval、VBench、FVD、CLIP相似度、mIoU、RMSE）。但未报告误差棒（因计算成本太高），且部分消融仅在0.5B模型上完成。整体实验设计较全面，但联合训练时存在任务间相互影响（T2I/T2V性能下降），作者解释为训练数据质量差异。

## 6. 主要结论与发现

- **整体性能**：OmniGen-AR在0.5B参数下在GenEval得0.55，1.5B参数下得0.63，超越同规模所有模型；在VBench上0.5B得74.72，1.5B得80.02，为自回归模型首次达到80+分。
- **DCA有效性**：以10%概率应用DCA相比不使用（0%）在图像编辑CLIP文本相似度从0.15提升至0.20，空间条件任务也有小幅提升，证明DCA可缓解信息泄露、促进指令跟随。
- **多任务协同**：联合训练提升了编辑和分割任务性能，但降低了T2I/T2V指标，作者认为基础能力（文本条件生成）的强化有助于下游任务，但低质量条件数据会拖累主任务。
- **模型缩放**：放大模型参数（0.5B→1.5B）显著提高生成质量和指令跟随能力。

## 7. 优点

- **方法创新性**：首次提出统一的任意到图像生成自回归框架，无需为每种条件训练单独模型。DCA作为一种训练时正则化，不改变推理流程，简单有效。
- **实验全面性**：涵盖6种生成任务，对比多个SOTA方法，在多个基准上达到SOTA或竞争性能。
- **模块化设计**：使用共享视觉分词器统一处理各类条件，易于扩展。
- **可扩展性**：展示了模型缩放带来的增益，验证了自回归范式的潜力。

## 8. 不足与局限

- **联合训练冲突**：多任务联合训练导致文本到图像和文本到视频性能下降，可能存在任务干扰，需要更精细的训练策略或数据平衡。
- **未报告误差棒**：由于计算成本未报告统计显著性，部分结论的稳健性需进一步验证。
- **失败案例分析**：模型在复杂指令跟随（如删除特定对象而非整体）和稀疏控制信号（深度/分割条件）下出现模糊或结构不一致结果，说明对细粒度空间推理和低质量条件训练覆盖仍不足。
- **训练数据未完全公开**：使用了内部数据和重新标注，限制了完全可复现性。
- **DCA概率选择**：仅实验了少数几个概率值（0%~30%），最优可能因任务而异，未深入分析。
- **应用限制**：模型仍面临深度伪造、偏见等伦理风险，文中未详细讨论防护措施。

（完）
