---
layout: default
title: "A linear list-coloring bound in terms of the Hadwiger number"
family: "157"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A linear list-coloring bound in terms of the Hadwiger number

> 结果族 157：Graph coloring, clique minors, and Colin de Verdière invariants　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

考试发调色盘，但每人盘里的颜色清单不同：你要从自己的清单挑色，相邻两人不能撞色。清单要多长，才能保证任何图都挑得开？论文证明：只要每份清单有 C·h(G) 种颜色——h 是 Hadwiger 数，C 是绝对常数——就永远够用。

**关键词卡片**

- 列表染色（list coloring）：每个顶点从自己的颜色清单里选色。
- 列表色数 ℓ(G)（list chromatic number）：保证总能正常染色的最小清单长度。
- Hadwiger 数 h(G)：把连通块收缩成点后能捏出的最大完全图阶数。
- 编织（woven）：大图内部能"织"出承载指定路线的团子式的结构性质，证明的组装车间。
- 桶（bucket）：把所有列表的颜色全局分组，各桶内部自行染色、互不冲突的调度装置。

**看个具体例子**

最小情形的直觉：给三角形的三个顶点都发清单 {1,2}，只有两色，必然撞色；清单扩到 {1,2,3} 就总能染开：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="30" text-anchor="middle" font-size="16">列表染色：各选各的清单</text><line x1="110" y1="75" x2="230" y2="75" stroke="#333"/><line x1="110" y1="75" x2="170" y2="190" stroke="#333"/><line x1="230" y1="75" x2="170" y2="190" stroke="#333"/><circle cx="110" cy="75" r="10" fill="#fff" stroke="#333"/><circle cx="230" cy="75" r="10" fill="#fff" stroke="#333"/><circle cx="170" cy="190" r="10" fill="#fff" stroke="#333"/><text x="110" y="58" text-anchor="middle" font-size="14">{1,2}</text><text x="230" y="58" text-anchor="middle" font-size="14">{1,2}</text><text x="170" y="222" text-anchor="middle" font-size="14">{1,2}</text><text x="170" y="250" text-anchor="middle" font-size="14" fill="#c0392b">只有两色，必然撞色 ✗</text><line x1="330" y1="75" x2="450" y2="75" stroke="#333"/><line x1="330" y1="75" x2="390" y2="190" stroke="#333"/><line x1="450" y1="75" x2="390" y2="190" stroke="#333"/><circle cx="330" cy="75" r="10" fill="#e74c3c"/><circle cx="450" cy="75" r="10" fill="#3498db"/><circle cx="390" cy="190" r="10" fill="#f1c40f"/><text x="330" y="58" text-anchor="middle" font-size="14">{1,2,3}</text><text x="450" y="58" text-anchor="middle" font-size="14">{1,2,3}</text><text x="390" y="222" text-anchor="middle" font-size="14">{1,2,3}</text><text x="390" y="250" text-anchor="middle" font-size="14" fill="#2e7d32">三色在手，总能染开 ✓</text></svg>

</div>

所以 ℓ(K₃)=3=h(K₃)。论文先解决至多约 t^11/10 个点的小图，再用高连通子图抽取推向任意阶数；定理的威力在大图：`@@M@@\ell(G)\le C\,h(G)@@`，清单长度只需与团子式阶数成正比；而有人构造出无 Kₜ 子式却要 (2−ε)t 色的图，故 C 至少是 2——线性阶恰到好处。

**为什么值得关心**

在 Hadwiger 猜想（系数 1）被同族反例推翻后，这篇肯定了它的线性松弛，而且证明的是更强的列表染色版本（常数 C 未加优化）。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明存在绝对常数 `@@M@@C@@`，使每个有限非空简单图满足 `@@M@@\chi_{\mathrm{list}}(G)\le Ch(G)@@`，肯定地解决 Kawarabayashi–Mohar 的线性列表 Hadwiger 猜想；对每点取相同列表即得 `@@M@@\chi(G)\le Ch(G)@@`。

## 问题背景
列表染色（list coloring）由 Vizing（1976）与 Erdős–Rubin–Taylor（1980）各自引入：每个顶点获得一个有限颜色列表，`@@M@@\mathcal L@@`-染色要求各点从自己的列表取色；列表色数 `@@M@@\ell(G)=\chi_{\mathrm{list}}(G)@@` 是保证总能正常染色的最小列表长度。Hadwiger 猜想 `@@M@@\chi(G)\le h(G)@@` 已被同族姊妹篇否定，其线性松弛追问：绝对常数能否替代系数 1？Kawarabayashi 与 Mohar（2007）就列表版提出这一猜想。此前最好界距线性尚远：Kostochka–Thomason 密度界经贪心算法给出 `@@M@@O(t\sqrt{\log t})@@`；普通染色已推进到 `@@M@@O(t\log\log\log t)@@`（Liu–Luo），列表染色最好结果是 Gu–Xu（2026 年 10 月）的 `@@M@@O(t\log\log t)@@`。下界方面，Steiner 证明无 `@@M@@K_t@@` 子式的图列表色数可达 `@@M@@(2-\varepsilon)t@@`，故任何这样的 `@@M@@C@@` 必至少为 2。难点有二：采样出的稳定集未必有全体成员都可用的公共颜色；拼装子式的路径可含任意多个点，删除代价必须按结构而非点数计费。

## 主要结果
定理 1.1：存在绝对整数 `@@M@@C\ge1@@`，使每个有限非空简单图 `@@M@@G@@` 满足
`@@M@@D\ell(G)\le Ch(G).@@`
常数与图的阶数、列表指派及调色板大小全部无关。对每点取相同列表 `@@M@@\{1,\dots,\ell(G)\}@@` 立得推论 1.2：`@@M@@\chi(G)\le Ch(G)@@`。线性列表 Hadwiger 猜想由此获得肯定解决；作者说明常数未加优化，且由 Steiner 的例子 `@@M@@C\ge2@@` 不可避免。

## 证明思路
证明先小图、后大图。第一步（命题 3.1）处理小图：无 `@@M@@K_t@@` 子式且至多 `@@M@@t^{11/10}@@` 个点的图是 `@@M@@Lt@@`-可列表染色的。把所有列表的并分成若干"桶"，每种颜色全局归入唯一桶；随机分桶保证在任何剩余图确定之前，每点已拥有足够多合格桶。核心的"合格稀释"引理逐段把分数色数上界减半：用 Liu–Luo 的有界稳定集采样（每点入样概率 `@@M@@1/(2r)@@`，集合大小至多 `@@M@@\lceil n/r\rceil@@`，试验次数 `@@M@@N=\lceil Br\log(2\max\{1,t/r\})\rceil@@`）只在合格点中删除稳定集。同一桶中被删的点构成一个稳定集，各点从桶中自选可用颜色，不同桶之间不会冲突，全程只需 `@@M@@O(t)@@` 个桶。稀释引理用反证法：若每次采样后分数色数仍超过 `@@M@@r/2@@`，则确定性分隔分解给出一个固定的高连通子图，其剩余部分期望分数色数仍大；独立重复产生两两不交的私有顶点集，各自支撑一个团模型；把 `@@M@@t@@` 个标签分成小块，对每块及每对块各用一个模型，再用保持高连通性的剩余部分把同标签的袋相连，即拼出被排除的 `@@M@@K_t@@` 子式。

第二步把小图结论推向任意阶数。列表抽取引理以线性损耗抽出高连通子图；加性列表删除引理为小点集预留颜色并控制其与所有剩余点的交互，其概率估计只测试多项式多个例外点，与图的阶数和调色板大小无关——最短路径系统提供所需稀疏性，使删除估计对任意长的路径也成立。密度论证还供应小块的高连通"城区"（district），供拼装团模型时改道路径。可分性引理断言：列表色数足够大的图要么已含所需的团子式，要么分成两个不交子图且几乎保住全部列表色数；每一步由一个小城区为模型袋提供新邻接、由一个独立汇合点接续携带袋前进的路径，删除估计作用于全部历史最短路径，包括已不再被模型使用的点。

最后是递归编织定理：`@@M@@Ka@@`-连通且 `@@M@@\ell\ge Qa@@` 的图是 `@@M@@(a,3a)@@`-编织的（woven），即可建出袋含指定根、且实现指定端点对路径的团模型。先给终端设互异的代理点、以两条最短路径接入小城区并腾出新鲜区域；把根标签分成三块，可分性给出三个不交城区，每一对块共享一个城区，每次递归调用只需约 `@@M@@2\lceil a/3\rceil\le3a/4@@` 个根，而任意标签对都在某个城区相遇从而获得邻接；编织性允许连接路径穿过递归城区时被重接。对 `@@M@@a@@` 强归纳即证；`@@M@@h\ge64a@@` 的大子式情形由生根引理直接处理。

## 可信度与备注
主结果暂无 Lean 形式化证明；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。文中分数子式界、连通性抽取、终端分组定理三项外部输入系引用复述而非自证。与同族两篇反例互补：姊妹篇否定系数 1 的 Hadwiger 与 Colin de Verdière 染色猜想，本文证明线性列表版本成立，并结合 `@@M@@h(G)\le\mu(G)+1@@` 给出 `@@M@@\chi_{\mathrm{list}}(G)\le C(\mu(G)+1)@@`。

{% endraw %}
