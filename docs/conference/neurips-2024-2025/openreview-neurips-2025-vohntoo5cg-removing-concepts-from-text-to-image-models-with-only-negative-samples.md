---
title: Removing Concepts from Text-to-Image Models with Only Negative Samples
title_zh: 仅用负样本从文本到图像模型中移除概念
authors: "Hanwen Liu, Yadong MU"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=voHNTOO5CG"
tags: ["query:ce"]
score: 9.0
evidence: 仅用负样本从文本到图像模型中移除概念
tldr: 本文提出Clipout方法，仅需负样本即可从文本到图像模型中移除目标概念，无需重新训练。通过随机裁剪单元并使用对比目标，模型学会区分裁剪后的嵌入向量。理论分析和实验表明Clipout简单高效，优于现有方法。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-vohntoo5cg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 949, \"height\": 209, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vohntoo5cg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 381, \"height\": 244, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vohntoo5cg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1432, \"height\": 708, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vohntoo5cg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 727, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vohntoo5cg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1441, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-vohntoo5cg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1379, \"height\": 322, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-vohntoo5cg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1434, \"height\": 669, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vohntoo5cg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 792, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vohntoo5cg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 618, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vohntoo5cg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 552, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vohntoo5cg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 867, \"height\": 265, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vohntoo5cg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 726, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-vohntoo5cg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 673, \"height\": 223, \"label\": \"Table\"}]"
motivation: 现有概念移除方法通常需要重新训练或大量先验知识，开销大且效率低。
method: 提出Clipout，利用随机裁剪嵌入单元和对比目标，仅使用自举生成的负样本进行概念移除。
result: 实验证明Clipout在少量负样本下即可有效移除概念，且效率高于现有方法。
conclusion: 该方法提供了一种轻量级的概念移除方案，适用于版权和有害内容移除等场景。
---

## Abstract
This work introduces Clipout, a method for removing a target concept in pre-trained text-to-image models. By randomly clipping units from the learned data embedding and using a contrastive objective, models are encouraged to differentiate these clipped embedding vectors. Our goal is to remove private, copyrighted, inaccurate, or harmful concepts from trained models without the need for retraining. This is achieved by considering only negative samples and generating them in a bootstrapping-like manner, requiring minimal prior knowledge. Additionally, theoretical analyses are provided to further understand our proposed Clipout. Extensive experiments on text-to-image show that Clipout is simple yet highly effective and efficient compared with previous state-of-the-art approaches.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：预训练的文本到图像模型（如 Stable Diffusion）在生成高质量图像的同时，可能被滥用于生成涉及隐私、版权、不准确或有害的内容（如深度伪造、未经授权的艺术风格模仿、偏见或暴力内容）。现有机器遗忘方法要么需要重新设计模型架构（如分片重训练），要么需要对整个扩散模型进行端到端微调，效率低下且容易引入副作用。
- **整体含义**：本文提出 **Clipout**，一种仅利用负样本即可从预训练模型中移除特定概念的方法，无需重新训练或大量先验知识。通过解耦文本-图像系统中的基础构件（如 CLIP 文本编码器），仅对负责生成概念嵌入的部分进行遗忘，从而高效、精准地移除目标概念，同时最大程度保留其他概念的性能。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

### 核心思想
- **解耦遗忘**：将复杂的文本-图像系统解耦为独立构件（如 CLIP 编码器），仅对其中与概念嵌入生成相关的构件进行优化，其他部分（如扩散生成器）保持不变。
- **负样本对比学习**：提出“对比遗忘”范式，利用随机掩码生成同一目标嵌入的多个变体作为负样本，通过对比损失最大化这些变体之间的不相似性，从而破坏目标概念的表征。

### 关键技术细节
- **随机掩码**：给定目标概念的数据嵌入 \( z = f_\theta(x) \in \mathbb{R}^d \)，随机生成二进制掩码 \( m \in \{0,1\}^d \)（元素服从 Bernoulli(p) 分布，p 称为 clipout rate），得到掩码变体 \( z \odot m \)。
- **负样本对比损失**（公式 (1)）：
  \[
  \ell_\theta = \frac{1}{N} \sum_{i=1}^N -\log \frac{e^{\text{sim}(z \odot m_i, z \odot m_i)/\tau}}{\sum_{j=1}^N e^{\text{sim}(z \odot m_i, z \odot m_j)/\tau}}
  \]
  其中 \(\text{sim}(\cdot,\cdot)\) 为相似度函数（如余弦相似度），\(\tau\) 为温度参数，\(N\) 为 batch size。由于正样本（即自身对 \(z \odot m_i\) 与 \(z \odot m_i\)）被单独处理，实际优化目标退化为最小化不同掩码变体间的相似度。
- **自举生成负样本**：不需要外部数据集，仅通过随机掩码目标嵌入本身生成负样本，类似 bootstrapping。

### 理论分析
- **收敛性**（Proposition 3.3）：当 \(N \to \infty\)，损失收敛到 \(\mathbb{E}_{m_i}[\log \mathbb{E}_{m_j}[e^{\text{sim}/\tau}]] - 1/\tau\)，收敛速度为 \(O(1/\sqrt{N})\)（Corollary 3.5）。
- **对齐与均匀性**（Remark 3.7）：最大化不同掩码变体间的欧氏距离（即增大对齐损失），从而破坏目标概念的表征；同时通过 Lemma 3.10 和 Proposition 3.11 证明，当掩码后的归一化向量在超球面上均匀分布时，原始特征向量也趋于均匀分布，从而保持其他概念信息。

### 算法流程（Algorithm 1）
1. 输入：目标 prompt \(x\) 和编码器 \(f_\theta\)。
2. 循环迭代（例如 200 epochs）：
   - 计算目标嵌入 \(z = f_\theta(x)\)。
   - 从 \(z\) 采样 \(N\) 个掩码变体。
   - 按公式 (1) 计算对比损失。
   - 梯度下降更新 \(\theta\)。
3. 返回更新后的编码器参数 \(\theta^*\)，替换原编码器。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

### 数据集与场景
1. **个人概念（Personal Concept）**：
   - **数据集**：CelebA-HQ、VGGFace2。
   - **场景**：通过三种个性化方法（Textual Inversion、DreamBooth、LoRA）将特定人脸概念（如 sks person）注入 Stable Diffusion，再尝试移除该概念。
   - **benchmark**：测试目标概念（如 sks person）生成质量，并检查相似概念（如 male、female）是否受影响。
2. **预训练模型内置概念（Built-in Concept）**：
   - **数据集**：LAION-5B（Stable Diffusion 预训练数据子集）。
   - **场景**：移除有害概念，如“children with guns”和“a naked woman”，并观察相关无害概念（如 children at park、guns、woman）是否保留。
3. **风格迁移（Style Transfer）**：
   - 测试部分 prompt 匹配（如用短 prompt “Claude Monet inspired painting” 替代完整 prompt 进行遗忘，观察是否仍能防止风格模仿）。
4. **不适当图像提示基准（I2P）**：针对“Sexual”类别评估不安全内容生成比例。
5. **多样性测试**：从 MS-COCO 采样 50 个不同 prompt 验证整体生成质量。

### 对比方法
- **ASD** (Ablating Stable Diffusion)
- **ESD** (Erasing Stable Diffusion)
- **SLD** (Safe Latent Diffusion) —— 训练时安全指导方法，非严格机器遗忘
- **FSMG** (Anti-DreamBooth) —— 基于不可学习数据的防御方法
- **SA** (Selective Amnesia)
- **UCE** (Unified Concept Editing)

### 评估指标
- **CLIP Score**：生成图像与 prompt 的匹配度。
- **FDFR** (Face Detection Failure Rate)：人脸检测失败率，越高说明生成的人脸越少（成功遗忘）。
- **ISM** (Identity Score Matching)：生成图像与原始人脸的相似度，越低越好。
- **FID Score**：生成图像分布与参考分布的距离。

## 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点

- **GPU 型号**：NVIDIA A40 48GB GDDR6。
- **训练时长**：论文未明确给出总 GPU 小时数，但指出 Clipout 仅需 200 epochs，且每 epoch 仅优化编码器的少量参数，远快于 ASD 和 ESD（如图 5a 所示，Clipout 使用约 40-43 秒，而 ASD 和 ESD 需 500-900 秒）。由于未公开代码，无法获得精确算力消耗数据。
- **硬件配置**：PyTorch 1.13.1，CUDA 11.6，Ubuntu 系统。

## 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平

- **实验数量**：论文进行了多组实验，包括：
  - 3 种个性化方法 × 2 个数据集（CelebA-HQ、VGGFace2） × 多种对比方法（约 4 组 × 3 种方法 = 12 个主要实验），每个实验生成 128 张图像。
  - 2 个内置概念移除实验（children with guns、a naked woman）。
  - 2 个风格迁移实验（Claude Monet、Pablo Picasso）。
  - I2P 基准测试。
  - 消融实验：学习率与 clipout rate 的网格搜索（图 5c/d）。
  - 鲁棒性分析：使用 Ring-A-Bell 对抗 prompt 测试。
  - 额外实验：同义词测试（Chris Hemsworth / Thor）、多概念顺序遗忘、MS-COCO 多样性测试。
- **充分性**：实验覆盖了个人概念、预训练概念、风格、安全基准、消融、鲁棒性等多个维度，对比方法全面（包括训练型与训练无关型），指标多样。实验设计较为充分。
- **客观与公平性**：所有实验均基于公开数据集和官方实现，超参数按推荐设置，随机种子固定。未报告误差棒（如标准偏差），但采样 128 张图像并取平均值。对比方法（如 ASD、ESD）采用了它们的最佳配置。与 SLD 的比较存在场景差异（SLD 是推理时安全引导，非严格遗忘），但论文对此进行了说明。

## 6. 论文的主要结论与发现

1. **有效性**：Clipout 能够在各种场景下精准移除目标概念，同时最小化对其他概念的影响。例如，在 DreamBooth 实验中，目标概念的 CLIP Score 下降至 23.23（远低于基线），而相似概念（female）仅下降 0.10；FDFR 差分达 0.91（基线最高仅 0.42）。
2. **效率**：Clipout 仅需 40-43 秒完成遗忘，GPU 内存约 10473 MiB，远优于 ASD（>900 秒，37311 MiB）和 ESD（>500 秒，13701 MiB）。
3. **理论支撑**：通过收敛性、对齐与均匀性分析，解释了为什么破坏掩码变体间相似度能有效遗忘目标概念，并保持了其他概念的均匀分布。
4. **鲁棒性**：即使在对抗 prompt（Ring-A-Bell）下，目标概念的 FDFR 仍保持 0.58（清洁 prompt 下 0.94），而良性概念几乎不受影响（0.03）。

## 7. 优点：方法或实验设计上有哪些亮点

- **仅需负样本**：无需正样本或锚定概念，仅通过自举掩码生成负样本，极大简化了遗忘流程。
- **解耦遗忘**：只修改文本编码器，不触碰生成器，高效且可迁移（适用于任何使用 CLIP 编码器的模型）。
- **理论严谨**：提供了收敛性、对齐与均匀性的数学分析，并证明了最优条件下的特征分布性质（Proposition 3.11）。
- **实验全面**：覆盖个人概念（多种个性化方法）、预训练概念、风格、安全基准、对抗鲁棒性、消融、多样性验证，对比基线多样。
- **效率极高**：时间与内存消耗远小于现有训练型方法，适合实际部署。
- **实现简单**：算法流程直白（Algorithm 1），仅需几行伪代码即可实现。

## 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等

- **超参数敏感**：性能高度依赖学习率和 clipout rate 的选择（图 5c/d），虽然 clipout rate 在一定范围内不敏感，但学习率过大会导致所有概念退化。
- **遗忘方向不可控**：由于仅使用负样本且无正样本引导，遗忘后的目标概念生成图像往往退化为随机风景或纹理，缺乏可控性（如无法指定替代内容）。
- **未提供误差棒**：所有数值结果均基于 128 张随机生成图像的平均值，未报告方差或置信区间，统计显著性不足。
- **基准差异**：与 SLD、FSMG 的比较需注意场景差异（SLD 为推理时安全引导，FSMG 为事前防御，非严格事后遗忘）。
- **潜在偏差风险**：如论文“Broader Impact”部分指出，概念移除可能被用于审查文化意义内容或引入偏见；此外，可能被用于移除模型水印，导致版权争议。
- **实验覆盖局限**：仅测试了 Stable Diffusion 2.1，未扩展到其他文本到图像模型（如 DALL-E、Midjourney）。未评估大规模连续遗忘（多个概念的联合遗忘）效率。
- **计算资源未详细公开**：未提供总 GPU 小时数，复现成本未知。

（完）
