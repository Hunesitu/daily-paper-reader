---
title: "FlowAR: Scale-wise Autoregressive Image Generation Meets Flow Matching"
title_zh: FlowAR：尺度级自回归图像生成与流匹配的结合
authors: "Sucheng Ren, Qihang Yu, Ju He, Xiaohui Shen, Alan Yuille, Liang-Chieh Chen"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=JfLgvNe1tj"
tags: ["query:ce"]
score: 7.0
evidence: 尺度级自回归图像生成
tldr: 现有尺度级自回归图像生成方法（如VAR）存在尺度设计僵化、生成器依赖离散分词器导致灵活性差的问题。本文提出FlowAR，将尺度级自回归与流匹配结合，实现更通用的下一尺度预测。该方法不仅提升了生成质量，还允许模块化更新分词器，为自回归图像生成提供了更灵活高效的框架。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 840, \"height\": 724, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1657, \"height\": 835, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1739, \"height\": 725, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1767, \"height\": 587, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 837, \"height\": 200, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 857, \"height\": 859, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 849, \"height\": 851, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 847, \"height\": 852, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 847, \"height\": 850, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 851, \"height\": 853, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-jflgvne1tj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 851, \"height\": 852, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-jflgvne1tj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1597, \"height\": 1111, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jflgvne1tj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 853, \"height\": 300, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jflgvne1tj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 856, \"height\": 193, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jflgvne1tj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 666, \"height\": 333, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jflgvne1tj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 540, \"height\": 448, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jflgvne1tj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 855, \"height\": 228, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jflgvne1tj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 579, \"height\": 159, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-jflgvne1tj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 878, \"height\": 292, \"label\": \"Table\"}]"
motivation: 克服VAR方法中尺度设计僵化和生成器对离散分词器的依赖问题。
method: 提出FlowAR，将尺度级自回归预测与流匹配损失相结合，实现灵活的下一个尺度预测。
result: FlowAR在图像生成任务上优于VAR，并支持分词器模块化更新。
conclusion: 尺度级自回归与流匹配的结合能提升图像生成的泛化性和灵活性。
---

## Abstract
Autoregressive (AR) modeling has achieved remarkable success in natural language processing by enabling models to generate text with coherence and contextual understanding through next token prediction. Recently, in image generation, VAR proposes scale-wise autoregressive modeling, which extends the next token prediction to the next scale prediction, preserving the 2D structure of images. However, VAR encounters two primary challenges: (1) its complex and rigid scale design limits generalization in next scale prediction, and (2) the generator’s dependence on a discrete tokenizer with the same complex scale structure restricts modularity and flexibility in updating the tokenizer. To address these limitations, we introduce FlowAR, a general next scale prediction method featuring a streamlined scale design, where each subsequent scale is simply double the previous one. This eliminates the need for VAR’s intricate multi-scale residual tokenizer and enables the use of any off-the-shelf Variational AutoEncoder (VAE). Our simplified design enhances generalization in next scale prediction and facilitates the integration of Flow Matching for high-quality image synthesis. We validate the effectiveness of FlowAR on the challenging ImageNet-256 benchmark, demonstrating superior generation performance compared to previous methods. Codes is available at \href{https://github.com/OliverRensu/FlowAR}{https://github.com/OliverRensu/FlowAR}.

---

## 论文详细总结（自动生成）

好的，作为一名资深学术论文分析助手，我将严格按照您的要求，对论文《FlowAR: Scale-wise Autoregressive Image Generation Meets Flow Matching》进行结构化、深入且客观的总结。

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：自回归模型在自然语言处理中取得了巨大成功，其核心是“下一个词预测”。将这一范式迁移到图像生成中，主流方法（如VQGAN、LlamaGen）是将图像离散化为1D的token序列，进行“下一个token预测”。然而，这会破坏图像固有的2D空间结构。
- **近期进展**：VAR方法提出了“尺度级”自回归建模（next scale prediction），通过从粗到细的多尺度token图生成图像，保留了2D结构，取得了显著成果。
- **核心问题**：尽管VAR有效，但其存在两个关键局限性：
    1.  **复杂且僵硬的尺度设计**：VAR使用了一个非均匀且复杂的尺度序列（如{1, 2, 3, 4, 5, 6, 8, 10, 13, 16}），限制了模型的泛化能力。
    2.  **生成器与分词器的紧耦合**：VAR需要一个与它共享相同复杂尺度结构的专用多尺度VQGAN离散分词器，这限制了模块化和灵活性，无法方便地更新或替换分词器。
- **整体含义**：本文旨在解决VAR的上述局限，提出一个更灵活、更一般的尺度级自回归图像生成框架，该框架能够兼容任何现代连续VAE分词器，并利用流匹配（Flow Matching）提升生成质量。

### 2. 论文提出的方法论：核心思想、关键技术细节

FlowAR的核心思想是**将简化的尺度级自回归预测与流匹配模型相结合**。

- **核心架构**：由三个主要组件构成：
    1.  **任意VAE分词器**：使用任何现成的**连续VAE**（如MAR-VAE、SD-VAE）将图像编码为连续潜在表示。
    2.  **尺度级自回归Transformer**：生成每个尺度的“语义”信息，用于条件化流匹配模型。
    3.  **尺度级流匹配模型**：根据语义信息，将噪声逐步转化为对应尺度的目标潜在表示。

- **关键技术细节与流程**：
    - **简化的尺度序列**：使用最简单的尺度序列 `S = {1, 2, 4, 8, 16}`，其中每个后续尺度的大小是前一个的两倍。粗尺度的token图是通过直接**下采样**最高分辨率（最细尺度）的潜在表示得到的，无需复杂的多尺度残差分词器。
    - **条件信息生成**：自回归Transformer以 `{[C], Up(s1, 2),..., Up(s_{i-1}, 2)}` 为输入，生成第 `i` 个尺度的语义信息 `ŝ_i`。其中 `[C]` 是类别条件，`Up(·,2)` 代表上采样2倍。
    - **尺度级流匹配**：对于每个尺度 `i`，模型学习一个从噪声 `F0` 到目标数据分布 `si` 的直线路径。训练时，通过公式 `Ft = t*si + (1-t)*F0` 构造插值样本，模型需要预测速度 `Vt = si - F0`。
    - **空间自适应层归一化（Spatial-adaLN）**：这是关键设计。不同于标准的adaLN使用全局平均语义，Spatial-adaLN将来自自回归Transformer的语义信息 `ŝ_i`，以**位置对位置**的方式注入到流匹配模型各层的缩放(`γ`)、平移(`β`)和门控(`α`)参数中，实现了细粒度的控制，从而显著提升图像质量。公式表示为：
        - `α₁, α₂, β₁, β₂, γ₁, γ₂ = MLP(ŝ_i + t)`
        - 其中，`γ` 和 `β` 用于调制层归一化（LN）后的特征，`α` 用于对特征进行门控。
    - **推理流程**：从类别条件 `C` 开始，循环执行：自回归Transformer输出 `ŝ_i` → 流匹配模型生成 `si` → 对 `si` 上采样后作为下一步输入。

### 3. 实验设计：数据集、Benchmark及对比方法

- **数据集**：使用**ImageNet-256**和**ImageNet-512**基准进行类条件图像生成。
- **Benchmark与评估指标**：使用**FID**（越低越好）和**Inception Score**（IS，越高越好）作为主要衡量指标，同时也报告Precision和Recall。
- **对比方法**：
    - **GANs**：BigGAN, StyleGAN, GigaGAN。
    - **Diffusion Models**：ADM, LDM, U-ViT, DiT。
    - **Flow Matching Models**：SiT。
    - **Token-wise Autoregressive Models**：VQVAE-2, VQGAN, RQTransformer, ViT-VQGAN, LlamaGen (不同配置)。
    - **Scale-wise Autoregressive Models**：**VAR**（本文的直接对标方法，包含d12, d16, d20, d30等多个配置）。
- **结果**：
    - 在**ImageNet-256**上，FlowAR-H（1.9B参数）取得了**1.65** FID，超越了所有对比方法，包括VAR-d30（2.0B参数，1.97 FID）和DiT-XL/2（2.27 FID）。
    - 在**ImageNet-512**上，FlowAR-L（590M参数）以**2.43** FID超越了VAR-d36（2.3B参数，2.63 FID）和DiT-XL/2（3.04 FID）。

### 4. 资源与算力

- **明确说明**：论文正文和附录中**没有明确提及**训练所使用的具体GPU型号、数量和训练时长。仅在超参数表（附录表6）中提到，训练epoch为400，batch size为1024，学习率为2e-4。

### 5. 实验数量与充分性

- **实验数量**：实验设计相当充分，主要包含：
    1.  **主实验结果**：在ImageNet-256和512上与大量SOTA方法对比。
    2.  **多项消融实验**：
        - **分词器兼容性**：测试了DC-AE, SD-VAE, MAR-VAE三种不同VAE，并与VAR的专用分词器对比。
        - **流匹配模型设计**：对比了“逐token”与“逐尺度”预测，以及“扩散”与“流匹配”框架。
        - **语义注入方法**：对比了addition, cross attention, sequence concatenation, channel concatenation, adaLN以及提出的Spatial-adaLN。
        - **尺度序列的构建方式**：对比了下采样图像后编码 vs. 下采样潜在表示。
        - **不同的尺度配置**：如{1,4,8,16}和{1,4,16}。
- **充分性与公平性**：
    - **充分**：消融实验覆盖了方法论的各个关键模块（分词器、流匹配、语义注入、尺度设计），数量充足。
    - **客观公平**：与VAR的直接对比是公平的，在相同参数量级下进行比较。论文也指出VAR的结果来自其官方代码和预训练权重。但需注意，部分对比方法（如BigGAN）的参数量级差异较大，但其作为经典baseline仍具有参考价值。

### 6. 论文的主要结论与发现

1.  **简化的尺度设计是有效的**：简单的`{1, 2, 4, 8, 16}`尺度序列，结合直接下采样潜在表示的方法，不仅消除了对复杂分词器的依赖，还提升了生成性能，证明了其泛化能力。
2.  **流匹配可以无缝集成到尺度级自回归模型**：用流匹配来建模每个尺度潜在空间的概率分布，比传统的分类分布建模或逐token预测效果更好，有助于生成更高质量的图像。
3.  **Spatial-adaLN是关键创新**：这种以位置为单位的语义注入方式，比全局性的adaLN或简单的特征拼接/叠加更有效，是实现高质量生成的关键。
4.  **模块化框架**：FlowAR解耦了生成器与分词器，允许用户灵活地使用任何先进的VAE（如MAR-VAE, SD-VAE）来提升性能，极大地增强了框架的灵活性和可扩展性。

### 7. 优点

- **创新性**：巧妙地结合了尺度级自回归和流匹配两种范式，提出了一种新颖且高效的生成框架。
- **实用性**：解耦生成器与分词器，支持即插即用任何现成的VAE，降低了使用门槛和后续升级成本。简化的尺度设计也降低了模型设计的复杂性。
- **性能卓越**：在ImageNet基准上，以较少的参数（如590M对比VAR的2.3B）取得了显著优于SOTA方法（包括VAR）的结果，证明了其高效性。
- **设计洞察力**：提出的Spatial-adaLN模块简单有效，直接解决了连续条件信息如何注入生成网络的核心问题，为未来相关研究提供了新思路。
- **充分的实验**：丰富的消融实验有力地支撑了每个设计选择的有效性。

### 8. 不足与局限

- **资源消耗不透明**：虽然模型参数被报告，但训练所需的实际计算资源（GPU时长、类型）未被披露，使得成本和复现难度的评估变得困难。
- **潜在的偏见风险**：论文本身在“Impact Statement”中提及，由于模型在ImageNet上训练，可能会继承该数据集固有的偏见（如对特定类别、背景的偏好）。
- **推理成本**：虽然使用了KV cache优化，但模型仍需要逐步进行多尺度生成，每个尺度都需要运行一次流匹配模型，这比单步生成模型（如GAN）的推理更复杂和耗时。论文未详细比较推理速度。
- **仅针对特定任务**：实验主要集中在ImageNet的类条件图像生成上，其方法论在更复杂的任务（如文本到图像生成）上的泛化能力和有效性有待进一步验证。
- **对比的局限性**：虽然与VAR对比充分，但与一些最新的、性能更强的掩码生成模型（如MaskGit的变体）或一些更简洁的扩散模型相比，讨论和实验可以更深入。

（完）
