---
title: "Fundamental Limits of Visual Autoregressive Transformers: Universal Approximation Abilities"
title_zh: 视觉自回归变换器的基本极限：通用逼近能力
authors: "Yifang Chen, Xiaoyu Li, Yingyu Liang, Zhenmei Shi, Zhao Song"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=magOSIm8UT"
tags: ["query:ce"]
score: 10.0
evidence: 自回归图像生成模型
tldr: 论文研究了视觉自回归变换器（VAR）的理论能力，证明简单的VAR变换器具有通用逼近性，为自回归图像生成模型提供了理论基础。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-magosim8ut/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 787, \"height\": 358, \"label\": \"Figure\"}]"
motivation: 自回归图像生成模型的理论基础尚不清晰。
method: 通过数学分析证明单层VAR变换器的通用逼近性。
result: 证明了VAR变换器是通用逼近器，理论性能优越。
conclusion: 该工作为VAR模型提供了理论支撑，推动自回归图像生成发展。
---

## Abstract
We investigate the fundamental limits of transformer-based foundation models, extending our analysis to include Visual Autoregressive (VAR) transformers. VAR represents a big step toward generating images using a novel, scalable, coarse-to-fine ``next-scale prediction'' framework. These models set a new quality bar, outperforming all previous methods, including Diffusion Transformers, while having state-of-the-art performance for image synthesis tasks. Our primary contributions establish that, for single-head VAR transformers with a single self-attention layer and single interpolation layer, the VAR Transformer is universal. From the statistical perspective, we prove that such simple VAR transformers are universal approximators for any word-to-image Lipschitz functions. Furthermore, we demonstrate that flow-based autoregressive transformers inherit similar approximation capabilities. Our results provide important design principles for effective and computationally efficient VAR Transformer strategies that can be used to extend their utility to more sophisticated VAR models in image generation and other related areas.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：视觉自回归变换器（VAR）通过“next-scale prediction”粗到细的框架在图像生成任务中取得了最先进的性能，甚至超越了扩散变换器（Diffusion Transformers）。然而，之前的工作仅停留在实证层面，缺乏对VAR变换器为何能如此有效的理论理解。同样，流自回归模型（FlowAR）也缺乏理论分析。
- **核心问题**：VAR变换器是否具有通用逼近能力？即能否在极简配置（单层、单头自注意力、单插值层）下逼近任意词到图像的Lipschitz函数？
- **整体含义**：证明即使是最小规模的VAR变换器也具备通用逼近性，为自回归图像生成模型提供了坚实的理论基础，并揭示了其成功背后的理论根源。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：通过数学推导证明单层、单头VAR变换器可以任意逼近任意Lipschitz连续的词到图像映射函数。同时将该结果推广到FlowAR和HOFAR模型中。
- **关键技术细节**：
  - **定义VAR Transformer**：由金字塔上采样层（Φ_up）、单层自注意力（Attn）和前馈网络（FFN）组成。输入初始令牌图X_init，经过多级上采样和注意力模块生成金字塔形状的令牌图。
  - **通用逼近性证明框架**：
    1. 使用量化技术将连续函数离散化，构造一个分段常数逼近函数。
    2. 利用上下文映射（Contextual Mapping）性质证明单层注意力可以区分不同序列中的相同令牌（Lemma 5.4）。
    3. 通过两层扰动引理（Lemma 6.3）和多层组合扰动引理（Lemma 6.4, 6.5）累积误差，最终证明VAR Transformer整体逼近误差为O(ϵ)（Theorem 6.6）。
  - **推广到FlowAR和HOFAR**：只需将上采样函数替换为下采样函数（FlowAR）或增加高阶项（HOFAR），相似的分析依然成立（Corollary 7.2, 7.3）。

### 3. 实验设计
- **实验情况**：论文完全是理论性质，没有设计任何实验。没有数据集、benchmark或对比方法。全文没有展示任何实验结果或数值验证。

### 4. 资源与算力
- **资源与算力**：论文未提及任何计算资源（GPU型号、数量、训练时长等），因为理论工作不依赖实验算力。

### 5. 实验数量与充分性
- **实验数量与充分性**：论文不包含实验。因此无法评价实验的充分性、客观性或公平性。所有结论均基于数学定理证明，而非实证验证。

### 6. 论文的主要结论与发现
- 单层、单头VAR变换器是Lipschitz词到图像函数的通用逼近器（Theorem 6.6）。
- FlowAR和HOFAR模型继承类似的通用逼近能力（Corollary 7.2, 7.3）。
- 即使在最简配置下（单层、单头），VAR Transformer也具备强大的表达能力，这解释了其在实际任务中的高效性。
- 研究为设计更灵活、高效的自回归生成模型提供了理论指导。

### 7. 优点
- **理论贡献突出**：首次严格证明了VAR变换器的通用逼近性，填补了该领域的理论空白。
- **方法严谨**：采用量化、上下文映射、扰动累加等数学工具，证明框架完整且具有推广性。
- **覆盖多种模型**：不仅分析VAR，还推广到FlowAR和HOFAR，显示方法的普适性。
- **指导意义**：证明最小配置已具备强大能力，暗示未来可专注于效率优化（如权值共享、低秩适配）而不损失表达能力。

### 8. 不足与局限
- **缺乏实验验证**：纯理论分析，未通过任何实验（如图像生成质量、训练效率）验证理论结论的实际有效性。
- **应用限制**：理论假设（如Lipschitz连续、量化粒度）在实际深层模型中可能不易严格满足，实际部署时的误差行为可能不同于理论保证。
- **可扩展性未明确**：结论基于单层、单头自注意力，对于多层、多头、大规模VAR模型是否严格成立需进一步分析。
- **未讨论计算效率**：虽然理论表明表达能力充足，但未分析达到给定精度所需的网络宽度/深度，缺乏实际部署的复杂度指引。

（完）
