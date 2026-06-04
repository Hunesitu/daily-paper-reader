---
title: "Orthus: Autoregressive Interleaved Image-Text Generation with Modality-Specific Heads"
title_zh: "Orthus: 基于模态特定头的自回归交错图文生成"
authors: "Siqi Kou, Jiachun Jin, Zhihong Liu, Chang Liu, Ye Ma, Jian Jia, Quan Chen, Peng Jiang, Zhijie Deng"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=dPyA4ZYs7n"
tags: ["query:ce"]
score: 8.0
evidence: 基于模态特定头的自回归交错图文生成
tldr: 针对现有模型难以在自回归框架下同时处理离散文本和连续图像特征的问题，提出Orthus，采用模态特定头：语言模型头预测文本，扩散头生成连续图像特征，替代向量量化，在高分辨率条件生成上展示了高效且高质量的结果，为统一自回归图文生成提供了新范式。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1779, \"height\": 300, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1561, \"height\": 581, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1648, \"height\": 1059, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1638, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 821, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 364, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 364, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 352, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 363, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 363, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 365, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 364, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 363, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 364, \"height\": 364, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 366, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 365, \"height\": 367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 363, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 366, \"height\": 366, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 365, \"height\": 363, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 369, \"height\": 370, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 365, \"height\": 365, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1594, \"height\": 519, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-dpya4zys7n/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1679, \"height\": 1444, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 866, \"height\": 280, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1743, \"height\": 687, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 883, \"height\": 643, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 905, \"height\": 236, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 850, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1079, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-dpya4zys7n/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1051, \"height\": 280, \"label\": \"Table\"}]"
motivation: 现有生成模型难以在自回归框架下同时处理离散文本和连续图像特征。
method: 采用模态特定头：语言模型头预测文本，扩散头生成连续图像特征，替代向量量化。
result: 在高分辨率条件生成上展示了高效且高质量的结果。
conclusion: 为统一自回归图文生成提供了新范式。
---

## Abstract
We introduce Orthus, a unified multimodal model that excels in generating interleaved images and text from mixed-modality inputs by simultaneously handling discrete text tokens and continuous image features under the \textbf{AR} modeling principle. The continuous treatment of visual signals minimizes the information loss while the fully AR formulation renders the characterization of the correlation between modalities straightforward. Orthus leverages these advantages through its modality-specific heads---one regular language modeling (LM) head predicts discrete text tokens and one diffusion head generates continuous image features. We devise an efficient strategy for building Orthus---by substituting the Vector Quantization (VQ) operation in the existing unified AR model with a soft alternative, introducing a diffusion head, and tuning the added modules to reconstruct images, we can create an Orthus-base model effortlessly (e.g., within 72 A100 GPU hours). Orthus-base can further embrace post-training to craft lengthy interleaved image-text, reflecting the potential for handling intricate real-world tasks. For visual understanding and generation, Orthus achieves a GenEval score of 0.58 and an MME-P score of 1265.8 using 7B parameters, outperforming competing baselines including Show-o and Chameleon.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有统一多模态模型在同时处理离散文本和连续图像特征时存在固有缺陷。一类方法（如Chameleon）使用向量量化（VQ）将图像转为离散token，导致信息损失，尤其影响高频细节（如OCR、人脸生成）；另一类方法（如Transfusion、Show-o）结合自回归（AR）文本与扩散图像，但扩散建模需要向模型输入噪声图像，干扰了视觉理解（如干净图像输入）与生成（噪声输入）的联合建模，造成性能下降。
- **整体含义**：Orthus旨在在纯自回归框架下，通过连续图像特征和模态特定头，同时实现高质量视觉理解与生成，并支持复杂交错图文生成，避免上述两类方法的缺陷。

## 2. 方法论
- **核心思想**：使用共享Transformer骨干（因果注意力）处理连续图像特征（来自预训练VAE）和离散文本token，然后通过两个模态特定头分别预测：LM头预测下一个文本token（分类）、扩散头预测下一个图像patch特征（条件扩散）。这样既保留连续图像信息的无损性，又保持自回归建模的简洁性。
- **关键技术细节**：
  - **可微软替代VQ**：将原始AR模型（如Chameleon）中VQ的argmin硬量化替换为带温度τ的softmax加权和（公式4），使视觉嵌入可微分，可重用预训练权重。
  - **高效构建Orthus-base**：基于预训练Chameleon-7B，仅替换视觉嵌入模块为可微版本，并添加扩散头（3层MLP，含AdaLN），在10k高质量图像上微调视觉嵌入和扩散头（共0.3B参数），使用扩散损失（公式3）训练，仅需9小时（8×A100）。
  - **后训练**：使用Lar（文本AR损失）+ λLdiff（扩散损失，λ=100）联合训练，更新所有参数（除视觉自编码器）。推理时通过特殊token [BOI]/[EOI] 切换文本生成与图像patch生成。
- **公式与流程**：扩散损失采用标准DDPM噪声预测，噪声调度为线性1000步。图像生成使用DDIM采样100步，CFG尺度5，分辨率512×512。

## 3. 实验设计
- **数据集与场景**：
  - **图像编辑**：Instruct-Pix2Pix训练集（400k）和测试集，评估CLIP相似度（指令一致性、图像相似度、方向得分）。
  - **故事书生成**：StoryStream数据集（卡通系列图像+叙事文本）。
  - **视觉理解**：POPE、MME-P、VQAv2、GQA、MMMU基准（零样本或微调后）。
  - **视觉生成**：GenEval、HPSv2基准。
  - **消融实验**：分离训练 vs 统一训练、不同视觉嵌入模块（argmin、softmax、线性）、损失函数（MSE vs 扩散）。
- **对比方法**：
  - 理解：LLaVA-v1.5、InstructBLIP、Qwen-VL-Chat、Emu3-Chat、Show-o、LWM、Chameleon（后训练版）等。
  - 生成：SD v1.5/v2.1、DALL-E、Emu3-Gen、SDXL、SEED-X、LWM、Show-o、Transfusion、Chameleon等。
- **公平性**：
  - Chameleon后训练使用与Orthus相同的数据集（LlaVA-v1.5-665K + JourneyDB + LAION-COCO-aesthetic recaptioned），确保苹果对苹果比较。

## 4. 资源与算力
- **Orthus-base构建**：8×NVIDIA A100 80GB GPU，训练15,000步，约9小时（总72 GPU hours）。
- **后训练**（instruct-tuning）：35,000步，16 batch size，学习率1e-5，使用AdamW。隐含所需GPU数量未明确，但推测同样使用8×A100。
- **未明确**：后训练具体耗时、总训练步数对应的时长未给出。

## 5. 实验数量与充分性
- **实验组数**：
  - 混合模态生成：2个任务（图像编辑、故事生成），各有定性+定量（编辑任务有3个指标对比）。
  - 视觉理解：5个基准（POPE, MME-P, VQAv2, GQA, MMMU），对比了8个以上方法。
  - 视觉生成：2个基准（GenEval, HPS），对比了8个以上方法（包括专用和统一模型）。
  - 消融实验：3组（分离训练 vs 统一训练；3种嵌入模块；MSE vs 扩散损失）。
- **充分性评估**：实验覆盖了主要任务类型，对比了多种方法，消融验证了设计选择。但仅7B参数规模，未在更大模型上验证；训练数据量相对较小（10k用于基础构建，35k步后训练），可能限制泛化能力。整体较充分，但可更广泛（如更多数据集、更多尺寸）。

## 6. 主要结论与发现
- Orthus在视觉理解上显著优于Chameleon（+ 约200 MME-P）、LWM、Show-o；在视觉生成上GenEval 0.58超越SDXL（0.55）和DALL-E（0.52），接近SD3（0.64）。
- 统一训练（理解和生成联合）优于单独训练，证明跨模态学习增益。
- 连续图像表示+扩散头优于离散VQ或MSE损失。
- 图像编辑任务中，Orthus性能匹敌专用模型Instruct-Pix2Pix，并展现上下文学习能力（通过示例而非指令完成编辑）。
- 故事生成中能产生逻辑连贯、细节一致的交错图文。

## 7. 优点
- **方法创新**：去除了VQ的不可微硬量化，提出可微软替代，实现从预训练AR模型的高效迁移；将扩散头与骨干解耦，避免噪声干扰，同时保持自回归统一建模。
- **高效构建**：仅需72 GPU小时即可从Chameleon构建基座模型，资源友好。
- **性能优势**：在多个基准上超越同类统一模型，甚至超过一些专用模型（如SDXL）。
- **能力广泛**：支持复杂交错图文生成（编辑、故事），且具备上下文学习能力。

## 8. 不足与局限
- **推理延迟高**：需要多次通过扩散头（DDIM 100步）生成图像，增加了推理时间。
- **模型规模受限**：仅7B参数，受限于计算资源；未探索更大规模下的潜力。
- **数据规模**：基础构建仅用10k图像，后训练数据量也有限，可能限制泛化与细节质量。
- **解码器依赖**：需要额外微调VAE解码器以获得高质量重建，增加复杂度。
- **实验覆盖**：未在更广泛的多模态任务（如视频、音频）上验证，也未与最新更大模型（如Llama-3多模态）对比。

（完）
