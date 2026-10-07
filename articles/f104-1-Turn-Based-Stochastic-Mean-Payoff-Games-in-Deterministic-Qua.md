---
layout: default
title: "Turn-Based Stochastic Mean-Payoff Games in Deterministic Quasipolynomial Time"
family: "104"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Turn-Based Stochastic Mean-Payoff Games in Deterministic Quasipolynomial Time

> 结果族 104：Quasipolynomial algorithms for mean-payoff, stochastic and parity games　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了：带机会顶点的回合制随机平均收益博弈中，期望下极限平均收益非负（含恰为零）的顶点集合，可被确定性算法在完整二进制输入长度 \(L\) 下用 \(2^{O((\log(L+2))^2)}\) 次位操作精确求出，概率分母与奖励的数值大小不再进入复杂度。

## 问题背景

平均收益博弈（mean-payoff game）让 Max 与 Min 在有限图上争夺无穷行走的长程平均奖励。Shapley（1953）开创含终止概率的随机博弈（stochastic games），Gillette（1957）转向无折扣的长期平均目标，Liggett 与 Lippman（1969）给出完美信息时间平均博弈的平稳策略定理。计算方面，Condon（1992）把简单随机博弈（simple stochastic game）的阈值问题放入 \(\mathrm{NP}\cap\mathrm{coNP}\)，Zwick 与 Paterson（1996）给出伪多项式（pseudopolynomial）算法，Andersson 与 Miltersen（2009）证明了多个随机博弈问题之间的多项式时间等价。但这些界的代价都依赖概率与奖励的数值大小：它们以二进制编码时长度虽短，数值却可以指数大——例如朴素求解折扣方程需要随 \(1/\lambda\) 增长的迭代步数。让复杂度真正只依赖输入长度 \(L\)，本文是首次在一般回合制随机平均收益博弈上做到。

## 主要结果

主定理（Theorem 1.1）：存在一致确定性图灵机与绝对常数 \(C\)，对顶点划分为 \(V_{\max}\sqcup V_{\min}\sqcup V_{\mathrm{ch}}\)、边带带符号整数奖励、机会顶点转移概率为二进制有理数的输入，精确输出 \(U=\{i\in V:\val(i)\ge0\}\)，其中 \(\val(i)=\sup_\sigma\inf_\tau\E_{i,\sigma,\tau}[\MP_w]\)，\(\MP_w=\liminf_{T\to\infty}\frac1T\sum_{t<T}w(e_t)\) 是路径下极限平均收益（liminf mean payoff），期望取在路径下极限之后。总代价至多 \(2^{C(\log_2(L+2))^2}\) 位操作，含读入、精确有理算术与输出；值恰为零的顶点计入 \(U\)。自环、平行边、零概率与未约分的分数均允许。文中并给出推论：把目标顶点改为 \(+1\) 自环、其余边赋 \(-1\)，路径平均收益的期望恰为二倍可达概率减一，于是"简单随机博弈可达性值是否 \(\ge1/2\)"也获得确定性拟多项式算法。

## 证明思路

先做定量折扣归约（quantitative discount reduction）。对 \(0<u<1\)，折扣映射 \(f_u\) 在每个顶点取 \(uw(e)+(1-u)t_j\) 的最大、最小或机会平均，是压缩映射，有唯一不动点 \(v(u)\)。固定位置策略对（positional pair）时其解是 \(u\) 的有理函数；沿用 Andersson–Miltersen 的符号法并以 Cramer 法则显式估计整多项式的系数范数，得到位长为多项式的整数 \(H\)：非零值与零的间隔至少 \(1/H\)，且取 \(\lambda_0=1/(32H^2)\) 时 \(\|v(\lambda_0)-\val\|_\infty\le1/(16H)\)。符号稳定化还给出对所有 \(u\le1/(2H)\) 同时最优的位置对，其增益—偏置（gain–bias）展开 \(v_i(u)=G_i+u\psi_i+O(u^2)\) 中的 \(G_i\) 是分母有界的有理数；再用"有限取值的亚鞅（submartingale）几乎必然最终常值"与"有界鞅差的平均几乎必然趋零"两条初等引理，把一步增益/偏置不等式转化为对任意行为策略（behavioral strategy）对手的路径保证，证得 \(G_i=\val(i)\)。

其次把不动点求解改造成抽象的同时标记（simultaneous labelling）。对满足单调性与 \(F(t+c\one)=F(t)+\gamma c\one\)（\(0<\gamma<1\)）的映射，整数盒中支撑质量（mass）至多为一的下解/上解作为证人（witness），要求靠近相应边界的坐标取得既定符号。算法继承确定性姊妹篇的两趟枢轴递归，关键新意在于证人的平移方向固定——下解下移、上解上移——而 \(0<\gamma<1\) 使 \(\gamma t\ge t\)，折扣平移恒等式恰好保住所需不等式，大盒证人因此能装进更小的递归盒。枢轴每趟停住时，最后一次原地不动的子调用是确定性证书：仍有主张的证人必有超过 \(3/4\) 的质量聚在峰值附近；半宽调用随即为这些坐标定性，再按"得势方变轻、失势方变重"重配质量，未决证人的质量仍小于 1，可在原盒继续递归，而每个乘积 \(a_ib_i\) 放大 \(32/25\) 倍，故沿任一递归路径此类预算消耗至多 \(O(\log n)\) 次。

最后回到具体博弈：取缩放映射 \(F(t)=Sf_{\lambda_0}(t/S)\)，证明存在间距至多 \(2(N+1)\) 的整数比较向量从两侧夹住不动点（仅用于证明，算法不计算它们）；用标记输出的排除性结论把盒边界逐轮内移 \(\le D/128\)，至多 \(128(d_0+1)\) 轮后逼近误差 \(\le1/(8H)\)；配合 \(1/H\) 的值隙，按 \(A_i\ge-8K\) 输出即得精确判定，零值顶点恰好收入。递归树中每条路径至多 \(d_0+B_0\) 条边，而分支位置至多 \(B_0=O(\log n)\) 个、每处至多 \(2048n+3\) 个选择，节点总数 \(\le\sum\binom{\ell}{j}s_*^j=2^{O((\log(L+2))^2)}\)。

## 可信度与备注

本篇暂无形式化证明，请以社区核验为准。它是族内"同时标记"技术的折扣版延伸：确定性平均收益篇（2026 年 9 月 25 日）第 4–5 节的两趟枢轴—质量重配递归是其直接前身，本文把平移恒等式从 \(F(z+t)=F(z)+t\) 推广到带 \(\gamma<1\) 的折扣版本，使机会顶点与玩家顶点在同一套秩序与平移性质下处理；奇偶篇则反向调用确定性篇作子程序，三篇互为支撑。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
