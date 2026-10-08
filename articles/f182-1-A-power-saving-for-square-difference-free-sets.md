---
layout: default
title: "A power saving for square-difference-free sets"
family: "182"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A power saving for square-difference-free sets

> 结果族 182：Power savings for intersective polynomial differences and prime arguments　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

从 1 到 N 里挑数，规则只有一条：任何两个挑中的数相减，差不能是非零完全平方——连差 1 都不行，所以相邻两数不能都要。这种集合叫"平方差自由集"，它能有多大？论文给出第一个固定幂上界 |A| ≤ C·N^(1−c)，正面回答了 Green–Sawhney 的公开问题。

**关键词卡片**

- 平方差自由集（square-difference-free set）：两两之差都不是非零平方数的集合，本文的主角
- 幂节省（power saving）：上界从"占比趋于零"强化为 |A| ≤ C·N^(1−c)，c 为绝对常数
- 下界构造（lower bound construction）：Ruzsa 等人造出约 N^0.733 的合法集合（最新达 0.7528）；它与上界之间的巨大缺口正是难度所在
- 色数（chromatic number）：给 1..N 染色使同色两数差非平方，所需颜色数至少 N^c——定理的直接推论

**看个具体例子**

数轴上 {1,4,7} 是合法的：两两之差只有 3、3、6，都不是平方。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="42" font-size="16" fill="#555" text-anchor="middle">一个平方差自由集：{1, 4, 7}</text>
<line x1="40" y1="150" x2="520" y2="150" stroke="#333" stroke-width="2"/>
<circle cx="80" cy="150" r="9" fill="#1a6feb"/>
<circle cx="200" cy="150" r="9" fill="#1a6feb"/>
<circle cx="320" cy="150" r="9" fill="#1a6feb"/>
<text x="80" y="118" font-size="16" fill="#1a6feb" text-anchor="middle">1</text>
<text x="200" y="118" font-size="16" fill="#1a6feb" text-anchor="middle">4</text>
<text x="320" y="118" font-size="16" fill="#1a6feb" text-anchor="middle">7</text>
<path d="M 80 168 L 80 176 L 200 176 L 200 168" fill="none" stroke="#2da44e" stroke-width="2"/>
<path d="M 200 168 L 200 176 L 320 176 L 320 168" fill="none" stroke="#2da44e" stroke-width="2"/>
<text x="140" y="198" font-size="14" fill="#2da44e" text-anchor="middle">差 3</text>
<text x="260" y="198" font-size="14" fill="#2da44e" text-anchor="middle">差 3</text>
<path d="M 80 208 L 80 216 L 320 216 L 320 208" fill="none" stroke="#2da44e" stroke-width="2"/>
<text x="200" y="238" font-size="14" fill="#2da44e" text-anchor="middle">差 6</text>
<rect x="170" y="250" width="14" height="14" fill="#b03030"/>
<text x="195" y="262" font-size="14" fill="#b03030">禁差：1, 4, 9, 16, 25, …（非零平方）</text>
</svg>

</div>

而定理说：N 变大时任何合法集都撑不过 C·N^(1−c)，如 N=10^6 时上界为 C·10^(6(1−c))（指数 c 为正但极小，论文不给数值）。推论：把 1..N 染色使同色两数之差避开平方，至少需要 N^c 种颜色。

**为什么值得关心**

这是 Sárközy–Furstenberg 平方差定理 1978 年以来定量方向的标志性一步，也是同族"多项式差"方法链（平方 → 一般多项式 → 素数）的源头。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了存在绝对常数 `@@M@@c>0@@` 与 `@@M@@C<\infty@@`：不含非零平方差的集合 `@@M@@A\subseteq\{1,\ldots,N\}@@` 必满足 `@@M@@|A|\le CN^{1-c}@@`。这正面回答了 Green–Sawhney 提出的固定幂问题，把 Sárköży 平方差定理以来的定量上界首次提升为固定幂。

## 问题背景

问题源自 Lovász：`@@M@@[N]@@` 中多大的集合能使其元素两两之差都不是非零平方？Furstenberg 与 Sárközy（1977–78）独立证明极值 `@@M@@s(N)=o(N)@@`。此后定量界在对数尺度上被反复改进：Pintz–Steiger–Szemerédi（1988）、Bloom–Maynard（2022），直到 Green–Sawhney（2025）的 `@@M@@N\exp(-c_1\sqrt{\log N})@@`，并在文中明确提出固定幂问题。下界方向，Ruzsa（1984）构造出 `@@M@@N^{0.7330\ldots}@@` 的例子，Lewko 改进到 `@@M@@0.7334\ldots@@`，Krachun（2026）突破四分之三线达 `@@M@@0.75279\ldots@@`。上界 `@@M@@1-c@@` 与下界指数之间的巨大缺口正是问题难度所在。

## 主要结果

定理：存在绝对常数 `@@M@@c>0@@`、`@@M@@C<\infty@@`，对每个 `@@M@@N\ge1@@` 与每个平方差自由集（square-difference-free）`@@M@@A\subseteq[N]@@` 有 `@@M@@|A|\le CN^{1-c}@@`；等价地，任何超过 `@@M@@CN^{1-c}@@` 的子集必含两个元素，其差的绝对值是正整数的平方。直接推论：平方差图 `@@M@@G_N@@`（顶点为 `@@M@@[N]@@`，平方差连边）的色数 `@@M@@\chi(G_N)\ge C^{-1}N^c@@`；当 `@@M@@N>(Cr)^{1/c}@@` 时任何 `@@M@@r@@`-染色都给出同色的 `@@M@@a@@` 与 `@@M@@a+d^2@@`（只要求两端同色）。作者注明指数为正但极小，论证不给出可用的数值或最优指数。

## 证明思路

策略是构造一个控制密度固定次幂的非负量，再证它随区间长度幂衰减；两件事分别对应"换尺度比较"与"正比例指派相消"两条估计。

先造量。固定偶数 `@@M@@d@@`、含一条 24 个标签指定有向圈的标签集 `@@M@@V@@`，以及介于固定阈值 `@@M@@P@@` 与 `@@M@@N^\beta@@`（`@@M@@\beta=10^{-5}@@`）之间的素数集 `@@M@@\mathcal P@@`。对每个 `@@M@@p\in\mathcal P@@` 在 `@@M@@\F_p@@` 上造概率律：单个标签一致分布；律反射正（reflection positivity，即棋盘法 chessboard method：沿指定反射切开元组所得耦合矩阵半正定）；除质量至多 `@@M@@p^{-4}@@` 的例外部分外，指定圈的相邻标签对在 `@@M@@\F_p@@` 中差为非零平方且在此类对中一致。逐素数相乘得乘积空间上的律，重复 Cauchy–Schwarz 给出符号 Hölder 不等式与半范数。`@@M@@G@@` 取 `@@M@@1_A@@` 的 Fourier 提升——保留分母无平方因子、`@@M@@\le N^\beta@@` 且素因子全在 `@@M@@\mathcal P@@` 中的有理频率系数，其均值恰为 `@@M@@|A|/N@@`。于是 `@@M@@(|A|/N)^d\le Y(N,A)@@`，只需证 `@@M@@Y@@` 幂衰减。

换尺度：固定乘积不超过 `@@M@@N@@` 的固定小幂的素坐标后，低频系数恰为模 `@@M@@D@@` 剩余类上的平均；把该类按公差 `@@M@@D^2@@` 拆进更短区间，尺度约为 `@@M@@N/D^2@@`——缩放 `@@M@@D^2@@` 保持"差为平方"，回避性随之传递，半范数的平方仿射对称性给出带趋于 1 因子的比较（对一切剩余类指派可用）。

算术相消：把小素数与模 8 并入固定模 `@@M@@M_0@@`；固定正比例的圈指派使圈增量构成"严格平方类"（`@@M@@\equiv1\pmod 8@@` 且模 `@@M@@M_0@@` 的每个奇素因子为非零平方）。把 `@@M@@[N]@@` 拆成有序区间，除"全部圈槽取同一区间"的小概率事件外，总有一条圈边从较早区间指向较晚区间；其余槽截断展开后归结为该边的对律。这里用符号核：模型核系数是规范单位二次 Gauss 和 `@@M@@\mathfrak g(\xi)@@`；实核支在真实平方 `@@M@@m^2@@` 上，带权 `@@M@@2m/N@@`、根限制 `@@M@@\rho_D@@` 与截断符号筛权（`@@M@@w_p=(p\mathbf 1_{p\mid m}-1)/(p-1)@@`，其完全除子和把一致剩余化为一致单位）。小弧用二次 Weyl 差分加 Dirichlet 逼近分块；大弧用周期均值与素数幂 Gauss 估计 `@@M@@|G_j(a)|^2=p^{-j}@@`；两核的 Fourier 变换一致相差 `@@M@@\ll H^{-1/3}@@`。回避性使实核双线性型逐项为零，从而对偶律相消。

最后对例外子测度做容斥展开：大乘积例外集由提升矩估计直接控制；小乘积 `@@M@@q_B@@` 导向尺度 `@@M@@\approx N/(M_0q_B)^2@@`，其质量乘 `@@M@@q_B@@` 后仍可和，足以吸收因子 `@@M@@q_B^{2a_0}@@`。合并成严格加权递归，归纳证明 `@@M@@Y(N,A)\ll N^{-a_0}@@`，取 `@@M@@c=a_0/d@@`。

## 可信度与备注

本篇暂无形式化证明。它是结果族 182 的方法论源头：交集多项式篇明确以本篇的反射正 tuple 律与符号泛函为直接前身并加以推广，素数参数篇再继续推进；而素数篇中 `@@M@@h=(x-1)^2@@` 的特例反过来重新蕴含本篇结论，形成闭环。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
