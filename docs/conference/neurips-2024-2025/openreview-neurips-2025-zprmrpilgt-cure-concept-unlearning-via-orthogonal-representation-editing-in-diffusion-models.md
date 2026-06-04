---
title: "CURE: Concept Unlearning via Orthogonal Representation Editing in Diffusion Models"
title_zh: CURE：通过正交表示编辑实现扩散模型的概念遗忘
authors: "Shristi Das Biswas, Arani Roy, Kaushik Roy"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=zprMrpiLgT"
tags: ["query:ce"]
score: 9.0
evidence: 扩散模型中的概念遗忘
tldr: 针对文本到图像扩散模型中不安全内容生成的问题，现有方法存在去除不彻底或计算开销大的缺陷。本文提出CURE，一种无需训练的概念遗忘框架，通过在权重空间中使用正交投影（光谱擦除器）直接抑制特定概念。该方法支持快速、可解释且高度特异性的概念移除，同时保持模型的其他生成能力。实验表明CURE在多个基准上实现了有效的概念擦除，且对模型其他能力的影响极小。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1163, \"height\": 839, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1381, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1091, \"height\": 549, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1445, \"height\": 730, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1171, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1094, \"height\": 242, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 672, \"height\": 257, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1449, \"height\": 419, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1446, \"height\": 517, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1165, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1165, \"height\": 553, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-zprmrpilgt/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1162, \"height\": 797, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-zprmrpilgt/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1450, \"height\": 434, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zprmrpilgt/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1442, \"height\": 399, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zprmrpilgt/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 484, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zprmrpilgt/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 712, \"height\": 261, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zprmrpilgt/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1444, \"height\": 397, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zprmrpilgt/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 863, \"height\": 388, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-zprmrpilgt/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1522, \"height\": 431, \"label\": \"Table\"}]"
motivation: 现有扩散模型的安全干预方法在概念移除上不彻底，易受越狱攻击或导致计算效率低下。
method: 提出训练无关的概念遗忘框架CURE，核心是光谱擦除器，通过闭式正交投影在权重空间中直接抑制目标概念。
result: 在多个扩散模型上，CURE有效擦除不安全概念，同时最小化对其他生成能力的影响。
conclusion: CURE提供了一种高效、可解释的概念擦除方法，可作为扩散模型的安全工具。
---

## Abstract
As Text-to-Image models continue to evolve, so does the risk of generating unsafe, copyrighted, or privacy-violating content. Existing safety interventions - ranging from training data curation and model fine-tuning to inference-time filtering and guidance - often suffer from incomplete concept removal, susceptibility to jail-breaking, computational inefficiency, or collateral damage to unrelated capabilities. In this paper, we introduce CURE, a training-free concept unlearning framework that operates directly in the weight space of pre-trained diffusion models, enabling fast, interpretable, and highly specific suppression of undesired concepts. At the core of our method is the Spectral Eraser, a closed-form, orthogonal projection module that identifies discriminative subspaces using Singular Value Decomposition over token embeddings associated with the concepts to forget and retain. Intuitively, the Spectral Eraser identifies  and isolates features unique to the undesired concept while preserving safe attributes. This operator is then applied in a single step update to yield an edited model in which the target concept is effectively unlearned - without retraining, supervision, or iterative optimization. To balance the trade-off between filtering toxicity and preserving unrelated concepts, we further introduce an Expansion Mechanism for spectral regularization which selectively modulates singular vectors based on their relative significance to control the strength of forgetting. All the processes above are in closed-form, guaranteeing extremely efficient erasure in only $2$ seconds. Benchmarking against prior approaches, CURE achieves a more efficient and thorough removal for targeted artistic styles, objects, identities, or explicit content, with minor damage to original generation ability and demonstrates enhanced robustness against red-teaming. Project Page at \url{https://sites.google.com/view/cure-unlearning/home}.

---

## 论文详细总结（自动生成）

# CURE：通过正交表示编辑实现扩散模型的概念遗忘

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：文本到图像（T2I）扩散模型（如 Stable Diffusion）在开放互联网数据集上训练，容易生成不安全、受版权保护或侵犯隐私的内容（如色情、暴力、特定艺术风格、名人肖像）。现有安全干预方法（训练数据筛选、模型微调、推理时过滤/引导）存在概念去除不彻底、易被越狱攻击、计算开销大或对无关能力造成附带损害等问题。
- **核心问题**：如何在不重新训练、不依赖推理时过滤的情况下，高效、精确、鲁棒地擦除模型中的特定概念，同时保持模型对其他内容的生成能力。
- **整体含义**：提出一种训练无关的闭式概念遗忘框架 CURE，通过直接修改模型权重空间实现快速、可解释、高特异性的概念抑制，为负责任的生成模型部署提供实用方案。

## 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：利用奇异值分解（SVD）对目标概念（遗忘集 F）和保留概念（保留集 R）的文本嵌入进行分解，构建正交子空间；通过闭式投影算子将嵌入空间的擦除操作吸收到交叉注意力权重中，实现单步权重更新，无需训练或迭代优化。
- **关键技术细节**：
  - **光谱擦除器（Spectral Eraser）**：
    - 对遗忘集 F 和保留集 R 的嵌入矩阵分别做 SVD：\( E_f = U_f \Sigma_f V_f^\top \), \( E_r = U_r \Sigma_r V_r^\top \)。
    - 构建能量加权的投影算子：\( P_f = U_f \Lambda_f U_f^\top \), \( P_r = U_r \Lambda_r U_r^\top \)，其中 \( \Lambda = \text{diag}(f(r_i; \alpha)) \) 是光谱扩展函数。
  - **光谱扩展机制（Spectral Expansion Mechanism）**：
    - 引入参数 α 控制每个奇异分量的加权强度。函数 \( f(r_i; \alpha) = \frac{\alpha r_i}{(\alpha-1)r_i + 1} \)，其中 \( r_i = \sigma_i^2 / \sum \sigma_j^2 \) 为归一化谱能量。α 越大，对弱分量的抑制越强，擦除越彻底。
  - **复合投影算子**：
    - 区分性子空间投影：\( P_{\text{dis}} = P_f - P_f P_r \)（从遗忘子空间中减去与保留子空间重叠的部分）。
    - 遗忘投影：\( P_{\text{unlearn}} = I - P_{\text{dis}} \)，作用于嵌入得到新嵌入 \( E_{\text{new}} = P_{\text{unlearn}} \cdot E \)。
  - **权重吸收**：将 \( P_{\text{unlearn}} \) 直接与交叉注意力层的键（K）和值（V）权重矩阵复合：\( W_k^{\text{new}} = W_k P_{\text{unlearn}} \), \( W_v^{\text{new}} = W_v P_{\text{unlearn}} \)，使得推理时所有嵌入自动被投影到擦除空间，无需运行时干预。
- **整体流程**：用户指定遗忘概念和可选保留概念 → 提取文本嵌入 → SVD分解 → 构造谱投影算子 → 单步更新交叉注意力权重 → 得到擦除后的模型（总耗时约2秒）。

## 3. 实验设计

- **使用的数据集/场景**：
  - **艺术家风格擦除**：5位古典艺术家（Van Gogh, Picasso等）和5位现代艺术家（Kelly McKernan, Thomas Kinkade等）；生成后使用 LPIPS 分数和 GPT-4o 分类评估。
  - **不安全内容擦除**：I2P 数据集（4703个真实提示，涵盖暴力、色情等）；使用 NudeNet（阈值0.6）检测裸体部位数量。
  - **对象擦除**：Imagenette 数据集（10个类，如“French Horn”等）；使用预训练 ResNet-50 计算分类准确率。
  - **身份擦除**：名人身份（如 John Wayne等）；使用 GIPHY 名人检测器评估。
  - **红队攻击鲁棒性**：使用 P4D、Ring-A-Bell、MMA-Diffusion、UnlearnDiffAtk 等白盒/黑盒攻击方法。
- **Benchmark 与对比方法**：
  - **训练后过滤方法**：SLD-Medium/Strong/Max (推理时安全引导)、SAFREE (推理时嵌入过滤)。
  - **基于训练的方法**：ESD (擦除概念)、SA (选择性遗忘)、CA (概念消融)、MACE (大规模概念擦除)、SDID (自发现潜在方向)。
  - **训练无关的模型编辑方法**：UCE (统一概念编辑)、RECE (可靠高效概念擦除)。
- **评估指标**：LPIPS（LPIPS_e 越高擦除越好，LPIPS_u 越低保留越好）、Acc_e/Acc_u（GPT-4o分类准确率）、FID、CLIP分数、裸体部位数量、攻击成功率（ASR）等。

## 4. 资源与算力

- 文中明确说明：实验使用 **NVIDIA A40 GPU（48GB显存）** 进行。
- **CURE 编辑时间**：约 **2 秒**（单步闭式更新）。
- **对比方法**：ESD 约 4500 秒，CA 约 484 秒，UCE 约 17 秒，RECE 约 37 秒，SLD/SAFREE 无需预修改但推理时额外开销。
- 未提及训练时长（因 CURE 无需训练），也未说明使用的 GPU 数量（推测单卡可完成）。

## 5. 实验数量与充分性

- **实验组数**：
  - 艺术家擦除：5×2 组（两种目标艺术家 + 多个未擦除艺术家评估）。
  - 不安全内容：在 I2P 全数据集（4703个提示）上评估，并报告8类裸体部位数量；此外在 Q16 分类器的7类（仇恨、骚扰等）上额外评估。
  - 对象擦除：10个 Imagenette 类逐个擦除，每个类生成500张图像。
  - 身份擦除：多个名人测试，定性展示。
  - 鲁棒性攻击：使用4种不同攻击方法（白盒+黑盒）评估 ASR。
  - 消融实验：光谱扩展参数 α 的消融（表6），多概念擦除的可扩展性（图6）。
  - 效率对比：表5比较编辑时间和推理时间。
- **充分性评价**：实验覆盖了主要的应用场景（艺术风格、不安全内容、对象、身份）和攻击维度，对比了多种代表性基线。消融实验验证了关键参数（α）的影响。定性结果也提供了直观佐证。整体实验设计较为全面，但部分实验未提供误差棒或统计显著性检验（作者注明遵循该领域惯例）。结论客观，未明显偏向自身方法。

## 6. 论文的主要结论与发现

- CURE 在**所有任务**上均实现了 **最低的擦除目标识别率**（Acc_e）和 **最低的裸体部位数量**，同时保持 **最高的未擦除内容保留性能**（Acc_u、FID、CLIP分数）。
- 在红队攻击鲁棒性上，CURE 的 **攻击成功率（ASR）** 显著低于所有训练无关方法，甚至优于多数训练方法。
- CURE 仅编辑模型 **2.23% 的参数**（交叉注意力层的 K/V 权重），修改时间约2秒，推理时间与原始模型相当，实现了效率与效果的最佳平衡。
- 光谱扩展参数 α 提供了可解释的擦除强度控制：α 增大 → 擦除更强但可能影响无关内容；α=2 为推荐默认值。

## 7. 优点

- **完全训练无关**：无需梯度更新、无需微调、无需迭代优化，只需单步闭式权重修改。
- **极高的效率**：整个擦除过程约2秒，推理时零额外开销；可在无法承担大算力的场景下快速部署。
- **高特异性与可解释性**：通过 SVD 分解构建正交子空间，显式分离遗忘概念和保留概念的特征方向；光谱扩展参数 α 提供直观的遗忘强度控制。
- **强鲁棒性**：对多种白盒/黑盒红队攻击表现出最低的 ASR，优于所有训练无关方法和多数训练方法。
- **广泛适用性**：支持单概念和多概念擦除，适用于艺术风格、不安全内容、对象、身份等多种场景；可扩展至擦除上千个概念（图6）。
- **透明性**：编辑算子可记录和验证，便于审计和负责任的发布。

## 8. 不足与局限

- **依赖文本嵌入质量**：投影算子的构建依赖 CLIP 文本编码器，若编码器对某些概念编码不充分（如抽象术语或多义词），擦除效果可能受影响。
- **超参数 α 的调优**：虽然提供了可解释的 α，但仍需用户根据任务手动选择，缺乏自动确定方法。
- **高对抗性提示可能泄露**：尽管鲁棒性大幅提升，但高度对抗性的提示仍可能触发部分概念泄漏，不能完全免疫所有攻击。
- **潜在的滥用风险**：可能被用于擦除取证水印或来源信号，作者建议结合提示过滤、沙盒执行和审计日志等防护措施。
- **未提供统计误差**：实验未报告置信区间或显著性检验，遵循领域惯例但可能影响结果泛化评估。
- **SVD 离线计算**：虽然 SVD 计算量小（毫秒级），但仍需对每个擦除概念执行，在大量概念频繁替换的场景下可能有累积开销（但作者指出这是离线一次性成本）。

（完）
