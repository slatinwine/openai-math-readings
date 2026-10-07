---
layout: default
title: "A continuum temperature singularity for a radial pair potential"
family: "228"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A continuum temperature singularity for a radial pair potential

> 结果族 228：Continuum phase transitions for radial pair potentials　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

在三维空间构造出一个稳定的径向二体势，其正则自由能在同一临界逆温度处发生严格向下的导数跳跃，且该奇性在一整个正密度开区间上同时成立——Simon 连续介质相变存在性问题在纯二体径向势类中获得肯定回答。

## 问题背景

相变可表述为热力学自由能（thermodynamic free energy）失去正则性。格点气体（如 Ising 模型）的相变早已严格证明，但连续空间 `@@M@@\R^3@@` 中的经典粒子若仅通过稳定的径向二体势（radial pair potential）相互作用，能否在固定密度处出现温度奇异性，是 Simon 1984 年数学物理问题清单中的著名难题。此前的严格结果各有妥协：Ruelle 的 Widom–Rowlinson 模型需要两种粒子，Israel 的凸构造带硬核，Lebowitz–Mazel–Presutti 的液气相变依赖四体排斥项，近年的 Kac 型与饱和相互作用结果则依赖固定盒子分割或多体能量。卡点在于：纯二体径向吸引容易把自由能"磨平"，要在同一密度坐标上保住两个不同的温度斜率极为困难。

## 主要结果

论文构造了容许（admissible）的径向二体势 `@@M@@\Phi(x)=\phi(|x|)@@`：`@@M@@\phi(r)\to+\infty@@`（`@@M@@r\downarrow 0@@`，发散排斥核）、在某区间 `@@M@@[r_1,r_2]@@` 上 `@@M@@\phi\le -a@@`（非平凡吸引）、尾部 `@@M@@\phi(r)=o(r^{-3})@@` 且 `@@M@@\int_R^\infty r^2|\phi|\,dr<\infty@@`，并满足稳定性 `@@M@@U_N^\Phi\ge -BN@@`。主定理断言：存在密度开区间 `@@M@@I\subset(0,\infty)@@` 与同一个 `@@M@@\beta_c\in(1/2,3/2)@@`，使自由边界条件下的正则自由能 `@@M@@f_\Phi(\beta,\rho)@@` 对一切 `@@M@@\beta>0@@`、`@@M@@\rho>0@@` 存在且有限，且对每个 `@@M@@\rho\in I@@` 都有 `@@M@@D_\beta^- f_\Phi(\beta_c,\rho)>D_\beta^+ f_\Phi(\beta_c,\rho)@@`：一个势、一个临界温度、整段密度区间上的严格向下导数跳跃。论文明确说明这是"工程化"构造，不涉及 Lennard–Jones 势，也不鉴别共存态的物理身份。

## 证明思路

证明分四步。第一步，造稳定的参考气体。核心想法是在高度 `@@M@@t^2@@` 的排斥核里开一条半径 `@@M@@e^{-t}@@` 的极窄"零能量壳"：粒子对落在壳内不付能量。几何上，`@@M@@\R^3@@` 中不可能有五个点两两距离都落在壳内（对四条差向量作 Gram 矩阵扰动论证），结合 Motzkin–Straus 极值图定理，小格内的壳图至多 `@@M@@3n^2/8@@` 条边，于是核能给出局域粒子数的二次下界——即 Ruelle 超稳定性（superstability）式控制。由此建立正则与巨正则热力学极限及其 Fenchel 对偶。

第二步，造三条竞争的压力分支。先让 `@@M@@t\to\infty@@`：裸核压力收敛到 `@@M@@\max(0,\,ph,\,4ph-9p)@@`，三支分别来自真空、单粒子与四面体四粒子团（`@@M@@p@@` 为单位间距堆积密度的极限）。再加质量 `@@M@@A=3/(2p)@@` 的理想长程吸引——它通过 Lebowitz–Penrose 型 Kac 极限在变分公式中贡献 `@@M@@+\beta Ad^2/2@@` 的二次密度项——极限压力变为三个仿射分支的最大值，其斜率 `@@M@@v_1=(0,0)@@`、`@@M@@v_2=(3p/4,p)@@`、`@@M@@v_3=(12p,4p)@@` 不共线，于 `@@M@@\lambda_*=(1,-3/4)@@` 处相遇，重心 `@@M@@g=(17p/4,\,5p/3)@@`。

第三步是全文枢纽：均匀逼近本身会把角磨圆，故必须在每一步新吸引质量的同一尺度上工作。利用对吸引范围一致的局部占据矩估计与尾部连续性，物理 Kac 逼近的误差可压到 `@@M@@a^2@@`，而新吸引质量为 `@@M@@a@@`；对压力做 `@@M@@a@@` 尺度的放缩分析，证明放缩后的变换收敛到 `@@M@@\max_{(s,d)\in K}(xs+yd+\beta_0d^2/2)@@`，其中正二次项严格禁止横跨三个密度组的混合支撑。由此得到"持久性引理"：存在邻近点，其子微分仍由三组分离斜率生成，并含公共斜率球 `@@M@@\overline B(g,\gamma)@@`。

第四步，合成一个势。关键是次序：先选定下一步质量 `@@M@@\sigma_{n+1}@@`，再选足够大的新范围 `@@M@@R_n@@` 去逼近当前理想压力。质量可和给出单一容许势 `@@M@@\Phi=\psi_t-t\sum_j\sigma_j w_{R_j}@@`；支撑点 `@@M@@\lambda_n@@` 收敛于 `@@M@@\lambda_c@@`，斜率球整体传递给物理压力 `@@M@@Q_\infty@@`。最后在斜率平面上取密度 `@@M@@\rho\approx 5p/3@@` 的水平切片：两个支撑向量 `@@M@@(g_1\pm\gamma/2,\rho)@@` 密度相同而温度斜率不同，由凹性，`@@M@@H_\infty(\cdot,\rho)@@` 在 `@@M@@\beta_c@@` 的左右导数之差至少 `@@M@@\gamma@@`；除以规范化因子即得自由能跳跃 `@@M@@t\gamma/\beta_c@@`。

## 可信度与备注

本篇主结果已 Lean 形式化。姊妹篇给出有界连续核版本，以定量范围估计把尾部推进到 `@@M@@|\phi(r)|\le Cr^{-3-1/32}@@`；两篇共享"窄壳四粒子团 + 三分支支撑斜率"框架，互相印证构造的稳健性。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已形式化，但构造针对的是显式可积尾类，论文本身也强调不宣称 Lennard–Jones 势有相变。

{% endraw %}
