---
layout: default
title: "Radial transfer estimates and polygon length laws for honeycomb walks"
family: "237"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Radial transfer estimates and polygon length laws for honeycomb walks

> 结果族 237：The three-quarter exponent for honeycomb self-avoiding walk　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把一根很长的毛线扔到蜂巢网格上，绕成一个不压线、首尾相接的闭合圈：毛线越长，这个圈平均能摊多大？这篇论文给出精确答案——周长为 `@@M@@n@@` 的圈，直径按 `@@M@@n^{3/4}@@` 增长，介于"醉汉乱走"和"摊平的圆圈"之间。

**关键词卡片**

- 蜂窝格点（honeycomb lattice）：蜂巢那样的正六边形网格，平面里最规整的"曲线路面"。
- 自回避多边形（self-avoiding polygon）：在网格上首尾相接、且全程不许与自己相交的闭合路径。
- 临界权重（critical weight）：给每条边乘以 `@@M@@x_*=(2+\sqrt2)^{-1/2}@@`——恰好让无穷长路径处在"收敛与发散"的分界点上。
- 直径（diameter）：图形上相距最远的两点之间的直线距离。
- 标度指数（scaling exponent）：周长 `@@M@@n@@` 与直径 `@@M@@D@@` 之间的幂次关系；本文主角是 Nienhuis 预言的 `@@M@@3/4@@`。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="80" y1="220" x2="480" y2="220" stroke="#333" stroke-width="2"/><line x1="80" y1="220" x2="80" y2="40" stroke="#333" stroke-width="2"/><rect x="115" y="170" width="60" height="50" fill="#9ab7d8"/><text x="130" y="242" font-size="13" fill="#336">普通随机行走</text><text x="128" y="162" font-size="13" fill="#336">约 10²</text><rect x="255" y="110" width="60" height="110" fill="#7dc7a3"/><text x="262" y="242" font-size="13" fill="#1a7a4a">自回避多边形</text><text x="268" y="102" font-size="13" fill="#1a7a4a">约 10³</text><rect x="395" y="65" width="60" height="155" fill="#e8b46e"/><text x="375" y="242" font-size="13" fill="#a06414">拉直成光滑圆</text><text x="392" y="57" font-size="13" fill="#a06414">约 3×10³</text><text x="150" y="30" font-size="13" fill="#555">同样取 10⁴ 步（纵轴对数刻度示意）</text><text x="88" y="36" font-size="12" fill="#555">直径</text></svg>

</div>

代入数字：固定周长 `@@M@@n=10^4@@` 步，允许自交的普通随机行走会折返堆叠，团块直径约 `@@M@@10^2@@`；自回避多边形因为"不许踩自己的脚印"被自我排斥撑开，直径约 `@@M@@10^3@@`；定理的一般形式是：条件于边数至少 `@@M@@n@@`，直径依概率为 `@@M@@D=n^{3/4+o(1)}@@`，例如 `@@M@@n=10^8@@` 时 `@@M@@D\approx10^6@@`。

**为什么值得关心**

`@@M@@3/4@@` 指数 1982 年由物理学家 Nienhuis 从直觉预言，此后四十多年一直停留在猜想层面；本文首次在多边形版本上给出严格证明，而且长度与直径如何相配的双侧估计也一并补齐。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在蜂窝格点上证明了临界自回避多边形（polygon）的两条直径尾律：无根质量为 `@@M@@r^{-2+o(1)}@@`、长度加权质量为 `@@M@@r^{-2/3+o(1)}@@`；由此长度至少 `@@M@@n@@` 的多边形直径依概率为 `@@M@@n^{3/4+o(1)}@@`，严格确立了 Nienhuis 预言的 3/4 尺寸指数的多边形形式。

## 问题背景

自回避多边形是自回避行走（self-avoiding walk）的闭合版本，按边数以临界权重 `@@M@@w(\gamma)=x_*^{L(\gamma)}@@` 计数，其中 `@@M@@x_*=(2+\sqrt2)^{-1/2}@@`。Nienhuis 1982 年借稀释 `@@M@@O(n)@@` 模型预言了这一临界活性与平面标度指数族，包括尺寸指数 `@@M@@3/4@@`；Duminil-Copin 与 Smirnov（2012）用仲费米观测（parafermionic observable）严格证明了 `@@M@@x_*@@` 是蜂窝连通常数，但 `@@M@@3/4@@` 本身始终停留在预言层面，Lawler–Schramm–Werner 只能从尚未证明的 `@@M@@\mathrm{SLE}_{8/3}@@` 标度极限猜想把它恢复出来。多边形版本的难点尤为具体：一个大多边形可以远比其直径"长"，长度与直径这两个尺寸在临界权重下如何相配，此前没有任何匹配的双侧估计。本文正面解决了这个问题。

## 主要结果

记 `@@M@@\gamma@@` 为按平移等价类计数的多边形，`@@M@@L(\gamma)@@` 为边数、`@@M@@D(\gamma)@@` 为欧氏直径。定理 1.1 证明：直径尾质量

`@@M@@DA(r)=\sum_{D(\gamma)\ge r}w(\gamma)=r^{-2+o(1)},\qquad P(r)=\sum_{D(\gamma)\ge r}L(\gamma)\,w(\gamma)=r^{-2/3+o(1)},@@`

并附带截断二阶矩（truncated second moment） bound `@@M@@M_2(r)=\sum_{D(\gamma)\le r}L(\gamma)^2w(\gamma)\le r^{2/3+o(1)}@@`，它阻止过多临界质量被"直径小而极长"的多边形携带。推论 1.2 把尾律换成长度截断：`@@M@@\sum_{L\ge n}w=n^{-3/2+o(1)}@@`、`@@M@@\sum_{L\ge n}Lw=n^{-1/2+o(1)}@@`，从而在任一归一化下、条件于 `@@M@@L(\gamma)\ge n@@`，有 `@@M@@D(\gamma)=n^{3/4+o(1)}@@` 依概率成立——这正是 Nienhuis 指数；反向条件于 `@@M@@D\ge r@@` 的长度加权定律给出 `@@M@@L=r^{4/3+o(1)}@@`，无根定律的条件平均长度亦为 `@@M@@R^{4/3+o(1)}@@`。文中还导出：固定近距端点的半平面行走有同样的条件平均长度；半平面拱（arch）质量 `@@M@@\asymp n^{-5/4}@@`、带（strip）穿越质量 `@@M@@\asymp H^{-1/4}@@` 且可限制在指定走廊内；以及收敛半径间隙 `@@M@@0\le x_{\rm strip}(W)-x_*\le W^{-4/3+o(1)}@@`。

## 证明思路

先把平面多边形投影到周长 `@@M@@N|h|@@` 的柱面（cylinder）上：投影后要么仍单射（可收缩柱面多边形），要么与自身平移像相撞。文章在取极限之前用有限转移矩阵（transfer matrix）比较两类质量。代数核心是两个缝捻（seam twist）`@@M@@\eta=\pm i@@` 的多项式固定向量：其带标记收缩分别数出"缠绕加可收缩"与"缠绕减可收缩"，相加即分离出正的缠绕质量 `@@M@@E_N@@`，并满足精确恒等式 `@@M@@E_N\tau_N=(2-\sqrt2)\tau^v_{N-1}@@`；行列式计算证明 `@@M@@\tau_N\ne0@@`，于是正质量被表为两个本身未必为正的有限和之比。再估计该比值：先经格点顶点算子（vertex operator）式的角向展开（双线性型不定，故先逐系数处理），后转为径向（radial）级数——插入电荷置于实轴位置并携带分段常数斜率（slope），斜率平方沿径向产生指数代价，中央标记大电荷在对数宽度区域内压制多数插入类型。最大的障碍是变换后的表达式全为复数，既非概率也非正权，形式首指数可能因系数消失而失真；作者以强制性（coercivity）不等式 `@@M@@\Re\sum_{x<y}t_xt_y\mathcal Q(x,y)\ge c\sum_I(\sum_{x\in I}t_x)^2-C\sum_x t_x^2@@` 保证绝对收敛并产生紧算子（compact operator），谱信息全部来自精确迹恒等式，而第 4 节的正缠绕界防止首系数消失，最终得单标记指数 `@@M@@-2/3@@`；双标记时三区贡献合成 `@@M@@k^{-9/8}(N/k)^{5/24}N^{-5/24}=k^{-4/3}@@`，给出二阶矩。最后转回平面：长度加权投影损失恰为 `@@M@@E_N@@`，无根损失 `@@M@@\asymp N^{-2}@@`；失败投影的直径必 `@@M@@\ge|h|N@@` 给下界，反向取三对称定向、`@@M@@N=\lfloor R^{1-\epsilon}\rfloor@@` 并用薄柱面横距估计排除高瘦投影，即得两条直径尾。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。它是结果族 237 的多边形支柱：姊妹篇《Critical honeycomb chords with prescribed boundary endpoints》证明边界弦的 `@@M@@R^{4/3}@@` 长度定律、《Cylinder loop weights and planar nesting》确定环路嵌套指数，三篇从多边形尾、边界弦、嵌套配分三个侧面共同支撑族级主张"n 步行走直径为 `@@M@@n^{3/4+o(1)}@@`"（族说明附有 Lean 文档，但覆盖的是族级主张而非本文逐条定理）。

{% endraw %}
