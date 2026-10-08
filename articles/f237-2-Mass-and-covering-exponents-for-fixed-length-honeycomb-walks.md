---
layout: default
title: "Mass and covering exponents for fixed-length honeycomb walks"
family: "237"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Mass and covering exponents for fixed-length honeycomb walks

> 结果族 237：The three-quarter exponent for honeycomb self-avoiding walk　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把一根 `@@M@@n@@` 节的链条随手扔在格子上，规矩是不许踩自己的脚印：它摊多开？局部多挤？要用几块小圆毯才能盖住？这篇论文对每一个足够大的长度 `@@M@@n@@` 同时回答这三个问题，全部答案只靠两个数：`@@M@@3/4@@` 和 `@@M@@4/3@@`。

**关键词卡片**

- 自避行走（self-avoiding walk）：从格点出发、永不重复访问顶点的路径，二维聚合物的标准模型。
- 均匀测度（uniform measure）：固定长度 `@@M@@n@@` 的所有自避路径一视同仁、等可能抽取。
- 直径（diameter）：路径访问过的顶点中相距最远两点的直线距离。
- 局部质量（local mass）：半径 `@@M@@s@@` 的球内路径访问了多少个顶点，衡量"局部有多挤"。
- 覆盖数（covering number）：盖住整条路径最少需要几个半径 `@@M@@s@@` 的球。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><path d="M 60 200 L 120 200 L 120 150 L 190 150 L 190 220 L 260 220 L 260 120 L 330 120 L 330 190 L 400 190 L 400 90 L 470 90" fill="none" stroke="#1a7a4a" stroke-width="3" stroke-linejoin="round"/><circle cx="190" cy="185" r="58" fill="none" stroke="#336" stroke-width="1.8" stroke-dasharray="6 4"/><text x="115" y="95" font-size="13" fill="#336">半径 s 的球内约有 s^(4/3) 个访问点</text><circle cx="95" cy="200" r="40" fill="none" stroke="#c0392b" stroke-width="1.2" stroke-dasharray="3 3"/><circle cx="185" cy="185" r="40" fill="none" stroke="#c0392b" stroke-width="1.2" stroke-dasharray="3 3"/><circle cx="285" cy="170" r="40" fill="none" stroke="#c0392b" stroke-width="1.2" stroke-dasharray="3 3"/><circle cx="370" cy="150" r="40" fill="none" stroke="#c0392b" stroke-width="1.2" stroke-dasharray="3 3"/><circle cx="445" cy="105" r="40" fill="none" stroke="#c0392b" stroke-width="1.2" stroke-dasharray="3 3"/><text x="130" y="252" font-size="13" fill="#c0392b">盖住全程约需 1+n/s^(4/3) 个球</text><text x="150" y="272" font-size="12" fill="#666">整体直径约 n^(3/4)：比普通随机行走（n^(1/2)）更摊开</text></svg>

</div>

代入 `@@M@@n=10^{12}@@` 步：直径约 `@@M@@n^{3/4}=10^9@@`；任何半径 `@@M@@s=10^6@@` 的球内访问点数约 `@@M@@s^{4/3}=10^8@@`；盖住全程约需 `@@M@@n/s^{4/3}=10^4@@` 个球。定理更强：这些关系对每个整数长度同时成立，失败概率可压到任意多项式小——`@@M@@\mathbb P(n^{3/4-\delta}\le D\le n^{3/4+\delta})\ge1-Cn^{-k}@@`。

**为什么值得关心**

Nienhuis 的 3/4 预言此前只在加权总体层面部分成立；本文首次让它在每个整数长度、上下双向、多尺度同时严格的概率意义下成立，给出了这根"理想聚合物链条"从整体到局部的完整几何画像，也为同族其它定理铺好了地基。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明：蜂窝格点上每个足够大的固定长度 `@@M@@n@@` 的均匀自避行走，以任意高多项式概率同时满足直径为 `@@M@@n^{3/4+o(1)}@@`、局部质量与覆盖数均呈 `@@M@@4/3@@` 指数。Nienhuis 的 `@@M@@3/4@@` 指数预言首次在"每个整数长度、上下双向、多尺度同时"的意义下成立。

## 问题背景

自避行走（self-avoiding walk）是从某格点出发、永不重复访问顶点的最近邻路径，是二维聚合物的标准模型：长度 `@@M@@n@@` 固定，空间延展却是随机的。Nienhuis（1982）由稀薄 `@@M@@O(n)@@` 模型与库仑气分析预言二维空间指数 `@@M@@\nu=3/4@@`，即 `@@M@@n@@` 步行走的典型直径约为 `@@M@@n^{3/4}@@`。Duminil-Copin 与 Smirnov（2012）用仲费米观测量（parafermionic observable）证得蜂窝格点连结常数为 `@@M@@\sqrt{2+\sqrt2}@@`，但桥质量的 `@@M@@-1/4@@` 衰减指数当时仅作为预测记录；Beaton 等（2014）证得带条穿越质量趋于零，Glazman–Manolescu 随后给出更短证明与对数子列界，Krachun–Panagiotis（2026）证得多项式上界与定量次弹道性。然而这些结果都停留在加权总体质量层面；对固定长度的均匀测度、在每个整数长度上、同时给出直径上下界、局部质量与覆盖数的估计，此前并不存在。

## 主要结果

记 `@@M@@\mathcal W_n@@` 为从固定原点出发的 `@@M@@n@@` 步自避行走集合，`@@M@@\Prob_n@@` 为其均匀分布；`@@M@@D(\gamma)@@` 为所访顶点集的直径，`@@M@@M_\gamma(z,s)@@` 为球 `@@M@@\overline B(z,s)@@` 内所访顶点数，`@@M@@\mathcal N_\gamma(s)@@` 为覆盖全部所访顶点所需半径 `@@M@@s@@` 的球的最少个数。主定理：对任意 `@@M@@\delta>0@@` 与 `@@M@@k>0@@`，存在常数 `@@M@@C_{\delta,k}@@` 与 `@@M@@n_0(\delta,k)@@`，使对每个整数 `@@M@@n\ge n_0@@`，在 `@@M@@\Prob_n@@`-概率至少 `@@M@@1-C_{\delta,k}n^{-k}@@` 的事件上同时有
`@@M@@Dn^{3/4-\delta}\le D(\gamma)\le n^{3/4+\delta},@@`
`@@M@@Dn^{-\delta}\min\{n,s^{4/3}\}\le M_\gamma(z,s)\le n^{\delta}\min\{n,s^{4/3}\},@@`
`@@M@@Dn^{-\delta}(1+ns^{-4/3})\le \mathcal N_\gamma(s)\le n^{\delta}(1+ns^{-4/3}),@@`
后两条对所有顶点 `@@M@@z@@` 与所有 `@@M@@s\in[1,n]@@` 同时成立。推论包括：行走沿三个格点法向的每个方向投影的张量（span）至少 `@@M@@n^{3/4-\delta}@@`；覆盖维数比 `@@M@@\log\mathcal N_\gamma(s)/\log(D(\gamma)/s)@@` 依概率收敛于 `@@M@@4/3@@`；回转半径（radius of gyration）`@@M@@R_g=n^{3/4+o(1)}@@`，且对一切 `@@M@@p>0@@` 有 `@@M@@\E_n[D^p]=n^{3p/4+o(1)}@@`。作者明确说明：结论不含连续统收敛、不含换格点的普适性，直径下界也不蕴含两端点分离。

## 证明思路

证明先在临界活度 `@@M@@\rho=(2+\sqrt2)^{-1/2}@@` 下进行，"质量"指未归一化权重和。解析输入由同族姊妹预印本提供：仲费米边界通量恒等式 `@@M@@\sum\rho^{|\gamma|}e^{3iW(\gamma)/8}=1@@`、带条恒等式 `@@M@@cA_h+B_h=1@@`（`@@M@@c=\cos(3\pi/8)@@`）以及 `@@M@@B_h\asymp h^{-1/4}@@`、`@@M@@m_h\asymp h^{3/4}@@`、嵌套质量 `@@M@@r^{1/12+o(1)}@@`、带条一阶长度质量上界 `@@M@@h^{13/12+o(1)}@@`、多边形长度平方质量 `@@M@@H^{2/3+o(1)}@@`、圆柱单弧一致界与多项式族尾界。几何论证要闯三关。第一，用于替换路径段的桥必须装进避开其余片段的走廊，总质量界不给这种保证：作者把较小的桥缝合成新路径并"回收缝线"，控制该操作的倍数，得到局部化的一、二阶长度矩，Cauchy–Schwarz 给出"看见长桥"的次幂概率，独立更新（renewal）试验将其放大，精确条件恒等式再把估计转移到指定高度。第二，单个桥估计要管住任意行走的一切子路径：对相邻更新路径做"有序测试"，同时压制过快行进与局部过长；两个测试碰上同一不可约桥时其权重恰计入一次，这在转弯数随尺度增长时必不可少。第三，同一球内的反复访问需要"多条不交穿越"的专门估计。合起来得到全盒估计：直径不超过 `@@M@@KH@@` 的根行走，其每个子路径 `@@M@@\sigma@@` 同时满足 `@@M@@|\sigma|\le H^\tau(1+\diam\sigma)^{4/3}@@`、`@@M@@\diam\sigma\le H^\tau(1+|\sigma|)^{3/4}@@`、球内点数 `@@M@@\le H^\tau s^{4/3}@@`，且违反任何一条者的总质量 `@@M@@\le C_{\tau,A}H^{-A}@@`——绝对到足以在对所有子路径求和后幸存。最后由次可乘性与带条多项式下界证 `@@M@@Z_n=c_n\rho^n\ge1@@`（否则 `@@M@@B_h@@` 将指数衰减，与 `@@M@@h^{-1/4}@@` 矛盾），于是除以 `@@M@@Z_n@@` 后任意多项式衰减在每个固定长度保留。直径、局部质量与覆盖数再由好事件上的确定性推理导出：取 `@@M@@q@@` 条边的连续时间块，模不等式保证其直径 `@@M@@\le s@@` 而整块落入球内，即得质量下界；覆盖上界用时间块剖分，下界把覆盖球重新中心化到所访顶点并用局部质量上界。

## 可信度与备注

本文主结果暂无 Lean 形式化证明。它是结果族 237 的几何主干：同族姊妹预印本（含本批"标记多边形""圆柱幅"两篇）提供它所引用的精确可观测量——多边形平方质量、嵌套指数、`@@M@@B_H\asymp H^{-1/4}@@`、`@@M@@13/12@@` 一阶长度质量等——本文再把这些输入加工成任意固定长度上的概率定理，各篇结论互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
