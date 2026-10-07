---
layout: default
title: "A nine-dimensional counterexample to Borsuk's covering assertion"
family: "156"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A nine-dimensional counterexample to Borsuk's covering assertion

> 结果族 156：Borsuk's conjecture fails in dimension nine　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文构造了 \(\mathbb{R}^9\) 中的紧集——\(\mathbb{R}^4\) 上全体秩一正交投影矩阵在 Frobenius 度量下的像——其直径为 \(\sqrt2\)，却不能被 10 个直径严格小于 \(\sqrt2\) 的集合覆盖，从而在 9 维推翻 Borsuk 覆盖猜想，把反例维度纪录从 63 一举压到 9。

## 问题背景

1933 年 Borsuk 提出划分问题：\(\mathbb{R}^d\) 中每个直径为正的有界集，能否用 \(d+1\) 个直径严格更小的子集覆盖？记 \(b(Y)\) 为所需子集个数的最小值，猜想即断言 \(b(Y)\le d+1\)。Kahn 与 Kalai 在 1993 年借助 Frankl–Wilson 的禁距定理（forbidden-intersection theorem）在高维推翻了它，此后反例维度被持续压低：Nilli 的 946、Raigorodskii 的 561、Hinrichs 用 Leech 格球码（spherical code）得到的 323、Bondarenko 与 Jenrich–Brouwer 用强正则图（strongly regular graph）得到的 65 与 64，直到 2026 年 Grinsztajn 的 63。这些反例都是有限点组，继续降维极为困难。本文改用连续构形——实射影空间 \(\mathbb{RP}^3\) 经投影矩阵嵌入的完整紧像——并直面新困难：它的"面"来自映射的坐标支撑而非三角剖分的单纯形，Walkup、Arnoux–Marin 等关于 \(\mathbb{RP}^3\) 三角剖分的经典顶点数下界无法直接套用，面结构必须从映射本身重新推导。

## 主要结果

定理：设 \(\operatorname{Sym}_4(\mathbb{R})\) 为实对称 \(4\times 4\) 矩阵空间，配 Frobenius 范数 \(\|A\|_F^2=\operatorname{tr}(A^2)\)；迹一超平面 \(\{\operatorname{tr}A=1\}\) 是九维欧氏空间（论文给出到 \(\mathbb{R}^9\) 的显式等距映射）。紧集
\[X=\{uu^{\mathsf T}:u\in\mathbb{R}^4,\ \|u\|=1\}\]
由全体秩一正交投影矩阵（rank-one orthogonal projector）组成，其直径为 \(\sqrt2\)，且不能被 10 个直径严格小于 \(\sqrt2\) 的集合覆盖，即 \(b(X)>10\)。于是在 9 维 Borsuk 断言失效；论文还给出推论，把同一构造推广为每个 \(d\ge 9\) 维的紧反例。几何上一切归结为公式 \(\|P_x-P_y\|_F^2=2-2\langle u,v\rangle^2\)：两个投影矩阵相距恰为 \(\sqrt2\)，当且仅当它们对应的直线正交。

## 证明思路

证明分四大步：先把覆盖问题化为射影空间上的映射，再做矩阵扩张，然后用模二度约束支撑复形，最后归结为有限组合矛盾。

先做几何约化。若 \(X\) 被 \(m\) 个直径 \(<\sqrt2\) 的集合覆盖，则把每个集合稍稍加厚为开集（直径仍 \(<\sqrt2\)），拉回 \(\mathbb{RP}^3\) 后用光滑单位分解得到非负、和为 1 的函数组 \(f_1,\dots,f_m\)，使得正交直线的正坐标标号集 \(S(x)\) 与 \(S(y)\) 不相交——此即"容许映射"（admissible map）。再做矩阵扩张：令 \(H(v)=\|v\|^2f([v])\)，对半正定矩阵按球面积分 \(E(Q)=k\int H(Q^{1/2}u)\,d\mu(u)\)，其正标号恰为 \(Q\) 的值域中直线用到的标号之并；对一般对称矩阵写 \(A=A_+-A_-\)，令 \(F(A)=E(A_+)-E(A_-)\)。正负谱子空间彼此正交，两组正标号无相消，故 \(\|F(A)\|_1=\operatorname{tr}|A|\)，归一化后 \(F\) 成为球面间的奇映射（odd map）。

然后是拓扑核心。奇映射 \(S^n\to S^d\) 要求 \(n\le d\)，故 \(m\ge N_k=k(k+1)/2\)；\(k=4\) 时即 \(m\ge 10\)，而 \(m=10\) 为等式情形，此时 \(F\) 的模二度（mod-2 degree）为 1。对支撑复形的任一极大面 \(I\)，在单个仿射坐标卡内取水平集 \(L\)，并在 \(L\) 上由正交补构成的球丛中诱导出奇映射 \(G\)：一方面 \(F\) 的奇度强制 \(G\) 的正则原像个数为奇数；另一方面当 \(\dim L>0\) 时，Stiefel–Whitney 类的拉回计算迫使诱导的射影丛间映射模二度为零、原像数应为偶——矛盾。由此每个极大面恰含 4 个标号（四面体），且全部四面体之和构成 \(\mathbb{F}_2\) 闭链：每个三角形属于正偶数个四面体。

最后化为有限组合矛盾。把 \(f\) 限制到某四面体见证直线的正交补 \(\mathbb{RP}^2\) 上，在 6 个补标号上得到"三角形系统"——每对互补三元组恰取其一、每对标号恰属于两个三角形；该系统刚性极强：顶点链环均为五边形圈，任何对换都不能保持它。回到 10 标号层面，沿相邻四面体搬运这些系统，依次得出每个三角形恰属两个四面体、边的链环只能是 3 或 4 圈，标号最终被组织成大小为 \(3,2,2\) 的"伙伴块"（partner block）外加 3 个余留标号；于是必有一个三角形至多属于一个四面体，与"恰属两个"矛盾。故容许映射 \(\mathbb{RP}^3\to\Delta^9\) 不存在，\(b(X)>10\)。

## 可信度与备注

本篇主结果已由 Lean 形式化验证（结果族 156 附有对应 Lean 文档），机器检查为这一横跨几何、拓扑与组合的长论证提供了强背书；OpenAI 官方声明"未经形式化的结果可能有问题"，而本篇恰属已形式化之列，可信度较高。本结果族仅此一篇手稿，无姊妹篇互相支撑，但结论与 Kahn–Kalai 以来的反例谱系完全相容，且论文显式给出九维等距坐标，便于独立复核。需注意：论文并未断言 9 是 Borsuk 猜想失效的最小维度，也未确定 \(b(X)\) 的精确值。

{% endraw %}
