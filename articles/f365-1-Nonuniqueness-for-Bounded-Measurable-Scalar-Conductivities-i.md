---
layout: default
title: "Nonuniqueness for bounded measurable scalar conductivities in three dimensions"
family: "365"
discipline: "Partial differential equations"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Nonuniqueness for bounded measurable scalar conductivities in three dimensions

> 结果族 365：Joint metric and connection recovery from one boundary patch　·　学科：Partial differential equations　·　验证状态：主结果已 Lean 形式化

## 一句话结论
在三维球上构造出两个不同的有界可测标量电导率（一致正、都在边界附近等于 1），它们的完整 Dirichlet–to–Neumann 算子却完全相同：仅有有界可测正则性时，标量 Calderón 唯一性在三维即告失败。

## 问题背景
Calderón 1980 年正是对有界可测、一致正的标量电导率（scalar conductivity）提出确定问题。`@@M@@n\ge3@@` 的光滑情形由 Sylvester–Uhlmann 证明唯一性，此后正则性要求一路下调：Haberman 达到 `@@M@@W^{1,n}@@`，Caro–Rogers 达到 Lipschitz；二维情形 Astala–Päivärinta 证明了有界可测唯一性。但三维及以上在"有界可测、无任何导数假设"层面是否有唯一性长期未决，本文给出否定回答，并说明对所有 `@@M@@n\ge3@@` 量化的唯一性命题为假。它与同族两篇光滑唯一性文章形成鲜明对照：光滑时一个补丁就够，可测时全边界也不唯一。

## 主要结果
**定理**：存在实值函数 `@@M@@\gamma_0,\gamma_1\in L^\infty(B(0,3))@@` 与常数 `@@M@@0<c<C<\infty@@`，使得：`@@M@@c\le\gamma_j\le C@@` 几乎处处；两者都在边界的一个邻域内恒等于 1；`@@M@@\gamma_0\ne\gamma_1@@` 于正测度集；且作为 `@@M@@H^{1/2}(\partial B)\to H^{-1/2}(\partial B)@@` 的有界算子，全弱意义 DN 算子（Dirichlet-to-Neumann operator）满足 `@@M@@\Lambda_{\gamma_0}=\Lambda_{\gamma_1}@@`。**推论（局部化非唯一性）**：任一有界连通 Lipschitz 区域内任取 `@@M@@m@@` 个两两不交的球，可造 `@@M@@2^m@@` 个两两不同的一致正有界可测电导率（球外恒为 1），共享同一个全边界 DN 算子。

## 证明思路
构造分三层。第一层是**精确标量化定理**（finite-field scalarization）：在局部光滑与梯度秩条件下，把一致椭圆对称张量 `@@M@@A@@` 连同两个指定解 `@@M@@u_1,u_2@@` 替换为一个有界正的标量系数 `@@M@@\gamma@@`，同时精确保持两个解的边界迹与整条法向通量泛函——这是对两个指定输入的完整响应，而非同质化近似。工具是坐标联结（coordinate join）的积式树叶分层（Marino–Spagnolo 式各向同性逼近的经典算术）、Raiță 多项式位势法产生的局部化通量波逐次修正，以及 Kirchheim 开创、Astala–Faraco–Székelyhidi 移植到椭圆方程的 Baire 连续点论证，用以选取满足两条本构关系的强极限。第二层造**分岔块**（branching block）：一个边界由三个环面（一亲两子）组成的区域，各配一个概率测度；标量化后它能实现任何零和电流三元组 `@@M@@p=(p_0,p_-,p_+)@@`，通量恰为 `@@M@@p_i@@` 乘相应测度。块内先在柱形平坦端上解变分问题，跨"秩一墙"修正小残差，再把一个衰减模通过逐次倍增的角频率转移到有限距离处消失，使两个电流向量张成零和平面。第三层把块按相似比 `@@M@@s@@`（`@@M@@2s^3<1@@`，保证剩余嵌套集零体积）自相似地嵌满球内，定义全局 `@@M@@\gamma@@`。对任一有界 `@@M@@\gamma@@`-调和函数 `@@M@@u@@`，用块位势作检验并由互易性得三个表面平均与零和平面正交、故相等，迭代推出 `@@M@@u@@` 在所有胞腔表面共享同一平均 `@@M@@u_*@@`。随后赋予符号电荷（每层总量恒为 2），相应级数在 `@@M@@L^\infty@@` 与 `@@M@@H^1@@` 中收敛到非零位势 `@@M@@w\in H^1_0\cap L^\infty@@`，支集远离外边界。关键恒等式在于：`@@M@@w@@` 的源虽然非零，却在一切乘积 `@@M@@(u-u_*)\phi@@`（`@@M@@u@@` 有界调和、`@@M@@\phi@@` 光滑紧支）上消失，这由公共平均与胞腔直径按 `@@M@@s^N@@` 缩小保证。于是取 `@@M@@\rho=1+\delta w@@`（`@@M@@\tfrac12\le\rho\le\tfrac32@@`）、`@@M@@\tilde\gamma=\rho^2\gamma@@`、`@@M@@\tilde u=u_*+(u-u_*)/\rho@@`：直接计算得通量 `@@M@@\tilde\gamma\nabla\tilde u=\rho\gamma\nabla u-(u-u_*)\gamma\nabla\rho@@` 无散，且外领区内 `@@M@@\rho=1@@`，边界响应不变；光滑边值的调和延拓有界，再由稠密性把等式扩张到整个 DN 算子。与依赖奇异变换的隐身构造不同，这里电导率始终一致椭圆，两个电导率在正测度集上确有差别。

## 可信度与备注
本文是族内唯一主结果已获 Lean 形式化证明的一篇，可信度最高。它为同族两篇光滑唯一性定理划出了正则性边界：从 `@@M@@C^\infty@@`（甚至 Lipschitz）降到有界可测，三维标量 Calderón 问题由唯一翻转为不唯一。据 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇不在其列。

{% endraw %}
