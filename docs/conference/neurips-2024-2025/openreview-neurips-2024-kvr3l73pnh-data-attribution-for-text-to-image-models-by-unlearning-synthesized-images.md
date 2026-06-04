---
title: Data Attribution for Text-to-Image Models by Unlearning Synthesized Images
title_zh: 通过遗忘合成图像实现文本到图像模型的数据归因
authors: "Sheng-Yu Wang, Aaron Hertzmann, Alexei A Efros, Jun-Yan Zhu, Richard Zhang"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=kVr3L73pNH"
tags: ["query:ce"]
score: 7.0
evidence: 文本到图像模型中的数据归因与机器遗忘
tldr: 本文提出通过模拟遗忘合成图像来实现文本到图像模型的数据归因。通过增加输出图像的训练损失同时避免灾难性遗忘其他概念，有效识别影响特定输出的训练图像。该方法避免了重复训练的计算开销，为模型可解释性和数据管理提供了新工具。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1430, \"height\": 1044, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1431, \"height\": 640, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 313, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1415, \"height\": 385, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1434, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1296, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1468, \"height\": 398, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1430, \"height\": 2049, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1430, \"height\": 1262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1436, \"height\": 618, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1437, \"height\": 642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1440, \"height\": 647, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1432, \"height\": 694, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1434, \"height\": 324, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-kvr3l73pnh/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1436, \"height\": 642, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-kvr3l73pnh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 526, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kvr3l73pnh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kvr3l73pnh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 944, \"height\": 266, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kvr3l73pnh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 293, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-kvr3l73pnh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1452, \"height\": 246, \"label\": \"Table\"}]"
motivation: 数据归因需要反复重新训练模型，计算成本极高，现有方法效率低。
method: 模拟遗忘合成图像，通过增大目标输出损失并保持其他概念不变来识别关键训练图像。
result: 该方法高效且准确地将生成图像归因于特定的训练样本。
conclusion: 为文本到图像模型提供了一种实用的数据归因方法，有助于理解模型行为和训练数据影响。
---

## Abstract
The goal of data attribution for text-to-image models is to identify the training images that most influence the generation of a new image. Influence is defined such that, for a given output, if a model is retrained from scratch without the most influential images, the model would fail to reproduce the same output. Unfortunately, directly searching for these influential images is computationally infeasible, since it would require repeatedly retraining models from scratch. In our work, we propose an efficient data attribution method by simulating unlearning the synthesized image. We achieve this by increasing the training loss on the output image, without catastrophic forgetting of other, unrelated concepts. We then identify training images with significant loss deviations after the unlearning process and label these as influential. We evaluate our method with a computationally intensive but "gold-standard" retraining from scratch and demonstrate our method's advantages over previous methods.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：文本到图像生成模型（如扩散模型）的训练数据庞大且不透明，如何准确识别对某个生成结果最具“影响力”的训练图像？这对于模型可解释性、版权归属、数据补偿等至关重要。
- **整体含义**：作者采用反事实定义——如果从训练集中移除某组图像并重新训练模型，模型将无法复现该生成结果，则这组图像就是有影响力的。然而，直接搜索这一组图像需要穷举所有子集并重新训练，计算上不可行。因此，需要一种高效且准确的近似方法。

## 2. 方法论：核心思想、关键技术细节

- **核心思想**：通过“机器遗忘”（unlearning）合成图像来模拟其从训练集中移除的效果，然后观察哪些训练图像的损失显著上升，从而识别出有影响力的训练图像。与传统的逐个移除训练样本不同，作者只对合成图像进行一次遗忘操作，再评估所有训练样本的损失变化。
- **关键技术细节**：
  - **遗忘合成图像**：使用弹性权重巩固（EWC）损失作为正则项，在增大合成图像损失的同时保持对其他概念的记忆。优化目标为：`L_unlearn(θ) = -L(ˆz, θ) + (N/2)(θ-θ0)^T F (θ-θ0)`，其中F是Fisher信息矩阵的对角近似。
  - **牛顿更新**：采用一步或多步牛顿更新：`θ ← θ + α N F^{-1} ∇L(ˆz, θ)`，仅需少数几步即可完成遗忘。
  - **参数选择**：只更新交叉注意力层中的键（W_k）和值（W_v）映射矩阵，而非全部参数，有效提升归因性能。
  - **归因分数**：对每个训练样本z，计算遗忘前后损失差：`τ(ˆz, z) = L(z, θ_{-ˆz}) - L(z, θ0)`，差值越大代表越有影响力。
- **算法流程**（文字说明）：
  1. 从预训练模型θ0出发，对查询合成图像ˆz执行带EWC正则的牛顿更新，得到遗忘模型θ_{-ˆz}。
  2. 计算每个训练样本在θ_{-ˆz}和θ0下的损失差。
  3. 按损失差降序排列，取Top-K作为最有影响力图像。

## 3. 实验设计

- **数据集/场景**：
  - **MSCOCO**（约118k图像）：用于“留K-out”反事实验证，可负担反复重新训练。从MSCOCO验证集选取110个生成查询，每个查询用文本提示生成。
  - **Customized Model Benchmark**：来自Wang et al. (2023)，包含20个定制模型（10个物体中心、10个艺术家风格），每个模型生成20张图像，共400个查询。该基准有真实标签（定制所用的样本图像）。
- **评估协议**：
  - **MSCOCO**：对每个查询，移除Top-K个图像后重新训练模型（K=500/1000/4000），测量DDPM损失增加∆L和生成图像偏差（MSE和CLIP相似度）。与随机移除、多种特征匹配方法（像素、CLIP、DINO、DINOv2）、以及影响函数方法（DataInf、TRAK、JourneyTRAK、D-TRAK）比较。
  - **Customized Model Benchmark**：作为检索任务，报告Recall@10和mAP。
- **对比方法**：包括随机基线、像素相似度、CLIP文本/图像特征、DINO、DINOv2、AbC微调特征（CLIP(AbC)和DINO(AbC)）、DataInf、TRAK、JourneyTRAK、D-TRAK。

## 4. 资源与算力

- 论文明确说明了计算资源：
  - **GPU型号**：NVIDIA A100 GPU。
  - **MSCOCO实验**：训练一个MSCOCO模型约16小时；评估所有训练图像损失约20小时；遗忘一个合成图像约2分钟。总GPU小时约77K小时。
  - **Customized Model Benchmark**：遗忘一个合成图像约2小时，跟踪训练图像损失约16小时。总GPU小时约36K小时。
- 未说明具体GPU数量，但可以推测使用了多卡并行。

## 5. 实验数量与充分性

- **实验数量**：
  - MSCOCO上：110个生成查询，每个查询测试K=500/1000/4000三种规模，对比13种方法（包括随机基线10次重复），并报告均值与标准误差。
  - 消融实验：考察有无EWC、不同权重子集（全部、注意层、交叉注意层、交叉注意KV）、不同更新步数（1步SGD、10步SGD、1步牛顿等）。
  - 空间局部归因演示（使用GroundingDINO提取对象框）。
  - Customized Model Benchmark上：400个查询，对比6种方法，并单独做消融（不同步数、权重子集、有无特殊标记V*等）。
- **充分性与公平性**：
  - 反事实验证是最直接的“黄金标准”，计算昂贵但可信。
  - 报告了标准误差，确保统计显著性。
  - 在MSCOCO上，所有方法共用相同训练和评估流程，公平比较。
  - 在Customized Model Benchmark上同样遵循原始评估标准。
  - 消融实验系统，关键设计选择均被覆盖。
- **判断**：实验充分、客观、公平。但限于计算资源，MSCOCO只测试了三个K值，未做更稠密的扫描（但随机基线做了稠密扫描作为参考）。

## 6. 主要结论与发现

- 提出的遗忘归因方法（Ours）在MSCOCO留K-out评估中，**在所有K值下均取得最优**的∆L和CLIP偏差，MSE偏差略低于D-TRAK但整体领先。移除仅0.42%的数据（500张）即可使生成结果严重退化，相当于随机移除48.6%数据的效果。
- 在Customized Model Benchmark上，物体中心模型上表现与AbC微调特征相当，**在艺术风格模型上显著超越所有基线**，说明本方法能更好地捕捉风格影响。
- 消融实验证明：
  - **EWC正则不可少**：直接最大化合成图像损失（无EWC）导致灾难性遗忘，归因性能退化为随机。
  - **只更新交叉注意KV层最佳**：全参数、注意力层、交叉注意层均不如仅更新KV。
  - **牛顿更新优于SGD**，且单步即可在MSCOCO上取得良好效果；在更大模型上需多步。
- 空间局部归因的演示表明方法可扩展至图像内部区域归因。

## 7. 优点

- **方法新颖且高效**：将机器遗忘反向应用于合成图像而非训练图像，只需一次遗忘即可评估所有训练样本，避免了逐个训练样本遗忘或重新训练。
- **理论连接清晰**：展示了与影响函数的联系，且方法更少近似（实际评估损失而非线性近似）。
- **反事实验证直接**：使用“留K-out重新训练”作为黄金标准，结果更具说服力。
- **鲁棒性**：EWC正则和参数选择显著提升性能，消融实验验证了每个组件的重要性。
- **可扩展性**：可处理不同规模模型（MSCOCO小模型和Stable Diffusion大模型），并可实现空间局部归因。

## 8. 不足与局限

- **计算效率瓶颈**：虽然遗忘本身高效（几秒到几分钟），但评估所有训练样本的损失需要多次前向传播，比基于点积检索的影响函数方法慢。论文也承认了这一点。
- **依赖Fisher信息矩阵估计**：需要额外的梯度计算来估计对角Fisher，尤其在大型数据集上可能耗时。
- **注意力机制假设**：对于没有交叉注意力的生成模型（如GANs），该方法无法直接应用，需要调整。
- **未考虑图像组间交互**：影响力分数是独立计算的，忽略了不同训练图像之间的协同或冗余效应。
- **实验覆盖有限**：仅在MSCOCO（~118k）和定制模型基准上测试，未在更大规模数据集（如LAION-5B）上进行反事实验证，因为计算成本过高。
- **D-TRAK在MSE指标上略有优势**：虽然本文方法在大多数指标上最佳，但D-TRAK在MSE偏差上表现更好，原因未完全解释。
- **局限性讨论**：作者在Section 6中明确指出了计算瓶颈、组间交互、以及未来细粒度归因（风格、结构、区域）的方向。

（完）
