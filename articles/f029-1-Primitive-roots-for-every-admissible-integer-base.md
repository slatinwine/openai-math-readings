---
layout: default
title: "Primitive roots for every admissible integer base"
family: "029"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Primitive roots for every admissible integer base

> 结果族 029：Primitive roots for every admissible integer base　·　学科：数论（Number theory）　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
论文无条件证明了 Artin 原根猜想的无穷性断言：对每个既非 \(-1\) 也非平方数的整数 \(a\)（包括 \(a=2\)），一切充分大的区间 \((x,2x)\) 内至少有 \(c_a x/(\log x)^2\) 个素数以 \(a\) 为原根，可容许基数全部"洗白"。

## 问题背景
设素数 \(p\nmid a\)，\(a\) 模 \(p\) 的乘法阶 \(\ord_p(a)\) 是使 \(a^k\equiv1\pmod p\) 的最小正整数；若 \(\ord_p(a)=p-1\)，称 \(a\) 为模 \(p\) 的原根（primitive root）。Artin 于 1927 年猜想：每个既非 \(-1\) 也非平方数的"可容许"整数都是无穷多个素数的原根，并给出渐近计数。Hooley 在 1967 年于 Kummer 扩域 \(\Q(\mu_n,a^{1/n})\) 的 Dedekind zeta 函数满足 GRH 的假设下证明了该渐近式。无条件的结果一直很弱：Gupta–Murty 造出 13 个整数保证其中至少一个成立；Heath-Brown 证明至多两个素基数失效（即 \(2,3,5\) 至少一个成立）；而 Klurman–Shparlinski–Teräväinen 的平均结果虽然对几乎处处的 \(a\) 给出期望渐近，但例外集随 \(x\) 变动，处理不了指定基数。固定基数要迈过两道坎：一是分裂域随可能的指数因子变化，经典零点自由区域宽度依赖域、导子与高度，无法一致使用；二是必须构造出大量"指数因子落入可控范围"的素数。

## 主要结果
论文给出两个定理。主定理：对每个可容许整数 \(a\)，存在常数 \(c_a>0\) 与 \(x_a\ge2\)，使对每 个实数 \(x\ge x_a\)，\(\#\{p\text{ 素}：x<p<2x,\ p\nmid a,\ \ord_p(a)=p-1\}\ge c_a\,x/(\log x)^2\)。猜想预测的量级是 \(x/\log x\)，这里低一个对数因子，但足以确立无穷性，且在每个二进区间一致成立。解析定理：设 \(F\) 是含 \(\mu_{12}\) 的分圆域（cyclotomic field），则对 \(F\) 上任何有限阶 Hecke 特征（finite-order Hecke character）\(\eta\)，\(L_F(s,\eta)\) 的亚纯延拓在 \(\re s>1-10^{-6}\) 内无零点（主特征在 \(s=1\) 的极点除外）；关键在于区域宽度 \(10^{-6}\) 对所有域与特征一致，没有导子或高度截断。由此导出一致分裂估计：固定 \(|a|>1\)，对所有素数 \(q\le\exp((\log x)^{0.3})\)，在 Kummer 域 \(K_q=\Q(\mu_q,a^{1/q})\) 中完全分裂的素数个数 \(\ll_a x/(q(q-1)\log x)+x^{1-10^{-6}}\)，常数与 \(q\) 无关。此外还有素数构造命题：在固定同余类里能找到 \(\gg x/(\log x)^2\) 个形如 \(p-1=crQ\)（\(c\in\{2,4\}\)，\(Q>x^{0.9}\) 素数，\(r\) 的素因子全落在 \((\exp(L^{0.1}),\exp(L^{0.3}))\)，\(L=\log x\)）的素数。

## 证明思路
整体是"先造素数、再拆指数、最后清点损失"的组装。先看指数约化：\(a\) 不是模 \(p\) 的原根，当且仅当某素数 \(q\) 整除指数 \(i_p(a)=(p-1)/\ord_p(a)\)。取 \(M=8\prod_{\ell\mid a}\ell\)，用二次互反律（含 \(d_0\in\{-1,\pm2,\pm3,\pm6\}\) 的补充定律表）选一个同余类 \(u\bmod M\)，使该类中素数满足 \((a/p)=-1\)；由 Euler 判据 \(a^{(p-1)/2}\equiv-1\pmod p\)，指数必为奇数，先排除 \(q=2\)。构造命题再供给 \(\gg_a x/L^2\) 个 \(p\equiv u\pmod M\)、\(p-1=crQ\) 的素数，于是剩余的指数素因子只能落在 \(rQ\) 里，分两段排除：若 \(q=Q\)，则 \(p\) 整除某个 \(a^j-1\)（\(j\le2x^{0.1}\)），这些整数的乘积之对数仅 \(\ll_a x^{0.2}\)，损失 \(O_a(x^{0.2}/L)=o(x/L^2)\) 个；若 \(q\mid r\)，分裂判据说 \(p\equiv1\pmod q\) 且 \(a^{(p-1)/q}\equiv1\pmod p\) 等价于 \(p\) 在 \(K_q\) 中完全分裂，逐个套用一致分裂估计再求和，\(\sum_{m>\exp(L^{0.1})}1/(m(m-1))\) 的尾部与 \(x\exp(-\delta_0L+L^{0.3})\) 均为 \(o(x/L^2)\)。两项损失扣除后仍剩 \(\gg_a x/L^2\) 个指数为 \(1\) 的素数。一致分裂估计的来历是：\(K_q\) 未必分圆，故取 \(F_q=\Q(\mu_{12q})\)、复合 \(\widetilde K_q=K_qF_q\)，用 Abel 扩张的 Artin 分解把 \(\zeta_{\widetilde K_q}\) 拆成 \(F_q\) 上 Hecke \(L\)-函数之积，每个因子都被一致零自由定理覆盖，零点自由性随之"下降"到 \(\zeta_{K_q}\)；再用一条误差仅线性依赖 \(\log D+n\) 的光滑显式公式，把宽度 \(\delta_0\) 的无零点区域转成与 \(q\) 无关的素理想计数上界。解析核心即 Hecke 零点自由定理：在 \(F\) 上取 Kazhdan–Patterson 三次 theta 系数做六次 Kummer 挠，用反射与 Poisson 求和两种方式估计同一个加性平均。反射一侧，挠中赋值为一的素与无平方系数素相互作用时六次指数为 \(1\) 与 \(-4\)，模 \(6\) 之和为 \(3\)，交互退化为二次型，由数域形式的 Heath-Brown 二次大筛法控制；Poisson 一侧，相对范数公式把三次 Gauss 相位的立方等同于 Hecke 特征值，主频首项恰是目标 \(L\)-函数倒数的局部因子，其余局部项组成全纯不消失的修正因子；导体大筛法与零点检测压住非主频。两估计相减所得的幂节省使主逆 Mellin 积分越过 \(\re s=1\) 延拓，从而排除零点；全程用理想范数让数值指数与 \(F\) 的次数无关——这正是"一致宽度"的来源。素数构造则靠 Bombieri–Vinogradov 分布、Brun–Hooley 分块筛与 Buchstab 最小素因子恒等式保住正筛余量，同余条件经 Dirichlet 特征展开后融入双线性估计。

## 可信度与备注
本族主结果暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。论文多处倚重同批姊妹稿：标记双线性估计取自《The Poisson–Dirichlet law for the prime factors of \(p-1\)》，反射与 Poisson 探针机制承接《The Quasi-Riemann Hypothesis》。姊妹篇《Simultaneous primitive roots》把本文的四个解析与筛法输入列为显式假设并推出联立原根下界，族内结果环环相扣，但也意味着整体可信度需随这批手稿一并通过审查。

{% endraw %}
