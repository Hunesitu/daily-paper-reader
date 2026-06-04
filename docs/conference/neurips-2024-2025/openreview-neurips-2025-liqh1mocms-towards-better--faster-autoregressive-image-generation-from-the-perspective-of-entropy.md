---
title: "Towards Better & Faster Autoregressive Image Generation: From the Perspective of Entropy"
title_zh: 从熵视角实现更好更快的自回归图像生成
authors: "Xiaoxiao Ma, Feng Zhao, Pengyang Ling, Haibo Qiu, Zhixiang Wei, Hu Yu, Jie Huang, Zhixiong Zeng, Lin Ma"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=LiQH1MOCMs"
tags: ["query:ce"]
score: 7.0
evidence: 基于熵的加速自回归图像生成解码策略
tldr: 本文从熵角度重新审视自回归图像生成的采样问题。提出基于空间熵的动态温度控制和熵感知接受规则，在不增加计算开销的情况下平衡多样性、对齐度和结构连贯性，实现更高质量和更快生成速度。适用于掩码和尺度模型。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1437, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1453, \"height\": 504, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1444, \"height\": 360, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1439, \"height\": 336, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1306, \"height\": 544, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1303, \"height\": 1113, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1383, \"height\": 578, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 638, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 688, \"height\": 278, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 813, \"height\": 240, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 896, \"height\": 236, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 881, \"height\": 248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 880, \"height\": 248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 876, \"height\": 248, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1172, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1155, \"height\": 593, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1158, \"height\": 888, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1162, \"height\": 1183, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 878, \"height\": 355, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1449, \"height\": 688, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 879, \"height\": 368, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1295, \"height\": 1037, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1442, \"height\": 1342, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1442, \"height\": 1348, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1441, \"height\": 1346, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-liqh1mocms/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1449, \"height\": 1161, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-liqh1mocms/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1313, \"height\": 656, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-liqh1mocms/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1308, \"height\": 331, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-liqh1mocms/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 733, \"height\": 252, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-liqh1mocms/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 522, \"height\": 248, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-liqh1mocms/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 594, \"height\": 245, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-liqh1mocms/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1022, \"height\": 405, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-liqh1mocms/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1447, \"height\": 262, \"label\": \"Table\"}]"
motivation: 自回归图像生成中图像令牌信息密度低且分布不均匀，现有解码策略效率低下。
method: 利用令牌分布的空间熵动态调节温度，并设计熵感知的接受规则。
result: 在多种自回归模型上提升了生成质量和速度，无额外计算开销。
conclusion: 熵信息可有效指导自回归图像生成解码过程。
---

## Abstract
In this work, we first revisit the sampling issues in current autoregressive (AR) image generation models and identify that image tokens, unlike text tokens, exhibit lower information density and non-uniform spatial distribution. Accordingly, we present an entropy-informed decoding strategy that facilitates higher autoregressive generation quality with faster synthesis speed. Specifically, the proposed method introduces two main innovations: 1) dynamic temperature control guided by spatial entropy of token distributions, enhancing the balance between content diversity, alignment accuracy, and structural coherence in both mask-based and scale-wise models, without extra computational overhead, and 2) entropy-aware acceptance rules in speculative decoding, achieving near-lossless generation at about 85% of the inference cost of conventional acceleration methods. Extensive experiments across multiple benchmarks using diverse AR image generation models demonstrate the effectiveness and generalizability of our approach in enhancing both generation quality and sampling speed.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：自回归（AR）图像生成模型中，图像 token 的信息密度远低于文本 token，且空间分布高度非均匀（例如大面积纯色区域与复杂前景共存）。现有采样策略（如固定 top-K、top-p）对所有 token 采用统一参数，忽略了这种空间差异，导致生成质量出现两难：高随机性丰富细节但破坏结构，低随机性稳定结构却造成平滑、细节缺失。
- **研究动机**：借鉴语言模型中的采样策略（如动态温度、对比解码）并不直接适用于图像，因为图像的低信息密度和非均匀性需要更细粒度的 token 级控制。论文提出利用预测 logits 的熵作为信息密度的代理指标，并据此设计自适应解码策略，以同时提升生成质量和速度。
- **整体含义**：本文首次系统地将熵引入 AR 图像生成采样过程，不仅实现质量提升，还拓展到推测解码加速，展示了熵作为统一指导信号的潜力。

## 2. 论文提出的方法论

- **核心思想**：通过计算每个预测 token 分布的熵 ϵ，动态调整采样温度和接受规则，低熵区域（简单/均匀区域）增加随机性以丰富细节，高熵区域（复杂/结构区域）降低随机性以保持结构稳定性。
- **关键技术细节**：
  - **动态温度控制**：温度计算公式为 \( T = T_0 e^{-\epsilon \alpha} + \theta \)，其中 \( T_0 \) 最大温度，θ 下限，α 衰减率。温度调整后的概率分布通过对 logits 除以 T 后 softmax 得到。
  - **适应两种主流 AR 范式**：
    - *掩码模型*：在每步通过置信度加温度修正的 Gumbel 采样确定接受令牌，利用熵感知温度提升低熵区随机性、高熵区准确性。
    - *尺度模型*：为不同尺度设置递减温度 \( T_s = T \cdot [1 - \beta (s - \lfloor S/2 \rfloor)] \)，早期尺度高随机性生成主体，后期低随机性细化纹理。
  - **熵感知推测解码**：修改标准推测解码的接受条件，将随机阈值 r 缩放为 \( 0.5 + (r - 0.5)(1 - \lambda \epsilon) \)，再结合偏移因子 \( \epsilon/e \)，使高熵区更严格验证，低熵区更宽松接受，从而节省约 15% 推理成本。
- **算法流程（文字说明）**：对于每个生成位置，先计算 logits 的熵 ϵ → 根据熵代入温度公式得到 T → 对 logits 进行温度缩放 → softmax 得到新概率分布 → 采用 top-K 等截断后采样。加速时，在推测解码的每步对比前后两次分布，用熵修改后的条件判断是否接受草案 token。

## 3. 实验设计

- **数据集**：主要使用 **MS-COCO 2017 验证集**（5,000 张）评估 FID、CLIP-Score。附录中补充使用 **COCO 2014**（更大规模）验证结果一致性。
- **Benchmark**：四种代表性 AR 模型：LlamaGen（next-token）、Lumina-mGPT（next-token）、Meissonic（mask-based）、STAR（scale-wise）。对比方法：各模型的**原始默认采样**（基线），以及加速场景下的 **SJD 推测解码**。消融实验中还比较了不同 top-K、CFG、温度等组合。
- **评价指标**：FID (↓)、CLIP-Score (↑)、DPG-bench (↑)、HPSv2.1 (↑)，覆盖图像质量、文本对齐、语义保真度和人类偏好。

## 4. 资源与算力

- 文中明确说明：**所有实验在 A100 GPU 上运行**。未报告具体 GPU 数量、并行方式或训练时长（因方法为推理期采样策略，无需训练）。加速实验可降低约 15% 推理成本，但未给出总 GPU·小时数。

## 5. 实验数量与充分性

- **主要实验数量**：
  - 采样质量：表 1 对 4 种模型分别报告基线 vs 提出方法（及掩码/尺度专用变体）的 4 个指标。
  - 加速性能：表 2 对 LlamaGen 和 Lumina-mGPT 对比 Vanilla、SJD、Ours 的延迟、步数、FID、CLIP。
  - 消融实验：图 8(a) 分析温度公式参数；图 8(b) 结合 top-K、CFG；图 3(c) 按熵区间调节温度；附录中随机种子稳定性（10 种子均值±std）、top-p 和温度组合、更多数据集（COCO2014）等。
- **充分性与公平性**：实验覆盖主流 AR 三种范式（next-token、mask、scale），消融较系统，但缺失与同类动态采样方法（如 EDT、PURE）的直接定量对比（作者解释语言模型方法不适用于图像，视觉方法 PURE 仅针对超分）。基线采用官方默认设置，随机种子实验验证了稳定性，因此实验设计整体充分且公平。

## 6. 论文的主要结论与发现

1. 图像生成中熵可以可靠地表示 token 的信息密度：低熵对应简单区域，高熵对应复杂前景。
2. 动态温度通过熵自适应调整能在不增加额外计算的情况下提升图像质量（FID 降低 1~4 点，DPG 提升 3~5 点），并保持或提升 CLIP-Score。
3. 该策略对掩码模型和尺度模型同样有效，通过专用扩展（掩码接受/Gumbel、尺度递减温度）进一步获益。
4. 将熵用于推测解码的接受规则后，可实现**约 85% 的基线推理成本**，而质量几乎无损（FID 和 CLIP 接近或略优）。
5. 方法对超参数（top-K、CFG）不敏感，能降低模型对采样参数的依赖性。

## 7. 优点

- **训练无关**：所有修改仅在推理时进行，无需重新训练或微调模型，易于部署。
- **理论创新**：首次系统剖析图像与文本在信息密度上的差异，并利用熵设计专门的解码策略，具有新颖性和通用性。
- **效果显著**：在多种 AR 框架上均取得质量和速度的双重提升，且加速部分与现有推测解码正交，可叠加其他加速技巧。
- **鲁棒性增强**：结合传统采样参数（top-K、CFG）后，模型对这些参数的敏感性降低，更易获得稳定高性能。

## 8. 不足与局限

- **超参数敏感**：动态温度公式中的 \( T_0, α, θ \) 需针对不同模型手动调整，且最优值差异较大（见表 5），缺乏自适应确定机制。
- **性能增益模型依赖**：对已充分训练的大规模模型（如 Lumina-mGPT）提升幅度较小；对弱模型（如 LlamaGen Stage-2）增益有限或无明显改善（文中提及）。
- **熵映射不一致**：部分情况下高语义区域（如人脸）熵反而较低，可能导致错误调节，造成结构扭曲或细节过度平滑（failure cases）。
- **实验覆盖不够广**：仅使用 COCO 数据集评估，缺少其他常见图像生成基准（如 ImageNet、PartiPrompts）或类条件生成任务；未与扩散模型对比采样速度或质量。
- **一次性结果**：未报告多次运行的置信区间（除随机种子实验外），主要实验只做单次生成，可能引入偏差。

（完）
