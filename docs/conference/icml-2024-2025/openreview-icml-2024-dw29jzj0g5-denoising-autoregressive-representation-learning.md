---
title: Denoising Autoregressive Representation Learning
title_zh: 去噪自回归表示学习
authors: "Yazhe Li, Jorg Bornschein, Ting Chen"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=dW29JZj0G5"
tags: ["query:ce"]
score: 6.0
evidence: 图像的自回归表示学习
tldr: 本文探索自回归生成式视觉表示学习方法。DARL采用仅解码器Transformer自回归预测图像块，并用去噪补丁解码器替换MSE损失以增强生成能力。通过定制噪声调度和更长的训练，学习到的表示接近最先进的掩码预测模型，表明自回归目标也可作为有效的视觉表示学习范式。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1699, \"height\": 600, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 836, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 857, \"height\": 350, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 763, \"height\": 259, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 740, \"height\": 253, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 754, \"height\": 262, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 774, \"height\": 970, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1767, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1122, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1452, \"height\": 412, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1248, \"height\": 684, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1405, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1248, \"height\": 681, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1403, \"height\": 480, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-dw29jzj0g5/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1521, \"height\": 2149, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 835, \"height\": 446, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 846, \"height\": 370, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 615, \"height\": 175, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 877, \"height\": 457, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1764, \"height\": 406, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 609, \"height\": 173, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 827, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 618, \"height\": 624, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 680, \"height\": 836, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 638, \"height\": 755, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1050, \"height\": 701, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1203, \"height\": 732, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 518, \"height\": 627, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 642, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 671, \"height\": 372, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-dw29jzj0g5/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1067, \"height\": 200, \"label\": \"Table\"}]"
motivation: 探索自回归生成目标在视觉表示学习中的潜力。
method: 使用解码器Transformer自回归预测图像块，并通过去噪补丁解码器优化。
result: DARL学到的表示在多个下游任务上接近掩码预测方法。
conclusion: 自回归成对损失结合去噪目标能有效学习视觉表示。
---

## Abstract
In this paper, we explore a new generative approach for learning visual representations. Our method, DARL, employs a decoder-only Transformer to predict image patches autoregressively. We find that training with Mean Squared Error (MSE) alone leads to strong representations. To enhance the image generation ability, we replace the MSE loss with the diffusion objective by using a denoising patch decoder. We show that the learned representation can be improved by using tailored noise schedules and longer training in larger models. Notably, the optimal schedule differs significantly from the typical ones used in standard image diffusion models. Overall, despite its simple architecture, DARL delivers performance remarkably close to state-of-the-art masked prediction models under the fine-tuning protocol. This marks an important step towards a unified model capable of both visual perception and generation, effectively combining the strengths of autoregressive and denoising diffusion models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：在视觉领域，表示学习和图像生成通常采用不同的技术路线（对比学习、掩码建模用于表示学习；扩散模型、自回归生成用于图像生成）。本文希望探索一种**统一模型**，既能学习高质量视觉表示，又能具备图像生成能力，从而结合自回归模型和去噪扩散模型的优势。
- **核心问题**：生成式预训练（如自回归下一个图像块预测）在视觉表示学习上能否达到与主流掩码预测方法（如MAE）相当的性能？如何通过引入扩散目标进一步提升表示质量和生成能力？
- **整体含义**：提出DARL（Denoising Autoregressive Representation Learning），证明简单的自回归目标（MSE损失）也能学到强表示，结合去噪补丁解码器后性能接近SOTA掩码预测模型，向统一感知与生成模型迈出重要一步。

## 2. 论文提出的方法论
### 2.1 核心思想
- 采用**仅解码器Transformer**（Vision Transformer + 因果注意力掩码）对图像补丁序列进行自回归预测。使用**2D旋转位置编码（2D RoPE）** 引入空间相对位置偏置。
- 基础训练目标为**均方误差（MSE）**；为增强生成能力，将MSE替换为**扩散目标**，并引入一个**去噪补丁解码器**（一个Transformer块），该解码器接收骨干网络输出和噪声补丁嵌入，预测原始干净补丁。
- 噪声调度使用**Beta分布**直接采样γ（噪声强度参数），通过调整a、b控制噪声水平分布。

### 2.2 关键技术细节
- **架构**：图像分割为非重叠补丁→线性投影→按光栅扫描顺序排列→添加序列开始token→输入因果注意力ViT。
- **训练目标**：
  - MSE损失：\( L_{MSE} \propto \sum_t \|f(x_{<t}) - x_t\|^2 \)
  - 扩散目标：优化变分下界（ELBO），简化损失为预测原始补丁\(x_0\)的MSE：\( L_{SIMP} = \mathbb{E}_{\gamma \sim B, \epsilon} [\|x_0 - g(x_s^\gamma, f(x_{<t}))\|^2] \)
- **去噪过程**：每个补丁独立加噪，使用DDPM前向过程，反向过程预测原始补丁（而非噪声），实验表明预测原始补丁优于预测噪声。
- **2D RoPE**：将RoPE扩展到二维，对x、y坐标分别应用旋转矩阵，分解实现，显著提升因果Transformer在图像上的表现，特别是分辨率变化时泛化能力强。

### 2.3 算法流程（文字说明）
1. 将图像分割为补丁，按光栅扫描顺序排列，添加起始token。
2. 在训练时，对于扩散目标：对每个补丁独立采样噪声强度γ（从Beta分布），生成加了不同噪声的补丁版本。
3. 骨干Transformer（因果注意力）处理序列，输出每个位置的上下文表示\(f(x_{<t})\)。
4. 去噪补丁解码器接收\(f(x_{<t})\)和噪声补丁\(x_s^\gamma\)，预测干净补丁\(x_0\)。
5. 优化预测补丁与原始补丁之间的MSE（简化扩散损失）。
6. 微调时，移除因果注意力掩码，使用最后一层的输出（最后补丁）作为全局描述符，进行分类或检测任务。

## 3. 实验设计
### 3.1 数据集与基准
- **预训练**：ImageNet-1K（约128万张图像）。
- **下游任务**：
  - 分类：ImageNet top-1准确率。
  - 迁移学习：VTAB基准（19个分类任务，分Natural、Specialized、Structured三大类）。
  - 目标检测与分割：COCO数据集，使用ViTDet + Cascade Mask R-CNN。

### 3.2 对比方法
- **对比学习**：DINO、MoCo v3。
- **掩码预测**：BEiT、MAE。
- **生成式预训练**：Image-GPT。
- 所有方法均使用标准ViT骨干（ViT-B、ViT-L、ViT-H），公平比较。

## 4. 资源与算力
- **未明确说明具体GPU型号、数量、总训练时长**。仅提到预训练使用AdamW优化器，batch size 4096，学习率余弦衰减，40 epoch warm-up。文中指出在800 epoch预训练下使用ViT-L16、ViT-H14等规模。按常规推测，需要大量GPU资源（如TPU或A100集群），但作者未提供详细算力统计。

## 5. 实验数量与充分性
### 5.1 实验数量
- **消融实验**：涵盖位置编码（5种）、补丁解码器（多种层数、有无γ条件）、读出头（因果/非因果、均值/最后一token）、噪声调度（参数a、b扫描）、训练时长（100/200/400/800 epoch）、补丁大小（16/28/32/56）、目标预测（预测噪声vs预测原图）、补丁排序（光栅、嵌套光栅、轮询、随机排序）。
- **主实验**：ImageNet分类（ViT-B/L/H）、VTAB迁移（19个数据集）、COCO检测分割。
- **线性评估**和**生成样本**展示。
- 总计超过20组不同设置。

### 5.2 充分性与公平性
- **充分性**：消融实验覆盖了架构、目标、调度、规模等关键维度，较为全面。
- **公平性**：与MAE等对比时使用相同骨干、相同微调超参（如RandAug、Mixup、layer-wise lr decay等），并指出使用了与MAE一致的初始化方案。与MAE的差距仅约1%。
- **偏差风险**：所有预训练仅在ImageNet上进行，未在更大数据集（如JFT-300M）上验证；VTAB的Structured类性能明显弱于其他类，表明对结构理解仍有不足。

## 6. 论文的主要结论与发现
- **自回归生成目标（MSE）** 在视觉表示学习上表现强劲，接近SOTA掩码预测模型。
- **扩散目标** 结合定制噪声调度（偏向高噪声水平，a=0.03, b=1）可以在更长训练下提升表示质量，尤其是大模型。
- **2D RoPE** 对于因果Transformer至关重要，显著优于绝对/可学习/1D RoPE，且在高分辨率下泛化良好。
- **固定光栅扫描顺序**接近最优，嵌套光栅略好，随机排序无优势且需要更长训练。
- **生成能力**：DARL具备条件图像生成能力（如图7所示），但生成与高层抽象存在容量竞争（最优噪声调度与标准扩散调度不同）。

## 7. 优点
- **简洁统一**：使用简单的解码器Transformer，结合自回归和扩散，无需复杂设计（如特殊token、瓶颈）。
- **性能接近SOTA**：在ImageNet上ViT-L/H达到84.9%/85.9%（扩散），与MAE差距约1%，显著优于对比方法。
- **迁移能力强**：在VTAB Natural和Specialized上超越监督预训练，在COCO检测分割上接近MAE。
- **深入分析**：对噪声调度、补丁大小、目标预测形式、补丁排序等进行了系统消融，提供了有价值的洞见。
- **实现贡献**：提出2D RoPE在图像Transformer中的应用，证明了其有效性。

## 8. 不足与局限
- **算力未公开**：缺乏详细计算资源说明，复现成本未知。
- **实验覆盖有限**：仅使用ImageNet预训练，未在更大或更多样化数据集（如JFT、LAION）上验证；VTAB Structured类性能差，表明对结构/空间关系理解不足。
- **生成能力尚未充分挖掘**：生成的样本（64×64分辨率）质量有限，论文主要关注表示学习，生成仅作为附带优势。
- **容量竞争**：生成与表示学习的冲突导致噪声调度偏好迥异，未来需更大模型或改进架构以缓解。
- **微调依赖**：由于缺乏瓶颈，表示分布式更强，线性评估不如掩码模型，且需要移除因果掩码才能达到最佳性能（非因果Transformer有更好归纳偏置）。
- **COCO实验**：ViTDet设计针对监督/编码器模型，对生成式预训练可能次优，论文承认这一点。

（完）
