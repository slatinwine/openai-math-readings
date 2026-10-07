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
