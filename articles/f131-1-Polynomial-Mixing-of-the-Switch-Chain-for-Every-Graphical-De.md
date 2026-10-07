---
layout: default
title: "Polynomial mixing of the switch chain for every graphical degree sequence"
family: "131"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Polynomial mixing of the switch chain for every graphical degree sequence

> 结果族 131：Rapid mixing of graph switches for every degree sequence　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明了简单无向图情形的 Kannan–Tetali–Vempala 猜想：对每个可图化度序列，惰性交换链的总变差混合时间不超过 `@@M@@2n^8@@`；同时给出期望多项式比特时间的精确均匀采样算法。

## 问题背景

给定度序列（degree sequence）`@@M@@d=(d_1,\dots,d_n)@@`，如何在所有恰好实现它的简单图上均匀采样？这是网络研究中基本零模型（null model）与近似计数的核心问题。Kannan、Tetali、Vempala 于 1999 年在正则二部情形的工作中提出了交换链（switch chain）纲领：每次操作删去两条边，并在四个端点上改放另一种完美匹配，从而保持全部顶点度数；他们猜想这类链对一切可实现的度规范都快速混合（rapid mixing）。此后，正则无向情形由 Cooper–Dyer–Greenhill 解决，Greenhill–Sfragara 等处理了带定量限制的不正则度，Erdős 等人证明了对所有 P-稳定（P-stable）度序列族的快速混合，二部情形最近由 Fu–Qin–Wang 证明。但对单个度序列不作任何额外假设的简单无向情形长期悬而未决——本文正面解决。

## 主要结果

论文有两条主结果。其一（定理 1.1）：设 `@@M@@n\ge4@@`，`@@M@@d@@` 可图化（graphical），`@@M@@\Omega_d@@` 为度向量等于 `@@M@@d@@` 的简单无向图全体。考虑惰性链：以 `@@M@@1/2@@` 概率不动；否则均匀取四元顶点集 `@@M@@S@@`，再均匀取 `@@M@@S@@` 上完全图六对有序完美匹配 `@@M@@(F,F')@@` 中的一对，若 `@@M@@F@@` 的两边都在且 `@@M@@F'@@` 的两边都不在就换成 `@@M@@F'@@`。则在总变差距离（total variation distance）`@@M@@1/4@@` 处，混合时间 `@@M@@t_{\mathrm{mix}}(d)\le 2n^8@@`；若 `@@M@@|\Omega_d|>1@@`，谱隙（spectral gap）至少为 `@@M@@[24n^2\binom n4]^{-1}@@`。其二（推论 1.2，精确采样）：存在随机算法，输入任意可图化标长度向量，使用无偏随机比特，几乎必然终止，输出恰按均匀分布取自 `@@M@@\Omega_d@@` 的图，期望比特运行时间被输入编码长度的固定多项式界住。

## 证明思路

证明不直接分析交换链，而是分析更强的"对重采样"（pair resampling）算子。取顶点对 `@@M@@a=\{i,j\}@@`，固定其余一切邻接关系，只重新随机分配每个恰与 `@@M@@a@@` 一端相邻的"单邻点"（singleton）归哪一端；每条 `@@M@@a@@`-纤维等距于固定尺寸的均匀子集切片（subset slice）。令 `@@M@@E_a@@` 为关于该划分的条件期望投影，`@@M@@h_a=I-E_a@@`，`@@M@@H=\sum_a h_a@@`。核心是二次型不等式 `@@M@@H^2\succeq H@@`。先按 Caputo 的平方生成元方法（squared-generator method）展开 `@@M@@H^2=\sum_T H_T^2-(n-3)H+D@@`，按两个指标对是否相交分组。相交项归结为固定行、列和的三行 0-1 矩阵上的方差不等式：三个行函数之和的方差至多为各行方差之和的两倍；其证明分两层——块大小固定时用标签对换算子的谱分解控制（思路源自 Carlen–Lieb–Loss 的对称群热流），块计数随机时用 Fu–Qin–Wang 的相邻总量耦合把算子范数压到 `@@M@@2@@`。不相交项 `@@M@@D@@` 是真正的难点：无向图上不相连的对交换会相互依赖，单个交叉项可为负。论文证明固定公共数据后这种依赖的秩至多为一，其负贡献由"两个邻居获得同一端点"的中心化指示投影控制；再用一条切片上的投影比较引理（借助 Johnson 切片分解的低次部分），证明这些投影之和被同切片的对换能量控制，求和后负项成对相消，故 `@@M@@D@@` 半正定。合起来得 `@@M@@H^2\succeq H@@`。随后用带确定性平局判决的 Havel 型论证证明交换链连通，从而 `@@M@@H@@` 的核恰为常数，得到 Poincaré 不等式 `@@M@@\operatorname{Var}_{\pi_d}(f)\le\langle f,Hf\rangle@@`。最后把整条纤维的重采样与纤维内两个单邻点的交换作热浴比较（heat-bath comparison），得 `@@M@@H\preceq 2n^2L@@`（`@@M@@L@@` 为交换图 Laplacian）；结合 `@@M@@I-P_d=L/(12\binom n4)@@` 与 `@@M@@|\Omega_d|\le 2^{\binom n2}@@`，收尾得到 `@@M@@2n^8@@`。精确采样则用稀有残余混合（rare residual mixture）技巧：取极小 `@@M@@\delta=2^{-D}@@` 使 `@@M@@(1-\delta)p\le\pi_d@@` 逐点成立，以 `@@M@@1-\delta@@` 概率走 `@@M@@t@@` 步输出近似分布 `@@M@@p@@`，以 `@@M@@\delta@@` 概率枚举全空间、按整数权重 `@@M@@w_G@@` 精确补偏；`@@M@@\delta@@` 取得足够小，使枚举的指数成本在期望中被打平，而链达到所需精度只需多项式步数，故期望比特时间仍为多项式。

## 可信度与备注

任务元数据标记本篇为未形式化，暂无 Lean 形式化证明，请以社区核验为准；作者在引言中声明全部证明成分均在文中给出。本结果族仅此一篇手稿，其技术骨架与两支姊妹文献互相支撑：三行方差不等式复证并推广了二部情形 Fu–Qin–Wang 的定理 5.1，精确采样套用 Göbel–Liu–Manurangsi–Pappik 的稀有残余混合框架。按 OpenAI 官方声明，未经形式化的结果可能存在问题，采用前请以待核验态度对待。

{% endraw %}
