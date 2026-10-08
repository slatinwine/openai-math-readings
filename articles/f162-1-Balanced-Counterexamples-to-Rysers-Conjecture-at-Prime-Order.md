---
layout: default
title: "Balanced counterexamples to Ryser's conjecture at prime orders"
family: "162"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Balanced counterexamples to Ryser's conjecture at prime orders

> 结果族 162：Counterexamples to Ryser's covering conjecture　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一个社团组队：成员分成 q+1 个"部门"，每支小队恰好从每个部门各抽一人；社团有条铁律——任何两支小队必有共同成员。你是干事，想挑尽量少的人，使每支小队里至少有一人被挑中。Ryser 猜想说 q 个人就够；这篇论文证明：存在这样的社团，非 q+1 人不可——而且每个部门的人数还取到了理论上的最小值。

**关键词卡片**

- 超图（hypergraph）：一条边可以同时连接多个点的图；一支小队就是一条"超边"。
- r-部 r-一致（r-partite r-uniform）：顶点分成 r 组、每条边恰好各组抽一个，正是组队规则。
- 相交（intersecting）：任何两条边都有公共点，即社团铁律。
- 覆盖数 τ（covering number）：碰到所有边所需的最少顶点数，即你要挑的最少人数。
- 匹配数 ν（matching number）：两两无公共点的边最多有几条；相交超图的 ν=1。

**看个具体例子**

Ryser 猜想：`@@M@@\tau\le(r-1)\nu@@`；相交时 ν=1，即"q+1 个部门至多挑 q 人"。反例（数字版）：对每个足够大的素数 q，存在每部门恰 q+1 人的社团，`@@M@@\tau=q+1@@`——比预算恰好多一人。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <polyline points="110,70 280,140 450,70" fill="none" stroke="#d84a3f" stroke-width="5" stroke-opacity="0.55" stroke-linejoin="round"/>
  <polyline points="110,70 280,210 450,210" fill="none" stroke="#3f7ad8" stroke-width="5" stroke-opacity="0.55" stroke-dasharray="12 7" stroke-linejoin="round"/>
  <circle cx="110" cy="70" r="9" fill="#ffd76e" stroke="#444444" stroke-width="2"/>
  <circle cx="110" cy="140" r="9" fill="#ffffff" stroke="#444444" stroke-width="2"/>
  <circle cx="110" cy="210" r="9" fill="#ffffff" stroke="#444444" stroke-width="2"/>
  <circle cx="280" cy="70" r="9" fill="#ffffff" stroke="#444444" stroke-width="2"/>
  <circle cx="280" cy="140" r="9" fill="#ffffff" stroke="#444444" stroke-width="2"/>
  <circle cx="280" cy="210" r="9" fill="#ffffff" stroke="#444444" stroke-width="2"/>
  <circle cx="450" cy="70" r="9" fill="#ffffff" stroke="#444444" stroke-width="2"/>
  <circle cx="450" cy="140" r="9" fill="#ffffff" stroke="#444444" stroke-width="2"/>
  <circle cx="450" cy="210" r="9" fill="#ffffff" stroke="#444444" stroke-width="2"/>
  <text x="110" y="40" font-size="14" text-anchor="middle" fill="#444444">第 1 部</text>
  <text x="280" y="40" font-size="14" text-anchor="middle" fill="#444444">第 2 部</text>
  <text x="450" y="40" font-size="14" text-anchor="middle" fill="#444444">第 3 部</text>
  <text x="280" y="252" font-size="14" text-anchor="middle" fill="#555555">红队、蓝队各从每部抽一人，且共用第 1 部的同一个人（相交）</text>
  <text x="280" y="272" font-size="12" text-anchor="middle" fill="#999999">示意：以 3 个部门代替构造中的 q+1 个部门</text>
</svg>

</div>

构造从有限几何的"方向与直线"出发：每个方向设一个部门；把某方向的两条平行线合并、另两条拆成对角配对，使部门人数与覆盖难度同时抬升；再用概率方法选出兼容的拆分，最后借助"素平面稳定性"定理排除一切省人的覆盖方案。

**为什么值得关心**

Ryser 猜想是 König 定理向超图推广的核心关口，如今连"各部门等大"的平衡版本也被证伪。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对每个足够大的素数 `@@M@@q@@`，本文构造出相交（intersecting）的 `@@M@@(q+1)@@`-部、`@@M@@(q+1)@@`-一致超图，覆盖数（covering number）达到理论上限 `@@M@@q+1@@`，且每部恰有 `@@M@@q+1@@` 个非孤立顶点，从而推翻 Ryser 覆盖猜想——连"各部等大"的平衡情形也一并推翻。

## 问题背景

Ryser 覆盖猜想断言：每个 `@@M@@r@@`-部 `@@M@@r@@`-一致超图（`@@M@@r@@`-partite `@@M@@r@@`-uniform hypergraph）`@@M@@H@@` 满足 `@@M@@\tau(H)\le(r-1)\nu(H)@@`，其中 `@@M@@\tau@@` 为覆盖数，`@@M@@\nu@@` 为匹配数（matching number）。`@@M@@r=2@@` 时即 König 定理，三部情形由 Aharoni 于 2001 年证明。相交超图中 `@@M@@\nu=1@@`，猜想退化为 `@@M@@\tau\le r-1@@`：Gyárfás 验证到秩 4，Tuza 到秩 5，线性相交情形到秩 9。截断射影平面在 `@@M@@r-1@@` 为素数幂时给出 `@@M@@\tau=r-1@@` 的取等例子，使这个界显得自然；Haxell–Scott 的一般下界却只有 `@@M@@\tau\ge r-4@@`。覆盖允许从各部混取顶点，要把覆盖数推过 `@@M@@r-1@@` 极难，此前一直无人做到。

## 主要结果

**定理**：存在阈值 `@@M@@q_0@@`，使对每个素数 `@@M@@q\ge q_0@@`，存在有限相交 `@@M@@(q+1)@@`-部 `@@M@@(q+1)@@`-一致超图 `@@M@@H@@`，满足 `@@M@@|V_1|=\cdots=|V_{q+1}|=q+1@@`、`@@M@@\tau(H)=q+1@@`，且每个顶点都属于某条边。因 `@@M@@\nu(H)=1@@` 而 `@@M@@r-1=q@@`，这直接违反 Ryser 不等式。两端都是紧的：任一条边本身即覆盖，故 `@@M@@\tau\le r@@`；又任一部全体非孤立顶点构成覆盖，故 `@@M@@\tau=r@@` 时每部至少需 `@@M@@r@@` 个非孤立顶点，本构造在所有部同时取到该最小值。**推论**：对足够大的素数 `@@M@@q@@`，存在 `@@M@@(q+1)@@`-边染色完全图，其顶点需恰好 `@@M@@q+1@@` 棵单色树（monochromatic tree）方能覆盖，Gyárfás 树覆盖猜想随之失效。

## 证明思路

先从仿射平面对偶模型出发：在 `@@M@@\mathbb{F}_q^2@@` 中，`@@M@@q+1@@` 个方向各成一部，每部以该方向的 `@@M@@q@@` 条直线为顶点，每个点对应一条由"过该点的各方向直线标签"组成的边。此图相交且 `@@M@@\tau=q@@`。为把覆盖数与各部大小同时抬到 `@@M@@q+1@@`，作者在每个方向改造直线划分：把两条平行线合并（merge）为一块，另取两条直线各保留四个指定点，按循环序 `@@M@@u_0,u_1,u_2,u_3@@` 拆（split）成对角对 `@@M@@\{u_0,u_2\}@@`、`@@M@@\{u_1,u_3\}@@` 两块，每部块数变为 `@@M@@(q-4)+1+4=q+1@@`。

第一个难点：拆分后同一直线上的两点可能失去该方向的公共标签，相交性濒临破裂。解法是把四个指定点安排成每个相邻对 `@@M@@u_{i-1},u_i@@` 恰好同落进某个其他方向的合并块，而相邻对正是被对角拆分分开的点对，于是任意两个保留点仍共享某块，相交性得以保住。

第二个难点：排除混用多部标签、大小至多 `@@M@@q@@` 的覆盖。论文先给出对任意有限域成立的确定性归约：若配置满足占用性（每条未删直线保留至少 `@@M@@\rho q@@` 个点）、核覆盖集中性（覆盖核心 `@@M@@R_0@@` 的 `@@M@@\le q@@` 条线中至少 `@@M@@(1-\rho/4)q@@` 条过同一射影点，即近似铅笔/pencil）及一个局部条件，则 `@@M@@\tau=q+1@@`。逻辑是：小覆盖先被逼成一支铅笔，占用性迫使铅笔内全部非拆分成员入选，剩余预算盖不住过中心的 `@@M@@b@@` 条拆分直线上的 `@@M@@4b@@` 个指定点，按中心在无穷远或在仿射点、以及 `@@M@@b@@` 的大小分情形导出矛盾。

几何数据由概率方法产生：每方向独立抽取两条成分直线生成候选四元组，经不相容图与独立横截（independent transversal）选出兼容组合，并附带"预定 `@@M@@s@@` 个槽"成功概率至多 `@@M@@(K_*/q)^s@@` 的定量输出。删点定理在换测度（密度被 `@@M@@e^{Kq}@@` 倍控制）下证明：`@@M@@\le q@@` 条线的核心覆盖渐近必然盖住几乎全平面，形象计数（profile counting）给出 `@@M@@\exp(-\Omega(q\log q))@@` 的节省，足以支付候选枚举与换测度代价。最后用 Szőnyi–Weiner 素平面稳定性定理把"几乎盖住全平面"化为"一支大铅笔"，这是需要 `@@M@@q@@` 为素数的关键一步。各成功事件取交后概率为正，拼装出所需超图。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准；定理中的阈值是渐近性的，未给出具体数值。姊妹篇在扩域阶 `@@M@@q=s^n@@`（`@@M@@s\equiv2\pmod3@@`、`@@M@@n@@` 为大奇数）给出另一组反例，覆盖不同的秩范围，两篇构造相互独立，姊妹篇仅引用本文附录 A 的三条初等估计。按 OpenAI 官方声明，未经形式化的结果可能有问题，引用前宜待同行评议。

{% endraw %}
