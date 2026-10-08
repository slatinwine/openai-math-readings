---
layout: default
title: "Exact asymptotic moduli in a Daugavet subspace of L1"
family: "331"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Exact asymptotic moduli in a Daugavet subspace of L1

> 结果族 331：Reflexive midpoint convexity and diamond distortion　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

给球的"渐近圆度"画体检曲线：一种指标是中点版——两边对称地迈步，看范数平均涨多少；另一种是单侧版——只往一边迈，看涨多少。这篇论文在 `@@M@@L^1@@`（可积函数空间）的一个特殊子空间里，把两条曲线精确地算了出来：中点曲线在小步长时是 `@@M@@t/2@@` 的线性上升，而单侧曲线直到步长 `@@M@@2@@` 之前纹丝不动是零。两条曲线一分开，"中点圆度换不出单侧圆度"就不再是印象，而是精确事实。

**关键词卡片**

- Daugavet 性质（Daugavet property）：对每个秩一算子 `@@M@@T@@` 都有 `@@M@@\|I+T\|=1+\|T\|@@`；球面处处存在几乎正对的点，极端"圆"。
- 平均渐近中点模（averaged midpoint modulus）：对称迈步 `@@M@@t@@` 时范数平均增益的最坏情形——中点圆度的曲线。
- 单侧渐近模（one-sided asymptotic modulus）：只往一边走 `@@M@@t@@` 的增益曲线——单侧圆度。
- 渐近一致凸（AUC）：单侧模非零的加强圆度；本文证明任何等价范数都达不到。
- 测度预紧（totally bounded in measure）：单位球在"依测度"距离下可用有限网覆盖，函数们不无限分裂。

**看个具体例子**

定理算出的两条曲线：`@@M@@H_E(x,t)=\max\{t/2,\ t-1\}@@`，`@@M@@D_E(x,t)=\max\{0,\ t-2\}@@`。代入步长 `@@M@@t=1@@`：

`@@M@@DH_E(x,1)=\max\{0.5,\ 0\}=0.5,\qquad D_E(x,1)=\max\{0,\ -1\}=0@@`

中点版涨一半，单侧版原地踏步；直到 `@@M@@t=2@@` 单侧曲线才开始抬头。这张"体检单"同时证明：继承范数非 AUC，且任何等价范数都不可能 AUC。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="28" font-size="15" fill="#222">两条圆度曲线：中点版先涨，单侧版到 t=2 才动</text>
  <line x1="90" y1="230" x2="520" y2="230" stroke="#999" stroke-width="1"/>
  <line x1="90" y1="230" x2="90" y2="40" stroke="#999" stroke-width="1"/>
  <line x1="90" y1="230" x2="290" y2="140" stroke="#b0348f" stroke-width="2.5"/>
  <line x1="290" y1="140" x2="490" y2="50" stroke="#b0348f" stroke-width="2.5"/>
  <line x1="90" y1="230" x2="290" y2="230" stroke="#2f8f4e" stroke-width="2.5"/>
  <line x1="290" y1="230" x2="490" y2="140" stroke="#2f8f4e" stroke-width="2.5"/>
  <line x1="290" y1="230" x2="290" y2="140" stroke="#bbb" stroke-width="1" stroke-dasharray="5 4"/>
  <circle cx="190" cy="185" r="4" fill="#b0348f"/>
  <text x="198" y="180" font-size="13" fill="#b0348f">t=1：H=0.5</text>
  <text x="95" y="250" font-size="13" fill="#666">0</text>
  <text x="282" y="250" font-size="13" fill="#666">t=2</text>
  <text x="480" y="250" font-size="13" fill="#666">t=4</text>
  <text x="60" y="60" font-size="13" fill="#666">增益</text>
  <text x="300" y="80" font-size="14" fill="#b0348f">中点模 max{t/2, t−1}</text>
  <text x="300" y="215" font-size="14" fill="#2f8f4e">单侧模 max{0, t−2}</text>
</svg>

</div>

**为什么值得关心**

它把"AMUC 不蕴含 AUC 可再赋范"从定性分离推进到精确模曲线，并给出 Kadets–Werner 构造的完整定量实现。

> 主结果已 Lean 形式化

## 一句话结论
对单位球在测度下完全有界且具 Daugavet 性质的 `@@M@@L^1@@` 子空间，本文把平均渐近中点模与单侧渐近模精确算出为 `@@M@@\max\{t/2,t-1\}@@` 与 `@@M@@\max\{0,t-2\}@@`，并证明任何等价范数都不渐近一致凸，把 Baudier 对"中点凸 ≠ 可再赋范一致凸"的分离做到了精确定量。

## 问题背景
渐近一致凸（asymptotically uniformly convex，AUC）与渐近中点一致凸（asymptotic midpoint uniform convexity，AMUC）是 Banach 空间几何中刻画单位球"渐近圆度"的两种强弱不同的性质：前者要求沿余维有限子空间的方向单侧移动时范数有增益，后者只要求两个对称端点的平均值有增益。Dilworth、Kutzarova、Randrianarivony、Revalski 与 Zhivkov（2016）定义了 AMUC 并提出问题：AMUC 与 AUC 是否在再赋范（renorming）意义下等价？Baudier（2026）给出否定回答：他证明单位球在测度下相对紧的 `@@M@@L^1@@` 子空间自动具有 AMUC，并套用 Kadets–Werner 的 Daugavet 例子。卡在哪里的是定量精度：此前只知道模的某个线性下界，两条模曲线的确切形状、以及"排除一切等价 AUC 范数"的完整论证，都未完成。

## 主要结果
设 `@@M@@E@@` 是概率空间上 `@@M@@L^1@@` 的无限维闭实子空间，满足两条几何假设：单位球依测度度量 `@@M@@d(f,g)=\inf\{a>0:\mathbb P(|f-g|>a)<a\}@@` 完全有界；继承的 `@@M@@L^1@@` 范数具 Daugavet 性质（Daugavet property，即对每个秩一算子 `@@M@@T@@` 有 `@@M@@\|I+T\|=1+\|T\|@@`）。对单位向量 `@@M@@x@@` 与 `@@M@@t>0@@`，定义平均中点模 `@@M@@H_E(x,t)@@` 为先取余维有限子空间 `@@M@@F@@`、再取 `@@M@@F@@` 中范数 `@@M@@\ge1@@` 的方向 `@@M@@y@@` 时 `@@M@@\frac{\|x+ty\|_1+\|x-ty\|_1}{2}-1@@` 的下确界的上确界，单侧模 `@@M@@D_E(x,t)@@` 类似。定理证明：在每个单位中心处 `@@M@@H_E(x,t)=\max\{t/2,t-1\}@@`，`@@M@@D_E(x,t)=\max\{0,t-2\}@@`。于是平均模在原点附近有线性增长 `@@M@@t/2@@`，而单侧模直到 `@@M@@t=2@@` 都恒为零——继承范数不仅自身非 AUC，且任何等价范数都不可能是 AUC。论文还给出 Kadets–Werner 构造的完整定量实现，保证满足两假设的空间确实存在，使整篇论证自足。

## 证明思路
下界的核心是"截断＋符号泛函"。由恒等式 `@@M@@(|a+b|+|a-b|)/2=\max\{|a|,|b|\}@@`，平均增量恰等于 `@@M@@\int(t|y|-|x|)_+\,d\mathbb P@@`，因此只需控制 `@@M@@y@@` 与 `@@M@@x@@` 的重叠。把每个单位向量在高度 `@@M@@|x|/t@@` 处逐点截断，截断算子逐点 1-Lipschitz，把测度预紧的单位球变成 `@@M@@L^1@@` 紧集；取其有限 `@@M@@\varepsilon@@`-网，用网元的符号泛函的公共核作 `@@M@@F@@`，则 `@@M@@F@@` 中任何单位向量的截断至多保留一半质量，即至少一半质量落在截断高度之外，直接给出 `@@M@@t/2@@` 的增益；三角不等式给出 `@@M@@t-1@@` 支。上界走完全相反的路线：先用 Kadets–Shvidkoy–Sirotkin–Werner 的切片刻画与 Bourgain 的"切片凸组合"引理，得到 Daugavet 性质等价于"单位向量的每个相对弱开邻域内都有几乎距离为 2 的点"；再对任意余维有限子空间 `@@M@@F@@` 取核为 `@@M@@F@@` 的有限秩投影 `@@M@@P@@`，在弱邻域 `@@M@@\{v:\|P(v-x)\|<\varepsilon\}@@` 中选出几乎直径点 `@@M@@v_\varepsilon@@`，其差在 `@@M@@F@@` 中的分量长度趋于 2，用凸组合恒等式把 `@@M@@\|x+t y_\varepsilon\|@@` 压到 `@@M@@1+(t-2)_+@@`，两条上界曲线一次得到。排除再赋范的论证最巧：设 `@@M@@N@@` 为等价 AUC 范数，取 `@@M@@N@@` 在球上的近似极大点 `@@M@@x_0@@`，AUC 性质给出子空间 `@@M@@F@@` 使大位移必带来 `@@M@@(1+\gamma)@@` 倍增益，而商坐标意义下 `@@M@@x_0@@` 的弱邻域内的点若想逃出增益区就必须与 `@@M@@x_0@@` 的 `@@M@@N@@`-距离很小，进而 `@@M@@\|\cdot\|@@`-距离小于 `@@M@@1/2@@`——与弱邻域内必有近直径点矛盾。最后的构造部分将 Kadets–Werner 的有限维扩张定量化：用均值 1、高度集中在 0 附近的重尾乘子 `@@M@@f=sV^{-1/p}@@` 乘旧单位向量生成新向量，借助常数 10、54、108 的尾概率与下界估计同时控制新球在测度度量下贴近旧球，用大数定律以平均恢复旧向量，再以可和误差 `@@M@@h_b=2^{-b}@@` 迭代取闭包，极限空间同时保有测度预紧性与 Daugavet 切片性质。

## 可信度与备注
论文声明其主结果已有 Lean 形式化证明，属结果族 331；姊妹篇（树位势模型与独立乘积模型）在同一框架下从三个不同角度印证"AMUC 不蕴含 AUC 可再赋范"，本文提供其中最精确的模曲线。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，可信度较高，但 Kadets–Werner 构造的定量常数等细节仍以论文原文与社区核验为准。

{% endraw %}
