---
layout: default
title: "Independent products in real L1: asymptotic midpoint convexity without AUC renormings"
family: "331"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Independent products in real L1: asymptotic midpoint convexity without AUC renormings

> 结果族 331：Reflexive midpoint convexity and diamond distortion　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论
在可数分支树的每条边上放独立同分布的正随机变量、沿路径连乘并取 `@@M@@L^1@@` 闭线性张成，本文证明：指数律与高斯平方律给出的空间具有正的平均渐近中点模（AMUC），而任何正、非常数、均值为一的乘子律给出的空间都不容许等价的渐近一致凸（AUC）范数——用最"随机"的方式再现 AMUC 与 AUC 的再赋范分离。

## 问题背景
"渐近中点一致凸（AMUC）的空间是否总能再赋范成渐近一致凸（AUC）"是 Dilworth–Kutzarova–Randrianarivony–Revalski–Zhivkov 2016 年提出的问题；他们已知带无条件 Schauder 基时答案肯定。Baudier 2026 年借 Kadets–Werner 的 Daugavet 空间给出否定回答，但那是一条精巧的迭代构造，且依赖"单位球测度预紧"这一定理桥梁。悬而未求的是：能否有一个完全显式、机制透明的空间，让中点增益与再赋范障碍都能直接验证？本文给出的方案极其自然——树上的独立乘积鞅：路径乘积 `@@M@@P_v@@` 的 `@@M@@L^1@@` 范数恒为 1，新鲜变量又天然带来中点增益，两件事在同一个构造里各司其职。

## 主要结果
设 `@@M@@\mathcal T=\mathbb N^{<\omega}@@` 为可数分支树，`@@M@@W@@` 是正、非常数、`@@M@@\E W=1@@` 且 `@@M@@m_2=\E W^2<\infty@@` 的实随机变量。在每个非根顶点放 `@@M@@W@@` 的独立 copies `@@M@@W_v@@`，定义路径乘积 `@@M@@P_\varnothing=1@@`、`@@M@@P_v=P_{v^-}W_v@@`，取 `@@M@@X_W=\overline{\operatorname{span}}\{P_v\}^{\,L^1}@@`（继承实 `@@M@@L^1@@` 范数）。定理证明：对每个这样的乘子律，`@@M@@X_W@@` 无限维且不容许任何等价 AUC 范数——障碍定量为 `@@M@@\overline\delta_N(a\rho/(2b))=0@@`，其中 `@@M@@\rho=\E|W-1|@@`、`@@M@@a,b@@` 是等价常数。对指数律（密度 `@@M@@e^{-w}@@`）与高斯平方律（`@@M@@G^2@@`，`@@M@@G@@` 标准正态），继承范数的平均渐近中点模有显的正下界，例如 `@@M@@\widehat\delta_{X_{\mathrm{exp}}}(t)\ge\frac{7t}{30}c(10/t)@@`（`@@M@@c(K)=\frac1{16}\E(|G|-2K)_+@@`），以及两条高斯平方界的 `@@M@@\widehat\delta_{X_{\mathrm{sq}}}(t)\ge\frac18\PP(|G|\ge4\sqrt2(2+\sqrt2)/t)@@` 等。论文明确声明不断言自反性、单位球测度预紧性或 Daugavet 性质。

## 证明思路
中点估计的难点是对余维有限子空间中一切方向的一致性。第一步用条件期望造投影：对有限、前驱封闭的子树 `@@M@@T@@`，`@@M@@\E(P_v\mid\mathcal G_T)=P_{v_T}@@`，故条件期望限制为 `@@M@@X_W@@` 上的压缩有限秩投影，核 `@@M@@F_T@@` 即所需的余维有限子空间。核心恒等式仍是 `@@M@@\frac{|a+b|+|a-b|}{2}=\max\{|a|,|b|\}@@`，把中点增量化为 `@@M@@\E(t|y|-|x|)_+@@`。第二步"首次出口分解"：把 `@@M@@F_T@@` 中的有限乘积组合按路径首次离开 `@@M@@T@@` 的顶点集 `@@M@@I@@` 分组，提出出口乘子得 `@@M@@y=d+\sum_{i\in I}W_iB_i@@`，其中系数 `@@M@@B_i@@` 只依赖旧坐标与 `@@M@@i@@` 的严格后代子树——不同出口的后代子树互不相交，故条件于旧坐标后诸 `@@M@@B_i@@` 独立且与出口变量 `@@M@@W_i@@` 独立。第三步用独立 copies 对称化加随机符号平均，得两条一阶矩估计 `@@M@@\norm{y}\le(\sqrt{m_2-1}+2)\E\sigma@@` 与 `@@M@@\norm{y}\le2\sqrt{m_2}\,\E\sigma@@`（`@@M@@\sigma=(\sum B_i^2)^{1/2}@@`），把方向的范数反向控制为系数表的期望欧氏尺寸。最后是逐分布的标量机制：指数情形，两个独立指数变量之差是 Laplace 分布，可写成高斯尺度混合 `@@M@@\sqrt{2U}\,G@@`；只重抽指数乘子，`@@M@@y-y'@@` 成为方差 `@@M@@V@@` 的中心化高斯混合，`@@M@@\E V=2@@`、`@@M@@\E V^2\le8@@`，Cauchy–Schwarz 给 `@@M@@\PP(V\ge1)\ge1/8@@`，于是在该事件上高斯超出量直接兑现，得到一致的超越估计 `@@M@@\E((|y|-K\sigma)_+)\ge c(K)\sigma@@`，再配上事件 `@@M@@\{|u|\le tK\sigma\}@@` 的截断与仿射引理收尾。高斯平方情形则用正交变量代换把差化为条件高斯变量，一条路线用联合界把尾概率转移回原变量，另一条直接对差用中点增量的偶凸性。再赋范障碍与姊妹篇的"有界弱零树"同机制：子增量 `@@M@@D_{v,n}=P_v(W_{v^\frown n}-1)@@` 在 `@@M@@L^2@@` 中两两正交，Bessel 不等式使其弱零，且范数恒为 `@@M@@\rho>0@@`；若等价范数 `@@M@@N@@` 是 AUC，则凸性迫使沿适当选出的树枝每步范数至少乘 `@@M@@(1+\gamma/2)@@`，`@@M@@k@@` 层后达 `@@M@@a(1+\delta/4)^k@@`，突破一致上界 `@@M@@b@@`，矛盾。

## 可信度与备注
论文声明主结果已有 Lean 形式化证明。它与结果族 331 的另两篇互为犄角：树位势篇给出显式组合模型与自反反例，Daugavet 篇算出精确模曲线，本文则证明"单一乘子律的独立乘积"这一概率化构造即可同时实现 AMUC 与再赋范障碍，且障碍部分适用于一切满足矩条件的乘子律。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，但文中数值常数（如 `@@M@@7/30@@`、`@@M@@1/8@@`、`@@M@@4\sqrt2(2+\sqrt2)@@`）作者自注并非最优，仍以社区核验为准。

{% endraw %}
