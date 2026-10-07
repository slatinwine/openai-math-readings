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

证明了 Friedgut–Kalai 1996 年提出的尖阈值（sharp threshold）猜想：\(n\) 个顶点的图上，任何在全体顶点置换下不变的非平凡单调性质，从概率 \(\varepsilon\) 涨到 \(1-\varepsilon\) 的边概率区间宽度至多 \(2^{19}\log(1/(2\varepsilon))/(\log n)^2\)，分母中的平方为最优阶。

## 问题背景

把图看成 \(\{0,1\}^{E_n}\) 中的点（\(E_n\) 为完全图的边集），每条边以概率 \(p\) 独立出现；图性质（graph property）是在每个顶点置换下不变的边集族，单调（monotone）指加边保持隶属。Friedgut 与 Kalai 在 1996 年利用 KKL 影响力不等式和 Margulis–Russo 概率导数公式证明：传递置换群下不变的单调图性质必有窄的过渡区间，宽度（threshold width）为 \(O(\log(1/(2\varepsilon))/\log n)\)；他们同时猜想（原文 Conjecture 1.2）顶点置换群比"传递"丰富得多的结构应把分母改进为 \((\log n)^2\)，并指出此阶最优——包含大小与 \(\log n\) 成比例的团（clique）这一性质，其过渡宽度就能达到 \((\log n)^{-2}\) 阶。此后 Bourgain–Kalai（1997）把宽度推进到 \((\log n)^{-2+\eta}\)（任意固定 \(\eta>0\)）；Kelman–Kindler–Lifshitz–Minzer–Safra 又在 \(p=1/2\) 处证明了 \(I_{1/2}(f)\ge c(\log n)^2\Var_{1/2}(f)/(\log\log n)^2\) 的影响力下界。卡点：阈值宽度需要方差–影响力不等式在整个过渡区间上对一切 \(0<p<1\) 一致，而已有结果或只在无偏测度处有效，或残留 \(\eta\)、重对数损失。

## 主要结果

记 \(\mu_p(\mathcal P)\) 为随机图属于 \(\mathcal P\) 的概率，\(p_a(\mathcal P)=\inf\{p:\mu_p(\mathcal P)\ge a\}\)；文中对数均以顶点数 \(n\) 为尺度。

**定理 1（Friedgut–Kalai 猜想）**：对每个 \(n\ge2\)、每个在全体顶点置换下不变的非平凡增图族 \(\mathcal P\) 及每个 \(0<\varepsilon<1/2\)，

\[p_{1-\varepsilon}(\mathcal P)-p_\varepsilon(\mathcal P)\le\frac{2^{19}}{(\log n)^2}\log\frac1{2\varepsilon}.\]

其驱动引擎是**定理 2（方差与影响力）**：对每个 \(n\ge2\)、每个在顶点置换下不变的布尔函数 \(f\) 与每个 \(0<p<1\)（同样不需要单调），

\[\Var_p(f)\le\frac{2^{17}}{(\log n)^2}I_p(f),\]

其中 \(I_p(f)=\sum_e\Pr_p(f(x_{e\leftarrow1})\ne f(x_{e\leftarrow0}))\) 为总枢轴影响力（total pivotal influence）。文中还由中位数 \(p_*=p_{1/2}\) 出发给出过渡曲线的双侧估计：\(\mu(p_*-s)\) 与 \(1-\mu(p_*+s)\) 都不超过 \(1/(1+\exp(s(\log n)^2/C_0))\)。

## 证明思路

证明分四步：偏倚傅里叶分析、低阶引理、随机顶点块限制、积分得宽度。

先在偏倚乘积测度上建立傅里叶展开（基 \(\chi_i=(x_i-p)/\sigma\)，\(\sigma=\sqrt{p(1-p)}\)），得到两条恒等式：方差是全部非空系数的平方和；加权 Dirichlet 型恒等式 \(\sum_S|S|\hat f(S)^2=\sigma^2I_p(f)\) 把高傅里叶度（degree）的质量用总影响力封顶。于是全部困难集中在低阶部分。

第二步证明低阶引理：当每个坐标的影响力都不超过总影响的 \(1/m\) 时，对噪声算子 \(T_\rho\)（\(\rho=\sigma/4\)）建立二到四范数不等式 \(\|T_\rho g\|_4\le\|g\|_2\)——这是 KKL 与 Bonami 超收缩性（hypercontractivity）论证的核心，文中对偏倚情形给出自足的显式证明——经对偶得 \(\|P_{\le k}g\|_2\le\rho^{-k}\|g\|_{4/3}\)，作用到离散导数上并分情况讨论，得 \(\sum_{1\le|S|\le k}\hat h(S)^2\le m^{-1/4}I(h)\)，\(k=\sigma\log m/64\)。右端关于 \(I(h)\) 线性，这一线性使后续平均合法。

第三步是全文最有创意的顶点块限制（restriction）：均匀随机取约 \(\sqrt n\) 个顶点的块 \(B\)，把与 \(B\) 相交的边全部留作自由坐标，其余边赋值固定。由于 \(B\) 内部的置换逐条固定外部边，任何赋值下限制函数仍享有块内完全对称；自由边的轨道（\(B\) 内部的边，以及从 \(B\) 连向每个固定外点的"星"）大小都至少为 \(m\)，故个体影响 \(\le I(f_y)/m\)，低阶引理对每个限制都适用。因估计对 \(I\) 线性，可先对外部赋值平均（限制恒等式为精确恒等式），再对 \(B\) 平均，得块估计，右端含因子 \(2m/n\)。

第四步捕捉（capture）：把傅里叶指标 \(S\) 看成 \(s\) 条边的图。只要 \(s\le k^2/2\)，它就有非孤立点 \(u\)，度数至多 \(\sqrt{2s}\le k\)；以不小于 \(m/(2n)\) 的概率，\(B\) 恰好只在 \(u\) 接触该图，存活的自由支撑边恰为过 \(u\) 的 \(1\) 到 \(k\) 条（不必恰为一条）。与块估计相除、\(m/n\) 相消，就把"条件度不超过 \(k\)"升级为"原始度不超过 \(k^2/2\)"的控制——度数的平方化正是 \((\log n)^2\) 中平方的来源。更高阶的尾部由 Dirichlet 恒等式压成 \(2\sigma^2I_p(f)/k^2\)；因 \(k\) 正比于 \(\sigma\log m\)，\(\sigma^2\) 精确相消，界对一切 \(p\) 一致，小 \(n\) 平凡处理。最后由 Russo–Margulis 公式 \(\mu'(p)=I_p(f)\) 得微分不等式 \(\mu'\ge(\log n)^2\mu(1-\mu)/C_0\)，积分对数几率即得定理 1（取 \(4C_0=2^{19}\)）。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准。姊妹篇《A uniform influence bound for hypergraph properties》原样复用本文的傅里叶估计与块限制论证，并推广到 \(r\ge3\) 的一致超图（指数变为 \(r/(r-1)\)），两篇共用同一方法骨架、互为印证；族内另有两篇处理阈值位置的比较（积分与分数覆盖的比较、图包含阈值与期望子图计数的比较），本文证明不依赖它们。按 OpenAI 官方声明，未经形式化的结果可能有问题，采信前请留意同行核验进展。

{% endraw %}
