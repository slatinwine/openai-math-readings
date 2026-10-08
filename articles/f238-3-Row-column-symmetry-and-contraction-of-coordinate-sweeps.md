---
layout: default
title: "Row–column symmetry and contraction of coordinate sweeps"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Row–column symmetry and contraction of coordinate sweeps

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把 1024 张牌的座位号改写成 32×32 的棋盘，你会突然看懂这种洗牌：一半的掷币只在同一行里换牌，另一半只在同一列里换。这篇论文就靠这个"行列分解"视角，证明了 Thorp 洗牌只需 `@@M@@\Theta(\log N)@@` 次物理洗牌就能把整副牌洗匀——把悬置多年的 `@@M@@O(d^3)@@` 上界一步改进到理论最优。

**关键词卡片**

- Thorp 洗牌（Thorp shuffle）：`@@M@@N=2^d@@` 张牌两两配对、掷币换牌的模型，位置可看作 `@@M@@d@@` 位二进制编号
- 行列分解（row–column split）：把 `@@M@@d@@` 个坐标对半分，座位排成 `@@M@@\sqrt N\times\sqrt N@@` 棋盘，前半扫在行内、后半在列内
- 相对熵（relative entropy）：信息论中两个分布差异的度量；论文证明行列两套随机性的"交叠税"只由删掉的格子数决定
- Schatten 范数（Schatten norm）：给矩阵"大小"定标的尺子，用以度量洗牌算子在每个成分上的收缩
- 杨图（Young diagram）：对称群不可约表示的形状"身份证"，形状决定维数

**看个具体例子**

`@@M@@N=2^{10}=1024@@` 时棋盘为 32×32：前 5 个方向＝每行内部的小扫掠，后 5 个方向＝每列内部（下图是其缩影）。证明对 `@@M@@d@@` 归纳：小棋盘上已经收缩，"交叠熵"估计保证行、列两半拼回大棋盘时不损失太多，专门设计的权重 `@@M@@W_\lambda@@` 恰好支付"补回删掉格子"的账。结论：固定次数扫掠后全变差趋于 0，混合时间 `@@M@@\Theta(d)@@`，与计数下界 `@@M@@2d-O(1)@@` 同阶。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="24" text-anchor="middle" font-size="15">坐标对半分：位置变成 √N×√N 棋盘</text>
  <line x1="130" y1="45" x2="130" y2="265" stroke="#333" stroke-width="1.5"/>
  <line x1="185" y1="45" x2="185" y2="265" stroke="#333" stroke-width="1.5"/>
  <line x1="240" y1="45" x2="240" y2="265" stroke="#333" stroke-width="1.5"/>
  <line x1="295" y1="45" x2="295" y2="265" stroke="#333" stroke-width="1.5"/>
  <line x1="350" y1="45" x2="350" y2="265" stroke="#333" stroke-width="1.5"/>
  <line x1="130" y1="45" x2="350" y2="45" stroke="#333" stroke-width="1.5"/>
  <line x1="130" y1="100" x2="350" y2="100" stroke="#333" stroke-width="1.5"/>
  <line x1="130" y1="155" x2="350" y2="155" stroke="#333" stroke-width="1.5"/>
  <line x1="130" y1="210" x2="350" y2="210" stroke="#333" stroke-width="1.5"/>
  <line x1="130" y1="265" x2="350" y2="265" stroke="#333" stroke-width="1.5"/>
  <circle cx="212" cy="127" r="6" fill="#333"/>
  <circle cx="267" cy="182" r="6" fill="#333"/>
  <circle cx="157" cy="237" r="6" fill="#333"/>
  <line x1="145" y1="72" x2="335" y2="72" stroke="#1f77b4" stroke-width="3"/>
  <polygon points="155,67 143,72 155,77" fill="#1f77b4"/>
  <polygon points="325,67 337,72 325,77" fill="#1f77b4"/>
  <line x1="322" y1="68" x2="322" y2="242" stroke="#d62728" stroke-width="3"/>
  <polygon points="317,78 322,66 327,78" fill="#d62728"/>
  <polygon points="317,232 322,244 327,232" fill="#d62728"/>
  <text x="240" y="38" text-anchor="middle" font-size="13" fill="#1f77b4">前半扫：行内掷币换牌</text>
  <text x="365" y="155" font-size="13" fill="#d62728">后半扫：列内换牌</text>
  <text x="365" y="180" font-size="13" fill="#555">●＝坐在格里的牌</text>
</svg>

</div>

**为什么值得关心**

它与同族另外两条技术路线（相容熵、随机子平面）各自独立证得同一最优阶，互为印证——一个难题被三把不同的钥匙同时打开。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明：`@@M@@N=2^d@@` 张牌的 Thorp 洗牌（Thorp shuffle）只需 `@@M@@\Theta(\log N)@@`（即 `@@M@@\Theta(d)@@`）次物理洗牌即可让**整副排列**在全变差（total variation）意义下混合到均匀分布，与计数下界 `@@M@@2d-O(1)@@` 同阶，把此前 `@@M@@O(d^3)@@` 的最好上界一举改进到最优阶。

## 问题背景

Thorp 洗牌由 Thorp 于 1973 年研究 Faro 纸牌游戏的非随机洗牌与作弊问题时提出：把 `@@M@@N=2^d@@` 张牌对半分，依二进制坐标依次对每对牌独立地"交换或不动"。它是最贴近真实洗牌的物理模型之一，但其整副排列的混合速度长期悬而未决。Morris 2008 用演化集（evolving sets）得到 `@@M@@O(d^{44})@@`，Montenegro–Tetali 改进到 `@@M@@O(d^{29})@@`，Morris 2009 对偶数牌数得到 `@@M@@O((\log N)^4)@@`，2013 年又对二的幂次牌数得到 `@@M@@O(d^3)@@`。难点在于：单张牌一次坐标扫掠（coordinate sweep，即 `@@M@@d@@` 次物理洗牌）后已完全均匀，但所有牌共用同一批随机开关，联合分布保有长程依赖；谱方法要求控制对称群 `@@M@@S_N@@` 的**全部**不可约表示上的 Fourier 矩阵，而连接下界（`@@M@@t@@` 次洗牌至多产生 `@@M@@2^{tN/2}@@` 个排列）早已给出 `@@M@@2d-O(1)@@`。

## 主要结果

论文的核心是如下"加权扫掠矩"定理：存在只依赖杨图（Young diagram）`@@M@@\lambda@@` 的正权 `@@M@@W_\lambda@@` 与绝对常数 `@@M@@p_*@@`，使得对一切 `@@M@@d\ge 1@@` 和 `@@M@@\lambda\vdash 2^d@@`，
`@@M@@DD_\lambda^{3/4}\le W_\lambda\le D_\lambda,\qquad W_\lambda\|K_d(\lambda)\|_{p_d}^{p_d}\le 1,@@`
其中 `@@M@@D_\lambda@@` 是不可约表示 `@@M@@V_\lambda@@` 的维数，`@@M@@K_d(\lambda)@@` 是一次扫掠的群代数 Fourier 矩阵，`@@M@@2\le p_d\le p_*@@` 一致有界。由此立得算子范数 `@@M@@\|K_d(\lambda)\|_{\rm op}\le D_\lambda^{-3/(4p_*)}@@`。再经 Diaconis–Shahshahani 的 Plancherel 公式加 Cauchy–Schwarz，固定（绝对常数）次扫掠后全变差距离趋于零，得到推论：混合时间满足
`@@M@@D\Big\lceil\tfrac2N\log_2\tfrac{3N!}{4}\Big\rceil\le t_{\rm mix}(d)\le Cd,\qquad N=2^d,@@`
即 `@@M@@t_{\rm mix}(d)=\Theta(d)=\Theta(\log N)@@`，且对最坏初始牌序一致成立。

## 证明思路

骨架是对坐标个数 `@@M@@d@@` 的归纳：把一次扫掠拆成前后两半，位置随之变成 `@@M@@\sqrt N\times\sqrt N@@` 棋盘，前半在行内、后半在列内各是独立的小扫掠。先证明关键的"横向交叠"估计：把子群投影的控制化为正的概率态乘积，用四分之一次幂滤波归一化后，误差归结为均匀选中格点相对"行×列边缘乘积"的相对熵（relative entropy）——这一熵代价只由删除格点数控制而与其排布无关（Carlen–Cordero-Erausquin 的熵/乘积对偶的有限形式）。再处理"补回删除格子"：选 `@@M@@b@@` 使 `@@M@@V_\lambda@@` 含于诱导表示 `@@M@@\mathrm{Ind}(V_a\otimes V_b)@@`，其按洞的摆放位置直和分解；摆放熵恰好由父图与子图之间的权差支付——这正是权 `@@M@@W_\lambda@@`（经钩形修剪构造）的设计目的。纠缠的载体向量用一个初等引理处理而不引入额外维数因子。随后用加权 Schatten 范数（Schatten norm）插值把投影估计传到任意矩阵，对数误差 `@@M@@O((\log D_\lambda)/d)@@` 与指数 `@@M@@p@@` 无关，于是归纳时指数只需乘 `@@M@@1+C/d@@`，沿逐次二分的尺度求乘积有界，得到一致指数 `@@M@@p_*@@`；第一行几乎占满全图的"稀疏"表示则用路径碰撞的森林估计直接覆盖（利用随机开关保持的负相关不等式），有限个小维数上的严格谱隙起动整个归纳。最后，重复扫掠的全变差由 `@@M@@\frac14\sum_{\lambda\ne(N)}D_\lambda\|K_d(\lambda)^j\|_2^2\le\frac14\sum D_\lambda^{-2}@@` 控制，此和趋于零。论文还给出同一交叠估计的另外两条独立路线：其一是"标号框架"路线（删除框架引理、选秩 Schatten-8 估计、符号张量估计与短时间窗稀疏估计互补拼合）；其二是"相干态"路线（把洞保留为有序表，恢复因子显式为 `@@M@@e^{3l}\binom Nl@@`，用 Perelomov 最高权相干态轨道与 Kempf–Ness 型最小范数矩匹配做归一化，配合 Araki–Lieb–Thirring 迹不等式封闭归纳）。三条路线各自封闭一个有界指数归纳，结论一致。

## 可信度与备注

本文暂无形式化证明；同族的《Compatibility entropy and the spectrum of a Thorp sweep》主结果已有 Lean 形式化，且姊妹篇《Random-subspace tests and trace smoothing for coordinate sweeps》被本文明确引用为相伴工作，提供部分迹平滑估计，三者在同一框架下互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
