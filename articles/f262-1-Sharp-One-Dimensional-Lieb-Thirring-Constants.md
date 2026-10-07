---
layout: default
title: "Sharp one-dimensional Lieb–Thirring constants"
family: "262"
discipline: "Mathematical physics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Sharp one-dimensional Lieb–Thirring constants

> 结果族 262：Sharp finite-matrix Lieb–Thirring inequalities and all equality cases　·　学科：Mathematical physics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

一维标量 Lieb–Thirring 猜想在剩余区间 `@@M@@1/2<\gamma<3/2@@` 全部证实：最优常数是单束缚态常数 `@@M@@L^{(1)}_{\gamma,1}@@` 而非半经典常数，由显式 `@@M@@\mathrm{sech}^2@@` 孤子取到。至此该猜想的一维情形完全解决，且主结果已有 Lean 形式化证明。

## 问题背景

对 `@@M@@0\le W\in L^{\gamma+1/2}(\mathbb R)@@`，Lieb–Thirring 不等式断言 `@@M@@\operatorname{Tr}(H_{-W})_-^\gamma\le L_{\gamma,1}\int W^{\gamma+1/2}@@`，最优常数 `@@M@@L_{\gamma,1}@@` 有两个自然候选：半经典常数（semiclassical constant）`@@M@@L^{\mathrm{cl}}_{\gamma,1}@@` 与只保留最低特征值时的最优常数 `@@M@@L^{(1)}_{\gamma,1}@@`。Lieb 与 Thirring 在 1975–76 年关于费米子动能估计与物质稳定性（stability of matter）的工作中引入这类不等式，并猜想 `@@M@@1/2<\gamma<3/2@@` 时后者正确、`@@M@@\gamma\ge 3/2@@` 时前者正确。端点早已知晓：`@@M@@\gamma=3/2@@` 的尖锐值 `@@M@@3/16@@` 来自 KdV 方程的反散射迹恒等式（trace identity）；Aizenman–Lieb 的矩提升单调性把半经典尖锐性推到一切更大指数；`@@M@@\gamma=1/2@@` 由 Weidl 的有限性与 Hundertmark–Lieb–Thomas 的尖锐值 `@@M@@1/2@@` 解决；Read–Schulz 又证明了 `@@M@@\gamma=1@@`。此前一般情形只有 `@@M@@L_{\gamma,1}\le 2L^{\mathrm{cl}}_{\gamma,1}@@` 这类带因子二的界，数值实验支持猜想却给不出对所有正交族的一致界——这正是本文要跨越的障碍。

## 主要结果

定理：对每个 `@@M@@1/2<\gamma<3/2@@` 与每个非负 `@@M@@W\in L^{\gamma+1/2}(\mathbb R)@@`，

`@@M@@D\operatorname{Tr}(H_{-W})_-^\gamma\ \le\ 2\Big(\frac{\gamma-1/2}{\gamma+1/2}\Big)^{\gamma-1/2}L^{\mathrm{cl}}_{\gamma,1}\int_{\mathbb R}W^{\gamma+1/2}，@@`

该常数最优且等于 `@@M@@L^{(1)}_{\gamma,1}@@`；等号由 `@@M@@W(x)=(r+1)\,\mathrm{sech}^2(rx)@@`（`@@M@@r=(\gamma-1/2)^{-1}@@`）取到。经 beta 积分，该常数可等价地写作 `@@M@@C_\gamma=\big(\frac{\gamma-1/2}{\gamma+1/2}\big)^{\gamma-1/2}\frac{\Gamma(\gamma+1)}{\sqrt\pi\,\Gamma(\gamma+3/2)}@@`，与族内矩阵篇所用形式一致。估计对粗糙无界势、含无穷多个负特征值的情形一致成立，全部负特征值都计入和式。论文还给出符号势情形的相应推论。

## 证明思路

先建立一个与势无关的有限区间变分不等式——作用不等式（action inequality）：给定有界区间上 `@@M@@N@@` 个标准正交实函数 `@@M@@u_i@@` 与正数 `@@M@@k_i@@`，记 `@@M@@K=\operatorname{diag}(k_i)@@`，证明作用泛函 `@@M@@\mathcal E_K(a)=\int\big(|a'|^2+a^{\mathsf T}K^2a-|a|^{2+2/\sigma}\big)@@`（`@@M@@\sigma=\gamma-1/2@@`）在形如 `@@M@@a=Cu@@`、`@@M@@C@@` 下三角的函数类上的上确界不小于 `@@M@@\sum_i\int_{-k_i}^{k_i}(k_i^2-s^2)^\sigma\,ds@@`；难点在于对任意正交族同时保留各自的尺度 `@@M@@k_i@@`；下三角性的作用是让第 `@@M@@i@@` 行只由前 `@@M@@i@@` 个试验函数混合而成，从而使能量排序在后续谱估计中得以保留。再构造正则化矩阵场 `@@M@@M_\delta(B)@@`（对称矩阵到自身的映射）及其标量原语：当 `@@M@@B@@` 沿路径从 `@@M@@K@@` 变到 `@@M@@-K@@` 时，原语的改变量恰为所需的端点积分。解析核心是秩一比较（rank-one comparison）：`@@M@@M(B)=aa^{\mathsf T}@@` 蕴含 `@@M@@a^{\mathsf T}(K^2-B^2)a\ge|a|^{2q}@@`。其证明把 `@@M@@M(B)@@` 与一个只依赖 `@@M@@B@@` 的矩阵比较，利用预解式（resolvent）表示与均差（divided difference）给出的切不等式（Daleckii–Krein 型）：积分切映射是酉共轭的平均，再用迹单调性把这一平均移出比较。路径本身由模行符号的延拓论证选取：紧性与零行的排除使得 `@@M@@C@@` 失秩时仍能继续，商零集边界的奇偶性强制出现端点解；罚项分两步消除——先固定正则化令罚参数趋于零，再移除正则化。最后回到谱：取 `@@M@@u_i@@` 为 Dirichlet 特征函数（特征值 `@@M@@-k_i^2@@`，按 `@@M@@k_1\ge\cdots\ge k_N@@` 排序），下三角性配合特征函数方程把作用的二次部分控制为 `@@M@@\int W|a|^2@@`，一次标量最优化再把整个作用控制为 `@@M@@\int W^{1+\sigma}@@` 的常数倍；截断试验空间从有限区间过渡到全直线，有限部分和取极限穷尽全部负特征值。尖锐性由显式孤子的谱与 beta 积分直接验证。

## 可信度与备注

主结果已 Lean 形式化（官方发布的 Lean 文档对应结果族 262），这是本结果族的基石：矩阵势篇把同一作用方法推广到矩阵维数任意、逐点不对易的势，等号分类篇进一步分类全部取等势；两篇姊妹篇尚未形式化。按 OpenAI 官方声明，未经形式化的结果可能有问题，族内未形式化部分请以社区核验为准。

{% endraw %}
