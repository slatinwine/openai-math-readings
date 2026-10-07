---
layout: default
title: "Unitarizability implies amenability for discrete groups"
family: "251"
discipline: "Group theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Unitarizability implies amenability for discrete groups

> 结果族 251：Amenability, unitarizability, and strong Ulam stability　·　学科：Group theory　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了离散群可酉化（unitarizable）当且仅当顺从（amenable），肯定解决 1950 年 Dixmier 提出的问题：每个非顺从离散群 `@@M@@G@@` 都有一致界 `@@M@@|\pi|\le 1+\varepsilon@@`、却不能相似于任何酉表示的表示 `@@M@@\pi@@`。

## 问题背景

设 `@@M@@\pi:G\to\mathrm{GL}(H)@@` 是离散群在复 Hilbert 空间上的表示。若 `@@M@@|\pi|=\sup_g\|\pi(g)\|<\infty@@`，称其一致有界（uniformly bounded）；若存在有界可逆算子 `@@M@@S@@` 使每个 `@@M@@S\pi(g)S^{-1}@@` 都是酉算子，称其可酉化，等价于给 `@@M@@H@@` 换一个等价的 `@@M@@\pi@@`-不变内积。Sz.-Nagy 1947 年解决单算子情形；Day 与 Dixmier 1950 年用不变平均（invariant mean）证明顺从群可酉化，Dixmier 随即追问：可酉化是否恰好刻划顺从性？七十多年来的反例都有局限：自由群上的 Pytlik–Szwarc 类只覆盖含非交换自由子群的群；Monod–Ozawa 与 Alpeev 关于花环积（wreath product）`@@M@@A\wr G@@` 的定理只把反例放在 `@@M@@G@@` 的扩张上；Epstein–Monod、Osin、Vergara 的判据则需附加 `@@M@@\ell^2@@`-Betti 数、剩余有限性或 `@@M@@M_d@@`-逼近性质等条件。真正的困难是对任意非顺从群本身造出失效证据，且不许对可能的酉化子做任何先验限制。

## 主要结果

**主定理**：离散群 `@@M@@G@@` 可酉化当且仅当 `@@M@@G@@` 顺从。证明是量化的：对每个非顺从离散群 `@@M@@G@@` 与 `@@M@@\varepsilon>0@@`，存在复 Hilbert 空间 `@@M@@\mathcal K@@` 和表示 `@@M@@\pi:G\to\mathrm{GL}(\mathcal K)@@` 满足 `@@M@@|\pi|\le 1+\varepsilon@@`，且不相似于任何酉表示；`@@M@@G@@` 可数时 `@@M@@\mathcal K@@` 还可取可分。顺从方向由经典的 Day–Dixmier 平均化论证给出，新意全在非顺从方向。文中另有推论：由此得到的 `@@M@@\ell^1(G)@@` 表示没有到全群 `@@M@@C^*@@`-代数 `@@M@@C^*(G)@@` 或约化群 `@@M@@C^*@@`-代数 `@@M@@C_r^*(G)@@` 的有界代数同态延拓。

## 证明思路

先化归为上圈（cocycle）语言：给定酉表示 `@@M@@U@@` 与有界算子上圈 `@@M@@D(gh)=D(g)+U(g)D(h)U(g)^{-1}@@`，三角表示 `@@M@@\pi(g)=\begin{pmatrix}U(g)&D(g)U(g)\\0&U(g)\end{pmatrix}@@` 自动一致有界；若它可酉化，其不变补空间必为某个有界算子 `@@M@@B@@` 的图像，迫使 `@@M@@D@@` 成为内上圈 `@@M@@D(g)=B-U(g)BU(g)^{-1}@@`。于是只需构造有界却非内的上圈。

核心是一个核能量障碍。在 `@@M@@\mathcal H_k=\ell^2(G;\mathbb C^k)@@` 上取平移不变的卷积型算子 `@@M@@A@@`（块 `@@M@@A[x,y]=W(x^{-1}y)@@`），记 `@@M@@E=\sum_s\|W(s)\|_{\mathrm{HS}}^2@@`（HS 为 Hilbert–Schmidt 范数）。引理证明：若 `@@M@@T@@` 在单位元处的块行与 `@@M@@A-T@@` 的块列一致被 `@@M@@K@@` 控制，则 `@@M@@T@@` 到左平移交换子（commutant）的距离至少 `@@M@@\frac12\sqrt{E/k}-K@@`。直和命题再把一列 `@@M@@(A_j,T_j)@@` 焊成一个表示：只要各块行、块列与共轭差 `@@M@@T_j-U_jT_jU_j^{-1}@@` 一致有界且 `@@M@@E_j/k_j\to\infty@@`，所得表示一致有界且不可酉化。妙处在于每个 `@@M@@D_j@@` 单独都由 `@@M@@T_j@@` 实现（是内的），障碍只出现在无穷直和上，因此完全不必对 `@@M@@\|T_j\|@@` 一致有界。

原料来自非顺从性。先用 Kesten 型收缩平均：非顺从给出有限集 `@@M@@S@@` 使 `@@M@@\|\frac1d\sum_{t\in S}R_t\|\le\rho<1@@`。取 `@@M@@\ell@@` 步乘积表 `@@M@@s_1,\dots,s_n@@`（`@@M@@n=d^\ell@@`，带重数）与 `@@M@@r=\lceil n\rho^\ell\rceil@@`，把标号边 `@@M@@(x,i)@@`（自行 `@@M@@x@@` 连到列 `@@M@@xs_i@@`）排成二部多重图，用 Hall 婚配定理把每条边指派给一个端点，使每点负载至多 `@@M@@r@@`，且 `@@M@@(r/n)\log n\to0@@`。再取 `@@M@@k\approx 2r\log(2n)@@` 维空间中的随机符号单位向量 `@@M@@v_1,\dots,v_n@@`，使任意至多 `@@M@@2r@@` 个的合成算子范数不超过 `@@M@@b_0=10@@`（集中不等式加网覆盖加联合界）。以秩一投影 `@@M@@P_i=v_iv_i^*@@` 加权卷积边，`@@M@@T@@` 保留行端边；经由以标号边为基的中间空间作因子分解 `@@M@@T_c=SM_cF@@`，块行、块列与全部共轭差一致被 `@@M@@b_0^2=100@@` 控制。保留边标号是关键：不同标号即使群元素乘积相同，也占据不同坐标，正性保证碰撞只增能量。最后得核能量 `@@M@@E=\sum_s\|\sum_{i:s_i=s}P_i\|_{\mathrm{HS}}^2\ge n@@`，而 `@@M@@k/n\to0@@`，故 `@@M@@E/k\to\infty@@`；整体缩放 `@@M@@t=\varepsilon/100@@` 即得 `@@M@@|\pi|\le1+\varepsilon@@`。不可数群经 Følner 准则化归到有限生成非顺从子群，再用保持一致界的诱导表示传回。

## 可信度与备注

本篇主结果已有 Lean 形式化证明，是本结果族中验证状态最可靠的一环。姊妹篇《Strong Ulam Stability Characterizes Amenability》与其技术同源——稀疏指派、随机符号向量与能量型障碍——并补上 Kazhdan 定理的逆，两文合起来给出"顺从 `@@M@@\iff@@` 可酉化 `@@M@@\iff@@` 强 Ulam 稳定"的完整等价链。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇不在其列，姊妹篇则尚待社区核验。

{% endraw %}
