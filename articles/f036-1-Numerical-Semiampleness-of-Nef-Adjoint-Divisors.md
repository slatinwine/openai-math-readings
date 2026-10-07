---
layout: default
title: "Numerical Semiampleness of Nef Adjoint Divisors"
family: "036"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Numerical Semiampleness of Nef Adjoint Divisors

> 结果族 036：Numerical semiampleness and generalized minimal models　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
论文在特征零代数闭域上的射影 klt 对上证明了 Lazić–Peternell 广义丰富性猜想：若 `@@M@@K_X+B@@` 伪有效、`@@M@@M@@` nef 且 `@@M@@K_X+B+M@@` nef，则 `@@M@@K_X+B+M@@` 必数值等价于一个半丰富 `@@M@@\mathbb{Q}@@`-Cartier 除子。这补上了极小模型纲领中"从 nef 到半丰富"的关键一环。

## 问题背景
nef 除子（nef divisor）在每条曲线上度数非负，半丰富（semiample）除子则有由整体截面生成的正倍数、从而给出到射影簇的态射；从数值正性走到全纯截面正是丰富性猜想（abundance conjecture）的核心。Lazić–Peternell 把广义丰富性表述为：加上任意 nef 项后，结论必须放宽为"数值等价于半丰富"。数值放宽即使在维数一也不可省：复椭圆曲线上非挠的零度线丛 nef 且数值平凡，但任何正幂次都没有非零截面，而 `@@M@@K@@` 平凡、`@@M@@B=0@@` 时它正是定理的反例情形。此前已知结果限于曲面、三维部分情形或附加数值/度量假设的 Chaudhuri、Fontanari 等特例，核心障碍是：典范类平凡簇上满 nef 维数的除子未必直接提供截面。

## 主要结果
设 `@@M@@(X,B)@@` 为特征零代数闭域上的射影 klt `@@M@@\mathbb{Q}@@`-对，`@@M@@K_X+B@@` 伪有效（pseudo-effective），`@@M@@M@@` 为 nef 的 `@@M@@\mathbb{Q}@@`-Cartier 除子，且 `@@M@@D=K_X+B+M@@` 为 nef，则存在半丰富 `@@M@@\mathbb{Q}@@`-Cartier 除子 `@@M@@L@@` 使 `@@M@@D\equiv L@@`（`@@M@@\equiv@@` 表示在所有整曲线上度数相同的数值等价）。取 `@@M@@M=0@@` 时结论与普通 klt 丰富性等价，后者是本文的输入而非推论。直接推论：若 `@@M@@K_X+B\equiv 0@@`，则 `@@M@@X@@` 上每个 nef `@@M@@\mathbb{Q}@@`-Cartier 除子都数值半丰富。论文还证明更强的"正部"形式：在某个光滑双有理模型上，`@@M@@w^*(K_X+B+M)@@` 的除子 Zariski 分解正部（positive part `@@M@@P_\sigma@@`，Nakayama 理论）是有理除子且数值半丰富。

## 证明思路
证明是两条命题的同步归纳：`@@M@@(P_n)@@` 说在"满 nef 维数"条件（某个 `@@M@@T+aM@@` 在过非常一般点的每条曲线上度数为正）下 `@@M@@T+cM@@` 对一切 `@@M@@c>0@@` 都是大的（big）；`@@M@@(Z_n)@@` 说正部有理且数值半丰富。先沿 Lazić–Peternell 的双有理约略路线运行一对相容的极小模型程序，同时保住一个半丰富的普通伴随和一个邻近的 nef 广义伴随；Iitaka 维数为正时沿纤维做归纳，剩下的满维数情形归结为 klt Calabi–Yau 对。此处必须新证的引理是：满 nef 维数的 nef 除子必大。终端情形（`@@M@@K_X\sim 0@@`）用反证法：把 `@@M@@L@@` 的丰富逼近 `@@M@@P=r(L+tA)@@` 归一化到体积有界而 `@@M@@r\to\infty@@`，于是过非常一般点的每条曲线的 `@@M@@P@@`-度数有趋于无穷的整下界。一方面得"标量 jet 估计"——非常一般点处截面消没阶 `@@M@@\leq 4k\rho@@`；若违反则产生移动基点成分族，低一维的 `@@M@@(P_f)@@` 给出其上 `@@M@@K+L@@` 为大，再用 Birkar–Zhang 极化双有理性定理造出度数有界的曲线族，与 `@@M@@r\to\infty@@` 矛盾。另一方面在 `@@M@@X\times X@@` 上的射影丛构作双槽 jet 系统，得到远超标量界的消没阶。最后用 Frobenius 比较收网：先把固定复数据扩散到正特征，Mustaț–Schwede 型 Frobenius jet 把普通 jet 放大为与剩余特征 `@@M@@p@@` 成比例的阶，而小极化在对角线上限制秩、点爆破上的固定可动曲线又给出相反的不等式，二者不相容，矛盾。经指标一覆盖与边界摄动推广到一切 klt Calabi–Yau 对后，再用 nef 约化与典范丛公式装配正部命题，并把数值半丰富性降回原簇、推广到任意特征零代数闭域。

## 可信度与备注
主结果暂无形式化证明，宜以社区核验为准。本文与本族 Kähler 篇互为支柱：本文的射影正部定理（其第 8.1 型命题）被 Kähler 篇直接引作输入，而其依赖的普通 log 丰富性与终止性 MMP 又来自配套文献；整条证明链尚未经独立同行评审。另请留意 OpenAI 官方声明"未经形式化的结果可能有问题"。

{% endraw %}
