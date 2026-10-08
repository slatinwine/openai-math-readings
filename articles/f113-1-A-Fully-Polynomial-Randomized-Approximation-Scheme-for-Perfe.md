---
layout: default
title: "A Fully Polynomial Randomized Approximation Scheme for Perfect Matchings in General Graphs"
family: "113"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Fully Polynomial Randomized Approximation Scheme for Perfect Matchings in General Graphs

> 结果族 113：Approximate counting and entropy of perfect matchings　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

联谊会上有 2n 个人，任意两人都可以结对，要把所有人两两配对——找出一种配法早就是教科书算法，但"数清一共有多少种配法"却被证明是 #P 完全的，几乎无望精确。本文给出随机近似算法：像"标记再捕"估计湖里有多少鱼一样，在多项式时间内给出相对误差 ε、成功率 1−δ 的估计，而且根本配不成对时必然如实输出 0。这补上了 1989 年提出、悬了近四十年的最后一块拼图。

**关键词卡片**

- 完美匹配（perfect matching）：让每个顶点恰好连一条边的边集，即全员结对。
- #P 完全（#P-complete）：计数问题的最高难度等级，精确求解被认为无望。
- FPRAS（fully polynomial randomized approximation scheme）：时间多项式于输入长、1/ε 与 log(1/δ) 的随机近似计数格式。
- 马尔可夫链蒙特卡洛（Markov chain Monte Carlo）：设计随机游走来采样，用样本估计数量。
- 退火（annealing）：从容易采样的完全图出发逐步收紧到目标图，逐级估比值再连乘。

**看个具体例子**

把立方体的 8 个顶点、12 条棱看作一张图：它共有 9 个完美匹配（图中红色 4 条"斜棱"是其中之一）。定理的数字版：`@@M@@\Pr[(1-\epsilon)\cdot 9\le\hat Z\le(1+\epsilon)\cdot 9]\ge 1-\delta@@`——比如取 ε=1%，输出就落在 8.91 与 9.09 之间；若图根本无法全员结对，则每次执行都输出 0。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="15" fill="#333333">立方体图（8 顶点 12 棱）：红色 4 条棱是一个完美匹配</text>
  <rect x="190" y="50" width="120" height="120" fill="none" stroke="#bbbbbb" stroke-width="2"/>
  <line x1="150" y1="80" x2="190" y2="50" stroke="#e0592a" stroke-width="4"/>
  <line x1="270" y1="80" x2="310" y2="50" stroke="#e0592a" stroke-width="4"/>
  <line x1="270" y1="200" x2="310" y2="170" stroke="#e0592a" stroke-width="4"/>
  <line x1="150" y1="200" x2="190" y2="170" stroke="#e0592a" stroke-width="4"/>
  <rect x="150" y="80" width="120" height="120" fill="none" stroke="#888888" stroke-width="2"/>
  <circle cx="190" cy="50" r="7" fill="#777777"/>
  <circle cx="310" cy="50" r="7" fill="#777777"/>
  <circle cx="310" cy="170" r="7" fill="#777777"/>
  <circle cx="190" cy="170" r="7" fill="#777777"/>
  <circle cx="150" cy="80" r="7" fill="#3b82c4"/>
  <circle cx="270" cy="80" r="7" fill="#3b82c4"/>
  <circle cx="270" cy="200" r="7" fill="#3b82c4"/>
  <circle cx="150" cy="200" r="7" fill="#3b82c4"/>
  <text x="280" y="245" text-anchor="middle" font-size="13" fill="#555555">每个顶点恰好连一条红棱 ⇒ 8 人全部结对；立方体图共有 9 个完美匹配</text>
</svg>

</div>

**为什么值得关心**

一般图完美匹配计数是近似计数理论的地标难题：二部图 2004 年解决、平面图早有精确解，一般图这一格被本文填上，连带指定度数、指定大小的匹配也能近似计数。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
对任意有限简单无向图给出完美匹配计数的全多项式随机逼近格式（FPRAS），时间多项式于输入长度、`@@M@@\varepsilon^{-1}@@` 与 `@@M@@\log\delta^{-1}@@`，无完美匹配时确定性输出零，正面解决了 Jerrum–Sinclair 在 1989 年提出的一般图难题。

## 问题背景

图 `@@M@@G@@` 的完美匹配（perfect matching）是让每个顶点恰好被一条边覆盖的边集，记其数目为 `@@M@@Z(G)@@`。"找到一个"与"数清全部"难度悬殊：Edmonds（1965）给出多项式时间求最大匹配的算法，而 Valiant（1979）证明即使在二部图上精确计数也是 #P 完全（#P-complete）的——即 0-1 矩阵的永久积（permanent）；只有平面图可由 Kasteleyn 的 Pfaffian 方法精确求解。近似计数须区分三个问题：Jerrum 与 Sinclair（1989）对"所有匹配的总数"给出 FPRAS；Jerrum、Sinclair、Vigoda（JSV，2004）对二部图完美匹配（非负矩阵永久积）给出 FPRAS；而一般图完美匹配的近似计数由 Jerrum–Sinclair 1989 年论文第 7(i) 节明确提出，此后近四十年是近似计数的标杆难题。卡点很明确：完美匹配可能只占匹配空间指数小的一份，"完美+近完美匹配"马尔可夫链的平稳质量过小；Štefankovič、Vigoda 与 Wilmes（2018）更构造出图例，证明任何 JSV 型链在这种图上要么平稳概率指数小、要么混合（mixing）指数慢。因此必须更换状态空间与能量比较方式。

## 主要结果

主定理（Theorem 1.1）：存在一致的经典随机算法，输入图 `@@M@@G@@` 与有理数 `@@M@@0<\varepsilon<1@@`、`@@M@@0<\delta<1/2@@`，输出非负有理数 `@@M@@\widehat Z@@`，满足

`@@M@@D\Pr\bigl[(1-\varepsilon)Z(G)\le\widehat Z\le(1+\varepsilon)Z(G)\bigr]\ge 1-\delta,@@`

且最坏情形比特时间多项式于输入编码长度、`@@M@@\varepsilon^{-1}@@`、`@@M@@\log\delta^{-1}@@`；若 `@@M@@Z(G)=0@@`，算法必然输出零（先以 Edmonds 算法做确定性存在性检测）。第 10 节还推出推论：规定每顶点度数的边子集（经 Tutte 归约到 `@@M@@f@@`-因子，f-factor）与指定大小 `@@M@@k@@` 的匹配（添加 `@@M@@n-2k@@` 个哑点）这两族对象，同样可近似计数，并可在全变差（total variation）意义下近似均匀采样，且采样器每次执行都返回可行对象。

## 证明思路

算法骨架沿用 JSV 式退火（annealing）：从完全图 `@@M@@K_V@@` 出发——其匹配数 `@@M@@(n-1)!!@@` 精确已知——把非边的活动度按 `@@M@@b^{-j}@@`（`@@M@@b=1+1/n@@`）逐级压低，估计相邻两级配分函数之比再连乘；级数 `@@M@@K@@` 足够大后，用到非边的匹配总偏差被压入 `@@M@@\varepsilon@@` 之内。采样的一大障碍是完美匹配质量塌缩，作者引入顶点缩放（vertex scaling）`@@M@@\lambda_{ij}=w_{ij}s_is_j@@` 维持平衡（balanced）条件：各顶点处两洞配分比（two-hole partition ratio）`@@M@@g_\lambda(ij)@@` 的行最大值始终落在 `@@M@@[1/4,1]@@`。

为让一次样本同时给出比值与两洞信息，作者把图放大：每条逻辑边替换为长 `@@M@@4p+1@@` 的带权路径，活动度相邻成对相等、由端点向中心递减，使实路径匹配与逻辑完美匹配一一对应且权只差公因子；再按瓶颈相似度（bottleneck similarity，两顶点间所有路径上最小活动度的最大值）的阈值分层构造标签树，在每个树包（bag）内添加活动度约 `@@M@@h_l/D@@` 的弱团边。核心的洞界定理断言：平衡时对任意偶数洞集 `@@M@@U@@` 有 `@@M@@g_\lambda(U)\Phi_B(U)\le 2D_0^{|U|/2}@@`，其中 `@@M@@\Phi_B@@` 是配对容量（pairing capacity，两两瓶颈值乘积在所有配对上的最大值）。其证明先用两个匹配的交替叠加（alternating overlay）得到四洞不等式，再把洞沿强路径逐点搬移、以行最大值归一使误差相加而非相乘，最后对新增边参数微分配分函数。由此辅助团边至多令配分函数翻倍（膨胀因子 `@@M@@I\le2@@`），一次样本以至少 `@@M@@1/2@@` 的概率全为实边；又在每条中心边上预留活动度 `@@M@@1/D@@` 的"探针"（probe），以精确恒等式暴露两洞比值，供下一轮单遍扫描式的尺度更新。

采样器本身是全新的乘积空间链：状态是两个匹配组成的对，提议分双边换边、换色、交替圈（alternating cycle）交换三类，按 Metropolis 规则接受。能量比较不走路径拥堵定理，而是把每个交替圈按标签树自适应地四边形剖分（quadrangulation），把整圈差异写成精确的带号恒等式——每条内部对角线在两侧互补弧上的贡献恰好相消——再用编码引理（每个需求至多 `@@M@@(10N)^{30}@@` 个原像）与圈交换控制语境误差。但这条两坐标不等式只控制可加函数；作者进而搭一座"梯子"：把活动度夹到 `@@M@@[c^{-t},c^t]@@`（`@@M@@c=1+N^{-2}@@`）得到一列相邻密度比不超过 2 的层，每层放 `@@M@@q=32L@@` 个独立副本，底层单位活动度可由树状动态规划精确计数与精确采样；借 Efron–Stein 正交分解与槽位排序，使每对坐标的残差交互项只被记费一次，复制平均将其吸收，从而对任意函数得到谱隙（spectral gap）下界与多项式混合时间。计数阶段每级取 `@@M@@S@@` 个独立样本，由 Hoeffding 不等式单次试验以至少 `@@M@@0.9@@` 的概率成功，取 `@@M@@10(\lceil\log_2\delta^{-1}\rceil+1)+1@@` 次独立试验的中位数即把置信放大至 `@@M@@1-\delta@@`。第 9 节补出完整的有限比特实现，所有参数有固定次数的多项式界。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。同族姊妹篇《Entropy and Face Dimension of the Perfect-Matching Polytope》证明了完美匹配熵猜想且主结果已 Lean 形式化，并给出确定性的 `@@M@@512^{-n}@@` 因子近似计数，与本篇的随机相对误差路线互补。按 OpenAI 官方声明，未经形式化的结果可能存在问题；且本文多项式指数很大，常数是为证明透明而设，并非实用运行时间。

{% endraw %}
