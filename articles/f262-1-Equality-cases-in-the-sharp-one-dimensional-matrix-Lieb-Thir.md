---
layout: default
title: "Equality cases in the sharp one-dimensional matrix Lieb–Thirring inequality"
family: "262"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Equality cases in the sharp one-dimensional matrix Lieb–Thirring inequality

> 结果族 262：Sharp finite-matrix Lieb–Thirring inequalities and all equality cases　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对 \(1/2<\gamma<3/2\) 与任意有限矩阵维数，本文把一维矩阵 Lieb–Thirring 不等式（Lieb–Thirring inequality）的取等势完全分类：在某个不随位置变化的酉基下，取等势恰是有限个标量 \(\mathrm{sech}^2\) 孤子的直和加零通道，各孤子尺度与中心彼此独立，每个非零通道恰含一个束缚态，故极值势至多有 \(m\) 个负特征值。

## 问题背景

Lieb–Thirring 不等式把薛定谔算子（Schrödinger operator）\(H_W=-d^2/dx^2-W\) 的负特征值矩与势的积分幂作比较；等号问题追问：势必须怎样组织，才能让束缚能达到最优。一维标量单束缚态优化子具有双曲正割轮廓，其显式形式可追溯到 Keller 1961 年的单态变分问题与 Lieb–Thirring 1975–76 年关于费米子动能与物质稳定性的工作。当波函数有多个分量时，势成为矩阵，若干标量轮廓可以占据相互正交的内部通道；悬而未决的是，等号是否还允许随位置旋转的通道，或同一通道内多个束缚态的相互作用。端点对照令人警醒：Frank–Gontier–Lewin 已证明在 \(\gamma=3/2\) 处标量优化子是 KdV 多孤子（multisoliton），同一标量通道可容纳多个束缚态。本文证明：在整个开区间上，等号情形一律是固定基下的独立标量轮廓。

## 主要结果

设 \(m\ge 1\)、\(1/2<\gamma<3/2\)、\(p=\gamma+1/2\)，\(W:\mathbb R\to\mathbb C^{m\times m}\) 可测、Hermitian、半正定，且 \(\int_{\mathbb R}\operatorname{tr}(W^p)\,dx<\infty\)。记 \(\operatorname{Tr}(H_W)_-^\gamma=\sum_{\lambda_j<0}|\lambda_j|^\gamma\)（计入重数）。定理断言

\[\operatorname{Tr}(H_W)_-^\gamma\le C_\gamma\int_{\mathbb R}\operatorname{tr}(W^p),\qquad C_\gamma=\Big(\frac{\gamma-1/2}{\gamma+1/2}\Big)^{\gamma-1/2}\frac{\Gamma(\gamma+1)}{\sqrt\pi\,\Gamma(\gamma+3/2)}，\]

且等号成立当且仅当存在 \(k\in\{0,\dots,m\}\)、常值酉矩阵（unitary matrix）\(U\)、正数 \(a_1,\dots,a_k\) 与实数 \(x_1,\dots,x_k\)，使得几乎处处

\[W(x)=U\,\operatorname{diag}\big(w_1,\dots,w_k,0,\dots,0\big)\,U^*,\qquad w_j(x)=(r+1)\,a_j^2\,\mathrm{sech}^2\!\big(ra_j(x-x_j)\big)，\]

其中 \(r=(\gamma-1/2)^{-1}\)。各非零通道恰有一个负特征值 \(-a_j^2\)，于是极值势的负特征值个数（计重数）至多为 \(m\)；\(k=0\) 对应零势。分类依赖严格不等式 \(r>1\)，故仅对开区间断言。

## 证明思路

证明分四步。先在矩阵姊妹篇的作用方法（action method）之上强化下界：除平方项 \(\|A'-BA\|_{\mathrm{HS}}^2\) 外，还保留同时控制换位子（commutator）\([B,K^2]\) 与余项 \(K^2-B^2-(AA^{\mathsf T})^r\) 的定量亏量，其系数只依赖最大束缚能与指数、与试验函数个数无关——这一一致性必不可少，因为事先并不知道极值势只有有限个负特征值；所需的两个非负平方来自积分迹恒等式（integrated trace identity）。再证固定列数下的紧性：试验列表增长时 \(A\) 的行数增加但列数固定为 \(m\)，密度 \(AA^{\mathsf T}\) 的秩至多 \(m\)；保留亏量用尾部的小束缚能控制尾行，于是即使负特征值有无穷多个，也能得到强逐点收敛，并在极限中提取精确代数关系，把能量不同的行分开；极限关系还附带给出极值势的连续代表元，各块矩阵为 \(C^2\)，并满足行特征函数方程 \(G_\alpha''=\alpha^2G_\alpha-G_\alpha W\)。然后证通道固定并求解：由 \(G_\alpha'=B_\alpha G_\alpha\) 与算子范数界，经 Gronwall 不等式知各能量块的核空间与位置无关，不同能量的行空间相互正交，非零方向至多 \(m\) 个；在每个非零块上，\(B_0=D'D^{-1}\) 满足矩阵 Riccati 方程 \(B_0'=r(B_0^2-\alpha^2 I)\)，在一点对角化后由常微分方程解的唯一性始终保持对角，标量解为 \(b_j(x)=-\alpha\tanh\big(r\alpha(x-y_j)\big)\)，代回 \(q(\alpha^2-b_j^2)\) 即得 \(\mathrm{sech}^2\) 轮廓。复 Hermitian 情形先实化为 \(W\oplus\overline W\)（两边各量同时加倍，等号保持），用实情形结论加投影论证还原。最后验证充分性：取 \(w=a\tanh\big(ra(x-x_0)\big)\)、\(Q=\partial_x+w\)，一阶分解给出 \(Q^*Q=H+a^2\) 与 \(QQ^*\ge a^2\)（用到 \(r>1\)），而 \(\ker Q\) 一维，故 \(-a^2\) 是唯一的负特征值；beta 积分算得 \(\operatorname{Tr}(H)_-^\gamma=a^{2\gamma}=C_\gamma\int V^p\)，直和与酉共轭保持等号。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。结果族中标量常数篇的主结果已 Lean 形式化，矩阵不等式篇则给出本文所分类的这条不等式，三篇共享同一套作用方法、互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文与端点 \(\gamma=3/2\) 处 KdV 多孤子结构的鲜明对比，尤其值得专家细察。

{% endraw %}
