---
title: Autoregressive Image Generation without Vector Quantization
title_zh: 无需向量量化的自回归图像生成
authors: "Tianhong Li, Yonglong Tian, He Li, Mingyang Deng, Kaiming He"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=VNBIF0gmkb"
tags: ["query:ce"]
score: 9.0
evidence: 无需向量量化的自回归图像生成
tldr: 传统自回归图像生成依赖向量量化将像素映射到离散空间，限制了模型能力。本文提出扩散损失函数，直接在连续值空间中建模每个令牌的概率分布，从而无需离散标记器。该方法应用于标准自回归和掩码自回归模型，在图像生成任务上取得与离散方法相当或更优的性能，开辟了连续空间自回归图像生成的新方向。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-vnbif0gmkb/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 569, \"height\": 361, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-vnbif0gmkb/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 638, \"height\": 1153, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-vnbif0gmkb/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 818, \"height\": 925, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-vnbif0gmkb/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 709, \"height\": 515, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-vnbif0gmkb/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1386, \"height\": 2317, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-vnbif0gmkb/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1441, \"height\": 289, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-vnbif0gmkb/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1342, \"height\": 412, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-vnbif0gmkb/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1288, \"height\": 305, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-vnbif0gmkb/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1400, \"height\": 787, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-vnbif0gmkb/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 920, \"height\": 181, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-vnbif0gmkb/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 934, \"height\": 591, \"label\": \"Table\"}]"
motivation: 自回归图像生成通常需要离散标记空间，但离散化会丢失信息。
method: 提出扩散损失函数，通过扩散过程建模连续令牌的概率分布，避免向量量化。
result: 在图像生成任务中，该方法与基于离散令牌的方法性能相当甚至更优。
conclusion: 连续空间自回归生成是可行的，且避免了离散化的信息损失。
---

## Abstract
Conventional wisdom holds that autoregressive models for image generation are typically accompanied by vector-quantized tokens. We observe that while a discrete-valued space can facilitate representing a categorical distribution, it is not a necessity for autoregressive modeling. In this work, we propose to model the per-token probability distribution using a diffusion procedure, which allows us to apply autoregressive models in a continuous-valued space. Rather than using categorical cross-entropy loss, we define a Diffusion Loss function to model the per-token probability. This approach eliminates the need for discrete-valued tokenizers. We evaluate its effectiveness across a wide range of cases, including standard autoregressive models and generalized masked autoregressive (MAR) variants. By removing vector quantization, our image generator achieves strong results while enjoying the speed advantage of sequence modeling. We hope this work will motivate the use of autoregressive generation in other continuous-valued domains and applications. Code is available at [https://github.com/LTH14/mar](https://github.com/LTH14/mar).

---

## 论文详细总结（自动生成）

### 论文详细中文总结

#### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**: 自回归图像生成模型通常需要依赖向量量化（VQ）将连续像素/特征映射到离散令牌空间，这限制了生成质量并增加了训练复杂度。本文质疑这种耦合是否必要。
- **研究动机**: 自回归建模的本质是“基于已知令牌预测下一个令牌”，并不要求输入/输出必须是离散的。离散空间只是便于定义分类分布和交叉熵损失。如果能找到替代的连续概率分布建模方法，就可以摆脱向量量化。
- **整体含义**: 提出一种新的**Diffusion Loss**，在连续值空间中用扩散过程来建模每个令牌的条件概率分布，从而允许自回归模型直接使用连续值令牌（如KL-16 tokenizer），避免了离散化带来的信息损失和训练困难。该方法统一了标准自回归（AR）和掩码自回归（MAR）框架，在ImageNet图像生成任务上取得了与最先进方法相当或更优的性能，且推理速度更快。

#### 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程（用文字说明即可）
- **核心思想**:
  - 将每个令牌的概率分布建模为条件扩散过程：自回归网络输出一个条件向量z，然后一个小的去噪MLP以z为条件，预测加入噪声的令牌xt中的噪声ε，从而隐式定义概率分布p(x|z)。
  - 用扩散损失替代交叉熵损失：损失函数为L(z,x)=E_{ε,t}[||ε - εθ(xt|t,z)||²]。该损失可微分，梯度可反向传播至自回归网络。
  - 推理时通过反向扩散过程采样令牌：从高斯噪声开始，迭代去噪得到x0 ~ p(x|z)，并支持温度τ缩放噪声以控制多样性。
- **关键技术细节**:
  - **扩散过程**: 采用DDPM框架，余弦噪声调度，训练时1000步，推理时100步。去噪网络为小型MLP（默认3个残差块、宽度1024），参数仅约21M（占总模型5%）。
  - **自回归模型**: 提出两种实现：
    - **标准AR**: 因果注意力，光栅顺序，每次预测一个令牌。
    - **掩码自回归（MAR）**: 双向注意力（类似MAE），随机顺序，每次可预测多个令牌（“下一组令牌预测”），训练时随机掩码率在[0.7,1.0]之间，推理时使用余弦调度逐步减少掩码。
  - **去噪MLP**: 使用AdaLN将条件向量z和时间嵌入融合到LayerNorm中。
  - **分类器无关引导（CFG）**: 训练时10%样本丢弃类别条件，推理时用引导尺度ω调整。
  - **温度采样**: 通过缩放逆扩散步骤中的噪声方差σ_t实现。
- **算法流程（伪代码见附录）**:
  - 训练：输入序列→自回归Transformer（输出每个位置的条件向量z）→对每个令牌采样噪声ε和时间t→加噪得到xt→MLP预测噪声εθ→计算L2损失→反向传播更新所有参数（包括MLP和Transformer）。
  - 推理：给定类别，自回归逐步预测：对每个步骤，使用已预测的令牌作为输入，Transformer输出各个未知位置的条件向量z，然后通过反向扩散采样令牌值。

#### 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法
- **数据集**: ImageNet，主要分辨率256×256，也报告了512×512的结果。
- **基准与评价指标**: FID（越低越好）、IS（越高越好），并报告Precision/Recall。使用官方评估套件。
- **对比方法**:
  - 像素级方法：ADM、VDM++
  - 离散令牌方法：VQGAN + 自回归、MaskGIT、MAGE、MAGVIT-v2
  - 连续令牌方法：LDM-4、U-ViT、DiT、DiffiT、MDTv2、GIVT
  - 本文自身消融：对比交叉熵损失 vs. 扩散损失、不同tokenizer（VQ-16, KL-16, Consistency Decoder）、AR vs. MAR变体、不同MLP规模、不同采样步数、不同温度等。
- **核心实验组**:
  - Table 1: 在AR/MAR四种变体下对比CrossEntropy和DiffLoss，使用VQ-16和KL-16 tokenizer。
  - Table 2: Diffusion Loss在不同tokenizer（VQ-16, KL-16, KL-8, Consistency Decoder）上的灵活性。
  - Table 3: 去噪MLP宽度的影响。
  - Figure 4/5: 采样步数和温度的影响。
  - Figure 6: 速度/精度权衡（与DiT对比）。
  - Table 4: 系统级对比（MAR-B/L/H，800 epochs）与其他最先进方法。
  - Table 6: ImageNet 512×512结果。

#### 4. 资源与算力：如果文中有提到，请总结使用了多少算力（GPU 型号、数量、训练时长等）。若未明确说明，也请指出这一点。
- **明确给出**（附录B）：
  - 训练平台：16台服务器，每台8块V100 GPU（共128块V100）。
  - 训练时间：MAR-L模型（约400M参数）训练400 epochs约需2.6天。
  - 对比：同等条件下，DiT-XL/2需4.6天，LDM-4需9.5天。
  - 推理速度：MAR-L+DiffLoss，256×256图像，<0.3秒/张（FID<2.0）。

#### 5. 实验数量与充分性：大概做了多少组实验（如不同数据集、消融实验等），这些实验是否充分、是否客观、公平。
- **实验数量**: 论文包含大量消融和比较：
  - 主要实验表：Table 1~4, Table 6，以及多个消融图（Figure 4~6）。
  - 消融维度包括：损失函数类型、tokenizer类型、MLP规模、采样步数、温度、AR vs. MAR变体、因果vs.双向注意力、顺序（光栅vs.随机）、多步预测数量、模型大小（B/L/H）、训练epochs（400 vs. 800）等。
  - 附录中还对比了MAGE的“on-the-fly顺序”策略（Table 5），以及像素空间建模（FID 2.93 on 64×64）。
- **充分性与公平性**: 实验设计较为充分：
  - 所有对比均在相同训练设置下进行（如Table 1中AR/MAR变体均用同一tokenizer和400 epochs）。
  - 与外部方法对比时，使用了公开代码和固定tokenizer（LDM的VQ-16/KL-16），并报告了多个指标（FID, IS, Precision, Recall）。
  - 速度对比（Figure 6）基于相同硬件（A100，batch size 256）。
  - 不足之处：主要仅在ImageNet上进行，未验证其他数据集（如CIFAR、LSUN）；未进行超参数大规模网格搜索（但已有足够消融）。

#### 6. 论文的主要结论与发现
- **主要结论**:
  - 自回归图像生成不必须依赖向量量化；使用**Diffusion Loss**可以在连续值令牌空间上实现有效建模，且性能优于离散交叉熵损失。
  - **MAR模型**（随机顺序+双向注意力+多令牌预测）结合Diffusion Loss，在速度和质量上都优于标准AR和DiT等扩散模型。
  - 通过调整温度和CFG，可以灵活控制生成质量与多样性。
- **关键量化结果**:
  - ImageNet 256×256: MAR-H (943M参数, 800 epochs) 达到FID 1.55 (CFG) 和 FID 2.35 (无CFG)，超越多数先前方法。
  - 推理速度：<0.3秒/图像即可实现FID<2.0。
  - Diffusion Loss也可直接用于VQ tokenizer（取VQ前的连续特征），并改善重建质量。
- **可扩展性**: 模型规模增大时性能持续提升（从MAR-B到MAR-H），暗示进一步扩大的潜力。

#### 7. 优点：方法或实验设计上有哪些亮点
- **方法创新**:
  - 首次将扩散模型作为“逐令牌损失函数”用于自回归生成，解耦自回归与离散化。
  - 统一AR与掩码生成模型至广义自回归框架（MAR），且随机顺序使训练与推理一致。
  - Diffusion Loss支持多种tokenizer（VQ、KL、Consistency Decoder），具有高度灵活性。
- **实验亮点**:
  - 大量系统消融（损失函数、注意力机制、顺序、多步预测等），验证了每个设计选择的有效性。
  - 速度/精度权衡对比清晰，展示了MAR+DiffLoss的实用优势。
  - 代码开源，可复现。

#### 8. 不足与局限：包括实验覆盖、偏差风险、应用限制等
- **实验覆盖局限**:
  - 仅使用ImageNet类别条件生成，未测试文本条件生成或其他数据集（如CIFAR、CelebA）。
  - 主要依赖LDM提供的预训练tokenizer（KL-16），tokenizer质量限制了生成上限（如reconstruction FID 21.2）。
  - 模型规模最大仅943M参数，未探索更大模型（如1B+）。
- **偏差风险**:
  - 基于ImageNet的训练可能反映数据集的偏见和局限性。
  - 生成图像有时出现明显伪影（附录图8），与DiT类似。
- **应用限制**:
  - 扩散损失需要额外的去噪MLP和采样多步，增加了推理计算量（虽然整体仍较快）。
  - 对于更高分辨率，当前使用的KL-16 tokenizer stride为16，直接扩展可能需更长的序列或更大patch。
  - 未在视频或多模态任务上验证。
- **其他**: 论文未报告误差棒，部分消融实验可能受随机种子影响。

（完）
