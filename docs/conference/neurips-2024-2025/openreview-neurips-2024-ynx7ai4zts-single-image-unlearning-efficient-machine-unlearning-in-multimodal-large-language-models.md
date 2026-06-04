---
title: "Single Image Unlearning: Efficient Machine Unlearning in Multimodal Large Language Models"
title_zh: 单图像遗忘：多模态大语言模型中的高效机器遗忘
authors: "Jiaqi Li, Qianshan Wei, Chuanyi Zhang, Guilin Qi, Miaozeng Du, Yongrui Chen, Sheng Bi, Fan Liu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=YNx7ai4zTs"
tags: ["query:ce"]
score: 9.0
evidence: 针对多模态大语言模型的单图像遗忘方法
tldr: 本文提出单图像遗忘（SIU），面向多模态大语言模型的高效机器遗忘方法。通过构造多方面的微调数据并联合优化，仅需对单张相关图像微调少数几步即可遗忘视觉概念识别。解决了多模态模型中视觉数据泄露的遗忘问题。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1440, \"height\": 700, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1415, \"height\": 446, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1413, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1412, \"height\": 413, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1620, \"height\": 526, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1232, \"height\": 1035, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1451, \"height\": 671, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1276, \"height\": 1055, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1299, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1287, \"height\": 829, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1281, \"height\": 1538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1272, \"height\": 1529, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1297, \"height\": 1353, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1284, \"height\": 1098, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1272, \"height\": 1497, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1291, \"height\": 1535, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1287, \"height\": 1454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1295, \"height\": 1297, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-ynx7ai4zts/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1291, \"height\": 1290, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1170, \"height\": 428, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 719, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1142, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 662, \"height\": 213, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1072, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1009, \"height\": 1434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1093, \"height\": 410, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1279, \"height\": 1536, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1294, \"height\": 1556, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1272, \"height\": 1529, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1272, \"height\": 1497, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-ynx7ai4zts/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1287, \"height\": 1454, \"label\": \"Table\"}]"
motivation: 多模态大语言模型可能记忆泄露的视觉概念数据，需要高效遗忘。
method: 基于单张图像构造多维度微调数据，联合优化实现概念遗忘。
result: 仅需几步微调即可有效遗忘视觉概念识别，且保持模型其他能力。
conclusion: SIU为多模态模型提供了轻量级的机器遗忘方案。
---

## Abstract
Machine unlearning (MU) empowers individuals with the `right to be forgotten' by removing their private or sensitive information encoded in machine learning models. However, it remains uncertain whether MU can be effectively applied to Multimodal Large Language Models (MLLMs), particularly in scenarios of forgetting the leaked visual data of concepts. To overcome the challenge, we propose an efficient method, Single Image Unlearning (SIU), to unlearn the visual recognition of a concept by fine-tuning a single associated image for few steps. SIU consists of two key aspects: (i) Constructing Multifaceted fine-tuning data. We introduce four targets, based on which we construct fine-tuning data for the concepts to be forgotten; (ii)  Joint training loss. To synchronously forget the visual recognition of concepts and preserve the utility of MLLMs, we fine-tune MLLMs through a novel Dual Masked KL-divergence Loss combined with Cross Entropy loss. Alongside our method, we establish MMUBench, a new benchmark for MU in MLLMs and introduce a collection of metrics for its evaluation. Experimental results on MMUBench show that SIU completely surpasses the performance of existing methods. Furthermore, we surprisingly find that SIU can avoid invasive membership inference attacks and jailbreak attacks. To the best of our knowledge, we are the first to explore MU in MLLMs. We will release the code and benchmark in the near future.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：多模态大语言模型（MLLMs）在大规模预训练中可能无意间记忆了包含个人隐私或涉及版权侵犯的视觉概念数据，带来数据泄露风险。传统的“重新训练”方式资源消耗大且不现实，因此需要高效的“机器遗忘”（Machine Unlearning, MU）方法。
- **背景挑战**：现有MU方法主要针对纯文本LLMs或分类任务，但在MLLMs中遗忘视觉概念面临两大困难：1) 针对目标概念收集大量图像数据十分困难；2) 直接使用梯度上升等方法容易导致模型退化（输出空白或重复token），而结合KL散度又会与遗忘目标冲突（KL会拉近被遗忘概念的概率分布）。
- **本文贡献**：首次探索MLLMs中视觉概念遗忘问题，提出**单图像遗忘（Single Image Unlearning, SIU）**，仅需一张训练图像、几步微调即可高效遗忘目标概念的视觉识别能力，同时保持模型其他能力。

## 2. 方法论

### 2.1 核心思想
SIU通过构造**多面微调数据**（Multifaceted Fine-tuning Data）和设计**双掩码KL散度损失（Dual Masked KL-divergence Loss, DMK Loss）**，联合交叉熵损失进行梯度下降优化，实现遗忘与保留的平衡。

### 2.2 关键技术细节
#### (1) 多面微调数据（四目标构造）
- **Aligning with Unseen Concepts**：让模型输出与“概念从未见过”时类似的错误名称（如将Donald Trump说成Jacob Campbell），而非简单回答“I don't know”。通过实验发现MLLMs对未见人物倾向于输出“John”、“a man”等。
- **Assigning New Visual Description**：为概念虚构新视觉描述（如“黑发、小脸”），避免模型混淆原名称与新名称。
- **Decoupling Factual Knowledge**：保留概念的纯事实知识（如“他是美国前总统”），避免遗忘超过视觉范围。
- **Preserving Non-targeted Knowledge**：引入其他无关概念的问答对，防止模型对非目标知识也遗忘。

每个目标各构造一条或多条（4条）训练样本，总计约16条。

#### (2) 联合训练损失
- **双掩码KL散度损失（DMK Loss）**：
  - **Token-Level Masking**：在句子中掩去与遗忘目标矛盾的token（如分配给新名称“Jacob Campbell”），使KL计算时不强制提升这些token的概率。
  - **Vocabulary-Level Masking**：在词汇表中掩去目标概念名称的所有token（如“Donald”和“Trump”），避免KL计算时保留它们的概率。
- 总损失：\[ \mathcal{L}_{\text{total}} = -\alpha \cdot \text{CrossEntropy} + \beta \cdot \mathcal{L}_{\text{DMK}} \]，其中\(\alpha=0.9\)，\(\beta=0.75\)。

## 3. 实验设计

### 3.1 数据集与Benchmark
- **MMUBench**：自建基准，包含20个概念（如Donald Trump, Hello Kitty, Mario, Picasso等），每个概念至少50张图像（1张用于训练遗忘，其余测试泛化）。由MIKE数据集采样并经LLAVA过滤得到。
- **评估指标**：
  - Efficacy（训练集准确率）
  - Generality（EM、GPT-4评估G-Eval、概念概率距离C-Dis）
  - Specificity（8个公共多模态基准的平均，如GQA、VQA-v2、POPE等）
  - Fluency（掩码后的困惑度）
  - Diversity（独特词数量）
  - 额外：Membership Inference Attack (MIA)、Jailbreak（多语言+多跳问题）

### 3.2 对比方法
- **PO**（Preference Optimization）：用“I do not know.”作为回答
- **GA**（Gradient Ascent）
- **GA+KL**：GA与KL散度结合
- **SIU**（本文方法）

### 3.3 模型与训练
- 使用LLAVA (7B, 13B)，LoRA微调，学习率3e-4，batch size 4，训练步数6（单概念），优化器Adam。

## 4. 资源与算力
- 使用 **4块 NVIDIA A100 40G GPU** 进行训练。
- 单概念训练步数仅6步，资源消耗较低。
- 文中未明确给出总训练时长或具体能耗数据，但通过LoRA和少量步数可推断效率很高。

## 5. 实验数量与充分性

- **主要对比实验**（表1）：两种模型规模（7B和13B）下对比4种方法，报告均值与标准差（3次独立试验）。
- **消融实验**（表2）：分别移除Token-Level Mask和Vocabulary-Level Mask，验证DMK各组件贡献。
- **不同训练步数分析**（图2、图3）：展示各方法在6-35步内各指标变化。
- **不同概念实验**（图4）：8个额外概念（Doodle, Elon Musk, Facebook等）的EM对比。
- **多概念同时遗忘**（表3）：20个概念联合遗忘，测试稳定性。
- **MIA与Jailbreak攻击**（表4）：ROUGE-L和多语言/多跳测试。
- **案例研究**（附录图9-22）：展示蝴蝶效应、多语言输出等。
- **实验充分性评价**：实验覆盖主要维度，有多次重复和统计，消融完整，考虑攻击鲁棒性，对比方法全面。但部分指标（如G-Eval）依赖GPT-4评估，存在主观性。

## 6. 主要结论与发现

- **SIU在所有指标上全面超越现有方法**，特别是在Generality（EM达99%以上）和Diversity（97%）上显著领先。
- **仅需一张训练图像**即可有效遗忘视觉概念，且对模型规模变化稳健（13B模型性能下降最小）。
- **双掩码KL损失有效解决了GA+KL的矛盾**：避免了遗忘任务与KL保持概率分布的冲突。
- **SIU具有防御MIA和Jailbreak攻击的能力**：输出与原模型相似度最低，且在多种语言和多跳问题下不易被诱导恢复被遗忘概念。
- **意外发现“正面蝴蝶效应”**：遗忘Donald Trump后，与其相关的Melania Trump在合影中被误认，但单独裁剪后仍可正确识别，表明遗忘是选择性而非盲目删除。

## 7. 优点

- **首次系统探索MLLM中视觉概念遗忘**，填补了研究空白。
- **数据效率极高**：仅需一张训练图像，几步微调，适合实际应用。
- **创新性损失设计**：DMK Loss通过双层掩码巧妙平衡遗忘与模型效用。
- **构建专用基准MMUBench**：包含20个概念、多种评估维度和攻击测试，便于后续研究。
- **实验严谨**：多维度评估（有效性、泛化、特异性、流畅性、多样性），并考虑鲁棒性（MIA、越狱）。
- **实用性强**：方法轻量、易部署，且能防御隐私攻击。

## 8. 不足与局限

- **模型多样性不足**：仅使用LLAVA（7B/13B）进行实验，未在其他MLLM架构（如InstructBLIP、CogVLM）上验证，泛化性有待检验（Appendix E说明受限于基准构建依赖LLAVA过滤）。
- **概念覆盖有限**：仅20个概念，且可能偏向LLAVA容易识别的对象；未涉及数据点级别（如单张图像）的遗忘。
- **评估依赖GPT-4**：G-Eval等指标引入主观偏差，且GPT-4的可重复性存疑。
- **未深入分析遗忘机制**：如“正面蝴蝶效应”现象未给出理论解释。
- **训练数据构造依赖人工设计**：需为每个概念手动生成微调样本，自动化程度可提升。
- **多概念联合遗忘时性能下降**（Specificity降至24.9%），虽优于其他方法，但仍存在效用损失。

（完）
