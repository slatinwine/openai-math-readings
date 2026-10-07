---
layout: default
title: "The complete Crouzeix theorem: optimal similarity and a common positive boundary representation"
family: "325"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The complete Crouzeix theorem: optimal similarity and a common positive boundary representation

> 结果族 325：The complete Crouzeix conjecture　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文以"最优相似＋公共正边界密度"的结构路线证明：任意复 Hilbert 空间上的有界算子 \(A\) 与任意矩阵值多项式 \(P\) 满足 \(\|P[A]\|\le 2\sup_{z\in W(A)}\|P(z)\|\)，数值域闭包是完全 2-谱集，常数 2 最优——完整 Crouzeix 猜想成立。

## 问题背景

Crouzeix 猜想自 2004 年提出后，普适常数从 11.08（Crouzeix，2007）经正双层位势（double-layer potential）方法压缩到 \(1+\sqrt2\)（Crouzeix–Palencia，2017）。本文切入的是一个更结构性的问题：能否为给定矩阵选定一次内积变换（相似）与一个正边界密度，使所有系数维数、所有解析函数的矩阵值求值都被统一表示和控制？这一方向有经典坐标可依：Paulsen 相似定理把最优条件数（condition number）与完全有界范数等同，Arveson 膨胀定理把完全压缩性与正规边界膨胀相连；Badea–Crouzeix–Delyon 曾在 \(2\times 2\) 椭圆数值域情形构造出条件数至多 2 的相似。此前的卡点有二：一般维数下最优度量常数 \(\kappa\le 2\) 难以落实；表示必须对一切系数维数与一切解析函数同时成立，不能逐个函数证明。

## 主要结果

设 \(\Omega\) 为包含 \(W(A)\) 的可容许域（admissible，即具正则实解析 Jordan 边界的有界凸开集），\(f:\Omega\to\mathbb D\) 为内部共形坐标，\(T=f(A)\)。其一（最优度量定理）：优化问题 \(\kappa^2=\min\{\tau:\ I\preceq H\preceq\tau I,\ T^*HT\preceq H\}\) 严格可行且最小值可达，\(1\le\kappa\le 2\)；对最小化度量取 \(S=H^{1/2}\)、\(A'=SAS^{-1}\)，则 \(D=Sf(A)S^{-1}\) 是压缩且谱半径（spectral radius）小于 1，而 \(\|S\|\|S^{-1}\|=\kappa\) 恰为把 \(T\) 相似成压缩的最小条件数。其二（公共正表示定理）：存在同一个连续正密度 \(\Lambda(t)\succeq 0\)、\(\int_{\mathbb T}\Lambda\,d\sigma=I\)，使得对每个系数维数 \(m\) 与每个在 \(\overline\Omega\) 邻近全纯的矩阵值函数 \(v\)，有 \(v[A']=\int_{\mathbb T}\Lambda(t)\otimes v(G(t))\,d\sigma\) 且 \(\|v[A]\|\le\kappa\max_{\overline\Omega}\|v\|\)；同一组 \(S,\Lambda,\kappa\) 通吃所有 \(m\) 与 \(v\)。推论进一步给出任意（不必可分）Hilbert 空间上有界算子的完整不等式：\(\overline{W(A)}\) 是完全 2-谱集（complete 2-spectral set），常数 2 一致最优。

## 证明思路

先解度量问题：Stein 型级数 \(H_0=\sum_j T^{*j}T^j\) 满足 \(H_0-T^*H_0T=I\)，提供严格可行的见证，有限维紧性保证最小值可达；并证 \(\kappa\) 恰为把 \(T\) 相似成压缩的最小条件数。再构造公共密度：Delyon–Delyon 正表示给出 \(\Phi_D\)，乘以边界换坐标的正 Jacobian 得 \(\Lambda\)；映射 \(b\mapsto(\Lambda^{1/2}\otimes I)b\) 是到边界 \(L^2\) 的等距嵌入，求值 \(v[A']\) 成为"嵌入—乘以 \(v(G(t))\)—取伴随"的公共压缩，且这一步在估计 \(\kappa\) 之前即告完成。接着反设 \(\kappa>1\)：有限维凸分离（convex separation）给出支撑于 \(H\) 的 \(\kappa^2\) 与 \(1\) 特征空间上的正矩阵 \(X_0,Y_0\) 及平衡式 \(X_0-Y_0=Z_0-TZ_0T^*\)；取平方因子得 \(SX=\kappa X\)、\(SY=Y\)、\(X^*Y=0\)，平衡式经酉实现（unitary realization）造出在闭圆盘上压缩的有理函数 \(F_{\mathbb D}\)，满足 \(F_{\mathbb D}[D]x=y\)。然后让两套正密度系统对撞：等距嵌入中等号成立迫使 \(y_\Lambda=(I\otimes F)x_\Lambda\) 逐点成立；对基空间取部分迹（partial trace）得密度 \(p,q,r\)，两种乘法顺序的保序关系 \(p=F^*r\)、\(q=rF^*\) 并存，且交叉密度的矩阵均值整体为零（\(r_0=0\)），恰好提供了所需的 Fourier 正交性；另一方面，原始矩阵的预解式正性 \(E_A\succeq 0\) 给出第二个正块，其元素是第一套密度经 Cauchy 投影的像，交叉项按乘法顺序分别带因子 \(\kappa\) 与 \(\kappa^{-1}\)。最后的决定性比较：令 \(g=\mathcal C^\dagger r\ne 0\)，\(r_0=0\) 把两个投影分支分入正、负频率子空间，故交叉范数平方至少 \(\kappa^2\|g\|_2^2\)；对两种顺序分开使用加权投影估计，得对角范数平方各不超过 \(4\|g\|_2^2\)；正块不等式 \(\mathrm{tr}(\Delta J\Delta J)\ge 0\) 联立即得 \(\kappa\le 2\)。收尾三步：高斯光滑化构造解析凸外逼近以覆盖点、线段数值域；有限压缩论证（压缩到 \(\mathrm{span}\{A^k\xi_j\}\)，其数值域落入原数值域）把不等式搬到任意 Hilbert 空间而无需可分性；Runge 逼近再把结论扩成 \(\overline{W(A)}\) 上对全纯矩阵值函数成立的完全 2-谱集断言。

## 可信度与备注

本文主结果已 Lean 形式化。姊妹篇《A direct proof of the complete Crouzeix inequality》从待估多项式的奇异向量出发直接证明同一不等式，与本文共享外部核与预解式计算这套解析内核，但两文证明路径彼此独立、各自完整，结论互为印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已完成形式化验证。

{% endraw %}
