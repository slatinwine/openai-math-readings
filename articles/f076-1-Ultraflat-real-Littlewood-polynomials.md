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

## 入门导读 🐣

掷 `@@M@@N@@` 次硬币：正面记 `@@M@@+1@@`，反面记 `@@M@@-1@@`，拼成多项式 `@@M@@P(z)=\pm1\pm z\pm\cdots\pm z^{N-1}@@`。让 `@@M@@z@@` 沿单位圆转一圈，`@@M@@|P|@@` 的图像通常像心电图一样大起大落。这篇论文证明：硬币可以"掷得足够聪明"，让整条曲线几乎变成水平线——上下误差不超过百分之几，而且只要长度够大，每个整数长度都做得到。

**关键词卡片**

- Littlewood 多项式（Littlewood polynomial）：系数只有 `@@M@@\pm1@@` 的多项式。
- 单位圆（unit circle）：`@@M@@|z|=1@@` 的圆周，多项式对所有"角度"的响应都在这里看。
- Parseval 下界：圆周上均方模恰为 `@@M@@\sqrt N@@`，故最大模不可能低于 `@@M@@\sqrt N@@`——天然地板。
- 超平坦（ultraflat）：归一化模 `@@M@@|P(z)|/\sqrt N@@` 在整圆上一致趋于 1，上下同时贴住 1。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="80" y="30" font-size="13" fill="#c0392b">随机符号：大起大落</text>
  <text x="300" y="30" font-size="13" fill="#1a7f37">存在选法：被夹进绿带</text>
  <line x1="70" y1="42" x2="70" y2="240" stroke="#333" stroke-width="2"/>
  <line x1="70" y1="240" x2="515" y2="240" stroke="#333" stroke-width="2"/>
  <rect x="70" y="112" width="440" height="16" fill="#d9f2dd"/>
  <line x1="70" y1="112" x2="510" y2="112" stroke="#1a7f37" stroke-width="1.5" stroke-dasharray="6 4"/>
  <line x1="70" y1="128" x2="510" y2="128" stroke="#1a7f37" stroke-width="1.5" stroke-dasharray="6 4"/>
  <polyline points="70,150 88,92 108,182 130,112 152,198 175,80 196,162 220,102 242,190 264,120 285,70 308,170 332,106 354,196 378,84 402,166 428,116 448,186 472,94 496,152 510,132" fill="none" stroke="#c0392b" stroke-width="2"/>
  <text x="18" y="117" font-size="11" fill="#1a7f37">1010</text>
  <text x="18" y="131" font-size="11" fill="#1a7f37">990</text>
  <text x="110" y="262" font-size="12" fill="#1a7f37">绿带 = (1±0.01)√N，即 990~1010</text>
  <text x="466" y="262" font-size="12" fill="#333">角度 θ</text>
</svg>

</div>

数字版定理（示意）：`@@M@@N=10^6@@`、`@@M@@\varepsilon=0.01@@` 时，`@@M@@\sqrt N=1000@@`，存在一组符号使 `@@M@@990\le|P(z)|\le1010@@` 对一切 `@@M@@|z|=1@@` 成立——连 `@@M@@z=\pm1@@` 两个"实端点"也不例外。

**为什么值得关心**

Erdős 1957 年提出、Littlewood 1966 年讨论的老问题得到肯定回答：仅用实符号也能造出超平坦多项式，且长度无需满足任何整除条件。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明了实 Littlewood 多项式（系数全为 `@@M@@\pm1@@`）可以是"超平坦"的：对每个足够大的长度 `@@M@@N@@`，都能选一组符号，使多项式在单位圆上每一点的模都落在 `@@M@@(1\pm\varepsilon)\sqrt N@@` 之间，包括 `@@M@@z=\pm1@@` 这两个实端点，回应了 Erdős 与 Littlewood 的著名问题。

## 问题背景
实 Littlewood 多项式指 `@@M@@P(z)=\sum_{k=0}^{N-1}\varepsilon_k z^k@@`，其中 `@@M@@\varepsilon_k\in\{-1,1\}@@`。由 Parseval 恒等式，它在单位圆上的均方模恰为 `@@M@@\sqrt N@@`，因此 `@@M@@\sqrt N@@` 是自然尺度，最大模至少为 `@@M@@\sqrt N@@`。Erdős 在 1957 年问：实符号多项式能否在整个圆周上被两个固定的正常数倍数夹住？Littlewood 1966 年的著作也讨论了此问题。此前已知：Rudin–Shapiro 构造在二进长度下给出最大模 `@@M@@\le\sqrt{2N}@@`；Balister–Bollobás–Morris–Sahasrabudhe–Tiba（2020）对所有次数给出双边常数因子界；Kahane（1980）对复单位模系数造出了超平坦多项式，但限制到实符号时困难陡增——本论文的姊妹篇此前只做到下界 `@@M@@\frac{1}{16}\sqrt N@@`，卡在"下界不够接近 `@@M@@\sqrt N@@`"这一步。

## 主要结果
**定理（主定理）**：对每个 `@@M@@\varepsilon\in(0,1)@@`，存在 `@@M@@N_0@@`，使得对每个整数 `@@M@@N\ge N_0@@`，都有符号 `@@M@@\varepsilon_0,\ldots,\varepsilon_{N-1}\in\{-1,1\}@@`，使
`@@M@@D(1-\varepsilon)\sqrt N\le\Bigl|\sum_{k=0}^{N-1}\varepsilon_k z^k\Bigr|\le(1+\varepsilon)\sqrt N\qquad(|z|=1).@@`
符号可随 `@@M@@N@@` 不同而重新选取，结论对同一个多项式在整圆上的两个极值同时成立。若一族多项式的归一化模 `@@M@@|P(z)|/\sqrt N@@` 在圆周上一致趋于 1，就称它超平坦（ultraflat）——本定理说明实 Littlewood 多项式经过每个足够大的整数长度都能超平坦，把姊妹篇的 `@@M@@\frac{1}{16}@@` 下界提升到渐近最优。

## 证明思路
整个证明是"先造连续函数、再取整到符号"两阶段。先在高维环面 `@@M@@\mathbb T^m@@` 上造一个实三角多项式 `@@M@@F(y)=\sum_{a}c_a\mathrm e(a\cdot y)@@`，满足 `@@M@@\|F\|_\infty\le1+\delta@@`，且每个频率的系数与权重 `@@M@@w_a=|a\cdot v|@@` 之间有双边比较 `@@M@@1\le|c_a|/\sqrt{w_a}\le1+C\delta@@`，总权重 `@@M@@\sum w_a@@` 接近 1。为此，先用递推 `@@M@@p_j=p_{j-1}+\frac12(1-p_{j-1}^2)\cos(2\pi y_j)@@` 造出 `@@M@@|p|\le1@@` 而平方平均趋近 1 的多项式；再把每个频率用二次相位"摊开"到一个频率盒上，摊开因子的系数借缺陷敏感的取整引理取成同一模长，盒子大小按 `@@M@@|b_s|^2/\rho_s@@` 配比，使每个新系数的平方恰与权重成正比。然后利用带符号区间装填引理（源自 Pippenger–Spencer 超图染色）在圆周上分出互不相交的短弧，在每段弧上定义波 `@@M@@B_N(t)=\frac{c_a}{\sqrt{w_a}}\mathrm e(\operatorname{sgn}(\lambda_a)/8+N\psi_{a,h}(t))@@`，其模为常数。关键在相位设计：要求 `@@M@@|dt/dx|=w_a\chi_h(x)^2@@`，则驻相（stationary phase）分析表明，第 `@@M@@k@@` 个 Fourier 系数的首项恰是 `@@M@@F@@` 在某点的值乘以 `@@M@@[0,1]@@` 中的因子，于是 `@@M@@\|F\|_\infty@@` 直接控制所有系数而无需累加 `@@M@@|c_a|@@`。端点处不降低振幅而是增大相位曲率（用递减函数 `@@M@@\chi_h@@` 压制端点贡献），间隙处用分段二次相位把相邻波连续衔接并同时匹配相位的导数——匹配导数使分部积分的边界项相消，得到外部 Fourier 系数 `@@M@@O((N+|k|)^{-2})@@` 的可和尾部。最后取 `@@M@@Y_k=\sqrt N\widehat{B_N}(k)/S_\delta\in[-1,1]@@`，Parseval 迫使其平均平方接近 1，即"缺陷"`@@M@@\mu/N@@` 很小；再用基于 Spencer 与 Lovett–Meka 部分染色方法的实矩阵偏差（discrepancy）引理把 `@@M@@Y_k@@` 舍入到符号 `@@M@@\varepsilon_k@@`，圆周上的一致误差仅 `@@M@@C\sqrt{q_\delta\log(80/q_\delta)}@@`，随 `@@M@@\delta\to0@@` 消失。所有维数、装填数据、区间与相位均在 `@@M@@N@@` 趋于无穷之前固定，因此结论对所有足够大的整数长度成立，不施加任何整除性条件。

## 可信度与备注
本文暂无形式化证明。它与同族姊妹篇互为支撑：取整与区间装填两条共享引理直接继承自"下包络"姊妹篇，而"渐近极小最大值"姊妹篇的 Lean 形式化覆盖了本族的核心路线；本篇是把下界从 `@@M@@\frac{1}{16}\sqrt N@@` 推进到 `@@M@@(1-\varepsilon)\sqrt N@@` 的最新一步。按 OpenAI 官方声明，未经形式化的结果可能有问题，阅读时请以社区核验为准。

{% endraw %}
