---
layout: default
title: "Reconstruction from Milnor K-theory modulo the characteristic"
family: "009"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Reconstruction from Milnor K-theory modulo the characteristic

> 结果族 009：Function-field reconstruction from Milnor K-theory and Galois data　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在特征 \(p\) 的函数域上，一阶 Milnor K 群模 \(p\) 连同二阶 Steinberg 关系（Steinberg relations）足以重构域本身及其代数闭常数域：每个相容同构都是唯一域同构所诱导，只差一个 \(\mathbb F_p^\times\) 标量。不同于模 \(\ell\ne p\) 情形只能找回完备闭包，这里直接找回原来的域。

## 问题背景

Milnor K 理论（Milnor K-theory）把域的乘法连同加法导出的 Steinberg 关系编码成一族群 \(K^{\mathrm M}_n(F)\)，而"重构问题"问：这些群能在多大程度上反推域本身，其同构是否都来自域同构？这类问题属于 Bogomolov 学派的几何重构纲领：Bogomolov–Tschinkel（2009）在特征零从 Milnor K 环重构函数域，Cadoret–Pirutka（2021）推广到完美域上的正则扩张；Topaz（2016、2023）对与特征互素的 \(\ell\) 证明模 \(\ell\) 数据可重构完备闭包（perfect closure），但需超越次数（transcendence degree）至少 5 及额外输入。而在约去特征本身（\(\ell=p\)）的情形，此前没有仅从 \(V_F=F^\times/(F^\times)^p\) 与 Steinberg 关系出发、不借助有理子群或代数相关性数据的重构定理——本文补上的正是这块缺口。

## 主要结果

设 \(K/k\)、\(L/l\) 为代数闭域上有限生成的扩张，特征 \(p\)，超越次数均至少 2。记 \(V_F=F^\times/(F^\times)^p=K^{\mathrm M}_1(F)/p\)（加法记号），\(R_F\subset V_F\otimes_{\mathbb F_p}V_F\) 为由 \([f]\otimes[1-f]\) 张成的 Steinberg 关系子空间，商 \(W_F=(V_F\otimes V_F)/R_F\) 即 \(K^{\mathrm M}_2(F)/p\)。称 \(\mathbb F_p\)-线性同构 \(\Theta:V_K\to V_L\) 相容（compatible），若 \((\Theta\otimes\Theta)(R_K)=R_L\)。主定理断言典范映射

\[\Isom(K,k;L,l)\longrightarrow\Isom_{\mathrm M}(V_K,V_L)/\mathbb F_p^\times\]

是双射。换言之：数据 \((V_F,R_F)\)——等价地，\(K^{\mathrm M}_1/p\)、\(K^{\mathrm M}_2/p\) 及其乘法配对——确定域 \(F\) 及其指定常数域；每个相容 \(\Theta\) 等于唯一域同构 \(\alpha\) 的诱导 \(\alpha_*\) 乘以一个非零标量，且 \(\alpha\) 自动把 \(k\) 映到 \(l\)。此处没有 Frobenius 歧义：Frobenius 映射在 \(V_F\) 上诱导零映射，论文注记对此作了澄清。

## 证明思路

先换视角，把不变量看成射影几何。因 \((F^\times)^p=(F^p)^\times\)，类 \([f]\) 恰是 \(F\) 在 \(C=F^p\) 上的一维子空间 \(Cf\)，故 \(V_F\) 的底层集合就是射影空间 \(\mathbb P_C(F)\) 的点集，群运算 \([f]+[g]=[fg]\) 则另行记录乘法。论文先证 \([F:C]=p^{\trdeg(F/\kappa)}\) 有限（对 \(p\)-单项式基计数并作塔式消去），于是超越次数至少 2 时维数不小于 \(p^2\ge4\)，射影几何论证有了立足点。

再提取零符号的域论含义：若 \(s\notin F^p\) 且 \(\{s,t\}_F=0\)，则 \(t\in F^p(s)\)。证法是把 \(p\)-无关对扩充成 \(p\)-基（p-basis），取交换的 Euler 导子（Euler derivation），用对数导数搭配出双线性型，直接验证它杀死 Steinberg 关系、却在无关对上取值 1。这只是 Bloch–Gabber–Kato 定理的坐标化影子，但完全初等。

然而 \(F^p(s)\) 未必是二维子空间，要得到射影直线 \(C+Cx\) 须作幂次修正。关键的交命题：对 \(p\)-无关的 \(X,Y\) 与非单项式的 \(U\in C(X)^\times\)、\(V\in C(Y)^\times\)，若乘法平移 \(X\,C(Y/X)^\times\) 与 \(U\,C(V/U)^\times\) 相交，则存在唯一的 \(1\le n<p\) 使 \(U^n\in C+CX^n\) 且 \(V^n\in C+CY^n\)。证明构造两个导子分别杀死交中元素的两种表达，比较其特征坐标得 \(A_X=c_XX^m\)、\(A_Y=c_YY^m\) 共享指数 \(m\)，再以 \(n=p-m\) 解对数导数方程完成"积分"。

接着把 Steinberg 关系变成交。在源空间取仿射构型 \(u=x+a\)、\(v=y+b\)、\(z=bx-ay=bu-av\)，得四个零符号；经 \(\Theta\) 传送并由前一步得 \(Z\in X\,C(Y/X)\cap U\,C(V/U)\)，交命题遂给出局部修正指数。由该指数的唯一性沿一张连通图（任两点路径长不超过 2）传播，得到统一标量 \(n\) 使 \(\Psi=n\Theta\) 把直线映入直线；对逆映射重复论证，并用"非平凡标量不保直线"的二项式系数引理，推出 \(\Psi\) 把直线映满直线且 \(n\) 唯一。

最后从直线回到域。论文自含地证明射影几何基本定理（fundamental theorem of projective geometry）：维数至少 3 时保直线的双射来自唯一的半线性提升，得到加性双射 \(S:K\to L\) 与域同构 \(\sigma:K^p\to L^p\)；群律迫使 \(w\mapsto S(fw)\) 与 \(w\mapsto S(f)S(w)\) 诱导同一射影映射且在 \(1\) 处相等，由唯一性二者相等，故 \(S\) 保乘法、是域同构。再用 Eisenstein 判别法证 \(\bigcap_{m\ge1}F^{p^m}=\kappa\)，从而 \(S(k)=l\)；定理的单射性最后仍调用标量引理收尾。

## 可信度与备注

本篇与同族姊妹篇互相支撑：模 \(\ell\)（\(\ell\ne p\)）一篇只能重构完备闭包及其常数域，本篇在模特征情形直接重构原域，两者恰好覆盖两种约化；第三篇则从 pro-\(\ell\) Galois 数据证明 Bogomolov–Pop 重构。三篇均无 Lean 形式化证明；论文对交命题与射影提升定理均给出完整初等证明，但按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
