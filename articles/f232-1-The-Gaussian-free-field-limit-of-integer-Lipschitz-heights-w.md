---
layout: default
title: "The Gaussian free field limit of integer Lipschitz heights with two-arc boundary data"
family: "232"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Gaussian free field limit of integer Lipschitz heights with two-arc boundary data

> 结果族 232：Gaussian fields and interfaces for triangular-lattice Lipschitz heights　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了三角格点上边界两弧分别取 \(+1\) 与 \(-1\) 的均匀奇整数 Lipschitz 高度场，中心化后收敛到 Dirichlet 高斯自由场的普适倍数，归一化常数由绝对收敛的有限体积计数公式显式给出，从而解决 Schramm 问题 2.2 的场部分。

## 问题背景
Schramm 在 2006 年提出、2007 年发表的问题集之问题 2.2 问：光滑单连通域上、边界被两标记点分成两弧并分别赋值 \(+1\) 与 \(-1\) 的三角格点奇整数高度函数（相邻差为 \(0\) 或 \(2\)），其高度场与零等高线是否有高斯自由场与 SLE 型标度极限。此前 Glazman–Manolescu 为均匀整数 Lipschitz 模型建立了两自旋表示、正相联与回路尺度估计并证明对数涨落；Glazman–Lammers 随后在更大参数区间证明离域化（delocalization），并把 GFF 极限作为猜想讨论。困难在于：对数涨落只是方差层面的证据，不足以确定极限定律——还需在稀有钉扎条件下做比较、识别协方差常数、控制强加的两弧边界值并确定全部联合矩。光滑一致凸梯度势的已知场极限定理（Miller）不覆盖这种每条边都有硬约束的整数模型。

## 主要结果
主定理：设 \(D\) 为带两个不同标记边界点的有界光滑单连通平面区域，\(D_\delta\) 为标记边界参数化一致收敛的三角格点多边形逼近，\(h_\delta\) 服从两弧边界的奇高度均匀律。则存在只依赖单位三角格点模型的常数 \(\sigma>0\)，使得 \(h_\delta\Rightarrow\bar g+\sigma\Phi_D\) 在 \(\mathcal D'(D)\) 中成立，其中 \(\bar g\) 是边界数据 \(+1/-1\) 的有界调和延拓（bounded harmonic extension），\(\Phi_D\) 是协方差为 \(G_D=(-\Delta_D)^{-1}\) 的 Dirichlet 高斯自由场（Gaussian free field, GFF）；等价地，整数高度 \(H_\delta=(h_\delta-1)/2\) 收敛到 \(m+\sqrt v\,\Phi_D\)，且 \(\sigma^2=4v\)、\(v=(2\pi)^2c_*\)、\(\sigma=4\pi\sqrt{c_*}\)。任意有限组检验函数的联合矩收敛。归一化由绝对收敛的有限体积级数给出：\(c_*=\frac1\pi\sum_j\bigl[b_{j0}+\sum_s(b_{j,s+1}-b_{js})\bigr]>0\)，其中 \(b_{js}\) 是指定光滑截断的 Fourier 系数乘以有限六角区域内双自旋构形对的均匀计数平均，全为有限整数计数之比，与区域无关。

## 证明思路
证明的主轴是识别子列极限 \(H\) 的全部矩。第一步由反射正性（reflection positivity）提取谱信息：条件于一条格点行上的自旋值时，两侧构形独立且互为镜像，故 \(\E[\overline{\Theta F}F]\) 是半正定 Hermitian 型；两个反射的复合给出步长 \(\sqrt3\) 的法向平移，它在反射商完备化后是正自伴压缩算子。由此协方差可写成法向频率上 Cauchy 核的正混合。关键的谱和规则（spectral sum rule）在于：第四阶角调和函数在六次格点旋转下平均为零，而同一函数的 Cauchy 平均除一个可和格点误差外非负；两者相减得到非负可积的"色散缺陷"，迫使每个小频率谱极限的密度必为 \(c_*/|p|^2\)；带符号角向求和再唯一确定 \(c_*\)，并顺带导出上述有限体积归一化公式。同时，支撑在反射线一侧的 Laplace 检验与其镜像的协方差趋于零，得到"反射零化"恒等式。第二步移动稀有销钉（pin）：高度模 \(4\) 编码为两个 \(\pm1\) 自旋，边界销钉规定这些符号；由于典型插入点被边界销钉环绕而无法全部置于一条反射线之后，先在边界窗口开缺口、只钉住两个自旋之一，用分离钉扎事件的乘性比较控制反射范数，再借正转移算子的幂把平移在多个法向解析延拓（方法承袭六顶点模型的对应论证），让销钉移过插入点；承载规定符号的自旋回路随后闭合缺口，并迫使各不相连的钉扎弧取同一高度偏移。第三步恢复原始边界条件：附着估计从合成的均值比较推导出开水平线连接，停止规则保证未被检查区域的条件 Gibbs 律不变；在常值边界弧附近取参考平均，其在极限中收敛到规定值，恰好固定了局部高度差所遗留的加性常数。最后，矩函数在各变量远离碰撞点处调和、只有对数碰撞奇性；局部切割混合与平面协方差定出每个奇性系数，减去相应 Green 函数得到高斯矩递推（Wick 递推），而一致矩界同时提供紧性与从矩收敛到分布收敛的过渡。

## 可信度与备注
本结果暂无形式化证明；按 OpenAI 官方声明"未经形式化的结果可能有问题"，应以社区核验为准。族内姊妹篇互相支撑：本篇与零边界加权模型篇共用"反射正性—销钉移动—矩方法"骨架但各自独立成文、互不引用对方定理为前提；实值 Lipschitz 曲面篇则另辟路线解决 Schramm 问题 2.3。问题 2.2 的界面部分（零等高线的 SLE 收敛）不在本篇范围之内。

{% endraw %}
