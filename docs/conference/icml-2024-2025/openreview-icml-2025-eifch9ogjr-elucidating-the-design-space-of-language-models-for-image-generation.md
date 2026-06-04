---
title: Elucidating the design space of language models for image generation
title_zh: 阐明用于图像生成的语言模型设计空间
authors: "Xuantong LIU, Shaozhe Hao, Xianbiao Qi, Tianyang Hu, Jun Wang, Rong Xiao, Yuan Yao"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=EIfCH9OgjR"
tags: ["query:ce"]
score: 7.0
evidence: 语言模型用于图像生成，自回归设计空间
tldr: 本文系统研究了将大语言模型（LLM）应用于图像生成的设计空间，包括分词方法、扫描模式、词汇表等。发现无需领域特定设计，仅通过合理选择上述因素，LLM即可在图像生成上达到接近最先进的性能，并分析了自回归模型的学习和缩放行为，为构建高性能自回归图像生成器提供了指导。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1701, \"height\": 1059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 866, \"height\": 319, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 882, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 862, \"height\": 682, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 764, \"height\": 381, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 856, \"height\": 264, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1682, \"height\": 1266, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1700, \"height\": 1996, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1592, \"height\": 2110, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1264, \"height\": 1550, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1776, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1777, \"height\": 762, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1728, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1723, \"height\": 394, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1662, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 898, \"height\": 583, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1599, \"height\": 855, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1600, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1598, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1223, \"height\": 481, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1734, \"height\": 664, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1557, \"height\": 2271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-eifch9ogjr/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1557, \"height\": 2269, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 841, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 658, \"height\": 136, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 851, \"height\": 1088, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 830, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1304, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1416, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 768, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1694, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1704, \"height\": 209, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 638, \"height\": 191, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1019, \"height\": 400, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1304, \"height\": 801, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1367, \"height\": 140, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1143, \"height\": 326, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-eifch9ogjr/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1341, \"height\": 554, \"label\": \"Table\"}]"
motivation: 系统探索LLM在图像生成中的设计选择，避免领域特定偏见。
method: 研究分词、建模、扫描、词汇和采样策略对LLM图像生成性能的影响。
result: LLM在图像生成上取得接近SOTA的结果，无需特殊设计。
conclusion: 合理的设计选择使LLM能够作为通用的图像生成架构。
---

## Abstract
The success of large language models (LLMs) in text generation has inspired their application to image generation. However, existing methods either rely on specialized designs with inductive biases or adopt LLMs without fully exploring their potential in vision tasks. In this work, we systematically investigate the design space of LLMs for image generation and demonstrate that LLMs can achieve near state-of-the-art performance without domain-specific designs, simply by making proper choices in tokenization methods, modeling approaches, scan patterns, vocabulary design, and sampling strategies. We further analyze autoregressive models' learning and scaling behavior, revealing how larger models effectively capture more useful information than the smaller ones. Additionally, we explore the inherent differences between text and image modalities, highlighting the potential of LLMs across domains. The exploration provides valuable insights to inspire more effective designs when applying LLMs to other domains. With extensive experiments, our proposed model, **ELM** achieves an FID of 1.54 on 256$\times$256 ImageNet and an FID of 3.29 on 512$\times$512 ImageNet, demonstrating the powerful generative potential of LLMs in vision tasks.

---

## 论文详细总结（自动生成）

# 论文《Elucidating the design space of language models for image generation》详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：大语言模型（LLM）在文本生成上取得了巨大成功，但将其直接应用于图像生成时，现有方法要么引入大量领域特定的归纳偏置（如低分辨率到高分辨率的扫描策略、扩散损失、随机置换等），要么简单地使用 LLM 而缺乏对其在视觉任务中潜力的系统探索。本文旨在回答：**LLM 能否在几乎不做领域特定设计的情况下，通过合理选择通用设计空间中的各个因素，达到接近最先进的图像生成性能？**
- **研究背景**：图像生成主流使用扩散模型（如 DiT、Stable Diffusion），文本生成则依靠自回归语言模型。将 LLM 范式迁移到视觉领域有望实现多模态统一、尺度扩展等优势，但设计空间尚未被系统阐明。本文填补了这一空白。

## 2. 论文提出的方法论

### 核心思想
通过系统探索图像生成中 LLM 的六个关键设计维度，找到最优组合，从而构建一个**无需领域特定偏置**的强自回归图像生成模型（ELM）。

### 关键技术细节

| 设计维度 | 探索选项 | 最优选择 |
|---------|---------|---------|
| 图像分词器 | VQGAN vs. BAE（二进制自动编码器） | **BAE**（代码利用率100%，重构/生成性能均更优） |
| 建模方法 | 自回归（AR） vs. 掩码语言模型（MLM） | **AR**（一致优于MLM，且缩放行为更稳定） |
| 扫描模式 | 行主序、列主序、行锯齿、列锯齿、对角锯齿等5种 | **行主序光栅扫描**（效果最佳） |
| 词汇表设计 | 代码维度 D 决定词汇量 K=2^D；通过代码分解将大词汇拆分为多个子词汇 | **拆分为两个子码**（如2-10、2-12）最优，降低复杂度、提升性能 |
| 模型尺度 | L/XL/XXL/2B（参数从315M到1.9B） | 词汇复杂度应匹配模型容量：小模型用简单词汇（2-10），大模型用复杂词汇（2-12） |
| 采样策略 | CFG（分类器自由引导）调度方式、top-k（AR）、温度τ（MLM）、MLM迭代次数 | **线性递增CFG**、**高随机性**（大top-k或大τ），MLM约10次迭代 |

### 关键公式/算法流程（文字说明）

- **BAE 量化**：对每个空间潜在向量 \( z_{ij} \in \mathbb{R}^D \) 的每个标量值进行符号函数或伯努利采样，将其转化为二进制值（0/1），从而形成结构化码本。
- **AR 模型**：序列 \( q = (q_1,...,q_L) \) 的概率建模为 \( p(q) = \prod_{l=1}^L p(q_l | q_1,...,q_{l-1}) \)，损失为交叉熵 \( \mathcal{L}_{\text{ar}} = -\mathbb{E}_{x\sim p(x)}[\log p(q)] \)。
- **MLM 模型**：对部分 token 进行掩码，预测被掩码的 token，损失为 \( \mathcal{L}_{\text{mlm}} = -\mathbb{E}_{x\sim p(x)}[\sum_{l: m_l=1} \log p(q_l | q_{\text{masked}})] \)。
- **代码分解**：例如将8位二进制码 [1,0,1,0,0,0,1,1] 拆分为两个4位子码 [1,0,1,0] 和 [0,0,1,1]，然后分别嵌入并拼接后投影回原始特征维度，预测头也分开。
- **采样策略**：AR 使用 top-k 从预测分布中采样，MLM 使用带 Gumbel 噪声的置信度采样（温度 τ），CFG 采用线性递增调度（如从1.0线性增加到3.0）。

## 3. 实验设计

### 数据集与场景
- **主数据集**：ImageNet（256×256 和 512×512），类别条件图像生成。
- **额外数据集**：CelebA（人脸，202,599张）、DTD（纹理，5,640张）——用于验证泛化能力。
- **零样本任务**：类别插值（混合两个类条件）、图像编辑（掩码区域重生成）。

### Benchmark
- **主要指标**：FID（弗雷歇 inception 距离）、IS（inception 分数）、Precision、Recall。
- 生成 50,000 张样本评估（消融实验中部分使用 30,000 张以提升效率，并在对比时统一到50k）。

### 对比方法
- **扩散模型**：DiT-L/2、DiT-XL/2、SiT-XL/2
- **掩码语言模型**：MaskGIT（含拒绝采样版本）
- **自回归模型**：VQGAN、LlamaGen（含不同大小）、VAR（不同尺度，含拒绝采样）、MAR（含B/H/L/H）
- 本文提出的 **ELM**：L/XL/XXL/2B 四个版本。

## 4. 资源与算力

- **GPU 型号与数量**：
  - BAE 分词器训练：80GB A800 GPU（未给出具体数量，推测为8卡）。
  - AR/MLM 模型训练：
    - L（315M）和 XL（757M）：各8张 A800，训练约400 epochs，分别耗时约6.4天和10天。
    - XXL（1.4B）：16张 A800（2节点×8卡），训练400 epochs约12天。
    - 2B（1.9B）：未明确说明卡数与时长，但提到因时间限制提前停止训练。
  - 所有模型使用 batch size 256，常数学习率 1e-4，weight decay 0.05，AdamW 优化器。

## 5. 实验数量与充分性

- **主要实验组数**：
  - 分词器对比：BAE vs VQGAN（不同词汇量，AR和MLM两种建模方式）。
  - 建模方法对比：AR vs MLM（L/XL/XXL三个尺度，训练400 epochs，记录FID/IS曲线）。
  - 扫描模式对比：5种模式（AR-L级别）。
  - 词汇设计：1-16、2-8、2-10、2-12、3-8、4-8等多种分解方式，在L/XL/XXL上测试。
  - 采样策略：CFG调度方式（常数、余弦、线性、平方等6种）、top-k范围、MLM迭代次数（1~256）、Gumbel温度τ。
  - 尺度缩放：不同模型大小（L/XL/XXL/2B）和词汇复杂度组合，展示损失曲线和生成效果。
  - 高分辨率迁移：256→512 fine-tune 仅250k步（约50 epochs）。
  - 额外数据集：CelebA和DTD上的训练与生成。
  - 零样本泛化：类别插值、图像编辑。
- **充分性评价**：
  - **优点**：覆盖了所有关键设计维度，每个维度均进行多组对比，消融实验较为完整；使用统一的模型架构（LLaMA-2）和训练策略，确保对比公平；最终结果在多个尺度上验证了稳定性。
  - **不足**：部分消融实验（如扫描模式）仅采用30k样本计算FID，且仅在一个模型大小上测试；高分辨率结果仅报告了两个模型（L和XL），且fine-tune步数较短；未在更大规模数据集（如LAION）上验证；MLM与AR的对比仅在BAE-16上进行，未在多种词汇复杂度下重复。

## 6. 论文的主要结论与发现

1. **BAE 优于 VQGAN**：BAE 具有 100% 码本利用率，重构和生成 FID 均显著优于 VQGAN，且不会出现“代码坍缩”。
2. **AR 优于 MLM**：在所有模型尺度上，AR 模型一致获得更低的 FID 和更高的 IS，且缩放行为更稳定（MLM 在后期会出现 FID 与 IS 背离）。
3. **行主序光栅扫描最佳**：但各种扫描模式差异不大，说明 AR 模型对扫描顺序不敏感。
4. **词汇分解为两个子码最优**：分解成两个较小的词汇（如 2-10、2-12）可降低学习难度、减少计算成本，过多子码（3-8、4-8）反而使训练损失升高。
5. **词汇复杂度与模型容量需匹配**：小模型（L/XL）用 2-10 最佳，大模型（XXL/2B）用 2-12 最佳。
6. **采样需要高随机性**：AR 需要较大的 top-k（接近词汇量一半），MLM 需要较高的 Gumbel 温度，远高于文本生成所需；线性递增的 CFG 调度优于恒定值。
7. **缩放规律成立**：更大模型能捕获更多全局信息（通过注意力可视化验证），训练损失和生成指标均随模型增大而改善。
8. **图像 token 具有更高随机性**：与文本相比，图像 token 分布更接近均匀分布，缺乏语法结构，导致训练损失难以收敛，但模型仍能生成高质量图像——这意味着图像生成对预测错误的容忍度更高，也解释了高随机性采样的必要性。

## 7. 优点（方法或实验设计亮点）

- **系统性**：首次完整、公正地探索了 LLM 用于图像生成的六个关键设计维度，每个维度均进行定量对比。
- **公平性**：所有 AR 和 MLM 模型使用完全相同的架构（LLaMA-2）和训练配置，去除了架构差异的影响。
- **无需领域偏置**：最终模型 ELM 未使用任何专为图像设计的技巧（如多尺度预测、随机置换、扩散损失等），证明了 LLM 的通用性。
- **深入分析**：通过注意力可视化解释了缩放行为，通过 token 分布分析揭示了视觉与语言模态的本质差异，为未来研究提供了理论依据。
- **实用性**：展示了 LLM 的可扩展性（高分辨率 fine-tune 高效）、零样本泛化能力（类别插值、图像编辑）以及任意尺寸生成（流式行为）。

## 8. 不足与局限

- **实验覆盖**：
  - 仅使用 ImageNet 一个主要数据集（虽然也在 CelebA、DTD 上做了补充，但未报告定量指标如 FID）。
  - 高分辨率 512×512 仅测试了两种模型大小，且 fine-tune 步数较少。
  - 部分消融（扫描模式、CFG 调度）仅在 30k 样本下评估，可能与 50k 结果存在偏差。
- **方法局限**：
  - 传统交叉熵损失对于高度随机的图像 token 分布并非最优目标，作者也指出未来应探索更合适的训练目标（如扩散损失）。
  - 词汇分解虽然有效，但未提供理论解释为何“分为两个子码”是最优数。
- **资源限制**：2B 模型未能完成全部 400 epochs 训练，导致最终性能可能尚未饱和。
- **应用限制**：模型仅在 ImageNet 类别条件生成上验证，未涉及开放域文生图等更实际的任务；英伟达/谷歌等还拥有大规模内部数据集和算力，论文使用的资源相对有限。
- **泛化性分析不足**：虽然做了类别插值和图像编辑实验，但仅提供定性展示，缺乏定量评估（如编辑成功率）。
- **与 SOTA 对比**：ELM 在 256×256 上 FID 1.54（ELM-2B）虽与 VAR-d30-re（1.80）和 MAR-H（1.55）相当，但略逊于 MAR-H（1.55），且未与最新的扩散模型（如 PixArt-α、SD v3）在同等尺度下对比。

（完）
