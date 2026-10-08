---
layout: default
title: "Rigidity of the Turing degrees"
family: "241"
discipline: "Mathematical logic"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Rigidity of the Turing degrees

> 结果族 241：Rigidity of the Turing degrees　·　学科：Mathematical logic　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把世上所有计算问题连成一张关系网：若"拿 B 当参考答案就能算出 A"，就在两者之间连一条线。现在把每个问题自己的名字全部涂掉，只留下这张纯粹的"谁难谁易"网。本文证明：光看网的结构就能认出每个难度是谁——任何保持上下级关系的"重新贴标签"，都只能是原样不动。

**关键词卡片**

- 图灵归约（Turing reducibility）：`@@M@@A\le_T B@@`，即把 B 当"谕示"（随取随用的参考答案），图灵机就能算出 A。
- 图灵度（Turing degree）：互相能算的问题归入同一档难度，全体难度构成一张偏序网。
- 自同构（automorphism）：把各难度整体重新编号、却保持全部"不高于"关系的双射。
- 刚性（rigidity）：唯一合法的自同构是恒等——网中每个位置都无法被冒名顶替。

**看个具体例子**

难度网的最底层是 `@@M@@\mathbf 0@@`（可计算问题），往上是 `@@M@@\mathbf 0'@@`（停机问题的难度）、`@@M@@\mathbf 0''@@`……定理说：任何保序双射 `@@M@@\pi@@` 都把每一个度送到它自己。下图虚线代表 `@@M@@\pi@@` 想做的"搬运"，结果全部原地踏步。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="34" font-size="15" fill="#333" text-anchor="middle">给难度重新贴标签（π）——结果只能原样不动</text><circle cx="170" cy="230" r="10" fill="#2c7fb8"/><circle cx="170" cy="150" r="10" fill="#2c7fb8"/><circle cx="170" cy="70" r="10" fill="#2c7fb8"/><line x1="170" y1="218" x2="170" y2="164" stroke="#333" stroke-width="2"/><line x1="170" y1="138" x2="170" y2="84" stroke="#333" stroke-width="2"/><polygon points="170,162 165,173 175,173" fill="#333"/><polygon points="170,82 165,93 175,93" fill="#333"/><text x="152" y="235" font-size="14" fill="#333" text-anchor="end">0（可计算）</text><text x="152" y="155" font-size="14" fill="#333" text-anchor="end">0′（停机问题）</text><text x="152" y="75" font-size="14" fill="#333" text-anchor="end">0″ …</text><text x="188" y="200" font-size="13" fill="#666">≤_T</text><text x="188" y="120" font-size="13" fill="#666">≤_T</text><circle cx="410" cy="230" r="10" fill="none" stroke="#c0392b" stroke-width="2" stroke-dasharray="4 3"/><circle cx="410" cy="150" r="10" fill="none" stroke="#c0392b" stroke-width="2" stroke-dasharray="4 3"/><circle cx="410" cy="70" r="10" fill="none" stroke="#c0392b" stroke-width="2" stroke-dasharray="4 3"/><line x1="182" y1="230" x2="396" y2="230" stroke="#c0392b" stroke-width="2" stroke-dasharray="6 4"/><line x1="182" y1="150" x2="396" y2="150" stroke="#c0392b" stroke-width="2" stroke-dasharray="6 4"/><line x1="182" y1="70" x2="396" y2="70" stroke="#c0392b" stroke-width="2" stroke-dasharray="6 4"/><text x="290" y="222" font-size="13" fill="#c0392b" text-anchor="middle">π(0)=0</text><text x="290" y="142" font-size="13" fill="#c0392b" text-anchor="middle">π(0′)=0′</text><text x="290" y="62" font-size="13" fill="#c0392b" text-anchor="middle">π(0″)=0″</text><text x="410" y="262" font-size="14" fill="#c0392b" text-anchor="middle">任何保序双射都是恒等</text></svg>

</div>

**为什么值得关心**

这正面解决了 Slaman–Woodin 刚性猜想，并连带证实图灵度序与二阶算术可无参数互相解释——一张涂掉名字的抽象关系网，竟装得下整个二阶算术的信息。

> 已 Lean 形式化

## 一句话结论

本文证明图灵度（Turing degrees）偏序 `@@M@@(\mathcal{D}_T,\le_T)@@` 完全刚性：任何保序自同构必为恒等，正面解决刚性猜想，并连带证实 Slaman–Woodin 双解释猜想——"谁计算谁"的序关系足以唯一标记每个度。

## 问题背景

图灵归约（Turing reducibility）`@@M@@A\le_T B@@` 指以 `@@M@@B@@` 为谕示（oracle）的图灵机能算出 `@@M@@A@@` 的特征函数；互相归约的集合视为等同，其等价类即图灵度（Turing degree），全体度构成偏序 `@@M@@(\mathcal{D}_T,\le_T)@@`。这一相对可计算性概念源自 Turing 1939 年的谕示机。自同构问题（automorphism problem）问：丢掉集合的具体编码、只留下抽象的序，还保有多少信息？刚性猜想断言任何满足 `@@M@@\mathbf a\le_T\mathbf b\iff\pi(\mathbf a)\le_T\pi(\mathbf b)@@` 的双射 `@@M@@\pi@@` 都是恒等。此前进展：Jockusch–Solovay（1977）证明保跳算子（jump operator）的自同构固定 `@@M@@\mathbf 0^{(4)}@@` 以上的度；Shore–Slaman（1999）证明跳算子可由序关系定义，因而被一切自同构保持；Slaman–Woodin（2005）进一步证明所有自同构共同固定 `@@M@@\mathbf 0''@@` 以上的锥（cone），且自同构群可数、每个自同构有算术表示。悬而未决的正是锥外——`@@M@@\mathbf 0''@@` 以下——的度。

## 主要结果

**刚性定理（定理 1.1）**　在 ZFC 中，对任何序自同构 `@@M@@\pi\in\mathrm{Aut}(\mathcal{D}_T,\le_T)@@` 与任何度 `@@M@@\mathbf a@@` 均有 `@@M@@\pi(\mathbf a)=\mathbf a@@`；对 `@@M@@\pi@@` 不附加任何可定义性或正则性假设。

**推论 5.1（双解释）**　图灵度序与二阶算术（full second-order arithmetic）无参数双解释（biinterpretable without parameters），这由 Slaman–Woodin 所证"刚性等价于双解释"直接得到。

支撑主定理的技术核心是恢复定理（recovery，命题 4.1）：设 Borel 函数 `@@M@@F:\mathbb R\to 2^{\mathbb N}@@` 具可数纤维（countable fibers）且满足加法归约 `@@M@@F(x+y)\le_T F(x)\oplus F(y)@@`，则对每个无理数 `@@M@@t\in(0,1)@@` 存在余贫集（comeager set）`@@M@@G_t\subseteq\mathbb R^2@@`，使对每对 `@@M@@(u,v)\in G_t@@` 有有理数 `@@M@@\delta\in(0,1)@@` 满足 `@@M@@C(t)\le_T F(u)\oplus F(u-v)\oplus F(v-u+\delta t)\oplus F(v-u+\delta(t-1))@@`，其中 `@@M@@C(x)=\{i:q_i<x\}@@` 是有理切割（rational cut）编码。该命题与自同构无关，独立成立。

## 证明思路

证明分三步：表示、恢复、消参。

先把自同构"落地"。本文唯一的外部输入是 Slaman–Woodin 表示定理（2005 年未刊手稿定理 6.3.1(2)）：任何自同构 `@@M@@\pi@@` 都由某个算术的、因而 Borel 的函数 `@@M@@\widehat F:2^{\mathbb N}\to 2^{\mathbb N}@@` 诱导，即 `@@M@@\deg_T\widehat F(A)=\pi(\deg_T A)@@` 对每个集合成立。复合有理切割得 `@@M@@F:\mathbb R\to2^{\mathbb N}@@`：它 Borel、纤维可数（`@@M@@\pi@@` 是单射而每个度只含可数多个集合），且由 `@@M@@\pi@@` 保序又保上确界（join）推出加法归约。

再证四值恢复，机制是有界递推（bounded recurrence）加平均恒等式：状态 `@@M@@s_0=0@@`，每步读 `@@M@@F(u+s_n)@@` 的一个固定比特位，据此选增量 `@@M@@\delta t@@`（向上）或 `@@M@@\delta(t-1)@@`（向下），记选择为 `@@M@@r_n@@`。求和得 `@@M@@s_N=\delta(Nt-\sum_{n<N}r_n)@@`；只要状态始终有界，频率 `@@M@@A_N=\frac1N\sum_{n<N}r_n@@` 便以误差 `@@M@@<1/(N\delta)@@` 逼近 `@@M@@t@@`，而 `@@M@@t@@` 无理，故可由这些逼近算出 `@@M@@C(t)@@`。有界性如此保证：可数纤维使 `@@M@@F@@` 在 `@@M@@u@@` 两侧近处取到不同值，取差异比特 `@@M@@j@@`；Borel 函数在某个余贫集上连续，于是该比特在区间两端附近各取常值，等效于"端点附近永远指向内部"，中间行为任意也不越界。递推只需四个真实谕示：辅助对 `@@M@@(u,v)@@` 把"从 `@@M@@u+s@@` 前进 `@@M@@a@@`"拆成两次加法 `@@M@@(u+s)+(v-u+a)=v+s+a@@`、`@@M@@(v+s+a)+(u-v)=u+s+a@@`；最小归约指标 `@@M@@e(x,y)@@` 是 Borel 的，在其连续点附近沿可数群 `@@M@@H=\mathbb Q+\mathbb Qt@@` 平移时两个程序指标保持固定，于是初始值 `@@M@@F(u)@@`、返程值 `@@M@@F(u-v)@@` 与两个增量处的值恰是全部谕示。

最后消参与收尾：四个自变量都是 `@@M@@t,u,v@@` 的有理线性组合，度不超过 `@@M@@\mathbf b=d(t)\vee d(u)\vee d(v)@@`，故 `@@M@@d(t)\le_T\pi(\mathbf b)@@`；用 `@@M@@\pi^{-1}@@` 作用得 `@@M@@\pi^{-1}(d(t))\le_T d(t)\vee d(u)\vee d(v)@@` 在余贫集上成立。若 `@@M@@\pi^{-1}(d(t))\not\le_T d(t)@@`，范畴避锥引理（category avoidance，归功于 Sacks）断言满足该式的 `@@M@@(u,v)@@` 只构成贫集，与 Baire 纲定理矛盾。于是 `@@M@@\pi^{-1}(\mathbf a)\le_T\mathbf a@@` 对一切度成立（无理数的度穷尽非可计算度，最小度显然固定）；对 `@@M@@\pi^{-1}@@` 再用一次并配合反对称性即得 `@@M@@\pi(\mathbf a)=\mathbf a@@`。

## 可信度与备注

主结果已有 Lean 形式化证明（结果族 241 文档），这是目前最强的核验方式；切割编码、Borel 连续性、范畴避锥、四值恢复等关键引理在文中均有自足证明，唯一整体引用的外部输入是 Slaman–Woodin 未刊手稿中的表示定理。本结果族目前仅此一篇手稿，它直接建立在 Jockusch–Solovay、Shore–Slaman、Slaman–Woodin 的经典链条之上；与 Kjos–Hanssen 的置换自同构刚性、Lutz–Siskind 的完满集四元恢复属同族技术但假设各异。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，可靠性相应较高。

{% endraw %}
