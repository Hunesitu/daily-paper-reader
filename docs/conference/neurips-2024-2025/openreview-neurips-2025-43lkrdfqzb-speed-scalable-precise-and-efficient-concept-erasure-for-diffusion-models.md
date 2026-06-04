---
title: "SPEED: Scalable, Precise, and Efficient Concept Erasure for Diffusion Models"
title_zh: SPEED：可扩展、精确、高效的扩散模型概念擦除方法
authors: "Ouxiang Li, Yuan Wang, Xinting Hu, Houcheng Jiang, Tao Liang, Yanbin Hao, Guojun Ma, Fuli Feng"
date: 2025-05-10
pdf: "https://openreview.net/pdf?id=43lkrdfQzB"
tags: ["query:ce"]
score: 7.0
evidence: 扩散模型的概念擦除
tldr: 为了解决扩散模型中概念擦除的效率和精度问题，本文提出SPEED方法，通过搜索零空间直接编辑模型参数，使得参数更新不影响非目标概念，从而实现对多个目标概念的可扩展、精确擦除。实验表明，SPEED在保持生成质量的同时有效擦除了目标概念。
source: NeurIPS-2025-Rejected-Public
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1445, \"height\": 547, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 698, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 677, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 474, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 734, \"height\": 383, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 649, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1419, \"height\": 2188, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1156, \"height\": 400, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1441, \"height\": 450, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-43lkrdfqzb/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1044, \"height\": 317, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 711, \"height\": 716, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 712, \"height\": 717, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 706, \"height\": 367, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1442, \"height\": 306, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 709, \"height\": 291, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1444, \"height\": 1301, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1013, \"height\": 819, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1012, \"height\": 830, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1442, \"height\": 340, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1011, \"height\": 719, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1439, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1150, \"height\": 241, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-43lkrdfqzb/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1149, \"height\": 206, \"label\": \"Table\"}]"
motivation: 现有概念擦除方法要么耗时且难以精确擦除多个概念，要么因优化目标冲突而降低非目标概念生成质量。
method: 搜索模型参数的零空间，在该空间内直接编辑参数，使更新只影响目标概念而不影响非目标概念。
result: 在多个数据集上，SPEED实现了高效、精确的概念擦除，同时保持了非目标概念的生成质量。
conclusion: SPEED提供了一种可扩展的概念擦除范式，可直接应用于大规模扩散模型。
---

## Abstract
Erasing concepts from large-scale text-to-image (T2I) diffusion models has become increasingly crucial due to the growing concerns over copyright infringement, offensive content, and privacy violations. In scalable applications, fine-tuning-based methods are time-consuming to precisely erase multiple target concepts, while real-time editing-based methods often degrade the generation quality of non-target concepts due to conflicting optimization objectives. To address this dilemma, we introduce SPEED, an efficient concept erasure approach that directly edits model parameters. SPEED searches for a null space, a model editing space where parameter updates do not affect non-target concepts, to achieve scalable and precise erasure. To facilitate accurate null space optimization, we incorporate three complementary strategies: Influence-based Prior Filtering (IPF) to selectively retain the most affected non-target concepts, Directed Prior Augmentation (DPA) to enrich the filtered retain set with semantically consistent variations, and Invariant Equality Constraints (IEC) to preserve key invariants during the T2I generation process. Extensive evaluations across multiple concept erasure tasks demonstrate that SPEED consistently outperforms existing methods in non-target preservation while achieving efficient and high-fidelity concept erasure, successfully erasing 100 concepts within just 5 seconds.

---

## 论文详细总结（自动生成）

# 论文总结：SPEED: Scalable, Precise, and Efficient Concept Erasure for Diffusion Models

## 1. 核心问题与整体含义

- **研究动机**：大规模文本到图像（T2I）扩散模型（如Stable Diffusion）生成内容可能涉及版权侵权、不当内容或隐私泄露，因此需要“概念擦除”（concept erasure）——让模型不再生成特定目标概念（如某角色、风格、名人）。但擦除时必须尽量不影响非目标概念的生成质量（即prior preservation）。
- **现有困境**：
  - **训练型方法**（如ConAbl、MACE）：效果较好但计算成本高，多概念擦除时耗时严重。
  - **编辑型方法**（如UCE、RECE）：效率高，但多概念时擦除与保留目标冲突，导致非目标概念语义退化，且存在非零保留误差下界。
- **本文目标**：提出**SPEED**，一种可扩展、精确、高效的编辑型概念擦除方法，能在秒级擦除多达100个概念，同时保持非目标概念的高生成质量。

## 2. 方法论：核心思想与关键技术

### 2.1 核心思想
- **零空间约束模型编辑**：寻找保留集（retain set）特征矩阵的零空间（null space），将所有参数更新限制在此零空间内，使得更新对非目标概念的输出无影响（保留误差严格为零），从而避免编辑型方法中的累积误差。
- **难点**：保留集过大时，特征矩阵接近满秩，零空间维度趋近于零，导致无法找到精确零空间，只能近似，从而引入语义退化。

### 2.2 关键技术：Prior Knowledge Refinement（先验知识精炼）
为解决上述难题，提出三项互补策略：

- **Influence-based Prior Filtering (IPF)**：
  - 定义“prior shift”指标（ ∥Δ_erase c∥₂ ），量化每个非目标概念受擦除影响的程度。
  - 仅保留影响程度大于均值的非目标概念，从而减小保留集规模，防止矩阵满秩，保证零空间精度。

- **Directed Prior Augmentation (DPA)**：
  - 对保留集中高影响概念，利用参数矩阵W的最小变化方向（通过SVD获取）生成定向噪声，产生语义一致的增广嵌入，增强保留集覆盖范围，同时避免随机增广引入无效噪声。
  - 增广后再次经过IPF过滤。

- **Invariant Equality Constraints (IEC)**：
  - 识别生成过程中的不变嵌入（如[SOT] token和null-text embedding），这些嵌入不应因擦除而改变。
  - 在优化目标中显式添加等式约束 (ΔP)C₂ = 0，通过拉格朗日乘子法导出闭式解。

### 2.3 算法流程（文字说明）
1. 构建擦除集C₁（目标概念）、锚定集C*（目标应映射到的概念）、保留集C₀（非目标概念）。
2. 计算投影矩阵P：对保留集协方差矩阵 C₀C₀ᵀ 进行SVD，取零奇异值对应的奇异向量构成正交基，得到投影矩阵。
3. 应用IPF、DPA、IEC对保留集精炼，得到R_refine，重新计算P。
4. 求解带等式约束的最小二乘问题，得到参数更新Δ，最终应用项目到模型参数 W’ = W + ΔP。

## 3. 实验设计

### 3.1 任务与数据集
- **少概念擦除**：实例擦除（如Snoopy, Mickey, SpongeBob）和艺术风格擦除（如Van Gogh, Picasso, Monet）。使用80个实例模板和30个风格模板，每模板生成10张图。非目标概念选取语义相近的（如Pikachu, Hello Kitty; Paul Gauguin, Caravaggio）。另用MS-COCO前1000个描述评估通用知识保留。
- **多概念擦除**：擦除10/50/100位名人（celebrity erasure），保留集为另外100位名人。使用GIPHY Celebrity Detector评估top-1准确率，计算擦除准确率Acc_e、保留准确率Acc_r及调和均值Ho。
- **隐式概念擦除**：在I2P基准（4703个不当提示）上擦除“nudity”，用NudeNet检测裸露部位数量。

### 3.2 对比方法
- ConAbl、MACE、RECE、UCE，以及附加对比SPM（含/不含Facilitated Transport模块）。所有方法使用默认配置。

### 3.3 评价指标
- CLIP Score (CS)：文本-图像相似度，用于衡量擦除效果（越低越好）和保留效果（越高越好）。
- Fréchet Inception Distance (FID)：衡量生成分布与原始模型分布的差异，用于量化保留质量（越低越好）。
- GCD准确率（Acc_e, Acc_r）及调和均值Ho。

## 4. 资源与算力

- 所有实验在单张 **A100 GPU** 上完成。
- 编辑型方法（包括SPEED）非常高效：擦除100个概念仅需 **5秒**，对比MACE约需30分钟（约350倍加速）。训练型方法需额外数据准备时间（例如ConAbl预采样1000张，MACE需8张图+8个分割掩码）。

## 5. 实验数量与充分性

- **少概念擦除**：独立擦除1~3个目标，汇报每个目标及非目标、MS-COCO的CS与FID，共数十组结果。
- **多概念擦除**：分别擦除10/50/100名人，包含500张生成图像评估，并与所有基线对比。
- **隐式概念擦除**：单一配置（nudity→空），报告检测计数和MS-COCO质量。
- **消融实验**：对IEC、IPF、DPA（含与随机增广对比）逐一消融；调节增广次数与秩；对比编辑键/值矩阵；对比IPF中重要性度量（prior shift vs. 文本相似度）。
- **跨模型迁移**：在DreamShaper、RealisticVision（合成概念擦除）、SDXL（知识编辑）、SDv3（DiT架构）上验证泛化性。
- **全面性**：实验覆盖主要任务、不同规模、多模型架构，消融设计合理。但缺乏对攻击鲁棒性的评估（文中仅在局限中提到）。

## 6. 主要结论与发现

1. **SPEED在保留非目标概念质量上一致优于所有基线**，在少概念和多概念场景均有最低FID和最高Acc_r。
2. **擦除效果足够但不过度**：CS并非最低，但足以成功擦除（定性图显示被擦除对象不再可辨识），而过度擦除（如RECE）会破坏非目标知识。
3. **可扩展性出色**：从1个到100个目标概念，保留质量退化远小于UCE/RECE等编辑型方法，与训练型方法MACE持平或更好，且速度极快。
4. **组件有效性**：IPF、IEC、DPA均贡献显著，三者组合达到最佳保留效果。
5. **跨模型迁移成功**：在主流T2I模型（DreamShaper, RealisticVision, SDXL, SDv3）上均能有效擦除并保持生成质量。

## 7. 优点

- **创新性**：将零空间约束引入扩散模型概念擦除，从根本上解决编辑型方法的累积保留误差。
- **高效性**：闭式解+直接参数编辑，单GPU秒级擦除上百概念，适合实际部署。
- **精确性**：通过精炼保留集和约束不变嵌入，实现了零保留误差，避免了语义退化。
- **可扩展性**：无需修改算法即可从单个概念扩展到大规模多概念，且性能稳定。
- **实验全面**：覆盖三种不同擦除任务，跨模型验证，消融分析详实。

## 8. 不足与局限

- **擦除效果温和**：擦除不够激进（如RECE），在某些极端对抗场景下可能存在残留痕迹（作者自述）。对于要求绝对不可恢复的擦除，可能需要结合其他手段。
- **依赖零空间近似**：奇异值阈值需手动调节（实验中采用10⁻¹或10⁻⁴），不同任务需调优，泛化性受限。
- **鲁棒性未评估**：未测试对针对擦除的对抗攻击（如white-box攻击绕过SPEED），而对比方法SPM的Facilitated Transport被指出易被绕过。
- **实验公平性讨论**：与SPM对比时，SPM使用了动态缩放（Facilitated Transport）进行推理时干预，SPEED仅做参数编辑，虽公平对比了SPM无FT版本，但整体比较仍存争议。
- **计算资源说明不完整**：仅提及单GPU和耗时，未报告具体显存占用、内存、CPU等细节。

（完）
