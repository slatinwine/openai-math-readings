---
layout: default
title: "A Sharp Threshold Bound for Monotone Graph Properties"
family: "186"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Sharp Threshold Bound for Monotone Graph Properties

> 结果族 186：Uniform influence and sharp thresholds for graph and hypergraph properties　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Friedgut–Kalai 1996 年提出的尖阈值（sharp threshold）猜想：`@@M@@n@@` 个顶点的图上，任何在全体顶点置换下不变的非平凡单调性质，从概率 `@@M@@\varepsilon@@` 涨到 `@@M@@1-\varepsilon@@` 的边概率区间宽度至多 `@@M@@2^{19}\log(1/(2\varepsilon))/(\log n)^2@@`，分母中的平方为最优阶。

## 问题背景

把图看成 `@@M@@\{0,1\}^{E_n}@@` 中的点（`@@M@@E_n@@` 为完全图的边集），每条边以概率 `@@M@@p@@` 独立出现；图性质（graph property）是在每个顶点置换下不变的边集族，单调（monotone）指加边保持隶属。Friedgut 与 Kalai 在 1996 年利用 KKL 影响力不等式和 Margulis–Russo 概率导数公式证明：传递置换群下不变的单调图性质必有窄的过渡区间，宽度（threshold width）为 `@@M@@O(\log(1/(2\varepsilon))/\log n)@@`；他们同时猜想（原文 Conjecture 1.2）顶点置换群比"传递"丰富得多的结构应把分母改进为 `@@M@@(\log n)^2@@`，并指出此阶最优——包含大小与 `@@M@@\log n@@` 成比例的团（clique）这一性质，其过渡宽度就能达到 `@@M@@(\log n)^{-2}@@` 阶。此后 Bourgain–Kalai（1997）把宽度推进到 `@@M@@(\log n)^{-2+\eta}@@`（任意固定 `@@M@@\eta>0@@`）；Kelman–Kindler–Lifshitz–Minzer–Safra 又在 `@@M@@p=1/2@@` 处证明了 `@@M@@I_{1/2}(f)\ge c(\log n)^2\Var_{1/2}(f)/(\log\log n)^2@@` 的影响力下界。卡点：阈值宽度需要方差–影响力不等式在整个过渡区间上对一切 `@@M@@0<p<1@@` 一致，而已有结果或只在无偏测度处有效，或残留 `@@M@@\eta@@`、重对数损失。

## 主要结果

记 `@@M@@\mu_p(\mathcal P)@@` 为随机图属于 `@@M@@\mathcal P@@` 的概率，`@@M@@p_a(\mathcal P)=\inf\{p:\mu_p(\mathcal P)\ge a\}@@`；文中对数均以顶点数 `@@M@@n@@` 为尺度。

**定理 1（Friedgut–Kalai 猜想）**：对每个 `@@M@@n\ge2@@`、每个在全体顶点置换下不变的非平凡增图族 `@@M@@\mathcal P@@` 及每个 `@@M@@0<\varepsilon<1/2@@`，

`@@M@@Dp_{1-\varepsilon}(\mathcal P)-p_\varepsilon(\mathcal P)\le\frac{2^{19}}{(\log n)^2}\log\frac1{2\varepsilon}.@@`

其驱动引擎是**定理 2（方差与影响力）**：对每个 `@@M@@n\ge2@@`、每个在顶点置换下不变的布尔函数 `@@M@@f@@` 与每个 `@@M@@0<p<1@@`（同样不需要单调），

`@@M@@D\Var_p(f)\le\frac{2^{17}}{(\log n)^2}I_p(f),@@`

其中 `@@M@@I_p(f)=\sum_e\Pr_p(f(x_{e\leftarrow1})\ne f(x_{e\leftarrow0}))@@` 为总枢轴影响力（total pivotal influence）。文中还由中位数 `@@M@@p_*=p_{1/2}@@` 出发给出过渡曲线的双侧估计：`@@M@@\mu(p_*-s)@@` 与 `@@M@@1-\mu(p_*+s)@@` 都不超过 `@@M@@1/(1+\exp(s(\log n)^2/C_0))@@`。

## 证明思路

证明分四步：偏倚傅里叶分析、低阶引理、随机顶点块限制、积分得宽度。

先在偏倚乘积测度上建立傅里叶展开（基 `@@M@@\chi_i=(x_i-p)/\sigma@@`，`@@M@@\sigma=\sqrt{p(1-p)}@@`），得到两条恒等式：方差是全部非空系数的平方和；加权 Dirichlet 型恒等式 `@@M@@\sum_S|S|\hat f(S)^2=\sigma^2I_p(f)@@` 把高傅里叶度（degree）的质量用总影响力封顶。于是全部困难集中在低阶部分。

第二步证明低阶引理：当每个坐标的影响力都不超过总影响的 `@@M@@1/m@@` 时，对噪声算子 `@@M@@T_\rho@@`（`@@M@@\rho=\sigma/4@@`）建立二到四范数不等式 `@@M@@\|T_\rho g\|_4\le\|g\|_2@@`——这是 KKL 与 Bonami 超收缩性（hypercontractivity）论证的核心，文中对偏倚情形给出自足的显式证明——经对偶得 `@@M@@\|P_{\le k}g\|_2\le\rho^{-k}\|g\|_{4/3}@@`，作用到离散导数上并分情况讨论，得 `@@M@@\sum_{1\le|S|\le k}\hat h(S)^2\le m^{-1/4}I(h)@@`，`@@M@@k=\sigma\log m/64@@`。右端关于 `@@M@@I(h)@@` 线性，这一线性使后续平均合法。

第三步是全文最有创意的顶点块限制（restriction）：均匀随机取约 `@@M@@\sqrt n@@` 个顶点的块 `@@M@@B@@`，把与 `@@M@@B@@` 相交的边全部留作自由坐标，其余边赋值固定。由于 `@@M@@B@@` 内部的置换逐条固定外部边，任何赋值下限制函数仍享有块内完全对称；自由边的轨道（`@@M@@B@@` 内部的边，以及从 `@@M@@B@@` 连向每个固定外点的"星"）大小都至少为 `@@M@@m@@`，故个体影响 `@@M@@\le I(f_y)/m@@`，低阶引理对每个限制都适用。因估计对 `@@M@@I@@` 线性，可先对外部赋值平均（限制恒等式为精确恒等式），再对 `@@M@@B@@` 平均，得块估计，右端含因子 `@@M@@2m/n@@`。

第四步捕捉（capture）：把傅里叶指标 `@@M@@S@@` 看成 `@@M@@s@@` 条边的图。只要 `@@M@@s\le k^2/2@@`，它就有非孤立点 `@@M@@u@@`，度数至多 `@@M@@\sqrt{2s}\le k@@`；以不小于 `@@M@@m/(2n)@@` 的概率，`@@M@@B@@` 恰好只在 `@@M@@u@@` 接触该图，存活的自由支撑边恰为过 `@@M@@u@@` 的 `@@M@@1@@` 到 `@@M@@k@@` 条（不必恰为一条）。与块估计相除、`@@M@@m/n@@` 相消，就把"条件度不超过 `@@M@@k@@`"升级为"原始度不超过 `@@M@@k^2/2@@`"的控制——度数的平方化正是 `@@M@@(\log n)^2@@` 中平方的来源。更高阶的尾部由 Dirichlet 恒等式压成 `@@M@@2\sigma^2I_p(f)/k^2@@`；因 `@@M@@k@@` 正比于 `@@M@@\sigma\log m@@`，`@@M@@\sigma^2@@` 精确相消，界对一切 `@@M@@p@@` 一致，小 `@@M@@n@@` 平凡处理。最后由 Russo–Margulis 公式 `@@M@@\mu'(p)=I_p(f)@@` 得微分不等式 `@@M@@\mu'\ge(\log n)^2\mu(1-\mu)/C_0@@`，积分对数几率即得定理 1（取 `@@M@@4C_0=2^{19}@@`）。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准。姊妹篇《A uniform influence bound for hypergraph properties》原样复用本文的傅里叶估计与块限制论证，并推广到 `@@M@@r\ge3@@` 的一致超图（指数变为 `@@M@@r/(r-1)@@`），两篇共用同一方法骨架、互为印证；族内另有两篇处理阈值位置的比较（积分与分数覆盖的比较、图包含阈值与期望子图计数的比较），本文证明不依赖它们。按 OpenAI 官方声明，未经形式化的结果可能有问题，采信前请留意同行核验进展。

{% endraw %}
