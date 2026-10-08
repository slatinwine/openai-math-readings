---
layout: default
title: "Graph Decompositions at the Integral Expectation Threshold"
family: "175"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Graph Decompositions at the Integral Expectation Threshold

> 结果族 175：Talagrand's expectation thresholds, discrete convexity, and graph decompositions　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象往桌上随机撒拼图碎片，要拼出一个指定的复杂图案。整体硬拼往往得付一笔"对数级加价"；这篇论文证明：可以预先把图案拆成固定数目的小包，每包单独拼，价格只比理论最低价贵一个固定倍数——加价被彻底抹掉了。关键在于拆包发生在撒点之前：分块方案只由图案本身决定；至于各包拼出来后落在桌面哪个位置、共享的顶点要不要对齐，都互不相干。

**关键词卡片**

- 随机图 G(n,p)（random graph）：每对顶点独立以概率 p 连边的"抽签网络"。
- 包含阈值 p_c（containment threshold）：让 G(n,p) 以至少一半概率含有目标图 H 的最小 p。
- 期望阈值 q（integral expectation threshold）：用小集合"便宜地"覆盖 H 一切出现方式的成本度量，总有 q ≤ p_c。
- 图分解（graph decomposition）：在撒点之前把 H 的边预先拆成常数多块，各块独立嵌入、互不干扰。
- 退化度（degeneracy）：衡量图局部稀疏程度的参数，越小越像森林。

**看个具体例子**

定理：每个图 H 的边集可拆成 k 块（k 是绝对常数），每块满足 `@@M@@p_c(H_i)\le L\,q(H)@@`。下图把一个 7 顶点图的边预先染成三色，即三块；若 `@@M@@q(H)=0.001@@`，则每块在密度 `@@M@@0.001L@@` 处就以至少 1/2 的概率出现在 `@@M@@G(n,p)@@` 里。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="32" fill="#555" font-size="14" text-anchor="middle">把图的边预先拆成常数块（示意）</text>
<line x1="150" y1="70" x2="320" y2="60" stroke="#d62728" stroke-width="3"/>
<line x1="320" y1="60" x2="450" y2="150" stroke="#d62728" stroke-width="3"/>
<line x1="450" y1="150" x2="320" y2="240" stroke="#d62728" stroke-width="3"/>
<line x1="320" y1="240" x2="150" y2="230" stroke="#1f77b4" stroke-width="3"/>
<line x1="150" y1="230" x2="60" y2="150" stroke="#1f77b4" stroke-width="3"/>
<line x1="60" y1="150" x2="150" y2="70" stroke="#1f77b4" stroke-width="3"/>
<line x1="150" y1="70" x2="260" y2="150" stroke="#2ca02c" stroke-width="3"/>
<line x1="450" y1="150" x2="260" y2="150" stroke="#2ca02c" stroke-width="3"/>
<line x1="150" y1="230" x2="260" y2="150" stroke="#2ca02c" stroke-width="3"/>
<circle cx="150" cy="70" r="7" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="320" cy="60" r="7" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="450" cy="150" r="7" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="320" cy="240" r="7" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="150" cy="230" r="7" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="60" cy="150" r="7" fill="#fff" stroke="#333" stroke-width="2"/>
<circle cx="260" cy="150" r="7" fill="#fff" stroke="#333" stroke-width="2"/>
<line x1="90" y1="265" x2="125" y2="265" stroke="#d62728" stroke-width="3"/>
<text x="132" y="270" fill="#555" font-size="13">块 1</text>
<line x1="210" y1="265" x2="245" y2="265" stroke="#1f77b4" stroke-width="3"/>
<text x="252" y="270" fill="#555" font-size="13">块 2</text>
<line x1="330" y1="265" x2="365" y2="265" stroke="#2ca02c" stroke-width="3"/>
<text x="372" y="270" fill="#555" font-size="13">块 3</text>
</svg>

</div>

**为什么值得关心**

它是 Talagrand 阈值纲领的关键一步：分块之后，Kahn–Kalai 型比较里的对数损失消失，而完美匹配的例子又说明整体意义下的对数删不掉——分块正是绕开它的正确姿势。其核心输入（离散凸性定理）已形式化，但本篇主结果尚未。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了 Ascoli–He–Park–Talagrand 图分解猜想：任何图的边都可预先拆成常数多块，每块的普通包含阈界不超过原图积分期望阈界的普适常数倍，从而在"分块"意义下彻底消除了 Kahn–Kalai 型阈值比较中的对数损失。

## 问题背景

随机图 `@@M@@G(n,p)@@` 中何时出现给定图 `@@M@@H@@` 的拷贝？普通阈界 `@@M@@p_c(H;n)@@` 是使包含概率达到 `@@M@@1/2@@` 的参数，而积分期望阈界（integral expectation threshold）`@@M@@q(H;n)@@` 衡量"用小集合便宜地覆盖所有包含事件"的能力，总有 `@@M@@q\leq p_c@@`。Kahn 与 Kalai 在 2007 年猜想两者只差一个对数因子，Park 与 Pham 于 2024 年证明了 `@@M@@p_c(H;n)\leq Cq(H;n)\log|E(H)|@@`。对数损失能否去掉？Ascoli、He、Park、Talagrand 于 2026 年提出图分解猜想：只要允许把目标图拆成不依赖随机宿主的常数块，每块的阈界就可控制在 `@@M@@O(q)@@`。他们证明了有界退化度的情形，以及退化度与最大度同时受限的另一些情形，并在其论文第 8 节指出高、低度顶点之间的二部边是剩余的主要困难。

## 主要结果

定理 1.1：存在绝对整数 `@@M@@k\geq2@@` 与绝对常数 `@@M@@L\geq1@@`，对每个 `@@M@@n\geq2@@` 与每个至多 `@@M@@n@@` 个顶点的图 `@@M@@H@@`，其边集有划分 `@@M@@E(H)=E(H_1)\,\dot\cup\,\cdots\,\dot\cup\,E(H_k)@@`，使每块满足 `@@M@@p_c(H_i;n)\leq Lq(H;n)@@`。这里 `@@M@@q(H;n)@@` 是使覆盖族 `@@M@@\mathcal C@@` 的成本 `@@M@@c_p(\mathcal C)=\sum_{S}p^{|S|}\leq1/2@@` 的最大参数 `@@M@@p@@`。要点有三：块数与常数绝对有效；划分只依赖 `@@M@@H,n@@`，在采样之前确定；各块的嵌入互不相干——共享顶点不必映到同一位置。定理意味着每个固定块都在密度 `@@M@@Lq@@` 处以至少 `@@M@@1/2@@` 的概率出现于 `@@M@@G(n,p)@@`。

## 证明思路

先取 `@@M@@r=2q@@`，调用同族姊妹篇"离散凸性定理"（常数 `@@M@@K_0=2^{75}@@`）的推论：对任何高概率类 `@@M@@\mathcal D@@`（`@@M@@\mu_r(\mathcal D)\geq1-1/K_0@@`），必有一个 `@@M@@H@@` 的标号拷贝落在 `@@M@@K_0@@` 个 `@@M@@\mathcal D@@` 中成员的并里。把每条边指派给一个包含它的典型图，得到 `@@M@@K_0@@` 份初始块，这是整个构造的骨架。初始块各自含于一个指定的典型图中，为后续传递论证保存了"源"信息。

再按退化度（degeneracy）`@@M@@d@@` 分治。大退化度情形：先把度超过 `@@M@@\sqrt n@@` 的顶点集逐步扩大成 `@@M@@Y@@`，使外部每点在 `@@M@@Y@@` 内至多 `@@M@@2d@@` 个邻居且 `@@M@@|Y|\leq n^{2/3}@@`，于是边被切成"Y 内、Y 外、跨切口"三部分。Y 内与 Y 外的边经退化度分裂成最大度不超过 `@@M@@n^{2/3}@@`、支撑很小的块，由分层贪心匹配的直接嵌入命题处理。跨切口的二部（bipartite）边是真正的难点：固定 `@@M@@Y@@` 嵌入时需为每个外部顶点找到相邻于其至多 `@@M@@s@@` 个指定邻居的不同像点，Hall 准则要求对任意候选集都有足够像点，单一典型类无法保证。作者的压缩引理（compression lemma）先把任意需求族压缩成至多 `@@M@@\lceil2r^{-s}\rceil@@` 个"代表需求"，再对一切小 `@@M@@Y@@` 与小需求族同时做 Hoeffding 集中来定义 `@@M@@\mathcal D@@`，使"源和"与"目标和"两类检验对所有测试同时成立；配合密度放大 `@@M@@r_*=1-(1-r)^{32}@@`，Hall 定理给出匹配（matching），得 `@@M@@p_c\leq32r=64q@@`。有界退化度情形则把图拆成森林，按深度奇偶分裂成星森林（star forest），逐块用"新鲜中心"贪心嵌入，阈界不超过 `@@M@@2Aq@@`，再由单调性 `@@M@@q(J;n)\leq q(H;n)@@` 即得 `@@M@@p_c\leq Lq@@`。最后清点，各情形块数均不超过 `@@M@@k@@`。

## 可信度与备注

本文主结果尚未形式化；其关键输入——离散凸性定理——在同族姊妹篇中已有 Lean 形式化证明，其余图分解与嵌入论证均在本文内自包含给出。按 OpenAI 官方声明"未经形式化的结果可能有问题"，读者宜以社区核验为准。

{% endraw %}
