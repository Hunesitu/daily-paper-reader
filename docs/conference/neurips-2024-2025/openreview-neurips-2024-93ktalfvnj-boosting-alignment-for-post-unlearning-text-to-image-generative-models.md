---
title: Boosting Alignment for Post-Unlearning Text-to-Image Generative Models
title_zh: 提升后遗忘文本到图像生成模型的对齐质量
authors: "Myeongseob Ko, Henry Li, Zhun Wang, Jonathan Patsenker, Jiachen T. Wang, Qinbin Li, Ming Jin, Dawn Song, Ruoxi Jia"
date: 2024-09-25
pdf: "https://openreview.net/pdf?id=93ktalFvnJ"
tags: ["query:ce"]
score: 8.0
evidence: 文本到图像生成模型的后遗忘对齐
tldr: 机器遗忘在文本到图像生成模型中常导致对齐质量下降。本文提出一个框架，在每个遗忘迭代中寻求最优更新，确保遗忘质量和文本-图像对齐单调改进。通过理论分析和实验验证，该方法在多个数据集上实现了更好的遗忘效果，同时保持甚至提升生成图像与提示的对齐，解决了遗忘与对齐之间的固有竞争。
source: NeurIPS-2024-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1219, \"height\": 478, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 729, \"height\": 479, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 868, \"height\": 705, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 546, \"height\": 604, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 964, \"height\": 311, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 950, \"height\": 434, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1240, \"height\": 1080, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1239, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1236, \"height\": 771, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1237, \"height\": 777, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-neurips-2024-93ktalfvnj/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1239, \"height\": 771, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-neurips-2024-93ktalfvnj/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 955, \"height\": 379, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93ktalfvnj/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1154, \"height\": 468, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93ktalfvnj/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1445, \"height\": 223, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93ktalfvnj/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 622, \"height\": 313, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93ktalfvnj/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1469, \"height\": 1283, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93ktalfvnj/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1466, \"height\": 1278, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93ktalfvnj/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1173, \"height\": 311, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-neurips-2024-93ktalfvnj/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1033, \"height\": 205, \"label\": \"Table\"}]"
motivation: 现有机器遗忘方法在消除有害知识时往往降低文本-图像对齐质量，两者存在竞争。
method: 提出单调优化框架，每步寻找最优更新，同时提升遗忘质量和对齐性能。
result: 在多数据集上，该方法在遗忘有效性和对齐指标上均优于基线。
conclusion: 该框架有效调和了遗忘与对齐的矛盾，提升了文本到图像模型的安全性与质量。
---

## Abstract
Large-scale generative models have shown impressive image-generation capabilities, propelled by massive data. However, this often inadvertently leads to the generation of harmful or inappropriate content and raises copyright concerns. Driven by these concerns, machine unlearning has become crucial to effectively purge undesirable knowledge from models. While existing literature has studied various unlearning techniques, these often suffer from either poor unlearning quality or degradation in text-image alignment after unlearning, due to the competitive nature of these objectives. To address these challenges, we propose a framework that seeks an optimal model update at each unlearning iteration, ensuring monotonic improvement on both objectives. We further derive the characterization of such an update.
  In addition, we design procedures to strategically diversify the unlearning and remaining datasets to boost performance improvement. Our evaluation demonstrates that our method effectively removes target classes from recent diffusion-based generative models and concepts from stable diffusion models while maintaining close alignment with the models' original trained states, thus outperforming state-of-the-art baselines.

---

## 论文详细总结（自动生成）

# 论文详细总结：Boosting Alignment for Post-Unlearning Text-to-Image Generative Models

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：大规模文本到图像生成模型（如 Stable Diffusion）在训练时使用了海量网络数据，容易生成有害内容（如裸体、暴力）或侵犯版权。机器遗忘（Machine Unlearning）旨在高效移除模型中的不良知识，但现有方法（如 SalUn、ESD）存在严重缺陷：要么遗忘效果不佳，要么在遗忘后导致生成图像与文本提示的语义对齐（text-image alignment）显著下降。
- **根源**：遗忘目标（最大化遗忘数据损失）与保留目标（最小化保留数据损失）本质上是竞争性的，直接聚合梯度更新往往顾此失彼；同时，现有方法构建保留数据集时过于简单（如仅用单一提示），导致过拟合，进一步损害对齐质量。
- **意义**：开发一种既能有效移除目标概念（如裸体、特定艺术风格），又能维持或接近原始模型对齐性能的遗忘方法，对于模型安全部署和遵守法规（如“被遗忘权”）至关重要。

## 2. 方法论：核心思想、关键技术细节
- **核心思想**：在每个遗忘迭代中寻求一个**最优更新方向**，使得遗忘损失和保留损失都能**单调递减**，从而调和两者的冲突。
- **关键技术方法**：
    1.  **受限梯度（Restricted Gradient, RG）**：
        - 定义：寻找方向 \(v\)，最小化联合损失 \(L_r + L_f\) 在 \(v\) 上的方向导数，同时满足两个约束：\(D_v L_r \le 0\) 且 \(D_v L_f \le 0\)（即同时改进两个损失）。
        - 理论推导（Theorem 4）：在线性近似下，最优更新为 \(\delta^*_f + \delta^*_r\)，其中：
            \[
            \delta^*_f = \nabla L_f - \frac{\nabla L_f \cdot \nabla L_r}{\|\nabla L_r\|^2} \nabla L_r, \quad 
            \delta^*_r = \nabla L_r - \frac{\nabla L_f \cdot \nabla L_r}{\|\nabla L_f\|^2} \nabla L_f.
            \]
          即分别将每个梯度投影到另一个梯度的法向上，再相加。这保证了更新方向不会违背任何单一目标的改进。
        - 与多任务学习中梯度手术（Gradient Surgery）的关系：本文首次给出了这一方法的严格目标函数解释。
    2.  **数据多样性（Data Diversification, RGD）**：
        - 动机：保留数据集 \(D_r\) 的多样性对维持模型性能至关重要。
        - 实现：对于 CIFAR-10，简单地从每个保留类中等量采样；对于 Stable Diffusion，使用大语言模型（LLM）生成与被遗忘概念 **c** 相关的多样化提示（如不同环境、情绪、动作），然后移除提示中的 **c** 得到保留提示 \(Y\)，再利用原始模型生成对应的图像 \(X\)，构成 \(D_r\)。
        - 效果：避免了过拟合，帮助模型找到更具代表性的受限梯度方向。
- **算法流程**（文字描述）：
    1.  准备遗忘数据集 \(D_f\)（如裸体概念相关图像-文本对）和保留数据集 \(D_r\)（经过多样性构造的无关数据）。
    2.  初始化模型参数为预训练权重 \(\theta_0\)。
    3.  对每个迭代：
        - 计算保留损失 \(L_r(\theta)\) 和遗忘损失 \(L_f(\theta)\)（遗忘损失带负号以最大化遗忘误差）。
        - 计算两个梯度 \(\nabla L_r\) 和 \(\nabla L_f\)。
        - 若梯度方向冲突（内积 < 0），则按照式(4)计算受限梯度更新 \(\delta^*_f + \delta^*_r\)；否则可直接求和。
        - 以学习率更新参数。
    4.  返回遗忘后的模型。

## 3. 实验设计
- **数据集与模型**：
    - **CIFAR-10 + EDM（扩散模型）**：用于类条件遗忘，逐步移除每个类（共10类）。
    - **Stable Diffusion v1.4**：用于概念移除，两个任务：
        - 裸体移除（使用 I2P 数据集评估）。
        - 艺术风格移除（如移除“梵高风格”，保留其他风格）。
- **Benchmarks & 对比方法**：
    - CIFAR-10 实验：Finetune, SalUn, GradDiff（梯度上升+下降），以及消融变体 RG（仅受限梯度）、RGD（受限梯度+数据多样性）。
    - Stable Diffusion 实验：原始 SD, ESD（全参数/非交叉注意力/交叉注意力版本），ESD-u, ESD-x, SalUn, GradDiffD（仅多样性的GradDiff）。
- **评估指标**：
    - 遗忘效果：CIFAR-10 上用 CLIP 零样本分类器计算**遗忘准确率（UA）**（1 - 目标类准确率）；Stable Diffusion 上用 Nudenet 检测裸体部位。
    - 保留性能：CIFAR-10 上**剩余准确率（RA）**和**FID**；Stable Diffusion 上用**CLIP对齐分数（AS）**（训练集和测试集）。
    - 特别地，CIFAR-10 上额外加入“随机噪声”类别以纠正分类器偏差。

## 4. 资源与算力
- 论文在 Appendix C 中说明：**所有实验使用 NVIDIA H100 GPU**。
- 未明确给出 GPU 数量、训练总时长、具体内存消耗等细节，仅提及批大小、学习率等。因此资源描述较为有限。

## 5. 实验数量与充分性
- **实验组数较多**：
    - CIFAR-10：遍历所有10个类作为遗忘目标，报告均值与标准差（Table 1）。
    - Stable Diffusion：两种概念移除（裸体、艺术风格），并分别评估训练和测试保留数据上的AS（Table 2）。
    - 消融实验：超参数（λ, α）敏感性（Figure 6）、多样性控制（Table 3：Case1 vs Case2）、数据集大小影响（Table 8）、不同预训练模型（SD v3, Table 7）等。
- **公平性与客观性**：
    - 严格控制变量：对比方法使用相同的数据集大小、超参数设置（尽量按原论文推荐）。
    - 对现有方法（如 SalUn）的局限性给出了清晰的定性（生成图像相似）和定量证据（AS低）。
    - 统计上报告了 CIFAR-10 上的方差，说明结果稳定。
- **结论**：实验覆盖了主要遗忘场景，进行了充分的消融分析和比较，整体较为充分、客观。

## 6. 主要结论与发现
- **所提方法（RGD）在两类任务中全面优于基线**：
    - **CIFAR-10**：遗忘准确率达 1.0（完全清除），剩余准确率（RA）最高（0.771），FID 最低（6.539），明显优于 SalUn 和 GradDiff。
    - **裸体移除**：Nudenet 检测到零暴露身体部位，而 SD 有598处、ESD-u 有48处、SalUn 有3处；同时对齐分数（AS）与原始 SD 几乎一致（0.350 vs 0.352），差距比 ESD-u 缩小 11 倍，比 SalUn 缩小 20 倍。
    - **艺术风格移除**：RGD 的对齐分数甚至略高于原始 SD（0.352 vs 0.348），且能正确生成其他风格（如莫奈、毕加索）。
- **关键发现**：
    - 受限梯度（RG）能有效克服梯度冲突，比直接求和梯度（GradDiff）提升 RA 和 FID。
    - 数据多样性（RGD）是维持模型泛化能力的关键，简单均匀采样（CIFAR-10）或 LLM 生成（SD）均有效。
    - 现有方法（SalUn）往往通过过拟合保留数据集来实现遗忘，导致生成图像缺乏多样性且对齐差。

## 7. 优点
- **理论新颖且严谨**：首次用受限梯度形式化定义了遗忘中同时改善两个目标的最优方向，并给出闭式解（Theorem 4），让“梯度手术”有了严格的目标函数解释。
- **方法简洁有效**：不需复杂架构修改，仅需在每次迭代中处理梯度投影，易于集成到现有训练流程。
- **关注到数据多样性问题**：通过 LLM 生成多样化的保留提示，设计巧妙，且实验证明其重要性。
- **实验全面**：覆盖分类模型和生成模型，对比了多种最新基线，并进行了细致的消融和超参数分析。
- **开源承诺**：代码将在 GitHub 公开。

## 8. 不足与局限
- **超参数敏感性**：方法对 λ（遗忘权重）和 α（损失截断）较敏感，需要调参才能达到最佳效果（文中承认这一点在 Limitations 中）。
- **数据多样性构造的偏差**：使用 LLM 生成保留提示，可能引入 LLM 自身的偏见或覆盖不全，且未研究不同采样策略（如近/远样本比例）的影响。
- **计算成本**：每次迭代需要计算两个梯度并做投影，相比简单求和略有增加；LLM 生成数据也需要额外成本。
- **评估局限**：
    - 主要实验在 SD v1.4 和 CIFAR-10（EDM）上，虽然附录补充了 SD v3 结果，但实验规模有限。
    - 未讨论对抗性攻击场景（如用户刻意用变体提示绕过遗忘）。
    - 未与基于 Fisher 信息矩阵的精确遗忘方法（如 Selective Synaptic Dampening）对比。
- **应用限制**：目前针对的是文本到图像模型，不直接适用于其他模态（如语言模型）。此外，遗忘的有效性可能依赖于数据集的质量和多样性。

（完）
