---
layout: default
title: "A proof of Seymour's second-neighborhood conjecture"
family: "173"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A proof of Seymour's second-neighborhood conjecture

> 结果族 173：Seymour's second-neighborhood conjecture　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把"单向关注"画成一张图。每个人看两类人：你直接关注的一步圈，和"你关注的人所关注、但你没直接关注"的两步圈。Seymour 猜想：任何单向关系网中，总有一个人他的两步圈不小于一步圈。这个 1995 年被正式记录的猜想，本文给出了完整证明。

**关键词卡片**

- 定向图（oriented graph）：每条边只许单向通行、不许成对互指的有向图
- 出邻域（out-neighborhood）`@@M@@N_1^+@@`：一步直接指向的顶点集合
- 第二邻域（second neighborhood）`@@M@@N_2^+@@`：恰好两步才能到达的顶点集合
- 竞赛图（tournament）：任意两点恰有一条单向边的图，特例 1996 年已被解决
- 极小反例（minimal counterexample）：假设坏图存在，挑顶点最少的它层层逼出矛盾

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="30" text-anchor="middle" font-size="16" fill="#333">总有好顶点：|N₁⁺(v)| ≤ |N₂⁺(v)|</text>
  <line x1="143" y1="145" x2="267" y2="95" stroke="#333" stroke-width="1.8"/>
  <polygon points="267,95 260,102 257,95" fill="#333"/>
  <line x1="143" y1="155" x2="267" y2="205" stroke="#333" stroke-width="1.8"/>
  <polygon points="267,205 260,198 257,205" fill="#333"/>
  <line x1="294" y1="87" x2="427" y2="53" stroke="#333" stroke-width="1.8"/>
  <polygon points="427,53 419,59 417,52" fill="#333"/>
  <line x1="294" y1="94" x2="427" y2="131" stroke="#333" stroke-width="1.8"/>
  <polygon points="427,131 417,132 420,126" fill="#333"/>
  <line x1="294" y1="212" x2="427" y2="228" stroke="#333" stroke-width="1.8"/>
  <polygon points="427,228 418,231 419,224" fill="#333"/>
  <circle cx="130" cy="150" r="14" fill="#ffe8e5" stroke="#c0392b" stroke-width="1.8"/>
  <circle cx="280" cy="90" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
  <circle cx="280" cy="210" r="14" fill="#fff" stroke="#333" stroke-width="1.5"/>
  <circle cx="440" cy="50" r="13" fill="#fff" stroke="#333" stroke-width="1.5"/>
  <circle cx="440" cy="135" r="13" fill="#fff" stroke="#333" stroke-width="1.5"/>
  <circle cx="440" cy="230" r="13" fill="#fff" stroke="#333" stroke-width="1.5"/>
  <text x="130" y="155" text-anchor="middle" font-size="14" font-weight="bold" fill="#c0392b">v</text>
  <text x="280" y="95" text-anchor="middle" font-size="14" fill="#333">a</text>
  <text x="280" y="215" text-anchor="middle" font-size="14" fill="#333">b</text>
  <text x="440" y="55" text-anchor="middle" font-size="14" fill="#333">c</text>
  <text x="440" y="140" text-anchor="middle" font-size="14" fill="#333">d</text>
  <text x="440" y="235" text-anchor="middle" font-size="14" fill="#333">e</text>
  <text x="280" y="152" text-anchor="middle" font-size="13" fill="#c0392b">一步圈 {a, b}：2 人</text>
  <text x="440" y="185" text-anchor="middle" font-size="13" fill="#2471a3">两步圈 {c, d, e}：3 人</text>
  <text x="280" y="268" text-anchor="middle" font-size="14" fill="#555">本例 2 ≤ 3：v 就是那个好顶点</text>
</svg>

</div>

这个 6 顶点小网中，`@@M@@v@@` 的一步圈是 `@@M@@\{a,b\}@@` 共 2 人，两步圈是 `@@M@@\{c,d,e\}@@` 共 3 人，`@@M@@2\le 3@@`。定理保证：无论网多大、方向多刁钻，好顶点必然存在；加权版也对——按任意非负"人气权"加权，仍有人一步圈权重不超过两步圈。它还顺带导出若干有向圈推论，例如最小入度、出度都不低于 `@@M@@n/3@@` 的定向图必含有向三角形。

**为什么值得关心**

一般定向图情形悬置三十年，此前所有结果都要附加结构假设或放松结论；本文无条件解决，且已通过机器核验。

> 已 Lean 形式化

## 一句话结论

论文正面证明了 Seymour 第二邻域猜想：任何非空有限定向图中必有顶点 `@@M@@v@@` 满足 `@@M@@|N_1^+(v)|\le|N_2^+(v)|@@`，即有向距离恰为二的顶点数不少于出邻点数。这一自 1995 年记录以来悬置三十余年的有向图基本问题就此解决，主结果并已通过 Lean 形式化验证。

## 问题背景

定向图（oriented graph）是给简单图的每条边各指定一个方向所得的有向图：无环、无重弧、也无反向弧对。对顶点 `@@M@@v@@`，记 `@@M@@N_1^+(v)@@` 为出邻域（out-neighborhood），`@@M@@N_2^+(v)@@` 为有向距离恰为二的顶点集——两步可达、且排除 `@@M@@v@@` 自身与一步已到达者。Seymour 第二邻域猜想断言：总存在 `@@M@@v@@` 使 `@@M@@|N_1^+(v)|\le|N_2^+(v)|@@`。猜想由 Dean 与 Latka 于 1995 年记录。最著名的竞赛图（tournament，任意两顶点间恰有一弧）特例即 Dean 猜想，由 Fisher 于 1996 年借助 Farkas 引理构造的概率分布证明，Havet 与 Thomassé 后以局部中位序给出纯组合证明；此后 Fidler–Yuster 等处理了缺一个匹配、星形或团的近竞赛图，Kaneko–Locke 证明了最小出度不超过 6 的情形（近期计算机辅助工作推进到 7），Chen–Shen–Yuster 与 Huang–Peng 分别给出约 0.657 与 0.716 的普遍比例下界，随机图取向与稠密情形亦有专题研究。但这些成果均依赖附加结构或放松结论，一般猜想始终未决。

## 主要结果

主定理（定理 1.1）：每个非空有限定向图都有顶点 `@@M@@v@@` 使 `@@M@@|N_1^+(v)|\le|N_2^+(v)|@@`，不带任何连通性或度数假设；汇点平凡地满足结论。论文又经 Seacrest 的等价性导出加权形式（第 5 节推论）：对任意非负顶点权 `@@M@@\eta@@`，存在 `@@M@@v@@` 使 `@@M@@\eta(N_1^+(v))\le\eta(N_2^+(v))@@`；存在总质量为 1 的非负权使每个顶点都满足该不等式；并有相应的弧加权（arc-weighted）形式。第 6 节给出有向圈推论：无有向三角形的图中必有顶点出度不超过其非邻点数（Thomassé 非邻点命题的定向图形式）；最小入、出度均不低于 `@@M@@n/3@@` 的定向图必含有向三角形；`@@M@@r@@`-正则且最短有向圈长（directed girth）为 4 的图至少有 `@@M@@3r+1@@` 个顶点，即 Behzad–Chartrand–Wall 最小阶猜想的围长 4 情形。

## 证明思路

全文反证，三步走。先做约化（第 2 节）：设存在反例，取顶点数最少、弧数其次最少者 `@@M@@D@@`，可证 `@@M@@D@@` 强连通且每点入度为正。核心是把 Seacrest 引理 4 的删弧思想加强为子集亏损：对非空真子集 `@@M@@S@@`，记 `@@M@@I=F(S)\cap S@@`、`@@M@@E=F(S)\setminus S@@`，每轮删去从 `@@M@@S@@` 指向 `@@M@@E\setminus T@@` 的全部弧，极小性迫使删弧后的图中某顶点满足邻域不等式；比较删弧前后的邻域变化并累加增量估计，得 `@@M@@|F^2(S)\setminus F(S)|<|F(S)\setminus S|@@`。再做字典积膨胀：把每个顶点换成 `@@M@@m>n@@` 个顶点的传递竞赛图（transitive tournament），块内像集的初等估计使每单位亏损放大 `@@M@@m@@` 倍、块内误差至多按基顶点各计 1，于是对所有非空真子集 `@@M@@U@@` 一致得到严格不等式 `@@M@@|U|+|F^2(U)|<2|F(U)|@@`，且每点入度为正。

其次是剪枝引理（第 3 节），它对任意有限二元关系成立，与定向性无关。两族有序点对 `@@M@@\mathcal R,\mathcal C@@` 中，`@@M@@(p,j)@@` 与 `@@M@@(i,s)@@` 冲突指 `@@M@@p\to i@@` 且 `@@M@@s\to j@@`，冲突生成点集 `@@M@@Z@@` 与 `@@M@@H@@`。引理断言：可删去部分成员使剩余两族无冲突、原先无冲突者全部保留，且删除总数不超过 `@@M@@|H|@@` 加上删完后仍无成员覆盖的 `@@M@@Z@@` 中点数——代价须对"事后未覆盖点"记账，这正是末步所要。证明先建增广二部图（左部 `@@M@@\mathcal R\sqcup Z_L@@`、右部 `@@M@@\mathcal C\sqcup Z_R@@`），把问题化为匹配（matching）大小不超过 `@@M@@|Z|+|H|@@`；再利用 Edmonds 关于泛型秩（generic rank）等于最大匹配数的经典对应，选取一组系数使四个线性映射同时满足交换关系 `@@M@@NL=AB@@` 与三个秩条件，并配合"最大支撑秩矩阵的左、右核（kernel）向量在允许位置逐坐标正交"的代数引理完成匹配界，最后以 König 定理的交替路构造把匹配界化为删除集。

最后是极值矛盾（第 4 节）：设 `@@M@@G@@` 满足上述严格不等式，在 `@@M@@X\times X@@` 上定义坐标像算子 `@@M@@F_1,F_2@@`，称 `@@M@@P,Q@@` 相容若 `@@M@@F_1P\cap F_2Q=\varnothing@@`。对角线 `@@M@@\Delta@@` 自身相容，故可在含 `@@M@@\Delta@@` 的相容对中取 `@@M@@M+d@@` 最大者（`@@M@@M@@` 为两族大小之和，`@@M@@d@@` 为未覆盖点数）。`@@M@@P@@` 的每一列、`@@M@@Q@@` 的每一行都是非空真子集，逐列逐行求和严格不等式得纤维和不等式；取补集构造新族，其总大小严格大于 `@@M@@M+2d@@`。新族未必相容，但对角线成员仍无冲突且被剪枝引理保留，且冲突集 `@@M@@H@@` 完全落入旧未覆盖点集，即 `@@M@@|H|\le d@@`。于是剪枝至多删除 `@@M@@d+d'@@` 个成员（`@@M@@d'@@` 为新族未覆盖点数），新目标值严格大于 `@@M@@M+2d-(d+d')+d'=M+d@@`，与极大性矛盾，定理得证。

## 可信度与备注

主结果已由 Lean 形式化证明验证，这是最强的可信度背书；加权与有向圈推论由主定理经 Seacrest 等价性与初等论证导出。本文为结果族 173 的唯一论文，独立完成猜想的完整解决；方法上建立在 Brantner–Brockman–Kay–Snively 的极小反例与图乘积技术、以及 Seacrest 的子集视角之上。按 OpenAI 官方声明，未经形式化的结果可能存在问题，相关推论仍宜以社区核验为准。

{% endraw %}
