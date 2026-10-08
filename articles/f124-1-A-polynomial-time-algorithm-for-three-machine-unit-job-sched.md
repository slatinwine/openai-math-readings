---
layout: default
title: "A Polynomial-Time Algorithm for Three-Machine Unit-Job Scheduling"
family: "124"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Polynomial-Time Algorithm for Three-Machine Unit-Job Scheduling

> 结果族 124：Polynomial-time scheduling on three identical machines　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

三位厨师、每道菜都恰好一分钟、有些菜必须等另几道出锅才能开做:怎样安排,让最后一道菜最早出锅?这个 1979 年就被挂账的"三台机器排序"悬案,论文给出圆满答案:存在一个保证在多项式时间内算出最优安排的算法。

**关键词卡片**

- 单位作业(unit job):每个任务耗时完全相同,都是"一分钟"。
- 前序约束(precedence constraint):"先切菜才能下锅"式的先后依赖,合起来是一张有向无环图。
- 完工时间(makespan):最后一个任务完成的时刻,要最小化的目标。
- 动态规划(dynamic programming):把大排程切成小段逐段登记,避免指数级穷举。
- 多项式时间(polynomial time):耗时是规模 `@@M@@n@@` 的固定次幂,是"理论上高效"的标志。

**看个具体例子**

6 个一分钟作业,依赖为 `@@M@@1\to3@@`、`@@M@@2\to3@@`、`@@M@@3\to5@@`、`@@M@@4\to5@@`、`@@M@@5\to6@@`。最长链 `@@M@@1\to3\to5\to6@@` 占 4 分钟,所以再快也快不过 4 分钟;下面的排程恰好用满 4 分钟,故为最优。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="26" text-anchor="middle" font-size="16" fill="#333">三台机器 × 四个时刻:最优排程(makespan = 4)</text><text x="160" y="62" text-anchor="middle" font-size="13" fill="#666">第1分钟</text><text x="260" y="62" text-anchor="middle" font-size="13" fill="#666">第2分钟</text><text x="360" y="62" text-anchor="middle" font-size="13" fill="#666">第3分钟</text><text x="460" y="62" text-anchor="middle" font-size="13" fill="#666">第4分钟</text><rect x="210" y="78" width="100" height="40" fill="#f5f5f5" stroke="#ccc"/><rect x="310" y="78" width="100" height="40" fill="#f5f5f5" stroke="#ccc"/><rect x="410" y="78" width="100" height="40" fill="#f5f5f5" stroke="#ccc"/><rect x="210" y="128" width="100" height="40" fill="#f5f5f5" stroke="#ccc"/><rect x="310" y="128" width="100" height="40" fill="#f5f5f5" stroke="#ccc"/><rect x="410" y="128" width="100" height="40" fill="#f5f5f5" stroke="#ccc"/><rect x="210" y="178" width="100" height="40" fill="#f5f5f5" stroke="#ccc"/><rect x="310" y="178" width="100" height="40" fill="#f5f5f5" stroke="#ccc"/><rect x="410" y="178" width="100" height="40" fill="#f5f5f5" stroke="#ccc"/><rect x="110" y="78" width="100" height="40" fill="#4a90d9"/><rect x="110" y="128" width="100" height="40" fill="#7bb661"/><rect x="110" y="178" width="100" height="40" fill="#9b6dd6"/><rect x="210" y="78" width="100" height="40" fill="#e2a33c"/><rect x="310" y="78" width="100" height="40" fill="#d977a0"/><rect x="410" y="78" width="100" height="40" fill="#5dc0b0"/><text x="62" y="103" text-anchor="middle" font-size="14" fill="#333">机器一</text><text x="62" y="153" text-anchor="middle" font-size="14" fill="#333">机器二</text><text x="62" y="203" text-anchor="middle" font-size="14" fill="#333">机器三</text><text x="160" y="104" text-anchor="middle" font-size="18" fill="#fff" font-weight="bold">1</text><text x="260" y="104" text-anchor="middle" font-size="18" fill="#fff" font-weight="bold">3</text><text x="360" y="104" text-anchor="middle" font-size="18" fill="#fff" font-weight="bold">5</text><text x="460" y="104" text-anchor="middle" font-size="18" fill="#fff" font-weight="bold">6</text><text x="160" y="154" text-anchor="middle" font-size="18" fill="#fff" font-weight="bold">2</text><text x="160" y="204" text-anchor="middle" font-size="18" fill="#fff" font-weight="bold">4</text><text x="280" y="248" text-anchor="middle" font-size="13" fill="#555">依赖:1→3,2→3,3→5,4→5,5→6;链 1→3→5→6 长 4 ⇒ 下界 4</text><text x="280" y="272" text-anchor="middle" font-size="13" fill="#888">白色空格 = 机器空闲;本排程恰达下界,故为最优</text></svg>

</div>

定理保证的是一般性:对任意张依赖图,算法都能在多项式时间内构造最优排程,并精确判断"能否在给定期限内完工"。

**为什么值得关心**

这是 Garey–Johnson 名著中的公开问题 OPEN8,悬置近半个世纪。不过要诚实说明:算法时间界 `@@M@@O((L+2)^{150020})@@` 的指数大得惊人,本文的价值在"三台机器属于 P"这一分类事实,而非实用程序。

> 暂无形式化证明(AI 结果待核验)

## 一句话结论

论文证明 `@@M@@P3\mid\mathrm{prec},p_j=1\mid C_{\max}@@` 属于 P：三台相同机器、单位时长、任意前序约束的排序存在确定性多项式时间精确算法，可构造最优排程并精确判定截止期可行性，解决悬置近五十年的 Garey–Johnson OPEN8。

## 问题背景

给定 `@@M@@n@@` 个非抢占（nonpreemptive）单位时长作业与任意前序约束（precedence constraints），要把它们排到三台相同机器上使完工时间（makespan）最小。两机器情形在 1969—1972 年由 Fujii–Kasami–Ninomiya 与 Coffman–Graham 解决；Ullman 于 1975 年证明机器数作为输入时问题 NP 完全，"固定三台"由此成为悬案，被 Garey 与 Johnson 1979 年专著列为 OPEN8。此前最好记录是 Nederlof–Swennenhuis–Węgrzycki（2025）的亚指数（subexponential）算法 `@@M@@2^{O(\sqrt n\log n)}@@`，受限结构另有 Dolev–Warmuth 等多项式与近似算法。卡点在于：删去若干槽后剩余的"洞"（gap）虽可独立排程，但用边界三元组命名洞并不能确定其作业集，递归继承祖先描述会使公式无限膨胀。

## 主要结果

输入是显式列出的 DAG `@@M@@G=(V,E)@@` 与整数截止期 `@@M@@T@@`，问是否存在 `@@M@@\tau:V\to\{1,\ldots,T\}@@`，使每个值至多被取三次、且 `@@M@@\tau(u)<\tau(v)@@` 对每条边成立（paper.tex:99–104）。主定理断言：存在确定性算法构造最小 makespan 的可行排程，精确判定截止期可行性并在可行时返回排程，耗时 `@@M@@O((L+2)^{150020})@@` 步（paper.tex:120–131）。作者声明指数常数极大、不作实用承诺，价值在于"属于多项式时间"的判定本身。

## 证明思路

证明分有限搜索与结构定理两半。先补齐（padding）孤立作业使每槽恰含三个作业，得到"满排程"（full schedule）；洞内重排不破坏可行性。再固定线性扩张（linear extension）及其反向作为两个"框架"（frame），原子测试只允许秩（rank）阈值、三元组及其四个前驱/后继锥（cone）`@@M@@P_a,D_a,\widehat P_a,\widehat D_a@@`；叶数不超过 `@@M@@K=10000@@` 的布尔公式之集族 `@@M@@\F@@` 只有 `@@M@@O(N^{3K})@@` 个成员。算法按基数递增对 `@@M@@\F@@` 做动态规划：状态 `@@M@@(L,Z,R)@@` 满足 `@@M@@W=L\dot\cup Z\dot\cup R@@`，`@@M@@Z@@` 为反链三元组，转移要求 `@@M@@L\cup Z\subseteq L'@@` 且新暴露差集已被接受；初始态达终态即接受 `@@M@@W@@`，可靠性由拼接子排程得出（paper.tex:380–400）。

难点是完备性：每个可行满排程都有"有界描述层级"（bounded-description hierarchy）——递归分解中各节点的作业集与标记槽前段都有与深度无关的有界公式（thm:structure，paper.tex:456）。见证取字典序最小（lexicographically minimal）的规范化排程：每区间选一个中心槽，两侧按优先序把作业从"高"到"低"逐个升级并推进分隔符（separator），使相邻标记分隔同一截断（shared cutoff）：洞内低作业是左端点的后继、高作业是右端点的前驱（separators.tex:75）。为不记忆祖先，每节点携带至多 5 个全局上集（upset）短列表：同向更新只做"携带"（carry）再追加一个注入（injection）；换向时丢弃旧表，用展平引理把历史折叠成 ≤21 叶的谓词重建。至多 5 项之界恰用上机器数 3：存活的注入在父集上两两不交，各含右边界三元组一成员（lists.tex:126）。两个全局边界不变式防止限定子与交换信息沿深度累积。最后把子区间写成全局公式：高部 `@@M@@\Qual(\K')\cap P_{b'}\cap(J\setminus\wP{a'})@@`，低部 `@@M@@D_{a'}\cap P_b\cap(J\setminus\wD{b'})\cap(J\setminus\wD v)\cap\widetilde S@@`，合计不足 500 叶（descriptions.tex:47、165）。层级既存，动态规划即可重建排程。

## 可信度与备注

本篇 formalized 标记为否，主结果尚无 Lean 形式化证明，请以社区核验为准。论文内部环环相扣：算法的完备性完全依赖结构定理，后者由分隔符、区间构造、短列表、边界不变式、最终描述五组件逐层衔接（construction.tex 表 1）。按 OpenAI 官方声明，未经形式化的结果可能有问题；指数高达 150020，本文应视为理论突破而非实用算法。

{% endraw %}
