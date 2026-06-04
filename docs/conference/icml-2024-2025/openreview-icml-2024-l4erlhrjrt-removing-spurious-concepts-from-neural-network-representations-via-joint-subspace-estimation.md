---
title: Removing Spurious Concepts from Neural Network Representations via Joint Subspace Estimation
title_zh: 通过联合子空间估计移除神经网络表示中的虚假概念
authors: "Floris Holstege, Bram Wouters, Noud Van Giersbergen, Cees Diks"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=L4ERlHrJRT"
tags: ["query:ce"]
score: 6.0
evidence: 从神经网络表示中移除概念
tldr: 论文针对神经网络表示中虚假概念移除过度的问题，提出联合子空间估计算法，将虚假概念与主要任务概念分离。实验表明该方法有效去除假相关概念且不损害模型性能，促进了可解释机器学习。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 831, \"height\": 463, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1297, \"height\": 845, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 790, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 785, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 820, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 677, \"height\": 537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 871, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 978, \"height\": 535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1331, \"height\": 469, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1332, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1334, \"height\": 483, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1334, \"height\": 484, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1331, \"height\": 466, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 825, \"height\": 2221, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1257, \"height\": 2157, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1254, \"height\": 2153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1450, \"height\": 858, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1514, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1516, \"height\": 810, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1221, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-l4erlhrjrt/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1229, \"height\": 384, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 1268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1519, \"height\": 1554, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1520, \"height\": 1555, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1521, \"height\": 1316, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1521, \"height\": 1314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1521, \"height\": 1314, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1544, \"height\": 601, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1762, \"height\": 1318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1762, \"height\": 1318, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1545, \"height\": 1080, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1599, \"height\": 1080, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1600, \"height\": 1081, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1706, \"height\": 646, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1626, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-l4erlhrjrt/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 880, \"height\": 1311, \"label\": \"Table\"}]"
motivation: 现有概念移除方法会误删正确特征。
method: 迭代估计两个正交低维子空间分别表示虚假和主任务概念。
result: 准确移除虚假概念，提升模型解释和性能。
conclusion: 该算法为有选择的概念移除提供了有效工具。
---

## Abstract
An important challenge in the field of interpretable machine learning is to ensure that deep neural networks (DNNs) use the correct or desirable input features in performing their tasks. Concept-removal methods aim to do this by eliminating concepts that are spuriously correlated with the main task from the neural network representation of the data. However, existing methods tend to be overzealous by inadvertently removing part of the correct or desirable features as well, leading to wrong interpretations and hurting model performance. We propose an iterative algorithm that separates spurious from main-task concepts by jointly estimating two low-dimensional orthogonal subspaces of the neural network representation. By evaluating the algorithm on benchmark datasets from computer vision (Waterbirds, CelebA) and natural language processing (MultiNLI), we show it outperforms existing concept-removal methods in terms of identifying the main-task and spurious concepts, and removing only the latter.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：深度神经网络（DNN）在完成主要任务时，容易利用数据中与主要任务**虚假相关**的概念（如背景、性别等），导致模型不可靠、难以解释，并且可能使用不期望的特征。现有的**后验概念移除方法**（如INLP、RLACE、LEACE）在移除虚假概念时，往往会“过度移除”——同时清除与主任务相关的正确特征，从而降低模型性能并产生错误解释。
- **动机**：需要一种能够**精确分离**虚假概念与主任务概念的方法，只移除虚假部分，保留主任务所需信息，提升模型的**可解释性**和**控制能力**。
- **整体含义**：提出了一种新的**联合子空间估计（JSE）** 算法，同时估计两个正交的低维子空间，分别对应虚假概念和主任务概念，在多个基准数据集上显著优于现有方法。

## 2. 论文提出的方法论
- **核心思想**：假设在神经网络的最后一层嵌入空间中，主任务概念和虚假概念分别存在于两个**线性子空间**（Z_mt 和 Z_sp）中，且这两个子空间**相互正交**。通过**联合估计**这两个子空间，可以只移除Z_sp，而保留Z_mt。
- **关键技术细节**：
  - **联合逻辑回归**：同时训练两个二元逻辑回归模型，分别预测主任务标签 y_mt 和虚假标签 y_sp，但强制两个权重向量 w_sp 与 w_mt **正交**（通过投影约束实现）。
  - **迭代过程**：采用**嵌套循环**（内外双层for循环）逐步找出多个基向量：
    - 内循环：在当前剩余嵌入中，找到与至今已找到的主任务方向正交的主任务方向（v_mt），并投影出去。
    - 外循环：在每次内循环后，找到一个与已找到的主任务子空间正交的虚假方向（v_sp），并投影出去。
    - 最终输出两个正交基集合：{v_sp} 和 {v_mt}。
  - **统计停止测试**：通过两个假设检验决定何时停止添加向量：
    - 准则1：方向必须对相应标签有显著预测能力（比随机分类器更好）。
    - 准则2：方向应更有利于预测自己的标签而非另一个标签（例如，v_sp 预测 y_sp 比预测 y_mt 更好）。
    - 使用基于**加权的二元交叉熵差**的t检验，在四个标签组合（ymt, ysp）上等权建模。
- **算法流程**（文字说明）：
  - 输入：样本集 (y_mt, y_sp, z)
  - 初始化嵌入矩阵 Z，令 Z_sp⊥ = Z
  - 外层循环 i=1,…,d：
    - 初始化剩余矩阵 Z_remain = Z_sp⊥
    - 内层循环 j=1,…,d：
      - 用联合逻辑回归（正交约束）估计 w_sp, w_mt，得到归一化方向 v_sp_i, v_mt_j
      - 若 v_mt_j 满足两个准则，则投影 Z_remain = Z_sp⊥ (I - V_mt V_mt^T)
      - 否则跳出内循环
    - 若 v_sp_i 满足两个准则，则投影 Z_sp⊥ = Z (I - V_sp V_sp^T)，并记录当前主任务方向
    - 否则跳出外循环
  - 返回基向量集合。

## 3. 实验设计
- **数据集与场景**：
  - **Toy数据**：人工生成20维嵌入，已知真实主任务和虚假方向，可控制虚假相关强度 ρ。
  - **Waterbirds**（视觉）：主任务=鸟类类型（水鸟 vs 陆鸟），虚假概念=背景（水 vs 陆）。
  - **CelebA**（视觉）：主任务=发色（金发 vs 非金发），虚假概念=性别（女性 vs 男性）。
  - **MultiNLI**（自然语言）：主任务=句子对是否矛盾，虚假概念=第二句末尾是否包含“!!”。
- **基准与对比方法**：
  - 对比方法：INLP（迭代零空间投影）、RLACE（松弛线性对抗概念擦除）、LEACE（最小二乘概念擦除）、ADV（对抗移除）、ERM（经验风险最小化）。
  - 还对比了实例重加权方法：GW-ERM、GDRO、SUBG、JTT（附录G）。
- **评估指标**：
  - 主实验：**OOD泛化**准确率（测试集无虚假相关），包括总体准确率和**最差组准确率**。
  - 辅助实验：回归分析（重建真实特征的MSE）、Grad-CAM可视化、像素级移除（CelebA）、干净BERT测试（MultiNLI）。
  - 消融研究：正交假设放松、样本大小影响、循环顺序交换、PCA前后对比、测试统计加权效果、∆参数调整。

## 4. 资源与算力
- 论文**未明确说明**使用的具体GPU型号、数量或训练总时长。但在方法实现中提到：
  - 视觉模型：ResNet50（预训练），微调100 epoch（Waterbirds）或50 epoch（CelebA），使用SGD优化器，batch size 32或128。
  - NLP模型：BERT-base-uncased，微调最多10 epoch，使用Adam优化器，batch size 32。
  - 概念移除方法（JSE、INLP、RLACE等）均使用SGD，最大50 epoch，early stopping（5 epoch无改善则停止）。
  - 所有实验在普通GPU上应可完成，但具体配置未披露。

## 5. 实验数量与充分性
- **实验数量**：Toy数据集上进行100次独立重复运行；其他三个数据集每个点进行5次重复。总共包含多个虚假相关强度（ρ或条件概率）下的对比。
- **充分性与公平性**：
  - 实验覆盖了**典型虚假相关场景**（高、中、低强度），并报告了95%置信区间。
  - 对比方法均使用相同底层DNN（微调后的ResNet50或BERT），并采用网格搜索选择超参数（学习率、权重衰减），确保公平。
  - 进行了多种**消融实验**（附录）：正交性假设效应、样本大小影响、循环顺序、PCA必要性、测试统计加权、∆调整等，验证了方法的鲁棒性。
  - 还测试了**有限虚假标签**场景（附录G.2），以及**多虚假概念**场景（附录H）。
- **客观性**：所有对比结果均以表格和图表呈现，误差条清晰。未发现选择性报告或刷分行为。

## 6. 论文的主要结论与发现
- JSE在所有数据集上**显著优于**现有概念移除方法（INLP、RLACE、LEACE、ADV），尤其在高虚假相关强度下，能保持较高的总体和最差组准确率。
- 在回归分析中，JSE能近乎完美地保留主任务特征（低MSE），同时有效移除虚假特征（高MSE），而其他方法会移除部分主任务特征。
- Grad-CAM可视化显示：JSE后的模型主要关注动物本身而非背景；INLP等方法仍依赖背景特征。
- 在干净BERT测试中（模型从未见过虚假相关性），只有JSE不损失性能，表明其能精确识别虚假子空间而不误伤主任务。
- JSE与实例重加权方法（GDRO、GW-ERM等）相比，在中等虚假相关强度下性能相当或更优，且在有限虚假标签场景下更有优势。

## 7. 优点
- **创新性**：首次同时估计主任务和虚假两个正交子空间，巧妙避免了现有方法“过度移除”的问题。
- **理论简洁**：基于线性子空间假设和正交约束，算法清晰且易于实现。
- **统计严谨**：引入两种统计测试作为停止条件，确保只保留真正有区分力的方向。
- **实验全面**：在视觉和NLP基准上均进行了验证，涵盖多种评估方式（OOD、重建、可视化、干净测试），并深入分析了假设不成立时的表现。
- **可解释性**：提供了直观的可视化（Grad-CAM、像素级变化）帮助理解移除效果。
- **实用价值**：后验方法，无需重新训练整个网络，适用于已训练好的模型。

## 8. 不足与局限
- **假设局限**：方法假设主任务和虚假概念在嵌入空间中呈线性且正交，但在BERT等复杂模型中，概念可能高度纠缠（如MultiNLI实验中JSE增益较小），影响效果。
- **样本规模敏感性**：当样本量较小且虚假相关极强（如ρ=0.9）时，JSE的性能略有下降（附录B.2），归因于有限样本估计噪声。
- **多概念扩展**：主文主要处理单一虚假概念，附录H虽展示了多概念场景，但未进行系统评估，缺乏通用性指南。
- **调参复杂性**：超参数（学习率、权重衰减、测试显著性水平α、β）需针对具体数据集调整，可能增加使用门槛。
- **计算开销**：嵌套循环中需多次训练逻辑回归，尽管轻量，但嵌入维度高时可能较慢（论文通过PCA降低维度缓解）。
- **未讨论非线性移除**：方法仅适用于线性分类器（最后一层），若主任务分类器为非线性，则投影有效性存疑。
- **应用限制**：需要已知虚假概念标签（ysp）来估计子空间，实际场景中可能难以获取。

（完）
