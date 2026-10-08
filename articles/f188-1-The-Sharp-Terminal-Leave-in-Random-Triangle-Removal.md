---
layout: default
title: "The sharp terminal leave in random triangle removal"
family: "188"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The sharp terminal leave in random triangle removal

> 结果族 188：The sharp terminal leave in random triangle removal　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一场"拆手链"游戏：n 个人两两拉手结成一张大网，每一轮随机挑出三个还彼此拉着手的幸运儿，让他们三人同时松开彼此的手；如此重复，直到再也凑不出三人互拉。散场时网上总会剩下一些零散的手——这篇论文精确算出了这些"剩手"的数量：约 `@@M@@n^{3/2}/(2\sqrt2)@@` 条，连常数都分毫不差。从 1990 年 Bollobás–Erdős 猜测残尾规模为 `@@M@@n^{3/2}@@` 起，指数早已确定，悬而未决的正是这个精确常数。

**关键词卡片**

- 完全图（complete graph）：任意两点之间都连一条边的图，好比"人人相识"的朋友圈。
- 随机三角移除（random triangle removal）：每一步等可能地挑一个现存的三角形，把它的三条边一起删掉。
- 残尾（leave）：过程终止后剩下的边——再也拼不进任何三角形的"边角料"。
- `@@M@@L^2@@` 收敛（`@@M@@L^2@@` convergence）：结果与常数之差的平方平均趋于零，比"大概率接近"更强的说法。
- Joos–Kühn 猜想：残尾规模应有精确渐近常数的猜测，本文敲定三角形情形的 `@@M@@1/(2\sqrt2)@@`。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="100" y="30" text-anchor="middle" font-size="15" fill="#222">开始：完全图 K_n</text>
<line x1="100" y1="90" x2="48" y2="128" stroke="#888" stroke-width="1.5"/>
<line x1="100" y1="90" x2="152" y2="128" stroke="#888" stroke-width="1.5"/>
<line x1="48" y1="128" x2="152" y2="128" stroke="#888" stroke-width="1.5"/>
<line x1="100" y1="90" x2="68" y2="188" stroke="#b03030" stroke-width="3"/>
<line x1="100" y1="90" x2="132" y2="188" stroke="#b03030" stroke-width="3"/>
<line x1="68" y1="188" x2="132" y2="188" stroke="#b03030" stroke-width="3"/>
<line x1="48" y1="128" x2="68" y2="188" stroke="#888" stroke-width="1.5"/>
<line x1="48" y1="128" x2="132" y2="188" stroke="#888" stroke-width="1.5"/>
<line x1="152" y1="128" x2="68" y2="188" stroke="#888" stroke-width="1.5"/>
<line x1="152" y1="128" x2="132" y2="188" stroke="#888" stroke-width="1.5"/>
<circle cx="100" cy="90" r="4" fill="#222"/>
<circle cx="48" cy="128" r="4" fill="#222"/>
<circle cx="68" cy="188" r="4" fill="#222"/>
<circle cx="132" cy="188" r="4" fill="#222"/>
<circle cx="152" cy="128" r="4" fill="#222"/>
<text x="100" y="225" text-anchor="middle" font-size="13" fill="#555">n(n−1)/2 条边</text>
<line x1="205" y1="140" x2="318" y2="140" stroke="#222" stroke-width="2"/>
<polygon points="318,134 318,146 334,140" fill="#222"/>
<text x="270" y="118" text-anchor="middle" font-size="13">随机删一个三角形</text>
<text x="270" y="168" text-anchor="middle" font-size="13">三条边一起消失</text>
<line x1="440" y1="85" x2="388" y2="123" stroke="#222" stroke-width="2" stroke-dasharray="6 5"/>
<line x1="388" y1="123" x2="408" y2="184" stroke="#222" stroke-width="2" stroke-dasharray="6 5"/>
<line x1="408" y1="184" x2="472" y2="184" stroke="#222" stroke-width="2" stroke-dasharray="6 5"/>
<line x1="472" y1="184" x2="492" y2="123" stroke="#222" stroke-width="2" stroke-dasharray="6 5"/>
<line x1="492" y1="123" x2="440" y2="85" stroke="#222" stroke-width="2" stroke-dasharray="6 5"/>
<circle cx="440" cy="85" r="4" fill="#222"/>
<circle cx="388" cy="123" r="4" fill="#222"/>
<circle cx="408" cy="184" r="4" fill="#222"/>
<circle cx="472" cy="184" r="4" fill="#222"/>
<circle cx="492" cy="123" r="4" fill="#222"/>
<text x="440" y="30" text-anchor="middle" font-size="15" fill="#222">结束：残尾（无三角形）</text>
<text x="440" y="225" text-anchor="middle" font-size="13" fill="#555">F_n ≈ n^(3/2)/(2√2)</text>
<text x="280" y="262" text-anchor="middle" font-size="14">代入 n = 10⁶：残尾 ≈ 10⁹/(2√2) ≈ 3.5 亿条边</text>
</svg>

</div>

代入具体数字：`@@M@@n=10^6@@` 时 `@@M@@n^{3/2}=10^9@@`，残尾约 `@@M@@10^9/(2\sqrt2)\approx 3.5@@` 亿条——不管随机运气好坏，这个数几乎总是这么多。

**为什么值得关心**

一个被研究了三十多年的随机过程，其"最终垃圾量"被算到了精确常数，说明看似混乱的随机过程也可以有铁律般的精确定律。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了从完全图 `@@M@@K_n@@` 出发随机逐个删三角形的终止残留边数 `@@M@@F_n@@` 满足 `@@M@@F_n/n^{3/2}@@` 依 `@@M@@L^2@@` 收敛于 `@@M@@1/(2\sqrt2)@@`，首次敲定该过程的精确尾常数，解决 Joos–Kühn 猜想的三角形情形。

## 问题背景

从 `@@M@@n@@` 个顶点的完全图（complete graph）`@@M@@K_n@@` 出发，每一步在三条边都还在的三角形中均匀选一个并删去其三条边，直到图中不再有三角形。被接受的三角形构成一个部分 Steiner 三元系（partial Steiner triple system），终止时残留的边称为残尾（leave），其边数记为 `@@M@@F_n@@`。Bollobás 与 Erdős 早在 1990 年就猜测 `@@M@@\E F_n@@` 的阶为 `@@M@@n^{3/2}@@`。此后 Spencer 的分支过程分析与 Rödl–Thoma 的 nibble 方法先证残尾为 `@@M@@o(n^2)@@`，Grable 与 Bohman–Frieze–Lubetzky 又把上界逐步压到 `@@M@@n^{7/4}@@` 量级乃至 `@@M@@F_n=n^{3/2+o(1)}@@`。指数虽已确定，精确常数却始终悬而未决：Joos 与 Kühn 在 2025 年关于严格平衡超图（strictly balanced hypergraph）移除过程的工作中猜想残尾有渐近常数，三角形情形为 `@@M@@1/(2\sqrt2)@@`。本文证明的正是这一情形。

## 主要结果

**主定理**：对从 `@@M@@K_n@@` 出发的一致三角形移除过程，

`@@M@@D\E\left[\left(\frac{F_n}{n^{3/2}}-\frac{1}{2\sqrt{2}}\right)^{2}\right]\longrightarrow 0,@@`

即 `@@M@@F_n/n^{3/2}@@` 均方收敛（`@@M@@L^2@@` convergence）于 `@@M@@1/(2\sqrt2)@@`。由此立即得到依概率收敛 `@@M@@\frac{F_n}{n^{3/2}}\xrightarrow{\Prb}\frac{1}{2\sqrt{2}}@@`，以及归一化期望极限 `@@M@@\E F_n/n^{3/2}\to 1/(2\sqrt2)@@`。这恰是 Joos–Kühn 猜想（其文献中的猜想 16.2）的三角形特款，且结论比猜想要求的依概率收敛更强。作者同时明确限定范围：定理只针对 `@@M@@K_n@@` 起始的移除，不涉及任意起始图、一般超图移除的精确常数，也不给出波动规律（fluctuation law）。

## 证明思路

先在确定性时刻"刹车"：当边密度降到 `@@M@@p=n^{-1/2+\epsilon}@@`（`@@M@@\epsilon=1/2000@@`）时停止。由 Joos–Kühn 的停止时间估计——这是全文唯一的外部证明输入——以超过 `@@M@@1-\exp\bigl(-(\log n)^{4/3}\bigr)@@` 的概率，此刻的图有 `@@M@@m=n^2p/2@@` 条边，每条边落在 `@@M@@D=np^2@@` 个三角形中，且每个顶点链接图（link graph）的圈计数与有根模板（rooted template）计数都近乎理想，这是后续一切估计的公共起点。

再把续跑过程改写为优先级扫描：给三角形赋予独立均匀优先级，从小到大扫描，三边俱全即接受。一条边的存活等价于一个递归测试返回真，其子测试询问候选三角形的另外两条边是否先于该候选存活；两条边合用一份联合有序候选表。若给递归树中每次出现都配上全新的独立优先级，就得到"独立展开"（independent unfolding）模型，其中存活概率满足精确的乘积恒等式，可与 Spencer 分支过程的标量解 `@@M@@q(t)=(1+2Dt)^{-1/2}@@` 比较。

然后攻克两个难点。其一为稳定性：不同边的偏差沿三角形的边邻接矩阵 `@@M@@A/D@@` 传播，朴素的极大范数界要损失 `@@M@@D@@` 倍。作者用链接圈计数做谱分离，使链接矩阵除主特征值外均为 `@@M@@O(n^{-\gamma})@@`、在欧氏范数下接近平均化投影，再经有限扰动展开把半群的极大范数界压到多对数级 `@@M@@C_1(1+\log n)^J@@`，自举闭合得 `@@M@@q_e(t)=(1+o(1))q(t)@@` 对所有边一致成立。其二为碰撞：真实过程中同一三角形类型会在不同查询里重现，独立展开则不会；耦合分析表明每次重现都迫使两条祖先查询路径之并上多出一条图边（见证，witness）。用有根模板界数出这类嵌入的数目，关键增益为 `@@M@@D^{-B}@@`（`@@M@@B=50@@`）；而访问指定路径既要求优先级沿路递减（`@@M@@1/j!@@` 因子），又要求偏离路径的候选全部失败（每步 `@@M@@q^2@@` 因子），二者相乘并对路径长度求和得碰撞概率 `@@M@@O(D^{-35})=o(D^{-1})@@`——这一精度必须小于双根存活概率自身的阶 `@@M@@(2D)^{-1}@@`，否则二阶矩无法成立。

最后读出矩：一或两个均匀随机根边的查询成功率分别给出 `@@M@@\E[F_n/m]@@` 与 `@@M@@\E[(F_n/m)^2]@@`，而 `@@M@@mq(1)=\frac{n^2p}{2\sqrt{1+2np^2}}\sim\frac{n^{3/2}}{2\sqrt{2}}@@`，坏前缀的贡献又被其超多项式小的失败概率吸收，于是无条件地得到 `@@M@@L^2@@` 收敛与常数 `@@M@@1/(2\sqrt2)@@`。

## 可信度与备注

本手稿（OpenAI，2026 年 9 月 25 日）主结果尚无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。除引用 Joos–Kühn 已公开的前缀估计外，其余关键续跑估计——半群的极大范数稳定性与 `@@M@@o(D^{-1})@@` 的成对查询碰撞界——均为本文自证，逻辑链前后闭环。本批任务中该结果族仅含此一篇手稿，暂无姊妹篇交叉支撑；其结论与此前 `@@M@@F_n=n^{3/2+o(1)}@@` 的指数级结果相容，并将常数精确到 `@@M@@1/(2\sqrt2)@@`。

{% endraw %}
