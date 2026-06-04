---
title: "In-Context Unlearning: Language Models as Few-Shot Unlearners"
title_zh: 上下文遗忘：作为少样本遗忘者的大语言模型
authors: "Martin Pawelczyk, Seth Neel, Himabindu Lakkaraju"
date: 2024-05-02
pdf: "https://openreview.net/pdf?id=GKcwle8XC9"
tags: ["query:ce"]
score: 8.0
evidence: 提出上下文遗忘方法用于大语言模型，直接关联机器学习中的概念擦除
tldr: 针对大语言模型机器遗忘计算开销大的问题，提出上下文遗忘方法，无需更新模型参数即可在少样本设置下移除特定训练数据的影响，为概念擦除提供了高效且无需参数访问的新范式，实验验证了其有效性。
source: ICML-2024-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 874, \"height\": 499, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 852, \"height\": 315, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 878, \"height\": 565, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 881, \"height\": 345, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1776, \"height\": 662, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1765, \"height\": 347, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1780, \"height\": 924, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1779, \"height\": 988, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1607, \"height\": 862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2024-gkcwle8xc9/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1608, \"height\": 866, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2024-gkcwle8xc9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 848, \"height\": 365, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-gkcwle8xc9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1148, \"height\": 297, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2024-gkcwle8xc9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1746, \"height\": 284, \"label\": \"Table\"}]"
motivation: 大语言模型遗忘特定训练数据通常需要全面重训练或参数更新，计算成本高且需参数访问。
method: 提出上下文遗忘方法，通过构造上下文示例实现少样本遗忘，无需更新模型参数。
result: 在多个基准上验证了该方法能有效移除训练数据影响，同时保持模型性能。
conclusion: 上下文遗忘为语言模型的概念擦除提供了一种高效、实用的新途径。
---

## Abstract
Machine unlearning, the study of efficiently removing the impact of specific training instances on a model, has garnered increased attention in recent years due to regulatory guidelines such as the Right to be Forgotten. Achieving precise unlearning typically involves fully retraining the model and is computationally infeasible in case of very large models such as Large Language Models (LLMs). To this end, recent work has proposed several algorithms which approximate the removal of training data without retraining the model. These algorithms crucially rely on access to the model parameters in order to update them, an assumption that may not hold in practice due to computational constraints or having only query access to the LLMs. In this work, we propose a new class of unlearning methods for LLMs called ``In-Context Unlearning.'' This method unlearns instances from the model by simply providing specific kinds of inputs in context, without the need to update model parameters. To unlearn specific training instances, we present these instances to the LLMs at inference time along with labels that differ from their ground truth. Our experimental results demonstrate that in-context unlearning performs on par with, or in some cases outperforms other state-of-the-art methods that require access to model parameters, effectively removing the influence of specific instances on the model while preserving test accuracy.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：随着 GDPR 等法规中“被遗忘权”的推行，机器学习模型需要能够高效移除特定训练样本的影响（即机器遗忘）。然而，大语言模型（LLM）参数规模巨大，完全重新训练模型代价极高；已有的近似遗忘方法（如梯度上升）需要访问模型参数，这在实际中可能因计算资源限制或仅有黑盒查询接口而不可行。
- **核心问题**：能否在不更新模型参数、仅利用 LLM 推理时的上下文输入，实现少样本（few-shot）遗忘，使模型行为近似于从未见过那些训练样本？
- **整体含义**：提出了一种全新的遗忘范式——**上下文遗忘（In-Context Unlearning, ICUL）**，通过构造特定上下文提示，使 LLM 在推理时直接表现出遗忘效果，无需参数访问或重训练，为黑盒模型的高效遗忘提供了可行路径。

## 2. 论文提出的方法论

### 核心思想
- 利用 LLM 的上下文学习（In-Context Learning）能力，在推理时向模型提供包含“遗忘点+错误标签”的上下文示例，以及若干正确标签的示例，从而让模型输出的分布近似于该点从未出现在训练集中的情况。

### 关键技术细节（以分类任务为例，三步构造流程）
1. **翻转遗忘点标签**：对于要遗忘的 K 个训练样本，将其标签随机改为其他标签（例如从“Positive”改为“Neutral”），形成模板 `[Forget Input 1][Different Label] ... [Forget Input K][Different Label]`。
2. **加入正确标签训练点**：随机抽取 L 个正确标签的训练样本（L 通常取 2、4、6），附加到上一步模板之后，形成 `[Forget Inputs with flipped labels] \n [Input 1][Correct Label] ... [Input L][Correct Label]`。
3. **预测**：将查询输入添加到模板末尾，令模型以温度 t=0 生成下一个 token。

- 对于问答任务，类似地将遗忘样本的答案翻转为其他随机答案。
- 无需任何梯度更新或参数访问，仅需一次前向推理。

### 公式或算法流程（文字说明）
- 不涉及复杂公式，核心是输入构造：构造一个混合了“错误标签遗忘点 + 正确标签参照点”的上下文，利用 ICL 的少样本学习特性“覆盖”模型对遗忘点的记忆。

## 3. 实验设计

### 数据集
- **分类任务**：SST-2（情感二分类）、Amazon Polarity（评论二分类）、AG-News（新闻四分类）。每个数据集随机子采样 25000 条用于微调。
- **问答任务**：SQuAD。

### Benchmark 与对比方法
- **方法对比**：
  - **ICUL**（本文方法，黑盒，不访问参数）
  - **Gradient Ascent (GA)**（现有白盒方法，需访问参数，在遗忘集上做梯度上升，搜索学习率 {5e-5, 3e-5, 1e-5, 5e-6}）
  - **Baseline**：不做遗忘的原始微调模型
  - **Benchmark**：随机猜测（LiRA 攻击下 TPR = FPR 的完美遗忘线）
- **评估指标**：
  - **遗忘有效性**：提出 **LiRA-Forget** 评估方法（基于 Carlini et al. 的 LiRA 会员推断攻击，但针对遗忘场景：用似然比检验区分“未学习模型”与“重新训练模型”输出），核心指标为 FPR=0.01 时的 TPR（越低越好）。
  - **模型性能**：测试集准确率。

## 4. 资源与算力

- **GPU 型号**：
  - Bloom 系列模型（560M、1.1B、3B、7.1B）：使用 **Nvidia Tesla V100 (32 GB RAM)**。
  - Llama-2 7B：微调用 **A100 (80 GB RAM)**，ICUL 推理用 **V100 (32 GB RAM)**。
- **训练时长**：
  - 微调一个 Bloom 模型约 1 GPU 小时；微调所有阴影模型（10 个）约 40 GPU 小时/数据集。
  - ICUL 推理：每轮约 2 小时（3 种上下文长度 × 40 模型 × 3 数据集 → 约 600 GPU 小时）。
  - GA 类似：4 种学习率 × 40 模型 → 约 600 GPU 小时。
  - 总计重现图 5 实验约 **1800 GPU 小时（75 GPU 天）**。
- **模型大小**：Llama-2 7B 微调需 48 小时/配置，推理约 8 小时/轮。
- **存储需求**：约 1500 GB 用于阴影模型权重的保存。

## 5. 实验数量与充分性

- **主要实验（图 5）**：在 3 个分类数据集上，对忘却集大小 {1, 5, 10, 20} 进行测试，对比 ICUL（3 种上下文长度 L=2,4,6）与 GA（4 种学习率）。每组 10 次运行取均值±标准差。
- **模型规模敏感度（图 3）**：在 SST-2 上用 4 种不同规模的 Bloom 模型（560M~7.1B）验证，忘却集大小为 10。
- **SOTA 模型验证（图 4）**：Llama-2 7B 上测试忘却集大小 {1, 10, 20}。
- **问答任务（表 1）**：SQuAD 上忘却 5 和 10 个样本。
- **消融实验（图 6）**：
  - 上下文长度 L 的影响（ICUL(2), ICUL(4), ICUL(6)）
  - 标签翻转必要性（对比标准 ICL 不放翻转）
  - 依赖遗忘点必要性（对比随机替换遗忘点为其他训练点）
- **充分性评价**：实验覆盖多数据集、多模型规模、多种忘却集大小，并进行了详细的消融分析，评估方法（LiRA-Forget）为最优似然比检验，结果客观。但仅在分类和问答任务上评估，未涉及开放生成任务。

## 6. 论文的主要结论与发现

- **ICUL 有效且无参数更新**：在 FPR=0.01 下的 TPR 接近随机猜测基准，显著低于 Baseline，表明 LiRA-Forget 无法区分遗忘点与从未见过点，遗忘成功。
- **对比 GA**：ICUL 在 14/16 个设置中遗忘效果优于 GA，且 GA 在中等忘却集大小（5/10）时效果下降甚至低于 Baseline。
- **保持测试准确率**：ICUL 的测试准确率随忘却集大小增加下降缓慢，而 GA 在大忘却集（20）时准确率显著下降。
- **适用于不同模型**：在 Bloom 系列和 Llama-2 上均有效，且模型越大，ICUL 相对 Baseline 的改善越明显（TPR 降低幅度更大）。
- **标签翻转是关键**：消融实验显示，若不翻转遗忘点标签（即标准 ICL），则无法实现遗忘；若用随机点替换遗忘点，效果也变差。

## 7. 优点

1. **新范式**：首次将上下文学习用于机器遗忘，提出无需参数访问的遗忘方案。
2. **实用性强**：适用于黑盒 API 模型，计算资源需求低（内存比 GA 小得多，如 Llama-2 7B 上 ICUL 可用 V100 32GB 运行，而 GA 需 A100 80GB）。
3. **评估方法创新**：提出 LiRA-Forget，基于最优似然比检验，比传统启发式评估更严谨。
4. **实验充分且透明**：详细报告了算力/存储需求，并公开代码，可复现性强。
5. **消融深入**：明确揭示标签翻转、依赖特定遗忘点、上下文长度对成功遗忘的必要性。

## 8. 不足与局限

1. **任务覆盖有限**：主要针对分类和问答任务，未在开放文本生成、代码生成等更复杂场景验证。
2. **忘却集规模受限**：当前上下文构造方式不支持较大忘却集（文中最大为 20），未来需设计更高效提示策略。
3. **推理时间开销**：忘却集增大时，上下文变长导致推理时间增加（表 3 显示 20 个忘却点推理时间约 1.64 秒，比无上下文长得多）。
4. **准确率下降**：在问答任务上，10 个忘却点时准确率下降超 15%（从 72% 降至 60%），提示泛化能力不足。
5. **隐私攻击风险**：ICUL 将遗忘点明文放入上下文，可能面临提示窃取攻击（prompt stealing），泄露敏感信息，论文未提供防护措施。
6. **评估计算成本高**：LiRA-Forget 仍需训练多个阴影模型，对于超大 LLM 可能不实际。

（完）
