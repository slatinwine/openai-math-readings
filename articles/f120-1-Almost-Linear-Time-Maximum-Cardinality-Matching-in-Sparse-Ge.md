---
layout: default
title: "Almost-Linear-Time Maximum-Cardinality Matching in General Graphs"
family: "120"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Almost-Linear-Time Maximum-Cardinality Matching in General Graphs

> 结果族 120：Almost-linear-time exact matching and prescribed-degree factors in general graphs　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

舞会上想给同学们配舞伴，每人只能牵一个人，怎样配出最多对？这个"最大匹配"问题自 1965 年起就有了多项式算法，但速度长期停在"边数 × 根号顶点数"的台阶上。这篇论文一步跨到近乎线性——几乎和把图读进电脑一样快。

**关键词卡片**

- 匹配（matching）：一组互不共享端点的边，没有人被重复占用。
- 最大匹配（maximum matching）：边数最多的匹配。
- `@@M@@f@@`-因子（`@@M@@f@@`-factor）：给每个顶点规定度数的生成子图问题。
- 近乎线性时间（almost-linear time）：`@@M@@(n+m)^{1+o(1)}@@`，几乎与输入规模同阶。
- 奇集合约束（odd-set constraints）：一般图匹配特有的结构障碍，二部图没有，是提速的拦路虎。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="150" y1="90" x2="150" y2="190" stroke="#333" stroke-width="5"/>
  <line x1="280" y1="90" x2="280" y2="190" stroke="#333" stroke-width="5"/>
  <line x1="410" y1="90" x2="410" y2="190" stroke="#333" stroke-width="5"/>
  <line x1="170" y1="70" x2="260" y2="70" stroke="#333" stroke-width="2"/>
  <line x1="300" y1="70" x2="390" y2="70" stroke="#333" stroke-width="2"/>
  <line x1="170" y1="210" x2="260" y2="210" stroke="#333" stroke-width="2"/>
  <line x1="300" y1="210" x2="390" y2="210" stroke="#333" stroke-width="2"/>
  <circle cx="150" cy="70" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="150" y="76" text-anchor="middle" font-size="15">1</text>
  <circle cx="150" cy="210" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="150" y="216" text-anchor="middle" font-size="15">2</text>
  <circle cx="280" cy="70" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="280" y="76" text-anchor="middle" font-size="15">3</text>
  <circle cx="280" cy="210" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="280" y="216" text-anchor="middle" font-size="15">4</text>
  <circle cx="410" cy="70" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="410" y="76" text-anchor="middle" font-size="15">5</text>
  <circle cx="410" cy="210" r="20" fill="none" stroke="#333" stroke-width="2"/>
  <text x="410" y="216" text-anchor="middle" font-size="15">6</text>
  <text x="60" y="250" font-size="14">粗边 = 匹配边：{1-2, 3-4, 5-6}</text>
  <text x="60" y="272" font-size="13">6 个点、7 条边的小图里，这是一份最大匹配（3 对）</text>
</svg>

</div>

数一数：粗边 `@@M@@\{1\text{-}2,\ 3\text{-}4,\ 5\text{-}6\}@@` 共 3 条且互不碰头，已是最大匹配。定理保证：对任何 `@@M@@n@@` 点 `@@M@@m@@` 边的简单图，单一随机算法在每条计算路径上都于 `@@M@@(n+m)^{1+o(1)}@@` 时间停机，至少以 `@@M@@2/3@@` 的概率输出显式最大匹配；答案输出前必被验证，绝不谎报。同一框架还近乎线性地解决 `@@M@@f@@`-因子的判定与构造。

**为什么值得关心**

此前最快的组合方法是 Micali–Vazirani 算法；前几年借近乎线性流算法，二部图率先突破到近乎线性，一般图却因"花"结构迟迟未动。本文把它扛过奇集合约束这道最难的门槛，推广到任意简单图，刷新了五十年的老纪录。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明任一无权简单图的最大匹配（maximum-cardinality matching）可用单一随机算法在 `@@M@@(n+m)^{1+o(1)}@@` 时间内精确求出，成功概率至少 `@@M@@2/3@@`，且时间界在每条计算路径上成立；同一方法把 `@@M@@f@@`-因子判定与构造也做到近乎线性，将一般图精确匹配从 `@@M@@O(m\sqrt n)@@` 推进到近乎线性。

## 问题背景

匹配（matching）是组合优化的基石：Edmonds 1965 年用花（blossom）收缩给出多项式算法后，一般图上最快的构造性组合算法长期是 Micali–Vazirani 的 `@@M@@O(m\sqrt n)@@`；代数方法（Mucha–Sankowski、Harvey）达到 `@@M@@O(n^\omega)@@`，但只在稠密图上占优。近十余年，基于内点法的几乎线性精确流算法（Chen 等与 van den Brand 等）使二部图匹配获得 `@@M@@(n+m)^{1+o(1)}@@` 解法。然而一般图的花结构对应奇集合约束（odd-set constraints），纯流与内点技术无法直接控制——这正是本文要跨越的最后一道障碍：把几乎线性精确求解从二部图推广到任意简单图。

## 主要结果

**定理（主定理）**：存在单一均匀随机 word-RAM 算法，对任何 `@@M@@n@@` 顶点、`@@M@@m@@` 边的简单图（记 `@@M@@p=n+m@@`），在每条计算路径上于 `@@M@@Cp^{1+\eta(p)}@@` 条指令内停机（`@@M@@\eta@@` 非增且随 `@@M@@p@@` 趋于 0），并以至少 `@@M@@2/3@@` 的概率输出显式最大匹配。稀疏端 `@@M@@m\le\kappa n@@` 给出 `@@M@@n^{1+o(1)}@@`，稠密端 `@@M@@m=\Theta(n^2)@@` 给出 `@@M@@n^{2+o(1)}@@`。算法不承诺完美匹配；否定答案只可能来自带上限的随机搜索，且绝无假阳性——每个候选解在输出前都被显式验证。

**推论（`@@M@@f@@`-因子）**：给定每个顶点的度指令 `@@M@@0\le f(v)\le\deg_G(v)@@`，在相同的时间与概率保证下，可判定 `@@M@@f@@`-因子（`@@M@@f@@`-factor，即满足 `@@M@@\deg_F(v)=f(v)@@` 的生成子图）是否存在并构造之；不存在时恒答 NO。

## 证明思路

全文骨架是"归约—核心算法—均匀化"三段。先把基数问题二分：对阈值 `@@M@@k@@`，用 Beneš 型重排网络（rearrangeable network）把"大小为 `@@M@@k@@` 的匹配"化成规模 `@@M@@O(m+n\log n)@@` 的完美匹配实例——朴素地添加 `@@M@@n-2k@@` 个万能顶点会引入二次多条边，网络把它压到近乎线性；再用 Dahlhaus–Karpinski 路径替换把最大度降到 3。于是核心化为次三次图（subcubic）上的完美匹配。核心状态把顶点分成"箱"（bins，带构造性 factor-critical 见证的奇块）与"行"（rows，沿原边指派到箱的单点），其余顶点显式配对；难点是结构改变后如何不全局扫描地修复这一表示。作者引入 `@@M@@a+1@@` 层账本（ledger）：每行向邻箱共分 `@@M@@L@@` 配额，箱 `@@M@@d@@` 有残差底线 `@@M@@c_jw_d@@`（`@@M@@w_d@@` 为箱权重），允许非负债务（debt）暂时违约。先看两端：最底层账本在稳态无债，直接给出每个非空箱集的严格 Hall 盈余（`@@M@@Lh(X)\ge y^a(X)\ge w(X)>0@@`），保证行—箱指派总可重排；最顶层账本带对数势 `@@M@@\Phi=\sum\log x_e+\sum\log s_d@@`，只要完美匹配存在且无结构动作可用，Berge 增广路径论证便给出改进环流方向，故不会假性停滞。再修中间：修复被实现为行—箱关联图上的精确流问题，只从债务相对其规模显著的箱出发探索；未探索的边界箱暂获乐观容量，吸收量足额即"锁定"与其规模成比例的份额，总流量受初始债务约束，物理扫描量随之受限；若请求底线不可行，则剥除箱集 `@@M@@R@@`（`@@M@@Lh(R)<c_jw(R)@@`），相邻两层底线恰差 1 的间隙使每个更粗账本债务净降至少 `@@M@@w(R)@@`——债务同时为局部探索与剥块买单。匹配目标与流测试共用"定价步"（priced-step）接口：寻找目标增益相对加权长度充分大的环流方向并走小的精确二进步，方向以森林中未展开的路径表示，免去逐步展开；该接口由冻结森林分解与预建路径副本构成的后端实现，承袭 Chen 等的几乎线性流框架与 Khandekar–Rao–Vazirani 的 cut-matching 技术。费用上，相位参数满足 `@@M@@Lg_*=O(N)@@`，几何重置周期 `@@M@@b_j=B^{a-j}@@` 把各级投影费用加总为 `@@M@@S^{1+O(1/a)+o_a(1)}@@`。最后，每个固定参数分支满足此界；随机耗尽只产生可能错误的否定答案（分支 `@@M@@t@@` 总错误 `@@M@@\le 2^{-(t+20)}@@`），确定性前提失败只挂起分支；Levin 式加权 dovetailing 把所有分支与一个确定的多项式回退分支编进一个程序，错误率求和 `@@M@@<1/3@@`，再以全输入上的上确界定义包络 `@@M@@\eta@@`，得到单一程序在每条路径上的时间界。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。证明链长达十节、技术密度很高，但设计上处处保守：候选解一律显式验证（无假阳性），确定性 guard 只挂起分支而不出错，多项式回退分支保证停机。结果族 120 内的姊妹结果（`@@M@@f@@`-因子等）均由本文主定理经见证保真的显式归约推出，彼此支撑为一个整体；其中个别构件（如路由助手）的技术细节该文未在解读层面展开，此处从略。

{% endraw %}
