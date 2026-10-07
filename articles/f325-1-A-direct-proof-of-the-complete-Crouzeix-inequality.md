---
layout: default
title: "A direct proof of the complete Crouzeix inequality"
family: "325"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A direct proof of the complete Crouzeix inequality

> 结果族 325：The complete Crouzeix conjecture　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文直接证明：对任意复方阵 `@@M@@A@@` 与任意矩阵系数多项式 `@@M@@P@@`，恒有 `@@M@@\|P[A]\|\le 2\max_{z\in W(A)}\|P(z)\|@@`，其中 `@@M@@W(A)@@` 为数值域；常数 2 达到最优，且与基维数、系数维数、次数全部无关——完整版 Crouzeix 猜想的矩阵形式就此解决。

## 问题背景

矩阵的数值域（numerical range）`@@M@@W(A)=\{u^*Au:\ u^*u=1\}@@` 是由 Toeplitz–Hausdorff 定理刻画的紧凸集，总包含谱。正规矩阵靠谱定理就能控制多项式取值，非正规矩阵却不行：非零幂零矩阵的谱是 `@@M@@\{0\}@@`，范数却可达 2。数值域保留了足够的非正规性信息，因而成为给出普适界的自然控制集。Crouzeix 于 2004 年提出以 `@@M@@W(A)@@` 为控制集、常数取 2 的猜想，2007 年先证得普适界 11.08；Delyon–Delyon 的正边界表示与 Crouzeix–Palencia 的正双层位势（double-layer potential）方法把完整界推进到 `@@M@@1+\sqrt2@@`，Badea–Crouzeix–Delyon 又对 `@@M@@2\times 2@@` 基矩阵得到完整的常数 2。2026 年 Jin、Lorist–Schwenninger、Luo 相继给出标量证明，Åhag–Czyż–Virtanen 证明了基维数至多 3 的完整情形。长期卡点在于：标量证明里的交换性论证经不起矩阵系数的放大（amplification），因为系数矩阵不必交换。

## 主要结果

定理 1.1：对任意正整数 `@@M@@n,m@@`、任意 `@@M@@A\in M_n(\mathbb C)@@`、任意次数 `@@M@@d@@` 及任意 `@@M@@P(z)=\sum_{k=0}^d B_kz^k@@`（`@@M@@B_k\in M_m(\mathbb C)@@`），记 `@@M@@P[A]=\sum_{k=0}^d A^k\otimes B_k@@`，则 `@@M@@\|P[A]\|\le 2\max_{z\in W(A)}\|P(z)\|@@`。常数 2 在所有 `@@M@@n,m,d@@` 上不能一致改进；数值域退化为点或线段的矩阵同样被覆盖。"完整"（complete）指该界对系数维数 `@@M@@m@@` 一致成立——这恰是 `@@M@@W(A)@@` 构成完全 2-谱集（complete 2-spectral set）的断言，比标量版本强得多。

## 证明思路

先把 `@@M@@W(A)@@` 严格放入一个边界为正则实解析 Jordan 曲线的有界凸域 `@@M@@\Omega@@`，用外部共形映射（exterior conformal map）`@@M@@h@@` 将 `@@M@@\partial\Omega@@` 参数化为单位圆，并把 Cauchy 核在无穷远处展开，得到 Faber 多项式（Faber polynomials）`@@M@@b_k@@`。第一步建立系数定理：边界值 `@@M@@b_k\circ h@@` 等于 `@@M@@\mu^k@@` 加上纯负频率修正，混合系数恰为微分化的 Grunsky 系数（Grunsky coefficients）；由它们合成的核 `@@M@@K=1+s+\bar s@@` 非负，且对每个变量的圆周积分均为 1。这两条边缘恒等式使"正频率到负频率"的映射成为 `@@M@@L^2@@` 压缩，从而夹住系数范数：`@@M@@\sum_k\|C_k\|_{HS}^2\le\int_{\mathbb T}\|G\circ h\|_{HS}^2\,d\tau\le\|C_0\|_{HS}^2+2\sum_{k\ge1}\|C_k\|_{HS}^2@@`。这一不等式把"边界上函数有多大"翻译成"系数有多大"，非零次系数所带的权重 2 正是最终常数 2 的来源。

随后对目标多项式 `@@M@@F@@`（设边界算子范数至多 1）取 `@@M@@F[A]@@` 的一对单位顶部奇异向量（top singular vectors）`@@M@@x,y@@`，用预解式（resolvent）`@@M@@R(\lambda)=\lambda h'(\lambda)(h(\lambda)I-A)^{-1}=\sum_k b_k(A)\lambda^{-k}@@` 生成系数泛函；数值域条件经支撑半平面不等式导出 `@@M@@R+R^*\succeq 0@@`，即 Delyon–Delyon 与 Crouzeix–Palencia 一脉相承的正双层位势。本文的关键新招是保序检验：既然系数矩阵不必交换，就把检验多项式 `@@M@@G@@` 分别放在 `@@M@@F@@` 的左侧与右侧，得 `@@M@@y^*(FG)[A]x=\gamma\,x^*G[A]x@@` 与 `@@M@@y^*(GF)[A]x=\gamma\,y^*G[A]y@@`，两条链各自使用相应乘法顺序的 Hilbert–Schmidt 乘法界；再对偶地选取检验系数，得到两个对角泛函的加权范数上界，其权重与对角压缩场的 Fourier 平方范数恰好互为倒数配对。最后把 `@@M@@R+R^*@@` 压缩成 `@@M@@2\times 2@@` 正块 `@@M@@\Delta\succeq 0@@`，正性蕴含交叉场范数受对角场控制，与 Parseval 计算合并得 `@@M@@2a^2\le 8a^2/\gamma^2@@`，即 `@@M@@\gamma\le 2@@`。收尾时用指数型支撑函数构造的解析凸邻域序列收缩到任意紧凸数值域，并附 Toeplitz–Hausdorff 凸性的简短证明；`@@M@@A=\begin{pmatrix}0&2\\0&0\end{pmatrix}@@` 与 `@@M@@P(z)=z@@` 表明常数 2 不可再小。

## 可信度与备注

本文主结果已 Lean 形式化。同族姊妹篇《The complete Crouzeix theorem》以"最优相似＋公共正边界表示"的结构路线另证同一不等式：两文共享外部核与预解式正性这套解析内核，但证明路径各自独立完整，互为印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已通过形式化验证，可信度相应更高。

{% endraw %}
