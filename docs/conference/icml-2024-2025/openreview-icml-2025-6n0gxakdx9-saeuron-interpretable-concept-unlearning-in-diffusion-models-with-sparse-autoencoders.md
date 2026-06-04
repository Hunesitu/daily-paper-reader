---
title: "SAeUron: Interpretable Concept Unlearning in Diffusion Models with Sparse Autoencoders"
title_zh: "SAeUron: 基于稀疏自编码器的扩散模型可解释概念遗忘"
authors: "Bartosz Cywiński, Kamil Deja"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6N0GxaKdX9"
tags: ["query:ce"]
score: 8.0
evidence: 面向图像生成的机器遗忘
tldr: 论文针对扩散模型生成有害内容的问题，提出SAeUron方法，利用稀疏自编码器学习可解释特征，并通过特征选择移除特定概念。实验表明该方法能有效去除目标概念而保持生成质量，为可解释机器遗忘提供了新途径。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 761, \"height\": 1079, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1767, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 844, \"height\": 438, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 808, \"height\": 492, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 847, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 857, \"height\": 582, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 841, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1580, \"height\": 691, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 853, \"height\": 416, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 885, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 800, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1313, \"height\": 528, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1313, \"height\": 527, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1703, \"height\": 706, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 834, \"height\": 624, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 833, \"height\": 623, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1166, \"height\": 1424, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1058, \"height\": 644, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1056, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1067, \"height\": 621, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 825, \"height\": 1118, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1209, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1210, \"height\": 846, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1213, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1675, \"height\": 1297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1550, \"height\": 520, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 859, \"height\": 568, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1380, \"height\": 726, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1391, \"height\": 673, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1390, \"height\": 663, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1402, \"height\": 2141, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1403, \"height\": 2141, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1598, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1550, \"height\": 1448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1232, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1234, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1230, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1230, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1234, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1231, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1232, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1233, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6n0gxakdx9/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 1232, \"height\": 485, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6n0gxakdx9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1773, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6n0gxakdx9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1778, \"height\": 472, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6n0gxakdx9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1782, \"height\": 315, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6n0gxakdx9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 988, \"height\": 246, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6n0gxakdx9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 873, \"height\": 963, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6n0gxakdx9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 661, \"height\": 200, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6n0gxakdx9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 873, \"height\": 634, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6n0gxakdx9/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1777, \"height\": 300, \"label\": \"Table\"}]"
motivation: 扩散模型可能生成有害内容，现有遗忘方法缺乏透明度。
method: 训练稀疏自编码器捕捉多时间步特征，选择对应概念的特征进行移除。
result: 成功移除指定概念，保持生成质量，且可解释。
conclusion: SAeUron提供了可解释且有效的概念遗忘方法。
---

## Abstract
Diffusion models, while powerful, can inadvertently generate harmful or undesirable content, raising significant ethical and safety concerns. Recent machine unlearning approaches offer potential solutions but often lack transparency, making it difficult to understand the changes they introduce to the base model. In this work, we introduce SAeUron, a novel method leveraging features learned by sparse autoencoders (SAEs) to remove unwanted concepts in text-to-image diffusion models. First, we demonstrate that SAEs, trained in an unsupervised manner on activations from multiple denoising timesteps of the diffusion model, capture sparse and interpretable features corresponding to specific concepts. Building on this, we propose a feature selection method that enables precise interventions on model activations to block targeted content while preserving overall performance. Our evaluation shows that SAeUron outperforms existing approaches on the UnlearnCanvas benchmark for concepts and style unlearning, and effectively eliminates nudity when evaluated with I2P. Moreover, we show that with a single SAE, we can remove multiple concepts simultaneously and that in contrast to other methods, SAeUron mitigates the possibility of generating unwanted content under adversarial attack. Code and checkpoints are available at [GitHub]( https://github.com/cywinski/SAeUron).

---

## 论文详细总结（自动生成）

# 论文总结：SAeUron: 基于稀疏自编码器的扩散模型可解释概念遗忘

## 1. 核心问题与整体含义（研究动机和背景）

扩散模型（如 Stable Diffusion）在生成高质量图像的同时，可能无意中产生有害或不希望的内容（如色情、版权风格等）。现有机器遗忘方法多基于微调，但缺乏透明度，难以理解模型内部如何被修改，且易受对抗攻击、多概念遗忘时性能下降。本文提出 SAeUron，利用稀疏自编码器（Sparse Autoencoder, SAE）从扩散模型的内部激活中学习稀疏、可解释的特征，通过定位并移除与目标概念相关的特征来实现概念遗忘，同时保持模型整体性能。

## 2. 方法论：核心思想、关键技术细节、算法流程

### 核心思想
- 在扩散模型 U-Net 的交叉注意力块上训练一个 SAE，该 SAE 以无监督方式学习激活向量的稀疏分解，每个隐藏特征对应一个可解释的视觉概念（如猫耳朵、爪子等）。
- 通过特征重要性分数（对比含目标概念和不含目标概念的激活均值）筛选出与目标概念高度相关的少数特征。
- 在推理时，将原始激活输入 SAE 编码器，对选中的特征施加负向缩放（ablating），然后通过解码器重构激活，从而阻断该概念在后续生成中的影响。

### 技术细节
- **SAE 结构**：采用 BatchTopK 激活函数，保留每批中最活跃的 \( k \) 个特征；使用膨胀因子 16，隐层维度 \( n = 20480 \)，\( k = 32 \)。
- **特征选择分数**：
  \[
  \text{score}(i, t, c, D) = \frac{\mu(i, t, D_c)}{\sum_j \mu(j, t, D_c) + \delta} - \frac{\mu(i, t, D_{\neg c})}{\sum_j \mu(j, t, D_{\neg c}) + \delta}
  \]
  其中 \(\mu\) 为平均激活，\(D_c\) 为目标概念样本，\(D_{\neg c}\) 为非目标样本。
- **特征阻断**：对排名前 \(\tau_c\) 的特征，当激活值超过全局平均时，乘以负乘数 \(\gamma_c\)（通常 -1 或负值）。
- **应用位置**：风格遗忘用 up.1.2 块，物体遗忘用 up.1.1 块。

### 算法流程
1. 预训练 SAE：收集扩散模型多个去噪时间步的激活（仅文本条件部分），用 BatchTopK SAE 重构。
2. 计算特征重要性分数，选定需要阻断的特征集 \(F_c\)。
3. 推理时：对每一时间步，将特征图展平，逐位置通过 SAE 编码器，对 \(F_c\) 中特征按公式（6）缩放，再经解码器还原，替换原激活图。

## 3. 实验设计、数据集、Benchmark 与对比方法

### 数据集与 Benchmark
- **UnlearnCanvas**：50 种风格 × 20 种物体，提供专用 Stable Diffusion v1.5 微调模型，评估风格和物体遗忘。指标包括：
  - UA（遗忘准确率）：目标概念不被分类器正确分类的比例。
  - IRA（域内保留准确率）：其他概念仍被正确分类的比例。
  - CRA（跨域保留准确率）。
  - FID：生成图像质量。
- **I2P 基准**：4703 条不当提示，用于评估 NSFW 内容移除，使用 NudeNet 检测。
- **对抗攻击评估**：采用 UnlearnDiffAtk 方法（5 词前缀优化 40 轮）。

### 对比方法
- ESD, FMN, UCE, CA, SalUn, SEOT, SPM, EDiff, SHS（共 9 种）。

## 4. 资源与算力

文中提及：
- SAE 训练使用 **单张 NVIDIA RTX A5000 GPU**。
- 物体块 SAE（up.1.1）训练约 **27 小时 40 分钟**，风格块（up.1.2）约 **59 小时 1 分钟**。
- 未说明训练数据总量具体大小，但提到使用 80 个锚点提示 × 20 类物体（80×20=1600 个提示），每个提示生成 50 步，每步取得 \(16\times16=256\) 个特征向量，总共样本量约 1600×50×256 ≈ 2048 万条激活向量。
- 推理时引入约 **1.92% 的额外时间开销**。

## 5. 实验数量与充分性

- **主实验**：UnlearnCanvas 上风格遗忘和物体遗忘各一组，结果取 5 个随机种子平均。
- **NSFW 遗忘**：I2P 基准上一组（含多个子类别检测）。
- **多概念顺序遗忘**：6 个风格依次遗忘，与 8 种方法比较。
- **对抗鲁棒性**：UnlearnDiffAtk 攻击前后 UA 对比。
- **消融/分析**：
  - KNN 分类验证特征区分能力（图 4，图 16）。
  - 特征激活热图可视化（图 5，图 6）。
  - 超参数选择实验（图 31）。
  - SAE 在不同训练数据规模下的性能（图 23）。
  - OOD 泛化：训练一半风格，测试全部（表 4）。
  - 极端多概念遗忘（49/50 风格）。

**充分性评价**：实验覆盖多种场景（风格、物体、不雅内容、多概念顺序、对抗攻击），对比方法全面，消融和可视化充分。但缺乏对更大模型（如 SDXL）的验证，以及未在更多随机种子下重复 NSFW 实验。

## 6. 主要结论与发现

1. **SAE 能有效提取视觉概念的可解释特征**：如猫的耳朵、兔子面部等，特征激活位置与语义区域吻合。
2. **SAeUron 在 UnlearnCanvas 上达到 SOTA**：风格遗忘 UA 95.80%，IRA 99.10%，CRA 99.40%；物体遗忘 UA 78.82%，IRA 95.47%，CRA 95.58%；综合平均值 94.03% 最高。
3. **NSFW 移除效果优秀**：I2P 上总检测数降至 118（原 SD v1.4 为 7743），且模型质量保持良好。
4. **多概念顺序遗忘性能稳定**：当丢弃概念数增至 6 个时，其他方法性能大幅下降，而 SAeUron 仍保持高 UA 和保留准确率。
5. **对对抗攻击鲁棒**：在 UnlearnDiffAtk 下，UA 几乎无下降，对比方法下降显著。
6. **SAE 可泛化到未见过概念**：仅用一半数据训练，仍能部分遗忘未见概念。

## 7. 优点

- **可解释性强**：通过 SAE 特征热图和 VLM 自动标注，清晰展示哪些特征被阻断，便于审核和诊断。
- **不修改模型权重**：仅在推理时干预激活，无永久性损害，易于复原。
- **低存储与计算需求**：SAE 仅约 2.8 GB 存储，训练只需单张 GPU。
- **鲁棒性高**：对对抗攻击和多概念遗忘任务表现优异。
- **模块化**：可同时或顺序遗忘任意多个概念，无需重新训练 SAE。

## 8. 不足与局限

- **推理时开销**：引入 1.92% 延迟，对实时应用可能不理想。
- **需要预训练数据**：SAE 训练需要足够多的激活样本（文中使用 1600 个提示 × 50 步），新概念若无代表性样本则难以精确定位特征。
- **相似概念干扰**：如猫和狗共享部分低层特征，遗忘一个会轻微影响另一个（图 24-28）。
- **抽象概念困难**：对“仇恨”“暴力”等非具体视觉概念，SAE 无法有效捕捉（I2P 总体表现一般）。
- **开源场景易被绕过**：因为推理时修改是外置模块，用户可移除屏蔽机制。
- **未验证更大模型**：仅基于 SD v1.4/v1.5，未测试 SDXL 等。
- **特征选择依赖验证集**：需事先收集目标概念的激活样本，增加部署成本。

（完）
