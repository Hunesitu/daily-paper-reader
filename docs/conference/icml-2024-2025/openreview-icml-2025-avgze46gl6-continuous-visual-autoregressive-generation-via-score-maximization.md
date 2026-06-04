---
title: Continuous Visual Autoregressive Generation via Score Maximization
title_zh: 通过评分最大化实现连续视觉自回归生成
authors: "Chenze Shao, Fandong Meng, Jie Zhou"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=avGZE46gL6"
tags: ["query:ce"]
score: 9.0
evidence: 无需量化的连续视觉自回归生成
tldr: 传统自回归模型处理连续视觉数据时需量化，导致信息损失。本文提出连续视觉自回归生成框架（Continuous VAR），无需向量量化，直接生成连续图像。核心理论是严格适当评分规则，将其作为训练目标。实验表明，该方法在图像生成质量上优于基于量化的VAR，且保持自回归模型的简洁性。这为自回归图像生成提供了新范式，尤其适用于需要连续输出的场景。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-avgze46gl6/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1458, \"height\": 737, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-avgze46gl6/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 846, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-avgze46gl6/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 843, \"height\": 464, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-avgze46gl6/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 761, \"height\": 333, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-avgze46gl6/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 773, \"height\": 341, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-avgze46gl6/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1685, \"height\": 782, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-avgze46gl6/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 846, \"height\": 279, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-avgze46gl6/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 843, \"height\": 283, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-avgze46gl6/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1772, \"height\": 1045, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-avgze46gl6/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 701, \"height\": 172, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-avgze46gl6/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 767, \"height\": 208, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-avgze46gl6/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1341, \"height\": 530, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-avgze46gl6/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 720, \"height\": 231, \"label\": \"Table\"}]"
motivation: 传统视觉自回归模型需量化离散化，造成信息损失，亟需直接处理连续数据的方法。
method: 基于严格适当评分规则，提出Continuous VAR框架，直接以连续值进行自回归生成，无需向量量化。
result: 该方法在图像生成任务上超越量化VAR，取得更高质量的生成结果。
conclusion: Continuous VAR为视觉自回归生成提供了无信息损失的有效方案。
---

## Abstract
Conventional wisdom suggests that autoregressive models are used to process discrete data. When applied to continuous modalities such as visual data, Visual AutoRegressive modeling (VAR) typically resorts to quantization-based approaches to cast the data into a discrete space, which can introduce significant information loss. To tackle this issue, we introduce a Continuous VAR framework that enables direct visual autoregressive generation without vector quantization. The underlying theoretical foundation is strictly proper scoring rules, which provide powerful statistical tools capable of evaluating how well a generative model approximates the true distribution. Within this framework, all we need is to select a strictly proper score and set it as the training objective to optimize. We primarily explore a class of training objectives based on the energy score, which is likelihood-free and thus overcomes the difficulty of making probabilistic predictions in the continuous space. Previous efforts on continuous autoregressive generation, such as GIVT and diffusion loss, can also be derived from our framework using other strictly proper scores. Source code: \url{https://github.com/shaochenze/EAR}.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 核心问题与整体含义（研究动机与背景）
- **问题**：传统视觉自回归模型（VAR）依赖向量量化将连续图像数据变为离散token，这一过程造成不可逆的信息损失（量化误差），制约了生成质量（尤其是低层次细节）和理解能力。
- **背景**：离散tokenizer的重构质量成为生成质量上限（如VQ-16重构FID 5.87 vs 连续KL-16的1.22）。同时，连续模态的自动回归生成缺乏统一理论框架，已有工作（GIVT、扩散损失）各有局限（GIVT表达能力受限于预定义高斯混合族；扩散损失需要多次去噪迭代，推理慢）。
- **动机**：提出无需量化的连续自回归生成框架，以严格适当评分规则（Strictly Proper Scoring Rules）为理论基石，通过最大化分数实现直接连续预测。

## 2. 方法论
- **核心思想**：选择严格适当的评分规则作为训练目标（最大化期望分数），使得模型分布唯一逼近真实分布。具体地，取负分作为损失：\( L_S(p, x) = -S(p, x) \)。对于序列自回归，采用序列损失：\( L_S(p, x) = -\sum_{t=1}^T S(p(\cdot|x_{<t}), x_t) \)。
- **关键技术细节**：
  - **能量分数**：\( S(p, y) = \mathbb{E}[|x_1 - x_2|^\alpha] - 2\mathbb{E}[|x - y|^\alpha] \)，其中 \(\alpha \in (0,2)\) 保证严格适当（\(\alpha=2\) 非严格，仅匹配期望）。
  - **能量损失**（无偏估计）：\( L = |x_1-y|^\alpha + |x_2-y|^\alpha - |x_1-x_2|^\alpha \)，其中 \(x_1, x_2\) 是模型独立采样，\(y\) 是真实标签。损失鼓励样本接近目标且保持多样性。
  - **模型架构（能量Transformer）**：与标准Transformer类似，但输入用线性投影替代查找表，输出用MLP生成器替代Softmax。MLP生成器输入为Transformer隐藏状态和随机噪声（均匀分布 \([-0.5,0.5]\), 维度64），通过多个残差块（自适应层归一化注入噪声）输出预测的连续token。MLP是隐式生成模型。
  - **其他技巧**：
    - 温度超参数：训练时对多样性项 \( |x_1-x_2|^\alpha \) 加权重 \(\tau_{train}<1\)；推理时仅缩放 \(shift(\epsilon)\) 为 \(\tau_{infer}\)。
    - 无分类器引导（CFG）：训练时10%丢弃条件，推理时线性增加引导尺度。
    - 掩码自回归生成：随机掩码比 [0.7,1.0]，64步余弦退火生成。
    - MLP生成器学习率系数：全局学习率8e-4，MLP生成器乘以0.25避免训练不稳定。

## 3. 实验设计
- **数据集和场景**：ImageNet 256×256 类条件生成（主要）；额外报告 ImageNet 512×512 结果。
- **基准**：对比了GAN（BigGAN、GigaGAN、StyleGAN-XL）、扩散模型（ADM、LDM、DiT-XL、L-DiT-7B、VDM++）、离散AR（VQGAN、RQ-Transformer、LlamaGen、MaskGIT、MAGE、MAGVIT-v2、VAR-d30）、连续AR（GIVT、MAR）。其中MAR是最直接竞争对手（均使用连续token、掩码Transformer）。
- **指标**：FID、Inception Score (IS)、Precision/Recall。
- **Tokenizer**：连续KL-16（重构FID 1.22），离散VQ-16（重构FID 5.87）用于对比实验。
- **模型配置**：EAR-B (205M), EAR-L (474M), EAR-H (937M)。MLP生成器约占15%参数。

## 4. 资源与算力
- **文中未明确说明**所使用的 GPU 型号、数量或训练总时长。仅提到训练 800 epochs（前750标准能量损失，后50降低温度 \(\tau_{train}=0.99\)），batch size 2048，使用 AdamW 优化器。未提供硬件配置细节。

## 5. 实验数量与充分性
- **实验组数丰富**：主要结果 Table 1 (3个模型大小 × 有/无CFG，与十余种方法对比)；α 消融 (Table 2: 5个值)；对比连续 vs 离散 (Figure 3)；高斯Transformer对比 (Figure 4)；学习率消融 (Figure 5)；噪声类型与维度 (Table 3)；CFG尺度 (Figure 7)；温度消融 (Figure 8)；512×512结果 (Table 4)；注意力掩码消融 (Table 5: 因果 vs 双向)。
- **充分性**：覆盖了关键设计维度（评分参数、架构变体、训练技巧）。实验客观：使用统一评估套件（Dhariwal & Nichol 2021），与MAR在同一连续tokenizer下对比速度（Figure 2）。消融设计合理，揭示了严格适当性和表达性的重要性。
- **潜在不足**：仅在一个数据集（ImageNet 256/512）上进行实验，未在其他视觉任务或模态上验证。

## 6. 主要结论与发现
- **能量Transformer在生成质量和推理效率上均优于传统离散VAR**：EAR-B (205M) 在CFG下FID 2.83，媲美LlamaGen-3B (2.18) 等大型离散模型；EAR-H (937M) FID 1.97，接近最佳扩散模型但推理快一个数量级（约1秒 vs MAR约10秒）。
- **严格适当性至关重要**：\(\alpha=2\)（非严格）导致FID>100完全失败；\(\alpha \in [1,2)\) 均有效，但 \(\alpha<1\) 梯度不稳定，训练崩溃。
- **隐式生成优于显式高斯假设**：高斯Transformer（MSE损失）FID远差于EAR，说明连续token分布复杂，预定义分布不足。
- **MLP生成器需更小学习率**：全局学习率8e-4下MLP生成器乘0.25可稳定训练，否则崩溃。
- **掩码双向注意力优于因果**：双向注意力获得显著更低FID（3.55 vs 8.10）。

## 7. 优点
- **理论统一性**：将GIVT（对数分数）、扩散损失（Hyvärinen分数）统一到连续VAR框架下，并提出基于能量分数的新实例。
- **无似然训练**：能量损失仅需采样，无需显式密度估计，允许设计更灵活的表达架构（MLP生成器）。
- **高效推理**：单步前向生成连续token，避开了扩散损失的多步去噪，速度优势明显。
- **公平比较**：与MAR使用相同连续tokenizer和掩码策略，速度/质量对比具有说服力。
- **消融全面**：对α、噪声、温度、CFG、学习率等关键超参数逐一实验，支撑设计选择。

## 8. 不足与局限
- **数值稳定性限制**：能量损失仅能在 \(\alpha \in [1,2)\) 有效（\(\alpha<1\) 梯度爆炸），缩小了严格适当分数选择范围。
- **超参数敏感**：需要调节训练温度 \(\tau_{train}\)、推理温度 \(\tau_{infer}\)、CFG尺度等，且 \(\tau_{train}>1\) 会导致损失无界不可用。
- **实验覆盖狭窄**：仅在ImageNet 256/512上进行条件生成，未验证无条件生成、其他数据集或多模态（视频、音频）任务。
- **参数量增加**：MLP生成器占总参数约15%，相比纯Transformer带来额外开销。
- **与SOTA扩散模型对比不完美**：EAR-H (937M) 在CFG下FID 1.97，而DiT-XL (675M) 在CFG下FID 2.27，参数量更多但FID优势不明显；且扩散模型可微调至更低FID（如VDM++ 2B FID 2.12）。需在同等计算预算下更系统对比。
- **推理速度比较仅针对MAR**，未与其他扩散模型（如DiT）在同一硬件上直接对比加速比。

（完）
