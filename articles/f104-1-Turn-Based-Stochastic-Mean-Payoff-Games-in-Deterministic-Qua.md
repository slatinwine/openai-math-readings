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

## 入门导读 🐣

一盘下不完的棋：你（Max）想让长期平均得分尽量高，对手（Min）想压低它，棋盘上还有几个格子由骰子决定去向。问哪些开局位置你能稳保平均分不亏？这篇论文给出确定性算法，运行时间只看输入的"位数"，与骰子概率、得分数字写得多大都无关。

**关键词卡片**

- 平均收益博弈（mean-payoff game）：在图上无穷对弈、比拼长期平均奖励的双人游戏。
- 机会顶点（chance vertex）：不由任何玩家做主、按给定概率随机跳转的位置。
- 值（value）：双方都下得完美时，某位置的期望长期平均得分。
- 拟多项式时间（quasipolynomial time）：`@@M@@2^{O((\log L)^2)}@@` 级别的运行时间，远好于指数、略逊于多项式。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 300"><text x="280" y="24" text-anchor="middle" font-size="15" fill="#222">回合制随机博弈：Max 与 Min 轮流走，骰子顶点随机跳</text><rect x="100" y="60" width="100" height="56" fill="#fbb" stroke="#933" stroke-width="2"/><text x="150" y="84" text-anchor="middle" font-size="14" fill="#222">Max</text><text x="150" y="102" text-anchor="middle" font-size="11" fill="#222">（想高分）</text><rect x="100" y="185" width="100" height="56" fill="#bcd" stroke="#369" stroke-width="2"/><text x="150" y="209" text-anchor="middle" font-size="14" fill="#222">Min</text><text x="150" y="227" text-anchor="middle" font-size="11" fill="#222">（想压低）</text><circle cx="410" cy="150" r="44" fill="#dfd" stroke="#3a3" stroke-width="2"/><text x="410" y="146" text-anchor="middle" font-size="13" fill="#222">机会顶点</text><text x="410" y="164" text-anchor="middle" font-size="11" fill="#222">（掷骰子）</text><line x1="150" y1="116" x2="150" y2="185" stroke="#556" stroke-width="2"/><polygon points="150,185 144,173 156,173" fill="#556"/><text x="162" y="155" font-size="12" fill="#333">+1</text><line x1="200" y1="210" x2="372" y2="167" stroke="#556" stroke-width="1.5"/><text x="285" y="178" font-size="12" fill="#333">−1 →</text><line x1="372" y1="133" x2="200" y2="95" stroke="#556" stroke-width="1.5"/><text x="285" y="103" font-size="12" fill="#333">→ 3/4</text><line x1="372" y1="180" x2="200" y2="232" stroke="#556" stroke-width="1.5"/><text x="285" y="225" font-size="12" fill="#333">→ 1/4</text><text x="280" y="285" text-anchor="middle" font-size="13" fill="#333">问：双方都最优时，哪些顶点的长期平均分 ≥ 0？算法精确输出这个集合</text></svg>

</div>

主定理：算法精确输出所有值 `@@M@@\ge0@@` 的顶点（含恰好为零者），代价 `@@M@@2^{C(\log_2(L+2))^2}@@` 次位操作，`@@M@@L@@` 是输入总位数。比如 `@@M@@L@@` 为一千位时 `@@M@@\log_2 L\approx10@@`，运算量在 `@@M@@2^{O(100)}@@` 量级——看似巨大，但旧方法会随概率分母、奖励数值增大而指数膨胀，新界彻底与数值脱钩。推论：简单随机博弈"可达概率是否 `@@M@@\ge1/2@@`"同样获得拟多项式算法。

**为什么值得关心**

此类博弈长期搁在 NP∩coNP 中，拟多项式已是已知最好量级；本文首次在含随机转移的一般情形做到复杂度只依赖输入长度。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了：带机会顶点的回合制随机平均收益博弈中，期望下极限平均收益非负（含恰为零）的顶点集合，可被确定性算法在完整二进制输入长度 `@@M@@L@@` 下用 `@@M@@2^{O((\log(L+2))^2)}@@` 次位操作精确求出，概率分母与奖励的数值大小不再进入复杂度。

## 问题背景

平均收益博弈（mean-payoff game）让 Max 与 Min 在有限图上争夺无穷行走的长程平均奖励。Shapley（1953）开创含终止概率的随机博弈（stochastic games），Gillette（1957）转向无折扣的长期平均目标，Liggett 与 Lippman（1969）给出完美信息时间平均博弈的平稳策略定理。计算方面，Condon（1992）把简单随机博弈（simple stochastic game）的阈值问题放入 `@@M@@\mathrm{NP}\cap\mathrm{coNP}@@`，Zwick 与 Paterson（1996）给出伪多项式（pseudopolynomial）算法，Andersson 与 Miltersen（2009）证明了多个随机博弈问题之间的多项式时间等价。但这些界的代价都依赖概率与奖励的数值大小：它们以二进制编码时长度虽短，数值却可以指数大——例如朴素求解折扣方程需要随 `@@M@@1/\lambda@@` 增长的迭代步数。让复杂度真正只依赖输入长度 `@@M@@L@@`，本文是首次在一般回合制随机平均收益博弈上做到。

## 主要结果

主定理（Theorem 1.1）：存在一致确定性图灵机与绝对常数 `@@M@@C@@`，对顶点划分为 `@@M@@V_{\max}\sqcup V_{\min}\sqcup V_{\mathrm{ch}}@@`、边带带符号整数奖励、机会顶点转移概率为二进制有理数的输入，精确输出 `@@M@@U=\{i\in V:\val(i)\ge0\}@@`，其中 `@@M@@\val(i)=\sup_\sigma\inf_\tau\E_{i,\sigma,\tau}[\MP_w]@@`，`@@M@@\MP_w=\liminf_{T\to\infty}\frac1T\sum_{t<T}w(e_t)@@` 是路径下极限平均收益（liminf mean payoff），期望取在路径下极限之后。总代价至多 `@@M@@2^{C(\log_2(L+2))^2}@@` 位操作，含读入、精确有理算术与输出；值恰为零的顶点计入 `@@M@@U@@`。自环、平行边、零概率与未约分的分数均允许。文中并给出推论：把目标顶点改为 `@@M@@+1@@` 自环、其余边赋 `@@M@@-1@@`，路径平均收益的期望恰为二倍可达概率减一，于是"简单随机博弈可达性值是否 `@@M@@\ge1/2@@`"也获得确定性拟多项式算法。

## 证明思路

先做定量折扣归约（quantitative discount reduction）。对 `@@M@@0<u<1@@`，折扣映射 `@@M@@f_u@@` 在每个顶点取 `@@M@@uw(e)+(1-u)t_j@@` 的最大、最小或机会平均，是压缩映射，有唯一不动点 `@@M@@v(u)@@`。固定位置策略对（positional pair）时其解是 `@@M@@u@@` 的有理函数；沿用 Andersson–Miltersen 的符号法并以 Cramer 法则显式估计整多项式的系数范数，得到位长为多项式的整数 `@@M@@H@@`：非零值与零的间隔至少 `@@M@@1/H@@`，且取 `@@M@@\lambda_0=1/(32H^2)@@` 时 `@@M@@\|v(\lambda_0)-\val\|_\infty\le1/(16H)@@`。符号稳定化还给出对所有 `@@M@@u\le1/(2H)@@` 同时最优的位置对，其增益—偏置（gain–bias）展开 `@@M@@v_i(u)=G_i+u\psi_i+O(u^2)@@` 中的 `@@M@@G_i@@` 是分母有界的有理数；再用"有限取值的亚鞅（submartingale）几乎必然最终常值"与"有界鞅差的平均几乎必然趋零"两条初等引理，把一步增益/偏置不等式转化为对任意行为策略（behavioral strategy）对手的路径保证，证得 `@@M@@G_i=\val(i)@@`。

其次把不动点求解改造成抽象的同时标记（simultaneous labelling）。对满足单调性与 `@@M@@F(t+c\one)=F(t)+\gamma c\one@@`（`@@M@@0<\gamma<1@@`）的映射，整数盒中支撑质量（mass）至多为一的下解/上解作为证人（witness），要求靠近相应边界的坐标取得既定符号。算法继承确定性姊妹篇的两趟枢轴递归，关键新意在于证人的平移方向固定——下解下移、上解上移——而 `@@M@@0<\gamma<1@@` 使 `@@M@@\gamma t\ge t@@`，折扣平移恒等式恰好保住所需不等式，大盒证人因此能装进更小的递归盒。枢轴每趟停住时，最后一次原地不动的子调用是确定性证书：仍有主张的证人必有超过 `@@M@@3/4@@` 的质量聚在峰值附近；半宽调用随即为这些坐标定性，再按"得势方变轻、失势方变重"重配质量，未决证人的质量仍小于 1，可在原盒继续递归，而每个乘积 `@@M@@a_ib_i@@` 放大 `@@M@@32/25@@` 倍，故沿任一递归路径此类预算消耗至多 `@@M@@O(\log n)@@` 次。

最后回到具体博弈：取缩放映射 `@@M@@F(t)=Sf_{\lambda_0}(t/S)@@`，证明存在间距至多 `@@M@@2(N+1)@@` 的整数比较向量从两侧夹住不动点（仅用于证明，算法不计算它们）；用标记输出的排除性结论把盒边界逐轮内移 `@@M@@\le D/128@@`，至多 `@@M@@128(d_0+1)@@` 轮后逼近误差 `@@M@@\le1/(8H)@@`；配合 `@@M@@1/H@@` 的值隙，按 `@@M@@A_i\ge-8K@@` 输出即得精确判定，零值顶点恰好收入。递归树中每条路径至多 `@@M@@d_0+B_0@@` 条边，而分支位置至多 `@@M@@B_0=O(\log n)@@` 个、每处至多 `@@M@@2048n+3@@` 个选择，节点总数 `@@M@@\le\sum\binom{\ell}{j}s_*^j=2^{O((\log(L+2))^2)}@@`。

## 可信度与备注

本篇暂无形式化证明，请以社区核验为准。它是族内"同时标记"技术的折扣版延伸：确定性平均收益篇（2026 年 9 月 25 日）第 4–5 节的两趟枢轴—质量重配递归是其直接前身，本文把平移恒等式从 `@@M@@F(z+t)=F(z)+t@@` 推广到带 `@@M@@\gamma<1@@` 的折扣版本，使机会顶点与玩家顶点在同一套秩序与平移性质下处理；奇偶篇则反向调用确定性篇作子程序，三篇互为支撑。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
