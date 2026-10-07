---
layout: default
title: "Bounded klt complements for Fano contractions"
family: "066"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Bounded klt complements for Fano contractions

> 结果族 066：Bounded klt complements for Fano contractions　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Shokurov 有界 klt 补 (bounded klt complement) 猜想的有限有理系数形式：维数 `@@M@@d@@` 与正有理数 `@@M@@\epsilon@@` 固定后，特征零代数闭域上任何 `@@M@@\epsilon@@`-lc 的 Fano 收缩在基底每个闭点附近都有指标只依赖 `@@M@@d,\epsilon@@` 的 klt 补，使伴随除子局部成为挠。

## 问题背景

Shokurov 在研究三维 log flip 时引入了补 (complement)：给 Fano 型空间找一个有效有理边界 (effective rational boundary) `@@M@@B@@`，使伴随除子 `@@M@@K_X+B@@` 在局部成为挠，即某正整数 `@@M@@N@@` 使 `@@M@@N(K_X+B)@@` 是 Cartier 且线性平凡，`@@M@@N@@` 称为指标 (index)。核心问题是指标能否只被维数与奇异性下界一致控制。lc 补 (log canonical complement) 允许某些处差异为零，Birkar 已证明其任意维有界性；klt 补则要求所有 log 差异 (log discrepancy) 严格为正，而直接缩小 lc 补的系数会破坏 `@@M@@K_X+B@@` 的线性平凡性，这正是此前卡住的地方。Chen 建立了有界 klt 补与一致局部超曲面阈值 (uniform local hypersurface threshold) 的等价，并解决了基底维数至多为 2 的情形；本文补上一般情形。

## 主要结果

主定理：对每个正整数 `@@M@@d@@` 与正有理数 `@@M@@\epsilon@@`，存在正整数 `@@M@@N=N(d,\epsilon)@@`，使得特征零代数闭域上任何收缩 `@@M@@f\colon X\to Z@@`（`@@M@@X@@` 正规 `@@M@@d@@` 维、`@@M@@K_X@@` 为 `@@M@@\mathbb Q@@`-Cartier、`@@M@@X@@` 为 `@@M@@\epsilon@@`-lc、`@@M@@-K_X@@` 在 `@@M@@Z@@` 上丰富，即 Fano 收缩）对每个闭点 `@@M@@z\in Z@@` 给出有效 `@@M@@\mathbb Q@@`-除子 `@@M@@B@@` 与邻域 `@@M@@U@@`，使 `@@M@@(X,B)@@` 在 `@@M@@f^{-1}(U)@@` 上 klt 且 `@@M@@N(K_X+B)|_{f^{-1}(U)}\sim 0@@`。定理不要求相对 Picard 数为 1，也不要求一般纤维正维数。推论（有限系数形式）：固定有限集 `@@M@@I\subset[0,1]\cap\mathbb Q@@`，对系数落在 `@@M@@I@@` 中的 `@@M@@\epsilon@@`-lc 对 `@@M@@(X,\Delta)@@`，若 `@@M@@X@@` 是 `@@M@@Z@@` 上的 Fano type 且 `@@M@@-(K_X+\Delta)@@` 相对 nef，则存在 `@@M@@\Delta^+\ge\Delta@@` 使 `@@M@@(X,\Delta^+)@@` 在 `@@M@@z@@` 附近 klt、`@@M@@M(K_X+\Delta^+)@@` Cartier 且线性平凡，`@@M@@M@@` 只依赖 `@@M@@d,\epsilon,I@@`。

## 证明思路

先做归约：由 Chen 的等价定理，只需证"双有理、零边界"的一致阈值命题——对 `@@M@@\epsilon@@`-lc、`@@M@@-K_X@@` 相对 nef 的双有理收缩，`@@M@@\lct(X;\mathfrak m_z\mathcal O_X)\ge c(d,\epsilon)@@`；域下降引理再把 `@@M@@\mathbb C@@` 上的结论搬到任意特征零代数闭域。

再反证：设有一列反例，先经相对基点自由定理取 crepant ample model，使 `@@M@@-K_X@@` 相对丰富且一切差异不变；阈值失败意味着存在 `@@M@@X@@` 上的素除子列 `@@M@@P@@` 使 `@@M@@P(\mathfrak m_z)/A_X(P)\to\infty@@`，即基理想在赋值意义上"集中"。同时 Birkar 的有界 lc 补定理给出固定的 `@@M@@n@@`，使 `@@M@@\frac1n|-nK_X|@@` 成为 lc 线性系统。

接着把反例编码进几何：将反典范截面打包为 `@@M@@p=d+1@@` 维仿射锥，其中有界次数 lc 系统里有一个中心化的 lc 处 (lc place) 检测上述集中。难点是要在 lc 等式约束下极小化正规化体积 (normalized volume)，而已知理论（Li 的固有性、Blum 的存在性、Xu 的拟单项性、Xu–Zhuang 的唯一性与稳定退化）只对无约束的 klt 对成立。本文的关键新器件是"精确罚函数"命题：约束极小值恰好等于某个小扰动有效 klt 对的普通极小值。有了这个精确性，就能照搬稳定退化得到有限生成分次环，同时在极小值处做一次比较，保住集中性 `@@M@@\tilde v(\mathfrak m_z)\to\infty@@`。

然后计数与优化交替进行：用相容滤过极大化记录赋值方向的环面秩，得到带弱本质性 (weak essentiality) 的对 `@@M@@(S,B+H)@@`——在其 lc 处把丰富除子 `@@M@@H@@` 换成任何有理等价的有效除子，阶至多放大 `@@M@@1+\eta@@` 倍（`@@M@@\eta\to0@@`）。把 `@@M@@m@@` 次反典范截面除以 `@@M@@h^{m/n}@@` 得有理函数空间 `@@M@@V_m@@`，配以代价 `@@M@@b(F)=m+v(F)@@`，并用差异恒等式 `@@M@@A_X(w)=A_{X,B_h}(w)+\sup\frac{-w(F)}m@@` 把截面信息译回 `@@M@@X@@` 的奇异性。宽度 `@@M@@W_j@@` 方向上，上界计数与独立截面的单项式下界互相挤压；宽度有界的方向则靠在标记族中保留有效除子代表元封死，否则会产生具有界正代价的零次截面，与集中性矛盾。

最后收网：在正特征约化上用 Takagi 的乘法理想与 test ideal 比较以及 Schwede 的 Cartier 代数得到迹生成 (trace generation)，经两次提升把迹生存性先拉回完整初始域、再拉回原域；与上界计数比较后即控制了坐标取值与值群分母，使所得赋值的有界倍数成为某素除子的整数倍，且该素除子的差异 `@@M@@<\epsilon@@`——与 `@@M@@X@@` 的 `@@M@@\epsilon@@`-lc 矛盾，反证完成。

## 可信度与备注

主结果暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。同族姊妹篇《Uniform Cartier sections for Fano type contractions》用独立的"特征与钉扎"论证证明双有理 klt 补定理，与本篇在 Chen 等价框架下互相印证、互为支撑。两篇均大量依赖 Birkar 的有界性定理、有界 lc 补定理及 normalized volume 理论等已发表结果，结论以这些文献的正确性为前提。

{% endraw %}
