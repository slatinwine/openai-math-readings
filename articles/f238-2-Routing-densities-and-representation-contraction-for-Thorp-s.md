---
layout: default
title: "Routing densities and representation contraction for Thorp sweeps"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Routing densities and representation contraction for Thorp sweeps

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

赌场荷官有一种极简洗牌法：把牌对半分、两两一摞、每摞掷一枚硬币决定换不换。硬币看着乱来，但究竟要洗多少轮，整副牌才和"彻底洗匀"分不出差别？这篇论文给出精确回答：`@@M@@N=2^d@@` 张牌只需**固定次数**的整轮扫描就够了——而且这个速度已碰到理论天花板，一步都不能再省。

**关键词卡片**

- Thorp 洗牌（Thorp shuffle）：对半分、两两配对、每对按掷币结果决定交换与否的洗牌模型
- 坐标扫掠（coordinate sweep）：沿全部 `@@M@@d@@` 个二进制方向各配对交换一轮，等于 `@@M@@d@@` 次物理洗牌
- 总变差距离（total variation distance）：两个分布"差多远"的尺子，为 0 表示任何统计检验都分不出来
- 混合时间（mixing time）：把最坏初始牌序洗到与均匀分布几乎一样所需的最少步数
- 不可约表示（irreducible representation）：对称群的"基本成分"，逐个控制住它们就控制住整副牌

**看个具体例子**

取 `@@M@@N=2^{10}=1024@@` 张牌。硬币数给出下界：`@@M@@t@@` 次物理洗牌至多产生 `@@M@@2^{tN/2}@@` 种牌序，远小于 `@@M@@1024!@@`，所以至少约 `@@M@@2d=20@@` 次。本文证明：存在与 `@@M@@N@@` 无关的常数次扫掠，使任何起点的总变差随 `@@M@@N@@` 增大趋于零，上界与下界夹出 `@@M@@t_{\rm mix}=\Theta(\log N)@@`。证明图景是把"扫＋反扫"看成下面的开关网络，两张牌的路线若共用开关就会"牵手"，密度估计于是变成数圈。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="24" text-anchor="middle" font-size="15">一扫＋反扫 ≈ 一张掷币开关网络</text>
  <line x1="50" y1="70" x2="185" y2="97" stroke="#aaa" stroke-width="1.5"/>
  <line x1="50" y1="125" x2="185" y2="97" stroke="#aaa" stroke-width="1.5"/>
  <line x1="50" y1="180" x2="185" y2="207" stroke="#aaa" stroke-width="1.5"/>
  <line x1="50" y1="235" x2="185" y2="207" stroke="#aaa" stroke-width="1.5"/>
  <line x1="185" y1="97" x2="375" y2="97" stroke="#aaa" stroke-width="1.5"/>
  <line x1="185" y1="97" x2="375" y2="207" stroke="#aaa" stroke-width="1.5"/>
  <line x1="185" y1="207" x2="375" y2="97" stroke="#aaa" stroke-width="1.5"/>
  <line x1="185" y1="207" x2="375" y2="207" stroke="#aaa" stroke-width="1.5"/>
  <line x1="375" y1="97" x2="510" y2="70" stroke="#aaa" stroke-width="1.5"/>
  <line x1="375" y1="97" x2="510" y2="125" stroke="#aaa" stroke-width="1.5"/>
  <line x1="375" y1="207" x2="510" y2="180" stroke="#aaa" stroke-width="1.5"/>
  <line x1="375" y1="207" x2="510" y2="235" stroke="#aaa" stroke-width="1.5"/>
  <path d="M50,70 L185,97 L375,207 L510,235" fill="none" stroke="#d62728" stroke-width="3"/>
  <path d="M50,235 L185,207 L375,97 L510,70" fill="none" stroke="#d62728" stroke-width="3"/>
  <circle cx="185" cy="97" r="11" fill="#fff" stroke="#333" stroke-width="2"/>
  <circle cx="185" cy="207" r="11" fill="#fff" stroke="#333" stroke-width="2"/>
  <circle cx="375" cy="97" r="11" fill="#fff" stroke="#333" stroke-width="2"/>
  <circle cx="375" cy="207" r="11" fill="#fff" stroke="#333" stroke-width="2"/>
  <circle cx="50" cy="70" r="5" fill="#333"/>
  <circle cx="50" cy="125" r="5" fill="#333"/>
  <circle cx="50" cy="180" r="5" fill="#333"/>
  <circle cx="50" cy="235" r="5" fill="#333"/>
  <circle cx="510" cy="70" r="5" fill="#333"/>
  <circle cx="510" cy="125" r="5" fill="#333"/>
  <circle cx="510" cy="180" r="5" fill="#333"/>
  <circle cx="510" cy="235" r="5" fill="#333"/>
  <text x="50" y="52" text-anchor="middle" font-size="13">输入牌</text>
  <text x="510" y="52" text-anchor="middle" font-size="13">输出位</text>
  <text x="185" y="74" text-anchor="middle" font-size="12" fill="#555">子网A</text>
  <text x="375" y="74" text-anchor="middle" font-size="12" fill="#555">子网B</text>
  <text x="280" y="136" text-anchor="middle" font-size="13" fill="#b03030">两条路线交叉：是否共用○是计数关键</text>
  <text x="280" y="264" text-anchor="middle" font-size="13" fill="#555">○＝掷币开关（换/不换）；红＝两张牌各自的路线</text>
</svg>

</div>

**为什么值得关心**

洗牌是"局部随机操作如何搅浑全局信息"的基准模型，本文把悬置多年的多项式鸿沟一步填平到最优阶，主结果还通过了计算机形式化验证。

> 已 Lean 形式化

## 一句话结论

证明对 `@@M@@N=2^d@@` 张牌，绝对常数次坐标"扫"即可使整副牌排列律与均匀律的总变差趋于零，Thorp 洗牌混合时间具最优阶 `@@M@@\Theta(\log N)@@`；主结果已有 Lean 形式化证明。

## 问题背景

Thorp 洗牌把 `@@M@@2^d@@` 张牌对半分、成对独立公平交换，在旋转坐标下即沿 `@@M@@\mathbb F_2^d@@` 各坐标方向依次做公平交换；`@@M@@d@@` 个方向各一次为一"扫"（sweep），耗 `@@M@@d@@` 次物理洗牌。全牌混合的经典上界法是 Diaconis–Shahshahani 的有限群 Fourier 方法：控制律在每个不可约表示上的 Fourier 矩阵。但该方法为共轭不变律设计，那里 Fourier 矩阵是标量、可用特征比（character ratio）估计；定向的坐标扫给出的是投影矩阵的乘积，矩阵非正规，其幂与奇异值须同时控制，纯标量方法失效。历史界为：Morris `@@M@@O(d^{44})@@`、Montenegro–Tetali `@@M@@O(d^{29})@@`、Morris `@@M@@O((\log N)^4)@@` 与 `@@M@@O(d^3)@@`；部分置换方面，Gelman–Ta-Shma 的双子网递推给出无序 `@@M@@k@@` 子集误差 `@@M@@k(k-1)/(2N)@@`，Czumaj–Vöcking 借填充空牌的非马尔可夫耦合得到固定比例部分牌的 `@@M@@O((\log N)^2)@@`。计数下界 `@@M@@t\ge 2d-O(1)@@`（`@@M@@t@@` 次洗牌至多产生 `@@M@@2^{tN/2}@@` 个排列）与 `@@M@@O(d^3)@@` 上界之间的多项式鸿沟，正是本文要填平的。

## 主要结果

定理（路由密度与表示收缩）：存在绝对常数 `@@M@@\eta,c,C>0@@`，取 `@@M@@a=1/1000@@`。设 `@@M@@T_N@@` 为一扫的平均作用矩阵，`@@M@@K_N=T_N^*T_N@@` 是"一扫再接其反射"（用新鲜独立开关）的正算子，`@@M@@R_x(y)=(N)_k\Pr_{K_N}(x\mapsto y)@@` 为相对均匀单射 `@@M@@u_{N,k}@@` 的密度，则
`@@M@@D\log\E_{y\sim u_{N,k}}R_x(y)^{1+a}\le Ck(k/N)^\eta\qquad(1\le k\le N),@@`
对一切起始单射 `@@M@@x@@` 一致成立；且对充分大的二进 `@@M@@N@@` 与每个非平凡不可约表示（irreducible representation）`@@M@@\lambda\vdash N@@`，
`@@M@@DT_N(\lambda)=0\quad\text{或}\quad\|T_N(\lambda)\|_{\op}\le D_\lambda^{-c},@@`
其中 `@@M@@D_\lambda@@` 为维数。推论：绝对常数次正向扫即可使最坏起点的全排列律与均匀律总变差趋于零，故混合时间 `@@M@@t_{\mathrm{mix}}=\Theta(\log N)@@`（按物理洗牌计）。附带熵解释：`@@M@@\KL(P_x\|u_{N,k})\le(C/a)k(k/N)^\eta@@`，当 `@@M@@k/N\to0@@` 时每张被追踪牌的熵亏趋于零。

## 证明思路

骨架是把"扫+反射"（`@@M@@2d@@` 层回文 `@@M@@d,\dots,1,1,\dots,d@@`，拓扑即经典 Beneš 网络）在最外坐标处劈开，得到两个独立的半尺寸网络。给定输入、输出单射，追踪路径之间因共用外输入开关或共用外输出开关而连边，两族匹配的并集由交替的路与圈组成：每条路比圈少一条约束边，而每个圈给"路径分配给两个子网"的指派多出一个因子 2（指派数为 `@@M@@2^{s-a+C}@@`）。于是密度相对均匀单射的超额指数恰为 `@@M@@X=\sum_jC_j+\log_2\big((N)_k/N^k\big)@@`，`@@M@@C_j@@` 为第 `@@M@@j@@` 高度的圈数——密度估计归结为圈数的指数矩。

先证圈数难以累积。组合事实（蝶形接触引理）：`@@M@@h@@` 条不同路径在蝶形网络上至多共享 `@@M@@h\log_2h/2@@` 个开关。阶乘矩引理：给若干圈开"特异槽"并按非降长度逐条暴露路径，最后一条闭合路径的条件概率为 `@@M@@2^u/n@@`（`@@M@@u@@` 为该路径上已暴露的开关数）；对起点做均匀旋转以平均掉历史暴露的增益，得 `@@M@@\E\prod_j(F_j)_{a_j}\le(k/\sqrt n)^A\prod_jj^{-a_j/2}@@`。由于不同高度共享开关币，把高度分成交替两族的带状层，在条件估计下逐层求和（不假设高度间独立）；低高度靠稀疏占据——乘积边际界在公平交换下保持（一种负相依性）——高高度几何衰减，两段用 Cauchy–Schwarz 合并得稀疏密度界。稠密端把中央定尺寸子网换成独立均匀置换（在少数指定块容许恒等），并在半正定序下比较 `@@M@@K_N\le\theta^{\epsilon N/S}I+\sum_EQ_E@@`。

再从密度走向表示。截断引理：若核 `@@M@@Q=A+E@@`、`@@M@@A@@` 的元素 `@@M@@\le B/M@@`、`@@M@@E@@` 的行列和 `@@M@@\le p@@`，则在重数（multiplicity）为 `@@M@@m@@` 的不可约表示上 `@@M@@\|Q(\lambda)\|_{\op}\le\sqrt{B/m}+p@@`。序 `@@M@@k@@` 单射模包含 `@@M@@\lambda@@` 的重数为 `@@M@@m=f^{\lambda/(N-k)}@@`：首行很长的形状在略大的单射模中出现极多次，密度截断使 Hilbert–Schmidt 范数有界，重复拷贝逼出该形状上的小范数；超过 `@@M@@N/2@@` 行的形状被 `@@M@@T_N@@` 直接消灭（奇偶性）；中等维数用改造后的网络，极大维数用 `@@M@@k=N@@` 的密度界。最后由 Plancherel 与 Schatten 范数，对固定 `@@M@@r@@` 次正向扫求和 `@@M@@\sum_\lambda D_\lambda^{2-2rc_*}\to0@@`；全程不把非正规 `@@M@@T_N@@` 的幂与 `@@M@@(T_N^*T_N)@@` 的幂混同。后文的 Casimir 分裂、调和限制、自适应字母表、核心截断等给出另外的收缩机制与定量界面。

## 可信度与备注

本篇是族 238 的骨架篇，主结果已由 Lean 形式化（族内附文档 lean/docs/238.md）。其共享开关接触界、密度平滑等接口被族内多篇伙伴篇引用；姊妹篇《Conditional information under deterministic coordinate sweeps》《Conditional permutations in a revealed switching environment》从条件信息角度给出显式常数（`@@M@@2048d@@`、`@@M@@16040400\,d@@`），伙伴篇另给出 `@@M@@1600d@@` 的显式界，本篇则以绝对常数达到同阶。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结论已形式化，是族内可信度最高的一环。

{% endraw %}
