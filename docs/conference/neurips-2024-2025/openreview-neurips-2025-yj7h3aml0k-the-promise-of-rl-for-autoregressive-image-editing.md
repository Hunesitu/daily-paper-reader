---
title: The Promise of RL for Autoregressive Image Editing
title_zh: 强化学习在自回归图像编辑中的前景
authors: "Saba Ahmadi, Rabiul Awal, Ankur Sikarwar, Amirhossein Kazemnejad, Ge Ya Luo, Juan A. Rodriguez, Sai Rajeswar, Siva Reddy, Christopher Pal, Benno Krojer, Aishwarya Agrawal"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=YJ7H3amL0k"
tags: ["query:ce"]
score: 6.0
evidence: 用于文本引导图像编辑的自回归多模态模型
tldr: 文本引导图像编辑任务中，自回归多模态模型面临执行编辑指令困难的挑战。本文系统比较了监督微调、强化学习和思维链推理三种策略，并在统一的自回归多模态模型框架下进行研究。发现结合大型多模态语言模型验证器的强化学习最为有效。最终发布了EARL模型，在多个编辑基准上取得了显著改进。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1435, \"height\": 731, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1419, \"height\": 541, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 665, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1448, \"height\": 428, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1446, \"height\": 567, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1438, \"height\": 811, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1428, \"height\": 1085, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-yj7h3aml0k/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1442, \"height\": 1642, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1446, \"height\": 289, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1457, \"height\": 649, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1454, \"height\": 296, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1446, \"height\": 134, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1438, \"height\": 165, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1397, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1284, \"height\": 130, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1293, \"height\": 129, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1445, \"height\": 154, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1448, \"height\": 230, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1445, \"height\": 164, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1450, \"height\": 160, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1110, \"height\": 149, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1272, \"height\": 147, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 766, \"height\": 155, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 727, \"height\": 124, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-yj7h3aml0k/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1444, \"height\": 431, \"label\": \"Table\"}]"
motivation: 自回归模型在文本引导图像编辑中执行简单指令常失败，需要更好的训练策略。
method: 在统一的自回归多模态模型中，比较监督微调、强化学习和思维链推理三种策略。
result: 强化学习结合大型多模态验证器在编辑任务上取得最佳性能。
conclusion: 强化学习是提升自回归模型图像编辑能力的关键方法。
---

## Abstract
While image generation techniques are now capable of producing high-quality images that respect prompts which span multiple sentences, the task of text-guided image editing remains a challenge. Even edit requests that consist of only a few words often fail to be executed correctly. We explore three strategies to enhance performance on a wide range of image editing tasks: supervised fine-tuning (SFT), reinforcement learning (RL), and Chain-of-Thought (CoT) reasoning. In order to study all these components in one consistent framework, we adopt an autoregressive multimodal model that processes textual and visual tokens in a unified manner.
We find RL combined with a large multi-modal LLM verifier to be the most effective of these strategies.
As a result, we release **EARL**: **E**diting with **A**utoregression and **RL**, a strong RL-based image editing model that performs competitively on a diverse range of edits compared to strong baselines, despite using much less training data. Thus, EARL pushes the frontier of autoregressive multimodal models on image editing. We release our code, training data, and trained models at [https://github.com/mair-lab/EARL](https://github.com/mair-lab/EARL).

---

## 论文详细总结（自动生成）

# 中文论文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **研究动机**：文本引导的图像生成技术已有显著进展，但文本引导的图像编辑仍是一大挑战。即使是几个词的编辑指令也常常无法被正确执行。
- **背景**：现有主流的图像编辑模型多基于扩散模型，并依赖监督微调（SFT），很少采用强化学习（RL）等后训练方法。同时，链式推理（Chain-of-Thought, CoT）在语言任务中非常成功，但尚未系统地在图像编辑中应用。
- **核心目标**：在**统一的自回归多模态模型**框架下，系统比较**监督微调（SFT）**、**强化学习（RL）** 和**思维链推理（CoT reasoning）** 三种训练范式，找出提升图像编辑性能的最有效策略，并发布高性能编辑模型**EARL**（Editing with Autoregression and RL）。

## 2. 论文提出的方法论
- **基础模型**：Emu3-8B，一个完全自回归的多模态模型，统一处理文本和视觉 token，便于集成各种训练方法。
- **任务形式化**：输入为原始图像的视觉 token 序列和编辑指令的文本 token 序列，模型自回归地生成编辑后图像的视觉 token 序列。
- **三种训练范式**：
  - **监督微调（SFT）**：标准下一个 token 预测，最小化交叉熵损失，使用编辑指令-目标图像三元组。
  - **强化学习（RL）后训练**：采用 **GRPO（Group Relative Policy Optimization）**，每组生成多个候选编辑，使用验证器（verifier）计算奖励。优化目标包含优势估计和 KL 散度惩罚，以保持模型稳定性。
  - **思维链推理（CoT reasoning）**：在回答前生成详细的中间推理步骤（如目标区域、编辑计划等），通过 SFT 学习这些推理轨迹。
- **RL 验证器设计**：使用 **Qwen2.5-VL-72B** 多模态大模型，根据 VIEScore 的四个维度（编辑成功、过编辑、自然感、伪影）为每个编辑图像打分，聚合为 0~10 的奖励信号。
- **数据划分**：
  - **简单编辑（S）**：单对象/属性/风格改变（OmniEdit 750K 样本）。
  - **复杂编辑（C）**：计数、空间、动作等复杂操作（来自 HumanEdit、MagicBrush、VisMin、Aurora、SomethingSomething 等，共 171K 样本，上采样至 300K）。
  - CoT 推理数据由 Qwen2.5-VL-72B 通过 few-shot 提示和边界框标注自动生成。

## 3. 实验设计
- **数据集/场景**：
  - **简单编辑**：OmniEdit、EmuEdit（OOD）。
  - **复杂编辑**：MagicBrush、AURORA、I2EBench（OOD）、VisMin（从理解基准转为编辑基准）。
- **评估指标**：**VIEScore**（GPT4o-mini 作为评测模型），四个子维度（编辑成功、过编辑、自然感、伪影），分数 0~10。已验证与人类判断具有合理相关性（Spearman 约 0.4-0.5）。
- **对比方法**：
  - 扩散模型基线：MagicBrush、InstructPix2Pix、Aurora、Omnigen（SOTA 开源）。
  - 自回归基线：EditAR（唯一同类工作）。
- **实验设置**：6 个公开基准，IID 和 OOD 场景，使用统一评测协议。

## 4. 资源与算力
- 训练细节（附录 F.2 表格）：
  - **模型**：Emu3-8B。
  - **GPU 配置**：8×A100L GPU（SFT 阶段与 RL 阶段共用）。
  - **训练时长**：总计约 108 小时（SFT ~ 60 小时，RL ~ 48 小时）。
  - **数据量**：SFT 约 750K 样本，RL 约 32K 样本（每次迭代 16 个唯一样本 × 8 次 rollout）。
- 对比：Omnigen 使用 104×A800 GPU 和约 4M 编辑样本，训练资源需求远高于 EARL。

## 5. 实验数量与充分性
- **实验组数量**：论文报告了超过 15 组不同配置的实验，包括：
  - SFT 变体：SFT(S)、SFT(S+C)、SFT(S+C) two-stage。
  - RL 变体：RL(S)、RL(C)、RL(S+C) 不同数据组合。
  - CoT 变体：SFT think(S)、SFT think(S+C) two-stage、RL 后训练。
  - 扩展实验：Best-of-N 采样、不同验证器选择、训练步长扩展。
- **充分性与公平性**：
  - 在相同基模型（Emu3）上统一比较，控制变量。
  - 对比了当前所有主流方法（扩散与自回归），使用相同评测指标（VIEScore）。
  - 进行了性能分解（四个子维度）和细粒度类别分析（如计数、空间、动作等）。
  - 进行了消融实验（验证器大小、数据混合策略、推理阶段采样）。
- **结论**：实验覆盖全面，对比公平，统计量充分，足以支持主要结论。

## 6. 主要结论与发现
1. **RL post-training 是最有效的策略**，显著提升编辑质量，尤其在复杂编辑上（计数、空间、动作）。SFT(S) → RL(S+C) 配置在所有基准上平均 VIEScore 达到 4.80，超越 Omnigen（4.70）和所有基线。
2. **复杂编辑在 SFT 阶段引入有害**，但在 RL 阶段有益。混合复杂数据训练 SFT 会降低简单编辑性能，而 RL 阶段加入复杂数据能在不牺牲简单编辑性能的同时提升复杂编辑。
3. **CoT reasoning 并未带来改进**，甚至可能降低性能。即使 RL 后训练也无法弥补，表明当前自回归模型在交错图像-文本生成上存在瓶颈。
4. **EARL 数据效率高**：使用约 750K 编辑样本（Omnigen 使用约 4M），达到相当甚至更优性能。
5. **强验证器至关重要**：Qwen2.5-VL-72B 验证器显著优于 7B 版本（小验证器导致 RL 崩溃）。

## 7. 优点
- **方法论统一性**：首次在自回归多模态框架下系统比较 SFT、RL 和 CoT，提供了可复现的训练配方。
- **RL 管线设计巧妙**：采用 GRPO + 强 MLLM 验证器（Qwen2.5-VL-72B），避免了偏好标注，可利用冻结验证器提供细粒度奖励。
- **数据效率高**：仅用 Omnigen 约 1/5 的编辑数据即达到 SOTA 水平，降低了训练成本。
- **推理速度有优势**：相比 Omnigen 的 200 秒/50 样本，EARL 仅需 52.7 秒（256×256），速度快约 4 倍。
- **开源可复现**：公开代码、数据、模型权重，遵循学术协议。
- **分析深入**：不仅报告总分，还分解 VIEScore 四维度和细粒度编辑类别，揭示不同策略的优劣。

## 8. 不足与局限
- **数据覆盖不完整**：训练数据依赖合成数据和公开数据集，对于长尾概念（如特定文化物品、科学图表）可能表现脆弱。
- **RL 验证器存在偏置**：Qwen2.5-VL-72B 在复杂编辑（尤其是高计数变化、细微动作）上评分不稳定，可能继承其训练数据的偏差（如种族、性别刻板印象）。
- **CoT 推理失败原因未彻底阐明**：论文推测是由于模型缺乏交错图像文本预训练，但未提供更深入的实验验证或补救方案。
- **计算资源门槛仍较高**：尽管数据效率提升，但仍需要 8×A100L GPU，对中小实验室不友好。
- **未见部署安全措施**：模型可能被用于生成误导性内容或深度伪造，论文仅指出风险但未提供实际防护机制（如内容过滤）。
- **评估指标局限性**：VIEScore 依赖 GPT4o-mini，虽然相关性与人类一致，但绝对分数范围较窄（0-10），对于微小质量差异可能不敏感。
- **实验未覆盖所有编辑类型**：如文本编辑（OCR）涉及较少，动作编辑在 AURORA 上未见提升（可能因 SFT 基础太弱）。
- **推理效率对比**：虽然比 Omnigen 快，但仍慢于纯扩散基线（如 MagicBrush，23.6 秒 vs. 52.7 秒），实时应用仍有挑战。

（完）
