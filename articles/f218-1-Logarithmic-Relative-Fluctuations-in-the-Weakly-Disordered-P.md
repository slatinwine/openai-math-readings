---
layout: default
title: "Logarithmic Relative Fluctuations in the Weakly Disordered Planar Ising Model"
family: "218"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Logarithmic Relative Fluctuations in the Weakly Disordered Planar Ising Model

> 结果族 218：Conformal universality for weakly interacting and random-bond Ising models　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对键强度为独立等概率 `@@M@@1\pm\varepsilon@@` 的方格 Ising 模型，在假设一组确定性临界参考估计的前提下，证明了固定环境（quenched）临界自旋关联的相对二阶矩按 `@@M@@(\log r)^{1/4+o(1)}@@` 增长——这正是物理学家 Shankar 在 1987 年预言的指数，也严格确认了二维无序的"边缘"本性。

## 问题背景

纯二维 Ising 模型的比热指数为零，恰是 Harris 判据无法裁决的边缘情形。Dotsenko–Dotsenko 由此预测随机模型比热有双对数奇性；Shalaev 论证主导临界指数不变；Shankar 与 Ludwig 进一步算出对数修正，其中 Shankar 预言自旋关联的二阶矩带因子 `@@M@@(\log r)^{1/4}@@`。这些重整化群计算针对热力学量与关联函数，从未有过对"归一化 quenched 关联"（先在固定环境中用各自的 Gibbs 归一化算出关联，再对键取矩）在物理临界点处的严格推导。困难在于：无序只在矩意义下小、并不一致小，且临界点本身要先被识别。此前 Chayes–Shtengel 在自对偶分布处证明了零磁化与代数下界，但不能排除临界区间。

## 主要结果

模型取 `@@M@@\xi_e=\pm1@@` 等概率、`@@M@@J_e=1+\varepsilon\xi_e@@`，`@@M@@\varepsilon@@` 固定。临界点 `@@M@@\beta_c(\varepsilon)@@` 由自发磁化阈值定义；文中证明它是方程 `@@M@@\sinh(2\beta(1-\varepsilon))\sinh(2\beta(1+\varepsilon))=1@@` 的唯一正解，即分布自对偶点。对自由边界的无穷体积关联 `@@M@@C_{\varepsilon,\omega}(r)=\lim_n\langle\sigma_0\sigma_{(r,0)}\rangle^{\mathrm f}_{n,\beta_c(\varepsilon),\omega}@@` 与相对二阶矩（relative second moment）`@@M@@R_\varepsilon(r)=\E[C^2]/\E[C]^2@@`，定理断言：存在 `@@M@@\varepsilon_0>0@@`，使每个固定 `@@M@@\varepsilon\in(0,\varepsilon_0)@@` 满足 `@@M@@\log R_\varepsilon(r)/\log\log r\to1/4@@`。极限次序至关重要：先固定 `@@M@@\varepsilon@@`，再取每个距离的热力学极限，然后取无序矩，最后 `@@M@@r\to\infty@@`；`@@M@@\varepsilon=0@@` 时 `@@M@@R_0(r)\equiv1@@`。注意定理显式假设另一文献 [ReferenceIsing] 的确定性参考估计成立。

## 证明思路

证明采用坐标 `@@M@@\log\sinh(2K_e)=t+D\xi_e@@`，核心是一套多尺度阻塞（blocking）重整化。在每个尺度，有效相互作用是局部偶自旋函数之和：每格允许一个"主项"可以很大，其余项按连通集合（动物）索引、范数小且随集合大小指数衰减；每个项同时记录它作用的自旋与它依赖的原始随机变量——第二份记录正是后续"远离的两个插入的领头因子严格独立"的来源。第一个难题是输送只在高矩意义下小的相互作用：孤立的大相互作用群被积成一个正指数权，插入由其归一化条件律输送，缓冲带参考比较控制密度，衰减失效必有远处大场作证，可用独立性与高矩买单。

线性化后背景流只剩一个扩张的平均坐标（靠打靶选 `@@M@@t@@` 消除，区间嵌套得温度 `@@M@@t_*(D)@@`）和一个中性的协方差坐标 `@@M@@g_j@@`（单位面积热荷方差）。非线性系数在系数章节用有限个微观能量插入计算：精确配分恒等式保持归一化荷不变，参考模型的能量与自旋算子积展开（operator product expansion）决定对数项，得 `@@M@@B_0=4\pi a^2\log L@@` 与方差流 `@@M@@g_j\sim(B_0j)^{-1}@@`——无序坐标按尺度倒数衰减，再次严格化"边缘不相关"。

关键的新对象是被输运的自旋插入：其领头随机因子（幅度）有有界正均值，`@@M@@q@@` 阶矩为 `@@M@@A_{j,q}=j^{\binom q2/8+o(1)}@@`；`@@M@@q=1@@` 时一致有界（均值无对数修正，与 Shalaev 相符），`@@M@@q=2@@` 时为 `@@M@@j^{1/8}@@`。读出阶段用两个反对易变量标记两个插入点，得到精确恒等式把 `@@M@@r_J^{2d}\langle\sigma_{y_1}\sigma_{y_2}\rangle@@`（尺度维数 `@@M@@d=1/8@@`）写成终端期望；主槽替换后关联分解为 `@@M@@Z_J\cdot w_{J,y_1}w_{J,y_2}@@`，其中 `@@M@@Z_J=\widetilde\alpha_{J,y_1}\widetilde\alpha_{J,y_2}@@` 的两因子依赖互不相交的环境足印、严格独立，而联合源误差仅为 `@@M@@J^{-1/8+o(1)}@@`。再以半径 `@@M@@J^{4/25}@@` 的增长的终端缓冲把剩余期望与参考期望比较（`@@M@@q_J=r_J^{2d}\langle\sigma\sigma\rangle_0@@` 介于正常数之间），最终得 `@@M@@r_J^{4d}\E C^2=J^{1/4+o(1)}@@`，而 `@@M@@J=\log_L\ell+O(1)@@`，即 `@@M@@R_\varepsilon(r)=(\log r)^{1/4+o(1)}@@`。同法还给出高阶有线臂估计 `@@M@@\E[\phi^{\mathrm w}(y\leftrightarrow\partial\Lambda_n)^{400}]\le n^{-400/8+o(1)}@@`。最后过渡章节用扭转环面配分函数把调出的参数定位在自对偶点，乘积空间影响力不等式与随机壳层探索证明阈值两侧磁化为零与为正。部分张量估计的技术细节此处从略。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，且定理以引用文献 [ReferenceIsing] 的确定性参考估计为前提，属条件性结果。它与族内两篇姊妹篇共享同一套尺度重整化技术：姊妹篇证明临界接口的 quenched `@@M@@\mathrm{SLE}_3@@` 收敛（几何普适性），本文则量化无序留下的对数涨落痕迹，二者互补地刻画"边缘但不改变普适类"。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
