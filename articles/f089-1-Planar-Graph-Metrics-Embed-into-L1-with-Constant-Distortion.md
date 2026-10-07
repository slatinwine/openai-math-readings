---
layout: default
title: "Planar Graph Metrics Embed into L1 with Constant Distortion"
family: "089"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Planar Graph Metrics Embed into L1 with Constant Distortion

> 结果族 089：Bounded-distortion <i>L</i><sub>1</sub> embeddings of planar and bounded-treewidth graphs　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了任何带任意正实数边长的有限连通平面图，其最短路度量（shortest-path metric）都能以一个普适常数 `@@M@@C@@` 的失真（distortion）嵌入实 `@@M@@L_1@@`，肯定地解决 Gupta–Newman–Rabinovich–Sinclair 嵌入猜想的平面情形，并给出平面图上多商品流—割间隙的一致上界。

## 问题背景

把有限度量嵌入 `@@M@@L_1@@` 的失真至多为 `@@M@@C@@`，指经正数缩放后所有点对距离都落在原距离与 `@@M@@C@@` 倍原距离之间。2004 年 Gupta、Newman、Rabinovich 与 Sinclair 猜想（GNRS 猜想）：每个以禁用固定子式定义的图族（proper minor-closed family）都有对族内所有加权图一致有界的 `@@M@@L_1@@` 失真。问题的重要性在于 Linial–London–Rabinovich 与 Aumann–Rabani 的经典定理：`@@M@@L_1@@` 失真恰好刻画多商品流的流—割间隙（flow–cut gap），度量嵌入与组合优化在此汇合。平面情形此前最好的界是 Rao 的 `@@M@@O(\sqrt{\log n})@@`；而 Newman–Rabinovich 证明即使系列平行图（series-parallel graph）嵌入欧氏空间也需要 `@@M@@\Omega(\sqrt{\log n})@@`，说明常数界必须绕开欧氏空间、直接构造 `@@M@@L_1@@` 嵌入。常数失真此前只在附加限制下已知：系列平行图（GNRS；Chakrabarti–Jaffe–Lee–Vincent 改进到 2，Lee–Raghavendra 证明 2 最优）、有界外平面度（bounded outerplanarity）、同一面上顶点间的 Okamura–Seymour 等距嵌入，以及 Busemann 曲面（Busemann surface）上的特殊几何。真正的障碍是：要让相差指数多个距离尺度的割同时起作用，又不能随尺度数目累积误差。

## 主要结果

**主定理**：存在有限的普适常数 `@@M@@C\ge 1@@`，使得对每个带严格正实数边长的有限连通平面图 `@@M@@G=(V,E)@@`，存在测度空间 `@@M@@(\Omega,\mathcal F,\mu)@@` 与映射 `@@M@@f:V\to L_1(\Omega;\mathbb R)@@`，满足
`@@M@@Dd_G(x,y)\le\|f(x)-f(y)\|_1\le C\,d_G(x,y)\qquad(x,y\in V).@@`
界与顶点数无关，也与边长无关，即与度量中距离尺度的个数无关。由于有限 `@@M@@L_1@@` 度量恰为割度量（cut metric）的非负组合，定理等价于构造一族带权割：既按比例分离每对顶点，又对每条边只收常数倍边长的"割费"，沿最短路传递即得上界。由此得到推论：平面图上任意容量与需求的无向分数多商品流的流—割间隙被 `@@M@@C@@` 一致界定。结合姊妹篇的有界树宽定理与 Lee–Sidiropoulos 的随机约化，固定的几乎可嵌入族（almost-embeddable family）也获得一致失真界；但一般 clique-sum 闭包未建立，完整 GNRS 猜想仍开放。

## 证明思路

整个证明是一个编排严密的随机构造，分五步推进。

**第一步：柱模型（column model）。** 取以 `@@M@@o@@` 为根的最短路生成树，令高度 `@@M@@h(v)=d_G(o,v)@@`；把每条非树边 `@@M@@uv@@` 替换为长度 `@@M@@\frac{\ell_e\pm(h(v)-h(u))}{2}@@` 的两条上升分支，在共同高度处相接。以加宽后树的根—叶路径为竖直"柱"，柱按平面轮廓的循环顺序排列，柱间的切换（switch）互不交叉。这一替换是等距的：路径长度恰为垂直移动总量，切换免费，而平面性恰好保证链接不交叉。

**第二步：标签集与自动上界。** 给每个点构造两族可测标签集 `@@M@@\mathcal A_v,\mathcal B_v@@`，点对的割距离即对称差测度。构造保证每个标签下每根柱上的活跃点构成上区间（upper interval），因此沿任何路径标签隶属的总改变量不超过路径长度——每个随机结果都自动满足上界，与更新次数无关。困难全部集中在下界。

**第三步：局部更新与插值。** 更新发生在"chart"（共享一个标量场 `@@M@@P@@` 与标签变量的区域）上，阈值形如 `@@M@@h(v)+\sigma\kappa P(v)@@`，对公平符号 `@@M@@\sigma@@` 取平均能同时探测高度差与场差。活跃图的外平面性——无 `@@M@@K_{2,3}@@` 子式——给出双门户引理（two portals）：高径向分量的入口都落在至多两个门户点附近；由此定义的径向胞（cell）弱直径不超过 `@@M@@10D@@`。相邻胞在公共边界上的公式经插值后逐点一致，使局部修改能无接缝拼接——这是"不按尺度数累积损失"的关键机制。

**第四步：两套系统分工。** 系统 `@@M@@A@@` 在尺度 `@@M@@r@@` 尝试抬升距离约 `@@M@@r@@` 的点对一端的场；失败则暴露一条旧场几乎以 Lipschitz 极限速率下降的短路径。再把活跃集细化为活跃柱的连通分量：足够低的切换尖端能把两侧活跃点分开，构成分离证书。只有"两端均有下降路径且无证书"的点对产生种子（seed）；装填引理（packing bound）把这些种子压缩到两条短路径附近的小球内，限制参与竞争的随机提案个数——这是绕开"环境度量本身无一致装填界"难点的关键。系统 `@@M@@B@@` 利用循环顺序构造沿两弧同时递增的场，配上区分两弧、在切换处归零的符号横向场，分离幸存的点对。

**第五步：稀疏日程组装。** 取相邻尺度比 `@@M@@Q@@` 足够大的日程，把三个一致估计——单步移动不超过 `@@M@@Mr@@`、合格点对以概率 `@@M@@\ge p@@` 获得证书、半径 `@@M@@\rho r@@` 的小球被分裂的概率 `@@M@@O(\rho/r)@@`——化成两个小几何级数：点对以概率 `@@M@@\ge\frac12@@` 存活到自己的尺度并获得证书，此后所有更细尺度的总移动不足以抹去它。在 `@@M@@m@@` 个交错日程上取平均并展开为有限个割坐标，得 `@@M@@\frac{pb}{8m}d_G\le\|F(x)-F(y)\|_1\le 2d_G@@`，缩放后 `@@M@@C=16m/(pb)@@`，且嵌入实际落在有限维 `@@M@@\ell_1@@` 中。

## 可信度与备注

主定理已通过 Lean 形式化验证（见结果族 089 的 Lean 文档）。姊妹篇解决有界树宽情形，两篇互相支撑：本文末尾的几乎可嵌入族推论正是把两文与 Lee–Sidiropoulos 约化拼合而成。需要说明，一般 clique-sum 闭包本文并未建立，故完整 GNRS 猜想仍未解决。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已形式化，形式化范围之外的数值常数与推论细节建议对照原文核验。

{% endraw %}
