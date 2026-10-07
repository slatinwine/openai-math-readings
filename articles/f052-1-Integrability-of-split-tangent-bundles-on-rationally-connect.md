---
layout: default
title: "Integrability of split tangent bundles on rationally connected manifolds"
family: "052"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Integrability of split tangent bundles on rationally connected manifolds

> 结果族 052：Tangent splittings and product decompositions　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明 Höring 猜想：光滑有理连通（rationally connected）射影复流形上，切丛的任何指定双和项全纯分裂都自动可积；结合 Höring 乘积定理，立得与指定分裂兼容的乘积分解。

## 问题背景

对指定分解 `@@M@@T_X=E_1\oplus E_2@@`，可积性（integrability，子丛的全纯截面关于李括号封闭）是它来自乘积结构的必要局部条件。Höring 在 2007 年证明：有理连通射影流形上只要一个和项可积，就存在与指定分裂兼容的乘积分解；他随后猜想至少一个和项总可积，并证明了所有和项秩不超过 2 的低秩情形。Campana–Peternell 处理过低秩 Fano 情形，2026 年的 Fano 型定理则要求 klt `@@M@@\mathbb Q@@`-因子的奇点环境。光滑性不可省：文献中已有带奇点的有理连通反例；而且即使流形本身是乘积，指定的和项也可能不可积——Höring 在阿贝尔曲面与 `@@M@@\mathbb P^1@@` 的乘积上给出过这样的例子。有理连通性恰好排除这些例子，并提供证明所用的丰富有理曲线。

## 主要结果

主定理（自动可积，automatic integrability）：设 `@@M@@X@@` 是维数至少为 2 的光滑连通射影复流形，且两个一般点（two general points，即某非空 Zariski 开集中的所有点对）落在某态射 `@@M@@\mathbb P^1\to X@@` 的像上，则每个指定全纯分解 `@@M@@T_X=E_1\oplus E_2@@`（正秩和项）的两个和项都可积，没有任何附加的秩或正性假设。这证明了 Höring 就此情形提出的猜想。推论（兼容乘积）：此时存在光滑射影流形 `@@M@@X_1,X_2@@` 与同构 `@@M@@X\simeq X_1\times X_2@@`，使 `@@M@@E_i=\pr_i^*T_{X_i}@@`。论文还把定理用于 uniruled 紧凯勒流形的有理连通商（rationally connected quotient）的一般纤维：纤维上继承的分裂 `@@M@@T_Z=W_1\oplus W_2@@` 自动可积，从而补上 Höring 结构定理所需的前提，并在 `@@M@@\operatorname{rank}V_1=2@@` 时给出三分款分类。

## 证明思路

核心构造是"切匣"（tangent box），而且它不需要任何可积性假设：对任意全纯映射 `@@M@@g:\mathbb P^1\to X@@`，构造 `@@M@@F:\mathbb P^1\times\mathbb P^1\to X@@`，在对角线上等于 `@@M@@g@@`，第一个因子方向切于 `@@M@@E_1@@`、第二个方向切于 `@@M@@E_2@@`，允许有临界点。构造分三步。先解形式 Cauchy 问题：在对角线的形式邻域（formal neighborhood）中取坐标 `@@M@@u=s,\ v=t-s@@`，方程 `@@M@@\partial_v\widehat F=P_2(\widehat F)\partial_u\widehat F@@` 把 `@@M@@g@@` 的导数逐步拆入两个和项，右端第 `@@M@@k@@` 次系数只依赖前 `@@M@@k@@` 个系数，递归给出唯一的形式解，坐标变换下的相容性保证它整体定义。再做有理重构：对角线的法丛是 `@@M@@\mathcal O(-2)@@`，据此给形式截面空间装上过滤并计数，得维数上界 `@@M@@\dim V\le m^2+O(m+1)@@`；而双多项式截面映射 `@@M@@(A,B)\mapsto AS_0+BS_\nu@@` 的来源空间维数为 `@@M@@2(m+1)^2@@`，`@@M@@m@@` 充分大时必有非零核关系 `@@M@@(A_\nu,B_\nu)@@`，故齐次坐标比 `@@M@@q_\nu=-A_\nu/B_\nu@@` 是有理函数；消去公共零点阶后，它们在对角线某点附近同时全纯，且形式展开与形式解一致。最后消去不确定点：在点爆破的消解上，两条切性写成楔形恒等式 `@@M@@(P_1\mathrm dF')\wedge\mathrm d(s\circ\mu)=0@@` 等，沿例外曲线消去公共幂次并在切向量上取值，逼出 `@@M@@P_1\mathrm dF'=P_2\mathrm dF'=0@@`，于是每条例外曲线被收缩为点，映射在整个 `@@M@@\mathbb P^1\times\mathbb P^1@@` 上全纯。

下一步是传输。分裂给出"投影括号偏联络"`@@M@@\nabla^i_\xi e=P_i[\xi,e]@@`（沿互补方向对 `@@M@@E_i@@` 求导），它在匣上拉回为相对全纯联络；限制到 `@@M@@\mathbb P^1@@` 纤维上，曲率是曲线上的全纯 2-形式，自动为零，`@@M@@\mathbb P^1@@` 又单连通，传输便与路径无关，给出同构 `@@M@@\Theta_i:\pr_i^*(g^*E_i)\simeq F^*E_i@@`，在对角线处为恒等。于是在直线 `@@M@@L_i\simeq\mathbb P^1@@` 上，相应的和项保持 `@@M@@g^*E_i@@`，而互补和项变成平凡丛——这正是后续测试所需的平凡靶。

有理连通性只在最后一步进场：两点族给出在标记点 `@@M@@a@@` 处为零、在 `@@M@@b@@` 处张成 `@@M@@E_i@@` 的截面。把括号张量（bracket tensor）`@@M@@\mathcal B_i:\bigwedge^2E_i\to E_j@@` 作用到两个这样的截面，经传输得到平凡丛在 `@@M@@\mathbb P^1@@` 上的整体截面——它是常值函数，在 `@@M@@a@@` 处为零则在 `@@M@@b@@` 处也为零；截面的张成性逼出 `@@M@@\mathcal B_i@@` 在 `@@M@@b@@` 处为零。两点族使 `@@M@@\mathcal B_i@@` 在一个非空开集上为零，恒等定理把它推广到整个 `@@M@@X@@`，而 `@@M@@\mathcal B_i=0@@` 正是可积性。

## 可信度与备注

本篇暂无形式化证明，请以社区核验为准。姊妹篇（同族 052 的万有覆盖分裂定理）主结果已 Lean 形式化，它假设两个和项可积、结论是万有覆盖的兼容乘积；本篇恰在有理连通射影情形免费提供该可积性，两篇合成从"切丛分裂"到"乘积分解"的完整链条。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
