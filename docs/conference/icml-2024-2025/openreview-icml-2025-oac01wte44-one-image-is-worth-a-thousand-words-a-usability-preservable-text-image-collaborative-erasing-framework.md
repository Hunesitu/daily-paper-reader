---
title: "One Image is Worth a Thousand Words: A Usability Preservable Text-Image Collaborative Erasing Framework"
title_zh: 一图胜千言：可用性保持的文本-图像协作擦除框架
authors: "Feiran Li, Qianqian Xu, Shilong Bao, Zhiyong Yang, Xiaochun Cao, Qingming Huang"
date: 2025-05-01
pdf: "https://openreview.net/pdf?id=OaC01wTE44"
tags: ["query:ce"]
score: 8.0
evidence: 提出文本-图像协作擦除框架用于文本到图像扩散模型中的概念擦除
tldr: 针对现有概念擦除方法依赖文本提示导致效果与可用性难以兼得的问题，提出文本-图像协作擦除框架，直接引入视觉监督以弥合模态差距，在保持模型对其他概念生成能力的同时实现高效概念擦除，实验证明该框架在多种有害概念移除上显著优于现有方法。
source: ICML-2025-Accepted
selection_source: conference_retrieval
figures_json: "[{\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1431, \"height\": 751, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 845, \"height\": 425, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 861, \"height\": 429, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 860, \"height\": 608, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 854, \"height\": 432, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 860, \"height\": 468, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 871, \"height\": 545, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 803, \"height\": 453, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1745, \"height\": 891, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1778, \"height\": 699, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 854, \"height\": 744, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 863, \"height\": 375, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 866, \"height\": 372, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1744, \"height\": 896, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1641, \"height\": 362, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 1667, \"height\": 358, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 1596, \"height\": 728, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1595, \"height\": 722, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1594, \"height\": 718, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-020.webp\", \"caption\": \"\", \"page\": 0, \"index\": 20, \"width\": 1590, \"height\": 715, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-021.webp\", \"caption\": \"\", \"page\": 0, \"index\": 21, \"width\": 1646, \"height\": 1554, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-022.webp\", \"caption\": \"\", \"page\": 0, \"index\": 22, \"width\": 1695, \"height\": 1862, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-023.webp\", \"caption\": \"\", \"page\": 0, \"index\": 23, \"width\": 1722, \"height\": 1889, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-024.webp\", \"caption\": \"\", \"page\": 0, \"index\": 24, \"width\": 1702, \"height\": 1793, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-025.webp\", \"caption\": \"\", \"page\": 0, \"index\": 25, \"width\": 1664, \"height\": 1948, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-026.webp\", \"caption\": \"\", \"page\": 0, \"index\": 26, \"width\": 1640, \"height\": 1932, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-027.webp\", \"caption\": \"\", \"page\": 0, \"index\": 27, \"width\": 1619, \"height\": 1821, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-028.webp\", \"caption\": \"\", \"page\": 0, \"index\": 28, \"width\": 1495, \"height\": 2002, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-029.webp\", \"caption\": \"\", \"page\": 0, \"index\": 29, \"width\": 1344, \"height\": 278, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-030.webp\", \"caption\": \"\", \"page\": 0, \"index\": 30, \"width\": 1341, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-031.webp\", \"caption\": \"\", \"page\": 0, \"index\": 31, \"width\": 1344, \"height\": 284, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-032.webp\", \"caption\": \"\", \"page\": 0, \"index\": 32, \"width\": 1339, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-033.webp\", \"caption\": \"\", \"page\": 0, \"index\": 33, \"width\": 1345, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-034.webp\", \"caption\": \"\", \"page\": 0, \"index\": 34, \"width\": 1323, \"height\": 281, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-035.webp\", \"caption\": \"\", \"page\": 0, \"index\": 35, \"width\": 1344, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-036.webp\", \"caption\": \"\", \"page\": 0, \"index\": 36, \"width\": 1328, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-037.webp\", \"caption\": \"\", \"page\": 0, \"index\": 37, \"width\": 1340, \"height\": 286, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-038.webp\", \"caption\": \"\", \"page\": 0, \"index\": 38, \"width\": 1352, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-039.webp\", \"caption\": \"\", \"page\": 0, \"index\": 39, \"width\": 1554, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-040.webp\", \"caption\": \"\", \"page\": 0, \"index\": 40, \"width\": 1338, \"height\": 280, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-041.webp\", \"caption\": \"\", \"page\": 0, \"index\": 41, \"width\": 1347, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-042.webp\", \"caption\": \"\", \"page\": 0, \"index\": 42, \"width\": 1338, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-043.webp\", \"caption\": \"\", \"page\": 0, \"index\": 43, \"width\": 1348, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-044.webp\", \"caption\": \"\", \"page\": 0, \"index\": 44, \"width\": 1341, \"height\": 277, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-045.webp\", \"caption\": \"\", \"page\": 0, \"index\": 45, \"width\": 1338, \"height\": 282, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-046.webp\", \"caption\": \"\", \"page\": 0, \"index\": 46, \"width\": 1343, \"height\": 288, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-047.webp\", \"caption\": \"\", \"page\": 0, \"index\": 47, \"width\": 1338, \"height\": 289, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-048.webp\", \"caption\": \"\", \"page\": 0, \"index\": 48, \"width\": 1346, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-049.webp\", \"caption\": \"\", \"page\": 0, \"index\": 49, \"width\": 1265, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-050.webp\", \"caption\": \"\", \"page\": 0, \"index\": 50, \"width\": 1294, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-051.webp\", \"caption\": \"\", \"page\": 0, \"index\": 51, \"width\": 1254, \"height\": 271, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-052.webp\", \"caption\": \"\", \"page\": 0, \"index\": 52, \"width\": 1262, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-053.webp\", \"caption\": \"\", \"page\": 0, \"index\": 53, \"width\": 1249, \"height\": 269, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-054.webp\", \"caption\": \"\", \"page\": 0, \"index\": 54, \"width\": 1255, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-055.webp\", \"caption\": \"\", \"page\": 0, \"index\": 55, \"width\": 1254, \"height\": 270, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-056.webp\", \"caption\": \"\", \"page\": 0, \"index\": 56, \"width\": 1269, \"height\": 272, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-057.webp\", \"caption\": \"\", \"page\": 0, \"index\": 57, \"width\": 1312, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-058.webp\", \"caption\": \"\", \"page\": 0, \"index\": 58, \"width\": 1318, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-059.webp\", \"caption\": \"\", \"page\": 0, \"index\": 59, \"width\": 1317, \"height\": 287, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-060.webp\", \"caption\": \"\", \"page\": 0, \"index\": 60, \"width\": 1325, \"height\": 285, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-061.webp\", \"caption\": \"\", \"page\": 0, \"index\": 61, \"width\": 1324, \"height\": 290, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-062.webp\", \"caption\": \"\", \"page\": 0, \"index\": 62, \"width\": 1446, \"height\": 2012, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-063.webp\", \"caption\": \"\", \"page\": 0, \"index\": 63, \"width\": 1222, \"height\": 268, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-064.webp\", \"caption\": \"\", \"page\": 0, \"index\": 64, \"width\": 1233, \"height\": 267, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-065.webp\", \"caption\": \"\", \"page\": 0, \"index\": 65, \"width\": 1222, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-066.webp\", \"caption\": \"\", \"page\": 0, \"index\": 66, \"width\": 1226, \"height\": 276, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-067.webp\", \"caption\": \"\", \"page\": 0, \"index\": 67, \"width\": 1230, \"height\": 273, \"label\": \"Figure\"}, {\"url\": \"assets/figures/openreview/openreview-icml-2025-oac01wte44/fig-068.webp\", \"caption\": \"\", \"page\": 0, \"index\": 68, \"width\": 847, \"height\": 1166, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1693, \"height\": 452, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 899, \"height\": 317, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 849, \"height\": 188, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 805, \"height\": 274, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1354, \"height\": 449, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1766, \"height\": 2195, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1281, \"height\": 1895, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1115, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1120, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-010.webp\", \"caption\": \"\", \"page\": 0, \"index\": 10, \"width\": 1130, \"height\": 422, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-011.webp\", \"caption\": \"\", \"page\": 0, \"index\": 11, \"width\": 1130, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-012.webp\", \"caption\": \"\", \"page\": 0, \"index\": 12, \"width\": 1129, \"height\": 404, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-013.webp\", \"caption\": \"\", \"page\": 0, \"index\": 13, \"width\": 1132, \"height\": 423, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-014.webp\", \"caption\": \"\", \"page\": 0, \"index\": 14, \"width\": 1131, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-015.webp\", \"caption\": \"\", \"page\": 0, \"index\": 15, \"width\": 1106, \"height\": 424, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-016.webp\", \"caption\": \"\", \"page\": 0, \"index\": 16, \"width\": 796, \"height\": 185, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-017.webp\", \"caption\": \"\", \"page\": 0, \"index\": 17, \"width\": 996, \"height\": 1443, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-018.webp\", \"caption\": \"\", \"page\": 0, \"index\": 18, \"width\": 1007, \"height\": 363, \"label\": \"Table\"}, {\"url\": \"assets/tables/openreview/openreview-icml-2025-oac01wte44/table-019.webp\", \"caption\": \"\", \"page\": 0, \"index\": 19, \"width\": 1694, \"height\": 407, \"label\": \"Table\"}]"
motivation: 现有概念擦除方法依赖文本提示，难以在擦除效果和模型可用性之间取得平衡。
method: 提出文本-图像协作擦除框架，引入视觉监督直接指导擦除过程。
result: 在多个概念擦除任务上实现了高擦除率，同时保持了对其他概念的生成质量。
conclusion: 该工作为文本到图像模型的概念擦除提供了更有效且可用性更好的方案。
---

## Abstract
Concept erasing has recently emerged as an effective paradigm to prevent text-to-image diffusion models from generating visually undesirable or even harmful content. However, current removal methods heavily rely on manually crafted text prompts, making it challenging to achieve a high erasure (**efficacy**) while minimizing the impact on other benign concepts (**usability**), as illustrated in Fig.1. In this paper, we attribute the limitations to the inherent gap between the text and image modalities, which makes it hard to transfer the intricately entangled concept knowledge from text prompts to the image generation process. To address this, we propose a novel solution by directly integrating visual supervision into the erasure process, introducing the first text-image Collaborative Concept Erasing (**Co-Erasing**) framework. Specifically, Co-Erasing describes the concept jointly by text prompts and the corresponding undesirable images induced by the prompts, and then reduces the generating probability of the target concept through negative guidance. This approach effectively bypasses the knowledge gap between text and image, significantly enhancing erasure efficacy. Additionally, we design a text-guided image concept refinement strategy that directs the model to focus on visual features most relevant to the specified text concept, minimizing disruption to other benign concepts. Finally, comprehensive experiments suggest that Co-Erasing outperforms state-of-the-art erasure approaches significantly with a better trade-off between efficacy and usability.

---

## 论文详细总结（自动生成）

# 论文中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

文本到图像扩散模型（如Stable Diffusion）在生成高质量图像的同时，可能产生不期望的有害内容（如NSFW图像）。现有概念擦除方法（concept erasing）大多仅依赖文本提示来定义要擦除的概念，导致两个关键目标难以兼得：

- **高擦除效果（efficacy）**：使模型避免生成指定不良概念；
- **高可用性（usability）**：保持模型对其他良性概念的生成质量和提示对齐。

作者指出，单纯使用文本存在固有局限：文本与图像模态之间存在“语义鸿沟”——语义上良性的文本可能诱导模型产生不当视觉内容；同时，概念本身复杂纠缠，有限的文本单词难以完全解耦和表示概念。因此，现有方法要么擦除不彻底（如ESD、FMN），要么严重损害生成质量（如SalUn、AdvUnlearn）。论文提出引入图像模态，直接提供视觉监督，以弥合模态差距，实现效果与可用性的平衡。

## 2. 论文提出的方法论

### 核心思想
使用文本提示和对应的不良图像共同描述目标概念，通过负引导（negative guidance）在训练中降低模型生成该概念的概率。图像由原始模型自生成，作为视觉模板，直接提供概念相关的视觉特征，绕过文本-图像间隙。

### 关键技术细节

1. **文本-图像协作框架（Co-Erasing）**：
   - 采用两个独立的编码器分支：文本分支使用CLIP文本编码器，图像分支使用CLIP图像编码器+预训练投影模型（来自IP-Adapter）。
   - 在U-Net的交叉注意力层中实现解耦交叉注意力：分别计算文本嵌入和图像嵌入的注意力，输出相加：\( Z_t^{\text{att}} = Z_t^{\text{text}} + Z_t^{\text{image}} \)。
   - 图像分支仅在训练时使用，推理时不需额外开销。

2. **负引导擦除**：基于ESD框架，修改噪声预测：
   \[
   \epsilon_{\theta^*}(Z_t, c, t) \leftarrow \epsilon_{\theta}(Z_t, t) - \eta [\epsilon_{\theta}(Z_t, c, t) - \epsilon_{\theta}(Z_t, t)]
   \]
   其中条件 \( c = [c_{\text{text}}, c_{\text{image}}] \)，通过降低条件概率 \( P_{\theta}(c|x) \) 实现擦除。

3. **文本引导的图像概念细化模块（Text-Guided Image Concept Refinement）**：
   - 为避免图像中的无关视觉信息（如背景、树）干扰擦除，使用注意力机制提取与目标文本词最相关的视觉特征。
   - 公式：\( c_{\text{image}} = \text{Softmax}(Q_r K_r^\top / \sqrt{d_r}) V_r \)，其中 \( Q_r = E_{\text{image}}(X) \)，\( K_r = V_r = E_{\text{text}}(Y) \)（Y为目标概念文本）。
   - 细化后的 \( c_{\text{image}} \) 与文本特征 \( c_{\text{text}} \) 并行注入交叉注意力。

4. **自生成图像**：擦除前使用原始模型根据模板“a photo of c”生成 \( n \) 张图像（如nudity用200张），作为视觉模板。实验表明自生成图像优于从真实NSFW数据集采样的图像，因为更贴近模型内部知识分布。

### 算法流程简述
1. 用原始SD生成目标概念图像集。
2. 每轮训练随机选一张自生成图像。
3. 通过CLIP文本编码器和图像编码器+投影模型分别获取 \( c_{\text{text}} \) 和 \( c_{\text{image}} \)（经过细化模块）。
4. 在交叉注意力层进行解耦计算，合并后作为条件。
5. 使用负引导损失微调U-Net全部参数，降低目标概念条件概率。
6. 推理时仅使用文本分支，模型结构不变。

## 3. 实验设计

### 任务与场景
- **nudity（色情内容）**：擦除不雅内容。
- **style（艺术风格）**：如Van Gogh、Picasso风格。
- **objects（物体）**：parachute, church, tench, French horn, garbage truck等。
- **portraits（人像）**：擦除特定人物（如Amanda Seyfried、Bill Gates等）。
- **multi-concepts（多概念）**：同时擦除多个物体（如church + French horn）。

### 评估指标
- **擦除效果**：pre-ASR、ASR（含对抗攻击）、P4D、CCE（越低越好）。
- **可用性**：FID（越低越好，与COCO-10k比较）、CLIP score（越高越好）。
- 还使用Ring-A-Bell (RAB) 攻击测试鲁棒性，以及CIFAR-10/100分类准确率衡量模型保留能力。

### 对比方法
共9种：ESD, FMN, AC, UCE, SPM, SH, ED, SalUn, AdvUnlearn。每种方法在各自适用的任务上进行比较。

### 数据集
- 自生成图像（目标概念）。
- 评估用I2P数据集（inappropriate image prompts）、COCO-10k、CIFAR-10/100、自定义GPT生成提示。
- NSFW真实数据集（用于对比实验）。

### 实验充分性
- 除主任务外，进行了消融实验（文本vs图像vs细化模块、图像数量、真实vs合成图像）。
- 迁移实验：将Co-Erasing集成到SLD和MACE框架中，验证通用性。
- 对抗攻击：UDA（Zhang et al., 2024d）、P4D、CCE、RAB。
- 细粒度分析：统计NSFW标签（如女性乳房暴露等）减少情况。
- 多概念和肖像擦除，可视化大量生成样本。
- 代码已开源。

## 4. 资源与算力

论文明确提到：
- 使用单张NVIDIA GeForce RTX 4090。
- 生成图像速度约1秒/张，最大200张约3分钟，几乎可忽略。
- 优化器为Adam，学习率1e-5，batch size 1。
- 训练时每轮随机选一张自生成图像。
- 未报告总训练时长（但通常微调扩散模型需数小时）。

## 5. 实验数量与充分性

论文进行了大量实验，覆盖以下方面（不少于15组主要实验）：
- 4个主要任务（nudity, Van Gogh, parachute, church）的量化对比（Table 9-12）及雷达图（Fig 9）。
- 另外4个任务（French horn, tench, garbage truck, Picasso）的额外结果（Table 13-16, Fig 14）。
- 消融实验（Table 3, Table 18）验证各模块贡献。
- 图像数量影响（Fig 13, 15, 16）从1到200。
- 自生成vs真实图像对比（Table 4）。
- 迁移到SLD和MACE（Table 2, Table 20, Table 1）。
- 对抗攻击测试（RAB, P4D, CCE, UDA）。
- 细粒度NSFW标签统计（Table 19）。
- CIFAR-10/100分类准确率（Table 17）。
- 肖像擦除和多概念擦除的可视化（Appendix C.5, C.6）。
- 失败案例展示（Fig 39）。

实验设计较为公平：对比方法均来自官方或复现，评估指标一致。消融实验充分证明了各组件的必要性。

## 6. 论文的主要结论与发现

1. **图像模态显著提升擦除效果**：仅用文本时ASR达76.05%，加入自生成图像后降至16.96%；加入细化模块后进一步降至0.85%（pre-ASR）。
2. **文本引导细化模块保护可用性**：无细化时FID上升至24.56，有细化后改善至18.77，同时CLIP score保持0.302。
3. **自生成图像优于真实图像**：自生成图像在效果和可用性上均优于真实NSFW数据集图像（Table 4）。
4. **无需大量图像**：使用200张图像即可达到较好平衡，更多图像收益递减。
5. **可迁移到其他框架**：集成到SLD和MACE后，擦除效果进一步提升，可用性损失极小。
6. **Co-Erasing显著优于现有方法**：在几乎所有任务上，Co-Erasing同时实现了高擦除效果和高可用性，而其他方法往往牺牲其中一方。

## 7. 优点

- **创新性**：首次提出文本-图像协作的概念擦除范式，直接利用视觉信息弥补模态鸿沟。
- **实用性**：图像分支仅在训练时需要，推理时零额外开销；自生成图像无需外部数据集。
- **通用性**：可轻松嵌入现有擦除框架（ESD, SLD, MACE），不依赖特定骨干。
- **全面性**：在多种概念（色情、风格、物体、肖像、多概念）上验证有效性，在多种对抗攻击下保持鲁棒。
- **可解释性**：通过文本引导细化模块，模型聚焦于概念相关视觉特征，可视化证明了其作用。
- **开源代码**，利于复现和后续研究。

## 8. 不足与局限

- **部分对象擦除仍有失败案例**：附录C.7展示了某些物体（如马、教堂）擦除后仍有少量特征残留，可能因为那些视觉特征并非目标概念独有，自生成图像中未充分包含，导致遗漏。
- **依赖自生成图像质量**：若原始模型本身对目标概念生成能力弱（如“parachute”需要附加提示才能生成），则自生成图像可能不典型，影响擦除效果。论文通过随机附加短语解决了部分问题，但未全面讨论。
- **训练开销**：虽然生成图像时间短，但微调U-Net所有参数仍需一定计算资源（单卡RTX 4090数小时），未与轻量级微调方法（如只微调注意力层）对比。
- **未讨论对模型公平性或偏见的影响**：擦除可能意外削弱模型对某些良性但视觉相似概念（如人体艺术）的生成能力，论文仅用FID/CLIP衡量，缺乏对特定边缘情况的深入测试。
- **实验范围**：主要在Stable Diffusion v1.4上评估，未在更大模型（如SDXL）上验证迁移性（但SLD和MACE迁移实验部分覆盖了其他版本）。
- **量化指标局限**：FID和CLIP score可能无法完全反映生成内容与提示的精细对齐度，尤其对于风格擦除，用户感知可能不同。

（完）
