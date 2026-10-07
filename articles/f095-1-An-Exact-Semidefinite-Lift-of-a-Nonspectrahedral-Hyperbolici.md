---
layout: default
title: "An Exact Semidefinite Lift of a Nonspectrahedral Hyperbolicity Cone"
family: "095"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An Exact Semidefinite Lift of a Nonspectrahedral Hyperbolicity Cone

> 结果族 095：Hyperbolicity cones without semidefinite lifts　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

为姊妹篇那个 23 变量的非谱面双曲锥构造了精确半定提升：`@@M@@100\times100@@` 齐次对称铅笔加 307 个辅助变量，覆盖含奇异边界点的整个闭锥——该锥不是谱面，却是谱面影子。

## 问题背景

谱面（spectrahedron）是有限仿射线性矩阵不等式 `@@M@@L(x)\succeq0@@` 的解集；谱面影子（spectrahedral shadow）是谱面的线性投影，等价于允许引入辅助变量的半定提升（semidefinite lift）。辅助变量可能让原本无表示的集合变得可表示，这正是广义 Lax 猜想与其"投影版"强弱之别的来源。围绕双曲锥（hyperbolicity cone）的表示问题，此前正面结果都依赖边界正则性：Netzer 与 Sanyal 证明边界光滑的双曲锥可提升，Scheiderer 近期在 Nash 光滑边界假设下给出二阶锥提升。本族的姊妹篇刚证明了一个 23 变量的显式双曲锥不是谱面，留下一个悬而未决的对照问题：允许辅助变量之后，它有没有精确提升？本文给出肯定回答，而且提升是显式、有界次代数的构造，对整个闭锥（包括退化点）精确成立，不需要取闭包。

## 主要结果

沿用姊妹篇的多项式：`@@M@@p(X,Z,y)=\det\big((\det X)Z-\Phi_y(\operatorname{adj}X)\big)@@`，其中 `@@M@@\Phi_y@@` 由 Choi–Lam 矩阵 `@@M@@Q(y)@@` 诱导，`@@M@@K=K(p,e)@@` 是它关于 `@@M@@e=(I_4,I_4,0)@@` 的闭双曲锥。主定理（Theorem 2.5）：存在固定矩阵 `@@M@@A_1,\ldots,A_{23},B_1,\ldots,B_{307}\in\Sym^{100}@@`，使得对每个点 `@@M@@x=(X,Z,y)@@` 都有
`@@M@@Dx\in K\quad\Longleftrightarrow\quad \exists v\in\R^{307}:\ \sum_{\nu=1}^{23}x_\nu A_\nu+\sum_{j=1}^{307}v_jB_j\succeq0 .@@`
等价在整个闭锥上成立，包括 `@@M@@X@@` 奇异的点；铅笔是齐次的、无常数项。作者强调尺寸只是显式上界，不声称极小。由于姊妹篇已证此锥在原始坐标下没有任何齐次半定表示（仿射表示对含原点的锥可自动齐次化），本文说明：它非谱面，但确是谱面影子。

## 证明思路

先做角切片。平面族 `@@M@@y=Y_\theta(\eta,\xi)=\eta(\cos\theta,\sin\theta,0)+\xi(0,0,1)@@` 覆盖整个 `@@M@@\R^3@@`；在每个平面上，Choi–Lam 矩阵 `@@M@@Q(y)@@` 有显式复 Gram 分解 `@@M@@F_\theta(\eta,\xi)=\eta U(\theta)+\xi V_0@@`，系数是 `@@M@@\theta@@` 的次数至多三的三角多项式（trigonometric polynomial）。由 Gram 列构造斜块 `@@M@@B(r)@@`，叠加得到恒等式 `@@M@@\sum_j B(r_j)^\top WB(r_j)=\Phi_{Y_\theta}(W)@@`，于是 20 阶齐次铅笔 `@@M@@L_\theta@@` 的行列式在切片上恰等于 `@@M@@p@@`；对称铅笔的特征值全实，这顺便重证了双曲性，而且 `@@M@@L_\theta\succeq0@@` 当且仅当切片点属于 `@@M@@K@@`——奇异 `@@M@@X@@` 的情形也一并成立。

再把角参数变成矩量条件。`@@M@@\theta@@` 是连续参数，本身不是有限线性矩阵不等式；作者转而使用矩方法（moment method）：提升变量取为 330 维空间 `@@M@@\mathcal E@@`（22 个切片变量的线性函数，系数为次数至多七的三角多项式）上的线性泛函 `@@M@@\Lambda@@`，要求它满足 23 个输出方程（`@@M@@\Lambda(\mathcal X)=X@@` 等）以及单个半定条件 `@@M@@H(\Lambda)\succeq0@@`——`@@M@@H@@` 是 `@@M@@100\times100@@` 的矩矩阵（moment matrix），元素为 `@@M@@\Lambda\big(f_af_b(L_\theta)_{ij}\big)@@`，`@@M@@f@@` 取遍 `@@M@@1,\cos\theta,\sin\theta,\cos2\theta,\sin2\theta@@`。正向容易：`@@M@@K@@` 中每点取一个合适的 `@@M@@\theta_0@@` 处的赋值泛函即为可行见证，即使 `@@M@@X@@` 奇异也无妨。

真正的难点在反向：可行泛函未必是某角度处的赋值，甚至未必来自任何测度，所以必须从 `@@M@@H(\Lambda)\succeq0@@` 直接榨出切片不等式。这里的关键新部件是"次数二匹配引理"（degree-two matching）：对任意（可以不定的）`@@M@@S\in\mathbb S^3@@` 与 `@@M@@(z_1,z_2)\ne(0,0)@@`，存在次数至多二的三角矩阵 `@@M@@C(\theta)@@`，其 Gram 矩阵恒为 `@@M@@Q(z)@@`、且配对 `@@M@@\langle F_\theta,C\rangle_S=\operatorname{tr}\big(SQ(Y_\theta(\eta,\xi),z)\big)@@` 关于 `@@M@@\eta,\xi@@` 线性。构造是用 `@@M@@2\times2@@` 西旋转 `@@M@@M(\theta)@@` 作用于固定因子：西性保住 Gram 矩阵，旋转把三次频率压制为一次谐波（核心是恒等式 `@@M@@w^3\kappa=w_0^2w@@`），再在单个角度处匹配函数值与一阶导数即可锁定配对。以 `@@M@@C@@` 的列拼出测试向量 `@@M@@q\in(\mathcal T_2)^{20}@@` 代入半定条件，角依赖被恒等式"配平"，得到一族标量不等式：对所有 `@@M@@u\in\R^4@@`、`@@M@@D\in\mathbb S^4@@`、`@@M@@z\in\R^3@@`，
`@@M@@Du^\top Zu+\operatorname{tr}\big(J_uDXDJ_u^\top Q(z)\big)-2\operatorname{tr}\big(J_uDJ_u^\top Q(y,z)\big)\ge0 .@@`
最后分况收网：`@@M@@X@@` 正定时取 `@@M@@D=X^{-1},z=y@@` 得 `@@M@@Z\succeq\Phi_y(X^{-1})@@`；`@@M@@X@@` 奇异时，取 `@@M@@D=tvv^\top@@`（`@@M@@v\in\ker X@@`）得值域条件 `@@M@@\operatorname{range}B_j\subseteq\operatorname{range}X@@`，取 `@@M@@D=X^\dagger@@` 得 `@@M@@Z\succeq\Phi_y(X^\dagger)=\sum_jB_j^\top X^\dagger B_j@@`；配方即可验证切片铅笔半正定，故点属于 `@@M@@K@@`。尺寸核算：`@@M@@\mathcal E@@` 有 `@@M@@22\times15=330@@` 个坐标，扣除 23 个输出方程恰余 307 个辅助变量，测试空间 `@@M@@5\times20=100@@` 给出铅笔尺寸。

## 可信度与备注

本文暂无形式化证明，按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。文章自足地重证了双曲性与切片刻画，仅在对比意义上引用姊妹篇的"非谱面"结论，两文合起来精确刻画了同一个锥：非谱面但谱面影子。族内另一篇高维构造则证明某些双曲锥连谱面影子都不是；三篇合观，恰好把 Lax 猜想谱系（谱面、影子、无提升）的三个层级各安放到一个具体例子上。文中明确声明尺寸非极小，未做最小性讨论。

{% endraw %}
