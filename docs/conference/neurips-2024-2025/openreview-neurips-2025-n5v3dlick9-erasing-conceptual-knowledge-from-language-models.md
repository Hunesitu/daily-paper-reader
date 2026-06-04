---
title: Erasing Conceptual Knowledge from Language Models
title_zh: 从语言模型中擦除概念知识
authors: "Rohit Gandikota, Sheridan Feucht, Samuel Marks, David Bau"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=N5V3dlIck9"
tags: ["query:ce"]
score: 9.0
evidence: 通过分布匹配从语言模型中擦除概念知识
tldr: 本文提出ELM（语言记忆擦除），一种面向语言模型的概念级遗忘方法。核心思想是利用模型自身的分类能力识别欲擦除概念，通过低秩更新降低相关内容的生成概率。在生物安全、网络安全和文学领域擦除任务上验证了有效性，同时保持模型通用能力。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-n5v3dlick9/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1457, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n5v3dlick9/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1445, \"height\": 422, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n5v3dlick9/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1431, \"height\": 454, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n5v3dlick9/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1157, \"height\": 817, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-n5v3dlick9/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1141, \"height\": 601, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-n5v3dlick9/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1469, \"height\": 828, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n5v3dlick9/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1232, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n5v3dlick9/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 916, \"height\": 268, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n5v3dlick9/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1473, \"height\": 987, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n5v3dlick9/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1418, \"height\": 303, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n5v3dlick9/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 875, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-n5v3dlick9/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 898, \"height\": 733, \"label\": \"Table\"}]"
motivation: 语言模型可能记忆有害或隐私概念，需要高效且无损地擦除。
method: 利用模型自身分类能力进行分布匹配，通过低秩更新减少概念相关生成概率。
result: 在多个安全敏感领域成功擦除概念，并保持模型通用性能。
conclusion: ELM提供了一种原则性的语言模型概念擦除框架。
---

## Abstract
In this work, we introduce Erasure of Language Memory (ELM), a principled approach to concept-level unlearning that operates by matching distributions defined by the model's own introspective classification capabilities. Our key insight is that effective unlearning should leverage the model's ability to evaluate its own knowledge, using the language model itself as a classifier to identify and reduce the likelihood of generating content related to undesired concepts. ELM applies this framework to create targeted low-rank updates that reduce generation probabilities for concept-specific content while preserving the model's broader capabilities. We demonstrate ELM's efficacy on biosecurity, cybersecurity, and literary domain erasure tasks. Comparative evaluation reveals that ELM-modified models achieve near-random performance on assessments targeting erased concepts, while simultaneously preserving generation coherence, maintaining benchmark performance on unrelated tasks, and exhibiting strong robustness to adversarial attacks.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：如何从大型语言模型中高效、稳健地擦除**广义的概念性知识**（例如关于生物武器、网络安全或特定文学世界），而不仅仅是删除单个训练样本。
- **动机背景**：现有的机器遗忘方法（如重训练过滤数据、梯度反转、表示扰动）存在成本高、不稳定、破坏生成连贯性或无法完全消除知识的局限。作者指出，这些方法缺乏一个**有原则的目标**来定义什么是成功的概念擦除。
- **整体含义**：ELM 将遗忘重新定义为**模型自身内部分类能力的分布匹配**，使得模型在无外部分类器的情况下，自己能判断哪些内容属于要擦除的概念并主动降低其生成概率，同时保持对其他能力的保留。

## 2. 论文提出的方法论：核心思想、关键技术细节（公式用文字说明）

- **核心思想**：利用语言模型自身的“内省分类”能力。给定一个文本序列，模型能隐式评估它属于某个概念的概率。通过构造两个上下文提示——`c⁻`（表示“专家”在讨论该概念）和 `c⁺`（表示“新手”无相关背景）——可以调节模型对目标概念的生成倾向。
- **关键技术细节**：
  - **分布匹配公式**：擦除后的模型输出分布定义为：
    ```
    P_erased(X) ∝ P_θ(X) * [P_θ(X|c⁺)/P_θ(X|c⁻)]^η
    ```
    其中 η 控制擦除强度。该公式源于贝叶斯规则和分类器自由引导思想。
  - **自分类损失**：将上述修改后的分布作为目标，通过交叉熵损失训练新模型参数 θ*：
    ```
    L_erase = CE(P_θ*(X), P_erased_θ)
    ```
  - **保留损失**：为了防止影响无关概念，额外使用一个保留数据集 D_retain（安全、无关文本），让模型保持原始输出：
    ```
    L_retain = CE(P_θ*(X), P_θ(X))
    ```
  - **流畅性损失**（仅对较小模型可选）：针对擦除数据集中的提示，用修改后的分布生成新文本，然后训练模型匹配这一生成，以维持对话连贯性：
    ```
    L_fluency = CE(P_θ*(生成文本), P_erased_θ(生成文本))
    ```
  - **低秩适配器**：使用 LoRA 对模型早期层（4-7层）进行微调，实现精确的局部知识修改，避免破坏整体能力。
- **算法流程**：1) 从要擦除的概念域获取文本 D_erase 和保留域 D_retain。2) 构造 c⁺ 和 c⁻ 前缀。3) 对每段文本，计算原始模型在三种前缀下的 logits，得到 P_erased。4) 用 LoRA 微调模型，最小化总损失 L_total = λ₁L_erase + λ₂L_retain + λ₃L_fluency。

## 3. 实验设计：数据集、基准、对比方法

- **数据集**：
  - **WMDP**: 生物安全（WMDP-bio, 5000文本片段）和网络安全（WMDP-cyber, 1000文本片段）的多选题（MCQ），用于评估擦除效果。
  - **Harry Potter 文学领域**：从小说中提取的 3000 文本片段，修改后的四选一 MCQ 数据集。
  - 保留数据集：WikiText 等通用文本。
- **基准（Benchmark）**：
  - **无辜性（Innocence）**：擦除后模型在目标概念 MCQ 上的准确率（期望接近随机 25%）。
  - **特异性（Specificity）**：在通用基准 MMLU 和 MT-Bench 上的性能。
  - **无缝性（Seamlessness）**：用独立模型（Llama3.1-8B）计算生成文本的反向困惑度（R-PPL）。
  - **鲁棒性（Robustness）**：GCG 对抗攻击、BEAST 攻击、微调攻击。
- **对比方法**：
  - RMU（表示误导遗忘），RepNoise（表示加噪），WHP（WhoIsHarryPotter 数据集过滤器）。
  - 同时与最新方法如 RR、TAR、K-FADE 进行了补充对比。
- **评估模型**：Zephyr-7B、Mistral-7B、Llama3-8B (Instruct)、Llama3-70B、Qwen2.5-32B、Llama2-7B-Chat。

## 4. 资源与算力

论文**未明确说明**使用了哪种 GPU 型号、数量以及训练时长。仅在附录中提到使用了低秩 LoRA 微调，训练一至两个 epoch，并提供了开源代码。因此关于精确算力消耗缺乏可溯源的描述。

## 5. 实验数量与充分性

- **实验数量**：相当充分。
  - 主要擦除实验：在 5 种以上模型上测试 WMDP 擦除，与 RMU、RepNoise 对比。
  - 文学领域擦除实验：在 Llama2-7B-Chat 上与 RMU、WHP 对比。
  - 消融实验：分别移除 L_erase, L_retain, L_fluency，并测试随机化替代方案。
  - 超参数分析：层选择、LoRA rank、η 的全面扫描。
  - 鲁棒性实验：GCG 攻击（最多 5000 步）、BEAST 攻击、微调攻击。
  - 内部探测：各层线性探针准确率、激活 norm 分析。
  - 新增对比：与 RR、TAR、K-FADE 进一步对比。
- **充分性与公平性**：
  - 实验设计全面，覆盖了已知主要基线，在多种模型上重复验证。
  - 消融实验清晰证明了各组件的重要性。
  - 但存在一定不足：在 Harry Potter 任务中，RMU 未经历充分超参数搜索（论文提及可能需要更大范围扫描），可能影响对比公平性。
  - 未报告多次运行的统计误差（计算开销大），但总体结论有足够支撑。

## 6. 论文的主要结论与发现

- ELM 能**有效擦除概念知识**，在 WMDP 生物/安全 MCQ 上达到接近随机水平（25% 左右），同时**保持通用能力**（MMLU 下降极小）。
- 相比基线方法，ELM 在**生成连贯性（低反向困惑度）和鲁棒性**上表现更优，尤其是大型模型（70B、32B）无需额外流畅损失即可保持自然对话。
- 良好的**对抗鲁棒性**：GCG 攻击 5000 步后仍无法诱导 ELM 模型生成擦除概念相关内容。
- 内部探测显示，擦除后模型的早期层激活分布发生偏移，但后期层恢复正常，说明知识被彻底移除而非隐藏。
- 消融表明，L_erase 是实现擦除的关键，L_retain 保护通用能力，L_fluency（中小模型）维持流畅度。

## 7. 优点：方法或实验设计的亮点

- **原则性目标**：基于模型的自主分类，避免了外部分类器或启发式规则的依赖，目标定义清晰。
- **同时满足三个要求**：该方法同时考虑了 innocence、specificity、seamlessness，并在实验中取得最佳平衡。
- **低秩高效**：使用 LoRA 在早期层微调，参数量少，训练快，且不会破坏模型整体能力。
- **可扩展性好**：在多个领域（生物安全、网络安全、文学）和多种模型（7B~70B）上验证，证明框架通用。
- **鲁棒性评估**：不仅做标准对抗攻击，还做了微调攻击，验证了概念擦除的持久性。
- **丰富的分析和消融**：超参数扫描、激活分析、逐层探测等，深入揭示了机制，增强了可信度。

## 8. 不足与局限

- **精确边界问题**：对语义相邻概念（如相关但安全的生物学知识）存在性能降级，说明擦除边界不够精细。
- **生成语义有时不连贯**：虽然反向困惑度低，但部分输出在语义上跳跃或无关，表明概率修改可能过于激进。
- **处理深度互联概念**：当概念之间高度纠缠时（如因果关系），擦除一个概念可能影响其他相关知道，论文提到需进一步研究。
- **计算资源未披露**：缺少 GPU 型号、训练时间等细节，可复现性打了折扣。
- **语言覆盖单一**：仅评估了英语知识擦除，未测试其他语言，可能存在跨语言偏移。
- **虚假安全感风险**：尽管鲁棒性测试通过，但完全可能存在未被发现的残留知识，不应依赖本方法作为唯一安全手段。
- **HP 任务基线不公平**：RMU 在此任务上未充分调参，可能低估了其性能，从而稍稍高估了 ELM 的优势。

（完）
