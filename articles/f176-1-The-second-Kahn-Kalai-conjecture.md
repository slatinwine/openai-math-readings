---
layout: default
title: "The second Kahn–Kalai conjecture"
family: "176"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The second Kahn–Kalai conjecture

> 结果族 176：The second Kahn–Kalai conjecture with an edge-count bound　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

往池塘撒网捞一条指定的鱼，网要多密才捞得到？随机图理论问的是同款问题：每对顶点以概率 p 连边，p 多大时才能"捞到"指定图 H 的一份拷贝。这篇论文证明：真实所需密度不超过理论下限乘上一个只随边数对数增长的因子，常数固定——Kahn–Kalai 第二猜想就此收官。随机世界里这种"刚好够用"的现象叫阈值：p 跨过临界值，H 出现的概率会从接近 0 跳到接近 1，论文精确圈出了跳变发生的位置。

**关键词卡片**

- 随机图 G(n,p)（random graph）：每对顶点独立以概率 p 连边的抽签网络。
- 期望阈值 p_E（expectation threshold）：让 H 的每个子图的期望拷贝数都至少为 1/2 的最小密度。
- 包含阈值 p_c（containment threshold）：以至少 1/2 概率含有 H 的最小密度，恒有 p_E ≤ p_c。
- 对数因子（logarithmic factor）：两者之间无法去除的差距来源，比如靠它消除宿主图的孤立顶点。

**看个具体例子**

主定理：`@@M@@p_c\le 2048\,e^{50}\,p_E\,(1+\log_2 h)@@`，其中 h 是 H 的边数。以完美匹配（h=n/2）为例：`@@M@@p_E\approx 1/n@@` 而真实阈值 `@@M@@p_c\approx\log n/n@@`——n=1000 时约 0.007，多出的对数恰好用来消除孤立顶点。下图以 H=三角形示意密度渐增的过程。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="95" y1="55" x2="45" y2="100" stroke="#bbb" stroke-width="2"/>
<line x1="45" y1="100" x2="67" y2="160" stroke="#bbb" stroke-width="2"/>
<line x1="280" y1="55" x2="230" y2="100" stroke="#bbb" stroke-width="2"/>
<line x1="280" y1="55" x2="330" y2="100" stroke="#bbb" stroke-width="2"/>
<line x1="230" y1="100" x2="252" y2="160" stroke="#bbb" stroke-width="2"/>
<line x1="252" y1="160" x2="308" y2="160" stroke="#bbb" stroke-width="2"/>
<line x1="330" y1="100" x2="308" y2="160" stroke="#bbb" stroke-width="2"/>
<line x1="415" y1="100" x2="437" y2="160" stroke="#bbb" stroke-width="2"/>
<line x1="437" y1="160" x2="493" y2="160" stroke="#bbb" stroke-width="2"/>
<line x1="493" y1="160" x2="515" y2="100" stroke="#bbb" stroke-width="2"/>
<line x1="465" y1="55" x2="415" y2="100" stroke="#d62728" stroke-width="3.5"/>
<line x1="465" y1="55" x2="515" y2="100" stroke="#d62728" stroke-width="3.5"/>
<line x1="415" y1="100" x2="515" y2="100" stroke="#d62728" stroke-width="3.5"/>
<circle cx="95" cy="55" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="45" cy="100" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="145" cy="100" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="67" cy="160" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="123" cy="160" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="280" cy="55" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="230" cy="100" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="330" cy="100" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="252" cy="160" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="308" cy="160" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="465" cy="55" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="415" cy="100" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="515" cy="100" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="437" cy="160" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="493" cy="160" r="5.5" fill="#fff" stroke="#333" stroke-width="2"/>
<text x="95" y="200" fill="#555" font-size="13" text-anchor="middle">p 很小</text>
<text x="280" y="200" fill="#555" font-size="13" text-anchor="middle">p 增大</text>
<text x="465" y="200" fill="#555" font-size="13" text-anchor="middle">p 到阈值</text>
<text x="280" y="240" fill="#555" font-size="13" text-anchor="middle">以 H = 三角形为例：密度渐增，红色拷贝 H 出现</text>
</svg>

</div>

**为什么值得关心**

它补上了 Kahn–Kalai 阈值纲领的最后一环：期望阈值与真实阈值之间，只差一个不得不有的对数因子。此前最好结果还带着平方乃至立方的对数，本文把它压到一次方，常数还完全显式。

> 已 Lean 形式化

## 一句话结论

证明了卡恩–卡莱第二猜想：任意有 `@@M@@h\ge1@@` 条边、至多 `@@M@@n@@` 个顶点的图 `@@M@@H@@`，其在 `@@M@@G(n,p)@@` 中的出现阈值不超过 `@@M@@C\,p_{\mathrm E}(n,H)(1+\log_2 h)@@`，`@@M@@C@@` 为普适常数——期望阈值与真实阈值只差一个依赖边数的对数因子。

## 问题背景

随机图 `@@M@@G(n,p)@@` 在每对顶点间独立以概率 `@@M@@p@@` 连边。经典问题是：给定目标图 `@@M@@H@@`（可随 `@@M@@n@@` 增长），`@@M@@p@@` 多大时 `@@M@@G(n,p)@@` 以恒定概率包含 `@@M@@H@@` 的一份拷贝？这可追溯到 Erdős–Rényi 与 Bollobás 的经典阈值理论。显然的必要条件是每个子图 `@@M@@F\subseteq H@@` 的期望拷贝数不太小；使所有子图期望拷贝数至少为 `@@M@@1/2@@` 的最小密度称为图期望阈值（graph expectation threshold）`@@M@@p_{\mathrm E}(n,H)@@`，以概率 `@@M@@1/2@@` 包含 `@@M@@H@@` 的最小密度称为包含阈值（containment threshold）`@@M@@p_{\mathrm c}(n,H)@@`，恒有 `@@M@@p_{\mathrm E}\le p_{\mathrm c}@@`。Kahn 与 Kalai 猜想两者只差一个对数因子（第二猜想）。对数差距确属必要：完美匹配的 `@@M@@p_{\mathrm E}=\Theta(1/n)@@` 而 `@@M@@p_{\mathrm c}=\Theta(\log n/n)@@`，多出的对数用于消除宿主图的孤立顶点。此前最好结果是 Dubroff–Kahn–Park 的 `@@M@@O(p_{\mathrm E}\log^3 n)@@` 与 Tran 的 `@@M@@O(p_{\mathrm E}\log^2(2e(H)))@@`，单对数版本仅在树和平均度不低于最大度对数的图上获证。

## 主要结果

主定理：对每个 `@@M@@n\ge2@@` 及每个恰有 `@@M@@h=e(H)\ge1@@` 条边、至多 `@@M@@n@@` 个顶点的有限简单图 `@@M@@H@@`，

`@@M@@Dp_{\mathrm c}(n,H)\le\min\{1,\;2048\,\mathrm e^{50}\,p_{\mathrm E}(n,H)\,(1+\log_2 h)\}.@@`

由 `@@M@@h\le n^2@@` 立得 `@@M@@p_{\mathrm c}(n,H)\le6144\,\mathrm e^{50}\,p_{\mathrm E}(n,H)\log_2 n@@`。拷贝按普通拷贝（ordinary copy）计，不要求导出，允许所选顶点间有额外边；`@@M@@p_{\mathrm E}(n,H)@@` 是使每个子图 `@@M@@F\subseteq H@@` 的期望拷贝数都 `@@M@@\ge1/2@@` 的最小密度。常数显式而普适，`@@M@@H@@` 可随 `@@M@@n@@` 变化；把基准 `@@M@@1/2@@` 换成原文的 `@@M@@1@@` 只差常数因子。

## 证明思路

证明分三步：先把 `@@M@@H@@` 剖分成记录全部扩展历史的概率树（probability tree），再用重采样同时削减各层，最后迭代取并。

先建图层级。记 `@@M@@q=p_{\mathrm E}(n,H)@@`、`@@M@@\sigma=128q@@`。对非空边集 `@@M@@I\subseteq H@@`，在其子图中选 `@@M@@S@@` 最大化 `@@M@@R_\sigma(I,S)=\sigma^{-|S|}\Pr(S_0\subseteq\boldsymbol I)@@`，`@@M@@\boldsymbol I@@` 为 `@@M@@I@@` 的均匀拷贝。期望约束与计数估计迫使选出的 `@@M@@S@@` 满足 `@@M@@|S|<|I|/17@@`，反复选取得嵌套链 `@@M@@\varnothing=H_0\subset\cdots\subset H_k=H@@`。再以副本为节点建树：子节点是包含它的 `@@M@@H_i@@` 副本，弧标签为新增边；沿任一路径标签两两不交，并为 `@@M@@H@@` 的副本，相邻层新增边数按 16 倍递增。`@@M@@R_\sigma@@` 的极大性给出 `@@M@@\Pr(J\subseteq A)\le\sigma^{|J|}@@`，即每层子分布是 `@@M@@\sigma@@`-spread（分散）的，此步即 Tran 的 spread-link 构造。

再做整树同削：用 Mossel–Niles-Weed–Sun–Zadik 的种植—后验重采样（planted posterior resampling），把源标签种进独立随机集 `@@M@@W\sim\mu_\rho@@`，按后验概率选目标标签，保留碎片 `@@M@@T=A_b\setminus W@@`。局部引理表明：在 spread 且 `@@M@@a/\rho\le\mathrm e^{-50}@@` 时，碎片长度以 `@@M@@\ge1-\mathrm e^{-9m}@@` 的概率减半，并附带控制 `@@M@@W@@` 在目标外坐标上测度畸变的不等式。难点是同一份 `@@M@@W@@` 被全树复用带来的依赖——Tran 的耦合猜想（coupling conjecture）想以此只付一次对数代价；本文绕开该猜想，改用树归约：任一子树内的标签都与进入该子树的弧标签不交，故其递归势函数只依赖 `@@M@@W@@` 在该标签之外的表现，畸变不等式恰好适用。自叶向根的势函数估计证明根"变坏"概率 `@@M@@<1/4@@`：单次抽取以 `@@M@@\ge3/4@@` 的概率把每层容量减半，spread 至多退化 `@@M@@(1-\mathrm e^{-m_j})^{-1}@@` 倍。

最后迭代：每次成功后换新的独立 `@@M@@W@@`，各层容量降为 `@@M@@\lfloor\ell_i/2^t\rfloor@@`；因容量按几何级数增长，spread 累计退化乘积小于 `@@M@@4@@`。`@@M@@s=\lfloor\log_2\ell_k\rfloor+1@@` 次成功后所有容量归零，回溯可知历次抽取之并含某条完整路径的标签并，即 `@@M@@H@@` 的一个副本。预设 `@@M@@4s@@` 次抽取取并，密度至多 `@@M@@16\,\mathrm e^{50}\sigma(1+\log_2\ell_k)@@`，成功概率 `@@M@@\ge2/3@@`；代回 `@@M@@\sigma=128q@@`、`@@M@@\ell_k\le h@@` 即得主定理。

## 可信度与备注

主结果已提供 Lean 形式化（见结果族 176 的 Lean 文档），正文从局部重采样、树覆盖到图层级逐环给出完整证明。本文是系列工作的收官：Park–Pham 以最小片段论证解决抽象版第一猜想，Dubroff–Kahn–Park 与 Tran 逐步压缩对数损失，此处补上最后一环；文中提及的同项目"积分/分数期望阈值等价"定理是平行的姊妹结果，但作者明确声明本证明并未使用它。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，可信度较高，常数细节以论文与形式化代码为准。

{% endraw %}
