---
layout: default
title: "Strict hot spots and absence of interior critical points on smooth simply connected planar domains"
family: "369"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Strict hot spots and absence of interior critical points on smooth simply connected planar domains

> 结果族 369：The hot spots conjecture for simply connected planar domains　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Burdzy 单连通平面 hot spots 猜想的强形式：光滑有界单连通平面区域上，第一正 Neumann 特征值的任一非零特征函数在区域内部梯度处处非零，全部全局最大、最小值都落在边界上，特征值多重时同样成立。

## 问题背景

hot spots 猜想源自 Rauch（1975）对绝热边界热流的讨论：边界绝热的平板长时间导热后，最热点与最冷点是否都贴到边界上？其谱表述是：第一正 Neumann 特征值（first positive Neumann eigenvalue）的特征函数（eigenfunction）的极值是否只能在边界取得。Bañuelos 与 Burdzy（1999）区分了严格与非严格、"每个特征函数"与"存在一个特征函数"等版本——特征值有多重性（multiplicity）时它们并不等价。拓扑在此举足轻重：Burdzy–Werner（1999）造出带两个洞的反例，Burdzy（2005）进一步表明一个洞即可让两个极值同时落入内部，故单连通（simply connected）假设不可去，他也在同文 Conjecture 1.2(ii) 明确表述了单连通平面猜想。此前的正面结果均需附加几何条件：正交对称凸域（Jerison–Nadirashvili）、lip 域（Atar–Burdzy）、谱–直径条件（Miyamoto）、各类三角形（Siudeja、Judge–Mondal、Chen–Gui–Yao）。一般光滑单连通区域上的猜想长期悬置。

## 主要结果

设 \(\Omega\subset\R^2\) 为有界单连通开集、边界 \(C^\infty\)，\(\mu=\mu_1(\Omega)\) 为第一正 Neumann 特征值（只计正特征值），\(\V\) 为对应特征空间（eigenspace）。主定理（Theorem 1.1）：每个 \(0\ne u\in\V\) 在内部处处 \(\nabla u\ne0\)；特别地，对一切内点 \(x\)，

\[\min_{y\in\partial\Omega}u(y)<u(x)<\max_{y\in\partial\Omega}u(y).\]

三点值得强调：其一，不假设任何凸性或对称性；其二，结论对特征空间的每个成员成立，特征值可以多重（文中并完整复证 Nadirashvili 多重性上界 \(\dim\V\le2\)，Proposition 2.5）；其三，"梯度非零"强于"极值在边界"——它同时排除了内部的鞍点（saddle point）型临界点（critical point），这正是标题中"严格"之意。

## 证明思路

证明把"极值在哪"改写为"梯度何时为零"，骨架四步。

先立向量变分原理（variational principle）。Neumann 条件使特征函数的梯度在边界上切向，于是考察切向量场 \(X\) 的散度–旋度（divergence–curl）能量：Rohleder 原理（Proposition 3.1，文中含等号情形的推导）给出 \(\Q(X)\ge\mu\int|X|^2\)，等号恰当 \(X=\nabla v\)、\(v\in\V\)——第一特征函数的梯度恰是某个非负二次型的零空间。难点在于：\(u\) 的两个笛卡尔导数各自满足同一 Helmholtz 方程，但边界值符号失控，单独哪个分量都无从下手，只能把两者捆绑、用切向边界条件。这一步的地基是谱隙 \(\mu<\lambda_D\)（Friedlander–Filonov 平面波比较的严格形式，文中自足证明）。

再经共形映射（conformal map）\(\Phi:\D\to\Omega\) 拉回单位圆盘，特征方程化为带位势 \(q=\mu|\Phi'|^2\) 的方程，而谱隙恰转为次临界不等式 \(\|\psi\|_{L^2(q)}^2\le d\int_\D|\nabla\psi|^2\)（\(d=\mu/\lambda_D<1\)）。在圆盘上构造边界核 \(N\) 与内部赋值核 \(K\)，把能量写成圆周上的双积分，得乘子恒等式（multiplier identity，Proposition 4.4）：对特征函数的边界梯度 \(g\) 与圆周上实值 Lipschitz 函数 \(b\)，

\[E(bg)=\tfrac12\iint N(s,t)(b(s)-b(t))^2g(s)\cdot g(t)\,\dd s\,\dd t.\]

但 \(g(s)\cdot g(t)\) 的符号无法控制，此式不能直接给出正性——这是必须绕过的坎。

绕行核心是倒数核定理（Theorem 5.1）：\(D_p(s,t)=K(p,s)K(p,t)/N(s,t)\)（对角置零）是条件半负定（conditionally negative semidefinite）核。证明先正则化圆盘格林函数（Green function），使逐项取倒数后的有限矩阵至多含一个正特征值（性质 (P)，思想源于 McCullough–Quiggin 对完全 Nevanlinna–Pick 核的刻画）；继而证明沿核矩阵某列的秩一更新保持 (P)，恰好对应格林预解式（resolvent）在求积（quadrature）节点上的链求和；最后经四重单调极限（求积加细、\(\epsilon\downarrow0\)、径向逼边、放开紧支撑截断）传到奇异核，"先取边界极限、后撤截断"的次序避免了把 Poisson 核误当作 \(L^2\) 函数。当 \(q=0\) 时 \(D_p\) 退化为圆盘自同构下的弦距离平方，可见定理是经典事实的深层推广。

最后收口：Schoenberg 的平方距离对应给出单射 Lipschitz 映射 \(b:\Sone\to\HH\)，使 \(\|b(s)-b(t)\|^2=D_p(s,t)\)。对每个坐标 \(b_j\) 用乘子恒等式再求和，因子 \(N\) 被精确消去，得 \(\sum_jE(b_jg)=\tfrac12|\nabla u(\Phi(p))|^2\)。若 \(\Phi(p)\) 是临界点，右端为零，而每项非负，故每个 \(b_jg\) 都是某个第一特征函数的边界梯度。由于圆周的连续单射像不共线，可取两坐标使 \(1,b_j,b_k\) 线性无关，从而凑出三个线性无关的特征函数梯度，与 \(\dim\V\le2\) 矛盾；若 \(g\) 在某段弧上恒为零，则改用边界唯一性：取线性组合使其在该弧上 Dirichlet 与 Neumann 迹同时为零，作 Filonov 式零延拓，再由解析延拓（analytic continuation）逼出其恒为零，亦矛盾。两种情形皆不可能，故梯度在内部处处非零，全局极值只能落在边界。

## 可信度与备注

本篇手稿的任务字段标注为未形式化，宜按"暂无形式化证明，请以社区核验为准"对待；族 369 的元信息虽附有 Lean 文档链接（lean/docs/369.md），其覆盖范围请读者自行核对。论文自足程度较高：谱隙、共形映射、多重性上界、向量变分原理、核定理等专门环节均在文中给出完整证明，外部输入限于 Filonov、Rohleder、Nadirashvili、McCullough–Quiggin、Schoenberg 等已发表结果。本批仅此一篇，即族 369 的主文；按 OpenAI 官方声明，未经形式化的结果可能存在问题，引用前请以社区核验为准。

{% endraw %}
