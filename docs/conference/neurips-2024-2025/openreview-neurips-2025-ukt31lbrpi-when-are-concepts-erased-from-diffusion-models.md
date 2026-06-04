---
title: When Are Concepts Erased From Diffusion Models?
title_zh: 扩散模型中的概念何时被真正擦除？
authors: "Kevin Lu, Nicky Kriplani, Rohit Gandikota, Minh Pham, David Bau, Chinmay Hegde, Niv Cohen"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=UKt31LbRPI"
tags: ["query:ce"]
score: 7.0
evidence: 扩散模型概念擦除评估
tldr: 概念擦除方法虽然发展迅速，但概念是否真正被移除尚不清楚。本文提出了一套独立的探测技术，包括提供视觉上下文、修改扩散轨迹等，用于评估擦除效果。实验发现当前方法往往未能完全移除概念，为未来研究提供了基准。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-ukt31lbrpi/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1444, \"height\": 369, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ukt31lbrpi/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1437, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ukt31lbrpi/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1224, \"height\": 616, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ukt31lbrpi/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1023, \"height\": 411, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ukt31lbrpi/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1293, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ukt31lbrpi/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1427, \"height\": 675, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ukt31lbrpi/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1489, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ukt31lbrpi/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 859, \"height\": 380, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-ukt31lbrpi/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1444, \"height\": 376, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-ukt31lbrpi/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1256, \"height\": 588, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ukt31lbrpi/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1396, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ukt31lbrpi/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1175, \"height\": 190, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ukt31lbrpi/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1215, \"height\": 334, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ukt31lbrpi/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 601, \"height\": 407, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ukt31lbrpi/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1551, \"height\": 717, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-ukt31lbrpi/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1552, \"height\": 717, \"label\": \"Table\"}]"
motivation: 概念擦除方法众多，但缺乏统一评估标准，难以判断概念是否真正被移除。
method: 提出多种探测技术：提供视觉上下文、修改扩散轨迹、应用分类器指导、分析替代生成等。
result: 对多种概念擦除方法进行评估，发现大多数方法留下残留信号。
conclusion: 该探测套件为概念擦除的鲁棒性评估提供了重要工具。
---

## Abstract
In concept erasure, a model is modified to selectively prevent it from generating a target concept. Despite the rapid development of new methods, it remains unclear how thoroughly these approaches remove the target concept from the model. We begin by proposing two conceptual models for the erasure mechanism in diffusion models: (i) interfering with the model’s internal guidance processes, and (ii) reducing the unconditional likelihood of generating the target concept, potentially removing it entirely. To assess whether a concept has been truly erased from the model, we introduce a comprehensive suite of independent probing techniques: supplying visual context, modifying the diffusion trajectory, applying classifier guidance, and analyzing the model's alternative generations that emerge in place of the erased concept. Our results shed light on the value of exploring concept erasure robustness outside of adversarial text inputs, and emphasize the importance of comprehensive evaluations for erasure in diffusion models.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

论文关注扩散模型中的概念擦除（concept erasure）问题：当模型被修改以阻止生成某个目标概念时，这种擦除是否真正从模型中移除了该概念的知识，还是仅仅在生成过程中回避它？现有方法虽然能够通过标准提示词实现视觉上的擦除成功，但已有研究（如Pham等，2023）表明，通过搜索合适的输入（如文本反转或对抗攻击）可以重新唤起被擦除的概念。这表明大多数现有方法可能只是“引导式规避”（guidance-based avoidance），而非真正的“破坏式移除”（destruction-based removal）。论文的核心动机是：提出一套全面的独立探测技术，以评估概念擦除的彻底性，并推动更严格的评估标准。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

论文提出了两种概念擦除机制的概念模型：

- **引导式规避（Guidance-based Avoidance）**：修改条件引导，使模型生成时偏离目标概念，但底层知识仍然保留。例如UCE方法通过优化注意力投影矩阵，将擦除概念的嵌入映射到中性向量，条件分布从P(X|ci)转向P(X|c*_i)，但核心特征未被消除。
- **破坏式移除（Destruction-based Removal）**：降低目标概念的无条件生成概率P(X)，试图从根本上抑制或消除知识。例如梯度上升（GA）和任务向量（Task Vector）等方法。

为了区分这两种机制，论文设计了一套探测套件，包含五种独立的探测技术：

1. **基于优化的探测（Optimization-based Probing）**：通过文本反转（Textual Inversion）和对抗攻击（UnlearnDiffAtk）优化输入，尝试重新唤起擦除概念。
2. **上下文探测（In-context Probing）**：
   - 图像修复（Inpainting）：给定包含擦除概念的部分图像，模型完成遮罩区域。
   - 扩散补全（Diffusion Completion）：从未擦除模型生成的中间噪声图像开始，由擦除模型完成去噪。
3. **训练无关的轨迹探测（Training-Free Trajectory Probing）**：在每次去噪步骤中增加额外高斯噪声（噪声缩放参数η在1.0至1.85间搜索），扩大扩散轨迹带宽，使模型可能回到高似然的概念区域。公式：˜x_{t-1} = (˜x_t - αϵ_D) + ηϵ。
4. **引导式潜在探测（Steered Latent Probing）**：训练一个轻量级的时间步感知分类器，在潜在空间中计算梯度，引导扩散轨迹朝向擦除概念的区域。梯度：g_t = ∇_{x_t} L_BCE(f_c*(x_t,t), y=1)，更新：˜x_t = x_t - s_clf σ_t g_t。
5. **动态概念追踪（Dynamic Concept Tracing）**：观察概念在逐步擦除过程中生成的替代图像变化，分析不同方法的轨迹特点。

## 3. 实验设计：使用的数据集/场景、基准、对比方法

- **概念集合**：10个对象概念（如教堂、客机、垃圾车等）和3种艺术风格（梵高、毕加索、安迪·沃霍尔），共13个概念。
- **评估指标**：
  - CLIP相似度：衡量生成图像与目标概念名称的语义相似度。
  - 分类准确率：使用ImageNet预训练的ResNet-50分类器检测概念存在。
- **对比方法**：
  - 基线：未编辑的Stable Diffusion 1.4。
  - UCE（统一概念编辑）
  - ESD-u / ESD-x（擦除稳定扩散，分别更新整个U-Net或仅交叉注意力层）
  - Task Vector（任务向量）
  - GA（梯度上升）
  - STEREO（两阶段对抗性擦除）
  - RECE（快速封闭形式擦除）
- **评估场景**：标准提示词、文本反转、UnlearnDiffAtk、图像修复、扩散补全（t=5和t=10）、噪声探测（6个η值×4个噪声缩放因子，共24种配置）、分类器引导（24个引导强度）、分类器引导+噪声探测、动态概念追踪。

## 4. 资源与算力

论文附录C.2明确指出：**使用了两个NVIDIA A6000 GPU**进行所有模型的训练、评估套件的运行以及CLIP和分类指标的生成。用于生成探测图像、评估擦除鲁棒性、攻击验证及无关概念干扰检测。

## 5. 实验数量与充分性

- 共对13个概念进行评估，每个概念生成多张图像（标准提示词下10张，攻击实验更少但多轮）。
- 每种探测方法都面向所有7种擦除方法 + 1个基线，形成全面对比。
- 噪声探测进行了网格搜索（6个η值×4个缩放因子=24组合），分类器引导搜索24个s_clf值，动态追踪在不同擦除强度（0%-100%）下生成并分析。
- 每项实验均报告了平均结果，并在附录中提供了标准差。
- 实验设计较充分：涵盖了多种探测视角（优化、上下文、轨迹修改、分类器引导、动态监控），且对比了主流方法。但也存在局限：仅使用Stable Diffusion 1.4基础模型，未扩展到其他架构；概念类型有限（对象和风格，未包含抽象概念如“暴力”）。

## 6. 论文的主要结论与发现

- 大多数现有擦除方法实际上只实现了**引导式规避**，而非真正的破坏式移除。
  - GA、Task Vector、STEREO对文本优化攻击（文本反转、UnlearnDiffAtk）鲁棒性较强，但Task Vector和RECE在图像修复和扩散补全中仍能恢复概念。
  - 噪声探测能恢复UCE、ESD-x、ESD-u等方法的擦除概念，即使优化攻击失效。
  - 分类器引导探测进一步暴露了残留知识：STEREO在标准分类器引导下只有5.8%准确率，但结合噪声探测后升至20.3%。
- 动态概念追踪显示：破坏式方法（GA、Task Vector）在逐步擦除中概念退化更连续；引导式方法（ESD-x、ESD-u）产生更突变的替代图像。
- 鲁棒性更强的擦除方法往往对无关概念造成更大副作用（如STEREO和GA在无关概念上的分类准确率显著下降）。
- 全面评估套件是必要的，单一探测不足以判断擦除彻底性。

## 7. 优点

- **概念视角新颖**：明确区分引导式规避与破坏式移除两种机制，为理解擦除方法提供理论框架。
- **探测技术全面且独立**：五种探测方法覆盖不同路径（输入优化、视觉上下文、轨迹随机性、分类器引导、动态演变），避免单一视角偏差。
- **可扩展性强**：评估套件可轻松应用于任何现有或新的擦除方法。
- **实验设计严谨**：多个方法、多个概念、多种配置的对比，并报告标准差。
- **揭示非单调现象**：如简单的噪声注入比复杂优化攻击更有效，提示评估应考虑非对抗性信号。

## 8. 不足与局限

- **概念覆盖有限**：仅10个对象和3种艺术风格，未涉及动词、关系或抽象概念（如“暴力”），结论推广性受限。
- **基础模型单一**：仅基于Stable Diffusion 1.4，未验证在其他架构（如Stable Diffusion XL）上的表现。
- **分类器引导探测的潜在风险**：优化过程本身可能诱导生成出模型训练时未真正学习过的概念（即发现 vs. 调用的问题），需谨慎解释结果。
- **因果关系模糊**：概念擦除的因果影响复杂（如擦除“梵高”是否应连带影响“爱德华·蒙克”），当前方法尚无法实现精细控制。
- **未提供人类评估**：所有指标基于CLIP和分类器，缺乏人类感知验证。
- **算力消耗未完全透明**：仅说明使用两张A6000，未说明训练单个方法的耗时或总计算时间。

（完）
