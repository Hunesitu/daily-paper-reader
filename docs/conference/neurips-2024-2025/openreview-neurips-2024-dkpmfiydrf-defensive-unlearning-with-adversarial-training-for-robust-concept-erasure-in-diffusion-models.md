---
title: Defensive Unlearning with Adversarial Training for Robust Concept Erasure in Diffusion Models
title_zh: 面向稳健概念擦除的防御性遗忘与对抗训练
authors: "Yimeng Zhang, Xin Chen, Jinghan Jia, Yihua Zhang, Chongyu Fan, Jiancheng Liu, Mingyi Hong, Ke Ding, Sijia Liu"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=dkpmfIydrF"
tags: ["query:ce"]
score: 9.0
evidence: 扩散模型中的概念擦除结合对抗训练
tldr: 该论文针对扩散模型在概念擦除后面临的对抗性提示攻击问题，提出了AdvUnlearn框架，将对抗训练融入机器遗忘中。通过在遗忘过程中同时优化无概念和有概念样本上的对抗损失，使模型在擦除敏感概念后仍能抵御对抗攻击。实验结果表明该方法在保持图像质量的同时显著提升了鲁棒性。这项工作为概念擦除的安全部署提供了重要保障。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 666, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 604, \"height\": 584, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 571, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 875, \"height\": 256, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 875, \"height\": 260, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 875, \"height\": 227, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 882, \"height\": 392, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 812, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1452, \"height\": 809, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 893, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-dkpmfiydrf/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 883, \"height\": 560, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 574, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 591, \"height\": 235, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 592, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 591, \"height\": 220, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 873, \"height\": 180, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 874, \"height\": 203, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 872, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 946, \"height\": 192, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 519, \"height\": 239, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1018, \"height\": 387, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 876, \"height\": 251, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 622, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-dkpmfiydrf/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 874, \"height\": 154, \"label\": \"Table\"}]"
motivation: 扩散模型概念擦除技术易受对抗提示攻击，导致已擦除概念被重新生成。
method: 提出AdvUnlearn，将对抗训练融入机器遗忘过程，联合优化遗忘损失和对抗损失。
result: 在各种概念擦除任务上，AdvUnlearn显著提升了对抗鲁棒性，同时保持了生成质量。
conclusion: 对抗训练能有效增强概念擦除的鲁棒性，为安全部署提供了新思路。
---

## Abstract
Diffusion models (DMs) have achieved remarkable success in text-to-image generation, but they also pose safety risks, such as the potential generation of harmful content and copyright violations. The techniques of machine unlearning, also known as concept erasing, have been developed to address these risks. However, these techniques remain vulnerable to adversarial prompt attacks, which can prompt DMs post-unlearning to regenerate undesired images containing concepts (such as nudity) meant to be erased. This work aims to enhance the robustness of concept erasing by integrating the principle of adversarial training (AT) into machine unlearning, resulting in the robust unlearning framework referred to as AdvUnlearn. However, achieving this effectively and efficiently is highly nontrivial. First, we find that a straightforward implementation of AT compromises DMs’ image generation quality post-unlearning. To address this, we develop a utility-retaining regularization on an additional retain set, optimizing the trade-off between concept erasure robustness and model utility in AdvUnlearn. Moreover, we identify the text encoder as a more suitable module for robustification compared to UNet, ensuring unlearning effectiveness. And the acquired text encoder can serve as a plug-and-play robust unlearner for various DM types. Empirically, we perform extensive experiments to demonstrate the robustness advantage of AdvUnlearn across various DM unlearning scenarios, including the erasure of nudity, objects, and style concepts. In addition to robustness, AdvUnlearn also achieves a balanced tradeoff with model utility. To our knowledge, this is the first work to systematically explore robust DM unlearning through AT, setting it apart from existing methods that overlook robustness in concept erasing. Codes are available at https://github.com/OPTML-Group/AdvUnlearn.

Warning: This paper contains model outputs that may be offensive in nature.

---

## 论文详细总结（自动生成）

## 论文中文总结

### 1. 论文的核心问题与整体含义

扩散模型在文本到图像生成中取得巨大成功，但其训练数据来自互联网，容易在不当提示下生成有害内容（如色情、版权风格）。为此，研究者提出**概念擦除**（即机器遗忘）来移除模型对特定敏感概念的生成能力。然而，现有概念擦除方法在面对**对抗性提示攻击**时极其脆弱：攻击者对输入提示施加微小扰动即可绕过擦除，使模型重新生成应被禁止的内容。论文旨在解决这一安全漏洞，首次系统性地将**对抗训练**融入机器遗忘，提出 **AdvUnlearn** 框架，在擦除概念的同时显著提升对对抗提示的鲁棒性，并保持模型正常的图像生成质量。

### 2. 论文提出的方法论

- **核心思想**：基于**双层优化**（BLO）框架，将对抗训练与概念擦除统一。上层优化实现遗忘（通过 ESD 等损失），下层优化生成对抗提示以最大化攻击效果，二者交替进行，使模型在对抗环境中仍能维持遗忘效果。
- **关键技术细节**：
  - **上層优化目标**：常规 ESD 损失会与 AT 结合导致生成质量严重下降。为此引入**效用保持正则化**：额外构建保留提示集 $C_{\text{retain}}$（经 LLM 过滤掉与被擦除概念相关的提示），添加一项 $\gamma \mathbb{E}_{\tilde{c} \sim C_{\text{retain}}} \left\| \epsilon_\theta(x_t|\tilde{c}) - \epsilon_{\theta_o}(x_t|\tilde{c}) \right\|_2^2$ 惩罚生成退化，平衡鲁棒性与效用。
  - **下层攻击生成**：采用 K 步迭代优化（如 30 步）生成对抗前缀向量，最大化攻击损失。也可使用**快速对抗训练**（1 步 FGSM）加速。
  - **模块选择**：对比发现，优化**文本编码器**比优化 UNet 更有效，且鲁棒性提升的同时仅带来轻微效用损失；获得的鲁棒文本编码器可即插即用到其他扩散模型（SD v1.5, DreamShaper, Protogen）。
- **算法流程**（文字说明）：
  1. 对当前模型参数，随机初始化对抗软提示嵌入 $\delta_0$。
  2. 通过 K 步梯度下降优化 $\delta$（目标为攻击损失最小化）。
  3. 用优化后的对抗提示计算 ESD 损失，并行抽取保留集中一批提示计算正则化损失。
  4. 联合损失反向传播更新文本编码器（或 UNet）参数。
  5. 重复迭代至收敛。

### 3. 实验设计

- **数据集与场景**：
  - **裸体擦除**：测试集来自 I2P 数据集中的敏感提示；效用评估用 COCO 数据集（10k 提示生成 10k 图像）。
  - **风格擦除**：擦除“梵高风格”，测试用 WikiArt 相关攻击；效用评估用 COCO。
  - **对象擦除**：擦除“教堂”“垃圾车”“降落伞”“丁鳜”等，测试用 GPT-4 生成的 50 个对象相关提示；效用同 COCO。
- **基准方法**：ESD, FMN, AC, UCE, SalUn, SH, ED, SPM 等 8 种开源 DM 遗忘方法。
- **评估指标**：
  - **鲁棒性**：攻击成功率（ASR），使用 UnlearnDiffAtk 作为默认攻击方法（并额外测试 CCE, PEZ, PH2P）。
  - **效用**：FID（越低越好）和 CLIP Score（越高越好）。

### 4. 资源与算力

论文明确提及在单个 **NVIDIA RTX A6000 GPU** 上进行实验。标准 AT（30 步攻击）每迭代耗时 78.57 秒，快速 AT（1 步 FGSM）每迭代 12.13 秒。未提供总训练迭代次数或总时长，也未说明多卡并行情况；但可推断实验以单卡为基础完成。

### 5. 实验数量与充分性

- **主要实验组**：裸体、风格、对象三种擦除任务各 1 个主表（共 3 表），对象擦除扩展至 3 个额外类别（共 6 种对象）。
- **消融与对比实验**：
  - 正则化权重敏感性（图 A3）
  - 保留集来源与 LLM 过滤影响（表 A3）
  - 不同对抗策略（替换/添加/前缀，表 A4）
  - 不同测试时攻击类型（表 A5、表 9）
  - 文本编码器层数影响（图 8）
  - 即插即用迁移到 SD v1.5、DreamShaper、Protogen（表 8）
  - 快速 AT 与标准 AT 对比（表 4）
  - 扩展对比 SH、ED 等（表 A1）
- **充分性评价**：实验场景覆盖常见概念擦除（有害内容、风格、对象），对比方法全面，消融深入，评价指标标准。但未涉及更大规模模型（如 SD v2、v3）或更广泛攻击（如黑盒攻击）；未做统计显著性检验（误差条未报告，原因是计算成本高）。

### 6. 论文的主要结论与发现

- 直接整合 AT 到遗忘会严重损害图像生成效用，而 AdvUnlearn 通过效用保持正则化有效平衡了鲁棒性与效用。
- **文本编码器**是比 UNet 更适合进行鲁棒化的模块，且可跨模型即插即用。
- 快速 AT 可大幅缩短训练时间，但会牺牲部分鲁棒性，适用于计算资源紧张场景。
- 在裸体、梵高风格、多种对象擦除任务上，AdvUnlearn 均取得最低的攻击成功率（ASR），同时保持与原始 SD 相近的 FID/CLIP 分数，大幅优于现有基线（如 SalUn 鲁棒性强但效用差，ESD 效用好但鲁棒性弱）。

### 7. 优点

- **创新性**：首次将对抗训练系统引入扩散模型机器遗忘领域，提出双层优化框架。
- **实用性**：发现的文本编码器即插即用特性大幅降低部署成本，快 AT 提供灵活的速度‑精度折衷。
- **实验全面**：涵盖多种概念擦除任务、多种攻击方法、多种基线，消融实验充分，验证了设计选择的有效性。
- **开源可用**：提供代码，便于复现和进一步研究。

### 8. 不足与局限

- **计算效率**：K 步攻击生成显著增加训练时间；快速 AT 虽加速但鲁棒性下降，仍需更高效的方案。
- **实验覆盖**：仅测试了 SD v1.4 及其衍生模型，未验证在更大/更现代模型（如 SD v2, SDXL）上的表现；攻击类型仅限于白盒前缀扰动，未考虑黑盒或物理世界攻击。
- **保留集构建**：依赖 LLM 过滤提示，可能引入主观偏差，且保留集大小固定（243 条），泛化性有待检验。
- **统计意义**：未提供误差条或置信区间，实验结果的稳定性未完全量化。
- **潜在滥用**：论文主要关注防御，但其方法可能被用于增强模型对有益概念的擦除，需注意伦理边界。

（完）
