---
title: Editable Concept Bottleneck Models
title_zh: 可编辑概念瓶颈模型
authors: "Lijie Hu, Chenyang Ren, Zhengyu Hu, Hongbin Lin, Cheng-Long Wang, Zhen Tan, Weimin Lyu, Jingfeng Zhang, Hui Xiong, Di Wang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=R0R3MRD8vh"
tags: ["query:ce"]
score: 6.0
evidence: 机器学习模型中的概念擦除
tldr: 论文针对概念瓶颈模型的概念编辑需求，提出可编辑概念瓶颈模型（ECBM），支持概念级别的数据移除，无需从头训练。该方法在多个数据集上验证了有效性和效率，为概念擦除提供了可扩展方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 807, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1562, \"height\": 495, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 629, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1438, \"height\": 532, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 629, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1690, \"height\": 571, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1608, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1607, \"height\": 558, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1608, \"height\": 554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1690, \"height\": 277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 601, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 603, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 601, \"height\": 406, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 602, \"height\": 407, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 604, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 602, \"height\": 431, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 606, \"height\": 410, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 602, \"height\": 408, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 612, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 739, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 603, \"height\": 631, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 754, \"height\": 569, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 746, \"height\": 564, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 538, \"height\": 630, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 408, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 587, \"height\": 448, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 481, \"height\": 548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 640, \"height\": 460, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-r0r3mrd8vh/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 698, \"height\": 702, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1691, \"height\": 485, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1392, \"height\": 1626, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 873, \"height\": 626, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 875, \"height\": 618, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 877, \"height\": 620, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 873, \"height\": 621, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 873, \"height\": 621, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 876, \"height\": 624, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 744, \"height\": 527, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 744, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 744, \"height\": 528, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-r0r3mrd8vh/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 742, \"height\": 527, \"label\": \"Table\"}]"
motivation: 现有概念瓶颈模型无法高效编辑已学概念。
method: 设计三种级别的数据移除机制，包括概念-标签级、概念级等。
result: 实现高效概念移除，保持模型性能。
conclusion: ECBM使概念瓶颈模型可编辑，适用于隐私修正等场景。
---

## Abstract
Concept Bottleneck Models (CBMs) have garnered much attention for their ability to elucidate the prediction process through a human-understandable concept layer. However, most previous studies focused on cases where the data, including concepts, are clean. In many scenarios, we always need to remove/insert some training data or new concepts from trained CBMs due to different reasons, such as privacy concerns, data mislabelling, spurious concepts, and concept annotation errors. Thus, the challenge of deriving efficient editable CBMs without retraining from scratch persists, particularly in large-scale applications. To address these challenges, we propose Editable Concept Bottleneck Models (ECBMs). Specifically, ECBMs support three different levels of data removal: concept-label-level, concept-level, and data-level. ECBMs enjoy mathematically rigorous closed-form approximations derived from influence functions that obviate the need for re-training. Experimental results demonstrate the efficiency and effectiveness of our ECBMs, affirming their adaptability within the realm of CBMs.

---

## 论文详细总结（自动生成）

# 详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：概念瓶颈模型（CBM）通过一个人类可理解的概念层来解释预测过程，增强了可解释性。然而，现有CBM假设训练数据（包括概念）是干净的。实际应用中常需要从已训练的CBM中删除/插入某些训练数据或新概念，原因包括隐私顾虑、数据错误标注、虚假概念、概念标注错误等。完全重新训练成本高昂，急需高效的无需重训练的编辑方法。
- **研究动机**：填补CBM在可编辑性方面的空白，提出一种能高效支持三种级别数据移除（概念-标签级、概念级、数据级）的模型，利用影响函数实现闭合形式近似，避免重训练。
- **整体含义**：ECBM使CBM变得可交互和可编辑，可应用于隐私删除、错误修正、概念更新等场景，提升CBM的实用性和适应性。

## 2. 论文提出的方法论

- **核心思想**：基于影响函数（Influence Function），对已训练的CBM进行编辑，近似重训练后的模型参数，不需要重新训练。针对CBM的两阶段结构（概念预测器g和标签预测器f），采用两阶段编辑策略。
- **关键技术细节**：
  - **概念-标签级编辑**：修改单个样本的某个错误概念标签。通过调整概念预测器的损失函数，利用影响函数计算参数变化量，近似得到新概念预测器；然后基于新概念预测器更新标签预测器。
  - **概念级编辑**：删除一组概念（如错误或虚假概念）。由于概念预测器输出维度改变，先通过插入零行映射到与原模型同维度的参数空间，再利用影响函数编辑，最后移除零行。
  - **数据级编辑**：完全删除某些样本。先编辑概念预测器，再通过中间标签预测器分两步编辑标签预测器。
  - **加速**：采用Eigenvalue-corrected Kronecker-Factored Approximate Curvature (EK-FAC) 方法近似Hessian矩阵，提升计算效率。
- **公式与算法**：论文给出了各编辑定理（Theorem 4.2-4.8）和相应的算法伪代码（Algorithm 1-3及EK-FAC版本Algorithm 6-8），主要涉及Hessian矩阵的逆、梯度计算和牛顿步更新。

## 3. 实验设计

- **数据集**：
  - OAI（X-ray Grading，膝关节炎数据集，36,369条数据，10个概念）
  - CUB（鸟类识别，11,788条数据，200类，112个二元属性）
  - CelebA（人脸属性，202,599张图片，40个二元属性，选取8个作为标签，32个作为概念）
- **任务场景**：三个编辑级别均进行测试。
- **基准方法**：
  - **Retrain**：完全重新训练（作为ground truth）
  - **CBM-IF**：直接应用影响函数定理的未加速版本
  - **ECBM**：使用EK-FAC加速的版本（本文方法）
- **评估指标**：F1分数（衡量模型性能）和运行时间（RT，分钟）。

## 4. 资源与算力

- 论文明确说明：实验使用了Intel Xeon CPU和一张RTX 3090 GPU。未提供具体训练时长细节，但给出了运行时间对比（如OAI数据集重训练需约297分钟，ECBM仅需约2.36分钟）。

## 5. 实验数量与充分性

- **主要实验组**：
  - 三个数据集 × 三个编辑级别，每个设置重复多次（如概念-标签级和数据级重复10次不同随机种子，概念级重复5次）。
  - 多比例编辑实验（1-10%样本删除、2-20个概念删除），分别在CUB数据集上进行（图2）。
  - 可解释性实验：分析最/最不重要概念的影响（图3），以及成员推断攻击（MIA）验证数据擦除效果（图4）。后续还有周期性编辑实验（图5-8）和可视化实验（图9-16）。
  - 附录中还包含噪声数据移除改善性能的实验、周期性编辑性能等。
- **充分性评价**：实验设计较为全面，覆盖了所有编辑级别、多个数据集、不同编辑比例，并进行了可解释性和隐私消除验证。对比了重训练和未加速版本，公平性较好。但缺少与现有模型编辑/遗忘方法的直接对比（如FT、SSD等），baseline仅包含自身变体，略显不足。

## 6. 论文的主要结论与发现

- ECBM能在显著降低运行时间（约22-30%的重训练时间）的同时，保持与重训练几乎相同的F1分数（差距通常在0.0025以内）。
- EK-FAC加速版（ECBM）相比未加速版（CBM-IF）F1分数更高、运行时间更短，证明Hessian近似引入正则化有益。
- 影响函数可用于识别重要概念，移除最/最不重要概念时F1变化与重训练一致。
- 成员推断攻击结果显示，ECBM能有效擦除特定样本的隐私信息（移除后RMIA分数更接近非成员）。
- 周期性编辑中ECBM性能稳定，即使10轮编辑后仍接近重训练结果。

## 7. 优点

- **方法创新**：首次将影响函数应用于CBM的编辑任务，并设计了三级别的编辑框架，具有理论严密性（给出近似误差界）。
- **计算高效**：通过EK-FAC加速，实际运行时间比重训练减少70%以上，适合大规模应用。
- **可解释性**：能评估概念重要性，支持可视化分析，增强模型透明度。
- **实用性**：可应对隐私擦除、错误纠正、动态概念更新等实际需求，且支持多次编辑。

## 8. 不足与局限

- **实验对比不足**：仅与自身重训练和未加速版本对比，未与现有模型编辑/遗忘方法（如机器遗忘、增量学习、参数高效微调等）进行比较，难以评估相对优势。
- **近似误差风险**：基于影响函数的近似本质上是线性的，当数据删除量较大或模型高度非线性时，误差可能增大。论文虽提供了理论误差界，但依赖于强凸性假设（实际非凸），边界可能较松。
- **标签预测器线性假设**：方法依赖于标签预测器为线性变换，扩展到非线性标签预测器可能需额外处理。
- **概念插入仅提及未展开**：论文说明方法可扩展至概念插入，但实验主要集中于删除，插入效果未验证。
- **数据集规模有限**：OAI和CUB规模中等，CelebA规模较大但计算资源有限，未测试更大规模模型（如ViT、LLM）下的效果。
- **隐私评估指标较简单**：仅使用RMIA，未采用更标准的成员推断攻击基准（如LiRA等），可能不够充分。

（完）
