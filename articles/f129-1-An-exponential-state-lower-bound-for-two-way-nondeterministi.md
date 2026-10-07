---
layout: default
title: "An exponential state lower bound for two-way nondeterministic complementation"
family: "129"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An exponential state lower bound for two-way nondeterministic complementation

> 结果族 129：Exponential state costs for two-way automata　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文证明双向非确定有限自动机（2NFA）的补运算不存在与字母表无关的多项式状态界：对每个 `@@M@@n\ge4@@` 构造 `@@M@@n@@` 状态的 2NFA，识别其补语言的任何 2NFA 至少需要 `@@M@@\tfrac12 2^{\lfloor(n-4)/127\rfloor}-1@@` 个状态，从而给出指数下界。

## 问题背景

双向非确定有限自动机（two-way nondeterministic finite automaton, 2NFA）的读头可在带端标记的输入上左右移动，接受当且仅当某条有限计算到达接受态。补运算问的是：是否存在一个与字母表无关的多项式 `@@M@@p@@`，使每个 `@@M@@n@@` 状态 2NFA 的补语言都能被 `@@M@@p(n)@@` 状态的 2NFA 识别？这条线索始于 Sakoda 与 Sipser 1978 年关于非确定性与双向自动机的经典工作；Vardi 1989 年给出指数级的一向非确定补机构造，Kapoutsis 2006 年证明了"单向活性"（one-way liveness）语言的补在所有扫掠式（sweeping）2NFA 中需指数状态，但读头只能在端标记处折返。对允许任意双向移动的补机，Guillon、Prigioniero 与 Taheri 在 2026 年的综述中仍将多项式补列为公开问题（他们只对可重写带格的 1-limited 自动机给出多项式补）。本文否定性地解决了这个字母表一致的多项式补问题。

## 主要结果

对每个 `@@M@@n\ge4@@`，取 `@@M@@H=\{1,\ldots,n-2\}@@`，字母表 `@@M@@\Sigma_n@@` 取为 `@@M@@H@@` 上全部二元关系（`@@M@@|\Sigma_n|=2^{(n-2)^2}@@`，随 `@@M@@n@@` 增长），考虑关系乘积活性语言 `@@M@@L_H=\{w:r(w)\ne\varnothing\}@@`，即 Sakoda–Sipser 的语言族 `@@M@@B_h@@`、Kapoutsis 所称的 one-way liveness。主定理：存在恰好 `@@M@@n@@` 状态的 2NFA `@@M@@A_n@@` 识别 `@@M@@L_H@@`，而任何识别补语言 `@@M@@\Sigma_n^*\setminus L(A_n)@@` 的 2NFA 至少需要 `@@M@@\tfrac12 2^{\lfloor(n-4)/127\rfloor}-1@@` 个状态。由于右端随 `@@M@@n@@` 指数增长，不存在与有限字母表无关的多项式补状态界。附带推论：借助 2DFA 可线性补的已知结果（Geffert–Mereghetti–Pighizzini），同一语言族也排除与字母表无关的多项式确定化界。

## 证明思路

证明把计算表示与有限代数下界分开。源机器极简：`@@M@@h+2=n@@` 个状态单向"猜路径"——初始态在左端标记处任选 `@@M@@p\in H@@` 进入，读到关系 `@@M@@R@@` 时若 `@@M@@(p,q)\in R@@` 则右移到 `@@M@@q@@`，抵达右端标记即接受；接受恰好当关系乘积非空。难点全在补机一侧。

先建立表示层。任何 `@@M@@s@@` 状态 2NFA 的有限计算被编码为"路径图"（path diagram）：一段计算由四个关系 `@@M@@F,B@@`（贯穿）与 `@@M@@L,R@@`（返回）记录其两个边界上的进出口，标签集是 `@@M@@m=s+1@@` 个带方向的机器状态副本。路径图按路径序合成，恰为 Martin–Mazorchuk 的分块二元关系幺半群（monoid of partitioned binary relations）`@@M@@\mathcal T_m@@`。加边只会增加接受路径，故 `@@M@@\tau(u)\sqsubseteq\tau(v)@@` 蕴含任意上下文中 `@@M@@u@@` 被 `@@M@@v@@` 替换后仍接受。而补机恰好接受乘积为空的字，用单点关系字母 `@@M@@I_{\{p\}},I_{\{q\}}@@` 做上下文即可逐对"测出"乘积内容，从而得到从 `@@M@@\mathcal T_{s+1}@@` 的子幺半群到 `@@M@@\mathcal R_H@@` 的满射同态 `@@M@@\phi@@`，且 `@@M@@\phi@@` 反转包含序：`@@M@@z\sqsubseteq w\Rightarrow\phi(w)\subseteq\phi(z)@@`。

再证代数下界 `@@M@@2m\ge2^{\lfloor(h-2)/127\rfloor}@@`。对幂等图 `@@M@@e@@`（`@@M@@e^2=e@@`），边界标签按"递归类"（recurrent classes）分组，至多 `@@M@@2m@@` 类；在角幺半群 `@@M@@e\mathcal T_me@@` 中，元素 `@@M@@z@@` 可能摧毁某些类的贯穿回路，记录为缺失集 `@@M@@\mathcal M_e(z)@@`。两个结构事实控制损失：其一（传输引理），经固定语境搬运时缺失界只放大两倍且落到单一公共集合上；其二（链界），沿嵌套幂等链逐级损失之和不超过初始预算的两倍——关键是一个二分法：每个新递归类要么包含一个未损失的旧类，要么包含两个旧类，用赋权 `@@M@@1/2@@` 的计数即可汇总。

最后是放大步骤。取 `@@M@@t=64@@`，归纳证明在像中添加一个非对角对（`@@M@@\phi(a)=I_H\cup\{(x,y)\}@@`）必须付出 `@@M@@|\mathcal M_e(a)|\ge D(h)=2^{\lfloor(h-2)/127\rfloor}@@` 的代价：先用置换的单位原像共轭出 `@@M@@2t@@` 个分别添加 `@@M@@(u_i,z)@@`、`@@M@@(z,v_j)@@` 的生成元，传输引理给它们公共预算 `@@M@@\le8tc@@`；相乘得 `@@M@@t^2@@` 个各添加一对 `@@M@@(u_i,v_j)@@` 的元素，沿长度 `@@M@@t^2@@` 的嵌套幂等链逐个加入，链界给出总代价 `@@M@@\le16tc@@`；而每一步限制到保留 `@@M@@h-127@@` 个点的小实例后由归纳假设至少花 `@@M@@D(h-127)/2@@`。两相比较得 `@@M@@c\ge(t/32)D(h-127)=D(h)@@`。代入 `@@M@@m=s+1@@`、`@@M@@h=n-2@@` 整理即得定理。

## 可信度与备注

主结果已在 Lean 中形式化证明（结果族 129 的官方文档）。同族姊妹篇用独立的"匹配图"秩损失论证对同一语言证明更强的确定性下界（指数率 `@@M@@h/62@@`，对比本文经线性补推出的 `@@M@@h/127@@`），两文方法独立而结论互相印证；本文的障碍甚至适用于非确定的补机，覆盖范围更广。作者为 OpenAI，按其官方声明，未经形式化的结果可能有问题，而本文主要结果已形式化，可信度高。

{% endraw %}
