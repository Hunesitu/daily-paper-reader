---
title: "EraseAnything: Enabling Concept Erasure in Rectified Flow Transformers"
title_zh: "EraseAnything: 在整流流变换器中实现概念擦除"
authors: "Daiheng Gao, Shilin Lu, Wenbo Zhou, Jiaming Chu, Jie Zhang, Mengxi Jia, Bang Zhang, Zhaoxin Fan, Weiming Zhang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=vvBAZJh2nQ"
tags: ["query:ce"]
score: 9.0
evidence: 首个针对整流流变换器的概念擦除方法
tldr: 针对现有概念擦除技术无法迁移到最新流匹配架构的问题，提出EraseAnything，将概念擦除建模为双层优化，采用LoRA参数调整和注意力引导，在Stable Diffusion v3和Flux上有效擦除概念并保持生成质量，为最新文本到图像范式提供了首个概念擦除方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 771, \"height\": 609, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 792, \"height\": 293, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 722, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 715, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 584, \"height\": 876, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 730, \"height\": 756, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 711, \"height\": 503, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1440, \"height\": 972, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1415, \"height\": 1270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1381, \"height\": 632, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1771, \"height\": 720, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 518, \"height\": 359, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 496, \"height\": 357, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1153, \"height\": 740, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1343, \"height\": 628, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1724, \"height\": 1943, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1578, \"height\": 2176, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1559, \"height\": 929, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1573, \"height\": 1134, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-vvbazjh2nq/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1619, \"height\": 1448, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-vvbazjh2nq/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 850, \"height\": 240, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vvbazjh2nq/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1595, \"height\": 475, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vvbazjh2nq/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 836, \"height\": 332, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vvbazjh2nq/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1364, \"height\": 270, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vvbazjh2nq/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 658, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vvbazjh2nq/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1482, \"height\": 507, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vvbazjh2nq/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1594, \"height\": 593, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-vvbazjh2nq/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1598, \"height\": 1108, \"label\": \"Table\"}]"
motivation: 现有概念擦除技术无法直接迁移到最新流匹配架构。
method: 将概念擦除建模为双层优化，采用LoRA参数调整和注意力引导。
result: 在Stable Diffusion v3和Flux上有效擦除概念并保持生成质量。
conclusion: 为最新文本到图像范式提供了首个概念擦除方法。
---

## Abstract
Removing unwanted concepts from large-scale text-to-image (T2I) diffusion models while maintaining their overall generative quality remains an open challenge. This difficulty is especially pronounced in emerging paradigms, such as Stable Diffusion (SD) v3 and Flux, which incorporate flow matching and transformer-based architectures. These advancements limit the transferability of existing concept-erasure techniques that were originally designed for the previous T2I paradigm (e.g., SD v1.4). In this work, we introduce EraseAnything, the first method specifically developed to address concept erasure within the latest flow-based T2I framework. We formulate concept erasure as a bi-level optimization problem, employing LoRA-based parameter tuning and an attention map regularizer to selectively suppress undesirable activations. Furthermore, we propose a self-contrastive learning strategy to ensure that removing unwanted concepts does not inadvertently harm performance on unrelated ones. Experimental results demonstrate that EraseAnything successfully fills the research gap left by earlier methods in this new T2I paradigm, achieving state-of-the-art performance across a wide range of concept erasure tasks.

---

## 论文详细总结（自动生成）

# EraseAnything: 在整流流变换器中实现概念擦除

## 1. 论文的核心问题与整体含义

**研究动机**：大规模文本到图像（T2I）扩散模型（如Stable Diffusion、Flux）在训练过程中学习了大量在线数据，存在生成不安全内容（如NSFW）的风险。现有概念擦除方法（如ESD、UCE、EAP）主要针对Stable Diffusion v1.4/v1.5这类基于DDPM+U-Net的旧范式设计，无法直接迁移到最新的流匹配（flow matching）加Transformer架构（如Stable Diffusion v3和Flux）。这些架构采用了T5文本编码器、旋转位置编码（RoPE）、双流/单流块等新组件，导致传统方法失效。

**核心问题**：能否为Flux这类新范式提出一种鲁棒的概念擦除方法？

**整体含义**：本文提出EraseAnything，据称是**第一个**专门面向流匹配T2I框架的概念擦除方法，填补了该领域的研究空白。方法通过双层优化（bi-level optimization）在擦除目标概念的同时保持无关概念的生成质量，并在多种擦除任务上达到当前最优性能。

## 2. 方法论

**核心思想**：将概念擦除建模为双层优化问题。下层专注于擦除目标概念（unlearned concepts），上层确保无关概念（irrelevant concepts）的生成质量不受影响。使用LoRA进行参数高效微调，并引入注意力图正则化和反向自对比损失。

**关键技术细节**：

- **注意力定位**：通过分析Flux架构，发现虽然Flux没有显式交叉注意力层，但其双流块中通过拼接文本和图像隐层特征，使得注意力图`W_attn`中存在文本token与图像区域的对应关系。通过定位目标概念的token索引，可以获取对应的激活特征`F_un`。

- **下层优化（概念擦除）**：
  - 采用ESD损失函数：`L_esd = E[ || v_{θ0+Δθ}(x_t, c_un, t) - η( v_{θ0}(x_t, c_un, t) - v_{θ0}(x_t, ∅, t) ) ||^2 ]`，其中`η`为负引导因子，`v`为流匹配中的速度。
  - 添加注意力图正则化：`L_attn = sum_{idx=start}^{end} F_un_idx`，通过抑制目标token的注意力权重来削弱其激活。为防止过拟合，每一轮迭代中随机打乱提示词的词序。

- **上层优化（无关概念保护）**：
  - 使用LoRA微调：`L_lora = E[ || v - v_{θ0+Δθ}(u_t, c, t) ||^2 ]`，其中`u_t`为加噪后的图像隐码，`v`为真实速度。
  - **反向自对比损失（Reverse Self-Contrastive Loss, RSC）**：利用LLM（GPT-4o）为目标概念生成K个无关概念（`F_ir`）和一个近义词（`F_syn`）。损失函数为：
    `L_rsc = log( sum_{i=0}^K exp( F_un·F_ki / τ ) / exp( F_un·F_syn / τ ) )`
    该损失使得目标概念的特征与无关概念对齐，同时推开近义词特征，从而弱化模型对目标概念的敏感性。温度`τ=0.07`。

- **双层优化整合**：
  - 下层：`Δθ* = argmin L_esd + L_attn`，针对目标概念`c_un`。
  - 上层：`min L_lora + L_rsc`，同时优化无关概念`c_ir`。
  - 整体算法流程（Algorithm 1）：从`D_un`中采样提示词，构建句子、打乱词序、定位token索引；下层更新LoRA；上层获取无关概念和近义词并替换，再次更新LoRA。迭代M步。

- **无关概念采样**：利用AI Agent（GPT-4o）生成三个类别的无关词（“no relation”、“far”、“mid”），再通过NLTK生成近义词。

## 3. 实验设计

**数据集与场景**：

- **裸体擦除**：使用I2P数据集（4703个不当提示），用NudeNet检测显式内容（阈值0.6）；MS-COCO 10K验证集评估FID和CLIP分数。
- **实体/抽象/关系擦除**：各选择10个概念（见表7），包括具体物体（足球、汽车等）、艺术风格（毕加索等）、关系（握手、亲吻等）。使用CLIP分类准确率评估擦除效果（Acc_e）、无关概念保留（Acc_ir）和近义词泛化（Acc_g）。
- **名人擦除**：从CelebA子集中选择100个名人（50个擦除组+50个保留组），训练自定义MobileNetV2分类器评估。
- **对抗攻击**：使用Ring-A-Bell-Nudity数据集（285个修改后的提示），测试MU-Attack（攻击步骤0、0-1-2）下的攻击成功率（ASR）。
- **复杂概念擦除**：颜色（红玫瑰）、数量（五支铅笔）等。
- **用户研究**：20名非艺术家参与者，每个方法约200个响应，评估5个维度（成像质量、提示遵循、输出多样性、擦除清洁度、无关概念保留）。

**对比方法**：CA（模型/噪声）、ESD、UCE、MACE、EAP、Meta-Unlearning。所有方法均适配到Flux架构。

**评估指标**：裸体检测数量、FID、CLIP分数、CLIP分类准确率、攻击成功率、用户评分。

## 4. 资源与算力

论文中**未明确说明**具体使用的GPU型号、数量或训练时长。仅提及：
- 使用Flux.1 [dev]模型（公开权重）。
- AdamW优化器，学习率`α_low=0.001`、`α_up=0.0005`，训练1000步。
- 流匹配Euler采样器，28步。
- LoRA秩未明确，仅提到微调文本相关参数（`add_q_proj`和`add_k_proj`）在双流块中。

缺乏详细的算力报告是本文的一个不足。

## 5. 实验数量与充分性

**实验数量**：全文包含约10组主要实验和若干辅助实验。
- **裸体擦除**（表2）：7个对比方法，3个检测类别。
- **实体/抽象/关系擦除**（表3、图5、图7）：3个粒度各10个概念。
- **消融研究**（表5）：5种损失配置。
- **对抗攻击**（表4）：3种方法，3种攻击设置。
- **用户研究**（图4）：5维度，20人×200响应。
- **多概念擦除**（图18）、**LoRA组合分析**（图16、17）等。

**充分性评估**：
- **正面**：覆盖了主流任务（NSFW、物体、风格、关系、名人）、多种评估指标（检测、图像质量、分类准确率、人类评估）、消融化完整、对比方法全面（包括经典和最新方法）、考虑了对抗攻击鲁棒性。
- **客观性**：使用标准数据集（I2P、COCO、CelebA）和公开检测器（NudeNet、CLIP），结果可复现。用户研究采用盲评。
- **公平性**：将传统方法适配到Flux架构（优化Q、K而非Q、V），但未明确说明适配过程中是否超参数调优一致，存在一定偏向风险。

总体实验设计较为充分，但缺少对计算开销和推理速度的对比。

## 6. 论文的主要结论与发现

1. EraseAnything成功实现了在流匹配Transformer架构（Flux）上的概念擦除，填补了该领域空白。
2. 在裸体擦除任务上，相比其他方法，EraseAnything在保持较低显式内容生成量的同时，取得了最佳的FID（21.75）和CLIP（30.24）分数，接近原始模型性能（21.32/30.87）。
3. 在实体、抽象、关系三类概念上，EraseAnything均实现了最低的擦除类准确率（Acc_e）和最高的无关类准确率（Acc_ir），并有效泛化到近义词（Acc_g较低）。
4. 对抗攻击测试中，EraseAnything相比ESD和CA具有最低的攻击成功率（原始2.46%，攻击后11.93%），表明更强的鲁棒性。
5. 消融实验证实了所有损失项（`L_esd`、`L_attn`、`L_lora`、`L_rsc`）各自的重要性，完整配置达到最佳性能。
6. 用户研究显示EraseAnything在擦除清洁度、无关概念保留、图像质量等5个维度均获得最高评分。
7. 多概念擦除（通过线性插值多个LoRA）可行，但大量概念组合（10个以上）时归一化会导致擦除效果减弱。

## 7. 优点

- **首次性**：第一个针对流匹配Transformer架构的概念擦除方法，填补了从SD到Flux的技术鸿沟。
- **方法论创新**：将概念擦除形式化为双层优化，下层专注擦除、上层专注保护，兼顾两者平衡；反向自对比损失是新颖设计，利用了LLM生成无关概念和近义词。
- **注意力定位**：证明了Flux中注意力图可定位特定token的激活，为后续工作提供借鉴。
- **鲁棒性**：基于学习的方法可应对拼写错误、同义词替换、词序打乱等黑盒攻击，优于简单的注意力图归零方法。
- **参数高效**：仅微调双流块中的Q/K投影的LoRA，训练高效（1000步）。
- **多概念扩展**：支持同时擦除多个概念，具有实用潜力。
- **实验全面**：覆盖多种概念类型、两大标准数据集、对抗攻击、消融研究和用户研究，论证充分。

## 8. 不足与局限

- **计算资源未公开**：未报告训练所需的GPU型号、数量和时间，不利于复现和成本评估。
- **大规模多概念擦除性能下降**：当同时擦除10个以上概念时，归一化叠加策略导致每个概念擦除效果减弱，缺乏高效组合方案（论文承认此为未来方向）。
- **擦除强度无法精细控制**：训练过程中无法按需调节擦除力度，缺乏类似滑块的交互式控制（论文提到此方向值得研究）。
- **对极简攻击仍有残留**：尽管鲁棒性优于其他方法，但在MU-Attack下攻击成功率仍达11.93%，并非完全免疫。
- **依赖LLM生成无关概念**：使用GPT-4o增加了额外成本，且生成质量可能影响性能；论文未充分讨论LLM引入的偏差风险。
- **实验局限性**：仅针对Flux.1 [dev]评估，未验证在其他流匹配模型（如SD v3）上的泛化能力；名人擦除仅用50个名人，规模较小。
- **对比方法适配公平性**：传统方法如ESD、UCE等被适配到Flux时，仅修改了微调参数，可能未充分优化，存在潜在的比较劣势。
- **伦理风险**：方法可被滥用擦除安全概念（如“safe”），需考虑双面性（论文仅讨论了正面影响）。

（完）
