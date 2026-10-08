---
layout: default
title: "Lech's multiplicity conjecture"
family: "194"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Lech's multiplicity conjecture

> 结果族 194：Lech's multiplicity conjecture　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把一块面团均匀擀开（不撕破、不折叠）是"平坦"的直观；一个形状在某点的"重数"衡量它在那里有多厚——越接近"光滑平坦"，厚度越接近 1。Lech 在 1960 年代猜测：均匀擀开只会让厚度保持或增加，绝不会变薄。本文在完全不设限的条件下证明：确实只增不减。此前最好的结果也只在等特征下给出带常数因子的界，常数的帽子如今被彻底摘掉。

**关键词卡片**

- Hilbert–Samuel 重数：局部环在一点处无穷小邻域增长的"主阶系数"，即厚度。
- 平坦局部同态（flat local homomorphism）：无扭、不撕破的环扩张，"均匀擀开"的代数化身。
- Noether 局部环：理想升链稳定、聚焦在一点上的标准代数舞台。
- Frobenius：特征 `@@M@@p@@` 世界的 `@@M@@p@@` 次幂自映射，证明里的放大镜。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="32" text-anchor="middle" font-size="14">平坦扩张 = 均匀擀开：厚度只许增，不许减</text>
<rect x="50" y="105" width="110" height="70" fill="none" stroke="#3050a0" stroke-width="2.5"/>
<text x="105" y="145" text-anchor="middle" font-size="14" fill="#3050a0">e(R) = 3</text>
<text x="105" y="205" text-anchor="middle" font-size="13">原来的面团</text>
<line x1="175" y1="140" x2="245" y2="140" stroke="#222" stroke-width="2"/>
<polygon points="245,135 245,145 257,140" fill="#222"/>
<text x="212" y="126" text-anchor="middle" font-size="12">平坦局部同态</text>
<rect x="270" y="70" width="180" height="140" fill="none" stroke="#222" stroke-width="2"/>
<text x="360" y="145" text-anchor="middle" font-size="14">e(S) = 6 ✓</text>
<text x="360" y="240" text-anchor="middle" font-size="13">变厚：允许</text>
<rect x="480" y="120" width="55" height="40" fill="none" stroke="#b03030" stroke-width="2"/>
<text x="507" y="145" text-anchor="middle" font-size="13" fill="#b03030">e=1</text>
<line x1="472" y1="112" x2="542" y2="168" stroke="#b03030" stroke-width="2.5"/>
<line x1="472" y1="168" x2="542" y2="112" stroke="#b03030" stroke-width="2.5"/>
<text x="507" y="205" text-anchor="middle" font-size="13" fill="#b03030">变薄：禁止</text>
</svg>

</div>

定理数字版：`@@M@@e(R)\le e(S)@@`。若源环 `@@M@@e(R)=3@@`，则任何平坦局部目标 `@@M@@S@@` 必有 `@@M@@e(S)\ge3@@`——翻倍、翻千倍都行，变薄不行。此处 `@@M@@e(A)@@` 由 `@@M@@\lim_{N\to\infty}d!\,\ell_A(A/\mathfrak a^N)/N^d@@` 定义。证明的难点在于：平坦性直接比较的是一套滤过的商，而重数由另一套滤过定义，两者无法直接对表，本文转而统一估计自由复形才闭合缺口。

**为什么值得关心**

一个悬置六十余年、连特殊情形都难得惊人的猜想被完整解决，且对维数、特征、剩余域零限制。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
本文完整证明 Lech 重数猜想：非零 Noether 局部环之间的平坦局部同态不会使 Hilbert–Samuel 重数减少，即 `@@M@@e(R)\le e(S)@@`，且对维数、剩余域、特征均无限制，宣告这一悬置六十余年的问题彻底解决。

## 问题背景
Hilbert–Samuel 重数（Hilbert–Samuel multiplicity）`@@M@@e(A)=\lim_{N\to\infty}d!\,\ell_A(A/\mathfrak a^N)/N^d@@` 度量局部环在闭点处无穷小邻域的主阶增长。二十世纪六十年代 Lech 提出猜想：平坦局部同态（flat local homomorphism）不会使它变小——平坦意味着"无扭"，目标环理应至少和源环一样"厚"。Lech 本人只证明了源维数至多二维以及完全交（complete intersection）闭纤维等特殊情形；Ma 证明了等特征三维情形，并建立了等特征下的一般界 `@@M@@e(R)\le\max\{1,d!/2^d\}\,e(S)@@`。基于 Ulrich 模（Ulrich module）与弱 lim Ulrich 序列的路线也无法普遍适用：Yhee 构造了不存在此类序列的二维非正规完备局部整环，本文引用的姊妹构造更给出一个三维正规完备局部 `@@M@@\mathbb C@@`-整环，其上不存在非零有限生成极大 Cohen–Macaulay 模（maximal Cohen–Macaulay module）。根本困难在于：平坦性比较的是 `@@M@@\mathfrak m^NS@@` 的商，而 `@@M@@e(S)@@` 由 `@@M@@\mathfrak n@@` 的幂定义，两套滤过即使都有有限余长，也无法直接比较首项。

## 主要结果
主定理：设 `@@M@@(R,\mathfrak m)\to(S,\mathfrak n)@@` 为非零 Noether 局部环之间的平坦局部同态，则 `@@M@@e(R)\le e(S)@@`，对维数、剩余域、特征均无任何限制。作为副产品，在特征 `@@M@@p>0@@` 时得到 Dutta 重数（Dutta multiplicity）不等式：完备 Noether 局部整环上的任何短复形（short complex，即集中在 `@@M@@0,\dots,d@@` 次、同调有限长且 `@@M@@H_0\ne 0@@` 的有限自由复形）满足 `@@M@@\chi_\infty^R(F)\ge e(R)@@`。这正是 Iyengar–Ma–Walker 相应猜想的整环情形，而其完全情形本就蕴含 Lech 猜想。

## 证明思路
全文枢纽是对自由复形的统一估计：设 `@@M@@C@@` 是可能非 Noether 的环，`@@M@@I=(z_1,\dots,z_h)C@@`，`@@M@@\lambda@@` 是使 `@@M@@z@@` 表现为参数系的加性长度（additive length）函数，则微分矩阵元全落在 `@@M@@I^s@@`、交错秩为零、在 `@@M@@V(I)@@` 外可缩的有限自由复形满足 `@@M@@\lambda(H_0F)\ge\lambda(C/I)\,s^h\bigl(b_0-A_h\textstyle\sum_i b_i/s\bigr)@@`，常数 `@@M@@A_h@@` 只依赖 `@@M@@h@@`。证明先过渡到爆破（blowup）`@@M@@Y=\mathrm{Proj}@@`，使 `@@M@@I@@` 变为可逆理想，用 `@@M@@L^{-is}@@` 除尽微分元；再取 Eisenbud–Schreyer 乘积射影直线构造的向量丛，其上同调根取在多项式 `@@M@@\prod_{i=1}^h(x+i)@@` 导数根的 `@@M@@s@@` 倍附近，迫使超同调集中到零次、欧拉特征非负；由于 `@@M@@C@@` 可能非 Noether，复形与爆破上拉回之间的欧拉特征比较改用有限滤过与截断映射的稳定像完成；最后黎曼和式误差估计使各层和的首项一致为 `@@M@@(h-1)!\,s^h@@`，交错秩恒等式恰好留下 `@@M@@b_0@@` 的贡献。

应用时先归约：完备化，经 Nagata 局部化定理与素滤过可加性化归为 `@@M@@R@@` 完备整环、`@@M@@\dim R=\dim S@@`、目标剩余域代数闭；再用 Avramov–Foxby–Herzog 的 Cohen 分解（Cohen factorization）得到 `@@M@@R\to T\twoheadrightarrow S=T/J@@`，其中 `@@M@@e(T)=e(R)@@`、`@@M@@J@@` 为完美（perfect）理想，而 `@@M@@F=P\otimes_TK(x_1,\dots,x_d;T)@@` 恰是满足估计条件的复形。特征 `@@M@@p@@` 时 Frobenius 把微分元升至 `@@M@@q@@` 次幂而秩不变，在完美化（perfection）上以正规长度（normalized length）把 `@@M@@H_0@@` 的长度识别为 Hilbert–Kunz 重数（Hilbert–Kunz multiplicity），逐分量套用估计后用 Ma 的恒等式加总为 `@@M@@e(S)@@`。混合特征时以参数根与 Heitmann 的整扩张 Briançon–Skoda 定理代替 Frobenius，用除以扩张秩 `@@M@@r@@` 消去秩增长，先对 `@@M@@x_i^N@@` 取幂极限得到与扩张无关的上界，再让微分元深度趋于无穷；每个顶层素恰落在 `@@M@@T@@` 的一个分量上，这正是系数 1 得以保持的原因。剩余特征零时，把严格反例编码为系数属 `@@M@@\mathbb Z@@` 的有限多项式方程组，经 Artin 逼近（Artin approximation）特化到正特征，与已证情形矛盾。

## 可信度与备注
主结果暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。证明显式引用多个外部深结果作为输入：perfectoid 正规长度理论（Cai–Lee–Ma–Schwede–Tucker）、Roberts 与 Hochster–Huneke 的 Frobenius 同调估计、Heitmann 的 Briançon–Skoda 型定理、Artin 逼近等。族内姊妹篇（如文中引用的三维无 MCM 模正规整环构造）从反面排除纯模路线，恰好支撑本文"弃模用复形"的战略；三个特征情形共用同一复形估计，结构上互相咬合。

{% endraw %}
