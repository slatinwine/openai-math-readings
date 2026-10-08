---
layout: default
title: "The crossing number of complete graphs"
family: "165"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The crossing number of complete graphs

> 结果族 165：The Harary–Hill and Zarankiewicz crossing-number formulas　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

开圆桌会议，n 个人每两人都要握手一次，把每次握手画成纸上的一条曲线——人一多，总有线躲不开地相交。问：相交点最少能有几个？这就是完全图 `@@M@@K_n@@` 的交叉数问题。Harary 与 Hill 在 1963 年猜出了一个简洁公式，悬置六十多年；这篇论文证明猜想成立：教科书式的"书脊画法"就是全局最优，任何曲线诡计都省不掉一个交叉。

**关键词卡片**

- 完全图 `@@M@@K_n@@`（complete graph）：n 个顶点两两连边的图，相当于人人握手一次。
- 交叉数（crossing number）：所有画法中交叉点个数的最小值，记 `@@M@@\operatorname{cr}(G)@@`。
- 画法（drawing）：顶点放在互异位置、边画成不自交的连续弧，允许交叉。
- 带号交叉（signed intersection）：给每个交叉按方向记 +1 或 −1，把几何问题代数化，是证明的引擎。

**看个具体例子**

公式（数字版定理）：`@@M@@\operatorname{cr}(K_n)=\frac14\lfloor\frac n2\rfloor\lfloor\frac{n-1}2\rfloor\lfloor\frac{n-2}2\rfloor\lfloor\frac{n-3}2\rfloor@@`。代入小数字逐一应验：`@@M@@\operatorname{cr}(K_5)=1@@`、`@@M@@\operatorname{cr}(K_6)=3@@`、`@@M@@\operatorname{cr}(K_7)=9@@`、`@@M@@\operatorname{cr}(K_8)=18@@`。要知道此前的最好成绩：计算机只核实到 `@@M@@n\le 13@@`，旗代数方法也只证到猜想值的约 `@@M@@0.9856@@` 倍，离终点始终差一口气。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="150" y1="90" x2="410" y2="90" stroke="#8899aa" stroke-width="2"/>
  <line x1="410" y1="90" x2="410" y2="230" stroke="#8899aa" stroke-width="2"/>
  <line x1="410" y1="230" x2="150" y2="230" stroke="#8899aa" stroke-width="2"/>
  <line x1="150" y1="230" x2="150" y2="90" stroke="#8899aa" stroke-width="2"/>
  <line x1="150" y1="90" x2="410" y2="230" stroke="#8899aa" stroke-width="2"/>
  <line x1="410" y1="90" x2="150" y2="230" stroke="#8899aa" stroke-width="2"/>
  <line x1="280" y1="25" x2="150" y2="90" stroke="#8899aa" stroke-width="2"/>
  <line x1="280" y1="25" x2="410" y2="90" stroke="#8899aa" stroke-width="2"/>
  <path d="M 280 25 Q 550 300 410 230" fill="none" stroke="#8899aa" stroke-width="2"/>
  <path d="M 280 25 Q 10 300 150 230" fill="none" stroke="#8899aa" stroke-width="2"/>
  <circle cx="280" cy="160" r="11" fill="none" stroke="#e0a000" stroke-width="2.5"/>
  <circle cx="150" cy="90" r="11" fill="#45607a"/>
  <circle cx="410" cy="90" r="11" fill="#45607a"/>
  <circle cx="410" cy="230" r="11" fill="#45607a"/>
  <circle cx="150" cy="230" r="11" fill="#45607a"/>
  <circle cx="280" cy="25" r="11" fill="#45607a"/>
  <text x="150" y="95" font-size="12" text-anchor="middle" fill="#ffffff">A</text>
  <text x="410" y="95" font-size="12" text-anchor="middle" fill="#ffffff">B</text>
  <text x="410" y="235" font-size="12" text-anchor="middle" fill="#ffffff">C</text>
  <text x="150" y="235" font-size="12" text-anchor="middle" fill="#ffffff">D</text>
  <text x="280" y="30" font-size="12" text-anchor="middle" fill="#ffffff">E</text>
  <text x="280" y="264" font-size="14" text-anchor="middle" fill="#333333">K₅：5 点两两连线，交叉最少 1 个（黄圈），不可能画成 0 个</text>
</svg>

</div>

下界证明不走"限制画法"的老路，而是从任意画法中提取代数信息：给边定向、统计带号交叉，构造双线性型 J 并证明它在圈上恒为零，再用拉格朗日插值多项式把"交叉必多"压缩成一次维数计数。

**为什么值得关心**

与姊妹篇（完全二部图）在同一个"带号交叉+插值"框架下连环解决两大画图猜想，且已通过 Lean 形式化。

> 已 Lean 形式化

## 一句话结论

论文证明了悬置六十余年的哈拉里–希尔猜想（Harary–Hill conjecture）：`@@M@@n@@` 顶点完全图 `@@M@@K_n@@` 的普通交叉数恰为 `@@M@@\frac14\lfloor\frac n2\rfloor\lfloor\frac{n-1}2\rfloor\lfloor\frac{n-2}2\rfloor\lfloor\frac{n-3}2\rfloor@@`，宣告希尔经典构图在任意连续弧画法下都无法改进。

## 问题背景

把一个图画进平面：顶点放在互异的点，边用简单连续弧表示，边内部只在有限个点发生正常交叉；交叉数（crossing number）`@@M@@\operatorname{cr}(G)@@` 就是所有画法中交叉点数的最小值。完全图（complete graph）`@@M@@K_n@@` 的交叉数公式由 Guy（1960）给出上界、Harary 与 Hill（1963）正式陈述为猜想。此前进展要么局部、要么渐近、要么受限：Pan–Richter 与 Aichholzer 借助计算机核实到 `@@M@@n\le 13@@`；半定规划方法只证到猜想值的 `@@M@@0.83@@` 倍，旗代数（flag algebras）方法推进到约 `@@M@@0.9856@@` 倍；两页画法（two-page drawings）、柱面画法、`@@M@@x@@`-有界画法乃至球面测地线画法等整条路线都只在受限画法类内确立下界。如何对完全不受限的画法证明下界，正是六十年来卡住所有人的难点。

## 主要结果

主定理：对每个整数 `@@M@@n\ge3@@`，

`@@M@@D\operatorname{cr}(K_n)=Z(n):=\frac14\left\lfloor\frac n2\right\rfloor\left\lfloor\frac{n-1}2\right\rfloor\left\lfloor\frac{n-2}2\right\rfloor\left\lfloor\frac{n-3}2\right\rfloor.@@`

按奇偶可写成 `@@M@@Z(2s+1)=\binom{s}{2}^2@@`、`@@M@@Z(2s)=\frac{s(s-1)^2(s-2)}4@@`；`@@M@@n=1,2@@` 时同一公式给出 `@@M@@0@@`。论文证明两半：任何画法至少有 `@@M@@Z(n)@@` 个交叉（下界），且存在恰有 `@@M@@Z(n)@@` 个交叉的画法（上界），合一即哈拉里–希尔猜想成立。

## 证明思路

证明分下、上两半，下界是核心；其策略不是限制画法，而是从画法中提取代数信息。先由附录引理把极小画法归一化（normalization）：换成折线画法，并消灭相邻边（共享端点的边）之间的交叉。再构造核心代数对象：给每条边定向，令 `@@M@@I(e,f)@@` 为两条边内部交叉的带号交和（signed intersection，符号由交叉处两切向的定向给出）；在公共端点 `@@M@@w@@` 处用辐条（spoke）的逆时针循环序给出比较符号 `@@M@@T_w@@`，定义双线性型 `@@M@@J(e,f)=I(e,f)+\frac12\sum\sigma_{we}\sigma_{wf}T_w(e,f)@@`。关键的圈配对引理（cycle pairing）断言 `@@M@@J@@` 在任意两条圈（cycle）上取值为零。证明时把两个圈改造成闭折线走道 `@@M@@\gamma@@` 与向左、右微移的两个版本 `@@M@@\eta_\pm@@`：圆盘内两条弦的带号交叉恰由端点在圆周上的交替模式决定（局部弦公式），而平面上两条闭折线的总带号交点数必为零——把第一走道的每段锥到远处一点，每个三角形与第二走道的进出交点成对相消；对两个平移版本取平均，公共辐条的比较符号恰好抵消，剩下的正是 `@@M@@J@@`。

接着是插值工具。给顶点配上互异实标号 `@@M@@t_i@@` 与拉格朗日权（Lagrange weights）`@@M@@w_i=1/F'(t_i)@@`：权重恒等式使加权链自动成为圈，于是圈配对引理批量给出恒等式——对每变量次数 `@@M@@\le n-2@@` 的多项式权 `@@M@@H@@`，`@@M@@J@@` 的四重加权和为零。论文再建立"偶节点序探测器"：先证双三角插值（两组三角形格点上的赋值都唯一决定双变量多项式），据此证明带序比较符号的配对 `@@M@@M@@` 非退化，即与整个测试空间配对全零的多项式必为零。

最后装配下界（奇数 `@@M@@n=2s+1@@`）：取每变量次数 `@@M@@\le s-2@@`、在两组端点内各自对称的多项式空间 `@@M@@\mathcal S@@`，其维数恰为 `@@M@@\binom{s}{2}^2=Z(2s+1)@@`；把它赋值到每个带号量非零的独立边对上，得评估映射 `@@M@@E@@`。先在多项式测试中插入差因子，迫使核中多项式在"两条边共享端点"的退化位置为零，于是碰撞因子 `@@M@@C=(x-y)(x-v)(u-y)(u-v)@@` 整除它；除掉 `@@M@@C@@` 后对称性与核资格都保持，次数可以无限下降，故 `@@M@@E@@` 单射。再把圈恒等式乘上六因子差积 `@@M@@\Delta@@` 用第二次，得像空间在非退化对角对称型下全迷向（totally isotropic），维数至多是坐标数之半，而每个支撑边对至少贡献一个交叉。合并得 `@@M@@c(D)\ge\binom{s}{2}^2@@`；偶数情形由删点计数 `@@M@@(n-4)c(D)\ge n\binom{s-1}2^2@@` 导出 `@@M@@Z(n)@@`。

上界则回到经典的两页画法：顶点排在一条"书脊"直线上，按 `@@M@@i+j\bmod n@@` 的余数分两色，两色边分别画成上、下半平面的半圆；沿循环序数间隙做初等计数，交叉数恰为 `@@M@@Z(n)@@`。

## 可信度与备注

主结果已有 Lean 形式化证明（结果族 165 的说明附有 Lean 文档链接）。姊妹篇《完全二部图的交叉数》与本文共享同一归一化附录与圈配对引理——论文明确注明该论证与姊妹篇的相应引理一致，两文在同一"带号交叉 + 插值"框架下分别解决 Harary–Hill 与 Zarankiewicz 两大猜想，互相支撑。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，属可信度最高一档，具体细节仍建议以社区核验为准。

{% endraw %}
