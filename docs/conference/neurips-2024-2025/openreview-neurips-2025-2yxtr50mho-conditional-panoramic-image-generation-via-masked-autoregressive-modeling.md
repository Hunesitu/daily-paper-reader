---
title: Conditional Panoramic Image Generation via Masked Autoregressive Modeling
title_zh: 基于掩码自回归建模的条件全景图像生成
authors: "Chaoyang Wang, Xiangtai Li, Lu Qi, Xiaofan Lin, Jinbin Bai, Qianyu Zhou, Yunhai Tong"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=2YxtR50mho"
tags: ["query:ce"]
score: 7.0
evidence: 掩码自回归建模用于全景图像生成
tldr: 本文提出全景自回归模型PAR，利用掩码自回归建模统一处理文本条件生成和图像外推。克服了扩散模型在等距柱状投影中的i.i.d.假设违背问题。在多个全景生成任务上达到先进水平。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1294, \"height\": 768, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1382, \"height\": 513, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1438, \"height\": 901, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1377, \"height\": 330, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1445, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1378, \"height\": 223, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1375, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1374, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1375, \"height\": 240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 672, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 671, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 670, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 670, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1353, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1434, \"height\": 620, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 668, \"height\": 343, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 665, \"height\": 342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1370, \"height\": 825, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 667, \"height\": 344, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-2yxtr50mho/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 666, \"height\": 341, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1419, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 878, \"height\": 262, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 738, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 838, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 903, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 959, \"height\": 227, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1159, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 599, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 649, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 631, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-2yxtr50mho/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 808, \"height\": 185, \"label\": \"Table\"}]"
motivation: 扩散模型不适合全景图像的等距柱状投影，且现有方法将文本和图像条件生成分离。
method: 采用掩码自回归建模统一处理文本和图像条件，利用全景几何约束。
result: 在全景生成任务上超越扩散基线，质量更高且更一致。
conclusion: 自回归模型为全景图像生成提供了更自然的框架。
---

## Abstract
Recent progress in panoramic image generation has underscored two critical limitations in existing approaches. First, most methods are built upon diffusion models, which are inherently ill-suited for equirectangular projection (ERP) panoramas due to the violation of the identically and independently distributed (i.i.d.) Gaussian noise assumption caused by their spherical mapping. Second, these methods often treat text-conditioned generation (text-to-panorama) and image-conditioned generation (panorama outpainting) as separate tasks, relying on distinct architectures and task-specific data. In this work, we propose a unified framework, Panoramic AutoRegressive model (PAR), which leverages masked autoregressive modeling to address these challenges. PAR avoids the i.i.d. assumption constraint and integrates text and image conditioning into a cohesive architecture, enabling seamless generation across tasks. To address the inherent discontinuity in existing generative models, we introduce circular padding to enhance spatial coherence and propose a consistency alignment strategy to improve the generation quality. Extensive experiments demonstrate competitive performance in text-to-image generation and panorama outpainting tasks while showcasing promising scalability and generalization capabilities.

---

## 论文详细总结（自动生成）

# 论文结构化总结（中文）

## 1. 核心问题与整体含义（研究动机与背景）

- **全景图像生成** 在 VR/AR、自动驾驶、视觉导航等领域有重要应用，现有方法主要基于扩散模型。
- 但扩散模型使用 **i.i.d. 高斯噪声假设**，而等距柱状投影（ERP）会导致像素方差随纬度变化，从而 **违背 i.i.d. 假设**，使得扩散模型理论上不适合 ERP 全景图。
- 此外，现有方法将 **文本到全景图（Text-to-Panorama, T2P）** 和 **全景外推（Panorama Outpainting, PO）** 视为独立任务，使用不同的架构和数据，缺乏统一框架，且存在冗余计算（如双分支结构、迭代扭曲等）。
- 论文旨在解决以上两个问题，提出 **统一、高效、理论合理的条件全景生成范式**。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想
- 采用 **掩码自回归建模（Masked Autoregressive Modeling, MAR）** 替代扩散模型，避免 i.i.d. 假设约束。
- MAR 允许 **任意顺序生成**，从而自然统一文本条件和图像条件：全景外推可视为部分可见序列的文本到全景生成子任务。
- 提出专用设计来适应全景特性：**双空间循环填充** 和 **循环平移一致性损失**。

### 关键技术细节
#### （1）基础架构（Vanilla MAR）
- 使用 VAE 编码器将全景图压缩为连续 token（避免量化误差）。
- Transformer 编码器–解码器结构：编码器输入未掩码 token + 文本嵌入（经预训练文本编码器）；解码器接收掩码 token 并生成条件信号 z；轻量 MLP ϵθ 在条件 z 下对噪声图像进行去噪。
- 训练损失（仅掩码区域）：
  \[
  L_{va} = \mathbb{E}_{t,\epsilon} \left[ M \circ \| \epsilon_t - \epsilon_\theta(x_t | t, z) \|^2 \right]
  \]

#### （2）循环平移一致性（Cyclic Translation Consistency）
- 利用 ERP 全景图的水平循环平移等变性，构造语义等价的对（x, ϵ, M）和其平移版本（x', ϵ', M'），强制模型输出在平移后对齐。
- 损失：
  \[
  L_{\text{consistency}} = M' \circ \| T_v(\epsilon_\theta(x_t|t,x,M)) - \epsilon_\theta(x'_t|t,x',M') \|^2
  \]
- 总损失：\( L = L_{va} + \lambda L_{\text{consistency}} \)（λ=0.1）。

#### （3）双空间循环填充（Dual-space Circular Padding）
- **预填充（Pre-padding）**：在像素空间对 VAE 编码器输入进行左右循环 padding。
- **后填充（Post-padding）**：在潜在空间对 VAE 解码器输出进行循环 padding。
- 公式：\( C_r(x) = \text{concat}(x[..., -rW/2:], x, x[..., :rW/2]) \)。
- 确保边界像素获得双向上下文，避免语义断裂。

#### （4）推理过程
- 采用 MAR 逐步解码：根据掩码顺序，每次预测部分 token，迭代至全部生成。
- 支持 classifier-free guidance（CFG 系数=5）。

## 3. 实验设计

### 数据集
- **Matterport3D**：室内全景数据集，用于主要对比（训练/验证划分遵循 PanFusion）。
- **Structured3D**：合成室内数据集，用于额外验证。
- **SUN360**：用于零样本外推测试（OOD）。

### 指标
- FID（Fréchet Inception Distance）—— 基于 Inception 网络，衡量真实性与多样性。
- FAED（Fréchet Auto-Encoder Distance）—— 专为全景图定制的 FID 变体。
- CLIP Score —— 文本–图像对齐度。
- Discontinuity Score (DS) —— 全景图循环一致性。

### 对比方法
- 文本到全景：PanFusion（扩散，基于 SD）、Text2Light（AR）、PanoLlama（AR）。
- 全景外推：AOG-Net、2S-ODIS，以及 PanoDiff、Diffusion360、StitchDiffusion 等。
- 所有对比在 Matterport3D 上公平执行。

## 4. 资源与算力

- 训练设备：**8 × NVIDIA A100 GPU**。
- 训练时长：1.4B 参数模型约 **2 天**（20K 迭代，batch size 32）。
- 推理速度：PAR-0.3B 在单张 A100、batch size 8 下，64 个 AR 步约 **10.03 秒/图**，远快于 PanFusion（28.91 秒/图）。

## 5. 实验数量与充分性

- 实验覆盖 **三个主要任务**（T2P、PO、零样本图像编辑）。
- **模型规模消融**：0.3B、0.6B、1.4B 三个参数量，展示参数和计算量扩展对效果的提升。
- **消融实验**：循环一致性损失、循环填充（预/后填充比例）、CFG 系数、AR 步数、去噪步数等。
- **零样本泛化**：在 SUN360 上进行外推测试，与 Diffusion360 对比 DS 优势（0.63 vs. 1.12）。
- **额外数据集验证**：在 Structured3D 上对比 PanoLlama，FID/DS 显著领先。
- **可视化分析**：提供大量生成图、修复效果、失败案例等定性比较。
- 实验设计较为全面，对比方法选取主流且公平，消融验证了各组件有效性。

## 6. 主要结论与发现

- PAR 在 **FID、FAED、DS** 等指标上全面超越之前的扩散和 AR 方法，例如 PAR-0.3B 在 Matterport3D 上 FID=41.15，优于 PanFusion（45.21），且 DS 大幅降低（0.58 vs. 0.71）。
- **统一框架有效**：单个模型无需任务特定数据即可同时完成 T2P、PO、编辑。
- 循环平移一致性损失和双空间循环填充 **显著提升全景连续性**，消融显示缺乏任一组件会导致语义或像素级断裂。
- 模型具有 **良好的可扩展性**：增大参数和计算量持续改善质量。
- **零样本泛化能力强**：在未见过的数据集上仍能生成合理全景，且比其他方法更少伪影。

## 7. 优点

- **理论创新**：指出现有扩散模型在 ERP 上的根本性缺陷，并提出 MAR 这一更合适的范式。
- **统一架构**：首次通过 MAR 将文本和图像条件生成融为一体，简化流程。
- **专用设计**：循环填充和一致性损失针对全景特性，简单有效。
- **实验严谨**：多数据集、多规模、多任务消融，可视化丰富，对比公平。
- **效率优势**：推理速度远快于扩散基线，且计算主要在 transformer 和 MLP 上，padding 开销极小（<2%）。

## 8. 不足与局限

- **细节质量仍有差距**：生成的小物体（如桌子、沙发）可能模糊，与大模型和真实图相比仍有提升空间。
- **数据稀缺**：全景训练数据有限，论文指出缩放至更大真实数据集可望改善，但暂未实现。
- **训练成本高**：1.4B 模型需 8×A100 训练 2 天，资源消耗较大。
- **CLIP 分数未显著优势**：略低于部分基线，作者解释为 CLIP 预训练于透视图像，与全景几何不匹配。
- **零样本编辑任务仅展示定性结果**，未进行定量评估（如 CLIP score 或用户调研），说服力有限。
- **缺乏语义多样性分析**：未讨论模型是否容易生成重复结构或模式。

（完）
