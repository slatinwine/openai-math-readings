---
layout: default
title: "Path selection and an elliptic inequality on degenerating Ricci-flat trees"
family: "351"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Path selection and an elliptic inequality on degenerating Ricci-flat trees

> 结果族 351：Scalar curvature and finite-time Ricci-flow singularities　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对固定的四维 Ricci-flat（Ricci 平坦）空间有限树证明了顺序椭圆不等式：当连接长度全部发散、尺度中立的加权 Ricci 误差 \(M\to0\) 时，重正化 Einstein–Hilbert 泛函满足 \(E=o(M)\)。这一静态估计是姊妹篇四维 Ricci flow 延拓定理的支柱。

## 问题背景

Ricci-flat 度量可以经由多个悬殊的长度尺度退化：一个区域的渐近局部欧氏端（ALE end）套进另一个区域的 orbifold 点邻域，如此重复便得到有限的根树（rooted tree）。每个顶点区域上的度量可以光滑收敛，而尺度之比趋于零——有用的估计必须控制整个连接后的度量，包括顶点之间的颈部。四维闭 Ricci flow 若标量有界却在有限时刻集中曲率，其重标度极限正是这样的树（Bamler–Zhang 证明了此类 Ricci-flat ALE 极限）。本文研究与流动无关的静态问题：考察重正化 Einstein–Hilbert 泛函 \(E\)（标量曲率积分减去边界通量，与 Deruelle–Ozuch 的质量减除重正化同源）。直接的一阶变分估计只给 \(|E|\le CM\)；主定理把它严格改进为 \(E=o(M)\)，这正是延拓定理中"正变分压倒静态小性"所需的形态。相关前人还有 Haslhofer 的重正化 Perelman 泛函与 Biquard、Ozuch 的 Einstein 去奇异性化反演估计。

## 主要结果

**树不等式**：固定有限根树，顶点是四维 Ricci-flat 空间；每个端带笛卡尔商坐标，模去 \(O(4)\) 中自由作用于 \(S^3\) 的有限群，且连接端的群必须非平凡；根的外端要求衰减 \(h_v-\delta=O(r^{-q})\)，\(q>1\)。设序列 \((g_j,L^{(j)},M_j)\) 满足：所有连接长度 \(L_e^{(j)}\to\infty\)、紧集上收敛到顶点度量、直到 10 阶标度导数的加权 Ricci 误差 \(M_j\to0\)。则在根的物理单位下 \(E(g_j)=o(M_j)\)；当 \(M_j=0\) 时断言为 \(E=0\)。文中还证明了推导此估计所用的多变量路径选择定理（path selection）。

## 证明思路

整体是反证加"对数有限变差"的框架：若不等式失败，可抽出序列使 \(F\ne0\)、\(F\to0\) 且 \(F^2\ge c_0J\)，其中 \(F\) 是解析族上的泛函值、\(J\) 是族中带根尾权重的非负平方 Ricci 范数。

先构造解析族。在主部为分量纯量椭圆算子的规范（DeTurck–Kazdan 坐标法）下，建立带复长度参数的有限维解析族 \(h_*(L,z)\)：固定顶点上用有限个核测试分离线性化核，用有限个紧支源表现余核——不假设 Einstein 变形无障碍（obstruction 观点承自 Biquard 与 Ozuch）；连接边上，两个 Cauchy 匹配条件再加上临界球面通道的取值，由显式径向模态矩阵给出随长度发散仍一致的反演。与原序列比较得 \(\|g-h_*\|\le CM\)、\(|E(g)-E(h_*)|\le CM^2\)，这解释了为何依赖无穷多变量的原始度量可被有限维族替代。

再证变分估计：一阶变分加上后代区域物理体积的收缩，给出 \(|dF|\le C\sqrt J\left(\sum_\alpha|dz_\alpha|+\sum_e e^{-cL_e}|dL_e|\right)\)。

关键的解析难点在于长度变量 \(L\to\infty\) 不是普通解析坐标：换元 \(t=e^{-L}\) 未必保持解析性，各阶幂-对数渐近展开可以全部存在而不收敛成幂级数。作者的替代方案是"容许族"理论：函数在每个长度上都有 \(e^{-dL}\) 乘 \(L\) 的多项式系数展开（指数集局部有限、余项指数严格更优），所有递归提取的系数在公共的普通参数邻域上全纯。路径选择定理断言：沿满足有限个符号条件与规定极限的任何序列，存在实解析路径实现同样的条件，且每个长度坐标与有界普通坐标最终单调或取常值——这是曲线选择引理向多指数端情形的多变量推广，思想源自 Ilyashenko 拟解析代数（Speissegger 等）的"时钟"演算。

最后收官：沿这条路径有 \(|d\log|F||\le\frac{C}{\sqrt{c_0}}\left(\sum|dz|+\sum e^{-cL}|dL|\right)\)。单调且收敛的普通坐标有有限变差；而 \(\int e^{-cL(u)}|L'(u)|\,du=c^{-1}e^{-cL(u_0)}<\infty\)。于是 \(\log|F|\) 有有限总变差与有限极限，与 \(F\to0\) 强制 \(\log|F|\to-\infty\) 矛盾。至于展开如何在几何量之间传递：逐条边打开、解在开口端上带整数指数尾部、有限个入射模抵消接缝失配、三角化的线性辅助方程逐阶提取系数、有限部分积分把展开搬到 \(F\) 与 \(J\) 上；所有阶共用同一非线性分支与同一基本反演，从而普通参数的解析域在全部阶中保持一致。

## 可信度与备注

本文是纯静态结果，假设的陈述独立于任何流动；它以定理 2.2 的身份成为四维延拓论文的核心外部输入，两文合并构成本结果族证明的闭环。主结果暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
