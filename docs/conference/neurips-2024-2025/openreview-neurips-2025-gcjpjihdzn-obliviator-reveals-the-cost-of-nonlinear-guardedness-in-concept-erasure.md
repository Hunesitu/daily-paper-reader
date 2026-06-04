---
title: Obliviator Reveals the Cost of Nonlinear Guardedness in Concept Erasure
title_zh: Obliviator揭示概念擦除中非线性防护的代价
authors: "Ramin Akbari, Milad Afshari, Vishnu Boddeti"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=GcjpjIHDZn"
tags: ["query:ce"]
score: 9.0
evidence: 处理非线性依赖的事后概念擦除方法Obliviator
tldr: 本文提出Obliviator，一种事后概念擦除方法。现有方法无法捕获表示与不希望属性之间的非线性统计依赖，且缺乏对擦除代价的研究。Obliviator通过捕获所有非线性依赖实现更彻底的擦除，同时揭示了效用与擦除之间的权衡轨迹。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1131, \"height\": 247, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1428, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1411, \"height\": 401, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1443, \"height\": 415, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 809, \"height\": 430, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1443, \"height\": 409, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1440, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 698, \"height\": 390, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 992, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 677, \"height\": 391, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 675, \"height\": 389, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1226, \"height\": 470, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-gcjpjihdzn/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 677, \"height\": 389, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 981, \"height\": 304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1447, \"height\": 463, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1441, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1330, \"height\": 194, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1453, \"height\": 283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1436, \"height\": 152, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1380, \"height\": 178, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1100, \"height\": 244, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1054, \"height\": 664, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 739, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-gcjpjihdzn/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 552, \"height\": 176, \"label\": \"Table\"}]"
motivation: 现有概念擦除方法对非线性攻击脆弱，且擦除过程中的效用损失轨迹未知。
method: Obliviator通过建模非线性统计依赖实现完全擦除，并分析擦除代价。
result: 更有效地抵御非线性攻击，并量化了效用-擦除权衡。
conclusion: Obliviator为概念擦除提供了更强健的非线性防护框架。
---

## Abstract
Concept erasure aims to remove unwanted attributes, such as social or demographic factors, from learned representations, while preserving their task-relevant utility. While the goal of concept erasure is protection against all adversaries, existing methods remain vulnerable to nonlinear ones. This vulnerability arises from their failure to fully capture the complex, nonlinear statistical dependencies between learned representations and unwanted attributes. Moreover, although the existence of a trade-off between utility and erasure is expected, its progression during the erasure process, i.e., the cost of erasure, remains unstudied. In this work, we introduce Obliviator, a post-hoc erasure method designed to fully capture nonlinear statistical dependencies. We formulate erasure from a functional perspective, leading to an optimization problem involving a composition of kernels that lacks a closed-form solution. Instead of solving this problem in a single shot, we adopt an iterative approach that gradually morphs the feature space to achieve a more utility-preserving erasure. Unlike prior methods, Obliviator guards unwanted attribute against nonlinear adversaries. Our gradual approach quantifies the cost of nonlinear guardedness and reveals the dynamics between attribute protection and utility-preservation over the course of erasure. The utility-erasure trade-off curves obtained by Obliviator outperform the baselines and demonstrate its strong generalizability: its erasure becomes more utility-preserving when applied to the better-disentangled representations learned by more capable models.

---

## 论文详细总结（自动生成）

# 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：预训练语言模型（PLMs）在广泛任务中表现出色，但常编码不希望的社会或人口统计属性（如性别、种族），导致偏见和不公平预测。概念擦除旨在从表示中移除这些不想要的属性，同时保留任务相关的有用信息。
- **核心问题**：现有概念擦除方法无法完全移除不想要的属性，尤其是面对非线性攻击者时仍存在脆弱性。这是因为它们未能充分捕获表示与不想要属性之间复杂的非线性统计依赖。此外，即使预期存在效用与擦除之间的权衡，但在擦除过程中这种权衡的动态演变（即擦除代价）尚未被研究。
- **整体贡献**：论文提出Obliviator，一种事后（post-hoc）概念擦除方法，旨在完全捕获非线性统计依赖，并通过迭代方法逐步变形特征空间，实现更保效的擦除，同时揭示了效用-擦除权衡的动态过程。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：从函数视角刻画擦除问题，将擦除表述为最小化表示与不想要属性之间的统计依赖（使用希尔伯特-施密特独立性准则，HSIC），同时保留任务相关信息。将嵌套优化问题转化为双目标优化，并采用两步迭代过程求解。
- **关键技术细节**：
  - **RKHS与HSIC**：利用再生核希尔伯特空间（RKHS）捕获非线性依赖，HSIC作为独立性度量，具有闭式经验估计：HSIC = (1/n²) trace(K H L H)，其中K、L为核矩阵，H为中心化矩阵。
  - **两步迭代过程**：
    1. **通过RKHS施加独立性（编码器训练）**：训练一个编码器ε(θ; X)，最小化输出Z与敏感属性S的HSIC，同时最大化Z与目标任务Y、原始表示X及当前输入Xi的HSIC（作为效用保留代理）。损失函数见公式(8)。
    2. **RKHS解缠（特征空间对齐）**：求解一个约束特征值问题（公式(11)），找到函数f（编码方向）最大化Z与X、Xi、Y的对齐，同时保持与S正交，从而在下一迭代前重新调整表示，使任务相关信息更易获取。输出为Xi+1 = Lzi QV。
- **算法流程**：初始化原始表示X0，对每个迭代i：训练编码器ε_i（用损失(8)）→ 得到Z_i → 求解特征值问题(11) → 用选出的特征向量变换Z_i得到X_{i+1} → 重复直至S预测精度降至随机水平。

## 3. 实验设计：数据集、场景、基准、对比方法

- **数据集**：
  - **BIAS IN BIOS**：目标职业（28类），敏感属性性别。
  - **DIAL-SENTIMENT**：目标情感（二类），敏感属性种族。
  - **DIAL-MENTION**：目标是否提及他人（二类），敏感属性种族。
- **评估场景**：四种组合：1) 微调+监督擦除（使用Y标签），2) 冻结+无监督擦除，3) 冻结+监督擦除，4) 微调+无监督擦除。此外还包括偏置采样控制实验（改变种族比例）。
- **对比方法**：
  - 线性/迭代：INLP
  - 非线性：kSAL、FaRM、KRaM、AdS（其中AdS和FaRM需微调PLM）
  - 随机猜测作为基准线。
- **评估指标**：通过训练多种非线性探针（RBF核SVM及多层MLP）报告最高泄露准确率；目标任务准确率。绘制效用-擦除权衡曲线（多独立运行）。

## 4. 资源与算力

- **论文中明确说明**：训练在单个NVIDIA RTX A6000 GPU上进行。使用PyTorch和cuML库。对于每个实验，计算了时间和内存复杂度（见附录B.4），例如BERT编码器平均每步约177ms，DeepSeek约220ms；总时间从几分钟到几小时不等（如BIAS IN BIOS冻结无监督约483秒到DeepSeek监督约1716秒）。Hyperparameters参见附录表2。

## 5. 实验数量与充分性

- **实验数量**：涉及三个数据集、四种语言模型（BERT、GPT-2、DeepSeek-LLM-7B-Chat、Llama-3.2-1B-Instruct）、四种实验场景（微调/冻结 × 监督/无监督）、偏置采样控制实验、公平性实验（Demographic Parity、Gap RMS）、超参数敏感性分析（γ和τ）、单步vs多步对比、不同探针网络消融。每次实验报告多个独立运行（通常5次）。
- **充分性与客观性**：实验设计较为全面，涵盖了不同模型、不同擦除方案、不同数据集，并考虑了多种探针网络以确保评估鲁棒性。公平性结果也展示了实际影响。对比方法包括常见的SOTA方法，且Obliviator在几乎所有权衡曲线上都表现更优。论文承认未测试所有可能配置，但已在关键基准上充分验证。

## 6. 论文的主要结论与发现

- **Obliviator实现了非线性防护的概念擦除**：通过直接最小化HSIC到零，达到统计独立，从而完全防御非线性攻击者。而现有方法（如FaRM、KRaM、kSAL）无法完全擦除，尤其在微调表示上存在12-14%的泄露。
- **效用-擦除权衡曲线揭示动态**：Obliviator在所有设置中在每个擦除水平上都优于基线，获得更高的任务准确率。监督擦除优于无监督擦除；微调表示比冻结表示更容易保留效用。
- **泛化性**：对更先进的PLM（如DeepSeek、LLaMa）应用时，Obliviator的擦除更保效，表明模型本身解缠越好，擦除越有效。
- **偏置采样恶化权衡**：数据倾斜导致HSIC估计偏差，使权衡更显著。
- **公平性指标提升**：擦除后Demographic Parity和Gap RMS均改善，尤其DeepSeek比BERT更具优势。

## 7. 优点：方法或实验设计上的亮点

- **方法创新**：
  - 首次提出迭代两步过程结合HSIC最小化和RKHS解缠，有效处理非线性依赖。
  - 利用HSIC的闭式估计和RKHS特征值问题，优化稳定可控。
  - 可灵活支持监督/无监督、微调/冻结等多种场景。
- **实验设计亮点**：
  - 系统分析效用-擦除权衡的完整动态，而非仅报告最终点，提供更深入见解。
  - 使用多种强非线性探针（SVM+MLP组合）进行最严苛的泄露检测。
  - 跨越多个PLM（BERT、GPT-2、DeepSeek、LLaMa）验证泛化性。
  - 包含偏置采样控制和公平性分析，增强实际相关性。

## 8. 不足与局限

- **实验覆盖**：仅在三个NLP数据集上验证，未涉及图像或跨模态数据；仅针对性别、种族敏感属性，未测试其他类型（如年龄、宗教）。
- **偏差风险**：偏置采样实验显示数据分布敏感，实际应用中如果训练数据不能代表真实分布，擦除效果可能下降。
- **应用限制**：需要明确指定不想要的属性定义，若定义模糊或缺失，则难以应用。监督擦除需要任务标签，可能不可用。
- **理论局限性**：优化非凸，无闭式全局最优解；虽在实践中有效，但缺乏理论保证实现完美非线性擦除。
- **计算资源**：虽报告了复杂度，但对于大规模数据或高维特征，RFF近似可能引入额外误差，且多步迭代增加了总时间。

（完）
