---
layout: default
title: "A logarithmic independence bound for clique-free graphs"
family: "184"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A logarithmic independence bound for clique-free graphs

> 结果族 184：Correspondence coloring with a fixed forbidden subgraph　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文证明：对每个固定 \(r\ge 4\)，任何 \(n\) 个顶点、平均度 \(d\ge 2\) 的 \(K_r\)-free 图都含有大小至少 \(c_r\,n\log d/d\) 的独立集 (independent set)，从而解决了 Ajtai–Erdős–Komlós–Szemerédi 1981 年猜想（Erdős 问题 802），并去掉此前最佳界中残留的 \(\log\log d\) 损失。

## 问题背景

独立集是图中两两不相邻的顶点集合；一般图有平凡界 \(\alpha(G)\ge n/(d+1)\)，且不交团并表明它已最优，而排除固定团 (clique) 会迫使独立集变大。Ajtai–Komlós–Szemerédi 1980 年证明了无三角形情形的对数改进，Shearer 随后对无三角形图得到渐近系数 \(1\)。1981 年 Ajtai、Erdős、Komlós、Szemerédi 猜想：对每个固定被禁团 \(K_r\)，同阶的 \(\Omega_r(n\log d/d)\) 成立；他们自己只证得较弱的 \(\Omega_r(n\log\log d/d)\)，Shearer 1995 年改进为 \(\Omega_r(n\log d/(d\log\log d))\)。本文消去了最后的 \(\log\log d\) 分母；且 \(n\log d/d\) 这一阶即使对无三角形图也已最优（相差常数倍），故定理在阶的意义上是终结性的。

## 主要结果

定理：对每个整数 \(r\ge 4\) 存在常数 \(c_r>0\)，使每个 \(n\) 顶点、平均度 \(d\ge 2\) 的有限简单 \(K_r\)-free 图满足
\[\alpha(G)\ \ge\ c_r\,\frac{n\log d}{d},\]
常数对 \(n\) 与 \(d\) 一致，可取 \(c_r=1/(16D_r)\)。证明的核心——加权三角形定理——是关于交叉质量 (cross-mass) 条件的独立命题，不依赖任何团假设，可单独使用。

## 证明思路

证明分三个阶段。第一阶段选"好权重"：研究泛函 \(F_G(w)=\sum_v w_v(1-\log w_v)-M_G(w)\)，即熵减边质量（Davies 势函数的特例），其最大化子 (maximizer) 满足驻点方程 \(\log(1/w_v)=w(N(v))\) 与一个变分恒等式。再把 AEKS 的稀疏子图递归改造成均值一随机乘子 (mean-one random multipliers)：在 \(K_r\)-free 图上反复摘除重的开邻域（每块自动 \(K_{r-1}\)-free），随机保留一块并除以其选择概率，使期望边质量降至 \(\varepsilon s^2\)。在变分不等式中放大集合 \(S\) 的权重、清零集合 \(D\) 的权重会产生负交叉项，由此得到关键的交叉质量估计 \(e_w(S,D)\le 16r^2\,g_x(w(S))\)（当 \(w(S),w(D)\le e^x\)），且它在删边与不重复保留原边的顶点分裂下存活。

第二阶段证中心不等式 \(T_G(w)\le B_r M_G(w)\)：最大化子处的三角形质量受边质量控制。先删去公共邻域权重过小的边，丢失的三角形记入边质量账；再在每个顶点 \(u\) 的邻域内运行带停留的加权随机游走。熵平滑引理表明 \(\lceil x\rceil\) 步内游走行分布相对权重的平均熵 (entropy) 仅 \(O_C(\log x)\)，故存在增量极小的步，经相对熵 (relative entropy) 到总变差距离 (total variation distance) 的换算推出：在有序三角形分布下，三角形另两顶点出发的行分布平均距离 \(O(\sqrt{\log x/x})\)。联合采样这些分布为 \(u\) 的关联边分组，用逆向转移概率的截断控制组内权重，按组分裂 (vertex splitting) 顶点后，最大邻域权重从 \(e^x\) 降至 \(e^{\sqrt{x}}\)，损失跨迭代可求和；邻域权重最终有界时，三角形质量直接被边质量控制。

第三阶段选独立集：最大度 \(\le\Delta\) 时以常数测试权重 \(p=\log\Delta/\Delta\) 得极值 \(F_G^*\ge\) 常数倍 \(n(\log\Delta)^2/\Delta\)；按权重比例随机选点、删其闭邻域，平均代价恰把邻居之间的边按三角形记账，故存在代价 \(\le D_r\log\Delta\) 的顶点，归纳给出 \(\alpha(G)\ge n\log\Delta/(4D_r\Delta)\)，且 \(\Delta\) 在归纳中保持不变。最后删去原图中度 \(>2d\) 的顶点（总数不足一半），以 \(\Delta=2d\) 代入即得定理。

## 可信度与备注

本篇主结果已在 Lean 中形式化验证，是结果族 184 的基石；姊妹篇（对应染色）显式沿用其乘子与熵-分裂方法，并在染色场景下自证全部所需引理，两文由此互相印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题，族内尚未形式化的染色篇仍待社区核验。定理为存在性结果，不涉及算法效率与最优首项常数。

{% endraw %}
