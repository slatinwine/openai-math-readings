---
layout: default
title: "Bounded scalar curvature and smooth extension of four-dimensional Ricci flow"
family: "351"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Bounded scalar curvature and smooth extension of four-dimensional Ricci flow

> 结果族 351：Scalar curvature and finite-time Ricci-flow singularities　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了四维闭流形上的正面定理：Ricci flow 只要在某有限时刻前标量曲率（scalar curvature）一致有界，就能在同一流形上光滑越过该时刻继续流动。四维的标量曲率延拓问题由此完全解决。

## 问题背景

自 Hamilton 1982 年引入 Ricci flow 以来，人们知道闭流形上的流在全曲率有界时总可延续；Šešum 进一步证明 `@@M@@\Ric@@` 一致有界也已足够。但标量曲率 `@@M@@R=\tr_g\Ric@@` 是弱得多的量：在假想的曲率集中点，逐次空间重标度的极限可以是 Ricci-flat（Ricci 平坦）而非平坦的，`@@M@@R@@` 在缩放下消失而 `@@M@@\Rm@@` 不消失。Bamler–Zhang 建立了标量界下的热核与曲率估计，并证出 `@@M@@H_2(M)=0@@` 时的延拓；Bamler 的收敛理论给出余维至少四的集合之外的光滑收敛；Simon 构造了极限空间上的 orbifold 延拓。但这些结论都允许曲率集中与 orbifold 点，而延拓问题问的是：给定的流能否在其原来的流形上光滑继续？Kähler 情形与 Type-I 情形的标量爆破此前已知，无速率限制的一般四维情形正是本文解决的空白。

## 主要结果

**延拓定理**：设 `@@M@@M@@` 是闭连通光滑四维实流形，`@@M@@g(t)@@`，`@@M@@0\le t<T<\infty@@`，是其上带光滑初始度量的光滑 Ricci flow。若 `@@M@@\sup_{M\times[0,T)}|R(g(t))|<\infty@@`，则存在 `@@M@@\varepsilon>0@@` 及 `@@M@@M@@` 上 `@@M@@0\le t<T+\varepsilon@@` 的光滑 Ricci flow `@@M@@\widetilde g(t)@@`，使得对每个 `@@M@@t<T@@` 有 `@@M@@\widetilde g(t)=g(t)@@`。

**推论**：具有有限极大时刻 `@@M@@T@@` 的四维闭流必有 `@@M@@\limsup_{t\uparrow T}\max_M R=+\infty@@`（由 `@@M@@(\partial_t-\Delta)R=2|\Ric|^2@@` 的最大值原理下界配合逐分支延拓得出）。

## 证明思路

反证：假设存在曲率集中点。先做退化几何：把 Einstein 度量的退化理论（Anderson 紧性、Bando 的 bubbling 分析、Cheeger–Tian 曲率能量估计）移植到仅标量有界的流切片上并保留 `@@M@@\Ric@@` 强迫项，得到真正的 orbifold 极限与有限根树（rooted tree）——每个非平坦顶点内部还可能含有更小的后代顶点。最外层非平坦顶点带有连续的最外尺度 `@@M@@a(t)@@`；选取缓冲时间区间，使 `@@M@@a@@` 在区间两端按固定倍数变化，抛物规范化后区间时长固定而 `@@M@@a\to0@@`。

其次处理外部区域：在半径 `@@M@@b=Na@@` 处保留真实度量的物质衣领（material collar），外接渐近局部欧氏（ALE）端。`@@M@@\Ric@@` 的散度约束消去近平坦环上的临界径向调和模，使环上衰减足够好、衣领之外的损耗相对根部能量变小；外部坐标则作为固定衣领上度量的解析函数构造（利用度量应变与线性化曲率的经典相容性及模刚体运动的 Korn 控制），更长的外部坐标只进入误差估计，因而可在各时间片上求导，避免了选取随时间光滑变化的泡泡树。

然后是核心的不等式对撞。记 `@@M@@K^2@@` 为根时空 Ricci 能量除以 `@@M@@a^4@@`。在保留的真实核上，重正化 Einstein–Hilbert 泛函 `@@M@@E@@` 的第一变分被积函数为 `@@M@@\langle\frac12Rg-\Ric,\partial_tg\rangle=2|\Ric|^2-R^2@@`，对时间积分给出正变分至少 `@@M@@2a^4K^2@@` 减去可控损耗；而静态输入——姊妹篇的树不等式 `@@M@@E=o(M)@@`，其中 `@@M@@M@@` 为尺度中立加权 Ricci 误差，由时间极大函数从时空能量转化而来——给出相反的上界 `@@M@@o(1)\cdot(K+1)^2@@`。两者相除得 `@@M@@cK^2\le o(1)(K+1)^2@@`，故 `@@M@@K\to0@@`，连 `@@M@@K@@` 的有界性都无需预先假设。

最后把能量消失翻译成几何：得到公共 Ricci 包络 `@@M@@|\Ric|\le Q_*(t)(1+(a/l)^2)@@`，`@@M@@\|Q_*\|_{L^2}\to0@@`；由长度变分公式与好物质点集（用 Fubini 定理剔除坏点），区间两端之间的距离在 `@@M@@o(a)@@` 精度内保持，从而两端极限之间存在保持一切两两距离的点态等距，它必然保持定义最外尺度的曲率半径最大值——这与 `@@M@@a@@` 的固定倍数变化矛盾。于是集中点不存在，`@@M@@T@@` 之前 `@@M@@|\Rm|@@` 一致有界，`@@M@@g(t)@@` 光滑收敛到极限度量 `@@M@@g_T@@`，再由 Ricci–DeTurck 短时存在性在同一 `@@M@@M@@` 上重启流动。

## 可信度与备注

主定理暂无形式化证明。本文与族内另两篇构成一体：静态树不等式是其不可或缺的输入，而高维反例说明"四维"这一维数假设不可去掉——四维恰好是正面结果成立与反例出现之间的分界。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
