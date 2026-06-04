---
title: "EraseFlow: Learning Concept Erasure Policies via GFlowNet-Driven Alignment"
title_zh: EraseFlow：通过GFlowNet驱动的对齐学习概念擦除策略
authors: "Naga Sai Abhiram kusumba, Maitreya Patel, Kyle Min, Changhoon Kim, Chitta Baral, Yezhou Yang"
date: 2025-09-18
pdf: "https://openreview.net/pdf?id=igB289kbej"
tags: ["query:ce"]
score: 9.0
evidence: 通过GFlowNet驱动的去噪路径探索实现概念擦除
tldr: 文本到图像生成模型的概念擦除技术常损害图像质量或需大量重新训练。本文提出EraseFlow，将概念遗忘建模为去噪路径空间的探索，利用GFlowNet和轨迹平衡目标学习随机策略。通过采样整个去噪轨迹而非单一终点，该方法有效引导生成远离目标概念，同时保持模型原有能力。在多个概念擦除基准上，EraseFlow在擦除效果和生成质量上均达到最优。
source: NeurIPS-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1421, \"height\": 622, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 731, \"height\": 736, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 641, \"height\": 215, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1227, \"height\": 617, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1424, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1228, \"height\": 320, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1437, \"height\": 436, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 581, \"height\": 467, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 940, \"height\": 803, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1406, \"height\": 914, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1411, \"height\": 898, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1406, \"height\": 889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1407, \"height\": 888, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1407, \"height\": 881, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1408, \"height\": 877, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2025-igb289kbej/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1458, \"height\": 1021, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 659, \"height\": 150, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1449, \"height\": 596, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1446, \"height\": 525, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1092, \"height\": 499, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 624, \"height\": 237, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1368, \"height\": 373, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1448, \"height\": 488, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 772, \"height\": 351, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 674, \"height\": 186, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 733, \"height\": 302, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1315, \"height\": 1759, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1461, \"height\": 1329, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1387, \"height\": 2272, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 945, \"height\": 349, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2025-igb289kbej/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 946, \"height\": 348, \"label\": \"Table\"}]"
motivation: 现有概念擦除方法存在图像质量下降或依赖脆弱的对抗损失等问题。
method: 提出EraseFlow框架，将概念遗忘视为去噪轨迹的探索，使用GFlowNet优化轨迹平衡目标。
result: 在多个数据集上，EraseFlow实现了高擦除率同时保持生成质量，优于现有方法。
conclusion: EraseFlow提供了一种基于路径探索的概念擦除新范式，有效平衡了擦除与质量。
---

## Abstract
Erasing harmful or proprietary concepts from powerful text‑to‑image generators is an emerging safety requirement, yet current ``concept erasure'' techniques either collapse image quality, rely on brittle adversarial losses, or demand prohibitive retraining cycles. We trace these limitations to a myopic view of the denoising trajectories that govern diffusion‑based generation. We introduce EraseFlow, the first framework that casts concept unlearning as exploration in the space of denoising paths and optimizes it with a GFlowNets equipped with the trajectory‑balance objective. By sampling entire trajectories rather than single end states, EraseFlow learns a stochastic policy that steers generation away from target concepts while preserving the model’s prior. EraseFlow eliminates the need for carefully crafted reward models and by doing this, it generalizes effectively to unseen concepts and avoids hackable rewards while improving the performance. Extensive empirical results demonstrate that EraseFlow outperforms existing baselines and achieves an optimal trade-off between performance and prior preservation.

---

## 论文详细总结（自动生成）

# EraseFlow 论文详细总结

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：文本到图像扩散模型在生成安全合规内容方面面临挑战，需要有效擦除有害或受版权保护的概念（如 NSFW 内容、特定艺术风格、商业标识），但现有方法存在多重缺陷。
- **现有方法局限**：
  - 基于微调的方法（如 ESD、UCE）导致图像质量下降，且容易遭受对抗性攻击复原擦除概念。
  - 基于强化学习的方法（如 DUO）依赖脆弱奖励模型，易出现奖励欺骗（reward hacking）。
  - 对抗训练方法（如 AdvUnlearn、R.A.C.E）虽然鲁棒性较好，但计算成本极高（单概念训练需数小时至一天）。
- **根本原因分析**：作者指出现有方法对所有去噪时间步（timestep）同等对待，忽视了早期步骤高度不确定性、后期步骤趋于确定性的关键差异。这种短视视角导致对去噪轨迹控制不足，引发次优擦除效果。

## 2. 方法论
- **核心思想**：将概念遗忘（concept unlearning）重新定义为**去噪路径空间中的探索问题**，利用生成流网络（GFlowNets）的轨迹平衡（Trajectory Balance, TB）目标，学习一个随机策略，通过采样整个去噪轨迹而非单一终点来引导生成远离目标概念，同时保留模型原有先验分布。
- **关键技术细节**：
  - **扩散过程建模为 DAG**：将扩散去噪过程视为一个有向无环图，其中中间潜在变量 x_T, x_{T-1}, ..., x_0 作为状态 s_t。前向策略 p_θ(x_{t-1}|x_t, t, c) 对应扩散模型反向过程，反向策略 q(x_t|x_{t-1}) 则对应加噪核。
  - **轨迹平衡（TB）约束**：不同于详细平衡（DB），TB 优化整个轨迹的流一致性，更高效地在早期步骤分配信用，避免中间奖励估计噪声。损失函数为公式(7)：
    \[
    L_{TB}(φ,θ) = \left( \log Z_φ + \sum_{t=1}^T \log p_θ(x_{t-1}|x_t, t, c) - \log R'(x_0) - \sum_{t=1}^T \log q(x_t|x_{t-1}) \right)^2
    \]
  - **无奖励对齐（Reward-Free Alignment）**：核心创新点——不依赖外部奖励模型，而是使用**恒定奖励 β** 赋予锚点（安全）轨迹，目标轨迹奖励为零。通过最小化公式(8)强制目标条件分布完全匹配安全条件分布：
    \[
    L_{\text{EraseFlow}}^{c \leftarrow c^*} = \left( \log Z_φ + \sum_{t=1}^T \log p_θ(x^*_{t-1}|x^*_t, t, c) - \log β - \sum_{t=1}^T \log q(x^*_t|x^*_{t-1}) \right)^2
    \]
  - **理论保证**：命题 4.1 证明，当损失为零时，对于每个时间步都有 p_{θ*}(x_{t-1}|x_t, t, c) = p_θ(x_{t-1}|x_t, t, c^*)，从而最终图像分布完全一致，实现概念彻底擦除。
  - **算法流程**（Algorithm 1）：
    - 每个 epoch 首先采样一条锚点提示 c* 下的完整去噪轨迹 τ'。
    - 仅在 STOP_SAMPLING 之前重新采样锚点轨迹，之后固定使用同一轨迹以稳定训练。
    - 使用目标提示 c 与锚点轨迹计算上述损失，更新模型参数 θ 和流分区函数 Z_φ。
    - 实际训练中仅采样部分时间步（前 40 步中随机 10 步 + 最后 10 步）以节省内存。

## 3. 实验设计
- **三个评估场景**：
  1. **NSFW（Nudity）**：擦除裸体概念。
  2. **艺术风格**：擦除 Van Gogh 和 Caravaggio 两种风格。
  3. **细粒度概念**：擦除 Nike 标识、Coca-Cola 标识、Pegasus 的翅膀。
- **数据集与评测集**：
  - NSFW：I2P（142 提示）、Ring-a-Bell（79 提示）、MMA-Diffusion（1000 提示）、UDAtk（142 对抗提示）。
  - 艺术风格：每个目标风格 50 个 UDAtk 生成的对抗提示。
  - 细粒度：每个概念 10 个多样化提示（GPT-4o 生成），每个提示生成 10 张图像，使用 Gecko VQA 框架评估。
- **对比方法**（分为三类）：
  - 非对抗训练：ESD, UCE, MACE, DUO, EraseFlow（本文）
  - 推理时干预：SAFREE（训练无关）
  - 对抗训练：R.A.C.E, AdvUnlearn
  - 还评估了 EraseFlow 与 SAFREE 或 AdvUnlearn 的组合效果。
- **评估指标**：
  - NSFW：攻击成功率（ASR），使用 NudeNet 检测（阈值 0.6）。
  - 艺术风格：CSD 特征余弦相似度（越低越好）。
  - 细粒度：概念分数（擦除目标正确否）和总分数（兼顾保留全部元素的正确率）。
  - 图像质量：CLIP Score（↑）、FID（↓）、训练时间（分钟）、峰值内存（GB）。

## 4. 资源与算力
- **GPU 配置**：单块 NVIDIA A100 80GB GPU。
- **训练时长**：
  - EraseFlow 仅需约 **2.8 分钟**（nudity 任务）。
  - 对比：R.A.C.E 需 225 分钟，AdvUnlearn 需 1440 分钟（24 小时）。
  - 艺术风格和细粒度任务类似量级。
- **峰值内存**：EraseFlow 约 42 GB（高于多数基线如 UCE 的 0.4 GB，但低于 AdvUnlearn 的 33.7 GB? 实际表中 EraseFlow 42 GB，说明内存需求较高）。
- **结论**：EraseFlow 以极低训练成本（分钟级）达到与小时级对抗方法可比的擦除效果，效率优势显著。

## 5. 实验数量与充分性
- **实验组数目**：
  - 主实验：3 个大任务×多数据集，共报告多项表格（Table 1-4, 7, 11, 13 等）。
  - 消融实验：5 项（logβ、STOP_SAMPLING、锚点提示类型、时间步选择、logβ 与 log zφ 联合）。
  - 扩展实验：多概念擦除（1/5/100 概念）、泛化至 Flux 模型、组合方法效果。
  - 定性对比：16 张生成图像对比图（含失败案例）。
- **充分性与公平性**：
  - **充分**：覆盖了主流基准（I2P, Ring-a-Bell, MMA-Diff, UDAtk），消融全面，对关键超参数进行了系统分析。
  - **公平**：对比方法采用官方实现或复现，超参数尽量沿用原文（Table 4-5 说明模型来源）。但未报告统计显著性（误差棒），文中注明“NA”。
  - **客观**：定量指标清晰，定性图显示直观对比，同时承认了失败案例。

## 6. 主要结论与发现
- **核心结论**：EraseFlow 在大多数任务上达到或超过现有最优方法，尤其在 NSFW 对抗攻击（UDAtk）上将 ASR 从 100% 降至 33.89%，优于所有非对抗方法和部分对抗方法（RACE 50.84%）。与 AdvUnlearn 组合后 ASR 降至 1.42%，几乎完全消除风险。
- **生成质量保留**：FID = 17.93，仅次于 MACE（17.11）；CLIP Score = 25.67，与 UCE/DUO 相当，远优于对抗方法（AdvUnlearn FID = 21.64）。
- **细粒度擦除**：总分数 76.01 超越 DUO（71.32），概念分数 83.24 与 ESD 接近（93.97）但 ESD 过度擦除导致总分数低。
- **效率**：训练时间仅 2.8 分钟，相比 AdvUnlearn（1440 分钟）提升约 500 倍。
- **鲁棒性**：无需对抗训练即可抵御多种攻击（UDAtk、Ring-a-Bell等），与训练无关方法 SAFREE 组合进一步提升。
- **泛化性**：成功扩展至 SDv3/Flux 等最新架构，在 Flux 上 I2P 降至 16.90%，优于 EraseAnything（24.60%）。

## 7. 优点
- **方法创新性**：首次将 GFlowNet 引入概念擦除，利用完整去噪轨迹进行全局优化，避免了以往方法对单一终点的短视。
- **无奖励设计**：理论证明恒定奖励足以实现完全分布对齐，消除了奖励模型带来的不稳定和可欺骗性，泛化到任意未见概念。
- **即插即用**：可轻松与 SAFREE（训练无关）或 AdvUnlearn（对抗训练）结合，进一步提升性能。
- **高效率与低资源**：分钟级训练即可达到小时级对抗方法的效果，适合实际部署。
- **形式保证**：命题 4.1 提供了理论上的分布一致性 guarantee，增强可靠性。
- **全面评估**：覆盖 NSFW、艺术风格、细粒度三种场景，消融实验深入，定量定性结果丰富。

## 8. 不足与局限
- **多概念扩展受限**：在擦除大量概念（如 100 个名人）时，性能下降明显（Unlearn 分数 65.6%，保留率 65.65%），概念间干扰问题突出。
- **内存需求较高**：峰值内存 42 GB，是 UCE（0.4 GB）的 100 倍，对资源受限环境不友好。
- **锚点提示依赖**：需要手动设计安全锚点提示（如“Fully dressed”），表 6 显示锚点选择对性能影响显著，实际应用可能需要针对每个目标概念精心设计。
- **泛化不完全**：在 Flux 上提升不如 Diffusion 架构显著（I2P 从 36.66% 降至 16.

.90%，相比 AdvUnlearn 组合后的 1.42% 仍有较大差距，说明在更强生成模型上实现彻底擦除更具挑战性。
- **超参数敏感**：关键超参数如 logβ（默认 83）和 STOP_SAMPLING（默认 5）的微小变化会显著影响擦除效果（见表 9、10），实际部署需要仔细调参。
- **锚点轨迹固定机制**：训练中后期固定锚点轨迹虽提高了稳定性，但可能导致对锚点轨迹的过拟合，限制了对未见概念的泛化。
- **评估指标局限**：未报告统计显著性（误差棒），且艺术风格擦除仅依赖 CSD 相似度，可能遗漏更高层级语义变化。

（完）
