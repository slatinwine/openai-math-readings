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

## 一句话结论

构造出整群环矩阵 \(A\in\mathrm{Mat}_n(\mathbb Z[G_D])\)，它在有理群环上可逆，而其 Fuglede–Kadison 行列式严格介于 \(0\) 与 \(1\) 之间（精确值 \(q^{-\theta}\)），否定无限制版本的群环行列式猜想。

## 问题背景

非奇异整数矩阵的行列式绝对值至少为一。Fuglede 与 Kadison（1952）借助左正则表示在 \(\ell^2(G)\) 上定义了群冯·诺依曼代数（group von Neumann algebra）中的行列式——按 \(\frac12\tau_n(\log(T_A^*T_A))\) 计算（\(\tau_n\) 为未归一化矩阵迹），是普通行列式绝对值的推广，属于 \(L^2\) 不变量理论。Lück 的行列式猜想断言：整群环矩阵的该行列式的对数非负。amenable 群（Schick）与 sofic 群（Elek–Szabó，用有限图逼近与正整矩阵非零特征值乘积的整性）上的肯定结果表明反例群必非 sofic。需注意这与行列式逼近（approximation）问题是两回事：Kammeyer 的 Heisenberg 群例子只是逼近公式失效，并未破坏下界。本文给出下界本身的首个反例。

## 主要结果

定理：存在有限生成的离散群 \(G_D\)、整数 \(n\ge1\) 及矩阵 \(A\in\mathrm{Mat}_n(\mathbb Z[G_D])\)，\(A\) 在 \(\mathbb Q[G_D]\) 中可逆，且

\[0<\det_{\mathcal N(G_D)}(T_A)<1 .\]

等价地，定义行列式的对数谱测度积分 \(\int_{(0,\infty)}\log t\,d\mu_A(t)\) 有限且严格为负。矩阵有有界逆，谱远离零，因此失败的是下界，而不是行列式类。矩阵阶数 \(n=2d+1\)，积分值为 \(-\frac{2\theta\log q}{2d+1}\)；群 \(G_D\) 由 \(H_2\) 的有限生成集加上一个三阶坐标生成元生成，故有限生成。

## 证明思路

起点是特征二姊妹篇的标量缺陷 \(a_2b_2=1\ne b_2a_2\in K_2[H_2]\)。第一步把标量缺陷转换为投影的"迹差"。以乘法矩阵表示把 \(K_2[H_2]\) 嵌入 \(\mathrm{Mat}_d(\mathbb F_2[H_2])\)（\(d=[K_2:\mathbb F_2]\)），得到 \(XY=I_d\) 及非零幂等 \(C=I_d-YX\)，且 \(XC=CY=0\)。放大群为 \(G_D=(\bigoplus_{h\in H_2}C_3)\rtimes H_2\)，在每个三阶循环坐标上取平均 \(p_h=(1+z_h+z_h^2)/3\)——这是一族两两交换的正交幂等；乘积 \(p=p_1\prod_{s\in S}(1-p_s)\) 用互补平均隔离出恒等系数，迹差 \(\theta=\frac13(\frac23)^{|S|}>0\)。于是 \(P=\mathrm{diag}(I_d,p)\) 是迹为 \(d+\theta\) 的有理正交投影，而其模 \(2\) 约化却可经 \(d\) 列分解：实迹超过列数，缺口 \(\theta\) 正是负行列式的来源。

第二步把缺口铸成整矩阵。仅有模 \(2\) 的分解还不够——整性要求右下块的 \(q^{-1}\) 被整除抵消。于是先在角环（corner ring）里用几何级数把模 \(2\) 分解提升到模 \(q=2^k\)（关键余项满足 \(W^k=0\) 的幂零性），并取 \(q\equiv1\pmod D\)，其中奇数 \(D=3^{1+|S|}\) 清除 \(P\) 的全部分母。随后写出分块矩阵 \(A=\begin{pmatrix}qI_r&V\\U&q^{-1}(UV-P-q(I_m-P))\end{pmatrix}\)：Schur 消元视角说明模 \(q\) 分解恰好抵消右下块的分母，故 \(A\) 是整矩阵；再沿道路 \(M(x)=L_xBR_x\) 把它连到对角形 \(B\)，从而显式给出有理逆。

第三步是分析核心。Fuglede–Kadison 的迹对数导数（文中完整自证，用泛函演算的一致收敛级数与迹的循环性，不假设 \(N\) 与 \(N'\) 交换）给出 \(\frac{d}{dx}\tau(\log(M^*M))=2\operatorname{Re}\tau(M'M^{-1})\)；而左右分块剪切（block shear）\(L_x,R_x\) 的生成元对角块为零、迹为零，故沿整条道路正平方的对数迹不变。在 \(x=0\) 处 \(B^*B\) 为对角阵，对数可直接算出，得 \(\log\det=(r-\tau_m(P))\log q\)。代入 \(r=d\)、迹 \(d+\theta\)，即得精确值 \(q^{-\theta}\in(0,1)\)。谱的双边估计保证积分有限。附带结论：把 Elek–Szabó 的 sofic 行列式下界用于正整矩阵 \(A^*A\)，可知 \(G_D\) 非 sofic。论文特别强调：投影构造、模提升与迹计算三者分工明确，任何一环都不能替代标量存在性输入。

## 可信度与备注

本文主结果已 Lean 形式化。全篇唯一的非自足输入是特征二姊妹篇的标量缺陷定理（该篇主结果亦已形式化），投影构造、模提升与迹计算均在本文内完成；三篇论文互为犄角，构成结果族 197 对直接有限性、满射性与行列式三大猜想的连环否定。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文及其所依赖的输入均不在警示之列。

{% endraw %}
