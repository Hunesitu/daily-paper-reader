---
title: "BitMark: Watermarking Bitwise Autoregressive Image Generative Models"
title_zh: BitMark：比特级自回归图像生成模型的水印技术
authors: "Louis Kerner, Michel Meintz, Bihe Zhao, Franziska Boenisch, Adam Dziedzic"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=VSir0FzFnP"
tags: ["query:ce"]
score: 8.0
evidence: 针对比特级自回归文本到图像模型的水印方法
tldr: 本文提出BitMark，一种针对比特级自回归文本到图像模型的水印方法。该技术将人眼不可见但可检测的信号嵌入生成图像中，以缓解模型因重复使用自生成数据导致的性能退化问题。实验表明水印在保持图像质量的同时有效标记模型输出。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 676, \"height\": 508, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 789, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 819, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 726, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1436, \"height\": 1927, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1436, \"height\": 1639, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1423, \"height\": 1204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1439, \"height\": 1181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1428, \"height\": 1897, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vsir0fzfnp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1442, \"height\": 1161, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 671, \"height\": 324, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1443, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1460, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 661, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 936, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1448, \"height\": 156, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1404, \"height\": 2022, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1436, \"height\": 680, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 662, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1118, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1382, \"height\": 287, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1447, \"height\": 366, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 843, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1477, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1476, \"height\": 179, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1116, \"height\": 138, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 826, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 913, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 736, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 855, \"height\": 182, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1450, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vsir0fzfnp/table-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 651, \"height\": 300, \"label\": \"Table\"}]"
motivation: 自回归文本到图像模型的输出易被重新用作训练数据，导致模型崩溃，需要水印溯源。
method: 提出比特级水印注入方法，在自回归生成过程中嵌入隐蔽信号。
result: 水印可检测且不影响图像质量，有效防止模型崩溃。
conclusion: 水印是保护自回归图像生成模型免于数据污染的有效手段。
---

## Abstract
State-of-the-art text-to-image models generate photorealistic images at an unprecedented speed. This work focuses on models that operate in a bitwise autoregressive manner over a discrete set of tokens that is practically infinite in size. However, their impressive generative power comes with a growing risk: as their outputs increasingly populate the Internet, they are likely to be scraped and reused as training data—potentially by the very same models. This phenomenon has been shown to lead to model collapse, where repeated training on generated content, especially from the models’ own previous versions, causes a gradual degradation in performance. A promising mitigation strategy is watermarking, which embeds human-imperceptible yet detectable signals into generated images—enabling the identification of generated content. In this work, we introduce BitMark, a robust bitwise watermarking framework. Our method embeds a watermark directly at the bit level of the token stream during the image generation process. Our bitwise watermark subtly influences the bits to preserve visual fidelity and generation speed while remaining robust against a spectrum of removal techniques. Furthermore, it exhibits high radioactivity, i.e., when watermarked generated images are used to train another image generative model, this second model’s outputs will also carry the watermark. The radioactive traces remain detectable even when only fine-tuning diffusion or image autoregressive models on images watermarked with our BitMark. Overall, our approach provides a principled step toward preventing model collapse in image generative models by enabling reliable detection of generated outputs. The code is available at https://github.com/sprintml/BitMark.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）
- 当前最先进的文本到图像模型（如 Infinity、Instella）采用**比特级自回归**方式生成图像，其输出质量高、速度快。
- 这些模型生成的图像大量涌入互联网，很可能被**重新抓取并用作训练数据**，导致**模型崩溃**（model collapse）——即反复在自生成数据（尤其是来自同一模型先前版本）上训练会逐步降低性能。
- **水印技术**是一种有前景的缓解策略：在生成图像中嵌入人眼不可见但可检测的信号，从而识别自生成内容，防止其被再次用于训练。
- BitMark 是**首个针对比特级自回归图像生成模型**的水印方法，旨在高效鲁棒地标记模型输出，防止模型崩溃。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：在图像生成过程中，直接在**比特流层面**注入水印，通过偏向比特序列的统计分布实现检测。
- **关键技术**：
  - 将所有可能的长度为 \(n\) 的比特序列划分为**绿列表** \(G\) 和**红列表** \(R\)（文中主要使用 \(n=2\)，\(G=\{01,10\}\)）。
  - **嵌入**：生成每个比特时，若该比特能补全一个绿列表序列，则在其 logit 上添加一个小的偏置 \(\delta\)；否则不变。这使生成图像中绿序列的比例显著高于自然图像的 50%。
  - **检测**：对图像进行编码（使用模型的编码器），统计所有比特序列中属于绿列表的数量 \(C\)。使用 **z 检验**：\(z = (C - \gamma T) / \sqrt{T \gamma (1-\gamma)}\)，其中 \(\gamma = |G|/2^n\)，\(T\) 为受水印影响的比特序列总数。若 z 超过阈值则判定为水印图像。
- **比特级优于令牌级**的动机：作者发现，图像经过编码-解码后，比特层面的重叠率（77.43%）远高于令牌层面（2.38%），说明比特级水印更鲁棒。
- **算法**：Algorithm 1 为嵌入（多尺度模型如 Infinity），Algorithm 2 为检测；单尺度模型（如 Instella）有对应的 Algorithm 3、4。

## 3. 实验设计
- **数据集**：主要使用 **MS-COCO 2014 验证集**（默认 10,000 张图像）；部分实验使用 ImageNet-1k、LAION POP 等。
- **场景与指标**：
  - **图像质量**：FID、KID、CLIP Score。
  - **鲁棒性**：常规攻击（高斯噪声、模糊、色彩抖动、随机裁剪、旋转、JPEG 压缩、水平/垂直翻转）；重建攻击（SD2.1-VAE 编码解码、CtrlRegen+）；水印在沙攻击（Watermarks in the Sand）；自适应 Bit-Flipper 攻击。
  - **放射性**：用 BitMark 水印图像微调下游模型（同一架构 Infinity-2B 或跨架构 Stable Diffusion 2.1），检测其输出。
- **对比基准**：三种后处理水印方法——RivaGAN、StegaStamp、TrustMark。
- **模型**：Infinity-2B（默认）、Infinity-8B、Instella IAR；扩展至扩散模型 BiGR。

## 4. 资源与算力
- 论文提及的实验环境：**Ubuntu 22.04，Intel Xeon Gold 6330 CPU，NVIDIA A40 GPU（40 GB 显存）**。
- 未明确说明 GPU 数量、训练总时长等具体算力消耗。仅提到：Watermarks in the Sand 攻击每个图像需要超过 12 分钟（200 次迭代，每次 100 个候选）。
- 水印生成速度：增加约 0.26 秒/图像（2.58 秒 vs 无水印 2.32 秒）；检测时间小于 0.5 秒/图像。

## 5. 实验数量与充分性
- **数量**：实验涵盖质量评估（表 1）、多种鲁棒性测试（表 2、3、4、5、6）、消融研究（附录 D、F、G 等），共 **22 个表格**和 **10 个图**。
- **充分性**：对比了三种主流后处理水印，覆盖了常规攻击、重建攻击、强针对性攻击（Watermarks in the Sand、Bit-Flipper），并验证了放射性（同一模型和跨模型）。
- **公平性**：在相同数据集和攻击条件下比较，指标标准（TPR@1%FPR、AUC 等）。消融实验详尽（δ 值、绿列表选择、尺度等）。总体充分、客观。
- **轻微不足**：对于大旋转角度（±50°）鲁棒性较弱（仅 56.8% TPR），但作者讨论了旋转校正后的改进（98.3%）。

## 6. 主要结论与发现
- BitMark 能在**几乎不损失图像质量和生成速度**的前提下嵌入鲁棒水印。
- 对大多数常规攻击和重建攻击**鲁棒性显著优于现有后处理水印**；对 Watermarks in the Sand 和 Bit-Flipper 攻击也保持较高检测率（89% 和 47.2%）。
- 具有**强放射性**：用 BitMark 水印图像微调的下游模型（同一架构或不同架构）的输出中仍可检测到水印，TPR@1%FPR 接近 100%。
- **仅需 5% 水印数据**即可产生统计显著的分布偏移（p=5.6e-62），有助于防止模型崩溃。

## 7. 优点
- **首创性**：第一个针对比特级自回归图像模型的水印方法，填补了空白。
- **比特级设计**：利用比特级在编码-解码后更高的稳定性，优于令牌级水印。
- **鲁棒性全面**：在广泛攻击下保持高检测率，包括针对性的强攻击。
- **放射性**：有效防止模型崩溃，因为水印可跨模型世代传播。
- **高效**：嵌入和检测开销极小（<0.5 秒检测），易于部署。
- **可解释性**：使用统计检验（z 检验）提供置信度。

## 8. 不足与局限
- **旋转敏感性**：当旋转角度超过 ±30° 时检测率下降显著（±50° 时仅 56.8% TPR），需要预旋转校正。
- **δ 调节**：偏置 \(\delta\) 需要手动调节，\(\delta>3\) 会明显降低图像质量（FID 从 29.61 跳到 127.44），限制了最大水印强度。
- **极端规模 FPR 风险**：TPR@1%FPR 在万亿级样本下可能导致大量假阳性，影响训练数据质量。
- **Infinity-8B 敏感性**：大型模型对 δ 更敏感，导致在相同 δ 下鲁棒性低于 2B 版本。
- **Instella 容量限制**：该模型仅 128 个 token（4096 比特），部分攻击下鲁棒性不足。
- **环境依赖**：实验仅在特定硬件和软件环境下进行，未说明多卡训练成本。

（完）
