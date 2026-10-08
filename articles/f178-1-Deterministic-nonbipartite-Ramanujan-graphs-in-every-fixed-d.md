---
layout: default
title: "Deterministic nonbipartite Ramanujan graphs in every fixed degree"
family: "178"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Deterministic nonbipartite Ramanujan graphs in every fixed degree

> 结果族 178：Deterministic nonbipartite Ramanujan graphs in every fixed degree　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

每张网络都有自己的"振动频率"（特征值）：非平凡频率越小，网络越均匀、信息扩散越快。Ramanujan 图是频率恰好压在理论天花板上的完美网络，此前人们只能在特定度数或"带误差"的条件下确定性地造它。这篇论文造出了全自动机床：你指定顶点数和度数，它直接打印一张精确达标的网。

**关键词卡片**

- d-正则图（d-regular graph）：每个顶点恰好连 d 条边，人人平等。
- 特征值（eigenvalue）：邻接矩阵的固有频率；非平凡频率小意味着扩张性好。
- Ramanujan 图（Ramanujan graph）：所有非平凡特征值都落在 `@@M@@\pm2\sqrt{d-1}@@` 内的 d-正则图。
- Alon–Boppana 界（Alon–Boppana bound）：顶点数变大时该区间无法再收紧，说明此界是最优天花板。
- 非二部（nonbipartite）：顶点不能分成"边全跨界"的两堆，双侧谱界因此更难控制。

**看个具体例子**

定理：对每个 d≥3 与充分大的偶数 n，算法在多项式时间内输出简单非二部 d-正则图，其一切非平凡特征值满足 `@@M@@-2\sqrt{d-1}<\lambda<2\sqrt{d-1}@@`。代入 d=3：全部非平凡频率严格落在 ±2.83 之间（下图蓝点），而平凡频率 3 独居界外。随机正则图本身早已以高概率近似达标——难的从来不是存在，而是把"扔骰子碰运气"换成一步步确定的工序，还要精确压线、不带一丝误差。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="124" y1="85" x2="124" y2="150" stroke="#2ca02c" stroke-width="2" stroke-dasharray="6,4"/>
<line x1="436" y1="85" x2="436" y2="150" stroke="#2ca02c" stroke-width="2" stroke-dasharray="6,4"/>
<line x1="60" y1="150" x2="500" y2="150" stroke="#555" stroke-width="2"/>
<line x1="60" y1="143" x2="60" y2="157" stroke="#555" stroke-width="2"/>
<line x1="115" y1="143" x2="115" y2="157" stroke="#555" stroke-width="2"/>
<line x1="170" y1="143" x2="170" y2="157" stroke="#555" stroke-width="2"/>
<line x1="225" y1="143" x2="225" y2="157" stroke="#555" stroke-width="2"/>
<line x1="280" y1="143" x2="280" y2="157" stroke="#555" stroke-width="2"/>
<line x1="335" y1="143" x2="335" y2="157" stroke="#555" stroke-width="2"/>
<line x1="390" y1="143" x2="390" y2="157" stroke="#555" stroke-width="2"/>
<line x1="445" y1="143" x2="445" y2="157" stroke="#555" stroke-width="2"/>
<line x1="500" y1="143" x2="500" y2="157" stroke="#555" stroke-width="2"/>
<circle cx="137" cy="150" r="6" fill="#1f77b4"/>
<circle cx="176" cy="150" r="6" fill="#1f77b4"/>
<circle cx="209" cy="150" r="6" fill="#1f77b4"/>
<circle cx="247" cy="150" r="6" fill="#1f77b4"/>
<circle cx="302" cy="150" r="6" fill="#1f77b4"/>
<circle cx="346" cy="150" r="6" fill="#1f77b4"/>
<circle cx="390" cy="150" r="6" fill="#1f77b4"/>
<circle cx="423" cy="150" r="6" fill="#1f77b4"/>
<circle cx="445" cy="150" r="7" fill="#333"/>
<text x="60" y="178" fill="#555" font-size="12" text-anchor="middle">-4</text>
<text x="115" y="178" fill="#555" font-size="12" text-anchor="middle">-3</text>
<text x="170" y="178" fill="#555" font-size="12" text-anchor="middle">-2</text>
<text x="225" y="178" fill="#555" font-size="12" text-anchor="middle">-1</text>
<text x="280" y="178" fill="#555" font-size="12" text-anchor="middle">0</text>
<text x="335" y="178" fill="#555" font-size="12" text-anchor="middle">1</text>
<text x="390" y="178" fill="#555" font-size="12" text-anchor="middle">2</text>
<text x="445" y="178" fill="#555" font-size="12" text-anchor="middle">3</text>
<text x="500" y="178" fill="#555" font-size="12" text-anchor="middle">4</text>
<text x="124" y="72" fill="#2ca02c" font-size="13" text-anchor="middle">-2√2 ≈ -2.83</text>
<text x="436" y="72" fill="#2ca02c" font-size="13" text-anchor="middle">+2√2 ≈ +2.83</text>
<text x="455" y="122" fill="#333" font-size="13">平凡值 d=3</text>
<text x="280" y="222" fill="#555" font-size="13" text-anchor="middle">d = 3 的 Ramanujan 图：非平凡特征值（蓝点）严格落在 ±2√2 内</text>
</svg>

</div>

**为什么值得关心**

这是首个同时做到精确谱界、指定偶数阶、非二部与确定性多项式时间的构造，扩张图的"按需生产"成为可能。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对每个固定度 `@@M@@d\ge 3@@`，本文在每个充分大的偶数阶 `@@M@@n@@` 上确定性构造简单、非二部（nonbipartite）的 `@@M@@d@@`-正则 Ramanujan 图：全部非平凡特征值严格落在 `@@M@@(-2\sqrt{d-1},\,2\sqrt{d-1})@@` 内，并以多项式位操作输出完整邻接表——首次把精确谱界、指定阶数与确定性同时实现。

## 问题背景

`@@M@@d@@`-正则图称为 Ramanujan 图，若其邻接矩阵（adjacency matrix）限制在常向量正交补 `@@M@@\mathbf1^\perp@@` 上的范数不超过 `@@M@@2\sqrt{d-1}@@`；这正是无穷 `@@M@@d@@`-正则树的谱半径，而 Alon–Boppana 界说明该阈值渐近最优，非平凡谱小意味着边分布接近均匀预测、扩张性好。1988 年 Lubotzky–Phillips–Sarnak 与 Margulis 的算术构造只在特定度数达到精确阈值，Morgenstern 推广到 `@@M@@q+1@@`；Bilu–Linial 的二提升（two-lift）路线经 Marcus–Spielman–Srivastava 的交错多项式（interlacing polynomials）方法解决了任意度数的二部情形，但对非二部简单图，确定性构造的最好结果长期停留在带正误差的 `@@M@@2\sqrt{d-1}+\varepsilon@@`（Mohanty–O'Donnell–Paredes 2020；Alon 2021）。去掉这个 `@@M@@\varepsilon@@`，必须在特征值到两条树边缘距离的精细尺度上控制谱，正是卡点所在。另一侧，Friedman 与 Bordenave 证明随机正则图近似 Ramanujan，Huang–McKenzie–Yau 的联合边缘普适性进一步给出精确 Ramanujan 事件概率趋于约 0.69——存在性早已无虞，缺的是确定性的精确构造。

## 主要结果

**定理 1.1**：对每个整数 `@@M@@d\ge 3@@`，存在常数 `@@M@@n_0(d)@@`、`@@M@@k_d@@` 与一个确定性算法，输入任意偶数 `@@M@@n\ge n_0(d)@@`，它以 `@@M@@O_d(n^{k_d})@@` 位操作输出一个简单 `@@M@@d@@`-正则图 `@@M@@G@@` 的邻接表，且 `@@M@@A_G|_{\mathbf1^\perp}@@` 的每个特征值 `@@M@@\lambda@@` 都满足 `@@M@@-2\sqrt{d-1}<\lambda<2\sqrt{d-1}@@`。由 `@@M@@d>2\sqrt{d-1}@@`（当 `@@M@@d\ge3@@`），该界自动排除多余的 `@@M@@\pm d@@` 特征值，故 `@@M@@G@@` 连通且非二部。**推论 1.2**：对任意充分大的目标规模 `@@M@@N@@`，算法给出满足全部上述性质的图，阶数落在 `@@M@@N@@` 与 `@@M@@N+1@@` 之间。注意：指数 `@@M@@k_d@@` 可以依赖 `@@M@@d@@`，论文不声称关于 `@@M@@n,d@@` 联合的多项式时间，也不提供局部邻接查询算法；"显式"专指输出整个邻接表。相对既有工作，这一构造首次同时做到：简单图（非多重图）、非二部（双侧谱界）、精确阈值（无 `@@M@@\varepsilon@@`）、指定偶数阶与确定性多项式时间。

## 证明思路

总体策略是把随机正则图谱分析中的局部树逼近改造成完全确定性的构造。先给每个顶点 `@@M@@d@@` 个可区分的半边（stub），逐步配对成边。全程对两个符号 `@@M@@\sigma=\pm1@@` 维护正定的 precision 矩阵（完工时即 `@@M@@zI-\sigma A_G@@`，`@@M@@z>s@@`，`@@M@@s=2\sqrt{d-1}@@`），其归一化逆与截断加权的非回溯路径（nonbacktracking path）之和逐项比较；对完工图，这条路径递推正对应正则图的 Ihara–Bass 束 `@@M@@I-\sigma hA_G+(d-1)h^2I@@`。每一步配对按"折算账本"（discounted accounts）规则选取加权统计量的最小化者——这是条件期望法与悲观估计子（pessimistic estimator）的确定性化，每个统计量带各自的折算因子，一次选择同时保住所有估计。

具体分四个阶段。先做早期配对，从空配对出发配掉绝大多数 stub：难点是在长序列选择中同时控制多项式多个条目，关键引理证明高阶矩的增长系数与矩阶无关，故取一个足够大的固定矩即可提取出最大值界。再在清理阶段把相互靠近或产生短返回的 stub 配掉，使剩余 `@@M@@l_0\asymp n^{2/3}@@` 个 stub 位于不同顶点、两两分离且无短非回溯返回。随后补全阶段以 Woodbury 恒等式对冻结的光滑路径参考做精确低秩逆更新：先压低行能量平方、再用变小的能量改进入口逐项界，这使最后几个 stub 可以任意匹配，最终得到非平凡谱落在 `@@M@@(-s-e/20,\,s+e/20)@@` 内的简单正则图，其中 `@@M@@e=n^{-2/3+a}@@`，`@@M@@a=10^{-4}@@`。

最后是精确修复定理——去掉残余误差的关键。它只需三个输入：谱约束（松弛量 `@@M@@x_i^\sigma=s-\sigma\lambda_i>-e/20@@`）、每点局部谱质量界 `@@M@@\sum_{x_i^\sigma\le w}|v_i(p)|^2\le Cw^{3/2}@@`，以及绝大多数边的 bulk 预解算子 `@@M@@R_B^\sigma@@` 的 `@@M@@2\times2@@` 端点块接近树块 `@@M@@\frac{1}{d-2}\begin{pmatrix}\sqrt{d-1}&\sigma\\ \sigma&\sqrt{d-1}\end{pmatrix}@@`。先用 Schur 补（即 Woodbury 恒等式加惯性论证）消去 bulk 模式，把正性化为近边缘模式上的二次型。此处有个关键观察：均匀随机换边的均值修正只会把每个松弛量乘以 `@@M@@1-o(1)@@`，救不了负松弛；于是对两条被选边的联合分布做倾斜（tilt），在最接近阈值的模式上注入远大于 `@@M@@e@@` 的正均值偏移，压过 `@@M@@-e/20@@` 的负松弛，其余近边缘模式仍保留固定比例的正余量。涨落与端点碰撞仅用二阶矩估计（成对独立即可）。确定性化时，先用 Bernstein 多项式作用于有理矩阵逼近倾斜律，再在素域 `@@M@@\mathbb F_P@@` 上用仿射构造生成成对独立样本、枚举全部 `@@M@@P^2@@` 个种子，对每个候选图以精确有理惯性检验 `@@M@@B^T(4qI-A_{G'}^2)B\succ0@@`（`@@M@@q=d-1@@`，`@@M@@B@@` 为 `@@M@@\mathbf1^\perp@@` 的有理基）；修复定理保证搜索中必有通过者。

## 可信度与备注

主结果尚无 Lean 形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。本结果族目前仅此一篇手稿，无姊妹篇互相印证；其外部支点是 MSS/HPS 的二部情形构造与 Huang–McKenzie–Yau 的存在性定理，而沿确定性配对历史的谱估计与双侧倾斜修复是本文新证。算法端全部为精确有理计算（Bareiss 分数无关消元、精确惯性判定），最终的谱检验原则上可被机器无条件复核，这是可信度的实质加分项。

{% endraw %}
