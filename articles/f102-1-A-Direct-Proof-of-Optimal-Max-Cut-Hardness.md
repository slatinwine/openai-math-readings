---
layout: default
title: "A Direct Proof of Optimal Max-Cut Hardness"
family: "102"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Direct Proof of Optimal Max-Cut Hardness

> 结果族 102：The Unique Games Conjecture and optimal approximation thresholds　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论
本文无条件证明：在简单无权图上，把 Max-Cut 近似到优于 Goemans–Williamson 常数 `@@M@@\alpha_{\mathrm{GW}}\approx 0.8786@@` 的任何固定比率都是 NP 难的。1995 年的半定规划算法由此被确认为最优多项式算法，且结论不再需要唯一博弈猜想作前提。

## 问题背景
Max-Cut 要把图顶点分成两部分，使跨越分割的边权最大，是 Karp 1972 年列出的最早一批 NP 完全问题之一。Goemans 与 Williamson 在 1995 年用半定规划（semidefinite programming）加随机超平面舍入得到期望比率 `@@M@@\alpha_{\mathrm{GW}}=0.878567\ldots@@` 的多项式算法，此后"该比率是否无条件最优"成为近似算法领域的中心问题。难度方面，Håstad 的 Fourier 方法配合 gadget 只能排除 `@@M@@16/17\approx 0.941@@` 以上的比率；Khot、Kindler、Mossel、O'Donnell 则证明：若承认唯一博弈猜想，`@@M@@\alpha_{\mathrm{GW}}@@` 就是最优的，其解析核心是"多数最稳定"定理（Majority Is Stablest）。Feige–Schechtman 的积分间隙只说明 SDP 松弛本身的局限，不构成对任意算法的难度。这一缺口悬置了二十余年。

## 主要结果
**定理 1.1**：对每个固定 `@@M@@\alpha\in(\alpha_{\mathrm{GW}},1]@@`，简单无权图上 Max-Cut 的 `@@M@@\alpha@@`-近似是 NP 难的。证明落在更精确的**间隙定理（定理 1.2）**：固定有理数 `@@M@@t\in(0,1)@@` 与 `@@M@@0<\varepsilon<(t-B(t))/4@@`，其中 `@@M@@B(t)=\frac{2}{\pi}\arcsin t@@`，则区分 `@@M@@\Val\ge\frac{1+t}{2}-\varepsilon@@` 与 `@@M@@\Val\le\frac{1+B(t)}{2}+\varepsilon@@` 的图（边权为有理概率分布，`@@M@@\Val@@` 为最大割权重）是 NP 难的。两阈值之比 `@@M@@\frac{1+B(t)}{1+t}@@` 的最小值恰为 `@@M@@\alpha_{\mathrm{GW}}@@`，故任何 `@@M@@\alpha>\alpha_{\mathrm{GW}}@@` 的近似算法都能切开这个间隙，与定理 1.1 等价。

## 证明思路
起点是已发表的 2-to-1 博弈构造（Dinur–Khot–Kindler–Minzer–Safra 一系，含 Khot–Minzer–Safra 扩张定理），本文取其精确的仿射形式：约束投影是二元线性空间之间维数差一的满射仿射映射，且字母表可在完整度误差任意调小之前、先按所需可靠度固定。这一量词顺序使全篇选参自洽；这是唯一的外部难度输入，唯一博弈猜想仅作历史背景。归约是长码（long code）式的：标签 `@@M@@a@@` 由独裁函数 `@@M@@w\mapsto w(a)@@` 表示，图为每个源左端点元组配一个字域，任意割即一族布尔函数。查边时经公共右端点抽两条边，把生成的字经仿射投影拉回并将第二个字取负；源约束全满足时独裁标记以约 `@@M@@\frac{1+t}{2}@@` 的概率被割开，此为完整度。核心创新是字的生成器：一棵有限根树，每个内部节点带 `@@M@@s@@` 对孩子与一张随机表，叶子携带标签空间上的仿射形式；门规则使 Walsh 展开的每个单项式从每对孩子中恰取一项。另做一次成对探索，每层只保留随机一对孩子的双方；两条探索在任何固定深度恰有一个公共节点，在该深度以逐元素相关 `@@M@@t@@` 耦合两边的表，使每个单项式恰染一个因子 `@@M@@t@@`；并对仿射行少量独立重采样以平滑。可靠性：把任意割的奇部沿源边平均，得在所选表项上均衡的函数；割值超过 NO 阈值意味着期望噪声稳定性超过 `@@M@@B(t)@@`，由"多数最稳定"检出一个高影响表项——但它由门的输入索引，并非源标签。随后三步弥合裂缝：其一，利用门对称性局部简化 Fourier 支撑，使仿射平移成为该门表格的平移；其二，向量值仿射散列引理：独立仿射平移下，弥散的 Fourier 质量平均造不出大表项影响，界还与行空间维数无关；其三，隐藏坐标译码：质量集中须固定许多行坐标，而左端点不知投影就无法拉回这些上下文——在乘积博弈的一个随机因子植入零系数，遗忘后分布几乎不变，该因子处无需投影即可拉回，只需跨因子比较所选门的 `@@M@@2s@@` 条自由行，代价 `@@M@@2^{2s}@@` 质量。译码损失与源字母表大小无关，否则字母表维数依赖所求可靠度，选参将循环。最终按"先译码损失与源可靠度，再字母表与因子数，最后源完整度误差"的顺序定参；附录给出向简单无权图的确定性转换。

## 可信度与备注
论文标注主结果已 Lean 形式化。姊妹篇《The Unique Games Theorem》证明唯一博弈猜想后，接入 KKMO 归约同样给出 Max-Cut 的最优阈值；本篇不依赖该猜想、从 2-to-1 博弈直接出发，两条独立路线互相印证。同族 Vertex Cover 篇则确立因子 `@@M@@2@@` 阈值。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，请以社区核验为最终参考。

{% endraw %}
