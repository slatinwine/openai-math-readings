---
layout: default
title: "Paired states and Hamiltonian cycles in cubic bipartite planar graphs"
family: "180"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Paired states and Hamiltonian cycles in cubic bipartite planar graphs

> 结果族 180：Barnette's Hamiltonian-cycle conjecture　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

骰子的骨架是一张"每个角恰好伸出 3 条棱"的网，还能黑白二染、画在平面上互不交叉。1969 年有人猜：凡是这类够硬实的"多面体骨架"（任取两个角都拎不散），一定存在一条"一日游"路线——经过每个顶点恰好一次再回到起点。这就是 Barnette 猜想，悬置五十余年后被这篇论文证明。别小看"二部"这顶帽子：去掉它的 Tait 猜想，早在 1946 年就被 Tutte 的反例击倒了。

**关键词卡片**

- 三正则图（cubic graph）：每个顶点的度数恰为 3，像立方体骨架。
- 二部图（bipartite graph）：顶点可黑白二染、每条边连异色两点的图。
- Hamilton 圈（Hamiltonian cycle）：经过每个顶点恰好一次的闭合路线。
- 3-点连通（3-vertex-connected）：去掉任意两个顶点图仍连通，是多面体骨架的刚性保证。

**看个具体例子**

立方体骨架满足全部条件（三正则、二部、平面、3-点连通），它的一条 Hamilton 圈如下图红线：8 个顶点各到一次、首尾相接；圈外恰好剩 4 条灰棱，每个顶点各分到一条——这正是"三正则"的体现。定理说任何满足条件的图都藏着这样一条红线，甚至可以要求它绕开你事先指定的任何一条边。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="34" fill="#555" font-size="14" text-anchor="middle">立方体骨架</text>
<line x1="190" y1="55" x2="190" y2="195" stroke="#bbb" stroke-width="2"/>
<line x1="350" y1="55" x2="350" y2="195" stroke="#bbb" stroke-width="2"/>
<line x1="235" y1="90" x2="305" y2="90" stroke="#bbb" stroke-width="2"/>
<line x1="235" y1="160" x2="305" y2="160" stroke="#bbb" stroke-width="2"/>
<line x1="190" y1="55" x2="350" y2="55" stroke="#d62728" stroke-width="3.5"/>
<line x1="350" y1="55" x2="305" y2="90" stroke="#d62728" stroke-width="3.5"/>
<line x1="305" y1="90" x2="305" y2="160" stroke="#d62728" stroke-width="3.5"/>
<line x1="305" y1="160" x2="350" y2="195" stroke="#d62728" stroke-width="3.5"/>
<line x1="350" y1="195" x2="190" y2="195" stroke="#d62728" stroke-width="3.5"/>
<line x1="190" y1="195" x2="235" y2="160" stroke="#d62728" stroke-width="3.5"/>
<line x1="235" y1="160" x2="235" y2="90" stroke="#d62728" stroke-width="3.5"/>
<line x1="235" y1="90" x2="190" y2="55" stroke="#d62728" stroke-width="3.5"/>
<circle cx="190" cy="55" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="350" cy="55" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="350" cy="195" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="190" cy="195" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="235" cy="90" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="305" cy="90" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="305" cy="160" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="235" cy="160" r="6" fill="#fff" stroke="#333" stroke-width="2"/>
<text x="280" y="235" fill="#555" font-size="13" text-anchor="middle">红线：Hamilton 圈——8 个顶点各经过一次、首尾相接</text>
<text x="280" y="258" fill="#777" font-size="13" text-anchor="middle">灰线：不在圈里的另外 4 条棱</text>
</svg>

</div>

**为什么值得关心**

它是 Tait 猜想被反例否定之后悬置最久的图论名题之一，证明走的是对偶三角剖分上"配对状态"的全新路线；注意论文只证存在性，不提供找圈的算法。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明了 1969 年问世的 Barnette 猜想：每个有限、简单、三正则（cubic）、二部（bipartite）、平面且 3-点连通的图都存在 Hamilton 圈（Hamiltonian cycle）。证明走对偶三角剖分上"配对状态+加权相消"的全新路线，并附带单边回避等加强推论。

## 问题背景

一个图称为三正则，若每个顶点的度数都是 3；称为二部，若顶点能分成两类而每条边都跨在两类之间。Hamilton 圈是经过每个顶点恰好一次的圈。19 世纪末 Tait 猜想每个三次多面体图（平面、3-点连通、三正则）都有 Hamilton 圈——它一旦成立即可推出四色定理，却被 Tutte 于 1946 年的反例否定。加上"二部"限制后得到的 Barnette 猜想（由 Grünbaum 记录于 1969 年滑铁卢会议文集）悬置了五十余年。此前最好结果都对面的大小设限：Goodey（1975）处理面全为四边形或六边形的情形，Feder 与 Subi（2006）、Kardoš（2020）推进到面至多六边形，Schnieders（2025）做到面至多八边形。真正的卡点在于：度数全为 2 的支撑子图可能裂成多个圈，局部调整无法保证把它们并成唯一一个圈，必须寻找全局性论证。

## 主要结果

主定理（论文 Theorem 1.1）：每个有限简单无向图若是三正则、二部、平面且 3-点连通的，则必有 Hamilton 圈。

证明的核心是等价的对偶命题（Theorem 2.2）：设 `@@M@@T@@` 是球面三角剖分（triangulation），其面被黑白二染色且每条边两侧颜色相反（Stein 的区域划分表述；Alt–Payne–Schmidt–Wood 2016 已证 Hamilton 性等价于把 `@@M@@T@@` 的顶点分成两个集合、每个集合都诱导一棵树，其中"诱导"要求包含类内的全部边），则对任意面三角形 `@@M@@t_0@@` 及其任一条边 `@@M@@e_0@@`，都能把顶点分成两类，使 `@@M@@e_0@@` 的两个端点同属一类、`@@M@@t_0@@` 的第三个顶点属另一类，且每类都诱导一棵树。

由此直接得到两个加强推论：其一（Corollary 7.1），可要求 Hamilton 圈避开任意指定的一条边——这正是 Kelmans 一脉证明的与 Barnette 猜想等价的全局加强；其二（Corollary 7.2），经由 Gorsky–Steiner–Wiederrecht（2023）的等价定理，每个有限简单三正则 3-点连通 Pfaffian 二部图都是 `@@M@@P_4@@`-Hamiltonian 的：任何三边路径都落在某个 Hamilton 圈内。

## 证明思路

整个证明是"对偶 + 全局相消"。先把图 `@@M@@G@@` 换成球面对偶三角剖分 `@@M@@T@@`：3-点连通保证 `@@M@@T@@` 简单，三正则保证对偶面都是三角形，`@@M@@G@@` 的二部性恰好给 `@@M@@T@@` 的面黑白二染色。于是问题化为上述 Stein 型顶点划分。

再引入"状态"（state，源自 Tutte 的 trinity 理论）：取一个黑三角 `@@M@@t_0@@` 为外面，其三顶点称为根；其余黑三角之集 `@@M@@A@@` 与非根顶点之集 `@@M@@X@@` 数目相等，状态即满足 `@@M@@r(t)\in V(t)@@` 的双射 `@@M@@r:A\to X@@`；一对状态（pair）要求两个状态在每个黑三角处取值都不同，等价于关联二部图的两条边不交完美匹配。第一步证明（无分离三角形时）"对"存在：用整值最大流—最小割化为割不等式，再译成平面密度不等式 `@@M@@e(U)-b(U)\le 2|U|-4@@`，对每个连通分量用 Euler 公式与带符号边侧计数验证。

接着是全文引擎——盘恒等式（disk identity）：由状态导出的任何简单有向圈的 `@@M@@\delta@@`-和必为 `@@M@@\pm 3@@`，证明只用 Euler 公式加上匹配计数 `@@M@@B=I+l@@`。有了它，考察有限指数和 `@@M@@Z(x)=\sum i^{J(r,s)}\exp(x\omega(s))@@`。先固定第二状态 `@@M@@s@@`：若 `@@M@@Q_s@@`（各黑三角中与 `@@M@@s(t)@@` 相对的边）含圈，则沿该圈把 `@@M@@r@@` 的取值换成第三顶点是一个对合，`@@M@@J@@` 恰好改变 `@@M@@\pm 2@@`，相位反号而权重不变（权重只依赖 `@@M@@s@@`），故此类项两两相消。再按无向边集 `@@M@@D@@` 分组：`@@M@@D@@` 的分量是圈，组内成员恰是各圈的独立定向。利用黑三角中心到三顶点的"辐条"上的正环流，每个圈逆时针定向的权和严格更大，于是每组的每个因子在 `@@M@@x=0@@` 处恰有一阶零点；圈数最少的那些组首项相位一致、幅度同号，无法相消，故 `@@M@@Z\neq 0@@`，必存在使 `@@M@@Q_s@@` 为森林的对。

最后从森林态复原两棵树：先看出度计数可知森林每个分量恰含一个根；删去相应辐条后，剩余图是辐条图的支撑树，取平面树对偶得到白面上的支撑树，并据此在每个黑、白面各选一条边得边集 `@@M@@P@@`。若 `@@M@@P@@` 含圈，把"每面恰一条选中边"的带号计数与三角剖分的边侧计数联立，可得该圈 `@@M@@\delta@@`-和为零，与盘恒等式的 `@@M@@\pm 3@@` 矛盾，故 `@@M@@P@@` 是森林；其补对偶连通且处处 2 度，构成一条 Jordan 曲线，按曲线两侧给顶点标号即得两类各诱导一棵树，且 `@@M@@t_0@@` 处的同号边恰为 `@@M@@e_0@@`。存在分离三角形时沿圈切分成两块较小的三角剖分（帽面染色由整除性论证可行），利用 `@@M@@e_0@@` 处方归纳粘合，两个诱导树沿一个顶点或一条边粘成树，完成定理。

## 可信度与备注

按任务元数据，本文主结果尚无 Lean 形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。本批结果族 180 仅此一篇主文，但其两个推论分别经由已发表的等价定理（APSW 2016 的划分等价、GSW 2023 的 Pfaffian 等价）与主结果互相印证。另需注意：论证是纯存在性的，作者明确说明不给出圈数的界，也不宣称多项式时间构造算法。

{% endraw %}
