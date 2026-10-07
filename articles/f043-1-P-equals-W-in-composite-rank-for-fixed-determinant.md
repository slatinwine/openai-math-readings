---
layout: default
title: "P=W in composite rank for fixed determinant"
family: "043"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | P=W in composite rank for fixed determinant

> 结果族 043：<i>P</i> = <i>W</i> for fixed-determinant SL<sub><i>n</i></sub> moduli spaces　·　学科：Algebraic and complex geometry（代数与复几何）　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文在复合秩（`@@M@@n\ge4@@` 非素数）、次数与秩互素的情形下，证明了固定行列式 `@@M@@\mathrm{SL}_n@@` Higgs 模空间上完整形式（整个有理上同调、含变体部分）的 `@@M@@P=W@@` 猜想；与已知素秩定理合并，固定行列式的 `@@M@@P=W@@` 在一切互素秩都成立。

## 问题背景

非阿贝尔霍奇理论（nonabelian Hodge theory）把两类几何上截然不同的模空间联系起来：一侧是稳定 Higgs 束（Higgs bundle）的 Dolbeault 模空间，另一侧是表示的特征簇（character variety），二者虽然微分同胚，却各自携带完全不同的代数结构。Higgs 侧的 Hitchin 映射诱导反常 Leray 滤过（perverse Leray filtration）`@@M@@P@@`，而特征簇作为拟射影代数簇带有 Deligne 混合霍奇结构的权滤过（weight filtration）`@@M@@W@@`。de Cataldo–Hausel–Migliorini 在 2012 年提出 `@@M@@P=W@@` 猜想——把 `@@M@@P@@` 的指标加倍后两种滤过应当重合——并在秩 2 证明。此前 `@@M@@\mathrm{GL}_n@@` 情形已由 Maulik–Shen 等在任意互素秩解决，固定行列式的素秩情形也已完成；复合秩的固定行列式情形卡在一个具体障碍上：张量 `@@M@@\Gamma=\mathrm{Pic}^0(C)[n]@@` 的作用把上同调分成不变部分与变体部分（variant cohomology），而已有的重言类生成定理只覆盖不变部分，变体部分无从下手。

## 主要结果

设 `@@M@@C@@` 为亏格 `@@M@@g\ge2@@` 的光滑射影复曲线，`@@M@@n\ge4@@` 为复合整数，`@@M@@\gcd(n,d)=1@@`，`@@M@@L\in\Pic^d(C)@@`。令 `@@M@@X=M_{\mathrm{Dol}}^L(\mathrm{SL}_n)@@` 为行列式等于 `@@M@@L@@`、迹为零的稳定秩 `@@M@@n@@` Higgs 束模空间，`@@M@@X^B@@` 为对应的扭特征簇 `@@M@@\{(A_1,B_1,\dots,A_g,B_g)\in\mathrm{SL}_n(\C)^{2g}:\prod_j[A_j,B_j]=\zeta I_n\}/\!/\mathrm{SL}_n(\C)@@`，其中 `@@M@@\zeta=\exp(2\pi\sqrt{-1}\,d/n)@@`。主定理断言：对所有 `@@M@@m,k\ge0@@`，
`@@M@@DP_kH^m(X^B,\Q)=W_{2k}H^m(X^B,\Q)=W_{2k+1}H^m(X^B,\Q).@@`
等式在整个有理上同调上成立，经复化后包括 `@@M@@\Gamma@@` 的每个非平凡特征子空间，而不仅是不变部分。结合素秩情形（Maulik–Shen 2024），本文推出推论：固定行列式、互素情形的 `@@M@@P=W@@` 猜想对所有秩 `@@M@@n\ge2@@` 成立。文中还给出两个推论：内窥对应的权相容性（endoscopic weight compatibility，正好回答 Maulik–Shen 2021 年的 Question 5.5），以及反常滤过的乘法性（perverse multiplicativity）`@@M@@P_aH^i\smile P_bH^j\subseteq P_{a+b}H^{i+j}@@`。

## 证明思路

整个证明的骨架是：先构造一对共同的 `@@M@@\mathfrak{sl}_2@@` 型算子，再证明这对算子同时控制两个滤过，最后用线性代数断言滤过必须重合。具体地，由普适丛定义次数 2 的类 `@@M@@e=\int_C\bigl(\mathrm{ch}_2-\frac{c_1^2}{2n}\bigr)\in H^2(X)@@`，第 2 节证明 `@@M@@H^2(X)=\Q e@@`，并借助分解定理（decomposition theorem）与相对硬 Lefschetz 得到 `@@M@@e@@` 在 `@@M@@\Gr^P@@` 上以 `@@M@@R=(n^2-1)(g-1)@@` 为中心的 Lefschetz 性质；第 3 节在 Betti 侧证明对偶的"好奇硬 Lefschetz"（curious hard Lefschetz）：`@@M@@H^*(X^B)@@` 的混合霍奇结构是 Hodge–Tate 型（奇权分片消失），且同一个类 `@@M@@e@@` 关于半权分次也有中心 `@@M@@R@@` 的 Lefschetz 性质。关键的线性代数命题（第 2 节 Proposition 2.6）说：若存在次数 `@@M@@-2@@` 的算子 `@@M@@f@@` 同时满足 `@@M@@fP_k\subset P_{k-2}@@`、`@@M@@fW_j\subset W_{j-4}@@` 且 `@@M@@[[f,e],e]=-2e@@`，则 `@@M@@h_0=[e,f]@@` 半单，两个滤过都等于 `@@M@@h_0@@` 特征子空间的直和，故必然相等。于是全部困难集中于构造这样一个 `@@M@@f@@`。

构造分三步。先引入带一个对数极点的 `@@M@@\lambda@@`-联络模空间，它把 Higgs 束（`@@M@@\lambda=0@@`）与联络（`@@M@@\lambda=1@@`）插入同一族；在极点处附加全旗（full flag）条件，并把有序残差形变到虚部互异的值。再对两条残差特征线格做方向相反的初等修正（elementary modification，即 Hecke 型格平移）：这两步平移生成模空间之间的同构族，在联络侧它恰好化为特征值的单值变换（eigenvalue monodromy）。取其某次幂的对数得到幂零导子 `@@M@@N@@`，它把"图表权"（diagram weight，按 Shende 的约定给动点基的上链赋权零）降低 2。令 `@@M@@f'=\pr_*\mathsf A\,N^2\mathsf B\,\pr^*@@`，其中 `@@M@@\mathsf A,\mathsf B@@` 是旗对应的 Gysin 映射（`@@M@@\mathsf A\mathsf B=(-1)^b n!\,\mathrm{id}@@`），旗带来的 `@@M@@\pm 2b@@` 权移位相消，`@@M@@N^2@@` 降权 4，对有限覆盖 `@@M@@S\to C@@` 的积分权移位为零，故 `@@M@@f'W_j\subset W_{j-4}@@`。最后，沿一条 Higgs 直线做专门化（specialization）：近傍闭链（nearby cycles）把平移实现为 Hitchin 基上直像的自同态，一个有限多项式实现 `@@M@@N@@`，与旗对应复合后得到层态射 `@@M@@Rh_*\Q_X\to Rh_*\Q_X[-2]@@`，由反常截断的移位规则立刻给出反常界 `@@M@@f'P_k\subset P_{k-2}@@`；一次格 Riemann–Roch 计算给出 `@@M@@[[f,e],e]=-2e@@`。组装后即得 `@@M@@P_k=W_{2k}@@`，奇权消失给出 `@@M@@W_{2k}=W_{2k+1}@@`；一般行列式 `@@M@@L@@` 通过张量 `@@M@@n@@` 次根线丛化归。全文最难的一环是把 Mellit 的环面分层（toric stratification）沿 `@@M@@n^{2g}@@` 次有限 étale 行列式根覆盖拉回：逐连通分量验证拉回是混合霍德结构同构，再用五引理把好奇硬 Lefschetz 从各分层传到整个模空间，并建立积分局部常值性与普通底变换（ordinary base change）——正因如此结论才覆盖变体上同调，而无需取 `@@M@@\Gamma@@` 不变量。个别步骤（图表权的混合霍奇模细节、交换子计算）技术性较强，此处从略。

## 可信度与备注

本文主结果尚无 Lean 形式化证明，按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。作为结果族 043 的代表篇，它与其姊妹结果互相支撑：任意秩的 `@@M@@\mathrm{GL}_n@@` 定理（Maulik–Shen 2024）、Mellit 的环面分层（2025）以及 Hausel–Mellit–Minets–Schiffmann 的 Hecke 代数方法是其直接输入，素秩固定行列式定理则由 de Cataldo–Maulik–Shen 给出，与本文合并方得"所有互素秩"的完整图景。证明中把滤过比较还原为单一 `@@M@@\mathfrak{sl}_2@@` 三元组的策略清晰可查，但覆盖拉回与图表权两处新几何步骤涉及大量技术引理，其核验依赖原文细节。

{% endraw %}
