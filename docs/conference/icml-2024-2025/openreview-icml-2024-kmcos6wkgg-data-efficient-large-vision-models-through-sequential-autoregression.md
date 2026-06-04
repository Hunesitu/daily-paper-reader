---
title: Data-efficient Large Vision Models through Sequential Autoregression
title_zh: 通过顺序自回归实现数据高效的大规模视觉模型
authors: "Zhiwei Hao, Jianyuan Guo, Chengcheng Wang, Yehui Tang, Han Wu, Han Hu, Kai Han, Chang Xu"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=KmCoS6WkgG"
tags: ["query:ce"]
score: 6.0
evidence: 基于自回归的视觉模型
tldr: 针对当前自回归视觉模型依赖海量数据和参数的问题，本文提出一种高效的自回归视觉模型，仅需有限数据集即可训练。该模型通过顺序自回归方式处理视觉数据，在高层和低层视觉任务上均展现出良好性能，降低了自回归模型在视觉领域的应用门槛。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1746, \"height\": 643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 825, \"height\": 840, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1749, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1715, \"height\": 723, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 820, \"height\": 1246, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 792, \"height\": 1217, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1761, \"height\": 1596, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1752, \"height\": 1389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1750, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1763, \"height\": 1005, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1760, \"height\": 2035, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1758, \"height\": 2053, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1659, \"height\": 2197, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1657, \"height\": 2191, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1664, \"height\": 2181, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1769, \"height\": 1501, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-kmcos6wkgg/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1769, \"height\": 1376, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1766, \"height\": 276, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 864, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1771, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 855, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 823, \"height\": 225, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 859, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 949, \"height\": 207, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 774, \"height\": 458, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1661, \"height\": 279, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1236, \"height\": 206, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1761, \"height\": 442, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-kmcos6wkgg/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1765, \"height\": 240, \"label\": \"Table\"}]"
motivation: 解决自回归视觉模型过度依赖大规模数据和模型参数的问题。
method: 设计一种基于顺序自回归的高效视觉模型架构，在有限数据集上训练。
result: 该模型在多种视觉任务上取得有竞争力的性能，数据效率显著提升。
conclusion: 自回归视觉模型可以在数据受限的情况下有效学习，拓展了其应用场景。
---

## Abstract
Training general-purpose vision models on purely sequential visual data, eschewing linguistic inputs, has heralded a new frontier in visual understanding. These models are intended to not only comprehend but also seamlessly transit to out-of-domain tasks. However, current endeavors are hamstrung by an over-reliance on colossal models, exemplified by models with upwards of 3B parameters, and the necessity for an extensive corpus of visual data, often comprising a staggering 400B tokens. In this paper, we delve into the development of an efficient, autoregression-based vision model, innovatively architected to operate on a limited dataset. We meticulously demonstrate how this model achieves proficiency in a spectrum of visual tasks spanning both high-level and low-level semantic understanding during the testing phase. Our empirical evaluations underscore the model's agility in adapting to various tasks, heralding a significant reduction in the parameter footprint, and a marked decrease in training data requirements, thereby paving the way for more sustainable and accessible advancements in the field of generalist vision models. The code is available at https://github.com/ggjy/DeLVM.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：当前自回归视觉模型（如 LVM）虽然能处理多种视觉任务，但严重依赖超大规模模型（参数达 3B 以上）和海量数据（如 400B tokens），导致训练成本高、可持续性差。需要探索如何在有限数据和较小模型规模下，仍能训练出具备多任务能力的自回归视觉模型。
- **核心问题**：如何通过数据增强和知识蒸馏，在不增加模型参数量和总训练数据量的前提下，使自回归视觉模型在多种高层和低层视觉任务上取得良好性能，提升数据效率。
- **整体含义**：降低自回归视觉模型的应用门槛，推动更可持续、更易获取的通用视觉模型发展。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：基于自回归框架（类似 LVM），但引入两种关键技术——**数据增强** 和 **知识蒸馏**，以缓解数据长尾分布和模型参数冗余问题。
- **关键技术细节**：
  - **模型架构**：采用 VQGAN 将图像编码为 256 个离散 token（码本大小 8192，维度 64），然后使用因果 LLaMA 模型进行自回归预测（next token prediction）。支持基于视觉提示的推理（few-shot prompting）。
  - **数据增强（Data Augmentation）**：
    - 对于数据量少的任务（如人体姿态估计、图像去雨），对每个训练样本应用随机裁剪和随机翻转，生成多份增强版本（例如 10~100 倍），并与原始数据混合。
    - 在多头任务场景中，利用增强策略实现不同任务数据量的平衡，避免模型被数据量大的任务（如分割）主导。
  - **知识蒸馏（Knowledge Distillation）**：
    - 使用大模型（LLaMA-1B）作为教师，训练小模型（LLaMA-300M 或 LLaMA-80M）模仿教师的输出分布（采用 Hinton 等人提出的经典 KD 损失）。
    - 蒸馏过程仅在训练时消耗额外资源，推理时学生模型保持轻量。
  - **训练流程**：所有模型采用余弦学习率衰减、AdamW 优化器（lr=1.5e-4, weight decay=0.1），等效 batch size 固定为 262144 tokens，上下文长度 2048。

## 3. 实验设计
- **数据集**：
  - **SA-1B**（分割）：1100 万图像，实验中取 1%~10% 子集。
  - **COCO-Pose**（姿态估计）：25 万图像。
  - **Rain13K**（去雨）：约 1.37 万对图像。
  - **HDvila-100M & LAION-400M**（额外无标签数据，仅用于训练教师模型）。
- **评测基准**：
  - 图像分割：SA-1B 保留子集上计算交叉熵损失、准确率、困惑度。
  - 姿态估计：MPII 数据集（验证集）。
  - 去雨：Test2800 数据集。
  - 前景分割（zero-shot 和微调后）：Pascal-5i 数据集，使用 mIOU 指标。
  - ImageNet 分类（仅 LLaMA-80M）：替换 VQGAN 为 patch embedding，评估 top-1 准确率。
- **对比方法**：
  - 数据平衡策略：直接使用不平衡数据 vs 重采样平衡 vs 数据增强平衡。
  - 有无知识蒸馏：LLaMA-300M/80M 从零训练 vs 蒸馏训练。
  - 连续学习场景：数据不 shuffle 的情况。
  - 前景分割：与 BEiT、VQGAN、MAE-VQGAN、LVM-3B 等对比（但强调公平性限制）。

## 4. 资源与算力
- **GPU 型号**：NVIDIA A100（40GB），使用 8~16 块。
- **训练时长**：
  - LLaMA-1B（教师模型）：16 块 A100，约 324 小时。
  - LLaMA-300M：16 块 A100，约 126 小时。
  - LLaMA-300M + KD：16 块 A100，约 235 小时。
  - LLaMA-80M：8 块 A100，约 65 小时。
  - LLaMA-80M + KD：8 块 A100，约 82 小时。
- **显存占用**：大约 49~80 GB（取决于模型和是否使用教师）。
- 文中未明确提及总碳排放或电费，但提供了详细的硬件配置和时间。

## 5. 实验数量与充分性
- **实验组数**：论文包含约 6~7 组主要实验，加上消融和附录，总计约 10 组以上。
  - 单任务数据增强对比（SA-1B 不同比例、COCO-Pose 增强倍数）。
  - 多任务数据平衡策略对比（不平衡、重采样、增强）。
  - 单任务和多多任务知识蒸馏效果对比。
  - 前景分割（zero-shot 和 fine-tune）对比。
  - 连续学习/灾难性遗忘实验。
  - LLaMA-80M 在 ImageNet 分类上的额外验证。
  - 附录中包括视频预测、图像修复等更多结果。
- **充分性**：实验设计较为全面，覆盖了核心假设（数据增强可替代新数据、蒸馏提升小模型性能），并在多个任务上采用统一的评估指标（loss/准确率/困惑度/mIOU）。对比基线合理，消融实验充分（如不同平衡策略、不同 prompt 背景、学习率重置等）。但缺乏与其他 SOTA 通用视觉模型（如 Painter、Unified-IO）在相同条件下的直接对比（可能因任务定义和 tokenizer 不同难以公平比较），作者也承认这一点。

## 6. 主要结论与发现
- **数据增强** 在数据量少时效果明显，其增益与引入新数据类似；在多任务场景中，数据增强平衡比重采样平衡效果更好，且能避免模型被大数据任务主导。
- **知识蒸馏** 在自回归视觉模型上首次验证有效，能显著缩小大模型与小模型之间的性能差距（困惑度、准确率），且在多任务场景下同样有效。
- **灾难性遗忘**：当训练数据未 shuffle（按任务顺序训练）时，模型会遗忘之前学习的任务；而使用 shuffle 的离线训练可以处理多个任务。
- **前景分割**：通过微调后，蒸馏后的 LLaMA-300M 可在 Pascal-5i 上取得较好 mIOU（最高约 21.32%），但仍低于使用定制 VQGAN 的 LVM-3B（约 50%）。
- **LLaMA-80M** 经蒸馏后在 ImageNet 分类上取得 83.04% top-1 准确率，展示了紧凑模型兼顾生成与理解的能力。

## 7. 优点
- **方法简洁有效**：数据增强和知识蒸馏都是成熟技术，但在自回归视觉模型中首次系统研究，并证明其能大幅降低数据需求和模型规模。
- **实验设计严谨**：对比了不同数据平衡策略、不同蒸馏设置，并分析了连续学习场景，为后续研究提供清晰基准。
- **开源代码**：提供 GitHub 仓库，便于复现和拓展。
- **数据处理公平性**：使用现有 VQGAN（Laion 训练），避免在自定义数据上重新训练 tokenizer 带来的不公平优势，并指出该局限性。

## 8. 不足与局限
- **量化输出困难**：对于复杂任务（如目标检测、实例分割），从 VQGAN 解码的生成图像中难以精确提取结构化标注（如边界框、关键点坐标），需要后处理或额外映射。
- **任务覆盖有限**：模型仅在训练过的任务上有效（分割、姿态、去雨、视频帧预测、修复），对于未见任务（如深度估计、去雾、颜色化）表现不佳或产生错误输出（如混淆为分割）。
- **公平性对比受限**：前景分割实验中，由于 VQGAN 编码器与 LVM-3B 不同，mIOU 远低于 SOTA，作者不将其作为主要目标，但限制了该场景下的结果说服力。
- **数据增强固有风险**：可能引入过拟合（尤其是增强倍率过大时）、偏差或对特定对抗攻击的脆弱性，作者在影响声明中已提到。
- **算力仍较高**：即使使用 80M 模型，仍需 8 块 A100 训练 80+ 小时，对资源有限的研究组仍有门槛。
- **缺乏与其他通用模型对比**：未与 Painter、Unified-IO 等非自回归框架在相同多任务设置下比较，难以评估方法优劣的普适性。

（完）
