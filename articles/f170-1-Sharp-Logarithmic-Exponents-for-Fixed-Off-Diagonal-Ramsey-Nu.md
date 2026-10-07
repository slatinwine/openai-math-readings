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

## 一句话结论

本文对每个固定整数 \(s\ge6\) 证明 \(r(s,t)=t^{s-1}/(\log t)^{s-2+o(1)}\)；连同姊妹篇的 \(s=5\) 情形，非对角拉姆齐数（off-diagonal Ramsey number）的对数指数（logarithmic exponent）对所有固定 \(s\ge5\) 完全确定，与经典上界只差 \(o(1)\) 的幂。

## 问题背景

Ramsey（1930）在研究形式逻辑问题时证明的有限划分定理保证拉姆齐数 \(r(s,t)\) 有限：\(n\) 足够大时，任何图必含 \(s\) 团（clique）或 \(t\) 个顶点的独立集（independent set）。在固定 \(s\)、\(t\to\infty\) 的非对角问题里，上界早已定型：Erdős–Szekeres（1935）的二项式界之后，Ajtai–Komlós–Szemerédi（1980）得到 \(O_s(t^{s-1}/(\log t)^{s-2})\)，Li–Rousseau–Zang（2001）把主导常数做到 \(1+o(1)\)——对数幂 \(s-2\) 始终来自上界一侧。下界则全面落后：Kim（1995）仅解决 \(s=3\)；Spencer（1977）的局部引理与 Bohman–Keevash（2010）的随机无 \(K_s\) 过程都只给出 \(t^{(s+1)/2}\) 量级；Mubayi–Verstraëte 的伪随机构造判据只是条件性结果；Mattheus–Verstraëte（2024）用有限几何处理了 \(s=4\)；Bradač（2026）证明 \(r(s,t)\ge c_s t^{s-1}/(\log t)^{2s-4}\)，多项式指数就此确定，但对数幂与上界仍差 \(s-2\) 一截。本文对一切 \(s\ge6\) 把这最后一截补齐。

## 主要结果

主定理：对每个固定整数 \(s\ge6\) 存在常数 \(C_s>0\)，使得对任意 \(\varepsilon>0\) 与一切充分大的 \(t\)，

\[\frac{t^{s-1}}{(\log t)^{s-2+\varepsilon}}\ \le\ r(s,t)\ \le\ C_s\,\frac{t^{s-1}}{(\log t)^{s-2}},\]

即 \(\lim_{t\to\infty}\frac{(s-1)\log t-\log r(s,t)}{\log\log t}=s-2\)。技术核心是素数指标的构造定理：对任意 \(d\ge5\)、\(0<\eta<1/10\) 与充分大的素数 \(q\)，存在 \(\lfloor q^d\log q\rfloor\) 个顶点、无 \(K_{d+1}\) 且独立数小于 \(\lfloor q(\log q)^{1+\eta}\rfloor\) 的图。上界一侧作者给出对 \(s\) 归纳的初等证明（三角无关图上 Shearer/Alon 型独立数下界加随机抽样删点）。与姊妹篇一样，定理不触及常数因子。

## 证明思路

先看骨架，它与 \(s=5\) 姊妹篇共享。在 \(\PG(d,q)\) 上取独立均匀的随机旗流：旗（flag）是入射对 \((a,b)\)，点 \(a\) 落在超平面 \(b\) 上；\(N=\lfloor q^d\log q\rfloor\) 个位置为顶点，\(i<j\) 时若 \(a_i\perp b_j\) 且 \(a_j\not\perp b_i\) 则连边。线性无关性排除 \(K_{d+1}\)，独立集对应一致序列（consistent tuple）。反设每个流都含长 \(k=\lfloor q\sigma^{1+\eta}\rfloor\)（\(\sigma=\log q\)）的一致序列：联合界给所选元组熵下界 \(H(F)\ge d\sigma\ell+\eta\ell\log\sigma-O(k)\)，因为固定元组必须出现在原流的某组位置上。此后用"标记—压缩—迭代"把描述长度压回 \(d\sigma\ell+O(k)\)，导出矛盾。

再补上通往任意维度的两件新工具。其一是重复投影（repeated projection）归约：把 \(\PG(j,q)\)（\(j\ge4\)）中的稀疏对描述问题投到适当中心 \(z\) 的商空间 \(\PG(j-1,q)\)；中心 \(z\) 借方差恒等式与 Markov 不等式选取，既保住 \(S\) 的绝大多数点又控制投影纤维的碰撞。但把帽子提升回原空间会放大 \(q\) 倍，于是交八次投影的帽，用 Cauchy–Schwarz 与碰撞界把尺寸收回。其二是高秩类的直接描述：用两条独立样本行加"富子空间"多项式界处理，后者源自 Nie–Wang 的有限度闭包不等式。低维 \(j\in\{2,3\}\) 则启用多项式方法：富线（rich line）计数采用随机采样加插值、再配合切平面/Hessian 型构造（Guth–Katz、Elekes–Kaplan–Sharir 一脉），并靠把所有相关曲面次数压在素特征 \(q\) 之下来化解 Ellenberg–Hablicsek 分析的正特征障碍；采样侧用若干独立泊松（Poisson）批次打分，二阶矩保证测试留住隐藏支撑的大多数，高阶矩排除环境杂点——两个角色严格分开。

最后迭代与换算。压缩阶段以平衡二叉树组织代表对，验证先于存活检查，可加位势函数对账消息长度；取 \(T=\lceil8/\eta\rceil\) 轮，参数递推给出 \(D_T\le 2\sigma^{2\beta}\)，最后一轮压缩得 \(H(F_*)\le d\sigma\ell_*+O(k)\)，与熵下界矛盾，故存在无长一致序列的流。数论收尾是初等的：作者用中心二项式系数证明每个固定比例区间 \([c_0x,x]\) 内必有素数，取 \(x=t/(\log t)^{1+\eta}\) 换算得 \(r(s,t)\ge c_{s,\eta}\,t^{s-1}/(\log t)^{s-2+(s-1)\eta}\)，再令 \(\eta=\varepsilon/(2(s-1))\) 完成主定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。作者在引言中说明：\(s=5\) 姊妹篇发展了选择律熵与低维稀疏对框架，本文"自成一体地给出全部所需论证"，而重复投影与高秩描述所需的高维估计是新的、并非从五团定理推断——这也意味着需要独立核验的环节更多。上界一侧为经典结果。两文合并恰好覆盖全部固定 \(s\ge5\)，构成结果族 170 的完整图景。

{% endraw %}
