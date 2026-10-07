---
layout: default
title: "The crossing number of complete bipartite graphs"
family: "165"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The crossing number of complete bipartite graphs

> 结果族 165：The Harary–Hill and Zarankiewicz crossing-number formulas　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文证明了 Zarankiewicz 猜想、解决了 Turán 1944 年提出的砖厂问题（brickyard problem）：完全二部图 `@@M@@K_{m,n}@@` 的普通交叉数恰为 `@@M@@\lfloor\frac m2\rfloor\lfloor\frac{m-1}2\rfloor\lfloor\frac n2\rfloor\lfloor\frac{n-1}2\rfloor@@`，经典的"坐标轴构图"在一切连续弧画法中被证明全局最优。

## 问题背景

1944 年，Turán 在布达佩斯附近一家砖厂看到连接窑炉与货场的铁轨频频相交，由此提出完全二部图（complete bipartite graph）`@@M@@K_{m,n}@@` 的交叉数问题。Zarankiewicz 在 1955 年给出沿两条坐标轴布点的构图并断言其最优，但最优性论证存在漏洞。此后 Kleitman 用排列论证解决了较小顶点类至多 6 个顶点的情形；Woodall 发展循环序图（cyclic-order graphs）方法并计算机验证了 `@@M@@K_{7,7}@@` 与 `@@M@@K_{7,9}@@`；半定规划与旗代数（flag algebras）给出 `@@M@@\operatorname{cr}(K_{n,n})\ge 0.9118\,d_n^2+o(n^4)@@` 的渐近下界。与完全图情形同病：对完全不受限的画法，下界始终无人能证。

## 主要结果

主定理：对一切正整数 `@@M@@m,n@@`，记 `@@M@@d_r=\lfloor\frac r2\rfloor\lfloor\frac{r-1}2\rfloor@@`，则

`@@M@@D\operatorname{cr}(K_{m,n})=d_m d_n.@@`

即 `@@M@@\lfloor\frac m2\rfloor\lfloor\frac{m-1}2\rfloor\lfloor\frac n2\rfloor\lfloor\frac{n-1}2\rfloor@@`。下界对任意画法成立，上界由古典构图达到，Zarankiewicz 猜想从而成立。

## 证明思路

证明由三个彼此独立的模块加一次组合装配构成。

模块一（纯代数）：若 `@@M@@N@@` 维实向量空间中的子空间（subspace）满足 `@@M@@U_i\cap V_i=\{0\}@@`，则 `@@M@@\sum_{i,j}\dim(U_i\cap V_j)\le\lfloor m^2/4\rfloor N@@`，且常数最优。证明用多项式插值：考察系数取值于子空间、在各节点处满足约束的多项式按次数形成的滤过，非节点处的赋值维数稳定；多项式矩阵子式（minor）的度数受列次数控制，而它在每个节点处的秩亏损迫使相应幂次的 `@@M@@(\xi-t_j)@@` 整除行列式，零点重数与度数比较后求和即得。再取线性映射的图（graph），交维数化为矩阵差之核的维数，得到实用的秩和不等式：当各 `@@M@@X_i-Y_i@@` 可逆时，`@@M@@\sum_{i\ne j}\operatorname{rank}(X_i-Y_j)\ge 2d_m d@@`。

模块二（几何）：与姊妹篇共享同一个带号交叉矩阵 `@@M@@J@@`——内部交叉的带号交和（signed intersection）加上公共端点处辐条循环序的半修正项；圈配对引理 `@@M@@z^{\mathsf T}Jy=0@@` 及其证明（闭折线走道、锥到一点）逐字相同。新的一步是用二部图的四圈（four-cycle）把几何信息压成矩阵关系：块 `@@M@@J^{ik}=J(ip,kq)@@` 满足循环差 `@@M@@J^{ik}-J^{i1}-J^{1k}+J^{11}@@` 的所有矩形差为零，故落在"行加列"矩阵空间 `@@M@@\mathcal L@@` 中。

模块三（秩探测器）：当 `@@M@@n=2s+1@@` 时构造线性映射 `@@M@@\Phi@@` 把 `@@M@@n\times n@@` 矩阵送到 `@@M@@s^2\times s^2@@` 矩阵，基砖是拉格朗日重心权（barycentric weights）`@@M@@(x_p-x_q)/(F'(x_p)F'(x_q))@@` 乘单项式赋值向量得到的秩一矩阵。`@@M@@\Phi@@` 消灭一切行加列矩阵与对角矩阵；把单个非对角元映为秩至多 1 的矩阵；把任一线性辐条序的半符号矩阵 `@@M@@S_\prec@@` 映为可逆矩阵——最后一点归结为"双三角"格点上的插值唯一性，用归纳法剥去整行整列的因子。

装配：取归一化极小画法，令 `@@M@@R_{ik}=\Phi(J^{ik})@@`。模块二保证 `@@M@@R_{ik}=X_i-Y_k@@` 具差形式；对角块 `@@M@@R_{ii}@@` 恰是顶点 `@@M@@a_i@@` 处辐条序的半符号矩阵之像，由探测器的可逆性满秩 `@@M@@d=s^2@@`；非对角块的秩不超过两颗星（star）之间的交叉点数。代入秩和不等式得 `@@M@@2d_m d\le 2c(D)@@`，即下界 `@@M@@d_m d_n@@`（奇数 `@@M@@n@@`）；偶数 `@@M@@n@@` 由删点计数 `@@M@@(n-2)c(D)\ge n\,d_m d_{n-1}@@` 归结为奇数情形。上界用古典轴构图：两坐标轴上尽量均分放置顶点、直线连边，每个象限贡献 `@@M@@\binom u2\binom v2@@` 个交叉，总和恰为 `@@M@@d_m d_n@@`；一般位置选取排除三线共点。

## 可信度与备注

主结果已 Lean 形式化（结果族 165 的说明附有 Lean 文档链接）。姊妹篇《完全图的交叉数》与本文共享归一化附录与圈配对引理，两文在同一"带号交叉 + 插值"框架下分别解决 Harary–Hill 与 Zarankiewicz 两大猜想，互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，属可信度最高一档，具体细节仍建议以社区核验为准。

{% endraw %}
