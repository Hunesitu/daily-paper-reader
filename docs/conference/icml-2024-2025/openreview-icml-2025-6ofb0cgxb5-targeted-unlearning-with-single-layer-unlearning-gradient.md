---
title: Targeted Unlearning with Single Layer Unlearning Gradient
title_zh: 基于单层遗忘梯度的目标遗忘
authors: "Zikui Cai, Yaoteng Tan, M. Salman Asif"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=6Ofb0cGXb5"
tags: ["query:ce"]
score: 9.0
evidence: 提出单层遗忘梯度方法用于CLIP、Stable Diffusion和视觉-语言模型，直接解决图像生成中的机器遗忘
tldr: 针对机器遗忘方法计算成本高且可能损害模型性能的问题，提出单层遗忘梯度（SLUG）方法，通过一次梯度计算更新单个关键层，利用层重要性和梯度对齐指标选择最优层，在CLIP、Stable Diffusion和视觉-语言模型上成功移除具体和抽象概念，同时保留模型效用，为图像生成模型的高效概念擦除提供了实用方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1629, \"height\": 798, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1697, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1366, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1313, \"height\": 843, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 856, \"height\": 530, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1349, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1360, \"height\": 586, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1224, \"height\": 1548, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1333, \"height\": 551, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1330, \"height\": 560, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1227, \"height\": 964, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1499, \"height\": 655, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1464, \"height\": 510, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1309, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1237, \"height\": 1204, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1285, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1276, \"height\": 1506, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1157, \"height\": 1753, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1168, \"height\": 1737, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1654, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1757, \"height\": 577, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1750, \"height\": 2060, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1748, \"height\": 2058, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1744, \"height\": 2045, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-6ofb0cgxb5/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1745, \"height\": 2035, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1769, \"height\": 401, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1768, \"height\": 437, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1507, \"height\": 592, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1704, \"height\": 354, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1422, \"height\": 312, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1776, \"height\": 1304, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1409, \"height\": 402, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1548, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1365, \"height\": 242, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1264, \"height\": 495, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-6ofb0cgxb5/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 970, \"height\": 278, \"label\": \"Table\"}]"
motivation: 现有机器遗忘方法需要大量模型更新，计算成本高且可能损害模型性能。
method: 提出SLUG方法，通过计算单层梯度一次更新关键层，实现高效目标遗忘。
result: 在多个视觉-语言模型上成功移除具体和抽象概念，性能损失小。
conclusion: SLUG为图像生成模型的机器遗忘和概念擦除提供了一种高效实用的方法。
---

## Abstract
Machine unlearning methods aim to remove sensitive or unwanted content from trained models, but typically demand extensive model updates at significant computational cost while potentially degrading model performance on both related and unrelated tasks. We propose Single Layer Unlearning Gradient (SLUG) as an efficient method to unlearn targeted information by updating a single critical layer using a one-time gradient computation. SLUG uses layer importance and gradient alignment metrics to identify the optimal layer for targeted information removal while preserving the model utility. We demonstrate the effectiveness of SLUG for CLIP, Stable Diffusion, and vision-language models (VLMs) in removing concrete (e.g., identities and objects) and abstract concepts (e.g., artistic styles). On the UnlearnCanvas benchmark, SLUG achieves comparable unlearning performance to existing methods while requiring significantly less computational resources. Our proposed approach offers a practical solution for targeted unlearning that is computationally efficient and precise. Our code is available at https://github.com/CSIPlab/SLUG

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：现代大规模基础模型（如CLIP、Stable Diffusion、视觉-语言模型VLM）在训练过程中会吸收大量数据，其中可能包含敏感、受版权保护或有害的内容。为了合规（如GDPR）与伦理要求，需要从已训练模型中移除特定信息，即“机器遗忘”（machine unlearning）。
- **现有方法缺陷**：传统方法（如梯度上升、微调、SalUn、SSD）通常需要对整个模型的全部或大量参数进行多轮迭代更新，计算开销大；且容易损害模型在保留集及其他无关任务上的性能（遗忘副作用）；超参数调节成本高。
- **目标**：提出一种同时满足**计算高效**、**遗忘有效且鲁棒**、**只针对目标概念移除、最小化副作用**的遗忘方法。

## 2. 论文提出的方法论

- **核心思想**：通过一次梯度计算，仅更新模型中**单个关键层**的权重，即可实现目标概念的遗忘，同时保持模型通用能力。
- **关键技术细节**：
  1. **单次梯度计算**：对模型初始参数，分别计算遗忘集上的损失梯度 \(\nabla_{\theta} L_{\text{forget}}\) 和保留集上的损失梯度 \(\nabla_{\theta} L_{\text{retain}}\)。
  2. **层重要性度量**：对每一层 \(l\)，定义重要性 = \(\frac{\|\nabla_{\theta_l} L_{\text{forget}}\|_2}{\|\theta_l\|_2}\)，反映该层参数对遗忘损失的敏感度。
  3. **梯度对齐度量**：计算遗忘梯度与保留梯度的余弦相似度 \(\cos(\nabla_{\theta_l} L_{\text{forget}}, \nabla_{\theta_l} L_{\text{retain}})\)，对齐度越小，更新该层对保留集的影响越小。
  4. **帕累托最优层选择**：在所有层中，找出重要性高且对齐度低的帕累托前沿层集合（见图2a,d）。
  5. **单步更新**：只对选中的最优层，沿遗忘梯度方向做一次权重更新：\(\theta_l^* = \theta_l^{(0)} - \lambda^* \nabla_{\theta_l} L_{\text{forget}}\)，步长 \(\lambda^*\) 通过二分搜索确定，使得遗忘准确率降为零且保留集准确率最大化。
  6. **损失函数设计**：保留集使用原始对比损失；遗忘集使用余弦嵌入损失，直接推离正样本对，不影响负样本对。
- **算法流程**（文字说明）：
  - 输入：遗忘集、保留集、原始模型、所有层。
  - ① 计算两个梯度（一次计算）。
  - ② 对每一层计算重要性和对齐度。
  - ③ 找出帕累托最优层集合。
  - ④ 对每个帕累托层，用二分搜索确定步长 \(\lambda\)，获得遗忘准确率和保留准确率。
  - ⑤ 选择遗忘准确率最低且保留准确率最高的层和步长。
  - ⑥ 用该层、该步长更新一次模型参数。

## 3. 实验设计

- **使用场景与数据集**：
  - CLIP：使用LAION-400M子集构建遗忘集（每个身份1000-6000对）；保留集为LAION-400M单分片（约7900张图）；评估用CelebA（100个名人）和ImageNet。
  - Stable Diffusion：身份遗忘用自定义名人图片；UnlearnCanvas基准（60种风格×20种物体，24000张生成图）。
  - VLM（LLaVA-1.5-7B）：从CelebA选取10个名人，每个100张图，用于评估遗忘准确率；保留集用标准VLM benchmark（MME、GQA、MMBench）。
- **基准与对比方法**：
  - CLIP：FT、GA、GAFT、SalUn、SSD。
  - SD（UnlearnCanvas）：ESD、FMN、UCE、CA、SalUn、SEOT、SPM、EDiff、SHS等9种方法。
  - VLM：无直接对比方法，仅报告SLUG效果。
- **评估指标**：
  - CLIP：遗忘准确率FA@1、FA@5；测试准确率（ImageNet + CelebA）。
  - SD：UA（遗忘准确率）、IRA（域内保留准确率）、CRA（跨域保留准确率）、FID。
  - VLM：遗忘准确率（错误识别比例）+ 标准VLM benchmark分数。
  - 综合性指标：Gap Ratio（GR）归一化距离。

## 4. 资源与算力

- 文中明确提到：梯度计算和更新在**NVIDIA A100 40GB** GPU上完成。对于UnlearnCanvas基准，SLUG的**计算时间仅39秒**（单次梯度计算+单层更新），内存消耗3.61GB，存储仅0.04GB（仅保存帕累托层的梯度）。对比方法中，最快的SEOT需95秒，内存7.34GB。
- 未详细说明训练每个场景的总GPU小时数，但一次性计算梯度成本极低，远低于迭代方法。

## 5. 实验数量与充分性

- **实验组数**：
  - CLIP：单身份遗忘（1个，但扩展至10个名人），多身份联合遗忘（N=1~6），多种CLIP架构（ViT-B-32, ViT-B-16, ViT-L-14, EVA01-g-14），目标概念（7个ImageNet类）。
  - SD：身份遗忘（多个名人），版权角色、新颖概念、艺术风格/物体（UnlearnCanvas四大类共80个子任务），鲁棒性测试（概念算术攻击、量化）。
  - VLM：10个不同名人分别遗忘，每个在标准benchmark上评估。
  - **消融实验**（表4）：比较使用重要性、对齐度、随机、帕累托前沿层、全层等不同选择策略，验证两者缺一不可。
- **充分性评价**：实验覆盖了多种模型规模（1.5亿~7B）、多种数据类型（身份、物体、风格、版权）、多个下游任务（分类、生成、问答），对比了9种当下主流方法，并在统一基准UnlearnCanvas上系统比较。结论具有较强普适性和客观性。

## 6. 论文的主要结论与发现

- SLUG通过单层单次梯度更新即可实现有效的目标遗忘。
- 相比现有方法，SLUG在保持同等遗忘效果的前提下，**计算时间减少1~3个数量级**，存储开销极低。
- 在UnlearnCanvas基准上，SLUG在所有指标（UA、IRA、CRA、FID、时间、内存、存储）的综合“Gap Ratio”最小，表明其效果与效率最佳平衡。
- SLUG对概念算术攻击和量化鲁棒，且能同时遗忘多个身份（模块化更新）。
- 单层更新的成功挑战了“必须全模型更新”的直觉。

## 7. 优点

- **计算效率极高**：只需一次梯度计算+一次更新，无需迭代，大幅降低算力和时间。
- **精确靶向**：通过帕累托优化选择单一关键层，最小化对保留集和无关概念的影响。
- **通用性强**：统一框架适用于CLIP、Stable Diffusion、VLM等多种视觉-语言基础模型。
- **无超参数手动调节**：步长通过二分搜索自动确定，简化使用。
- **轻量存储**：只需存储少量梯度值，适合模型编辑的模块化部署。
- **实验充分**：跨模型规模、跨任务、跨场景，并与9种SOTA方法在UnlearnCanvas上公平比较。

## 8. 不足与局限

- **未达所有指标同时最优**：在UnlearnCanvas上，SLUG在UA、IRA、CRA等单项指标并非最高，仅在综合Gap Ratio上最优（牺牲部分纯效果换取极端效率）。
- **理论解释不足**：未提供严格的理论证明解释为何对单个关键层的线性更新足以遗忘概念；理解“何时有效”仍是开放问题。
- **白盒对抗攻击鲁棒性弱**：在UnlearnDiffAtk/P4D攻击下，SLUG的ASR较高（与其他方法类似），表明缺乏对白盒对抗提示的抵抗力。
- **黑盒重学习攻击未检测**：未评估攻击者使用部分遗忘数据重新训练后能否恢复概念。
- **LLM未验证**：实验主要针对视觉-语言模型，未涉及纯语言大模型（LLM）。
- **不能保证完美擦除**：简单操纵可能无法完全移除模型内部信息，仍可能被复杂提示恢复。

（完）
