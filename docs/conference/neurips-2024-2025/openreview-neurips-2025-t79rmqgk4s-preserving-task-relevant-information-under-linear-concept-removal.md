---
title: Preserving Task-Relevant Information Under Linear Concept Removal
title_zh: 在线性概念移除下保持任务相关信息
authors: "Floris Holstege, Shauli Ravfogel, Bram Wouters"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=t79rMQGk4S"
tags: ["query:ce"]
score: 7.0
evidence: 保持任务信息的线性概念移除
tldr: 神经网络中不希望的概念嵌入影响公平性和可解释性，现有后处理方法常破坏有用信号。本文提出SPLINCE，通过斜投影在移除线性概念可预测性的同时，精确保持与目标标签的协方差。理论上它是唯一满足该性质的解，且经验上在多个任务中优于现有方法，实现高效的概念净化。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1397, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1000, \"height\": 834, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1436, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1305, \"height\": 739, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1155, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1151, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 720, \"height\": 511, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 878, \"height\": 1010, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 994, \"height\": 1643, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 992, \"height\": 1642, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 944, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 997, \"height\": 832, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 981, \"height\": 813, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 987, \"height\": 821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-t79rmqgk4s/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1438, \"height\": 447, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-t79rmqgk4s/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 824, \"height\": 526, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t79rmqgk4s/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 683, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t79rmqgk4s/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 681, \"height\": 362, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t79rmqgk4s/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 986, \"height\": 566, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t79rmqgk4s/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 857, \"height\": 382, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t79rmqgk4s/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 765, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t79rmqgk4s/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1459, \"height\": 264, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-t79rmqgk4s/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 607, \"height\": 519, \"label\": \"Table\"}]"
motivation: 现有概念移除方法会退化有用信号，需要一种既能去除概念又能保留任务重要信息的方法。
method: 提出SPLINCE，使用斜投影同时移除敏感概念方向并保护目标标签的协方差。
result: 在多个基准上，SPLINCE在概念移除质量和任务性能保持上均超越现有方法。
conclusion: SPLINCE为线性概念移除提供了理论最优且实用的解决方案。
---

## Abstract
Modern neural networks often encode unwanted concepts alongside task-relevant information, leading to fairness and interpretability concerns. Existing post-hoc approaches can remove undesired concepts but often degrade useful signals. We introduce SPLINCE—Simultaneous Projection for LINear concept removal and Covariance prEservation—which eliminates sensitive concepts from representations while exactly preserving their covariance with a target label. SPLINCE achieves this via an oblique projection that ``splices out'' the unwanted direction yet protects important label correlations. Theoretically, it is the unique solution that removes linear concept predictability and maintains target covariance with minimal embedding distortion. Empirically, SPLINCE outperforms baselines on benchmarks such as Bias in Bios and Winobias, removing protected attributes while minimally damaging main-task information.

---

## 论文详细总结（自动生成）

# 论文《Preserving Task-Relevant Information Under Linear Concept Removal》详细中文总结

## 1. 核心问题与整体含义
- **研究动机**：深度神经网络（尤其是语言模型）的嵌入中常编码了不希望的概念（如性别标记），导致预测偏向和不公平。现有后处理概念移除方法（如 INLP、LEACE、SAL）虽然能线性擦除概念（实现线性守卫），但也会连带移除与目标任务相关的有用信息（例如在传记数据中，移除性别可能损害职业预测性能，因为某些职业与性别存在真实关联）。
- **核心问题**：如何在线性概念擦除的同时，最大程度保留对目标任务有用的信息？
- **整体含义**：提出一种新的斜投影方法 SPLINCE，在保证线性分类器无法预测敏感概念的前提下，精确保持嵌入与目标标签之间的协方差，从而在移除偏见时减少对任务性能的损害。

## 2. 方法论
- **核心思想**：构建一个斜投影矩阵 \(P\)，使其核包含跨协方差矩阵 \(\Sigma_{x,z}\)（概念方向），而其值域包含跨协方差矩阵 \(\Sigma_{x,y}\)（任务方向），从而同时满足：
  - 核约束：\(P\Sigma_{x,z}=0\)（线性守卫）
  - 值域约束：\(P\Sigma_{x,y}=\Sigma_{x,y}\)（保持任务协方差）
- **关键技术细节**：
  - 采用“白化-投影-去白化”的框架：定义白化矩阵 \(W=(\Sigma_{x,x}^{1/2})^+\)，先对数据白化。
  - 定义子空间：\(\mathcal{U}_\perp = \text{colsp}(W\Sigma_{x,z})\)，\(\mathcal{V} = \text{colsp}(W\Sigma_{x,y}) + \mathcal{U}_-\)，其中 \(\mathcal{U}_-\) 是 \(\mathcal{U}\) 中与两个子空间正交的部分。
  - 最优投影（定理1）：\(P^*_{\text{SPLINCE}} = W^+ V(U^T V)^{-1} U^T W\)，其中 \(U,V\) 分别是 \(\mathcal{U}\) 和 \(\mathcal{V}\) 的正交基。
  - 该投影是唯一在满足两个约束下最小化 \(\mathbb{E}\|Px - x\|^2_M\) 的解。
- **理论基础**：
  - 定理2：若重新训练最后一层且无正则化，则任何具有相同核的投影（如 LEACE、SAL）都会产生相同的预测，即范围选择不影响结果；但若存在正则化或不重新训练，则范围选择影响显著。
  - 附录A.3提供了SplinCE在特定情形（白化数据或高斯分布）下优于LEACE的保证。

## 3. 实验设计
- **数据集与场景**：
  - **分类任务（重新训练最后一层+正则化）**：
    - Bias in Bios（职业预测 vs 性别移除）
    - Multilingual Text Detoxification（毒性检测 vs 语言移除）
  - **语言建模（冻结最后一层）**：
    - 职业数据集（Llama2/3 等）：消除刻板印象（性别与职业的刻板关联）但保留事实性别信息
    - Winobias（共指消解）：移除提示的刻板性（pro-stereo vs anti-stereo），保持正确职业预测
  - **图像数据**：
    - CelebA（微笑 vs 眼镜）：定性展示不同投影对像素的影响
    - Waterbirds（鸟种 vs 背景）：附加实验
- **对比方法**：
  - Original（无干预）、LEACE、SAL（Spectral Attribute Removal）
  - 部分实验还对比了 DFR TR（深度特征重加权）和 GDRO（组分布鲁棒优化）
- **实验设置**：
  - 人为改变目标任务与概念之间的相关性（如控制 \(p(y|z)\) 从 0.5 到 0.9），测试方法在强相关下的鲁棒性。
  - 评估指标：总体准确率、最差组准确率（worst-group accuracy）、以及用于语言模型的系数 \(\exp(\hat{\beta})\) 等。
  - 多次重复（3~5 个随机种子），报告均值和 95%置信区间。

## 4. 资源与算力
- 文中未明确说明使用的 GPU 型号、数量、训练时长等具体算力信息。仅在附录提到“计算的资源相对适度”（modest compared to nowadays standards）。因此，无法提供详细的算力总结。

## 5. 实验数量与充分性
- **实验数量**：覆盖了**4 个主要数据集**（Bias in Bios、Multilingual Detox、Profession、Winobias），以及**2 个视觉数据集**（CelebA、Waterbirds），涉及**多种模型架构**（BERT、ME5、Llama2/3、Mistral、Phi-2）。包括：
  - 分类任务中改变相关性的实验（每个数据集 5~6 个条件）
  - 消融实验：不同正则化强度、不同干预层（多层投影）、不同模型
  - 附加实验：全量 Bias in Bios 数据集、与其他 OOD 方法对比
- **充分性与公平性**：
  - 提供了统计误差和显著性检验（如 t 检验）。
  - 对比方法均为最新且公开的基线（LEACE、SAL），实现合理。
  - 实验设计系统，控制变量清晰（相关性、正则化等）。
  - **不足**：视觉数据集（CelebA、Waterbirds）上 SPLINCE 表现明显弱于 NLP 数据集，作者承认这是未来工作方向；另外，未在多模态或跨模态场景下验证。

## 6. 主要结论与发现
- SPLINCE 在所有 NLP 分类和语言建模任务中，**在维持线性守卫的同时，显著优于 LEACE 和 SAL 保留任务相关信息**，尤其当概念与任务高度相关时。
- 在语言模型中，SPLINCE 能有效减少刻板印象依赖，同时**保留（甚至增强）事实性性别信息**（见表1、表5）。
- Winobias 实验中，SPLINCE 在多数模型上提高了共指消解准确率，特别是反刻板提示。
- 理论贡献：给出了唯一满足核和值域约束的最小失真投影（定理1），并揭示了重新训练时投影范围等效的条件（定理2）。
- 可视化实验（CelebA）直观显示 SPLINCE 能保留与任务（眼镜）相关的像素方向，而其他方法会模糊该特征。

## 7. 优点
- **理论严谨性**：给出了解的唯一性证明，并分析了范围选择的实际影响条件（正则化、不重新训练）。
- **算法简洁高效**：闭式解，无迭代训练，可即插即用。
- **实验设计系统**：人工控制相关性强度，量化方法在不同条件下的表现差异，对比全面。
- **可解释性**：通过几何图示（图1）和像素可视化（图4）直观说明投影效果。
- **代码开源**：提供官方实现与实验脚本，便于复现和扩展。

## 8. 不足与局限
- **视觉任务效果差**：在 CelebA 和 Waterbirds 数据集上，SPLINCE 不仅未能优于 LEACE，甚至低于原始无干预方法，作者指出这是未来研究重点。
- **多层干预性能下降**：在 Winobias 中对多层应用投影时，SPLINCE 的准确率随层数增加而下降（附录 B.4），可能因为高维协方差估计不稳定。
- **假设限制**：依赖线性子空间假设，仅保证线性守卫，无法处理非线性概念关联。
- **协方差保持可能不最优**：在非白化、非高斯的一般数据中，保持 \(\Sigma_{x,y}\) 不一定等价于保持任务性能（附录 A.3 仅给出特例保证）。
- **未探索跨模态场景**：如 CLIP 等多模态模型，协方差子空间可能不对齐。
- **未提供详细算力消耗**：影响可重复性评估。

（完）
