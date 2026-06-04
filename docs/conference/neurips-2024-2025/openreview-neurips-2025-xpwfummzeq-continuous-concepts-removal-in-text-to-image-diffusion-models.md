---
title: Continuous Concepts Removal in Text-to-image Diffusion Models
title_zh: 文本到图像扩散模型中的连续概念移除
authors: "Tingxu Han, Weisong Sun, Yanrong Hu, Chunrong Fang, Yonglong zhang, Shiqing Ma, Tao Zheng, Zhenyu Chen, Zhenting Wang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=xpwFuMmzeq"
tags: ["query:ce"]
score: 9.0
evidence: 文本到图像扩散模型中的连续概念移除
tldr: 现有概念移除方法在连续移除场景下会导致文本-图像对齐严重下降，本文提出CCRT方法，通过设计专门的机制解决连续移除中的累积偏差问题。实验表明CCRT在多次概念移除后仍能保持良好对齐，适用于实际动态需求。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1370, \"height\": 296, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 697, \"height\": 382, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1433, \"height\": 437, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1431, \"height\": 683, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 977, \"height\": 702, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 422, \"height\": 243, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 890, \"height\": 991, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 431, \"height\": 241, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1363, \"height\": 552, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1385, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1411, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1414, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1351, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1290, \"height\": 518, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-xpwfummzeq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1178, \"height\": 378, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpwfummzeq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1071, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpwfummzeq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1457, \"height\": 281, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpwfummzeq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 787, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpwfummzeq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 453, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpwfummzeq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1136, \"height\": 255, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpwfummzeq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1209, \"height\": 184, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpwfummzeq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1373, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-xpwfummzeq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1455, \"height\": 764, \"label\": \"Table\"}]"
motivation: 现有概念移除方法在需要连续移除多个概念时，文本提示与生成图像的对齐质量显著下降。
method: 提出CCRT方法，设计专门的机制来维护连续移除过程中的文本-图像对齐。
result: 实验证明CCRT在连续概念移除场景下优于现有方法，保持了对齐质量。
conclusion: 该方法使得概念移除更具实用性，可应对动态需求的应用场景。
---

## Abstract
Text-to-image diffusion models have shown an impressive ability to generate high-quality images from input textual descriptions/prompts. However, concerns have been raised about the potential for these models to create content that infringes on copyrights or depicts disturbing subject matter.
Removing specific concepts from these models is a promising solution to this issue. However, existing methods for concept removal do not work well in practical but challenging scenarios where concepts need to be continuously removed. Specifically, these methods lead to poor alignment between the text prompts and the generated image after the continuous removal process.
To address this issue, we propose a novel concept removal approach called CCRT that includes a designed knowledge distillation paradigm.
CCRT constrains the text-image alignment behavior during the continuous concept removal process by using a set of text prompts.
These prompts are generated through our genetic algorithm, which employs a designed fuzzing strategy. 
To evaluate the effectiveness of CCRT, we conduct extensive experiments involving the removal of various concepts, algorithmic metrics, and human studies.
The results demonstrate that CCRT can effectively remove the targeted concepts from the model in a continuous manner while maintaining the high image generation quality (e.g., text-image alignment).
The code of CCRT is available at https://github.com/wssun/CCRT.

---

## 论文详细总结（自动生成）

# 论文《Continuous Concepts Removal in Text-to-image Diffusion Models》详细中文总结

---

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题背景**：文本到图像扩散模型（如 Stable Diffusion）能够根据文本提示生成高质量图像，但可能被滥用于生成侵犯版权（如模仿特定艺术家风格）、有害（如暴力、色情）或涉及知识产权的内容。
- **现有方法不足**：已有概念移除方法（如训练数据过滤、微调编辑）在需要**连续移除多个不同概念**的现实场景中表现不佳。反复移除会导致“实体遗忘”（entity forgetting），即文本提示与生成图像之间的对齐质量严重恶化，模型无法准确理解未移除的实体（如“向日葵”）。
- **核心挑战**：如何在低成本下实现连续概念移除，同时保持模型对非目标概念的生成能力和文本-图像对齐。

## 2. 论文提出的方法论

### 核心思想
提出 **CCRT（Continuous Concepts Removal in Text-to-image Diffusion Models）**，基于**知识蒸馏范式**：将原始稳定扩散模型作为教师网络，编辑模型作为学生网络，同时实现概念移除（去除不想要的知识）和语义空间对齐（保留文本-图像对齐能力）。

### 关键技术细节
1. **概念移除损失**（`L_rm`）：基于 ESD 的负引导方向，量化移除概念 c 的噪声预测方向：
   ```
   Δc = ϵθ∗(xt, t) − η[ϵθ∗(xt, c, t) − ϵθ∗(xt, t)]
   L_rm = ∥ϵθ(xt, c, t) − Δc∥_p
   ```
   该损失使模型对包含概念 c 的提示不再预测出相关特征。

2. **对齐正则化损失**（`L_reg`）：利用一组**校准提示集**（calibration prompt set）约束学生网络的行为，使其在非目标实体（如“sunflower”）上的预测与教师网络一致：
   ```
   L_reg = MSE(ϵθ(xt, e, t), ϵθ∗(xt, e, t)), e ∈ E
   ```

3. **总目标**：
   ```
   min L = L_rm + λ · L_reg
   ```

4. **校准提示集生成**（关键创新）：
   - **动机**：随机选择实体进行蒸馏会导致语义空间对齐不稳定，需挖掘“最需要对齐的硬样本”。
   - **方法**：定义 **Misalignment Distance (MD)** 度量各实体上学生与教师模型的偏差，选择 MD 最高的实体。
   - **遗传算法 + 模糊策略**：
     - 初始实体集来自 ImageNet 类别。
     - 通过交叉（crossover）和变异-模糊（mutation_fuzzing）生成新实体。
     - 交叉规则：若实体有共同父类，则生成父类；否则组合为新个体。
     - 变异-模糊：利用 LLM（GPT-4）将实体替换为同义词或批量生成语义多样实体。
     - 迭代选择 MD 最高的前 k 个实体。
   - 最终用 LLM 将实体组合成语义连贯的文本提示，构成校准集。

### 算法流程
- **阶段 (a)**：生成校准提示集 → 初始化实体集 → 按 MD 排序选 top-k → 交叉+变异-模糊生成新实体 → 用 LLM 组合为文本提示。
- **阶段 (b)**：连续概念移除 → 每次移除新概念时，对模型进行蒸馏优化（总损失 L），教师网络固定，学生网络为上一轮编辑后的模型。

---

## 3. 实验设计

### 使用的数据集/场景
- **艺术风格移除**：Van Gogh → Picasso → Monet → Cezanne（连续 4 步）
- **不当内容移除**：Eroticism → Violence → Self-harm（连续 3 步），使用 I2P 数据集
- **知识产权移除**：Spider Man → Super Mario → Iron Man（连续 3 步）
- **对象移除**：Church → Tench → Parachute（连续 3 步）
- **跨域移除**：Van Gogh → BMW（验证不同语义类别的泛化）
- **不同移除顺序实验**：6 种排列测试鲁棒性
- **模型泛化**：SD v1.4 和 SD-XL

### 基准方法
- **强基线**：ESD、AdvUn（能有效移除概念但破坏对齐）
- **弱基线**：UCE、MACE、SPM（移除能力弱）
- 对比指标：RR-CLS（基于训练的二进制分类器）、RR-LLM（基于 GPT-4 的 in-context 评估）、CLIP-Score、VQA-Score、人类评估（11 位参与者，平均 150 次/人）

### 评估维度
- 概念移除效果（RR-CLS, RR-LLM）
- 文本-图像对齐（CLIP-Score, VQA-Score）
- 其他概念保留性（人类评估）
- 图像质量（人类评估）

---

## 4. 资源与算力

- 论文提到：“Each removal is a light fine-tune (≈3 GPU-hours)”，即每次概念移除约需 **3 GPU 小时**。
- 未明确说明 GPU 具体型号、数量、batch size 等详细硬件配置。
- 总训练时间取决于需要连续移除的概念数量（实验中最多 4 步，约 12 GPU 小时）。

---

## 5. 实验数量与充分性

- **实验数量丰富**：涵盖四大类概念移除（风格、不当内容、IP、对象），多种基线对比，连续多步（3-4 步），不同移除顺序，不同模型，消融实验，超参数 λ 敏感性分析。
- **消融实验**：移除蒸馏对齐（`L_reg`）、移除校准集生成（CSG）、移除遗传算法+模糊（GAF），分别验证各组件必要性。
- **人类研究**：11 名参与者，4 个维度打分（概念移除、文本-图像对齐、其他概念保留、图像质量），结果统计排名。
- **充分性判断**：实验设计较全面，自动化指标与人工评估相结合，对比方法覆盖主流 SOTA。但未报告误差棒或统计显著性检验（作者解释计算成本高），这一点略有不足。总体而言实验客观、公平。

---

## 6. 论文的主要结论与发现

- CCRT 在连续概念移除场景下显著优于所有现有方法。
  - 平均 RR-CLS 0.753，RR-LLM 0.874；相比次优方法 MACE 分别提升 0.347 和 0.724。
  - CLIP-Score 比 ESD 平均高约 3.3（从 21.698 提升至 25.005），VQA-Score 也明显领先。
- CCRT 能保持每步移除效果的持续性：移除后续概念时，先前移除概念的 RR 值不会大幅下降。
- 人类评估显示，CCRT 在所有四个维度上取得平衡（概念移除、对齐、保留、质量），而 ESD 虽移除能力强但严重破坏对齐。
- 方法适用于不同模型（SD v1.4, SD-XL）和不同类型概念，具有良好泛化性。

---

## 7. 优点

- **问题定义创新**：首次明确提出并形式化“连续概念移除”问题，更贴近实际需求（如艺术家持续投诉、用户不断报告有害内容）。
- **方法设计巧妙**：
  - 知识蒸馏范式同时实现移除和对齐，避免实体遗忘。
  - 遗传算法+模糊策略自动生成高质量校准提示集，解决了随机提示稳定性差的问题。
  - 利用 MD 度量自动挖掘“硬样本”，提升蒸馏效率。
- **实验全面深入**：多种概念、多种基线、自动+人工评估、消融与超参分析，验证充分。
- **代码开源**：便于复现和后续研究。

---

## 8. 不足与局限

- **模型类型局限**：仅研究了文本到图像扩散模型，未扩展到其他 AIGC 模型（如大语言模型、视频生成模型），作者在限制部分已指出此点。
- **计算资源细节缺失**：未明确 GPU 型号、batch size、优化器细节等，影响完全复现。
- **统计显著性未报告**：缺少误差棒和置信区间（作者解释为计算成本高），但可能影响结论的严谨性。
- **移除顺序影响**：虽然测试了 6 种顺序，但结论是 CCRT 基本鲁棒，未深入探讨可能存在的顺序效应机制。
- **实际应用挑战**：文中提到若需一次性移除数百个概念，从头训练可能更经济，暗示当前方法适用于概念逐个到达的场景，极端大规模场景未覆盖。
- **伦理风险**：虽然论文聚焦于移除不当概念，但移除技术也可能被恶意利用来审查合法内容或隐藏模型问题，需注意双刃剑效应。

---

（完）
