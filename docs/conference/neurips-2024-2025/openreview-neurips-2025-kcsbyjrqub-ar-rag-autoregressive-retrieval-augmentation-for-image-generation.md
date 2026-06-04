---
title: "AR-RAG: Autoregressive Retrieval Augmentation for Image Generation"
title_zh: AR-RAG：面向图像生成的自回归检索增强
authors: "Jingyuan Qi, Zhiyang Xu, Qifan Wang, Lifu Huang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=kcSbYJRQub"
tags: ["query:ce"]
score: 7.0
evidence: 面向图像生成的自回归检索增强
tldr: 本文提出AR-RAG，一种自回归检索增强的图像生成范式。与传统单次检索不同，该方法在每一步生成时基于已生成块进行上下文感知的KNN检索，动态融入视觉参考。避免了过度复制和风格偏差等问题，在多个基准上提升了生成质量和多样性。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-kcsbyjrqub/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1256, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kcsbyjrqub/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1446, \"height\": 477, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kcsbyjrqub/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1434, \"height\": 786, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kcsbyjrqub/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1415, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kcsbyjrqub/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 931, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kcsbyjrqub/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1333, \"height\": 502, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-kcsbyjrqub/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 705, \"height\": 528, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-kcsbyjrqub/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1380, \"height\": 771, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kcsbyjrqub/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1163, \"height\": 525, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kcsbyjrqub/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 689, \"height\": 368, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kcsbyjrqub/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 877, \"height\": 253, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kcsbyjrqub/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1450, \"height\": 299, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-kcsbyjrqub/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 590, \"height\": 267, \"label\": \"Table\"}]"
motivation: 现有检索增强图像生成多采用静态单次检索，导致过度复制和风格偏差。
method: 在自回归生成的每一步进行补丁级KNN检索，动态融入相关视觉参考。
result: 有效避免过度复制，提升生成质量和多样性。
conclusion: 自回归检索增强为图像生成提供了更灵活的上下文利用方式。
---

## Abstract
We introduce  Autoregressive Retrieval Augmentation (AR-RAG), a novel paradigm that enhances image generation by autoregressively incorporating k-nearest neighbor retrievals at the patch level.
Unlike prior methods that perform a single, static retrieval before generation and condition the entire generation on fixed reference images,  AR-RAG performs context-aware retrievals at each generation step, using prior-generated patches as queries to retrieve and incorporate the most relevant patch-level visual references, 
enabling the model to respond to evolving generation needs while avoiding limitations (e.g., over-copying, stylistic bias, etc.) prevalent in existing methods. To realize AR-RAG, we propose two parallel frameworks: (1) Distribution-Augmentation in Decoding (DAiD), a training-free plug-and-use decoding strategy that directly merges the distribution of model-predicted patches with the distribution of retrieved patches, and (2) Feature-Augmentation in Decoding (FAiD), a parameter-efficient fine-tuning method that progressively smooths the features of retrieved patches via multi-scale convolution operations and leverages them to augment the image generation process. We validate the effectiveness of AR-RAG on widely adopted benchmarks, including Midjourney-30K, GenEval and DPG-Bench, demonstrating significant performance gains over state-of-the-art image generation models.

---

## 论文详细总结（自动生成）

# AR-RAG: Autoregressive Retrieval Augmentation for Image Generation 中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **问题**：现有图像生成模型虽然能生成逼真图像，但在复杂结构、多物体交互、稀有概念等场景下常出现局部扭曲、不一致性。检索增强生成（RAG）通过引入外部视觉参考可以缓解这些问题，但现有方法（如RDM、ImageRAG、RA-CM3）采用**静态单次检索**，即在生成前根据文本提示检索整张参考图像，并在整个生成过程中固定使用。这导致两个主要缺陷：1）**过度复制**：参考图像中与提示无关的视觉元素（如背景、物体）被错误地复制到生成图像中；2）**风格偏差和指令跟随退化**：固定参考图像会偏置生成过程，忽略文本提示中的物体关系和属性，例如多物体场景中遗漏部分对象。
- **整体含义**：本文提出一种全新的**自回归检索增强（AR-RAG）** 范式，在生成过程的每一步，基于已生成的视觉上下文（补丁级）动态检索最相关的局部视觉参考，从而避免静态检索的弊端，提升生成图像的局部一致性和语义保真度。

## 2. 论文提出的方法论

### 核心思想
- 在自回归图像生成的每一步，利用**已生成的周围补丁作为查询**，从一个预构建的**补丁级数据库**中检索最相似的**顶部K个补丁**，并将这些检索到的视觉信息融入当前补丁的预测中，实现动态、细粒度的上下文感知增强。

### 关键技术细节

#### 2.1 补丁级检索数据库构建
- 基于大型真实图像数据集（CC12M、JourneyDB、DataComp），使用Janus-Pro的量化自编码器将图像编码为**补丁特征**。
- 每个数据库条目包含：**值**（该补丁本身的特征向量）和**键**（该补丁的h-hop空间邻居特征向量的拼接）。缺失邻居用零向量填充。

#### 2.2 并行框架1：Distribution-Augmentation in Decoding (DAiD)
- **训练无关、即插即用**的解码策略。
- 在预测下一个图像token时，根据其h-hop邻居特征在数据库中检索top-K个最相似补丁，使用L2距离计算检索分布 `D_retrieval`（通过softmax，温度参数τ控制尖峰程度）。
- 将检索分布与模型原生分布 `D_model` 线性加权融合：`D_merge = (1-λ)·D_model + λ·D_retrieval`，然后从融合分布中采样下一个token。
- 关键超参数：λ（检索权重）、τ（检索温度）。

#### 2.3 并行框架2：Feature-Augmentation in Decoding (FAiD)
- **参数高效微调**方法，通过可学习的平滑和融合机制整合检索信息。
- **多尺度特征平滑**：对每个检索到的补丁特征，用不同尺寸（2×2到Q×Q）的卷积核在其周围上下文中进行平滑，得到多尺度表示并加权融合（可学习参数Ω）。
- **特征增强**：计算每个平滑后检索补丁的**兼容性分数**（通过线性投影），然后将这些检索补丁的加权和加到当前补丁的隐状态上：`h' = h_layer + Δh_layer + Σ s_k·h_k`。
- 在多个解码器层中插入FAiD模块，实现渐进式细化。

### 算法流程（文字说明）
- 以自回归方式生成图像序列。每一步，构造当前待预测补丁的h-hop邻居表示 → 在FAISS索引的数据库中检索top-K个最相似补丁 → 对于DAiD，直接计算检索分布并合并到模型分布；对于FAiD，先对检索补丁进行多尺度平滑，再计算兼容性分数并融合到隐状态中 → 预测下一个token。重复直到图像生成完成。

## 3. 实验设计

### 数据集与Benchmark
- **训练数据**：从CC12M和Midjourney-v6中采样共50,000对图文样本用于微调；检索数据库使用CC12M（570万）、JourneyDB（330万）、DataComp（460万）中随机采样图像构建，确保测试集无泄露。
- **测试Benchmark**：
  - **GenEval**：评估属性、关系、计数等细粒度指令跟随能力（6个子任务）。
  - **DPG-Bench**：评估复杂详细提示的生成能力（5个子类）。
  - **Midjourney-30K**：使用FID、CMMD、FWD三种指标评估图像质量与分布对齐。
  - **T2I-Bench**：评估颜色、形状、纹理、计数等组合推理。
  - **RareBench**：评估罕见概念组合生成能力。

### 对比方法
- **非检索方法**：LlamaGen、LDM、SDv1.5/v3、PixArt-α、DALL-E 2/3、Show-o、Janus-Pro、FLUX.1-dev等。
- **图像级检索增强方法**：RDM、ImageRAG、RA-CM3（基于Janus-Pro复现）。
- **基线设置**：以Janus-Pro-1B和Show-o为骨干，确保公平比较。

## 4. 资源与算力
- **训练**：使用4张NVIDIA A100 (80GB) GPU，全局batch size 256，AdamW优化器，学习率2e-4，线性warm-up 10%，训练1个epoch。
- **推理**：单张L40 GPU上统计时间。DAiD几乎无额外开销（仅+0.22%）；FAiD因逐补丁检索和特征融合增加约36%推理时间。
- 论文未提供总训练时长具体数值。

## 5. 实验数量与充分性

### 实验数量
- 在**5个Benchmark**上进行了主实验，每个包含多个子指标。
- 进行了**消融实验**：超参数λ、τ、h-hop、b（FAiD模块数量）的系统调优（见附录C.2）。
- 进行了**定性对比**（图4、图5）和**检索有效性分析**（图6）。
- 展示了**推理时间对比**（表6）。
- 适配了另一种骨干模型Show-o，验证泛化性。

### 充分性与公平性
- **充分**：覆盖了多种评价维度（指令跟随、图像质量、罕见组合、属性绑定），包含训练无关和微调两种方法；对比了SOTA模型和现有RAG基线。
- **公平**：大部分基线采用官方结果或复现，RA-CM3基于相同骨干（Janus-Pro）复现；所有方法在同一硬件上推理对比。
- 不足之处：未提供多次运行的统计显著性和误差条；部分对比方法参数规模不一致，但作者已尽量选取相近规模。

## 6. 论文的主要结论与发现

1. **AR-RAG显著优于静态检索增强方法**：在GenEval上，FAiD达到0.78总分（+0.07 vs Janus-Pro）；DPG-Bench上达到79.36（+2.10）；Midjourney-30K上FID降至6.67（Janus-Pro为14.33）。
2. **DAiD与FAiD均有效**：DAiD训练无关、几乎零开销即可带来提升；FAiD通过微调获得更大增益。
3. **动态补丁级检索避免了过度复制和指令跟随失败**：定性示例显示，ImageRAG会错误复制参考图中的背景或多余物体，而AR-RAG正确聚焦于提示内容。
4. **泛化性良好**：在Show-o骨干上也取得一致改进，证明了方法的架构无关性。
5. **检索到的补丁与目标补丁高度相关**：L2距离分析显示检索补丁与ground truth的距离远小于随机采样补丁，验证了检索有效性。

## 7. 优点

1. **创新性**：首次提出自回归补丁级检索增强范式，打破了静态图像级检索的局限，实现动态、上下文感知的视觉参考融合。
2. **两种实现策略互补**：DAiD无需训练、即插即用；FAiD通过参数高效微调进一步优化性能，适应不同计算资源场景。
3. **细致的模块设计**：多尺度平滑、兼容性分数等机制确保检索信息与局部上下文自然融合，避免生硬插入。
4. **全面的实验验证**：在5个高质量benchmark上主实验+消融+定性分析+推理效率对比，证据充分。
5. **代码开源**：承诺发布代码和模型，促进复现和应用。

## 8. 不足与局限

1. **依赖离散token化**：方法针对基于离散token的自回归模型（如Janus-Pro、Show-o），不能直接应用于连续潜空间的扩散模型。
2. **检索数据库规模受限**：受算力限制，数据库小于十亿级，可能无法完全覆盖真实世界的长尾视觉模式，引入偏差。
3. **仅限2D图像生成**：未探索到3D点云等结构化生成任务，理论可迁移但未验证。
4. **推理速度**：FAiD在单GPU上增加约36%推理时间，多卡并行可缓解但仍有开销。
5. **超参数敏感**：DAiD的λ和τ、FAiD的h和b需要根据任务调整；论文在Midjourney-10K上调优，可能在其他数据集上不是最优。
6. **无误差棒**：未报告多次独立运行的标准差，无法评估结果稳定性。
7. **潜在安全风险**：检索数据库可能包含不当内容，检索结果可能引入有害视觉元素，需要额外过滤机制。

（完）
