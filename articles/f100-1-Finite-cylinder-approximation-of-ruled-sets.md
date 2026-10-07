---
layout: default
title: "Finite cylinder approximation of ruled sets"
family: "100"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Finite cylinder approximation of ruled sets

> 结果族 100：Cylinder coverings below the half-area bound　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明一个"直纹集有限圆柱逼近"定理：由迹零、行列式非正的 `@@M@@C^1@@` 速度场（特征值 `@@M@@\pm\lambda@@` 且 `@@M@@0\le L\lambda<1@@`，含无剪切上限的平方零微分）导出的紧线段连续族，可用有限个方形砖圆柱覆盖，垂直底面积至多为其积分投影成本加任意正误差——它是本族推翻半面积猜想的"有限化机器"。

## 问题背景

覆盖凸体的圆柱成本问题（见本族背景）提示一个自然的省钱策略：让覆盖直线的方向随交点标签连续变化，在每个小标签片上"冻结"一个方向。但朴素地逐片冻结会在相邻片之间开缝，或产生不随网格加细而消失的面积损失；而连续变化族的积分成本 `@@M@@\int_D J_h(V)\,dp@@` 本身又并不自动给出有限个圆柱。本文把这个"从连续到有限"的最后一步提炼成带精确假设与精确面积因子的定理，供同族其他构造当作黑盒使用：先扰动一个简单线构型、比较新增标签面积与垂直投影的节省、最后才做有限化。

## 主要结果

对紧标签集 `@@M@@D\subset\R^2@@`、速度场（velocity field）`@@M@@V@@` 与半长 `@@M@@L>0@@`，记直纹集（ruled set）`@@M@@E(D,V,L)=\{(s,p+sV(p)):p\in D,\ |s|\le L\}@@`。主定理：若 `@@M@@V@@` 在 `@@M@@D@@` 的邻域上 `@@M@@C^1@@` 且逐点满足 `@@M@@\tr DV=0@@`、`@@M@@-L^{-2}<\det DV\le0@@`，则对任意 `@@M@@\varepsilon>0@@` 存在有限个紧的非退化方形砖 `@@M@@T_i@@`（方向可各异）与常速度 `@@M@@g_i@@`，使 `@@M@@E(D,V,L)\subset\bigcup_i\Cyl(T_i,g_i)@@` 且 `@@M@@\sum_i|T_i|J_h(g_i)\le\int_D J_h(V(p))\,dp+\varepsilon@@`；经物理伸缩 `@@M@@F_h@@` 后各垂直底是紧的非退化平行四边形，总面积为 `@@M@@h\sum_i|T_i|J_h(g_i)@@`。谱条件即特征值为 `@@M@@\pm\lambda_p@@`（`@@M@@\lambda_p=\sqrt{-\det DV}@@`）且 `@@M@@0\le L\lambda_p<1@@`：既允许非零双曲对逼近严格长度界，也允许平方零微分（square-zero differential，`@@M@@(DV)^2=0@@`）而完全不限制剪切系数，两类可在同一场中并存（例 `@@M@@V=(p_2,p_1^3/3)@@`）。定理不要求 `@@M@@\partial D@@` 面积为零、不要求 `@@M@@\|DV\|@@` 小，甚至允许 `@@M@@|D|=0@@`。

## 证明思路

证明分两层。先解决冻结的仿射场：迹零矩阵必有一个使对角线为零的正交基（在四分之一圆上用连续性找 `@@M@@q(e)=0@@` 的单位向量），于是 `@@M@@A=\bigl(\begin{smallmatrix}0&b\\ c&0\end{smallmatrix}\bigr)@@`，高度 `@@M@@s@@` 处单位方格中心移到 `@@M@@(i+sbj,\,sci+j)@@`。关键引理（变形方格覆盖）：只要 `@@M@@0\le\alpha\beta<1@@`，这些中心上的闭单位方格仍覆盖全平面。证明是对目标点解取整不动点方程 `@@M@@i=R(u_1-\alpha j)@@`、`@@M@@j=R(u_2-\beta i)@@`：该映射单调、在无穷远处斜率 `@@M@@\alpha\beta<1@@`，单调有界迭代必达不动点——这是 Tarski 单调不动点原理的有限链实例，且把零乘积情形与方格边界一并处理（正乘积情形也可由 Kolountzakis 的符号瓷砖恒等式得到，Stein 的缺角方砖为其特例）。砖本身永不变形、面积不变，动的只是中心；再由 Cayley–Hamilton（`@@M@@A^2=-(\det A)I@@`）得一致逆界 `@@M@@\|(I+sA)^{-1}\|\le(1+L\|A\|)/(1+L^2\det A)@@`。第二层把 `@@M@@C^1@@` 场有限化：先取边长 `@@M@@\delta@@` 的粗方格网覆盖 `@@M@@D@@`，在每个粗方格上把场冻结为仿射逼近 `@@M@@V_S@@`，并在其正交坐标里用细网格 `@@M@@\tau=\delta^2@@`。无穷的仿射覆盖先抓住真实的非线性目标点；一致逆估计给出 `@@M@@|l-p|\le R_\delta=C(\tau+L\eta_\delta\delta)=o(\delta)@@`，故只需保留距粗方格 `@@M@@R_\delta@@` 以内的中心——这是一个与 `@@M@@p,s@@` 均无关的有限清单。保留砖的总面积至多 `@@M@@(\delta+2R_\delta+2\tau)^2=\delta^2(1+o(1))@@`，每格加权成本 `@@M@@\delta^2J_h(V(b_S))+o(\delta^2)@@`，且双曲、平方零、零微分之间的切换不损失界。最后对 `@@M@@O(\delta^{-2})@@` 个粗格求和：粗格并 `@@M@@U_\delta@@` 夹在 `@@M@@D@@` 与其 `@@M@@\sqrt2\delta@@` 邻域之间，Lebesgue 测度的上连续性给出 `@@M@@|U_\delta\setminus D|\to0@@`，无需 `@@M@@\partial D@@` 的任何正则性假设，成本收敛到 `@@M@@\int_DJ_h(V)\,dp@@`。文中另给出以双曲线为边界的开胞元构造（长臂吸收一个特征方向的膨胀与另一方向的收缩，但需面积零边界），并讨论应用：谱条件严格弱于算子范数小（例 `@@M@@\bigl(\begin{smallmatrix}0&2\\ 1/8&0\end{smallmatrix}\bigr)@@` 特征值 `@@M@@\pm1/2@@` 而范数为 `@@M@@2@@`），奇异端点应先截断到紧标签集、单独覆盖省略线段、再在剩余严格间隙内分配逼近误差。

## 可信度与备注

本文未形式化，定理与证明应以社区核验为准。它是结果族 100 的方法支柱：姊妹篇《Slope-field perturbations of the two-cylinder covering》把本文定理 1.2 当作黑盒，对正四面体的两圆柱等式覆盖做斜率场扰动并实现严格节省；与自足的显式构造文一起，三篇从不同路径印证同一否定结论。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
