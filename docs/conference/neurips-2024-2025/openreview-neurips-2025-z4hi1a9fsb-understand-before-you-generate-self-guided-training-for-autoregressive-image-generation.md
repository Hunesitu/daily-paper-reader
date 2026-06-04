---
title: "Understand Before You Generate: Self-Guided Training for Autoregressive Image Generation"
title_zh: 先理解再生成：面向自回归图像生成的自引导训练
authors: "Xiaoyu Yue, ZiDong Wang, Yuqing Wang, Wenlong Zhang, Xihui Liu, Wanli Ouyang, LEI BAI, Luping Zhou"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=Z4hi1a9FsB"
tags: ["query:ce"]
score: 8.0
evidence: 自引导训练的自回归图像生成模型
tldr: 该论文首次系统研究了自回归图像生成中视觉语义学习的问题，指出局部依赖、语义不一致和空间不变性不足三个关键障碍；提出自监督训练目标以增强模型对图像高层语义的理解；实验表明该方法有效提升了生成质量，为自回归模型在视觉领域的应用提供了重要改进。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1399, \"height\": 395, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1228, \"height\": 559, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1451, \"height\": 423, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 447, \"height\": 523, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1429, \"height\": 945, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-z4hi1a9fsb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1412, \"height\": 638, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 997, \"height\": 617, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1460, \"height\": 927, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1449, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 482, \"height\": 222, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 440, \"height\": 218, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-z4hi1a9fsb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 470, \"height\": 225, \"label\": \"Table\"}]"
motivation: 现有自回归图像生成模型难以学习高层视觉语义，面临局部依赖、语义不一致和空间不变性不足等问题。
method: 提出自监督训练目标，引入对图像高层理解的引导，解决自回归模型在视觉域的下一个词预测范式中的关键缺陷。
result: 实验证明该方法能显著提升自回归图像生成的质量和语义一致性。
conclusion: 自回归模型通过自监督理解训练可以更好地进行图像生成，为视觉表示学习提供新思路。
---

## Abstract
Recent studies have demonstrated the importance of high-quality visual representations in image generation and have highlighted the limitations of generative models in image understanding. As a generative paradigm originally designed for natural language, autoregressive models face similar challenges. In this work, we present the first systematic investigation into the mechanisms of applying the next-token prediction paradigm to the visual domain. We identify three key properties that hinder the learning of high-level visual semantics: local and conditional dependence, inter-step semantic inconsistency, and spatial invariance deficiency. We show that these issues can be effectively addressed by introducing self-supervised objectives during training, leading to a novel training framework, Self-guided Training for AutoRegressive models (ST-AR). Without relying on pre-trained representation models, ST-AR significantly enhances the image understanding ability of autoregressive models and leads to improved generation quality. Specifically, ST-AR brings approximately 42% FID improvement for LlamaGen-L and 49% FID improvement for LlamaGen-XL, while maintaining the same sampling strategy.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 核心问题与整体含义
- **研究动机**：自回归图像生成模型（如 LlamaGen）在视觉领域应用时，面临与扩散模型类似的视觉表示学习瓶颈。论文首次系统研究了“下一个词预测”范式在视觉域中的机制，发现三个关键问题阻碍了高层视觉语义的学习：
  - **局部和条件依赖**：模型过度关注邻近 token 和首 token（条件 token），缺乏全局上下文感知。
  - **步间语义不一致**：不同生成步骤的语义信息波动，后期准确率反而下降，说明无法维持已学到的语义。
  - **空间不变性不足**：视觉 tokenizer（如 VQ‑GAN）对微小图像扰动敏感，导致相同对象的不同视角产生完全不同的 token，增加了模型学习难度。
- **整体含义**：增强自回归模型的图像理解能力是提升生成质量的关键。论文提出自引导训练框架 ST‑AR，在不依赖预训练表示模型的前提下，通过自监督目标来缓解上述问题，从而同时提升理解与生成性能。

## 2. 方法论
- **核心思想**：将自监督学习技术（掩码图像建模 + 对比学习）集成到自回归模型的 next‑token prediction 训练中，采用教师‑学生架构（EMA 更新教师权重）提供额外监督，不改变采样策略。
- **关键技术细节**：
  - **掩码图像建模（MIM）**：不在输入 token 上掩码，而是在注意力图上随机选择一定比例（默认 25%）的位置赋为 `-inf`，强制模型关注更广区域。通过余弦距离对齐学生与教师的最后层隐藏状态，损失记为 \( \mathcal{L}_{\text{MIM}} \)。
  - **步间对比损失（\( \mathcal{L}_{\text{step}} \)）**：对同一图像同一视图的不同 token 位置，拉近学生特征与教师特征，推远其他图像的对应特征，促进跨步语义一致性。
  - **视图间对比损失（\( \mathcal{L}_{\text{view}} \)）**：对同一图像的不同增强视图的相同 token 位置，拉近学生与教师特征，增强空间不变性。
  - **总损失**：\( \mathcal{L}_{\text{ST-AR}} = \mathcal{L}_{\text{AR}} + \alpha \mathcal{L}_{\text{MIM}} + \beta \frac{1}{2}(\mathcal{L}_{\text{step}} + \mathcal{L}_{\text{view}}) \)，其中 \( \alpha=1.0, \beta=0.5 \)。
  - **投影头（projector）**：在学生特征上附加 MLP 投影头（SimSiam 风格）以防止 collapse。
  - **采样策略**：推理时保持原始自回归采样，无需修改。

## 3. 实验设计
- **数据集**：ImageNet 256×256，类条件图像生成。使用与 LlamaGen 相同的 VQGAN tokenizer 预计算 token 序列（含 10‑crop 数据增强）。
- **基准与对比方法**：
  - 基架：LlamaGen‑B / L / XL（111M / 343M / 775M 参数）。
  - 对比方法类别：GAN（BigGAN, StyleGAN‑XL）、扩散模型（LDM‑4, DiT‑XL, SiT‑XL）、掩码自回归（MaskGIT）、并行自回归（VAR‑d16/d20）、因果自回归（VQGAN, LlamaGen 不同规模）。
- **评估指标**：
  - **图像理解**：线性探测 top‑1 准确率（使用第 6 层特征，训练 90 个 epoch）。
  - **图像生成**：FID、sFID、Inception Score、Precision、Recall（使用 ADM 评估套件），部分结果使用 classifier‑free guidance（CFG）。
- **主要实验结果**：
  - 线性探测：LlamaGen‑B 从 18.68% 提升至 45.27%（50 epoch），300 epoch 从 21.00% 提升至 55.23%。
  - 生成指标（无 CFG）：LlamaGen‑B 300 epoch FID 从 26.26 降至 18.44；LlamaGen‑L 从 13.45 降至 9.38；LlamaGen‑XL 50 epoch 从 19.42 降至 9.81，300 epoch 达到 6.20（优于 4 倍参数的 LlamaGen‑3B）。
  - 消融实验：验证三种损失各自的作用、掩码比例、对比损失深度、选取步数 K 的影响（见表 3‑6 及图 7）。

## 4. 资源与算力
- 文中仅说明训练超参数（学习率 1e‑4 per 256 batch size、AdamW、权重衰减 0.05、梯度裁剪 1.0、EMA decay 0.9999），并提及模型训练轮数（50 或 300 epoch），但**未明确说明使用的 GPU 型号、数量及具体训练时长**。因此无法给出精确的算力估计。

## 5. 实验数量与充分性
- **实验数量**：较为充分，包含：
  - 3 种模型规模（B/L/XL）在不同 epoch 下的对比（表 1‑2）。
  - 与其他范式（GAN、Diffusion、Masked AR、Parallel AR）的全面比较（表 2）。
  - 4 组消融实验：损失组合（表 3）、掩码比例（表 4）、对比损失深度（表 5）、选取步数 K（表 6）。
  - 可视化分析：注意力图（图 2、5、7）、线性探测跨步变化（图 4）。
- **充分性与公平性**：
  - 所有实验均基于相同数据、相同基架，控制变量严谨。
  - 消融实验覆盖了关键超参数，并给出了合理分析。
  - 评估指标同时涵盖理解与生成，视角全面。
  - 实验可重复性较好（公开代码、详细超参数）。

## 6. 主要结论与发现
- ST‑AR 显著增强了自回归模型的图像理解能力（线性探测准确率提升约 30+ 个百分点），并直接带来生成质量的飞跃（例如 LlamaGen‑XL 300 epoch FID 6.20，优于 4 倍参数的 LlamaGen‑3B）。
- 所提三个问题（局部依赖、步间不一致、空间不变性不足）确实是自回归视觉模型的瓶颈，通过 MIM 和对比学习可有效缓解。
- ST‑AR 无需依赖预训练表示模型，仅通过自引导训练实现性能提升，且不改变采样策略，保持了与 NLP 模型联合训练的可能性。

## 7. 优点
- **系统性分析**：首次深入剖析自回归视觉模型的内部机制，并总结三类关键问题，为后续研究提供理论基础。
- **方法简洁高效**：将成熟的 SSL 技术（MIM + 对比学习）巧妙地适配到自回归训练中，无需额外预训练模型。
- **兼容性强**：不改变采样策略，可直接应用于现有基于 next‑token prediction 的框架，易于推广到多模态场景。
- **实验充分**：涵盖不同规模、不同训练轮次、多种评估指标及大量消融，结果可信度高。
- **生成与理解双重提升**：既证明了模型理解能力的增强，又验证了生成质量的改善，逻辑闭环。

## 8. 不足与局限
- **训练成本增加**：引入了额外的 MIM 损失和对比损失，并且需要维护 EMA 教师网络，训练时间与显存消耗高于纯自回归基线（文中承认此点）。
- **实验覆盖有限**：
  - 仅评估了 ImageNet 类条件生成，未在文本条件生成（如 text‑to‑image）或更大规模数据集上验证。
  - 仅使用了 LlamaGen 系列，未在 VAR、MaskGIT 等其他自回归变体上测试。
- **潜在风险**：生成质量提升可能被滥用（如深度伪造），文中提及但未提供具体防护措施。
- **未报告统计误差**：所有结果均为单次运行，未提供标准差或置信区间，公平性依赖复现。
- **算力细节缺失**：未说明训练所需的具体 GPU 型号、数量及时间，不利于他人复现和成本评估。

（完）
