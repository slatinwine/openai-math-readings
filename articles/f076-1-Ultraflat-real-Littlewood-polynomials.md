---
layout: default
title: "Ultraflat real Littlewood polynomials"
family: "076"
discipline: "Real and complex analysis"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Ultraflat real Littlewood polynomials

> 结果族 076：Real ultraflat Littlewood polynomials and unbounded binary merit factors　·　学科：Real and complex analysis　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了实 Littlewood 多项式（系数全为 \(\pm1\)）可以是"超平坦"的：对每个足够大的长度 \(N\)，都能选一组符号，使多项式在单位圆上每一点的模都落在 \((1\pm\varepsilon)\sqrt N\) 之间，包括 \(z=\pm1\) 这两个实端点，回应了 Erdős 与 Littlewood 的著名问题。

## 问题背景
实 Littlewood 多项式指 \(P(z)=\sum_{k=0}^{N-1}\varepsilon_k z^k\)，其中 \(\varepsilon_k\in\{-1,1\}\)。由 Parseval 恒等式，它在单位圆上的均方模恰为 \(\sqrt N\)，因此 \(\sqrt N\) 是自然尺度，最大模至少为 \(\sqrt N\)。Erdős 在 1957 年问：实符号多项式能否在整个圆周上被两个固定的正常数倍数夹住？Littlewood 1966 年的著作也讨论了此问题。此前已知：Rudin–Shapiro 构造在二进长度下给出最大模 \(\le\sqrt{2N}\)；Balister–Bollobás–Morris–Sahasrabudhe–Tiba（2020）对所有次数给出双边常数因子界；Kahane（1980）对复单位模系数造出了超平坦多项式，但限制到实符号时困难陡增——本论文的姊妹篇此前只做到下界 \(\frac{1}{16}\sqrt N\)，卡在"下界不够接近 \(\sqrt N\)"这一步。

## 主要结果
**定理（主定理）**：对每个 \(\varepsilon\in(0,1)\)，存在 \(N_0\)，使得对每个整数 \(N\ge N_0\)，都有符号 \(\varepsilon_0,\ldots,\varepsilon_{N-1}\in\{-1,1\}\)，使
\[(1-\varepsilon)\sqrt N\le\Bigl|\sum_{k=0}^{N-1}\varepsilon_k z^k\Bigr|\le(1+\varepsilon)\sqrt N\qquad(|z|=1).\]
符号可随 \(N\) 不同而重新选取，结论对同一个多项式在整圆上的两个极值同时成立。若一族多项式的归一化模 \(|P(z)|/\sqrt N\) 在圆周上一致趋于 1，就称它超平坦（ultraflat）——本定理说明实 Littlewood 多项式经过每个足够大的整数长度都能超平坦，把姊妹篇的 \(\frac{1}{16}\) 下界提升到渐近最优。

## 证明思路
整个证明是"先造连续函数、再取整到符号"两阶段。先在高维环面 \(\mathbb T^m\) 上造一个实三角多项式 \(F(y)=\sum_{a}c_a\mathrm e(a\cdot y)\)，满足 \(\|F\|_\infty\le1+\delta\)，且每个频率的系数与权重 \(w_a=|a\cdot v|\) 之间有双边比较 \(1\le|c_a|/\sqrt{w_a}\le1+C\delta\)，总权重 \(\sum w_a\) 接近 1。为此，先用递推 \(p_j=p_{j-1}+\frac12(1-p_{j-1}^2)\cos(2\pi y_j)\) 造出 \(|p|\le1\) 而平方平均趋近 1 的多项式；再把每个频率用二次相位"摊开"到一个频率盒上，摊开因子的系数借缺陷敏感的取整引理取成同一模长，盒子大小按 \(|b_s|^2/\rho_s\) 配比，使每个新系数的平方恰与权重成正比。然后利用带符号区间装填引理（源自 Pippenger–Spencer 超图染色）在圆周上分出互不相交的短弧，在每段弧上定义波 \(B_N(t)=\frac{c_a}{\sqrt{w_a}}\mathrm e(\operatorname{sgn}(\lambda_a)/8+N\psi_{a,h}(t))\)，其模为常数。关键在相位设计：要求 \(|dt/dx|=w_a\chi_h(x)^2\)，则驻相（stationary phase）分析表明，第 \(k\) 个 Fourier 系数的首项恰是 \(F\) 在某点的值乘以 \([0,1]\) 中的因子，于是 \(\|F\|_\infty\) 直接控制所有系数而无需累加 \(|c_a|\)。端点处不降低振幅而是增大相位曲率（用递减函数 \(\chi_h\) 压制端点贡献），间隙处用分段二次相位把相邻波连续衔接并同时匹配相位的导数——匹配导数使分部积分的边界项相消，得到外部 Fourier 系数 \(O((N+|k|)^{-2})\) 的可和尾部。最后取 \(Y_k=\sqrt N\widehat{B_N}(k)/S_\delta\in[-1,1]\)，Parseval 迫使其平均平方接近 1，即"缺陷"\(\mu/N\) 很小；再用基于 Spencer 与 Lovett–Meka 部分染色方法的实矩阵偏差（discrepancy）引理把 \(Y_k\) 舍入到符号 \(\varepsilon_k\)，圆周上的一致误差仅 \(C\sqrt{q_\delta\log(80/q_\delta)}\)，随 \(\delta\to0\) 消失。所有维数、装填数据、区间与相位均在 \(N\) 趋于无穷之前固定，因此结论对所有足够大的整数长度成立，不施加任何整除性条件。

## 可信度与备注
本文暂无形式化证明。它与同族姊妹篇互为支撑：取整与区间装填两条共享引理直接继承自"下包络"姊妹篇，而"渐近极小最大值"姊妹篇的 Lean 形式化覆盖了本族的核心路线；本篇是把下界从 \(\frac{1}{16}\sqrt N\) 推进到 \((1-\varepsilon)\sqrt N\) 的最新一步。按 OpenAI 官方声明，未经形式化的结果可能有问题，阅读时请以社区核验为准。

{% endraw %}
