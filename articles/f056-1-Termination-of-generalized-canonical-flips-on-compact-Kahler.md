---
layout: default
title: "Termination of generalized-canonical flips on compact Kähler fourfolds"
family: "056"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Termination of generalized-canonical flips on compact Kähler fourfolds

> 结果族 056：Termination of projective and Kähler fourfold minimal model programs　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了紧 Kähler 四重折叠上广义典范翻转序列必终止：边界系数小于一、允许例外对数差异等于一、每步为具相反丰富符号的射影小双有理图，且不需要伪有效性或缩放规则假设，把四维终止性推广到了非射影复几何的广义配对情形。

## 问题背景
极小模型纲领（minimal model program, MMP）中的翻转（flip）把伴随除子为负的小收缩换成其为正的小收缩，序列能否无限继续——终止性（termination of flips）——是高维双有理几何的老大难。四维代数情形的路线由 Kawamata–Matsuda–Matsuki（终端、空边界）与 Fujino（典范配对、有效有理边界）开辟：Shokurov 差异（discrepancy）计数加曲面类下降。广义配对（generalized pair）把伴随扩为 `@@M@@K_X+B+M_X@@`，其中 `@@M@@M@@` 是更高双有理模型上 nef 数据的迹，它能在没有边界的地方改变差异。已知广义终止性结果多带硬条件：Chen–Tsakanikas 与 Moraga 要求伪有效 NQC；Das–Hacon–Păun 的 Kähler 四维 dlt 结果要求伴随有理线性等价于有效除子且各模型保持 Kähler；Hacon–Xie 的带缩放结果要求边界加 nef 部分为大（big）。本文去掉这些假设，在紧 Kähler（可非射影）环境中处理广义典范情形。

## 主要结果
主定理：设 `@@M@@X_0@@` 是正规不可约、整体 Weil `@@M@@\Q@@`-因子化（globally Weil `@@M@@\Q@@`-factorial）的紧 Kähler 四重折叠，`@@M@@B_0\geq0@@` 是系数落在 `@@M@@[0,1)@@` 的有理除子，`@@M@@\bM@@` 是由射影双有理态射 `@@M@@X'\to X_0@@` 上解析 nef（analytically nef，即其 `@@M@@c_1@@` 在 Kähler 锥的闭包中）`@@M@@\Q@@`-Cartier 除子 `@@M@@M'@@` 代表的固定有理 b-除子，且 `@@M@@D_0=K_{X_0}+B_0+M_{X_0}@@` 为 `@@M@@\Q@@`-Cartier。初始配对满足：每个素 place 的广义对数差异为正，每个例外素 place 的差异至少为一（即广义典范，generalized canonical；例外差异允许恰等于一）。若序列 `@@M@@X_0\dashrightarrow X_1\dashrightarrow\cdots@@` 每步都是射影小双有理态射组成的图 `@@M@@X_i\to Z_i\leftarrow X_{i+1}@@`，且 `@@M@@-D_i@@` 为 `@@M@@f_i@@`-丰富、`@@M@@D_{i+1}@@` 为 `@@M@@f_i^+@@`-丰富，则序列有限。定理针对"已给定的"图，不涉及下一步收缩或翻转的存在性。

## 证明思路
整个论证由维数枢纽串联：小性（smallness）给出两个例外轨迹维数至多为二，相反的丰富符号迫使二者维数之和至少为三，因此一旦目标侧例外轨迹不含曲面，源侧必含曲面——曲面正是差异与循环计数的交汇点。第一步证"严格比较"：中心落在任一例外轨迹中的 place，其差异在翻转后严格上升；结合边界的有效性与拉回 nef 迹同 nef 数据之差 `@@M@@J_W\geq0@@` 的有效性，推出目标四重折叠在翻曲面（flipped surface）一般点的邻域内具有普通终端奇性，进而在该点光滑——这正是后续爆破计算所需的确切光滑性，承袭并推广了 Fujino 的经典引理。第二步构造"见证"（witness）：在翻曲面的光滑一般点爆破，得到一个整体素除子，其目标差异落在固定格点 `@@M@@\Lambda_m=(1,2]\cap\frac1m\Z@@` 上，其中 `@@M@@m@@` 是同时清除 `@@M@@M'@@` 的 Cartier 指标与全部边界系数的整数；由于每次充当见证差异都严格上升，同一 place 至多用 `@@M@@m@@` 次。第三步做按边界系数降序的归纳：系数 `@@M@@b@@` 分量中的翻曲面，其见证在源上的差异严格小于 `@@M@@2-b@@`；再由"低位 place 引理"（差异低于二的 place 除有限个外，中心必落在某个正系数边界分量中），若见证不属于有限集，其中心必落在系数 `@@M@@d>b@@` 的分量里——而归纳阶段已排除高系数分量中的翻转曲面，曲面中心的持久性引理据此导出矛盾。于是每个系数层面只余有限步。第四步在同一系数的边界分量上比较解析曲面类的秩：用 Borel–Moore 局部化序列、Kähler 正性（保证被消去的曲面类非零）以及 Wang 的解析负性引理，证明秩 `@@M@@c_2@@` 在含翻曲面的步骤严格下降，且此比较对非正规的既约解析空间成立，无需正规化。所有正系数处理完后，取 `@@M@@b=0@@` 的见证论证排除一切翻曲面；此时目标例外轨迹维数至多为一，维数枢纽迫使源例外轨迹恒含曲面，把同样的循环比较用于四重折叠本身得 `@@M@@c_2(X_i)>c_2(X_{i+1})@@`，非负整数无法无限严格下降，序列必有限。值得注意的是证明自成一体，不引用任何终止性定理。

## 可信度与备注
本文主结果暂无 Lean 形式化证明，请以社区核验为准。它与族内另两篇构成互补：射影 log canonical 四重折叠一文提供了它在代数侧的对应物，广义 log canonical Kähler 一文则允许系数为一的边界、改用带分支界修正的难度泛函，而本文走"见证格点+按系数下降的循环秩"路线并允许例外差异等于一。按 OpenAI 官方声明，未经形式化的结果可能有问题，结论宜以同行评议为最终标准。

{% endraw %}
