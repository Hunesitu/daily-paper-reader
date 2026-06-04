---
title: Erasing Undesirable Concepts in Diffusion Models with Adversarial Preservation
title_zh: 通过对抗保留擦除扩散模型中的不期望概念
authors: "Anh Tuan Bui, Long Tung Vuong, Khanh Doan, Trung Le, Paul Montague, Tamas Abraham, Dinh Phung"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=GDz8rkfikp"
tags: ["query:ce"]
score: 9.0
evidence: 基于对抗保留的扩散模型概念擦除
tldr: 针对扩散模型生成有害内容的问题，本文提出对抗性概念保留方法，识别并保护受参数变化影响最大的概念，在擦除目标概念的同时最小化对其他概念的负面影响。实验表明该方法在有效去除不需要概念的同时保持了模型对其他概念的良好生成能力。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1429, \"height\": 452, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1158, \"height\": 625, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1158, \"height\": 626, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1384, \"height\": 607, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1364, \"height\": 588, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1384, \"height\": 2012, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1433, \"height\": 757, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1454, \"height\": 1538, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1456, \"height\": 1540, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1455, \"height\": 1537, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1456, \"height\": 1539, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1435, \"height\": 1250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1434, \"height\": 1250, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-gdz8rkfikp/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1435, \"height\": 1255, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-gdz8rkfikp/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1018, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gdz8rkfikp/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 874, \"height\": 234, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gdz8rkfikp/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 798, \"height\": 375, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gdz8rkfikp/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1018, \"height\": 273, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gdz8rkfikp/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1389, \"height\": 1980, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gdz8rkfikp/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1022, \"height\": 284, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gdz8rkfikp/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 875, \"height\": 144, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-gdz8rkfikp/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 875, \"height\": 262, \"label\": \"Table\"}]"
motivation: 扩散模型可能生成有害内容，现有概念擦除方法难以平衡擦除效果与对其他概念的影响。
method: 提出对抗性概念保留，识别受参数变化影响最大的概念并在擦除过程中加以保护。
result: 实验证明该方法能在有效擦除目标概念的同时保持对其他概念的生成质量。
conclusion: 该方法为扩散模型概念擦除提供了更好的权衡方案，具有实用价值。
---

## Abstract
Diffusion models excel at generating visually striking content from text but can inadvertently produce undesirable or harmful content when trained on unfiltered internet data. A practical solution is to selectively removing target concepts from the model, but this may impact the remaining concepts. Prior approaches have tried to balance this by introducing a loss term to preserve neutral content or a regularization term to minimize changes in the model parameters, yet resolving this trade-off remains challenging. In this work, we propose to identify and preserving concepts most affected by parameter changes, termed as *adversarial concepts*. This approach ensures stable erasure with minimal impact on the other concepts. We demonstrate the effectiveness of our method using the Stable Diffusion model, showing that it outperforms state-of-the-art erasure methods in eliminating unwanted content while maintaining the integrity of other unrelated elements. Our code is available at \url{https://github.com/tuananhbui89/Erasing-Adversarial-Preservation}.

---

## 论文详细总结（自动生成）

# 论文中文详细总结

## 1. 核心问题与整体含义（研究动机与背景）

- **问题**：文本到图像扩散模型（如Stable Diffusion）在未过滤的互联网数据上训练，能够生成高质量图像，但也可能输出有害内容（如色情、暴力、种族歧视）。现有方法通过微调模型来擦除目标概念，但擦除一个概念往往会损害模型对其他概念的生成能力，存在擦除效果与保留性能之间的根本性权衡。
- **现有方法的不足**：先前工作（ESD、UCE、Concept Ablation等）通常依赖于保留一个中性概念（如“a photo”）或使用正则化项来限制参数变化，但这些策略并不最优。实验表明，中性概念位于敏感性频谱的中间位置，而擦除目标概念对高度相关概念（如“nudity”对“women”“person”）的影响远大于对中性概念的影响。因此，固定保留中性概念无法有效维护模型整体性能。

## 2. 提出的方法论

### 核心思想
引入**对抗性概念保留（Adversarial Preservation）**：在每次参数更新前，识别当前模型中对参数变化最敏感的（即受影响最大）概念——称为“对抗性概念”（adversarial concept），并在擦除目标概念的同时显式保护该概念，从而最小化对其他概念的副作用。

### 关键技术细节
- **搜索敏感概念**：由于概念空间是离散的（文本词汇），直接遍历所有概念成本过高。论文采用**Gumbel-Softmax技巧**对离散分布进行连续松弛，将搜索转化为在概率单纯形上的最大化问题。
- **优化目标**：一个min-max双层优化公式：

  \[
  \min_{\theta'} \max_{\pi \in \Delta_R} \mathbb{E}_{c_e \in E}\left[ \|\epsilon_{\theta'}(c_e) - \epsilon_\theta(c_n)\|_2^2 + \lambda \|\epsilon_{\theta'}(G(\pi) \odot R) - \epsilon_\theta(G(\pi) \odot R)\|_2^2 \right]
  \]
  - 外层最小化：擦除目标概念（迫使输出接近中性概念）并保留对抗性概念。
  - 内层最大化：在剩余概念空间 \(R\) 中搜索使保留损失最大的对抗性概念 \(c_a\)。
- **算法流程**（伪代码在 Algorithm 1 & 2）：
  1. 固定当前模型参数，通过梯度上升更新概率向量 \(\pi\) 以最大化保留损失，得到 \(c_a = G(\pi^*) \odot R\)。
  2. 固定对抗性概念，更新模型参数以最小化擦除损失+保留损失。

## 3. 实验设计

### 场景与数据集
- **物体概念擦除**：使用Imagenette数据集（10个易识别类别），选择4组不同的5个类作为擦除目标，生成500张图像/类，用预训练ResNet-50检测对象是否存在。
- **不道德内容擦除（NSFW）**：使用I2P prompts生成4703张图像，利用Praneet检测器识别暴露身体部位，同时用COCO 30K prompts和FID评估保留质量。
- **艺术风格擦除**：选择四位艺术家（Kelly McKernan, Thomas Kinkade, Tyler Edlin, Kilian Eng），使用长文本prompt+5个种子生成200张图像/艺术家，评估CLIP score和LPIPS。

### 基准方法
- ESD (Gandikota et al., 2023)
- UCE (Gandikota et al., 2024)
- Concept Ablation (CA) (Kumari et al., 2023)
- 原始SD模型作为上界参考

### 评估指标
- **擦除性能**：ESR-k（物体检测的擦除成功率）、NER（NSFW图像比例）、CLIP score（艺术风格）。
- **保留性能**：PSR-k（物体检测的保留成功率）、FID、LPIPS（图像感知距离）、CLIP score。

## 4. 资源与算力

- **硬件**：1张NVIDIA A100 GPU（80GB显存）。
- **训练时间**：
  - 擦除“nudity”（需微调所有非交叉注意力模块）耗时少于6小时。
  - 擦除其他概念（仅微调交叉注意力模块）耗时少于1小时。
- 训练步数：1000步，batch size=1，Adam优化器，学习率1e-5。

## 5. 实验数量与充分性

- **实验组数**：涵盖三大场景（物体、NSFW、艺术风格），每个场景均有多组设置（物体擦除有4组不同5类组合；NSFW有不同阈值下的NER；艺术风格有4位艺术家）。
- **消融实验**：分析了超参数 \(K\)（候选概念数）、\(N_{iter}\)（搜索步数）的影响；比较了不同搜索空间（Oxford 3000 vs CLIP token vocabulary）；研究了微调模块（交叉注意力 vs 非交叉注意力）的影响。
- **充分性评价**：实验设计较为全面，覆盖主要应用场景，并提供了统计误差（标准差）。但缺乏在更大规模数据集（如完整ImageNet）上的验证，以及对抗性搜索的计算成本分析。

## 6. 主要结论与发现

- 擦除不同目标概念会对其他概念产生**不同的影响**，固定保留中性概念并非最优策略。最敏感的概念往往是与目标概念高度相关的概念。
- 所提出的对抗性概念保留方法在**所有场景下均优于或持平于现有方法**，尤其在保留性能上显著提升（例如物体擦除中PSR-5从66.5%提升到79.9%；NSFW擦除中NER-0.3降至3.64%）。
- 方法具有灵活性，可扩展至不同擦除任务，且Gumbel-Softmax使得搜索过程连续可微，能够生成有意义的视觉对抗概念。

## 7. 优点

- **创新性强**：首次将对抗性搜索引入概念擦除，从“保留什么”的角度解决问题，突破了依赖中性概念或固定正则化的范式。
- **方法合理**：基于实证分析（中性概念敏感性中等），实验验证充分。
- **实现技术上**：使用Gumbel-Softmax对离散概念空间进行连续优化，兼顾了搜索效率和生成有意义概念的能力。
- **实验客观**：在多个标准数据集和指标上与主流方法公平对比，提供了误差棒和消融分析。

## 8. 不足与局限

- **计算开销**：每次参数更新前需执行内部最大化搜索（\(N_{iter}\)步），即使使用小批量候选概念（\(K=50\)或100），仍比无搜索的方法耗时更长。
- **搜索空间限制**：需要预定义一个概念词汇表（如Oxford 3000或CLIP token），可能遗漏某些对擦除任务重要的概念；词汇表的选择对结果有影响（表7中CLIP词汇保留性能更好）。
- **NSFW擦除的复杂性**：必须微调非交叉注意力模块才能取得较好效果，这导致训练更耗时且参数变化范围更大，增加了模型整体被破坏的风险。
- **缺乏通用擦除度量**：论文指出当前擦除性能度量（如CLIP score、检测器）仍存在局限性，例如CLIP在NSFW内容上训练不足。没有提出更完善的评估标准。
- **模型和数据集规模**：仅基于Stable Diffusion v1.4和相对较小的数据集（Imagenette、I2P），在更现代模型（如SDXL）或更大概念空间上的泛化性未验证。
- **潜在偏差**：搜索得到的对抗性概念可能偏向于词汇表中高频或相似度高的概念，导致对低频概念的保留不足。

（完）
