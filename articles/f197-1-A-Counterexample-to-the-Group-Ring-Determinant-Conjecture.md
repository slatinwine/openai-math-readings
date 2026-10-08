---
layout: default
title: "A Counterexample to the Group-Ring Determinant Conjecture"
family: "197"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Counterexample to the Group-Ring Determinant Conjecture

> 结果族 197：A torsion-free group algebra that is not directly finite　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

可逆的整数方阵，行列式的绝对值至少是 1——行列式是整数，不为零就得是 ±1、±2……这篇论文研究给"无限群上的矩阵"量出的一个类似行列式的数，直觉认为它同样不该小于 1，作者却造出一个严格落在 0 与 1 之间的例子。就像给一栋无限大的房子量面积，结果量出了 0.7 个单位。这个"平均对数"版行列式在有限交换情形就退化为普通行列式的绝对值，可视为"体积缩放率"向无穷维的推广。

**关键词卡片**

- 群环（group ring）：系数配在群元素上的有限和，可以相加相乘
- Fuglede–Kadison 行列式（Fuglede–Kadison determinant）：把行列式推广到无限维的办法：先取对数、再对群求平均
- 幂等元（idempotent）：满足 `@@M@@p^2=p@@` 的元素，像投影仪，把整个空间投出一块"影子"
- sofic 群（sofic group）：能用有限图案逼近的好群；sofic 群上这个行列式的下界已知成立

**看个具体例子**

定理造出整数群环上的方阵 `@@M@@A@@`：它在有理群环上可逆，但其 Fuglede–Kadison 行列式

`@@M@@D\det_{\mathcal N(G)}(T_A)=q^{-\theta},\qquad 0<q^{-\theta}<1 ,@@`

缺口 `@@M@@\theta=\frac13\left(\frac23\right)^{|S|}>0@@` 来自一个投影的"实际迹"比它的列数多出的部分。矩阵有有界逆、谱远离零点，说明出问题的正是下界本身，而不是行列式的定义。放到数轴上看：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="60" y1="160" x2="500" y2="160" stroke="#555" stroke-width="3"/>
<line x1="60" y1="145" x2="60" y2="175" stroke="#555" stroke-width="3"/>
<line x1="500" y1="145" x2="500" y2="175" stroke="#555" stroke-width="3"/>
<text x="54" y="205" font-size="18" fill="#222">0</text>
<text x="494" y="205" font-size="18" fill="#222">1</text>
<circle cx="280" cy="160" r="8" fill="#d33"/>
<text x="196" y="125" font-size="17" fill="#d33">q^(−θ) 落在这里</text>
<line x1="262" y1="132" x2="278" y2="152" stroke="#d33" stroke-width="1.5"/>
<text x="70" y="60" font-size="15" fill="#888">普通整数矩阵：|det| ≥ 1</text>
<text x="315" y="240" font-size="15" fill="#888">本例：严格落在 0 与 1 之间</text>
</svg>

</div>

**为什么值得关心**

这是无限制版群环行列式猜想（Lück 下界）的首个反例，且失败的是下界本身、不是计算方式；反例群自然又是非 sofic 群。它与两篇姊妹篇互为犄角，构成对直接有限性、满射性、行列式三大猜想的连环否定。

> 已 Lean 形式化

## 一句话结论

构造出整群环矩阵 `@@M@@A\in\mathrm{Mat}_n(\mathbb Z[G_D])@@`，它在有理群环上可逆，而其 Fuglede–Kadison 行列式严格介于 `@@M@@0@@` 与 `@@M@@1@@` 之间（精确值 `@@M@@q^{-\theta}@@`），否定无限制版本的群环行列式猜想。

## 问题背景

非奇异整数矩阵的行列式绝对值至少为一。Fuglede 与 Kadison（1952）借助左正则表示在 `@@M@@\ell^2(G)@@` 上定义了群冯·诺依曼代数（group von Neumann algebra）中的行列式——按 `@@M@@\frac12\tau_n(\log(T_A^*T_A))@@` 计算（`@@M@@\tau_n@@` 为未归一化矩阵迹），是普通行列式绝对值的推广，属于 `@@M@@L^2@@` 不变量理论。Lück 的行列式猜想断言：整群环矩阵的该行列式的对数非负。amenable 群（Schick）与 sofic 群（Elek–Szabó，用有限图逼近与正整矩阵非零特征值乘积的整性）上的肯定结果表明反例群必非 sofic。需注意这与行列式逼近（approximation）问题是两回事：Kammeyer 的 Heisenberg 群例子只是逼近公式失效，并未破坏下界。本文给出下界本身的首个反例。

## 主要结果

定理：存在有限生成的离散群 `@@M@@G_D@@`、整数 `@@M@@n\ge1@@` 及矩阵 `@@M@@A\in\mathrm{Mat}_n(\mathbb Z[G_D])@@`，`@@M@@A@@` 在 `@@M@@\mathbb Q[G_D]@@` 中可逆，且

`@@M@@D0<\det_{\mathcal N(G_D)}(T_A)<1 .@@`

等价地，定义行列式的对数谱测度积分 `@@M@@\int_{(0,\infty)}\log t\,d\mu_A(t)@@` 有限且严格为负。矩阵有有界逆，谱远离零，因此失败的是下界，而不是行列式类。矩阵阶数 `@@M@@n=2d+1@@`，积分值为 `@@M@@-\frac{2\theta\log q}{2d+1}@@`；群 `@@M@@G_D@@` 由 `@@M@@H_2@@` 的有限生成集加上一个三阶坐标生成元生成，故有限生成。

## 证明思路

起点是特征二姊妹篇的标量缺陷 `@@M@@a_2b_2=1\ne b_2a_2\in K_2[H_2]@@`。第一步把标量缺陷转换为投影的"迹差"。以乘法矩阵表示把 `@@M@@K_2[H_2]@@` 嵌入 `@@M@@\mathrm{Mat}_d(\mathbb F_2[H_2])@@`（`@@M@@d=[K_2:\mathbb F_2]@@`），得到 `@@M@@XY=I_d@@` 及非零幂等 `@@M@@C=I_d-YX@@`，且 `@@M@@XC=CY=0@@`。放大群为 `@@M@@G_D=(\bigoplus_{h\in H_2}C_3)\rtimes H_2@@`，在每个三阶循环坐标上取平均 `@@M@@p_h=(1+z_h+z_h^2)/3@@`——这是一族两两交换的正交幂等；乘积 `@@M@@p=p_1\prod_{s\in S}(1-p_s)@@` 用互补平均隔离出恒等系数，迹差 `@@M@@\theta=\frac13(\frac23)^{|S|}>0@@`。于是 `@@M@@P=\mathrm{diag}(I_d,p)@@` 是迹为 `@@M@@d+\theta@@` 的有理正交投影，而其模 `@@M@@2@@` 约化却可经 `@@M@@d@@` 列分解：实迹超过列数，缺口 `@@M@@\theta@@` 正是负行列式的来源。

第二步把缺口铸成整矩阵。仅有模 `@@M@@2@@` 的分解还不够——整性要求右下块的 `@@M@@q^{-1}@@` 被整除抵消。于是先在角环（corner ring）里用几何级数把模 `@@M@@2@@` 分解提升到模 `@@M@@q=2^k@@`（关键余项满足 `@@M@@W^k=0@@` 的幂零性），并取 `@@M@@q\equiv1\pmod D@@`，其中奇数 `@@M@@D=3^{1+|S|}@@` 清除 `@@M@@P@@` 的全部分母。随后写出分块矩阵 `@@M@@A=\begin{pmatrix}qI_r&V\\U&q^{-1}(UV-P-q(I_m-P))\end{pmatrix}@@`：Schur 消元视角说明模 `@@M@@q@@` 分解恰好抵消右下块的分母，故 `@@M@@A@@` 是整矩阵；再沿道路 `@@M@@M(x)=L_xBR_x@@` 把它连到对角形 `@@M@@B@@`，从而显式给出有理逆。

第三步是分析核心。Fuglede–Kadison 的迹对数导数（文中完整自证，用泛函演算的一致收敛级数与迹的循环性，不假设 `@@M@@N@@` 与 `@@M@@N'@@` 交换）给出 `@@M@@\frac{d}{dx}\tau(\log(M^*M))=2\operatorname{Re}\tau(M'M^{-1})@@`；而左右分块剪切（block shear）`@@M@@L_x,R_x@@` 的生成元对角块为零、迹为零，故沿整条道路正平方的对数迹不变。在 `@@M@@x=0@@` 处 `@@M@@B^*B@@` 为对角阵，对数可直接算出，得 `@@M@@\log\det=(r-\tau_m(P))\log q@@`。代入 `@@M@@r=d@@`、迹 `@@M@@d+\theta@@`，即得精确值 `@@M@@q^{-\theta}\in(0,1)@@`。谱的双边估计保证积分有限。附带结论：把 Elek–Szabó 的 sofic 行列式下界用于正整矩阵 `@@M@@A^*A@@`，可知 `@@M@@G_D@@` 非 sofic。论文特别强调：投影构造、模提升与迹计算三者分工明确，任何一环都不能替代标量存在性输入。

## 可信度与备注

本文主结果已 Lean 形式化。全篇唯一的非自足输入是特征二姊妹篇的标量缺陷定理（该篇主结果亦已形式化），投影构造、模提升与迹计算均在本文内完成；三篇论文互为犄角，构成结果族 197 对直接有限性、满射性与行列式三大猜想的连环否定。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文及其所依赖的输入均不在警示之列。

{% endraw %}
