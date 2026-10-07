---
layout: default
title: "A density-uniform condensate bound for dilute Bose gases"
family: "267"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A density-uniform condensate bound for dilute Bose gases

> 结果族 267：Positive-temperature Bose–Einstein condensation and exact quantum depletion　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对三维中任一固定的有界、径向、有限力程非负势 \(v\)，论文证明稀薄玻色气体正则吉布斯态的常数轨道凝聚分数（condensate fraction）有统一正常数下界 \(c_*(v)\)：它对所有足够小的密度及一切 \(0\le T\le\rho^2\) 的温度一致成立。这是在固定势、固定密度的热力学极限框架下，对整段稀薄区间一致的正温凝聚结果。

## 问题背景

玻色–爱因斯坦凝聚（Bose–Einstein condensation）指平衡态中某个单体轨道宏观地占据有限比例的粒子；Penrose 与 Onsager（1956）把它严格化为单体密度矩阵（one-particle density matrix）出现宏观本征值。对有相互作用的气体，已有严格占据结果大多在 Gross–Pitaevskii 标度下（Lieb–Seiringer 2002 及 Deuchert–Seiringer 2020 的正温推广），相互作用随粒子数缩放；或者采取稀薄与体积联合变化的极限（Fournais 2021、Chong–Liang–Nam 2026、Junge 2026 的 Neumann 盒）。Sütő 的热力学极限定理则要求势的 Fourier 变换非负——球形方势阱这类基本势就不满足——且凝聚阈值依赖温度。另一方面，能量理论（Dyson、Lieb–Yngvason、Fournais–Solovej、Basti 等）只确定能量渐近，无法决定单体轨道占据，因为单体动能隙随体积增大趋于零。固定势、固定正密度下的正则系综（canonical ensemble）凝聚因此长期缺失。

## 主要结果

设 \(v\ge 0\) 有界、可测、径向、有限力程且不几乎处处为零。在体积 \(V=L^3\) 的环面 \(\Lambda_L\) 上取哈密顿量 \(H_{N,L}=-\sum_i\Delta_i+\sum_{i<j}v_L(x_i-x_j)\)（作用于对称波函数），温度 \(T>0\) 的态为正则吉布斯态 \(\Gamma_{N,L,T}=e^{-H_{N,L}/T}/\Tr e^{-H_{N,L}/T}\)，\(T=0\) 时取基态；\(u_0=V^{-1/2}\) 为常数轨道（constant orbital）。主定理：存在 \(\rho_*(v),c_*(v)>0\)，使得对每个 \(0<\rho<\rho_*(v)\) 有 \(L_0(\rho,v)\)，凡 \(L\ge L_0\)、\(\rho/2\le N/L^3\le 2\rho\)、\(0\le T\le\rho^2\)，就有

\[\frac{\langle u_0,\gamma^{(1)}_{N,L,T}u_0\rangle}{N}\ge c_*(v).\]

要点有三：势不随 \(N\) 缩放；密度与温度先固定、再让体积增大；体积阈值可以依赖密度，但凝聚下界 \(c_*(v)\) 不依赖——这正是"密度一致"（density-uniform）的含义。

## 证明思路

整个证明是一场正路径测度的比较。Feynman–Kac 公式（Feynman–Kac formula）把配分函数写成闭路径集合上的正权重；把其中一条路径的一个配对端点换成独立积分的空间点，便得到总质量恰为凝聚分数 \(q_0\) 的正测度 \(\mu\)。证明分两步：先构造一个测度 \(\nu\)——只在长度 \(\delta=s^2\) 的短时间板块（slab）内改动路径，\(s\asymp\rho^{-1/2}\) 为胞边长——并证其质量至少为某固定正常数；再证密度 \(f=\dd\nu/\dd\mu\) 的二阶矩一致有界，Cauchy–Schwarz 立即给出 \(q_0\ge c_*(v)\)。密度一致性来自尺度配合：稀释时每胞平均粒子数 \(m\asymp\rho^{-1/2}\) 变大（可挑选的粒子增多），而板块长度相对 \(1/T\) 在整个正温区间内始终很短。局部上，先用能量与熵估计得到占据尾部，并在更短尺度 \(r=\zeta\rho^{-1/3}\) 上分离大多数端点；一个粒子"合格"要求端点分离、路径在首末短时段内贴住端点、且满足整体禁闭与相互作用积分分数（score）界。相互作用桥并不独立，作者另做一个局部化的配分函数比较来控制其联合轨迹失败率，代价与受检胞体积成比例，从而"指定胞集不可用"是小概率事件。远程连接靠随机格点骨架（skeleton）：两条独立骨架的相遇（encounter）数具有有界指数矩，遇到不可用胞簇则沿确定性规则绕行。在所得简单路径上每胞选一个合格粒子，循环重排其起点，打开一端并按精确归一的相互作用律重采样选中的桥，即得 \(\nu\)。二阶矩涉及两次独立的改路；若直接对原闭位形逐段估计，代价会与路径长度成正比而失控。绕过办法是引入"反向插入"（reverse insertion）提供基线，使远离相遇处的贡献精确抵消；只剩两个小量——两条分离桥相遇的相互作用代价 \(O(r^{-1/2})\)、两次选中同一粒子的概率 \(O(1/m)\)——都随 \(\rho\to0\) 消失。最棘手的是改路会改变哪些胞可用、哪些粒子合格，故两条路线不能视为与气体独立：作者用更严的胞测试、显式的路径列表以及全程保留的公共远端选择权重把这些约束钉死，最后对稀有连通分量取指数矩、对骨架用两个相遇矩求平均完成估计。收尾按"先固定只依赖 \(v\) 的截断、再缩小 \(\rho_*\)、最后取 \(L_0\)"的次序选定常数，得 \(c_*(v)=\upsilon^2/(4C_v)\)；正温一致的界再经热核的正性改进（positivity improving，保证唯一玻色基态）与 Gibbs 态向投影子的迹范数收敛过渡到 \(T=0\)。

## 可信度与备注

本文暂无形式化证明。它与族内姊妹篇《Ground-state condensation in the dilute hard-sphere gas》互相支撑：后者明确把本文第 8.1 节的显式骨架律与两个相遇矩引理（不含任何物理参数）作为其"唯一外部输入"，而本文则把这套比较机制用于软势的正温吉布斯态。按 OpenAI 官方声明，未经形式化的结果可能存在问题，读者宜以社区核验为准。

{% endraw %}
