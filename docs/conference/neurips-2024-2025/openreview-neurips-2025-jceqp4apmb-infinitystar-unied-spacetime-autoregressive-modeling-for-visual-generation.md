---
title: "InfinityStar: Uniﬁed Spacetime AutoRegressive Modeling for Visual Generation"
title_zh: InfinityStar：统一的时空自回归建模用于视觉生成
authors: "Jinlai Liu, Jian Han, Bin Yan, Wuhui, Fengda Zhu, Xing Wang, Yi Jiang, BINGYUE PENG, Zehuan Yuan"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=JcEqp4aPmb"
tags: ["query:ce"]
score: 8.0
evidence: 统一时空自回归建模用于视觉生成
tldr: 本文提出InfinityStar，一个统一的时空自回归框架，支持文本到图像、文本到视频等多种生成任务。该框架在单个架构中联合捕获空间和时间依赖，在VBench上取得83.74分，优于所有自回归模型及部分扩散模型。展示了自回归模型在视觉生成中的强大潜力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-jceqp4apmb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1411, \"height\": 870, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jceqp4apmb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1284, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jceqp4apmb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1431, \"height\": 1108, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jceqp4apmb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1260, \"height\": 396, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jceqp4apmb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1320, \"height\": 650, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jceqp4apmb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1301, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-jceqp4apmb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1295, \"height\": 555, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-jceqp4apmb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1304, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jceqp4apmb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1369, \"height\": 1069, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jceqp4apmb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jceqp4apmb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1247, \"height\": 577, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-jceqp4apmb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1414, \"height\": 243, \"label\": \"Table\"}]"
motivation: 现有自回归模型通常针对单一任务设计，缺乏统一处理图像和视频生成的能力。
method: 提出统一时空自回归框架，在离散空间中联合建模空间和时间依赖性。
result: 在多个基准上超越其他自回归模型和部分扩散模型，生成高质量图像和视频。
conclusion: 统一自回归框架为视觉生成提供了高效且通用的解决方案。
---

## Abstract
We introduce InfinityStar, a unified spacetime autoregressive framework for high-resolution image and dynamic video synthesis. Building on the recent success of autoregressive modeling in both vision and language, our purely discrete approach jointly captures spatial and temporal dependencies within a single architecture. This unified design naturally supports a variety of generation tasks such as text-to-image, text-to-video, image-to-video, and long-duration video synthesis via straightforward temporal autoregression. Through extensive experiments, InfinityStar scores 83.74 on VBench, outperforming all autoregressive models by large margins, even surpassing diffusion competitors like HunyuanVideo. Without extra optimizations, our model generates a 5s, 720p video approximately 10$\times$ faster than leading diffusion-based methods. To our knowledge, InfinityStar is the first discrete autoregressive video generator capable of producing industrial-level 720p videos. We release all code and models to foster further research in efficient, high-quality video generation.

---

## 论文详细总结（自动生成）

# InfinityStar: 统一的时空自回归建模用于视觉生成 —— 论文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **现有方法的局限**：
  - **扩散模型**（如 SORA、HunyuanVideo）：通过迭代去噪生成高质量视频，但推理步骤多（数十至数百步），计算成本高，难以平滑扩展到更长视频或外推任务。
  - **自回归模型**（如 Emu3、Nova）：采用逐 token/逐尺度预测，天然支持流式生成，但视觉保真度不足，且因推理步骤过多（数万步）导致延迟高。
- **动机**：需要一种同时具备**高视觉质量、高效率和时序泛化能力**的统一生成框架，能够无缝支持文本到图像、文本到视频、图像到视频、长视频外推等任务。
- **整体含义**：InfinityStar 首次在**纯离散自回归架构**中联合捕获空间和时间依赖性，实现了工业级 720p 视频生成，性能匹敌甚至超越领先的扩散模型，同时大幅提升推理速度。

## 2. 方法论：核心思想、关键技术细节
### 核心思想：时空金字塔建模（Spacetime Pyramid Modeling）
- 将视频分解为**图像金字塔（Image Pyramid）**和**多个片段金字塔（Clip Pyramid）**：
  - 第一帧作为图像金字塔（静态外观），后续每个片段（clip）的时空维度建模为 3D 体积金字塔：仅扩展空间尺度（h, w），时间维度保持固定。
  - 生成时先逐尺度预测图像金字塔，再逐片段逐尺度预测 clip 金字塔，从而实现**外观与运动解耦**。
- 自回归似然公式（以 clip c、尺度 k 排序）：
  \[
  p(\mathbf{r}_1^1,\dots,\mathbf{r}_N^K) = \prod_{c=1}^{N}\prod_{k=1}^{K} p(\mathbf{r}_c^k \mid \mathbf{r}_{\le c}^{<k}, \psi(t))
  \]
  其中 \(\psi(t)\) 为文本嵌入。

### 关键技术细节
1. **视觉分词器（Visual Tokenizer）**：
   - **知识继承**：从预训练的连续视频 VAE（Wan 2.1 VAE）继承架构和权重，插入无参数的 Bitwise Spherical Quantizer（BSQ），避免从零训练，加速收敛。
   - **随机量化器深度（Stochastic Quantizer Depth, SQD）**：训练时以概率 p 丢弃最后 N 个尺度的量化，迫使早期尺度承载更多信息，缓解信息分布不均。
2. **时空自回归 Transformer**：
   - **语义尺度重复（Semantic Scale Repetition, SSR）**：重复前 Ks 个语义尺度 N 次，加强早期尺度预测，改善结构稳定性和运动质量，额外计算开销可忽略。
   - **时空稀疏注意力（Spacetime Sparse Attention, SSA）**：仅在片段内进行粗粒度因果掩码，并只关注前一片段的最后尺度，大幅降低计算量，同时避免偏差累积。
3. **训练策略**：四阶段渐进式训练（T2I 预训练 → T2V 192p → 480p → 720p），分辨率提升时保留低分辨率尺度并添加新尺度。

## 3. 实验设计
### 数据集
- **文本-图像数据**：130M 预训练 + 70M 高质量 + 5M 合成（调整分布和美学）。
- **文本-视频数据**：约 16M 视频（时长>5秒），其中 13M 为 192p（来自 Panda-70M、Mira 等），3M 为 480p，50K 为 720p 高质量视频（用于微调）。

### 基准与评估
- **图像生成**：GenEval（物体级对齐）、DPG（整体分数）。
- **视频生成**：VBench（16 维度，含质量、语义、整体分）。
- **零样本任务**：图像到视频、视频外推（无额外微调）。

### 对比方法
- **扩散模型**：HunyuanVideo（13B）、Wan 2.1（14B）、CogVideoX（5B）、OpenSora V1.2、Gen-3 等。
- **自回归模型**：Nova（0.6B）、Emu3（8B）、Infinity（2B）等。

## 4. 资源与算力
- 训练环境：内部 GPU 集群（未指明具体型号和数量）。
- 各阶段 GPU 小时估算（来自论文）：
  - 四阶段视频生成训练：5,000 + 40,000 + 30,000 + 30,000 = **105,000 GPU 小时**。
  - 视频 VAE 训练：**2,000 GPU 小时**。
  - 消融实验：**10,000 GPU 小时**。
  - 评估：**1,000 GPU 小时**。
- 总消耗（含初步实验）：约 **118,000+ GPU 小时**。

## 5. 实验数量与充分性
- **实验组数**：涵盖文本到图像（2 个基准）、文本到视频（1 个综合基准）、零样本任务、消融实验（5 组核心组件：tokenizer 预训练、SQD、SSR、SSA、时空金字塔设计）、推理延迟对比（3 种分辨率/长度）。
- **公平性**：
  - 所有对比均采用公开基准（VBench 为官方评测，避免自定义偏差）。
  - 消融实验在受控设置下（1M 192p 数据，固定 batch 和迭代）进行，确保可归因。
  - 推理延迟采用相同单 GPU 环境，使用各自默认配置。
- **结论**：实验设计较系统，消融覆盖了所有关键创新，定量结果充分支持论文主张。

## 6. 主要结论与发现
- **性能**：
  - VBench 总分 **83.74**，超越所有自回归模型（Nova 80.12，Emu3 80.96），并超过大部分扩散模型（HunyuanVideo 83.24，仅低于 Wan 2.1 84.70）。
  - GenEval 总分 **0.79**（Infinity 0.73），DPG **86.55**（Infinity 83.46）。
- **速度**：生成 5s 720p 视频仅需 58 秒（Wan 2.1 需 1864 秒），**速度提升 32 倍**；相比 Nova（480p）提升 6 倍。
- **零样本能力**：无需微调即可完成图像到视频、视频外推，且保持时序连贯。
- **首次**：离散自回归模型实现工业级 720p 视频生成。

## 7. 优点
- **统一框架**：单一架构支持 T2I、T2V、I2V、长视频外推，无需任务特定修改。
- **高效率**：推理步数极少（仅为尺度数 × 重复次数），在同等压缩率下比扩散模型快 10 倍以上。
- **技术改进**：
  - 知识继承避免了视频 tokenizer 的昂贵从头训练。
  - SQD 和 SSR 解决了多尺度信息不均和早期语义生成问题。
  - SSA 在保持质量的同时显著降低计算量。
- **开源贡献**：代码和模型全部开源，便于社区复现和拓展。

## 8. 不足与局限
- **质量-运动权衡**：在高运动场景中，有时会牺牲细粒度视觉细节以换取运动保真度。
- **算力限制**：模型规模和训练数据未达到领先扩散模型的水平（如 14B 参数的 Wan 2.1），可能限制性能上限。
- **推理优化**：推理管道尚未充分优化（如未使用 KV-cache、并行解码等），仍有提速空间。
- **实验覆盖**：缺乏对长视频生成（>10s）的定量评估；零样本 I2V 仅在附录展示部分样本，未提供量化指标。
- **潜在风险**：论文提到已过滤有害和版权数据，但未详细讨论公平性和滥用风险（如深度伪造），应在最终版本中加强。

（完）
