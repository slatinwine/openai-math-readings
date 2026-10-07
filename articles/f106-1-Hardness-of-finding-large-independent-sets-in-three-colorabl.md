---
layout: default
title: "Hardness of finding large independent sets in three-colorable graphs"
family: "106"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Hardness of finding large independent sets in three-colorable graphs

> 结果族 106：Hardness of coloring three-colorable graphs　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文证明：对任意固定 `@@M@@0<\delta<1/3@@`，区分三着色图与"所有独立集都少于 `@@M@@\delta n@@` 个顶点"的图是 NP 难的；从而对每个固定 `@@M@@c\ge3@@`，给三着色图找 `@@M@@c@@`-着色是 NP 难的——困扰理论计算机科学界三十余年的常数色板近似着色猜想就此无条件解决。

## 问题背景

近似图着色（approximate graph coloring）问：输入被承诺为三着色（three-colorable）时，能否用固定常数 `@@M@@c@@` 种颜色给出正常着色（proper coloring）？其决策版本即区分三着色图与非 `@@M@@c@@`-着色图。Khanna–Linial–Safra（2000）证明 `@@M@@c=4@@` 时已困难；Barto–Bulín–Krokhin–Opršal 的代数 PCP 理论推到 `@@M@@2k-1@@` 色（`@@M@@k=3@@` 时即 5 色）；对一般固定 `@@M@@c@@` 的猜想长期悬而未决。条件性突破不少：Dinur–Mossel–Regev 的鱼形 Label Cover 猜想、Braverman–Khot–Lifshitz–Minzer 的 Rich 2-to-1 猜想均可推出本论文的结论形态；Guruswami–Sandeep（2020）从 `@@M@@d@@`-to-1 Games 出发的归约，配上 Fei–Minzer–Wang（2026）证明的 4-to-1 完美完备性猜想，已得任意固定 `@@M@@c@@` 的着色困难，但其完备侧只承诺八着色、且不保留独立集信息。本文无需任何未证猜想，只用普通投影 Label Cover，即取得"三着色完备＋独立集密度任意小"的最强形态。

## 主要结果

主定理（Theorem 1.1）：对每个固定实数 `@@M@@0<\delta<1/3@@`，存在确定性多项式时间归约 `@@M@@R_\delta@@`，把每个 3-CNF 公式 `@@M@@\phi@@` 映为有限简单无向图 `@@M@@G_\phi@@`，满足：`@@M@@\phi@@` 可满足时 `@@M@@G_\phi@@` 三着色；`@@M@@\phi@@` 不可满足时 `@@M@@\alpha(G_\phi)<\delta\,|V(G_\phi)|@@`，即最大独立集（independent set）占顶点数不足 `@@M@@\delta@@` 倍。小的独立性比（independence ratio）迫使色数（chromatic number）很大，故此结论强于任何固定色数下界。直接推论（Corollary 1.2）：对每对固定整数 `@@M@@3\le k\le c@@`，区分 `@@M@@k@@`-着色图与非 `@@M@@c@@`-着色图是 NP 难的——因为 `@@M@@c@@`-着色图必含大小至少 `@@M@@n/c@@` 的独立集，恰被可靠性排除。

## 证明思路

起点是投影式 Label Cover（PCP 定理加并行重复）：3SAT 可多项式归约为其实例，可满足时价值（value）为 1，不可满足时至多 `@@M@@\sigma@@`。作者先构造一个"层链"结构：第 `@@M@@i@@` 层放置问答元组 `@@M@@(v_1,\dots,v_{i-1},u_i,\dots,u_{r-1})@@`，即沿链把左问题逐个换成右问题，相邻层由测试投影 `@@M@@\pi_c@@` 在对应位置约束。在每个元组处安放环面 `@@M@@\mathbb T^{M_i}@@` 的细网格，格内两点按上确界圆距离连边，而投影拉回点对 `@@M@@x@@` 与 `@@M@@x\circ\pi@@` 以零长度连接，最短路定义伪度量 `@@M@@\mathrm{dist}@@`；若某点满足 `@@M@@\mathrm{dist}(x,Tx)\le1/8@@`（`@@M@@T@@` 为全坐标加 `@@M@@1/2@@` 的半移位），则直接输出团 `@@M@@K_q@@`。顶点来自一个被精确展开为整数重数的随机实验：采样一条链、一个 `@@M@@s@@` 层集合 `@@M@@B\sim\mu@@`、每层的系数 `@@M@@t_j\in\{0,1/m,\dots,1\}@@`（概率按 `@@M@@\lambda^k@@` 几何递减）与旋转相位，位置取 `@@M@@\sum_{j\in B}t_j\hat\theta_j@@` 在 `@@M@@b=\min B@@` 层的像。两顶点 `@@M@@x,y@@` 相邻当且仅当 `@@M@@\mathrm{dist}(x,Ty)\le1/8@@`。

完备性：一个满足的标号让"在满足乘积答案处取值"的求值映射非扩张且跨零链一致，于是相邻顶点的相位圆距离超过 `@@M@@1/3@@`，把圆周三等分即得覆盖全顶点的正常三着色。可靠性：独立集诱导奇函数（odd function）`@@M@@f@@`——在集合处取 1、满足 `@@M@@f(Tx)=-f(x)@@`、64-Lipschitz——经 McShane 延拓到整个环面。先引用 Austin 的维度无关 junta 逼近定理（Friedgut junta 定理的连续版），把每个小子链上的函数用总量至多 `@@M@@d@@` 个答案坐标逼近，`@@M@@d@@` 与字母表大小无关；再证分离子链的终端列表若相交，即可解码出 Label Cover 的成功策略，故概率受 `@@M@@\sigma@@` 压制。接着是全文的组合核心——分布对齐引理（distributional alignment）：先用极小极大与 Ramsey 均质化把任意列表族化为序不变的随机模式，从而存在层分布 `@@M@@\mu@@`，使得以高概率每个出现的标号都能被指派到它全部出现的一个公共层。最后做系数测试：对每层引入辅助均匀相位，奇性给出均值零，方差大则必有大影响坐标；对齐使零系数层的影响被 junta 吸收（系数恰为 1 才能在模 1 下平移旋转），几何递减律使正系数层的大影响罕见，合并得均方至多 `@@M@@6\varepsilon@@`，即独立集密度任意小。

## 可信度与备注

本手稿主结果已由 OpenAI 完成 Lean 形式化证明（结果族 106 附有 Lean 文档），这是目前最强的机器可查正确性背书；分布对齐等全新组合引理的证明也在正文完整给出，未读的参数选定一节按依赖顺序固定常数。本篇与 Fei–Minzer–Wang 的 4-to-1 Games 工作及同门姊妹篇（证明普通 2-to-1 完美完备性前提）互相印证，共同闭合常数色板猜想。按 OpenAI 官方声明，未经形式化的结果可能存在问题，核验时宜以 Lean 证明与社区评议为准。

{% endraw %}
