---
layout: default
title: "Bounded anticanonical metrics on klt pairs and torus quotients"
family: "068"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Bounded anticanonical metrics on klt pairs and torus quotients

> 结果族 068：Anticanonical nonvanishing in every dimension　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对射影 `@@M@@\mathbb Q@@`-因子 klt 对证明了"有界度量非消没"判据：反典范除子 nef、拉回在消解上有局部有界半正度量、结构层 Euler 特征非零，则正 Cartier 倍数必有截面；再用 GIT 环面商推出光滑有理连通簇上的自然不变非消没，给出丘成桐反典范非消没问题的一条 klt 路线。

## 问题背景

非消没定理要把正性变成指定线丛的截面。对带边界奇点的对（pair）`@@M@@(W,D)@@`，目标线丛是反典范除子 `@@M@@P=-(K_W+D)@@`；nef 只保证它对每条曲线交数非负，并不直接给出与某正倍数线性等价的有效除子。此前最好结果是 LMPTX 2023 在三维对数典范对上的数值有效性（num-effectivity），以及 Müller 2025 附加半放大假设或三维时的非消没；光滑半正与半放大的区别在曲面上已经出现——CFSTZ 2026 分类中就有反典范光滑半正但不可能半放大的有理曲面。本文的切入点是：把"度量局部有界"作为从 nef 走向截面的中间条件，并在环面商上具体构造这一条件，最终绕开半放大假设。

## 主要结果

定理 1.1（有界度量非消没）：`@@M@@(W,D)@@` 为射影 `@@M@@\mathbb Q@@`-因子 klt 对（Kawamata log terminal），边界为有效有理除子，`@@M@@P=-(K_W+D)@@` nef；若在某光滑射影消解 `@@M@@\rho:\widetilde W\to W@@` 上 `@@M@@\rho^*P@@` 有局部有界权重的半正度量，且 `@@M@@\chi(\widetilde W,\mathcal O_{\widetilde W})\ne0@@`，则存在使 `@@M@@mP@@` Cartier 的整数 `@@M@@m>0@@` 使 `@@M@@H^0(W,\mathcal O_W(mP))\ne0@@`。定理 1.2（稳定商的不变截面）：光滑有理连通射影簇 `@@M@@Z@@` 的反典范线丛带光滑半正度量时，对每个作用在 `@@M@@Z@@` 上的代数环面 `@@M@@T@@`，都有 `@@M@@m>0@@` 使自然线性化（natural linearization）下 `@@M@@H^0(Z,-mK_Z)^T\ne0@@`。推论 4.1：光滑连通射影簇上 `@@M@@-K_X@@` 光滑半正则 `@@M@@H^0(X,-mK_X)\ne0@@`。

## 证明思路

klt 判据的证明分五步。先用 Riemann–Roch 与带乘子理想子的 Hard Lefschetz 定理造扭曲微分形式：`@@M@@\chi(\mathcal O_{\widetilde W})\ne0@@` 使 `@@M@@\chi(K_{\widetilde W}+t\rho^*P)@@` 这一多项式在 `@@M@@t=0@@` 非零，从而无穷多次非零，固定某个上同调次数后经 Lefschetz 得到无界指数的截面；再沿用 Lazić–Peternell 与 LMPTX 的行列式方法，从这些截面的函数域张量中取出固定的饱和秩一余切张量子层 `@@M@@\mathcal O_W(M)@@`，配合 LMPTX 的余切子层定理（Ou 的可移动斜率法的对数推广）得 `@@M@@-M@@` 伪有效，于是有有效 Weil 除子 `@@M@@N_i\sim_{\mathbb Q}M+m_iP@@`，`@@M@@m_i\to\infty@@`。然后取被 `@@M@@P@@` 支配的极大纤维化 `@@M@@S\to Y@@`（即 `@@M@@d\pi^*P-f^*A@@` 伪有效、`@@M@@\dim Y@@` 极大），极大性排除新铅笔，使 `@@M@@N_i@@` 的水平部分随 `@@M@@m_i@@` 仿射变化，差商给出 `@@M@@\pi^*P@@` 的无水平极点有理截面；沿基素除子取垂直系数最小值，分解 `@@M@@r\pi^*P=f^*V+H@@`，并保证每个基素除子上方有不含于 `@@M@@H@@` 的分量——这个"缺席分量"是后面边界估计的关键。接着做差异舍入：`@@M@@R=K_S-\pi^*(K_W+D)@@` 的系数大于 `@@M@@-1@@`，令 `@@M@@E=\lceil R\rceil@@`、`@@M@@\Xi=\lceil R\rceil-R@@`，得恒等式 `@@M@@K_S+\pi^*P+\Xi=E@@`，且每个非负扭曲的伴随直像秩为一；用 Păun–Takayama 的奇异伴随直像半正性，规范化的纤维积分 `@@M@@u_a=-\frac1a\log\int_{S_y}t^a\,d\mu_y@@` 收敛到逐纤维本性上确界（essential supremum）`@@M@@u=-\log\operatorname{ess\,sup}|s|^2@@`，缺席分量保证 `@@M@@u@@` 在基除子附近有上界，可去奇点与 Hartogs 延拓把它扩张成 `@@M@@V@@` 上整体局部有界的 psh 度量。最后把支配条件与 Skoda 小指数可积性混合出一个曲率 `@@M@@\ge\epsilon f^*\omega_A@@`、乘子理想子平凡的度量，其极点恰给出理想 `@@M@@\mathcal O_S(-aH)@@`；Fujino 的 Kollár–Nadel 消没定理对每个 `@@M@@a\ge0@@` 消去高阶上同调，Euler 多项式 `@@M@@Q(a)@@` 处处等于截面维数，例外除子 `@@M@@E@@` 的典则截面使 `@@M@@Q(0)>0@@`，多项式非零故某正 `@@M@@a@@` 有截面，乘 `@@M@@s_H^a@@` 后推回 `@@M@@W@@`。不变定理则走 GIT：将度量在紧形式上平均，经 Sumihiro 等变嵌入与 Białynicki-Birula 分解证明 `@@M@@L@@` 的通有权（generic weight）严格正，对 `@@M@@L+\delta J@@` 作小扰动与特征平移使稳定轨迹等于半稳定轨迹，得射影商 `@@M@@W=U/T@@`；Luna 切片给出系数 `@@M@@1-1/e_B@@` 的 klt 边界与等变恒等式 `@@M@@L|_U=q^*P@@`；沿代数弧的凸性论证（psh 权在对数坐标下凸、初始斜率 `@@M@@rw_L\ge0@@`）加上图紧化给出平移提升的一致界，轨道上确界范数经 Kiselman 最小值原理成为 `@@M@@P@@` 上的有界 psh 度量；有理连通性传给商的消解使 `@@M@@\chi=1@@`，定理 1.1 产生截面，上确界范数使它在 `@@M@@U@@` 上有界从而经可去奇点延拓过整个补集，稠密性给出不变性。最终引用姊妹篇的有限覆叠结构定理与 étale 范数，把 `@@M@@Z@@` 因子上的不变截面张上其余因子的不变典则框架，下降后取范数即得 `@@M@@X@@` 上的截面。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。其有限覆叠结构与范数引理直接引用同族第一篇，而主结论与第一篇的有限体积路线、第二篇的不变指标路线构成三条独立互补的论证链。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
