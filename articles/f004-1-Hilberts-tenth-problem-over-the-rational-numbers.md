---
layout: default
title: "Hilbert’s tenth problem over the rational numbers"
family: "004"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Hilbert’s tenth problem over the rational numbers

> 结果族 004：Hilbert’s tenth problem over ℚ　·　学科：Number theory（数论）　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一台"方程判题机"：塞进去任何整系数多项式，它都能回答"这方程有没有有理数解"。希尔伯特 1900 年为整数解提出这个愿望，1970 年被证明落空——机器造不出来。有理数版本又悬了五十多年，这篇论文给出同样的否定答案：在分数的世界里，判题机也永远造不出来。

**关键词卡片**

- 希尔伯特第十问题（Hilbert's tenth problem）：寻求一个通用算法，判定整系数多项式方程有没有指定类型的解。
- 丢番图方程（Diophantine equation）：求整数或有理数解的多项式方程。
- 有理零点（rational zero）：让多项式取值为 0 的有理数取值组合。
- 递归可枚举（recursively enumerable）："解可以一个一个列出来"的计算性质，整数版不可判定正源于此。
- 典范高度（canonical height）：衡量椭圆曲线上一个点"大小"的标尺，证明结尾的高度矛盾靠它收官。

**看个具体例子**

有的方程一眼能判：`@@M@@x^2+y^2+3=0@@` 没有有理解，因为左边恒为正。难的不是单个方程，而是"统一机器"：论文证明不存在算法对所有多项式（变量个数也任意）作答，而且你无法事先知道哪个多项式属于"答不出"的那类。归约思路是：假如有理判题机存在，就能拼出整数判题机，与 1970 年的著名否定结论矛盾。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" font-size="17" text-anchor="middle" fill="#222">假如"有理数判题机"存在……</text>
  <rect x="40" y="60" width="180" height="64" fill="none" stroke="#333" stroke-width="2"/>
  <text x="130" y="86" font-size="14" text-anchor="middle" fill="#222">输入：整系数多项式 f</text>
  <text x="130" y="108" font-size="14" text-anchor="middle" fill="#222">（变量个数任意）</text>
  <line x1="220" y1="92" x2="288" y2="92" stroke="#333" stroke-width="2"/>
  <polygon points="288,87 300,92 288,97" fill="#333"/>
  <rect x="300" y="60" width="200" height="64" fill="none" stroke="#333" stroke-width="2"/>
  <text x="400" y="100" font-size="15" text-anchor="middle" fill="#222">万能判定算法？</text>
  <line x1="310" y1="66" x2="490" y2="118" stroke="#c0392b" stroke-width="3"/>
  <line x1="490" y1="66" x2="310" y2="118" stroke="#c0392b" stroke-width="3"/>
  <line x1="370" y1="124" x2="330" y2="180" stroke="#333" stroke-width="1.5" stroke-dasharray="5,4"/>
  <line x1="430" y1="124" x2="470" y2="180" stroke="#333" stroke-width="1.5" stroke-dasharray="5,4"/>
  <rect x="290" y="180" width="90" height="44" fill="none" stroke="#333" stroke-width="1.5" stroke-dasharray="5,4"/>
  <text x="335" y="206" font-size="14" text-anchor="middle" fill="#222">有理解</text>
  <rect x="420" y="180" width="90" height="44" fill="none" stroke="#333" stroke-width="1.5" stroke-dasharray="5,4"/>
  <text x="465" y="206" font-size="14" text-anchor="middle" fill="#222">无解</text>
  <text x="280" y="252" font-size="15" text-anchor="middle" fill="#555">论文证明：中间那台机器永远造不出来</text>
  <text x="280" y="272" font-size="14" text-anchor="middle" fill="#555">若它存在，整数版判题机也能造出，与 1970 年定理矛盾</text>
</svg>

</div>

**为什么值得关心**

这是数理逻辑与数论（椭圆曲线、模形式、Shimura 曲线、Green–Tao–Ziegler 素数定理）深度联手的成果，补上了丢番图不可判定版图上最大的空白。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明 ℚ 上的希尔伯特第十问题（Hilbert's tenth problem over ℚ）有否定答案：不存在算法能判定整系数多项式（变量个数任意）是否有有理零点。这一悬置五十余年的难题，由椭圆曲线、模形式与高度理论的深度组合攻克。

## 问题背景

1900 年希尔伯特提出第十问题：寻找有限步骤，判定整系数多项式方程有无整数解。Davis–Putnam–Robinson 与 Matiyasevich（1961/1970）证明每个递归可枚举（recursively enumerable）关系都是丢番图（Diophantine）的，整数情形因此不可判定。把未知数改为取值于 `@@M@@\Q@@` 后，问题长期开放：枚举总能找到存在的有理零点，却无法证明不存在。最直接的路线是用纯存在量词在 `@@M@@\Q@@` 中定义 `@@M@@\Z@@`，但 Julia Robinson（1949）、Poonen（2009）、Koenigsmann（2016）的定义都离不开全称量词，Mazur 的猜想甚至暗示丢番图式定义不可能。近年 Koymans–Pagano 等人无条件解决了所有数域整数环上的同类问题，但 `@@M@@\Q@@` 不是有限生成 `@@M@@\Z@@`-代数，有理域本身一直悬而未决——本文补上了这块拼图。

## 主要结果

主定理（Theorem 1.1）：不存在算法，给定 `@@M@@f\in\Z[X_1,\ldots,X_n]@@`（`@@M@@n@@` 属于输入的一部分），判定 `@@M@@f@@` 在 `@@M@@\Q^n@@` 中是否有零点。等价地说，论文把整数可解性归约到有理可解性：若有理情形可判定，则由 DPRM–Matiyasevich 定理已知不可判定的整数情形也将变得可判定，矛盾。论文引言还指出，文末第 7 节把结论加强到图灵度 `@@M@@0'@@`，并给出四次正规形式（quartic normal form）。

## 证明思路

整体骨架是"有限测试"归约。对每个非常数 `@@M@@f@@`，论文有效地枚举一列有限测试，每个测试只含有限多个有理可解性查询，并证明 `@@M@@f@@` 有整数零点当且仅当全部测试通过。若有理可解性可判定，便可并行搜索整数零点与失败测试，必有一个终止，从而整数可解性也可判定，与 DPRM 矛盾。整数零点自然充当所有测试的见证；难点是证明 `@@M@@f@@` 无整数零点时必有测试失败。

先看模型论一侧。假设全部测试通过，紧性定理（compactness theorem）给出 `@@M@@\Q@@` 的初等扩张（elementary extension）`@@M@@{}^*\Q@@`，其中嵌着环 `@@M@@R@@` 与 `@@M@@f@@` 的零点 `@@M@@\mathbf a@@`。理论给每个 `@@M@@a\in R@@` 指派椭圆曲线 `@@M@@E:\ y^2=x^3-d^2x@@`（`@@M@@d=75-53\sqrt2\in\Q(\sqrt2)@@`）上的点 `@@M@@T_a@@`，满足 `@@M@@T_{a+a'}=T_a+T_{a'}@@`、`@@M@@T_1=P@@`、`@@M@@a\ne0\Rightarrow T_a\ne O@@`。第 5 节用二同源下降（two-isogeny descent）算出 `@@M@@E(\Q(\sqrt2))@@` 秩为 1，故有 `@@M@@m@@` 与非挠点 `@@M@@P@@` 使 `@@M@@mE(F)=\Z P@@`，于是 `@@M@@\widetilde T_a=\eta(a)P@@`，指标 `@@M@@\eta(a)\in{}^*\Z@@`。`@@M@@\eta@@` 加性、单射且 `@@M@@\eta(1)=1@@`，但不必保持乘法——这是核心障碍。

再补三项算术输入。局部比较引理合并两条测试：截断形式对数（formal logarithm）`@@M@@\ell_K@@` 之比在好素数处以精度 `@@M@@K@@` 逼近 `@@M@@\widetilde a@@`，共轭曲线 `@@M@@E^\sigma@@` 上的参数赋值比保证指标比在该处可积，合起来给出 `@@M@@v_q(\widetilde a-\eta(a))\ge K@@`。第 6 节用 Green–Tao–Ziegler 线性素方程定理配合 Selberg 上界筛证明素数模式：任意整数都可写成三个分数之和，使十三个接触形式的值全为 `@@M@@\pm kr@@`（`@@M@@k@@` 属固定有限集，`@@M@@r@@` 为大分裂素数），测试因此在整数模型中可满足。第 3 节构造正存在公式 `@@M@@\Phi@@` 排除固定素数外的奇极点，证明依赖 `@@M@@y^2=x(x-l)(x+3l)@@` 型曲线的 Selmer 群（Selmer group）`@@M@@\F_2@@`-矩阵计算、姊妹篇的点态 2-逆定理与 Cassels–Tate 配对。

最后以高度矛盾收官。第 4 节证明五点高度估计 `@@M@@h(s)\le HM(s)^c@@`（`@@M@@M(s)@@` 为与固定五个有理点奇接触的素数之积）：几何上取判别式 210 的不定四元数代数（quaternion algebra）对应的 Shimura 曲线——亏格 5，Atkin–Lehner 商为 `@@M@@\mathbf P^1@@`，恰五个有理分支值——及其上带四元数乘法的阿贝尔曲面族；算术上经"奇正则 Fontaine–Mazur"模性（modularity）定理、导子估计与定量同源定理完成。令 `@@M@@\delta=f(\eta(a_1),\ldots,\eta(a_n))@@`：若 `@@M@@\delta=0@@`，初等性直接给出普通整数零点；否则 `@@M@@|\delta|\le C_fB^D@@`（`@@M@@B=\max|\eta(a_j)|@@`），取 `@@M@@K\ge cD@@` 后，一切表示式的接触素数均 `@@M@@K@@` 次整除 `@@M@@\delta@@`，高度估计给出 `@@M@@h(\widetilde A)\ll_f B@@`（一切 `@@M@@A\in R@@`）。用于 `@@M@@x(T_{a_j})@@` 的坐标得 `@@M@@h(x(\eta(a_j)P))\ll_f B@@`，而典范高度（canonical height）随指标平方增长，故 `@@M@@B^2\ll_f B@@`，各 `@@M@@\eta(a_j)@@` 被逼入普通有限区间，均为普通整数；由 `@@M@@\eta@@` 加性单射，`@@M@@a_j@@` 即这些整数，`@@M@@f@@` 有整数零点，与 `@@M@@\delta\ne0@@` 矛盾，定理得证。

## 可信度与备注

本文暂无 Lean 形式化证明，验证状态以社区核验为准。证明横跨模型论、椭圆曲线、Shimura 曲线与解析数论，多处调用极深的外部工具（Green–Tao–Ziegler 定理、定量同源定理、模性定理），核验门槛很高。同族姊妹篇《A pointwise 2-converse for elliptic curves with rational two-torsion》所证的 2-逆定理，正是第 3 节把 Selmer 类实现为有理点的关键输入，两篇互为支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
