---
layout: default
title: "Sharp logarithmic exponents for fixed off-diagonal Ramsey numbers"
family: "170"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Sharp logarithmic exponents for fixed off-diagonal Ramsey numbers

> 结果族 170：Sharp logarithmic exponents for off-diagonal Ramsey numbers　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

还是那场派对：固定小团体人数 `@@M@@s@@`，让陌生人群 `@@M@@t@@` 无限变大，问最少请多少人才能保证出现"`@@M@@s@@` 人全相识"或"`@@M@@t@@` 人全陌生"。姊妹篇解决了 5 人团体的情形，本文把 6 人及以上全部一网打尽，公式整齐得像一段楼梯：分子是 `@@M@@t^{s-1}@@`，分母的对数幂恰是 `@@M@@s-2@@`，楼梯每升一级恰好加一。

**关键词卡片**

- 非对角拉姆齐数（off-diagonal Ramsey number）：`@@M@@r(s,t)@@` 在 `@@M@@s@@` 固定、`@@M@@t\to\infty@@` 时的取值
- 对数指数（logarithmic exponent）：分母 `@@M@@(\log t)@@` 的幂，本文证得恰为 `@@M@@s-2@@`
- 旗（flag）：射影空间里"点落在超平面上"的入射对
- 一致序列（consistent tuple）：构造图中对应"独立集"的特殊结构
- 熵压缩（entropy compression）：用"信息量必须守恒"逼死坏构形的计数技术

**看个具体例子**

对数指数随 `@@M@@s@@` 变化的图像：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="80" y1="230" x2="500" y2="230" stroke="#333" stroke-width="1.5"/>
  <polygon points="500,230 490,226 490,234" fill="#333"/>
  <line x1="80" y1="230" x2="80" y2="50" stroke="#333" stroke-width="1.5"/>
  <polygon points="80,50 76,60 84,60" fill="#333"/>
  <polyline points="160,190 260,160 360,130 460,100" fill="none" stroke="#2471a3" stroke-width="2"/>
  <circle cx="160" cy="190" r="5" fill="#c0392b"/>
  <circle cx="260" cy="160" r="5" fill="#c0392b"/>
  <circle cx="360" cy="130" r="5" fill="#c0392b"/>
  <circle cx="460" cy="100" r="5" fill="#c0392b"/>
  <text x="160" y="252" text-anchor="middle" font-size="14" fill="#333">s=5</text>
  <text x="260" y="252" text-anchor="middle" font-size="14" fill="#333">s=6</text>
  <text x="360" y="252" text-anchor="middle" font-size="14" fill="#333">s=7</text>
  <text x="460" y="252" text-anchor="middle" font-size="14" fill="#333">s=8</text>
  <text x="176" y="185" font-size="13" fill="#c0392b">3</text>
  <text x="276" y="155" font-size="13" fill="#c0392b">4</text>
  <text x="376" y="125" font-size="13" fill="#c0392b">5</text>
  <text x="476" y="95" font-size="13" fill="#c0392b">6</text>
  <text x="90" y="42" font-size="13" fill="#333">对数指数</text>
  <text x="512" y="235" font-size="14" fill="#333">s</text>
  <text x="280" y="272" text-anchor="middle" font-size="14" fill="#555">对数指数 = s−2：对每个固定 s≥6 精确成立</text>
</svg>

</div>

写成公式：`@@M@@r(s,t)=\dfrac{t^{s-1}}{(\log t)^{s-2+o(1)}}@@`（每个固定 `@@M@@s\ge6@@`）。例如 `@@M@@s=6@@` 时 `@@M@@r(6,t)=t^5/(\log t)^{4+o(1)}@@`，`@@M@@s=10@@` 时分母幂为 8——多项式指数 `@@M@@s-1@@` 与对数指数 `@@M@@s-2@@` 同时锁定，与 1980 年的经典上界只差 `@@M@@o(1)@@` 的幂；常数因子同样留作公开问题。

**为什么值得关心**

与姊妹篇合并，所有固定 `@@M@@s\ge5@@` 的非对角拉姆齐数对数指数全部确定，一个悬置四十年的参数就此收官。通往高维的新工具（重复投影、高维稀疏对描述）是独立于五团定理的新估计，并非从低维直接推断。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文对每个固定整数 `@@M@@s\ge6@@` 证明 `@@M@@r(s,t)=t^{s-1}/(\log t)^{s-2+o(1)}@@`；连同姊妹篇的 `@@M@@s=5@@` 情形，非对角拉姆齐数（off-diagonal Ramsey number）的对数指数（logarithmic exponent）对所有固定 `@@M@@s\ge5@@` 完全确定，与经典上界只差 `@@M@@o(1)@@` 的幂。

## 问题背景

Ramsey（1930）在研究形式逻辑问题时证明的有限划分定理保证拉姆齐数 `@@M@@r(s,t)@@` 有限：`@@M@@n@@` 足够大时，任何图必含 `@@M@@s@@` 团（clique）或 `@@M@@t@@` 个顶点的独立集（independent set）。在固定 `@@M@@s@@`、`@@M@@t\to\infty@@` 的非对角问题里，上界早已定型：Erdős–Szekeres（1935）的二项式界之后，Ajtai–Komlós–Szemerédi（1980）得到 `@@M@@O_s(t^{s-1}/(\log t)^{s-2})@@`，Li–Rousseau–Zang（2001）把主导常数做到 `@@M@@1+o(1)@@`——对数幂 `@@M@@s-2@@` 始终来自上界一侧。下界则全面落后：Kim（1995）仅解决 `@@M@@s=3@@`；Spencer（1977）的局部引理与 Bohman–Keevash（2010）的随机无 `@@M@@K_s@@` 过程都只给出 `@@M@@t^{(s+1)/2}@@` 量级；Mubayi–Verstraëte 的伪随机构造判据只是条件性结果；Mattheus–Verstraëte（2024）用有限几何处理了 `@@M@@s=4@@`；Bradač（2026）证明 `@@M@@r(s,t)\ge c_s t^{s-1}/(\log t)^{2s-4}@@`，多项式指数就此确定，但对数幂与上界仍差 `@@M@@s-2@@` 一截。本文对一切 `@@M@@s\ge6@@` 把这最后一截补齐。

## 主要结果

主定理：对每个固定整数 `@@M@@s\ge6@@` 存在常数 `@@M@@C_s>0@@`，使得对任意 `@@M@@\varepsilon>0@@` 与一切充分大的 `@@M@@t@@`，

`@@M@@D\frac{t^{s-1}}{(\log t)^{s-2+\varepsilon}}\ \le\ r(s,t)\ \le\ C_s\,\frac{t^{s-1}}{(\log t)^{s-2}},@@`

即 `@@M@@\lim_{t\to\infty}\frac{(s-1)\log t-\log r(s,t)}{\log\log t}=s-2@@`。技术核心是素数指标的构造定理：对任意 `@@M@@d\ge5@@`、`@@M@@0<\eta<1/10@@` 与充分大的素数 `@@M@@q@@`，存在 `@@M@@\lfloor q^d\log q\rfloor@@` 个顶点、无 `@@M@@K_{d+1}@@` 且独立数小于 `@@M@@\lfloor q(\log q)^{1+\eta}\rfloor@@` 的图。上界一侧作者给出对 `@@M@@s@@` 归纳的初等证明（三角无关图上 Shearer/Alon 型独立数下界加随机抽样删点）。与姊妹篇一样，定理不触及常数因子。

## 证明思路

先看骨架，它与 `@@M@@s=5@@` 姊妹篇共享。在 `@@M@@\PG(d,q)@@` 上取独立均匀的随机旗流：旗（flag）是入射对 `@@M@@(a,b)@@`，点 `@@M@@a@@` 落在超平面 `@@M@@b@@` 上；`@@M@@N=\lfloor q^d\log q\rfloor@@` 个位置为顶点，`@@M@@i<j@@` 时若 `@@M@@a_i\perp b_j@@` 且 `@@M@@a_j\not\perp b_i@@` 则连边。线性无关性排除 `@@M@@K_{d+1}@@`，独立集对应一致序列（consistent tuple）。反设每个流都含长 `@@M@@k=\lfloor q\sigma^{1+\eta}\rfloor@@`（`@@M@@\sigma=\log q@@`）的一致序列：联合界给所选元组熵下界 `@@M@@H(F)\ge d\sigma\ell+\eta\ell\log\sigma-O(k)@@`，因为固定元组必须出现在原流的某组位置上。此后用"标记—压缩—迭代"把描述长度压回 `@@M@@d\sigma\ell+O(k)@@`，导出矛盾。

再补上通往任意维度的两件新工具。其一是重复投影（repeated projection）归约：把 `@@M@@\PG(j,q)@@`（`@@M@@j\ge4@@`）中的稀疏对描述问题投到适当中心 `@@M@@z@@` 的商空间 `@@M@@\PG(j-1,q)@@`；中心 `@@M@@z@@` 借方差恒等式与 Markov 不等式选取，既保住 `@@M@@S@@` 的绝大多数点又控制投影纤维的碰撞。但把帽子提升回原空间会放大 `@@M@@q@@` 倍，于是交八次投影的帽，用 Cauchy–Schwarz 与碰撞界把尺寸收回。其二是高秩类的直接描述：用两条独立样本行加"富子空间"多项式界处理，后者源自 Nie–Wang 的有限度闭包不等式。低维 `@@M@@j\in\{2,3\}@@` 则启用多项式方法：富线（rich line）计数采用随机采样加插值、再配合切平面/Hessian 型构造（Guth–Katz、Elekes–Kaplan–Sharir 一脉），并靠把所有相关曲面次数压在素特征 `@@M@@q@@` 之下来化解 Ellenberg–Hablicsek 分析的正特征障碍；采样侧用若干独立泊松（Poisson）批次打分，二阶矩保证测试留住隐藏支撑的大多数，高阶矩排除环境杂点——两个角色严格分开。

最后迭代与换算。压缩阶段以平衡二叉树组织代表对，验证先于存活检查，可加位势函数对账消息长度；取 `@@M@@T=\lceil8/\eta\rceil@@` 轮，参数递推给出 `@@M@@D_T\le 2\sigma^{2\beta}@@`，最后一轮压缩得 `@@M@@H(F_*)\le d\sigma\ell_*+O(k)@@`，与熵下界矛盾，故存在无长一致序列的流。数论收尾是初等的：作者用中心二项式系数证明每个固定比例区间 `@@M@@[c_0x,x]@@` 内必有素数，取 `@@M@@x=t/(\log t)^{1+\eta}@@` 换算得 `@@M@@r(s,t)\ge c_{s,\eta}\,t^{s-1}/(\log t)^{s-2+(s-1)\eta}@@`，再令 `@@M@@\eta=\varepsilon/(2(s-1))@@` 完成主定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。作者在引言中说明：`@@M@@s=5@@` 姊妹篇发展了选择律熵与低维稀疏对框架，本文"自成一体地给出全部所需论证"，而重复投影与高秩描述所需的高维估计是新的、并非从五团定理推断——这也意味着需要独立核验的环节更多。上界一侧为经典结果。两文合并恰好覆盖全部固定 `@@M@@s\ge5@@`，构成结果族 170 的完整图景。

{% endraw %}
