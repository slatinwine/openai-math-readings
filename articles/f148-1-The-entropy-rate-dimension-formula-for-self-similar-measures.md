---
layout: default
title: "The entropy-rate dimension formula for self-similar measures on the line"
family: "148"
discipline: "Dynamical systems and ergodic theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The entropy-rate dimension formula for self-similar measures on the line

> 结果族 148：The entropy-rate dimension formula for self-similar measures　·　学科：Dynamical systems and ergodic theory　·　验证状态：主结果已 Lean 形式化

## 一句话结论

在完全不设分离条件的前提下，证明了直线上任何自相似测度的 Hausdorff 维数都等于 `@@M@@\min\{1,h_{\mathrm{RW}}/\chi\}@@`：随机游走熵率除以 Lyapunov 指数，精确重叠、不等压缩比与负压缩比统统允许，彻底解决熵率维度猜想。

## 问题背景

取有限个压缩相似（contracting similarity）`@@M@@\varphi_i(x)=r_i x+t_i@@`（`@@M@@0<|r_i|<1@@`）与正权重 `@@M@@p_i@@`，独立随机复合后取极限，便得到自相似测度（self-similar measure）`@@M@@\mu@@`。Moran 与 Hutchinson 的经典理论在开集条件（open set condition）下给出维数公式；一旦去掉分离假设，问题立刻变得极其微妙：Erdős 证明 Pisot 参数的 Bernoulli 卷积（Bernoulli convolution）奇异，Solomyak 证明几乎处处绝对连续，Hochman 的熵增长逆定理表明维数亏损必迫使圆柱映射超指数集中。此后 Varjú、Rapaport、Feng–Feng、Bárány–Verma 等在超越参数、代数压缩比、有理平移等种种算术或分离条件下逐步推进；而 Varjú 综述中的熵率维度猜想（Conjecture 3）断言：不用任何分离与算术假设，维数也应由映射随机游走的熵率给出。更棘手的是，Baker 与 Bárány–Käenmäki 构造了没有精确重叠、不同圆柱却以任意超指数速度互相逼近的系统，这意味着证明必须能在毫无定量分离下界时处理"极近而不重合"的映射。

## 主要结果

主定理：对任意有限指标化映射族 `@@M@@\varphi_i(x)=r_i x+t_i@@`（压缩比可不等、可为负、不同指标可给出同一映射）及任意严格正概率向量 `@@M@@p@@`，记 `@@M@@G_n=\varphi_{I_1}\circ\cdots\circ\varphi_{I_n}@@` 为随机复合的完整仿射映射，其熵率（entropy rate）`@@M@@h_{\mathrm{RW}}=\lim_{n\to\infty}H(G_n)/n@@`，Lyapunov 指数 `@@M@@\chi=-\sum_i p_i\log|r_i|@@`，则

`@@M@@D\dim_{\mathrm H}\mu_{\Phi,p}=\min\left\{1,\frac{h_{\mathrm{RW}}(\Phi,p)}{\chi(\Phi,p)}\right\}.@@`

关键在于熵按"映射"而非"地址"计数：精确重叠（exact overlap，不同字定义同一完整仿射映射）被显式允许。由 Feng–Hu 的精确维性（exact dimensionality）定理，上式常数同时是测度的几乎处处局部维数。同文推论包括：无精确重叠时回到经典公式 `@@M@@\min\{1,H(p)/\chi\}@@`；吸引子维数 `@@M@@\dim_{\mathrm H}K_\Phi=\min\{1,s_*\}@@`（`@@M@@s_*@@` 为相似维数）；以及齐次三映射族 `@@M@@x\mapsto\lambda x,\ \lambda x+1,\ \lambda x+t@@` 的维数公式。定理只断言维数，不断言绝对连续性。

## 证明思路

上界较直接：把编码符号按 `@@M@@n@@` 个一组分块，以 `@@M@@G_n@@` 支撑中互不相同的映射为新字母表，重组后的系统仍生成同一 `@@M@@\mu@@`，其单符号熵为 `@@M@@H(G_n)@@`、平均压缩深度为 `@@M@@n\chi@@`，再用大数定律与覆盖论证即得 `@@M@@d\le\min\{1,h/\chi\}@@`。下界用反证法：设 `@@M@@d<1@@` 且 `@@M@@d\chi<h@@`，分三步导出矛盾。

第一步建立两件熵机制。其一为有限律估计：有限律 `@@M@@\nu@@` 的精确熵超出其尺度 `@@M@@\rho@@` 网格熵的部分，是"藏在格子里"的信息；引理断言这些信息必然体现为更细尺度上可观的公平两点律（fair pair，等权二点分布）质量，且常数与支撑点间最小距离无关。证明采用随机化嵌套分割，把切割线随机扰动后取平均，使贴近边界的原子不被反复计费——这正是无需定量分离的原因。其二为一致非饱和（uniform nonsaturation）：若 `@@M@@d<1@@`，则每个一比特尺度窗口都有一致正的熵亏 `@@M@@\delta>0@@`，否则用停止时自相似性把近饱和传递到一切更细尺度，与维数压制的熵上界矛盾。

第二步做块型（block type）分解：把符号流按长度 `@@M@@b@@` 分块，条件于每块中各符号的出现计数。计数固定了该块的带符号压缩比；所有块的压缩确定后，平移量唯一决定完整复合映射。记录计数每块只耗 `@@M@@m\log(b+1)@@` 比特，故条件平移律仍保有至少 `@@M@@nh_b@@` 的映射熵，哪怕许多地址相撞。维数 `@@M@@d@@` 又压住其在尺度 `@@M@@\rho_n=2^{-\lceil An\rceil}@@` 的网格熵，两者之差给出埋在该尺度之下的信息量 `@@M@@\ge\varepsilon n@@`；固定类型还使和集（sumset）很小，代入有限律估计即得：在典型收缩事件上，某个有限深度带 `@@M@@[a_n,B_n]@@` 内积累了 `@@M@@\ge cn@@` 的公平对质量。

第三步处理深度带可任意延伸的困难：在前面的带端点已知后才逐段选取块长，使后面的带严格排在前面带之下。在每个目标深度 `@@M@@L@@` 观测窗口熵 `@@M@@g_j@@`；由 `@@M@@\Delta_v@@` 的凸性与"对未观测未来类型取平均恰还原 `@@M@@\mu@@` 的缩放拷贝"，每个公平对经两点增益（two-point gain）引理产生至少 `@@M@@\delta/2@@` 的窗口熵增益。而同一深度下保留的窗口互不相交，增益沿望远镜求和被 `@@M@@2\log M@@` 一致封顶。对 `@@M@@L=1,\dots,T@@` 求和，每个带都贡献与 `@@M@@T@@` 成正比的下界，最终得到 `@@M@@2T\log M\ge\delta c qT/(4D)@@`；右端随带数 `@@M@@q@@` 无限增长，矛盾。

## 可信度与备注

本文主结果已有 Lean 形式化证明，是结果族 148 的定理核心篇；无重叠测度公式、吸引子公式与三映射特例均作为同文推论由主定理直接导出，彼此支撑。论文明确声明不断言绝对连续、有效分离或定量收敛速率，深度带上端 `@@M@@B_n@@` 也无有效界。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇核心结论已过形式化核验，在家族中可信度最高。

{% endraw %}
