---
title: Minimalist Concept Erasure in Generative Models
title_zh: 生成模型中的最小化概念擦除
authors: "Yang Zhang, Er Jin, Yanfei Dong, Yixuan Wu, Philip Torr, Ashkan Khakzar, Johannes Stegmaier, Kenji Kawaguchi"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=oBCw6PZ0fX"
tags: ["query:ce"]
score: 9.0
evidence: 生成模型的最小化概念擦除方法
tldr: 针对现有概念擦除方法过度修改模型、损害实用性的问题，提出仅基于生成输出分布距离的最小化擦除目标，通过端到端反向传播优化，在保持模型效用下有效擦除概念，为生成模型的安全实用概念擦除提供了轻量级方案。
source: ICML-2025-Accepted
selection_source: conference_retrieval
motivation: 现有概念擦除方法过度修改模型，损害生成实用性。
method: 提出仅基于生成输出分布距离的最小化擦除目标，通过端到端反向传播优化。
result: 在保持模型效用下有效擦除概念。
conclusion: 为生成模型的安全实用概念擦除提供了轻量级方案。
---

## Abstract
Recent advances in generative models have demonstrated remarkable capabilities in producing high-quality images, but their reliance on large-scale unlabeled data has raised significant safety and copyright concerns. Efforts to address these issues by erasing unwanted concepts have shown promise. However, many existing erasure methods involve excessive modifications that compromise the overall utility of the model.
In this work, we address these issues by formulating a novel minimalist concept erasure objective based *only* on the distributional distance of final generation outputs. 
Building on our formulation, we derive a tractable loss for differentiable optimization that leverages backpropagation through all generation steps in an end-to-end manner. 
We also conduct extensive analysis to show theoretical connections with other models and methods. 
To improve the robustness of the erasure, we incorporate neuron masking as an alternative to model fine-tuning. 
Empirical evaluations on state-of-the-art flow-matching models demonstrate that our method robustly erases concepts without degrading overall model performance, paving the way for safer and more responsible generative models.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **研究动机**：当前生成模型（如 FLUX、SD3.5）因依赖大规模无标注训练数据，容易生成有害或受版权保护的内容（如 NSFW、武器、著名 IP 角色、艺术家风格）。现有概念擦除方法（如 ESD、CA、SLD）通常过度修改模型参数，导致模型生成能力退化（如 CLIP 对齐下降、FID 升高），且对对抗性提示缺乏鲁棒性。
- **整体含义**：论文旨在提出一种**最小化概念擦除**框架——在仅对模型做必要改变的前提下，有效擦除目标概念，同时最大程度保留模型原有生成质量和能力，并提高对恶意提示的抵抗性。

### 2. 论文提出的方法论

- **核心思想**：将概念擦除转化为一个优化问题，目标是最小化**最终生成结果**（而非中间步骤）中目标概念的识别概率，并使用 KL 散度限制与原始模型的分布差异，实现“刚刚好”的修改。
- **关键技术细节**：
  - **损失函数推导**：基于链式法则与高斯近似，将原始 KL 散度上界转为可微分的均方误差（MSE）项。最终优化目标为：
    \[
    L = \mathbb{E}_{c \in C_R, x_T}\left[\|F_\theta(x_T,c) - F_{\theta'}(x_T,\emptyset)\|_2^2\right] + \beta\,\mathbb{E}_{c \in C_N, x_T}\left[\|F_\theta(x_T,c) - F_{\theta'}(x_T,c)\|_2^2\right]
    \]
    其中 \(C_R\) 为要擦除的概念集，\(C_N\) 为中性概念集，\(F\) 表示整个采样流程，\(\theta'\) 为原始参数。
  - **端到端优化**：通过**步骤级梯度检查点**实现全生成步的反向传播，内存复杂度与步数无关，支持大模型优化。
  - **神经元掩码**：使用可学习的二值化掩码（基于 Hard-concrete 松弛）直接**裁剪**表示目标概念的神经元连接，替代权重微调，增强鲁棒性。
  - **提示过滤**：筛选背景一致且前景清晰的图像对，提升擦除精度。

### 3. 实验设计

- **使用数据集/场景**：
  - **目标概念**：不适当物品（枪、刀、毒品）、IP 角色（Hulk、Superman 等 5 个）、艺术风格（Van Gogh、Picasso 等 5 个）、色情内容。
  - **对抗攻击数据集**：Ring-A-Bell、MMA-Diffusion、P4D、I2P（均为公开的对抗性提示集）。
- **Benchmark**：FLUX.1-Schnell（最新 rectified flow 模型，12B 参数）。评估指标的标称值为 FLUX 原始模型性能。
- **对比方法**：ESD、CA、SLD、EAP、FlowEdit（共 5 种），均适配到 FLUX 架构并调优关键参数（如 β）。

### 4. 资源与算力

- **明确信息**：
  - 使用 **1× NVIDIA H100** GPU。
  - 训练步骤：**400 步**（约 40 步时概念已明显擦除）。
  - 批大小：**4**。
  - 学习率：FFN 和 Norm 层均为 0.5，优化器 Adam，权重衰减 1e-2。
  - 内存：借助步骤级梯度检查点，内存消耗与步数无关。

### 5. 实验数量与充分性

- **实验组数**：
  - **主实验**（表 1）：覆盖 3 大类 × 每类多个概念（如 inappropriate objects 含 3 个，IP 5 个，styles 5 个）。
  - **对抗攻击鲁棒性**（表 2，图 4）：4 个攻击数据集 + 正常提示 + LAION 5K FID 评估。
  - **消融实验**（图 5-6，表 3-5）：β 值、提示过滤、掩码模块选择、优化步数、训练数据规模（1/8/16/20）。
  - **额外视觉展示**（图 7-14 及附录）：包括 SD-XL 上的验证、NSFW 数据集过滤对比等。
- **充分性与公平性**：
  - 对比方法均调参适配 FLUX，且论文对 ESD 等做了额外参数调节（附录图 12）。
  - 评估指标多样（ACC 检测率、CLIP、FID、SSIM），采用标准检测器（NudeNet）和 GPT-4o 生成测试提示。
  - 消融实验设计合理，系统检验各组件贡献。
  - **潜在不足**：仅在一个主要模型（FLUX）上做全面比较，附录中仅有少量 SD-XL 示例；未与更多最新方法（如 SafetyDPO、Pruning for Robust CE）进行对比（因计算限制合理性说明）。

### 6. 论文的主要结论与发现

- **有效性与保持性**：提出方法在擦除效果上显著优于基线（如“色情”ACC 从基线最低 19% 降至 4%），同时 CLIP/FID/SSIM 接近原始模型，验证了**最小化干扰**原则。
- **鲁棒性**：在 4 种对抗攻击下，方法攻击成功率（ASR）大幅低于所有基线（如 Ring-A-Bell 从 45%→19%），证明了神经元掩码的强抵抗性。
- **理论统一性**：将概念擦除与 RLHF 对齐目标等价联系起来，提供了理论支撑。
- **扩展性**：推导了适用于扩散模型的类似损失，并在 SD-XL 上通过少量示例验证了模型无关性。

### 7. 优点

- **方法创新**：仅依赖最终输出分布距离进行擦除，避免对中间步骤的过度扰动，更精准。
- **高效计算**：步骤级梯度检查点使端到端优化在 12B 模型上可行，且内存开销恒定。
- **鲁棒性增强**：神经元掩码比权重微调更难被对抗性提示绕过，实验验证充分。
- **理论扎实**：严格推导损失上界，并与 RLHF 等框架建立联系。
- **实验全面**：涵盖 3 类概念 + 4 个公开攻击数据集 + 多项消融，评估客观。

### 8. 不足与局限

- **模型覆盖**：全面实验仅在 FLUX 上进行，SD-XL 仅作少量验证，未测试其他主流架构（如 DiT、UNet 的 SD3.5）。
- **对比方法数量**：未对比最新方法（如 SafetyDPO、AdvUnlearn），可能影响结论的时效性（论文解释为计算资源限制）。
- **训练数据规模**：擦除训练仅用 20 个提示（表 5），若概念多样或复杂时，可能不足以保证泛化。
- **硬件限制**：单 GPU 训练，无法支持多卡分布式或更细粒度的权重级掩码。
- **理论假设**：KL 散度推导中假设后验为高斯分布且协方差很小，实际采样可能偏离，引入近似误差。
- **后处理缺失**：未进行掩码后微调（受限于资源），可能影响最终性能上限。

（完）
