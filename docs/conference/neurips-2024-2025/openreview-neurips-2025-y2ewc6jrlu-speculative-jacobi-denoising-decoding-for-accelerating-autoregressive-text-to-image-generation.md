---
title: Speculative Jacobi-Denoising Decoding for Accelerating Autoregressive Text-to-image Generation
title_zh: 推测性雅可比去噪解码加速自回归文本到图像生成
authors: "Yao Teng, Fu-Yun Wang, Xian Liu, Zhekai Chen, Han Shi, Yu Wang, Zhenguo Li, Weiyang Liu, Difan Zou, Xihui Liu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=y2eWc6jrlu"
tags: ["query:ce"]
score: 8.0
evidence: 推测性雅可比去噪解码加速自回归文本到图像生成
tldr: 本文提出SJD2，通过将去噪过程融入雅可比迭代，实现自回归文本到图像模型的并行令牌生成。利用下一干净令牌预测范式，使预训练模型接受噪声扰动嵌入并对低代价微调进行处理。显著加速推理同时保持生成质量。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-y2ewc6jrlu/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 1475, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y2ewc6jrlu/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 674, \"height\": 743, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y2ewc6jrlu/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 678, \"height\": 741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y2ewc6jrlu/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 544, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y2ewc6jrlu/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 792, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y2ewc6jrlu/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 697, \"height\": 953, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y2ewc6jrlu/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 695, \"height\": 951, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y2ewc6jrlu/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1431, \"height\": 951, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-y2ewc6jrlu/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1258, \"height\": 1212, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-y2ewc6jrlu/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1379, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y2ewc6jrlu/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1421, \"height\": 439, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y2ewc6jrlu/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1105, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y2ewc6jrlu/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 816, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y2ewc6jrlu/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 765, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y2ewc6jrlu/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y2ewc6jrlu/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 768, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-y2ewc6jrlu/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1448, \"height\": 382, \"label\": \"Table\"}]"
motivation: 自回归文本到图像模型逐令牌解码速度慢，需要数千次前向传播。
method: 将去噪融入雅可比迭代，训练模型从噪声嵌入预测干净令牌以并行生成。
result: 大幅提升生成速度，质量无损或略有提升。
conclusion: 雅可比去噪解码为自回归生成提供了高效加速框架。
---

## Abstract
As a new paradigm of visual content generation, autoregressive text-to-image models suffer from slow inference due to their sequential token-by-token decoding process, often requiring thousands of model forward passes to generate a single image. To address this inefficiency, we propose Speculative Jacobi-Denoising Decoding (SJD2), a framework that incorporates the denoising process into Jacobi iterations to enable parallel token generation in autoregressive models. Our method introduces a next-clean-token prediction paradigm that enables the pre-trained autoregressive models to accept noise-perturbed token embeddings and predict the next clean tokens through low-cost fine-tuning. This denoising paradigm guides the model towards more stable Jacobi trajectories. During inference, our method initializes token sequences with Gaussian noise and performs iterative next-clean-token-prediction in the embedding space. We employ a probabilistic criterion to verify and accept multiple tokens in parallel, and refine the unaccepted tokens for the next iteration with the denoising trajectory. Experiments show that our method can accelerate generation by reducing model forward passes while maintaining the visual quality of generated images.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

自回归文本到图像模型（如 Lumina-mGPT、Emu3）通过逐令牌顺序解码生成图像，生成一张高分辨率图像往往需要数千次模型前向传播，导致推理延迟巨大。现有加速方法（如雅可比解码）虽然可以并行解码，但其令牌精炼过程无约束、轨迹不稳定，导致收敛慢、加速比低。而扩散模型通过明确的去噪轨迹可以用很少的迭代生成高质量图像。本文希望将扩散模型的去噪过程引入雅可比解码，以稳定轨迹、加速自回归图像生成。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：提出 **推测性雅可比去噪解码（SJD2）**，将连续去噪过程融入雅可比迭代。通过 **下一干净令牌预测** 范式，使预训练自回归模型能够接受噪声扰动嵌入，并预测偏移一位的干净令牌，从而同时具备自回归预测与去噪能力。
- **关键技术细节**：
  - **噪声增强的微调**：在训练时，随机将输入令牌序列分段，对每段嵌入添加不同等级的连续高斯噪声（按扩散过程调度），并附加时间步编码。模型仍用交叉熵损失预测下一干净令牌。
  - **嵌入归一化**：对令牌嵌入进行均值和方差的归一化/反归一化，使噪声分布与预训练模型兼容。
  - **推理解码过程**：
    1. 用固定长度的滑动雅可比窗口初始化纯高斯噪声嵌入。
    2. 并行前向推理：所有位置同时输入模型，预测条件概率，采样下一干净令牌。
    3. 验证接受：使用概率准则（与推测解码类似）接受一个前缀的令牌。
    4. 精炼：未接受令牌分为两类——若仍是噪声嵌入，则按扩散公式做一步去噪（线性组合）；若已去噪变干净，则按标准雅可比精炼。
  - **去噪公式**：采用 Karras 调度器，定义递减时间步序列，对每个位置按 `e_tk-1 = (σ_tk-1/σ_tk)*e_tk + α_tk*(α_tk-1/α_tk - σ_tk-1/σ_tk)*ˆe0` 进行线性组合。
- **算法流程**（文字说明）：初始化窗口→并行前向→验证接受→对未接受令牌去噪/重采样→移除已接受令牌并补充新噪声令牌→重复直至生成完整图像。

## 3. 实验设计

- **数据集/场景**：使用 MSCOCO 2017 (5k) 和 MSCOCO 2014 (30k) 验证集，以及 GenEval 基准。图像数据约 8 万张高分辨率（≥720×720）互联网图像，缺失描述的用 Qwen2-VL 生成。
- **基准模型**：Lumina-mGPT 和 Emu3。
- **对比方法**：原始自回归解码、推测性雅可比解码（SJD）。此外在消融和对比中还涉及 Jacobi 解码、EAGLE、LANTERN、ZipAR 等（在附录中）。
- **评估指标**：FID、CLIP-Score、步骤压缩比（#生成令牌数 / #解码步数）、实际延迟（秒）、GPU 内存、GenEval 多维度得分（颜色、位置、计数等）。

## 4. 资源与算力

- 论文明确提及：每个模型使用 **8 张 GPU（80G 显存）** 进行微调。Lumina-mGPT 使用 8×A100，约 14 小时；Emu3 使用 8×H100，约 26 小时。全局 batch size 64，学习率 2e-5，AdamW 优化器，训练 6 个 epoch。推理时在单张 RTX 4090 或 A100 上测试延迟。

## 5. 实验数量与充分性

- **主要实验**：在 COCO 验证集上报告平均步骤数、步骤压缩比、FID、CLIP-Score（表1）；在 GenEval 上报告多维度指标（表2）；在 100 个 COCO 提示上测试实际延迟和 GPU 内存（表3）。
- **消融实验**：研究去噪迭代次数与雅可比窗口长度的权衡（图4）；验证嵌入归一化的必要性（图5）；对比纯去噪与去噪+雅可比的效果（图9）；比较与其他加速方法（表7、表8）。
- **额外对比**：在 Janus-Pro-1B 上验证（表5、表6）；分析 Flops（表4）；展示令牌轨迹稳定性（图8）。
- **总评**：实验数量较充分，涵盖主流基准、不同模型规模、多种度量，消融实验合理，对比方法较新。但未在更多模型（如视频生成）上验证，且所有实验基于自研微调模型，可能受数据分布影响。

## 6. 论文的主要结论与发现

- SJD2 能将模型前向传播步骤减少约 **4× (Lumina-mGPT) 至 5.6× (Emu3)**，实际延迟加速 **2× 以上**。
- 生成图像质量（FID、CLIP-Score、GenEval）与原始自回归解码相当，甚至略有提升。
- 引入去噪过程使令牌轨迹更稳定，减少振荡，加速收敛。
- 方法仅需低代价微调（6 个 epoch），无需额外模块，可移植到不同自回归模型。
- 与扩散模型相比，SJD2 可缩小自回归模型与扩散模型之间的速度差距（如 Janus-Pro-1B + SJD2 比 SDXL 更快）。

## 7. 优点

- **创新性**：首次将连续扩散去噪过程无缝融入离散自回归模型，提出“下一干净令牌预测”范式。
- **高效性**：仅需少量微调即可获得显著加速，且不增加模型参数量。
- **通用性**：适用于不同规模的自回归模型（Lumina-mGPT、Emu3、Janus-Pro-1B）。
- **稳定性**：去噪轨迹约束使令牌精炼过程更稳定，收敛更快。
- **实验扎实**：包含多维评估（质量、速度、显存），并与多种最新加速方法对比。

## 8. 不足与局限

- **实际延迟加速比例低于步骤压缩比**：由于 KV 缓存大小不同，部分模型（如 Lumina-mGPT）实际延迟加速（约 2.6×）低于步骤压缩（约 4×）。论文推测与 KV 缓存有关，但未深入解决。
- **额外开销**：并行解码带来更高的 FLOPs 和额外约 3GB 显存占用（因需存储去噪中间变量）。
- **训练数据限制**：微调使用互联网收集的 8 万张图像，可能引入数据偏差；且仅训练 6 个 epoch，泛化性待验证。
- **场景局限**：仅测试文本到图像生成，未扩展至视频或多模态生成。
- **公平性**：对比的加速方法（如 EAGLE、LANTERN）可能经过不同的优化，且论文未对所有方法做相同轮次的调参，略有偏差风险。
- **理论保证**：未提供严格的收敛性证明，实际效果依赖经验设定（如窗口长度、去噪步数）。

（完）
