---
title: Normalizing Flows are Capable Generative Models
title_zh: 归一化流是强大的生成模型
authors: "Shuangfei Zhai, Ruixiang ZHANG, Preetum Nakkiran, David Berthelot, Jiatao Gu, Huangjie Zheng, Tianrong Chen, Miguel Ángel Bautista, Navdeep Jaitly, Joshua M. Susskind"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=2uheUFcFsM"
tags: ["query:ce"]
score: 6.0
evidence: 基于自回归变换器的归一化流用于图像生成
tldr: 针对归一化流近年关注不足的问题，提出TarFlow，一种基于Transformer的掩码自回归流，在图像块上交替自回归方向，能够端到端训练并直接生成像素，在图像生成任务上展现了优异性能，证明了简单可扩展的归一化流架构可以达到先进生成性能。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 898, \"height\": 445, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1746, \"height\": 654, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1772, \"height\": 677, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 709, \"height\": 947, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 687, \"height\": 507, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1774, \"height\": 542, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1790, \"height\": 926, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1775, \"height\": 371, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 893, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 892, \"height\": 936, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 892, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 892, \"height\": 932, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 894, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 892, \"height\": 919, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 893, \"height\": 893, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 893, \"height\": 913, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 892, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 891, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 893, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 892, \"height\": 933, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 892, \"height\": 894, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 892, \"height\": 920, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 889, \"height\": 893, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-2uheufcfsm/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 890, \"height\": 927, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 859, \"height\": 392, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 871, \"height\": 600, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 517, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 863, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 738, \"height\": 166, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 841, \"height\": 353, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-2uheufcfsm/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1629, \"height\": 242, \"label\": \"Table\"}]"
motivation: 归一化流近年受关注较少，潜力未被充分挖掘。
method: 提出TarFlow，基于Transformer的掩码自回归流，在图像块上交替自回归方向。
result: 在图像生成任务上表现优异，展示了归一化流的强大能力。
conclusion: 证明了简单可扩展的归一化流架构可以达到先进生成性能。
---

## Abstract
Normalizing Flows (NFs) are likelihood-based models for continuous inputs. They have demonstrated promising results on both density estimation and generative modeling tasks, but have received relatively little attention in recent years. In this work, we demonstrate that NFs are more powerful than previously believed. We present TarFlow: a simple and scalable architecture that enables highly performant NF models. TarFlow can be thought of as a Transformer-based variant of Masked Autoregressive Flows (MAFs): it consists of a stack of autoregressive Transformer blocks on image patches, alternating the autoregression direction between layers. TarFlow is straightforward to train end-to-end, and capable of directly modeling and generating pixels. We also propose three key techniques to improve sample quality: Gaussian noise augmentation during training, a post training denoising procedure, and an effective guidance method for both class-conditional and unconditional settings. Putting these together, TarFlow sets new state-of-the-art results on likelihood estimation for images, beating the previous best methods by a large margin, and generates samples with quality and diversity comparable to diffusion models, for the first time with a stand-alone NF model. We make our code available at https://github.com/apple/ml-tarflow.

---

## 论文详细总结（自动生成）

# 论文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：归一化流（NFs）是基于似然的连续输入生成模型，曾在密度估计和生成建模中取得良好效果，但近年关注度远低于扩散模型和大语言模型。作者质疑这种滞后是NFs本身的局限性，还是尚未找到合适的训练方式。
- **核心问题**：能否设计出简单、可扩展的NF架构，使其在图像密度估计和样本生成上达到与扩散模型相当的性能，从而证明NFs仍是强大的生成范式。
- **整体意义**：提出TarFlow架构，首次实现独立NF模型在ImageNet 64×64上BPD低于3.0，并在生成质量（FID）上接近扩散模型，重振对NF方向的信心。

## 2. 方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：将NF设计为堆叠的**块自回归流**，每个流块内使用**因果Transformer**（替代传统MLP）对图像块序列做自回归变换，并交替自回归方向（正序/逆序），从而构造深度、可逆的变换。
- **关键技术细节**：
  - **块自回归流**：输入图像先划分为 \(N\) 个块（patch），每个块维度 \(D\)。第 \(t\) 个流块 \(f_t\) 先对序列进行排列 \(\pi_t\)（除第一层外均为逆序），然后使用因果Transformer预测两个函数 \(\mu_t^i(\tilde{z}_{<i})\) 和 \(\alpha_t^i(\tilde{z}_{<i})\)，按公式 \(\tilde{z}_i^{t+1} = (\tilde{z}_i^t - \mu_t^i(\tilde{z}_{<i})) \odot \exp(-\alpha_t^i(\tilde{z}_{<i}))\) 做仿射变换。
  - **逆过程**：通过 \(\tilde{z}_i^t = z_i^{t+1} \odot \exp(\alpha_t^i(\tilde{z}_{<i})) + \mu_t^i(\tilde{z}_{<i})\) 及反排列恢复。
  - **损失函数**：最大似然等价于最小化 \(0.5\|z^T\|_2^2 + \sum_{t,i,j} \alpha_t^i(\tilde{z}_{<i})_j\)，即先验高斯项与Jacobian的行列式项。
  - **噪声增强训练**：使用高斯噪声（\(\sigma \approx 0.05\)）而非传统均匀去量化噪声，扩大训练分布支撑，提升生成泛化能力。
  - **基于分数的后处理去噪**：利用Tweedie公式 \(E[x|y] = y + \sigma^2 \nabla_y \log p_{\text{model}}(y)\)，对生成样本进行一步去噪，无需额外模块。
  - **指导（Guidance）**：对条件模型采用类似无分类器指导（CFG）的方法，对无条件模型通过调节注意力温度 \(\tau\) 构造低质量预测，再做指导外推。

## 3. 实验设计：数据集/场景、基准、对比方法

- **数据集**：
  - 无条件ImageNet 64×64（密度估计和生成）
  - 条件ImageNet 64×64、128×128
  - 条件AFHQ 256×256
- **基准**：BPD（比特/维度）用于似然评估；FID（Fr´echet Inception Distance）用于生成质量评估。
- **对比方法**：
  - 密度估计：与Glow、Flow++、PixelCNN、SPN、Sparse Transformer、VDM、Flow Matching、NFDM等对比。
  - 生成质量：与EDM、iDDPM、ADM、BigGAN、IC-GAN、CDM、RIN等扩散模型、GAN、一致性模型对比。
- **消融实验**：
  - 噪声强度 \(\sigma\) 与去噪效果（FID曲线）
  - 指导权重 \(w\) 与FID的关系（条件/无条件）
  - 模型缩放：不同深度配置（T×K）与训练损失、FID关系
  - 对比体积保持（VP）和通道耦合（移除因果掩码）变体
  - 训练损失与FID的典型曲线相关性

## 4. 资源与算力

- **硬件**：A100 GPU
- **数据类型**：默认bfloat16（似然任务使用float32避免数值问题）
- **训练时长与配置**：
  - 最优模型批量大小256~768，训练200~4000 epoch
  - 所有任务在14天内完成训练（作者提到更长时间可能更好）
  - 具体配置见表7：
    - 无条件ImageNet 64x64（生成）：patch=2, channels=768, 8 flows, 8 layers/flow，高斯噪声σ=0.05，batch=256，200 epoch，8 GPU
    - 条件ImageNet 64x64：patch=2, channels=1024, 8 flows, 8 layers/flow，batch=768，320 epoch，32 GPU
    - 条件ImageNet 128x128：patch=4, channels=1024, 8 flows, 8 layers/flow，batch=768，320 epoch，32 GPU
    - 条件AFHQ 256x256：patch=8, channels=768, 8 flows, 8 layers/flow，batch=256，4000 epoch，8 GPU

## 5. 实验数量与充分性

- **实验数量**：
  - 3个数据集（ImageNet 64/128, AFHQ 256）覆盖无条件、条件设置
  - 密度估计（BPD）在ImageNet 64上对比10+种方法
  - 生成质量（FID）对比8+种方法
  - 消融实验包括：3种噪声水平、多种指导权重、2种深度配置实验（T×K固定与变化）、VP/通道耦合变体、训练曲线分析
- **充分性评估**：
  - 实验设计较全面：考虑了主任务、消融、对比，且消融方向覆盖了关键设计（噪声、指导、深度、变体）。
  - 公平性：对比方法均使用标准公开结果或复现，但未公开NF领域其他模型FID数值（可能是首次），因此直接比较可能受限于不同训练设置。
  - 统计上：生成质量使用50K样本，符合常规。
  - **不足**：未在更高分辨率（如256×256 ImageNet）上验证；未与最前沿扩散模型（如Stable Diffusion 3）直接比较；去噪步骤仅论文中定性展示，定量消融中只给出FID曲线，未单独评估去噪对FID的具体贡献；指导机制在无条件模型上的有效性展示较简略。

## 6. 主要结论与发现

- **密度估计**：TarFlow在ImageNet 64×64上达到2.99 BPD，首次低于3.0，超越所有先前方法（包括扩散模型变体）。
- **生成质量**：FID在ImageNet 64×64上达到2.66（条件），优于GAN/一致性模型，接近扩散模型；ImageNet 128×128上FID 5.03，仍有差距但属NF最佳。
- **关键技术有效性**：
  - 高斯噪声增强（σ≈0.05）显著优于传统均匀去量化噪声，且必须配合后处理去噪才能发挥最佳效果。
  - 指导方法在条件/无条件模型上均有效，可连续调节生成保真度与多样性。
  - 模型深度需均衡分配流块数（T）与每块层数（K），最优比例约T=K；单块自回归（T=1）导致失败。
  - 体积保持（VP）或移除因果掩码（通道耦合）均大幅降低性能，说明非体积保持的自回归变换是核心。

## 7. 优点

- **架构简洁性**：仅由因果Transformer堆叠组成，无复杂的1×1卷积或多类型模块，易于实现和扩展。
- **训练稳定性**：损失函数简单（L2 + 线性项），训练曲线平滑，无数值不稳定性（相比连续NF或一些扩散模型）。
- **可扩展性**：通过增加T或K可平滑提升性能，与Transformer架构天然兼容，可利用现代硬件并行性。
- **无需额外去噪网络**：后处理去噪仅需模型本身的梯度计算，无需训练额外网络。
- **首次证明NF可达与扩散竞争的质量**：打破领域认知，为NF研究注入新动力。

## 8. 不足与局限

- **采样效率低**：反向过程需逐序列位置推理（尽管使用了KV-cache，但仍较慢），单次采样时间远高于扩散模型（尤其多步去噪时）。
- **分辨率上限**：仅在64/128/256分辨率测试，未在更高分辨率（如512×512）上验证，且AFHQ仅有3类，泛化性存疑。
- **指导机制不够成熟**：无条件指导依赖手动调节温度τ，缺乏理论指导；条件指导虽借鉴CFG，但性能仍弱于最先进扩散模型（如EDM、Simple Diffusion）。
- **噪声选择依赖调参**：最优σ需人工搜索，且不同分辨率/数据集需调整（如128×128时σ=0.15更好）。
- **实验覆盖不全**：未在视频、文本、1D信号等其他模态上验证；缺乏与近期扩散模型（如DDPM、LDM）在统一计算预算下的公平对比。
- **代码可用性**：论文提及开源，但截至分析时仓库可能未公开所有细节（如去噪实现、KV缓存采样代码）。

（完）
