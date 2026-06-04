---
title: On Mechanistic Knowledge Localization in Text-to-Image Generative Models
title_zh: 文本到图像生成模型中的机理知识定位
authors: "Samyadeep Basu, Keivan Rezaei, Priyatham Kattakinda, Vlad I Morariu, Nanxuan Zhao, Ryan A. Rossi, Varun Manjunatha, Soheil Feizi"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=fsVBsxjRER"
tags: ["query:ce"]
score: 7.0
evidence: 研究文本到图像模型中的机理知识定位，支持模型编辑和概念擦除
tldr: 针对文本到图像模型中知识定位困难的问题，引入机理定位概念，通过因果追踪识别控制视觉属性的层，发现早期扩散模型知识集中于CLIP文本编码器第一层，而近期模型定位更分散，为模型编辑和概念擦除提供了理论指导和实践基础。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1655, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 666, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 675, \"height\": 261, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1673, \"height\": 1009, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1785, \"height\": 494, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1761, \"height\": 908, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 827, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 818, \"height\": 629, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 852, \"height\": 765, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 844, \"height\": 424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1675, \"height\": 615, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1714, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1224, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1731, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1719, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1711, \"height\": 461, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1720, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1696, \"height\": 462, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1706, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1715, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1711, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1705, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1713, \"height\": 458, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1719, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1721, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1693, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1678, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1687, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1666, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1681, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1677, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1723, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1701, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1689, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1694, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1691, \"height\": 449, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1717, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1717, \"height\": 455, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1708, \"height\": 457, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1692, \"height\": 540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1498, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1737, \"height\": 770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 1752, \"height\": 750, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-044.webp\", \"caption\": \"\", \"page\": 0, \"index\": 44, \"width\": 1736, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-045.webp\", \"caption\": \"\", \"page\": 0, \"index\": 45, \"width\": 1736, \"height\": 747, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-046.webp\", \"caption\": \"\", \"page\": 0, \"index\": 46, \"width\": 1666, \"height\": 941, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-047.webp\", \"caption\": \"\", \"page\": 0, \"index\": 47, \"width\": 1686, \"height\": 938, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-048.webp\", \"caption\": \"\", \"page\": 0, \"index\": 48, \"width\": 1311, \"height\": 704, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-049.webp\", \"caption\": \"\", \"page\": 0, \"index\": 49, \"width\": 1298, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-050.webp\", \"caption\": \"\", \"page\": 0, \"index\": 50, \"width\": 1730, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-051.webp\", \"caption\": \"\", \"page\": 0, \"index\": 51, \"width\": 1505, \"height\": 546, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-052.webp\", \"caption\": \"\", \"page\": 0, \"index\": 52, \"width\": 853, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-053.webp\", \"caption\": \"\", \"page\": 0, \"index\": 53, \"width\": 1385, \"height\": 941, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-054.webp\", \"caption\": \"\", \"page\": 0, \"index\": 54, \"width\": 903, \"height\": 2076, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-055.webp\", \"caption\": \"\", \"page\": 0, \"index\": 55, \"width\": 1250, \"height\": 1965, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-056.webp\", \"caption\": \"\", \"page\": 0, \"index\": 56, \"width\": 1249, \"height\": 1946, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-057.webp\", \"caption\": \"\", \"page\": 0, \"index\": 57, \"width\": 756, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-058.webp\", \"caption\": \"\", \"page\": 0, \"index\": 58, \"width\": 1603, \"height\": 171, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-fsvbsxjrer/fig-059.webp\", \"caption\": \"\", \"page\": 0, \"index\": 59, \"width\": 726, \"height\": 731, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-fsvbsxjrer/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 873, \"height\": 653, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-fsvbsxjrer/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1258, \"height\": 203, \"label\": \"Table\"}]"
motivation: 现有因果追踪难以精确定位知识层，阻碍了高效的模型编辑。
method: 引入机理定位概念，通过因果追踪分析视觉属性对应的知识层。
result: 发现早期模型知识集中，近期模型知识分散，解释了编辑困难的原因。
conclusion: 该工作为文本到图像模型的概念擦除和编辑提供了定位方法。
---

## Abstract
Identifying layers within text-to-image models which control visual attributes can facilitate efficient model editing through closed-form updates. Recent work, leveraging causal tracing show that early Stable-Diffusion variants confine knowledge primarily to the first layer of the CLIP text-encoder, while it diffuses throughout the UNet. Extending this framework, we observe that for recent models (e.g., SD-XL, DeepFloyd), causal tracing fails in pinpointing localized knowledge, highlighting challenges in model editing. To address this issue, we introduce the concept of mechanistic localization in text-to-image models, where knowledge about various visual attributes (e.g., "style", "objects", "facts") can be mechanistically localized to a small fraction of layers in the UNet, thus facilitating efficient model editing. We localize knowledge using our method LocoGen which measures the direct effect of intermediate layers to output generation by performing interventions in the cross-attention layers of the UNet. We then employ LocoEdit, a fast closed-form editing method across popular open-source text-to-image models (including the latest SD-XL) and explore the possibilities of neuron-level model editing. Using mechanistic localization, our work offers a better view of successes and failures in localization-based text-to-image model editing.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：在文本到图像生成模型中，如何高效定位控制特定视觉属性（如风格、对象、事实）的知识层，以便通过闭式更新进行模型编辑？现有的因果追踪方法在早期 Stable Diffusion 模型（如 v1.5）上能发现 CLIP 文本编码器第一层的局部知识，但在较新模型（如 SD-XL、DeepFloyd）上失效，知识分布更分散或无法定位，导致模型编辑困难。
- **背景**：文本到图像模型（如 Stable Diffusion、Imagen、DALL·E）在生成逼真图像方面表现优异，但内部知识存储机制尚不明确。现有解释性方法（DAAM、Prompt-to-Prompt）侧重于注意力图分析，而因果追踪只能适用于特定架构。作者希望提出一种通用框架，能在多种模型上定位视觉属性的控制层，从而支持高效的模型编辑（如去除风格、修改对象、更新事实）。

## 2. 方法论：核心思想、关键技术细节、算法流程
- **核心思想**：引入“机理定位”（mechanistic localization）概念，即通过测量中间层对输出的直接效应来定位控制特定视觉属性的少量交叉注意力层。相比因果追踪的间接效应，该方法直接干预层输入，观测输出变化。
- **关键技术细节**：
  - **LocoGen 算法**：给定视觉属性（如“梵高风格”），构建一组包含该属性的提示 `T_i` 和对应的目标提示 `T'_i`（属性被移除或更新）。对于 UNet 中连续的 m 个交叉注意力层子集 `C'`，将这些层的键/值输入替换为目标提示的文本嵌入 `c'_i`，其他层保持原提示嵌入 `c_i`。生成修改后的图像，用 CLIP 分数评估属性是否被移除（对于风格、对象，CLIP 分数越低越好；对于事实，CLIP 分数越高越好）。遍历所有候选子集（仅考虑相邻连续层，降低搜索复杂度），选择使平均 CLIP 分数最优的层集作为控制层。
  - **m 的选择**：从 1 开始递增，直到找到满足阈值的最小 m。
  - **LocoEdit 方法**：在 LocoGen 定位的层上，通过闭式解优化键矩阵和值矩阵，使其对原提示的嵌入映射到目标提示的嵌入。优化目标为最小化重建误差加正则项（岭回归），公式为：
    ```
    min_W_K ||X_orig W_K - X_target W_K||^2 + λ_K ||W_K - W_K||^2
    ```
    得到闭式解：`W_K = (X_orig^T X_orig + λI)^-1 (X_orig^T Y_target + λ_K W_K)`，对值矩阵类似处理。
  - **神经元级编辑**：在定位层内，通过 z-score 识别对特定风格激活差异最大的少数神经元，在推理时 dropout 这些神经元，以去除风格。

## 3. 实验设计：数据集 / 场景、基准、对比方法
- **数据集与场景**：使用 Basu et al. (2023) 和 Kumari et al. (2023) 中的提示集，包括多种视觉属性：
  - **风格**：梵高、莫奈、毕加索、格雷格·鲁特科夫斯基等。
  - **对象**：Snoopy、R2D2、Nemo 等商标对象。
  - **事实**：“美国总统”（替换为“乔·拜登”）、“英国君主”（替换为“查尔斯王子”）等。
- **基准 (Benchmark)**：主要使用 CLIP 分数（CLIP-Score）定量评估编辑效果。对于风格和对象，编辑后 CLIP 分数应降低；对于事实，应提高。还进行了人类评估。
- **对比方法**：
  - 因果追踪（Basu et al., 2023）——但仅在早期模型上有效。
  - 概念擦除方法：Concept-Ablation (Kumari et al., 2023)、Concept-Erasure (Gandikota et al., 2023)、DiffQuickFix (Basu et al., 2023)。
  - 对比场景：在 SD-v1.5 上比较 LocoEdit 与上述方法；在 SD-v2.1 上对比 DiffQuickFix；还比较了“更新所有层” vs “仅更新定位层”。

## 4. 资源与算力
- **明确说明**：论文中未提及具体使用的 GPU 型号、数量或训练时长。仅说明代码将开源（https://github.com/samyadeepbasu/LocoGen）。推测所需算力较低，因为方法本身是推理时的干预和闭式更新，无需大规模重新训练。但具体资源消耗未报告。

## 5. 实验数量与充分性
- **实验数量**：
  - **因果追踪失效验证**：对 SD-v1.5、SD-v2.1、OpenJourney、SD-XL、DeepFloyd 五类模型进行 UNet 和文本编码器的因果追踪实验，展示了分布情况（Figure 2、3）。
  - **LocoGen 定位实验**：对每种模型、每种属性（风格、对象、事实）分别进行定位，给出定性图像（Figure 4）和定量 CLIP 分数曲线（Figure 5）。覆盖多个提示（每个属性至少 8 个提示）。
  - **LocoEdit 编辑实验**：定性展示编辑效果（Figure 6、46-53），定量对比 CLIP 分数（Figure 8）。
  - **神经元级编辑实验**：对 6 种艺术家风格进行神经元 dropout 实验（Figure 9、10），定量展示不同神经元数量下的 CLIP 分数变化。
  - **鲁棒性测试**：使用 320 个 MS-COCO 提示（80 个对象 × 4 个位置）测试编辑后模型对通用提示的影响（Table 1）。
  - **人类评估**：132 对图像，5 名评估者，92.58% 验证率（Appendix J）。
- **充分性与客观性**：
  - 覆盖主流开源模型，对比了现有方法，定量指标多样。但缺乏对其他基准（如 FID、IS）的评估，主要依赖 CLIP 分数。消融实验包括 m 选择、局部 vs 全层更新，较充分。人类评估增强了主观验证。但未在更大规模数据集（如 LAION 全量）上进行验证。

## 6. 主要结论与发现
- **因果追踪局限性**：在 SD-v1.5 和 SD-v2.1 的文本编码器中存在唯一因果状态，但在 SD-XL 和 DeepFloyd 中消失；UNet 中知识分布情况因模型而异（SD-XL 稀疏，DeepFloyd 无显著因果状态）。
- **LocoGen 有效性**：可在所有测试模型中发现控制视觉属性的少量连续交叉注意力层。风格知识集中在特定层（如 SD-v1.5 和 SD-v2.1 的层 8，SD-XL 的层 45），对象和事实知识集中于其他层（如 SD-v1.5 的层 6）。DeepFloyd 的定位依赖于具体提示而非属性类别。
- **LocoEdit 编辑能力**：能有效去除风格、修改对象、更新事实，且保持对通用提示的鲁棒性（CLIP 分数下降很小）。局部编辑优于全层编辑。
- **神经元级编辑可能性**：对风格属性，可通过 dropout 少量神经元（如 50-100 个）实现风格去除，表明了更细粒度的控制。

## 7. 优点：方法或实验设计上的亮点
- **通用性强**：提出的 LocoGen 方法适用于多种架构（SD-v1/2、OpenJourney、SD-XL、DeepFloyd），而因果追踪只适用于早期模型。
- **高效编辑**：LocoEdit 基于闭式解，无需微调，速度快；仅更新少量层，不破坏模型其他能力。
- **可解释性提升**：揭示了不同模型知识存储的差异（如 SD-XL 风格和事实在同层，DeepFloyd 依赖于提示），为理解模型内部机制提供了工具。
- **神经元级分析**：首次展示可以定位和编辑到神经元级别，推动了更细粒度的理解。
- **实验设计全面**：包括定性、定量、消融、人类评估和鲁棒性测试，对比了多种基线方法。
- **代码开源**：促进可重复性。

## 8. 不足与局限
- **实验覆盖有限**：
  - 未在更多数据集（如 LAION-5B 子集或真实用户提交的提示）上测试，仅使用手工选取的少量提示。
  - 缺乏对编辑后模型生成多样性和质量的其他指标评估（如 FID、IS）。
- **DeepFloyd 局限性**：LocoGen 虽能定位，但 LocoEdit 闭式更新因 T5 编码器双向注意力而失效（需要 token 级映射，但 T5 中后续 token 也含重要信息）。论文未提出替代方案。
- **搜索空间简化**：只考虑相邻连续层，可能遗漏非连续的最优子集。m 通过阈值手动选择，可能不最优。
- **CLIP 分数偏差**：主要依赖 CLIP 分数评估，但 CLIP 分数本身可能对某些属性不敏感（如风格细微变化）。
- **鲁棒性测试范围**：仅用 320 个提示测试通用提示影响，可能不够全面。
- **未说明算力消耗**：无法评估方法实际计算成本。
- **神经元级编辑的副作用**：droput 神经元可能影响其他属性，质量随神经元数量增加而下降（文中已指出）。

（完）
