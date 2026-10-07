---
layout: default
title: "An atomic certificate for triangular-lattice universal optimality"
family: "090"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An atomic certificate for triangular-lattice universal optimality

> 结果族 090：Triangular-lattice optimality, long-range Riesz and Coulomb energies, and spherical logarithmic energy　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：在所有中心圆盘密度为一的平面局部有限点集中，单位密度三角格子对一切"平方距离的非负完全单调函数"型势能（含发散能量）最小化每粒子能量的下极限，从而在不设任何周期性、分离性或微扰假设的前提下，确立了三角格子在平面上的普适最优性（universal optimality）。

## 问题背景

普适最优性问：是否存在一个点组态，对一整族排斥相互作用同时最小化能量。Cohn 与 Kumar 2007 年提出欧氏普适最优性猜想，点名三角格、\(E_8\) 与 Leech 格；后两者已由 Cohn–Kumar–Miller–Radchenko–Viazovska 在 8 维与 24 维用模形式与 Fourier 插值解决。平面的经典结果——Rankin、Cassels、Ennola、Diananda 关于 Epstein zeta 函数的工作，以及 Montgomery 的 theta 定理——只在格子之间比较。真正的困难在于：与三角格竞争的组态可以毫无周期、含任意接近的点对、局部点数极不均匀；此前平面比较结果都对竞争者加了限制（限定周期类、固定环面、或仅允许对格子的小偏差位移）。本文给出无限制的完整比较。

## 主要结果

记 \(b=\sqrt3/2\)，\(A=b^{-1/2}\{m(1,0)+n(1/2,b)\}\) 为协体积一的三角格（triangular lattice）。设局部有限集 \(\mathcal C\) 满足中心圆盘密度（centered disk density）一：\(N_R/(\pi R^2)\to1\)，其中 \(N_R=\#(\mathcal C\cap B_R)\)。势函数取完全单调（completely monotone）的非负光滑函数：\((-1)^j g^{(j)}(t)\ge0\)。定义每粒子能量的下极限

\[E_g(\mathcal C)=\liminf_{R\to\infty}\frac1{N_R}\sum_{\substack{x,y\in\mathcal C\cap B_R\\x\ne y}}g(|x-y|^2).\]

定理断言：在扩张的非负实数中 \(E_g(\mathcal C)\ge\sum_{a\in A\setminus\{0\}}g(|a|^2)=E_g(A)\)，包括格子和发散的情形（例如 \(g(t)=t^{-p}\) 对一切 \(p>0\)）；定理确定最小值，但不分类取等组态。配套的解析定理（sharp Gaussian minorants）是：对每个 \(\alpha>0\) 存在实径向 Schwartz 函数 \(f_\alpha\)，满足 \(f_\alpha\le k_\alpha=e^{-\pi\alpha|x|^2}\)、\(\widehat f_\alpha\ge0\)，且 \(f_\alpha\) 在 \(A\setminus\{0\}\) 上与 \(k_\alpha\) 处处相等、\(\widehat f_\alpha\) 在对偶格（dual lattice）\(A^*\setminus\{0\}\) 上为零——每个高斯核各有一张达到最优的 Fourier 证书；在 \(\alpha\ge1\) 时构造由两个 \(20\times20\) 有限插值块加一个绝对可和的无穷修正组成。

## 证明思路

能量归约只用到中心密度。对有限点集 \(\mathcal C_R\) 用 Fourier 反演得恒等式 \(\sum_{x,y}f_\alpha(x-y)=\int\widehat f_\alpha(\xi)|M_R(\xi)|^2\,d\xi\)，其中 \(M_R\) 是指数和；再用圆盘的光滑截断与 Plancherel 定理证明"低频质量引理"：\(\liminf_R\frac1{N_R}\int_{|\xi|\le\varepsilon}|M_R|^2\,d\xi\ge1\)。结合 \(\widehat f_\alpha\ge0\) 与连续性，去掉 \(N_R\) 个对角项后得到下界 \(\widehat f_\alpha(0)-f_\alpha(0)\)；Poisson 求和（Poisson summation）与两组接触条件把这个差精确等于三角格的高斯格点和。参数 \(0<\alpha<1\) 经对偶式 \(f_\alpha=k_\alpha-\alpha^{-1}\widehat f_{1/\alpha}\) 归结到 \(\alpha\ge1\) 的构造。最后用 Bernstein–Widder 定理把 \(g\) 表示为高斯核的正 Laplace 混合（允许零点处的原子与无穷总质量），沿任意半径序列以 Fatou 引理转移，于是势在零点的奇性与无穷能量都被容纳。

证书构造在标度坐标 \(s=b|x|^2\) 中进行：插值节点取模 \(36\) 的剩余类集（覆盖格子的全部平方半径坐标），正弦平方乘积 \(P(s)\) 在每个节点有二阶零点，配上双极与单极因子即可独立规定各节点的值与导数。前十个正节点用阻尼三角列——阻尼前是三角多项式，谱测度（spectral measure）是有限个原子，"原子证书"之名由此而来；其余节点用有理单极列，其谱测度绝对连续且全变差一致有界。两侧输入函数与其 Fourier 变换组合成 Fourier 对 \((F_1,F_2)\)。有限部分每侧 20 个未知坐标，取和差分离成两个 20 阶块；再把高斯参数数据装进一个多面体，用向外交大的区间算术（interval arithmetic）与 Bernstein 系数在整个多面体上验证全部不等式，全程不用网格。无穷部分对有限列表与 \(\ell^1\) 尾空间之间的算子建立一致界，经 Schur 消元与 Neumann 级数在尾空间精确解出所有插值方程（修正量约为 \(10^{-5}\) 与 \(10^{-9}\) 量级）。最后证整体符号：节点附近先减去值与线性项再除以位移平方，有限多项式检验、修正界与高斯凸性比较控制前七个半胞（第一个右半胞另需三次 Bernstein 论证），远处由正负号固定的正弦乘积项主导全部剩余曲率，得 \(J_1\le G_z\)、\(J_2\ge0\) 于整条半直线，归一化后即得 \(f_\alpha\)。

## 可信度与备注

本文主结果暂无形式化证明；计算部分由附录给出精确求值方案，并附整数区间算术检验器（`verification/check_certificate.py`），明确不使用浮点、网格与数值求积。姊妹篇《Universal optimality of the triangular lattice》以模 \(12\) 节点、每块 \(168\) 个坐标的独立插值构造证明同一能量结论：两文的辅助函数定理并不相同，而能量推论一致，互为佐证；本篇的有限系统更小。同族的平面圆堆积证书一文提供了被本文改编的高斯基数函数与 Bernstein 符号认证框架。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
