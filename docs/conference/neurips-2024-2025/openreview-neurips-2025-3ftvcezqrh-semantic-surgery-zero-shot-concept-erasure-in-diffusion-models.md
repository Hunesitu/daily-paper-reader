---
title: "Semantic Surgery: Zero-Shot Concept Erasure in Diffusion Models"
title_zh: 语义手术：扩散模型中的零样本概念擦除
authors: "Lexiang Xiong, Liu Chengyu, Jingwen Ye, YAN LIU, Yuecong Xu"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=3FTVceZQrh"
tags: ["query:ce"]
score: 9.0
evidence: 通过嵌入中和实现扩散模型中的零样本概念擦除
tldr: 文本到图像扩散模型可能生成有害内容，现有概念擦除方法常损害生成能力。本文提出Semantic Surgery，一种训练无关的零样本概念擦除框架，直接在文本嵌入阶段动态检测并中和目标概念。该方法在概念出现之前从语义根源移除其影响，提高了擦除的完整性和局部性。实验证明，在多个概念擦除任务中，该方法在保持生成质量的同时有效消除了目标概念。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1461, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1383, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1089, \"height\": 1300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1289, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1296, \"height\": 738, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1306, \"height\": 956, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1098, \"height\": 788, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1378, \"height\": 1808, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1443, \"height\": 1043, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1332, \"height\": 1573, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1348, \"height\": 485, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-3ftvcezqrh/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1346, \"height\": 481, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ftvcezqrh/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1447, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ftvcezqrh/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1429, \"height\": 885, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ftvcezqrh/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1177, \"height\": 433, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ftvcezqrh/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 984, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ftvcezqrh/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 198, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ftvcezqrh/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1062, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ftvcezqrh/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1080, \"height\": 454, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ftvcezqrh/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 972, \"height\": 224, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-3ftvcezqrh/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1421, \"height\": 1887, \"label\": \"Table\"}]"
motivation: 现有概念擦除方法要么需要重训练，要么在擦除时损害生成能力。
method: 提出Semantic Surgery，在扩散之前对文本嵌入进行动态中和操作，实现零样本概念擦除。
result: 在多个概念擦除基准上，该方法在保持生成质量的同时有效擦除了目标概念。
conclusion: Semantic Surgery提供了一种高效且无损的训练无关概念擦除方案。
---

## Abstract
With the growing power of text-to-image diffusion models, their potential to generate harmful or biased content has become a pressing concern, motivating the development of concept erasure techniques. Existing approaches, whether relying on retraining or not, frequently compromise the generative capabilities of the target model in achieving concept erasure.

Here, we introduce **Semantic Surgery**, a novel training-free framework for zero-shot concept erasure. Semantic Surgery directly operates on text embeddings *before* the diffusion process, aiming to neutralize undesired concepts at their semantic origin with dynamism to enhance both erasure completeness and the locality of generation. Specifically, Semantic Surgery dynamically estimates the presence of target concepts in an input prompt, based on which it performs a calibrated, scaled vector subtraction to neutralize their influence at the source. The overall framework consists of a Co-Occurrence Encoding module for robust multi-concept erasure and a visual feedback loop to address latent concept persistence, thereby reinforcing erasure throughout the subsequent denoising process.

Our proposed Semantic Surgery requires no model retraining and adapts dynamically to the specific concepts and their intensity detected in each input prompt, ensuring precise and context-aware interventions. Extensive experiments are conducted on object, explicit content, artistic style, and multi-celebrity erasure tasks, demonstrating that our method significantly outperforms state-of-the-art approaches. That is, our proposed concept erasure framework achieves superior completeness and robustness while preserving locality and general image quality (e.g., achieving a 93.58 H-score in object erasure, reducing explicit content to just 1 instance with a 12.2 FID, and attaining an 8.09 H_a in style erasure with no MS-COCO FID/CLIP degradation). Crucially, this robustness enables our framework to function as a built-in threat detection system by monitoring concept presence scores, offering a highly effective and practical solution for safer text-to-image generation.

Our code is publicly available at: https://github.com/Lexiang-Xiong/Semantic-Surgery

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

文本到图像扩散模型在生成高质量图像的同时，可能产生有害、侵权或偏见内容（如色情、版权风格、名人肖像）。现有概念擦除方法主要分为两类：

- **参数修改方法**（如 ESD、UCE、Receler、MACE）：通过微调或去学习（unlearning）修改模型权重。这类方法通常需要大量计算资源，且容易发生灾难性遗忘，导致生成能力下降；其防御是静态的，难以适应概念变体。
- **推理时方法**（如 SLD、SAFREE）：不修改模型参数，通过引导或在中间层干预实现擦除。但现有方法多在 token 级别或注意力层面操作，难以彻底消除目标概念，且无法有效处理“潜在概念持续性”（LCP）——即概念因 U-Net 先验而在语义移除后仍被生成。

本文提出 **Semantic Surgery**，一种**训练无关的零样本概念擦除框架**，在扩散过程开始前直接操作**全局文本嵌入**，通过动态估计概念存在强度并进行**校准向量减法**，从根源上中和目标概念，同时通过**共现编码**和**视觉反馈循环**分别解决多概念擦除和 LCP 问题。目标是同时实现高**完整性**（完整擦除目标概念）和高**局部性**（对非目标概念影响最小），并具备对提示变体的鲁棒性。

### 2. 论文提出的方法论：核心思想、关键技术细节

**核心思想**：利用 CLIP 文本编码器嵌入空间的**线性结构**（如词向量类比），通过向量算术操纵语义。对于给定输入提示嵌入 \(e_{\text{input}}\) 和目标概念方向 \(\Delta e_{\text{erase}}\)，理想擦除公式为 \(e'_{\text{input}} = e_{\text{input}} - \rho \Delta e_{\text{erase}}\)，其中 \(\rho\) 为概念存在强度（0 或 1）。

**关键技术细节**：

1. **语义活检（Semantic Biopsy）**：  
   动态估计每个目标概念在输入提示中的存在概率 \(\hat{\rho}\)。通过计算输入嵌入与概念方向的余弦相似度 \(\alpha_c = \cos(e_{\text{input}}, \Delta e_{\text{erase}})\)，然后经 sigmoid 校准映射到概率值：
   \[
   \hat{\rho}(\alpha_c) = \sigma\!\left(\frac{\alpha_c - \beta}{\gamma}\right)
   \]
   其中 \(\beta\) 为决策阈值，\(\gamma\) 控制陡峭程度。该设计基于**统计可分离性假设**：含概念与不含概念的 \(\alpha_c\) 分布可分离（附录 E.2 实验验证），从而保证高置信度估计。

2. **共现编码（Co-Occurrence Encoding）**：  
   针对多概念擦除，简单累加各概念方向会导致语义重叠区域的过度擦除。本文通过**存在顺序拼接**构建联合提示 \(p_{\text{co}} = \LARGE{\Lsh}_{c_i \in C_{\text{active}}} p_{c_i}\)，再计算联合方向 \(\Delta e_{\text{co}} = \phi(p_{\text{co}}) - e_n\)。最终手术操作为：
   \[
   \hat{e}'_{\text{input}} = e_{\text{input}} - \hat{\rho}_{\text{joint}} \Delta e_{\text{co}}
   \]
   其中 \(\hat{\rho}_{\text{joint}} = \max_{c_i \in C_{\text{active}}}\{\hat{\rho}_i\}\)，\(C_{\text{active}} = \{c_i \mid \hat{\rho}_i \ge \tau\}\)（\(\tau=0.5\)）。

3. **视觉反馈循环（Visual Feedback for LCP Mitigation）**：  
   即使语义手术已移除概念，U-Net 先验仍可能导致概念“再现”（LCP）。本文引入可选的二阶段机制：首先生成图像，用视觉检测器（如 NudeNet、AOD）检查是否仍有目标概念残留。若检测到，则根据检测分数 \(\hat{\rho}_{\text{im}}\) 更新活跃概念集，并执行更强的手术：
   \[
   \hat{e}'_{\text{final}} = e_{\text{input}} - \hat{\rho}^{*}_{\text{joint}} \Delta e^{*}_{\text{co}}
   \]
   理论分析（定理 3）证明该操作可降低 LCP 风险。

**算法流程**（文字描述）：  
给定输入提示 \(p\)，通过 CLIP 文本编码器获得嵌入 \(e_{\text{input}}\)。逐目标概念计算余弦相似度 \(\alpha_c\)，经 sigmoid 得到存在分数 \(\hat{\rho}_i\)。筛选活跃概念集 \(C_{\text{active}}\)（阈值 \(\tau\)）。若非空，拼接活跃概念提示，获得联合方向 \(\Delta e_{\text{co}}\) 和联合强度 \(\hat{\rho}_{\text{joint}}\)，执行向量减法得到初步擦除嵌入。可选地，生成初始图像并用视觉检测器检查 LCP；若检测到残留，更新目标集并重新计算方向与强度，施加第二次手术。最终嵌入送入扩散模型生成图像。

### 3. 实验设计

| 任务 | 数据集/场景 | 评估指标 | 对比方法 |
|------|------------|----------|----------|
| 对象擦除（Object Erasure） | CIFAR-10 10 类，每个类擦除目标概念。含简单提示和 ChatGPT 生成释义提示。 | Acc_E（有效性，越低越好）、Acc_R（鲁棒性，越低越好）、Acc_L（局部性，越高越好）、H-score（调和平均，越高越好） | ESD-x, ESD-u, UCE, AC, Receler, MACE |
| 显式内容去除（Explicit Content） | I2P 数据集（4703 个提示），擦除 “nude, naked, sexual, erotic”。 | NudeNet 检测的敏感部位实例数、MS-COCO 30k 的 FID↓ 和 CLIP↑ | SD v1.4, SD v2.1, AC, ESD-u, ESD-x, UCE, Receler, MACE, SLD, SAFREE |
| 艺术风格擦除（Artistic Style） | Image Synthesis Style Studies 数据库，200 位艺术家（100 擦除组 + 100 保留组）。 | CLIP_e（有效性，越低越好）、CLIP_s（特异性/局部性，越高越好）、Ha = CLIP_s - CLIP_e（越高越好）、FID-30k↓、CLIP-30k↑ | AC, UCE, ESD-x, ESD-u, Receler, MACE |
| 多概念名人擦除（Celebrity Erasure） | MACE 提供的 200 位名人（100 擦除组 + 100 保留组），分别擦除 1/5/10/100 个名人。 | Accuracy_e（擦除组正确率越低越好）、Accuracy_s（保留组正确率越高越好）、Hc（调和平均）、FID-30k↓、CLIP-30k↑ | MACE, ESD-u, SLD-M, UCE, ESD-x, Receler, AC |
| 对抗鲁棒性（Adversarial Robustness） | 黑盒攻击 RAB（380 条提示）、白盒攻击 UnlearnDiffAtk。 | ASR（攻击成功率，越低越好） | SLD, SAFREE, MACE, Receler |

所有实验基于 **Stable Diffusion v1.4**，DDIM 采样器 50 步。超参数：\(\gamma=0.02\)，\(\tau=0.5\)，各任务 \(\beta\) 不同（-0.12 至 -0.06），LCP 模块仅在对象擦除和显式内容任务中使用（使用对应视觉检测器）。

### 4. 资源与算力

- **文中明确**：推理时间实验在单张 **NVIDIA RTX 4090 GPU** 上运行 50 步采样。
- **具体耗时**（附录 B 表 7）：
  - 基线 SD v1.4：3.11 秒/图
  - 本文（LCP 禁用）：3.21 秒/图
  - 本文（LCP 平均在 I2P 上）：4.09 秒/图
  - 其他推理时方法（SLD/SAFREE）约 4 秒/图
- **未说明**：参数修改方法的训练算力（如 ESD、MACE 等），因为本文方法本身无需训练。整体上，本文方法的算力需求与现有推理时方法相当，远超参数修改方法的效率。

### 5. 实验数量与充分性

- **实验组数**：覆盖 5 个大类任务，每个任务下有多组对比（对象擦除含 10 个子类，每个类独立评估；名人擦除含 4 个擦除数量；风格擦除含 100 位艺术家）。此外包含消融研究（视觉反馈的消融、超参数敏感性分析）和对抗鲁棒性测试。
- **充分性**：实验设计较为充分，采用了**标准基准数据集**（CIFAR-10、I2P、MS-COCO）和**广泛使用的基线**（包含参数修改和推理时两类）。**公平性**：对象擦除使用独立检测器 OWL-ViT 避免评估偏差；风格和名人任务直接使用 MACE 提供的设置和数据以保证可比性；对抗测试使用了流行攻击框架。
- **局限性**：所有实验仅在 **SD v1.4** 上进行，未在 SDXL 或 SD3 等更现代模型上验证；对象擦除仅覆盖 CIFAR-10 的 10 个简单类别，未测试更复杂的自然对象集；显式内容仅依赖 NudeNet 一个检测器。

### 6. 论文的主要结论与发现

- **对象擦除**：平均 H-score **93.58**，比最佳对比方法 Receler（88.74）高 4.84。特别在鲁棒性（Acc_R）上，本文 **2.00%**，远低于 MACE（13.80%）和 Receler（10.00%），表明对释义提示有极强抵抗力。
- **显式内容去除**：仅生成 **1** 个裸体实例（NudeNet 检测），远优于次优方法 ESL-u（55）和 MACE（123）。FID 达 **12.2**，甚至优于原始 SD v1.4（14.04），表明未损害图像质量。
- **艺术风格擦除**：Ha 达 **8.09**，是唯一同时保持 CLIP_s 接近原始模型（28.84 vs 28.90）且无 MS-COCO FID/CLIP 下降的方法，优于 MACE（Ha=5.99）。
- **多概念名人擦除**：擦除 100 位名人时 Hc ≈ **0.965**，远高于 MACE（0.892），且 FID/CLIP 几乎不变，而其他方法（如 UCE）在擦除 10+ 概念时急剧退化。
- **对抗鲁棒性**：黑盒攻击 ASR **1.05%**（MACE 3.95%，统计显著 p=0.0089），白盒攻击 ASR **0.0%**。本文方法可作为内置威胁检测系统。
- **关键发现**：训练无关的推理时操作，通过对全局文本嵌入进行动态、校准的向量减法，可以达到甚至超越参数修改方法的效果，特别是在**鲁棒性**和**局部性**上优势显著。视觉反馈模块对处理 LCP 至关重要。

### 7. 优点

- **训练无关与零样本**：无需重新训练，可即时适应新概念，计算开销低。
- **动态自适应**：根据每个输入提示的概念强度动态调整擦除力度，避免静态防御。
- **高完整性与局部性平衡**：理论保证了完整性（定理 4）、局部性（定理 5）和鲁棒性（定理 6）；实验验证了优异的平衡。
- **共现编码**：优雅解决多概念擦除中的语义重叠问题，防止过度擦除。
- **视觉反馈机制**：有效应对潜在概念持续性（LCP），进一步强化擦除。
- **内置威胁检测**：通过监控概念存在分数可检测对抗攻击，提供额外安全层。
- **可解释性**：操作在语义空间进行，几何意义明确（向量减法）。
- **实验结果充分且强于 SOTA**：在四个标准任务和一个对抗测试中均取得最优或领先成绩，尤其是鲁棒性方面远超同类方法。

### 8. 不足与局限

- **依赖编码器线性结构**：方法假设 CLIP 嵌入具有良好线性可分性，对于高度抽象或隐喻概念（如“怀旧”）可能失效；对非线性编码器（如未来架构）需重新适配。
- **超参数敏感性**：\(\beta\) 和 \(\gamma\) 需根据任务人工调整（论文提供了经验选择方法，但未完全自动化），\(\tau\) 虽在 0.05~0.5 稳定，但极端值影响性能。
- **视觉检测器依赖**：LCP 模块的性能高度受限于外部检测器（如 NudeNet、AOD）的精度，误报会损伤局部性，漏报会导致擦除不彻底。对抽象风格等无可靠检测器的任务无法启用。
- **仅评估 SD v1.4**：未在 SDXL、SD3 等新模型上验证，泛化性未知。
- **对象擦

- **仅评估 SD v1.4**：未在 SDXL、SD3 等新模型上验证，泛化性未知。  
- **对象擦除任务仅使用 CIFAR-10**：类别的语义较为简单且容易分离，在更复杂的自然对象上（如不同品种的狗、细微物体）效果有待验证。  
- **未测试非英文提示**：方法依赖 CLIP 文本编码器，对于英文之外的语种可能存在嵌入空间差异，影响擦除可靠性。  
- **对抽象/隐喻概念失效风险**：当概念难以通过单一文本方向线性表示（如“怀旧”、“恐怖”等抽象情感）时，向量减法可能无法准确中和语义。  
- **未考虑提示工程绕过**：虽然方法对释义提示鲁棒，但未系统测试对抗性提示改写（如使用同义词替换、句法变换）是否能绕过擦除。  
- **可组合性限制**：当目标概念与保留概念的语义高度纠缠（如同时擦除“狗”和“动物”），共现编码可能无法完全避免局部性下降。  

（完）
