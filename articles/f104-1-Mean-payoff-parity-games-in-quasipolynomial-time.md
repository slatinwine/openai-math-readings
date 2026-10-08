---
layout: default
title: "Mean-payoff parity games in quasipolynomial time"
family: "104"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Mean-payoff parity games in quasipolynomial time

> 结果族 104：Quasipolynomial algorithms for mean-payoff, stochastic and parity games　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一盘永不结束的桌游：你和对手轮流把棋子从一个据点挪到下一个，每个据点写着"路过赚 3 元"或"路过亏 5 元"，还挂着一个编号。你要同时办成两件事：长期平均下来不亏钱，而且最常经过的据点之中编号最小的那个是偶数。这篇论文造出一台"电子裁判"，能算清从哪些据点出发你必有办法双管齐下，而且判得飞快——拟多项式时间。

**关键词卡片**

- 平均收益奇偶博弈（mean-payoff parity game）：在图上永远走下去，既比长期平均收益、又比"常访最小编号是否为偶"的二人博弈
- 取胜集（winning set）：先手能同时锁定两个目标的全部出发点；算法的任务就是画出这条分界线
- 拟多项式时间（quasipolynomial time）：步数形如 `@@M@@2^{O((\log L)^2)}@@`——只把"输入长度的对数"送上指数
- 优先级（priority）：顶点上挂的编号；无穷对局里频繁出现的最小编号之奇偶定胜负
- 策略（strategy）："走到哪、下一步怎么走"的完整手册；本文中赢家的手册可能厚到需要无限记忆

**看个具体例子**

最小例子只需两个据点：A（奖励 +3，优先级 4）、B（奖励 −5，优先级 2），棋子在两者间无限往返。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<circle cx="160" cy="110" r="38" fill="#e8eef8" stroke="#345" stroke-width="2"/>
<text x="160" y="102" text-anchor="middle" font-size="16" fill="#123">A</text>
<text x="160" y="124" text-anchor="middle" font-size="12" fill="#123">奖励 +3 · 优先级 4</text>
<circle cx="400" cy="110" r="38" fill="#f8e8e8" stroke="#843" stroke-width="2"/>
<text x="400" y="102" text-anchor="middle" font-size="16" fill="#702">B</text>
<text x="400" y="124" text-anchor="middle" font-size="12" fill="#702">奖励 −5 · 优先级 2</text>
<line x1="200" y1="98" x2="360" y2="98" stroke="#345" stroke-width="2"/>
<polygon points="362,98 350,92 350,104" fill="#345"/>
<line x1="366" y1="132" x2="200" y2="132" stroke="#843" stroke-width="2"/>
<polygon points="198,132 210,126 210,138" fill="#843"/>
<text x="280" y="88" text-anchor="middle" font-size="12" fill="#345">A→B</text>
<text x="280" y="154" text-anchor="middle" font-size="12" fill="#843">B→A</text>
<text x="280" y="192" text-anchor="middle" font-size="14">循环一圈：平均 = (3 + (−5))/2 = −1 &lt; 0 ⇒ Max 输</text>
<text x="280" y="220" text-anchor="middle" font-size="14">把 B 的奖励改为 −2：平均 = +1/2 ≥ 0，常访最小编号 2 为偶 ⇒ Max 赢</text>
<text x="280" y="252" text-anchor="middle" font-size="12" fill="#567">圈中标注：每路过一次的收益与优先级编号</text>
</svg>

</div>

原始数字下，一圈的平均收益是 `@@M@@(3+(-5))/2=-1<0@@`，"不亏"目标破产，A 不在取胜集；把 B 的奖励改成 `@@M@@-2@@`，平均变 `@@M@@+1/2@@`，且常访最小编号 2 恰是偶数，A 立刻翻盘。算法要做的，就是对着任意大的图把这条胜负线一刀切清。

**为什么值得关心**

这类博弈是电路验证与反应式系统合成的理论核心，带数值版本此前只有"伪拟多项式"算法；本文首次把它整体压进拟多项式。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

给出平均收益奇偶博弈（mean-payoff parity game）取胜集的确定性拟多项式算法：在完整二进制输入长度 `@@M@@L@@` 下用 `@@M@@2^{O((\log(L+2))^2)}@@` 次位操作，精确算出 Max 能同时强制非负下极限平均收益与奇偶条件的全部顶点；优先级个数与奖励数值均不受限。

## 问题背景

Chatterjee、Henzinger 与 Jurdziński（2005）引入平均收益奇偶博弈，以同时表达定性规范（无穷次重现的最小优先级为偶）与定量性能（长程平均奖励非负）。两个目标会互相牵制：反复访问有利的优先级可能亏本。已知强制该合取的一方可能需要无限记忆的策略，而对手有位置最优策略（Bouyer–Markey–Olschewski–Ummels 2011）。算法方面，Chatterjee–Doyen（2012）把阈值问题放入 `@@M@@\mathrm{NP}\cap\mathrm{coNP}@@`；Chatterjee–Henzinger–Svozil（2017）给出 `@@M@@O(n^{d-1}mW)@@` 算法；Daviaud–Jurdziński–Lazić（2018）用策略分解把对优先级个数的依赖降到拟多项式，但界中仍带数值权重因子 `@@M@@W@@`——对二进制大权重呈指数级，故只算"伪拟多项式"。另一方面，纯奇偶博弈（parity game）自 2017 年起已有拟多项式算法，Parys（2019）的降精度递归是本文结构的直接源头。卡点在于：如何把平均收益约束嫁接进奇偶递归而不引入数值因子，且组合策略时不被反复重启的累积损失击穿。

## 主要结果

定理（Theorem 1.1）：一致的确定性算法精确返回所有使 Max 能对每个 Min 策略强制"`@@M@@\min\{p(v):v@@` 在无穷对局中频繁出现`@@M@@\}@@` 为偶数"且 `@@M@@\MP(\pi)=\liminf_{T\to\infty}\frac1T\sum_{t<T}r(v_t)\ge0@@` 的出发顶点。顶点带整数奖励 `@@M@@r(v)@@` 与自然数优先级 `@@M@@p(v)@@`（奖励放在顶点，等价于边权 `@@M@@w(v,u)=r(v)@@`），总代价至多 `@@M@@2^{C(\log_2(L+2))^2}@@` 位操作，优先级个数与奖励、优先级的数值大小都不受限制。结构上本文是一条归约：整个算法以 `@@M@@2^{O((\log_2(n+2))^2)}@@` 次调用普通平均收益博弈求解器完成，每次查询的输入长度为 `@@M@@(L+2)^{O(1)}@@`。

## 证明思路

核心难点是组合策略时不破坏平均收益：只对每条不间断对局段有平均界，不足以控制任意多次重启的累积损失。为此先确立一致前缀性质（uniform prefix property）：对每个 `@@M@@\epsilon>0@@` 存在 `@@M@@C_\epsilon@@`，使 Max 的策略的每条长 `@@M@@t@@` 的一致前缀权重 `@@M@@\ge-\epsilon t-C_\epsilon@@`。构造采用递增轮次（increasing rounds）思想：第 `@@M@@j@@` 轮先沿全局位置平均收益策略走恰好 `@@M@@j@@` 条边（由姊妹篇接口，该策略保证每条有限前缀权重 `@@M@@\ge-(N-1)W_H@@`），再在残区跟随局部取胜策略，最后把对局吸引到最小优先级集。到时刻 `@@M@@T@@` 完成的轮数至多 `@@M@@1+\sqrt{2T}@@`，于是每轮的固定开销被摊成 `@@M@@K_\delta(1+\sqrt{2T})@@`，再用初等不等式 `@@M@@K\sqrt{2T}\le\epsilon T/2+K^2/\epsilon@@` 收尾。这一对全部 `@@M@@\epsilon@@` 一致的界使策略被反复打断、重启后仍守住平均收益，并支撑起与决定性（determinacy）的联合归纳：每个顶点恰属一方取胜区域，且 Max 的取胜顶点都配有满足该性质的策略。

其次是结构引理。设 `@@M@@d@@` 为当前最小优先级，`@@M@@P@@` 在 `@@M@@d@@` 为偶时取 Max、奇时取 Min，`@@M@@R=H\setminus\Attr_P^H(S)@@` 是去掉最小优先级吸引子（attractor）后的残区。当 `@@M@@d@@` 为偶且 Max 在全区赢得普通平均收益时，对手 Min 的任何非空统辖域（dominion）都含一个在残区中非空的 Min 统辖域——否则把组合引理反推，会得出 Max 在该域全胜的矛盾。

最后是 Parys 式降精度递归（reduced-precision recursion）。过程 `@@M@@\Solve(H,(b_{\Max},b_{\Min}))@@` 保证：尺寸不超过 `@@M@@b_J@@` 的 `@@M@@J@@`-统辖域全部归入 `@@M@@J@@` 标记。每步取当前最小优先级 `@@M@@d@@`：`@@M@@d@@` 为偶时先查询普通平均收益取胜集，把 Max 输掉的顶点连同其 Min-吸引子删去；随后两个"相位"以对手界减半 `@@M@@b'=\lfloor b/2\rfloor@@` 的参数递归，中间夹一次界不变的调用——由结构引理，若对手统辖域仍在，这次调用至少删去其中 `@@M@@b'+1@@` 个点，剩余不超过 `@@M@@b'@@`，于是第二个减半相位即可将其清空。每个孩子都删去父层的最小优先级，故递归路径至多 `@@M@@n@@` 条边；每条路径至多 `@@M@@2(1+\lfloor\log_2 n\rfloor)@@` 次减半，每个节点至多 `@@M@@M=2(n+1)@@` 个减半孩子，调用总数 `@@M@@\le\sum\binom{\ell}{j}M^j=2^{O((\log_2(n+2))^2)}@@`。再把每次查询替换为同族确定性篇的求解器（其输入长度仅多项式放大、只改常数），即得主定理的位复杂度。

## 可信度与备注

本篇以姊妹篇《Deterministic quasipolynomial-time mean-payoff games》的定理 1.1 与推论 7.1（取胜集与双方全局位置策略）为黑箱接口，归约部分（策略组合、统辖域提取、递归与计数）自足完成；族内三篇共享同一"单一保精度孩子"的拟多项式计数机制，互为印证。暂无形式化证明；OpenAI 官方声明未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
