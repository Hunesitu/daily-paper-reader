---
title: "Kaleido Diffusion: Improving Conditional Diffusion Models with Autoregressive Latent Modeling"
title_zh: Kaleido扩散：用自回归潜在建模改进条件扩散模型
authors: "Jiatao Gu, Ying Shen, Shuangfei Zhai, Yizhe Zhang, Navdeep Jaitly, Joshua M. Susskind"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=qZSwlcLMCS"
tags: ["query:ce"]
score: 7.0
evidence: 通过自回归潜在先验改进扩散模型
tldr: 扩散模型在条件生成中样本多样性有限，尤其是高引导权重时。本文提出Kaleido，引入自回归语言模型生成潜在变量作为先验，指导扩散过程。这些潜在变量作为抽象的中间表示，能够编码不同下游任务的信息。实验表明，该方法显著提升了生成图像的多样性，同时保持高质量，是扩散模型与自回归模型结合的有效尝试。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 591, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 606, \"height\": 139, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1441, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 490, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1443, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 819, \"height\": 354, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1444, \"height\": 1360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1423, \"height\": 1741, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1431, \"height\": 1169, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1295, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1286, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1250, \"height\": 752, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1262, \"height\": 203, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1448, \"height\": 1038, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1370, \"height\": 2241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1371, \"height\": 2247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1393, \"height\": 2142, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1396, \"height\": 2158, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-qzswlclmcs/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1440, \"height\": 1562, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-qzswlclmcs/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 214, \"label\": \"Table\"}]"
motivation: 扩散模型在条件生成中多样性不足，尤其是高分类器自由引导权重下。
method: 集成自回归语言模型编码原文本并生成潜在变量，作为扩散过程的抽象先验。
result: 在多个文本到图像数据集上，该方法提高了生成图像的多样性，同时保持了质量。
conclusion: 自回归潜在先验能有效提升扩散模型的生成多样性。
---

## Abstract
Diffusion models have emerged as a powerful tool for generating high-quality images from textual descriptions. Despite their successes, these models often exhibit limited diversity in the sampled images, particularly when sampling with a high classifier-free guidance weight. To address this issue, we present Kaleido, a novel approach that enhances the diversity of samples by incorporating autoregressive latent priors. Kaleido integrates an autoregressive language model that encodes the original caption and generates latent variables, serving as abstract and intermediary representations for guiding and facilitating the image generation process.
In this paper, we explore a variety of discrete latent representations, including textual descriptions, detection bounding boxes, object blobs, and visual tokens. These representations diversify and enrich the input conditions to the diffusion models, enabling more diverse outputs.
Our experimental results demonstrate that Kaleido effectively broadens the diversity of the generated image samples from a given textual description while maintaining high image quality. Furthermore, we show that Kaleido adheres closely to the guidance provided by the generated latent variables, demonstrating its capability to effectively control and direct the image generation process.

---

## 论文详细总结（自动生成）

# Kaleido Diffusion 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：条件扩散模型（如文本到图像生成）在使用高分类器自由引导（CFG）权重时，生成的图像多样性严重不足。尽管 CFG 能提升图像质量和对文本的对齐性，但会锐化条件分布，导致“模式坍塌”——即使使用不同噪声种子，同一文本提示也会生成外观极为相似的图像。
- **背景**：扩散模型在图像生成领域已取得巨大成功，但高 CFG 下的多样性损失限制了其在需要多样化创意输出的场景（如艺术创作、用户偏好适应）中的应用。现有方法（如 CADS）通过退火条件信号来提升多样性，但往往以牺牲图像质量为代价。
- **研究目标**：提出一种通用框架，在不降低质量的前提下，有效提升扩散模型在任意 CFG 权重下的生成多样性。

## 2. 方法论：核心思想、关键技术细节

### 2.1 核心思想
- **引入自回归潜在先验**：将图像生成过程分解为两个步骤：（1）先通过自回归模型从原始条件（如文本）预测一组离散的潜在变量（latent tokens），这些潜在变量捕捉图像中的抽象“模式”（如物体描述、空间布局、风格等）；（2）再将原始条件和这些潜在变量共同输入扩散模型，生成最终图像。
- **理论依据**：CFG 会同时锐化模式选择分布 \(p(z|c)\) 和图像变化分布 \(p(x|z,c)\)。通过显式建模模式选择（自回归生成 z），可以在应用 CFG 之前采样 z，从而避免模式分布被扭曲，保留多样性。

### 2.2 关键技术细节

#### 潜在变量类型（四种）
| 潜在类型 | 描述 | 提取方法 |
|---------|------|---------|
| 文本描述（text） | 详细描述图像内容的文本，补全原始标注的不足 | 使用 Qwen-VL-Chat 生成 |
| 检测边界框（bbox） | 物体的坐标位置（归一化，带标注） | Qwen-VL 生成带定位的标题 |
| 物体斑点（blob） | 倾斜椭圆，表示物体的位置、大小和朝向 | 基于边界框，用 SAM 分割后拟合椭圆 |
| 视觉令牌（voken） | 通过 VQ-VAE 编码得到的离散视觉 token 序列 | 使用 SEED tokenizer |

#### 联合训练框架
- **整体目标**：最大化证据下界（ELBO），包含两项损失：
  - \(L_{AR}\)：自回归模型预测潜在变量的负对数似然（交叉熵）
  - \(L_{DM}\)：扩散模型的去噪损失（MSE）
- **损失平衡**：\(L = L_{DM} + \eta \cdot L_{AR}\)，其中 \(\eta\) 为超参数。
- **训练流程**：
  1. **固定推理**：对每个训练图像，使用预训练 MLLM 生成多种潜在变量（text/bbox/blob/voken），并存储。
  2. **联合优化**：冻结文本编码器（T5-XL），同时训练自回归解码器（初始化为 T5-XL 解码器）和去噪 UNet。自回归解码器的最终隐藏状态与文本编码输出拼接后作为扩散模型的额外条件。
- **推理流程**：
  1. 自回归模型根据原始文本生成潜在变量序列。
  2. 扩散模型在原始文本和潜在变量共同指导下生成图像。
  3. 用户可手动编辑潜在变量（如修改文本描述、调整边界框），再重新生成图像，实现细粒度控制。

## 3. 实验设计

### 3.1 数据集与场景
| 任务 | 数据集 | 分辨率 | 条件类型 |
|------|--------|--------|----------|
| 类别条件图像生成 | ImageNet（256×256） | 256×256 | 类别标签 |
| 文本到图像生成 | CC12M（256×256） | 256×256 | 原始 alt-text |

### 3.2 Benchmark 与对比方法
- **基准模型**：Matryoshka Diffusion Models (MDM)（像素空间扩散，T5-XL 编码器 + NestedUNet）。
- **对比方法**：
  - MDM（基线）
  - MDM + CADS（条件退火采样，一种提升多样性的采样策略）
  - Ours（Kaleido）
  - Ours + CADS

### 3.3 评估指标
| 指标 | 测量内容 | 说明 |
|------|----------|------|
| FID-50K | 整体质量+多样性 | 50K 样本 vs 训练集 |
| Precision | 图像质量 | 高精度可能掩盖多样性不足问题 |
| Recall | 多样性 | 直接衡量覆盖率 |
| MSS (SSCD) | 多样性 | 平均相似度，越低越多样 |
| Vendi (SSCD / DiNOv2) | 多样性 | 分数越高越多样 |

## 4. 资源与算力

- **GPU 型号与数量**：64 块 A100 GPU。
- **训练时长**：约 2 周（400K 步训练）。
- **显存限制**：由于并入了 T5 解码器，每 GPU 仅能容纳 4~8 张图像，训练速度约为原始 MDM 的 1/3。
- **参数量**：去噪 UNet 约 500M，自回归解码器为 T5-XL 解码器（~1.5B），总参数量较大。

## 5. 实验数量与充分性

### 5.1 主要实验组
1. **定量对比**：在 ImageNet 上，对 MDM、MDM+CADS、Ours、Ours+CADS 进行 FID、Precision、Recall、MSS、Vendi 评估，共 4 组 × 6 指标。
2. **引导权重分析**：在 ImageNet 上，对不同 CFG 权重（1~25）下的 FID 和 Recall 进行对比。
3. **多种潜在变量验证**：在 CC12M 上训练了 5 种模型：text、bbox、blob、voken、combined（text+bbox+voken），并展示定性结果。
4. **消融实验**：潜在编辑能力（修改文本/边界框后重新生成）。
5. **额外实验**：颜色簇作为潜在变量（无需外部知识），展示多样性提升。

### 5.2 充分性与公平性
- **充分性**：涵盖主要评估维度（质量+多样性），多种潜在类型对比，并兼容现有方法（CADS）。
- **公平性**：基线模型与 Kaleido 使用相同架构、超参数、训练步数（400K），但 Kaleido 需额外训练 T5 解码器，且推理步骤多一步（自回归生成潜在变量）。未提供多次运行的标准差，仅单次运行结果。CADS 作为采样策略对比，但 CADS 无需重新训练，对比不完全对等。

## 6. 主要结论与发现

1. **多样性显著提升**：在 ImageNet 上，Kaleido (combined) 的 Recall 从 0.22（MDM）提升至 0.42，MSS 从 0.21 降至 0.16，Vendi (DiNOv2) 从 3.04 升至 3.79。在 CFG=4 时，Kaleido 的 FID 为 9.0（MDM 为 15.5）。
2. **质量保持**：Kaleido 的 Precision 保持较高（0.85 vs MDM 0.93），同时质量未下降（FID 更优）。
3. **与 CADS 互补**：Ours + CADS 取得最佳 FID（5.9）和最高多样性（Vendi DiNOv2 4.83）。
4. **潜在变量的控制力**：生成的潜在 token 可有效引导图像细节（物体外观、位置、风格），用户编辑潜在变量后图像能够忠实反映修改。
5. **高 CFG 下稳定性**：Kaleido 在各种 CFG 下 FID 和 Recall 曲线更平坦，而基线模型随 CFG 增加性能急剧下降。

## 7. 优点

- **方法创新性**：巧妙地将自回归模型与扩散模型结合，通过显式模式选择解决高 CFG 下的多样性问题，理论分析清晰（温度调整视角）。
- **潜在变量多样且可解释**：支持文本、边界框、斑点、视觉令牌等多种形式，且均为人类可解读，提供生成过程的透明性。
- **细粒度控制**：用户可通过修改潜在 token 实现局部编辑（如改变背景、移动物体位置），无需重新训练模型。
- **与现有技术兼容**：可叠加 CADS 等采样策略进一步提升性能。
- **实验全面**：涵盖定量、定性、引导权重分析、潜在编辑演示，并在两种任务（类别/文本条件）上验证。

## 8. 不足与局限

- **训练复杂度高**：需要额外训练自回归解码器，且受限于 T5 解码器显存占用，训练速度慢（约 3 倍于基线），对计算资源要求高。
- **潜在变量提取依赖外部模型**：需要 Qwen-VL、SAM、SEED 等预训练模型预处理数据集，增加了数据准备复杂度；且外部模型的质量可能影响下游性能。
- **寻找最优潜在变量的困难**：探索了多种潜在类型，但未给出系统性的选择指导；不同类型可能对特定任务效果不一，需要经验性调参。
- **实验局限性**：
  - 仅在 ImageNet 和 CC12M 上验证，未在更大规模数据集（如 LAION-5B）或更高分辨率（如 512×512）上测试。
  - 未提供多次运行的标准差，结果稳健性未知。
  - CADS 对比中，MDM+CADS 在定量多样性指标上优于 Kaleido，但定性图像多样性却不如（如猫的品种），说明现有多样性指标可能不完善。
- **应用风险**：未讨论潜在变量的错误生成（如不合理的边界框）对图像质量的影响；可控编辑的精度和鲁棒性未量化评估。
- **社会影响**：虽然文章提到正面社会影响（多样性促进公平性），但未讨论深度伪造、偏见放大等潜在负面风险。

（完）
