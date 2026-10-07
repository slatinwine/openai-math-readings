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
