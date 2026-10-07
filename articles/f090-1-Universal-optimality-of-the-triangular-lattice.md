---
layout: default
title: "Universal optimality of the triangular lattice"
family: "090"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Universal optimality of the triangular lattice

> 结果族 090：Triangular-lattice optimality, long-range Riesz and Coulomb energies, and spherical logarithmic energy　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明三角格子在中心密度为一的一切平面局部有限组态中，对全部非负完全单调势（含发散能量）普适最小化能量下极限，并进一步推出：对 \(0\le s<2\) 的对数与 Riesz 势，三角格最小化重整化能量与 jellium 热力学能量，兑现了 Petrache–Serfaty"普适最优性蕴含结晶化"的路线图。

## 问题背景

Cohn–Kumar 2007 年的欧氏普适最优性（universal optimality）猜想在 8 维、24 维已被模形式方法解决，平面情形悬置：竞争组态可以非周期、含任意接近的点对、局部点数极不均匀，经典格子结果（Rankin–Cassels 的 Epstein zeta 极小化、Montgomery 的 theta 定理）无法触及。另一层困难是长程势：当 \(0<s<2\)，原始 Riesz 能量即使在三角格子上也发散，逐点求和没有区分力，必须引入中性化均匀背景的 jellium（凝胶）模型与重整化能量（renormalized energy）。Petrache–Serfaty 2020 证明了"普适最优性 \(\Rightarrow\) Coulomb/Riesz 结晶化"的一般蕴含，但其前提——平面普适最优性本身——恰是缺口。本文同时补上这两级台阶。

## 主要结果

主定理：对每个光滑非负完全单调（completely monotone）的 \(g\)（即 \((-1)^r g^{(r)}\ge0\)）与每个中心圆盘密度一（\(N_R/(\pi R^2)\to1\)）的局部有限 \(\mathcal C\subset\mathbb R^2\)，

\[E_g(\mathcal C)=\liminf_{R\to\infty}\frac1{N_R}\sum_{\substack{x,y\in\mathcal C\cap B_R\\x\ne y}}g(|x-y|^2)\ \ge\ \sum_{a\in A\setminus\{0\}}g(|a|^2)=E_g(A),\]

在扩张非负实数中成立：允许 \(g\) 在零点奇异（如 \(t^{-p}\)，一切 \(p>0\)）、允许无穷能量，且对 \(\mathcal C\) 不设分离性或局部占据数界。中间结果是归一化高斯 Fourier 对定理：对每个 \(k\ge2.36\) 存在整函数 \(H_1,H_2\)，使 \(f=e^{-\pi hb|x|^2}H_1(b|x|^2)\) 与其同形式的 Fourier 变换构成径向 Schwartz 对，满足 \(H_1\le T_k=k^{-1}e^{-k(s-1)}\)、\(H_2\ge0\)，并在每个正节点 \(n\in\mathcal N\) 处同时规定值与一阶导数；\(\mathcal N\) 是由剩余类 \(\{0,1,3,4,7,9\}\) 生成的模 \(12\) 周期集，严格包含全部三角壳（例如 \(24\in\mathcal N\) 却不是格子壳值）。推论（重整化与 jellium）：对 \(0\le s<2\)（\(s=0\) 为 \(-\log|x|\)，\(0<s<2\) 为 \(|x|^{-s}\)），三角格 \(A\) 的 \(n^2\) 个陪集在环面 \(\mathbb R^2/(nA)\) 上最小化周期能量；\(A\) 最小化无穷系统场能量 \(W_s\)；有序对 jellium 热力学最小值 \(e_{\mathrm{Jel}}^{(s)}=\kappa_s^{-1}W_s(A)\)，其中 \(\kappa_0=2\pi\)、\(\kappa_s=4\pi\)。

## 证明思路

构造分三阶段。第一阶段做插值机制：在壳坐标 \(s=b|x|^2\)（\(b=\sqrt3/2\)）下，正弦平方乘积 \(P(s)\)（系数显式给出）在节点集 \(\mathcal N\) 上有二阶零点；基数函数 \(p_a(s)=P(s)\bigl(C+\sum_n(c_n/(s-n)^2+d_n/(s-n))\bigr)\) 可写成紧支谱测度（spectral measure）的 Fourier 型积分，折叠测度的全变差被系数的 \(\ell^1\) 范数线性控制，故任意可和列表都给出整函数。乘以高斯阻尼 \(e^{-\pi hs}\)（\(h=2/5\)）得径向 Schwartz 函数，其 Fourier 变换可在测度内逐项变换，得到带更强高斯衰减的第二核；尾部估计表明远处节点的输出射流（jet）按 \(e^{-0.7n}\)、\(e^{-0.187n}\) 一致衰减。两个基数函数与其变换耦合为 \(H_1=p_1+K_{p_2}\)、\(H_2=p_2+K_{p_1}\)，插值问题化为两个可和列表的线性方程组。第二阶段用正求积构造有限参考列表并认证矩阵与多项式不等式；因全耦合算子的界过大、直接小扰动不可行，改为求逆有限块、Schur 消元后在尾空间用 Neumann 级数，精确解出全部方程并给出对参考列表的误差界。第三阶段证符号：在节点处减去值与线性项再除以位移平方，避免小误差被消失的平方放大；Bernstein 基系数在完整半胞区间上界定多项式，参数数据用矩形界覆盖整个参数区间；无界尾部上正弦乘积的二次下界对抗其余项的小二阶导数。

能量转移沿用密度版线性规划（linear programming，Cohn–de Courcy–Ireland）：把点测度与稍大圆盘的面积测度放进正半定双线性型，用 Cauchy–Schwarz，交叉项误差对点的聚集一致；Poisson 求和使下界恰为格子高斯和。混合一步不用无移位表示（奇势可能没有有限表示测度），而是对移位 \(g(\varepsilon+t)\) 建立 Hausdorff–Bernstein–Widder 有限矩表示（差分非负性、Bernstein 基与测度紧性），核 \(v^t\) 恰是高斯；经 Fatou 与 Tonelli 定理沿任意序列转移，再用单调收敛去掉移位。重整化推论走 Petrache–Serfaty 的场论路线：跨周期格的热核（heat kernel）比较引理把两个周期组态的能量差写成 \(\int_0^\infty(H_{\mathcal C}-H_{\mathcal D})t^{-s/2}\,dt\)，而 \(H_{\mathcal C}(t)\) 正是高斯能量乘 \((4\pi t)^{-1}\)，于是主定理的高斯不等式逐点给出 \(H_{\mathcal C}\ge H_A\)，积分即得三角最小性；无穷系统下确界由方周期逼近封闭，jellium 数值由 Lewin–Lieb–Seiringer 与 Lauritsen 的热力学恒等式以及加权强极值原理（把粒子限制回背景方格）确定。

## 可信度与备注

本文主结果暂无形式化证明。姊妹篇《An atomic certificate for triangular-lattice universal optimality》用模 \(36\) 节点的原子插值独立证明同一主定理（两文互不引用对方为前提）；同族还有平面圆堆积证书一文提供方法框架、以及 \(s=0\) 的独立直接对数结果，多线互证。计算部分由附录的区间验证器支撑，其中一份有理数验证程序的结论以检验通过为条件。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
