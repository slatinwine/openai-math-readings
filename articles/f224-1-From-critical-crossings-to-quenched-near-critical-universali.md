---
layout: default
title: "From critical crossings to quenched near-critical universality in Voronoi percolation"
family: "224"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | From critical crossings to quenched near-critical universality in Voronoi percolation

> 结果族 224：Critical and quenched near-critical universality for Poisson–Voronoi percolation　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一锅水恰好烧开是"临界点"；把火拧小一点点，沸腾的样子多久才变？这篇论文研究的是"随机炉子"版本：把平面按随机撒下的种子切成不规则拼图、逐格染黑白，然后问——染黑概率偏离临界值 `@@M@@1/2@@` 多少时，"从左连到右"的宏观现象开始响应？答案惊人：与最经典的三角格点模型完全同步。

**关键词卡片**

- 沃罗诺伊渗流（Poisson–Voronoi percolation）：平面上撒随机种子点，每处归最近种子，切出不规则胞，每胞独立染黑白。
- 近临界（near-critical）：染黑概率从临界值偏离一点点时，宏观连通如何变化的学问。
- 淬火（quenched）：先把随机拼图固定死，只对染色随机性取平均。
- pivotal 位点（pivotal site）：翻转这一个格子的颜色，就会翻转"左右是否连通"这一事实的格子。
- 单调耦合（monotone coupling）：每格预先藏一个均匀随机数 `@@M@@U@@`，密度 `@@M@@p@@` 时染黑当且仅当 `@@M@@U\le p@@`，让不同 `@@M@@p@@` 能在同一画面上比较。

**看个具体例子**

每个模型用自己的尺子：把密度写成 `@@M@@p=\frac12+\lambda r@@`，其中 `@@M@@r=1/\mathbb E[N]@@`（`@@M@@\mathbb E[N]@@` 是该模型单位方块跨越的期望 pivotal 数）；四边形 `@@M@@Q@@` 的跨越阈值 `@@M@@\tau(Q)@@` 就是让 `@@M@@Q@@` 首次被穿越的 `@@M@@\lambda@@`。定理说：固定拼图、只对颜色平均，所有 `@@M@@\tau(Q)@@` 的联合定律在几何随机性下依概率收敛到与三角格点完全相同的极限 `@@M@@\nu_\triangle@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="40" y="40" width="360" height="200" fill="none" stroke="#333" stroke-width="2"/><polygon points="40,40 190,60 170,150 40,165" fill="#555" stroke="#222"/><polygon points="190,60 400,45 400,120 170,150" fill="#555" stroke="#222"/><polygon points="40,165 170,150 400,120 400,240 40,240" fill="#fff" stroke="#222"/><path d="M190,60 L400,45 L400,120 L170,150 Z" fill="none" stroke="#c0392b" stroke-width="3" stroke-dasharray="6 4"/><text x="12" y="108" font-size="15">左</text><text x="406" y="70" font-size="15">右</text><text x="228" y="92" font-size="13" fill="#fff">pivotal 胞</text><text x="420" y="150" font-size="13">黑格连成</text><text x="420" y="170" font-size="13">左右通道</text><text x="420" y="200" font-size="13">只翻红胞：</text><text x="420" y="220" font-size="13">通道断开</text></svg>

</div>

图中灰色两胞连成一条从左到右的通道；虚线标出的 pivotal 胞是"一票定乾坤"者：只翻转它，通道就会断开（或接通）。近临界理论正是以这类格子的数量为尺子来度量偏离。

**为什么值得关心**

这是首次对"几何本身完全随机"的模型证明近临界极限与经典格点一致——普适性跨越了随机几何。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在承认姊妹篇证明的 Cardy 公式后，本文证明泊松–沃罗诺伊渗流的淬火近临界普适性：固定随机镶嵌、只平均颜色，各四边形的跨越阈值经模型自身期望 pivotal 数归一化后，在几何概率下依概率收敛到与三角格点完全相同的极限定律。

## 问题背景

临界渗流刻画密度恰在临界值时的宏观连通几何，近临界（near-critical）渗流则问：密度偏离临界点多远，宏观跨越才开始响应？在三角格点上，Kesten 的标度关系、Nolin 的系统近临界估计以及 Garban–Pete–Schramm 的连续 pivotal 测度与近临界标度极限理论，给出了这一问题的参考框架。对几何本身随机的泊松–沃罗诺伊（Poisson–Voronoi）渗流，Benjamini–Kalai–Schramm 提出了跨越集中性问题，Ahlberg 等人随后证明了淬火（quenched，即固定几何后仅平均颜色）集中性与噪声敏感性。悬而未决的是：典型固定几何在只平均颜色后，是否产生与三角格点相同的近临界极限过程？此前卡在 Voronoi 模型连联合临界信息（探索路径极限、pivotal 响应的收敛）都未建立，可用的只有一条标量的 Cardy 公式。

## 主要结果

设 `@@M@@\eta_\varepsilon@@` 为强度 `@@M@@\varepsilon^{-2}@@` 的全平面泊松过程，其沃罗诺伊胞独立染色；每位点带独立均匀标记 `@@M@@U_v@@`，密度 `@@M@@p@@` 时为黑当且仅当 `@@M@@U_v\le p@@`（单调耦合，monotone coupling）。翻转某位点颜色会改变单位方块左右跨越的位点称为颜色 pivotal（color-pivotal），其计数记 `@@M@@N_\varepsilon^V@@`，三角格点模型类似记 `@@M@@N_\delta^\triangle@@`。两个模型各以自身尺度 `@@M@@r_e^M=1/\mathbb{E}N_e^M@@` 定义近临界密度 `@@M@@p_e^M(\lambda)=\frac12+\lambda r_e^M@@` 与四边形（quad）`@@M@@Q@@` 的跨越阈值 `@@M@@\tau_e^M(Q)=\inf\{\lambda: C_Q \text{ 在密度 } p_e^M(\lambda)\text{ 发生}\}@@`。主定理（Quenched near-critical universality）：在标量临界 Cardy 公式（Hypothesis，即姊妹篇定理 1.1）假设下，各期望 pivotal 数有限且严格为正、两个归一化尺度趋于零；三角格点的阈值向量定律收敛到某测度 `@@M@@\nu_\triangle@@`；而条件于泊松镶嵌，Voronoi 阈值向量（取值于有理多边形四边形族上的乘积型紧空间 `@@M@@\mathcal K@@`）的条件定律在几何概率下依概率收敛到同一个 `@@M@@\nu_\triangle@@`。

## 证明思路

证明要完成两次转移。第一次是从标量跨越提取联合临界信息：条件于典型固定几何，只探索颜色位；临界臂估计控制探索与未探索域边界的接触，Cardy 测试逐段决定停下的壳层，迭代得出 SLE`@@M@@_6@@` 探索路径与环路极限（把 Camia–Newman 方法推广到所需几何），再恢复限定在给定多边形内、甚至强制若干分离方块为指定颜色的联合临界测试，由对小扰动的连续性与有限多边形跨越见证识别其共同定律。第二次是把微观颜色变化与固定介观改变相比较。先做"位点展开"：单个位点在多个时刻的颜色历史定律恰为临界定律加上一个居中的小符号测度 `@@M@@q_ew_{\mathbf t}@@`，逐位相乘并用泊松阶乘矩公式展开成无穷级数。系数带符号，须证绝对收敛：作者构造合并森林（merging forest，方法论上源自 GPS 的谱样本分析），用 Kruskal 型算法把相近插入点组织成聚类，在每个"生命区间"的环形探针上要求四臂事件，聚类直径的损失经伸缩求和后仅以位点数 `@@M@@k@@` 为界，最终得到 `@@M@@C^kk^{-(1-g/2)k}@@` 型的超指数系数界。随后是保号的局部比较（sewing）：以四段交替单色弧构成的分离环为中介，把单点插入与固定大小方块的插入互换，同时保留任意符号历史权重；再借助 Russo 恒等式使展开的首系数恰为 `@@M@@1@@`，从而校准出共同的比较常数 `@@M@@c\in(0,\infty)@@`，全程无需预先知道微观 pivotal 振幅的收敛。之后用同一比较把辅助的 `@@M@@2{:}1@@` 矩形归一化换算成单位方块归一化，得到 `@@M@@q_e\mathbb{E}N_e(Q_*)\to B>0@@`。最后，一重复印的收敛给出期望，两份共享同一几何的独立颜色复印给出二阶矩，`@@M@@L^2@@` 收敛配合紧空间上等连续函数族的有限 `@@M@@\zeta@@`-网，完成条件定律在几何上的依概率收敛。

## 可信度与备注

主结果未形式化。本文的关键输入——标量 Cardy 公式——由同族姊妹篇证明，本族另一篇再证明该归一化尺度实为纯幂 `@@M@@\varepsilon^{-3/4}@@`（带正常数振幅），三篇环环相扣。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
