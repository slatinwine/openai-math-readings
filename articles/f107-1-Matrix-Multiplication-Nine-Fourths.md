---
layout: default
title: "An Upper Bound of 9/4 for the Matrix Multiplication Exponent"
family: "107"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An Upper Bound of 9/4 for the Matrix Multiplication Exponent

> 结果族 107：Matrix multiplication with exponent at most 9/4　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论
本文证明复数域上矩阵乘法指数满足 \(\omega\le 9/4=2.25\)：对任意 \(\varepsilon>0\)，两个 \(n\times n\) 复矩阵只需 \(O_\varepsilon(n^{9/4+\varepsilon})\) 次算术运算即可相乘。这比此前 2.371177 的世界纪录下降逾 0.12，而且完全绕开了统治该领域三十余年的 Coppersmith–Winograd 框架，是路线级的突破。

## 问题背景
两个 \(n\times n\) 矩阵相乘，朴素算法需 \(n^3\) 次乘法；矩阵乘法指数 \(\omega\) 是使 \(O(n^{\tau+\varepsilon})\) 次算术运算可行的最小 \(\tau\)，它同时决定行列式、矩阵求逆等基本线性代数运算的复杂度。Strassen 于 1969 年用 \(2\times2\) 矩阵的七次乘法算法证明 \(\omega\le\log_2 7\approx2.81\)；此后 Bini 的近似—精确转换、Schönhage 的渐近和不等式与 Strassen 的激光方法确立了张量框架，Coppersmith 与 Winograd 在 1990 年结合 CW 张量与无等差数列集合把纪录推进到 2.375477。近十余年，Stothers、Vassilevska Williams、Le Gall、Alman–Vassilevska Williams、Duan–Wu–Zhou 等在同一框架内层层精化，Dupont 等人于 2026 年用大规模优化得到 2.371177。这条路线的改进已趋饱和，且被怀疑存在内在壁垒。本文彻底更换赛道：回到 Strassen 的渐近谱理论，转而分析多项式乘法张量，一举把指数压到 2.25。

## 主要结果
主定理：对每个 \(\varepsilon>0\)，两个 \(n\times n\) 复矩阵可用 \(O_\varepsilon(n^{9/4+\varepsilon})\) 次标量算术运算相乘；特别地 \(\omega\le 9/4\)。作者说明这是渐近算术复杂度意义下的结果，证明不指定有竞争力的有限矩阵规模；另由秩分解方程组具有有理系数及 Nullstellensatz，算法系数可取在 \(\overline{\mathbb Q}\) 的一个数域中。

## 证明思路
证明的主轴是把指数问题转化为对一族数值不变量的一致估计。张量视为三线性型（trilinear form），其三组变量称为腿；限制（restriction）在每条腿上独立做线性代换，张量秩 \(\mathrm R(A)\) 是满足 \(m\ge A\) 的最小整数。记精确秩指数 \(\nu=\inf_n\log_n\mathrm R(T_n)\)。Strassen 渐近谱理论中的张量特征（tensor character）\(\lambda\) 是在直和下可加、张量积下可乘、限制下单调且 \(\lambda(1)=1\) 的数值泛函。关键的探测引理（detecting characters，附录用有限维分离、紧性与 Schauder–Tychonoff 不动点定理证明）指出：只要 \(k<d^\nu\)，就存在特征使 \(\lambda(T_d)\ge k\)。于是只需证明每个特征都满足 \(\lambda(T_d)\le d^{9/4}\)。

先看特征的取值如何参数化。对点积张量 \(B_X(m)\)，乘法性论证给出幂律 \(\lambda(B_X(m))=m^{p_X}\)；三个取向的点积之积同构于 \(T_m\)，故 \(\lambda(T_m)=m^{3t}\)，其中 \(t=(p_X+p_Y+p_Z)/3>0\)。目标于是等价于证明 \(t\le 3/4\)。

核心是分离引理。设张量由 \(M\) 个块求和而成，各块共享 \(X\) 腿，而 \(Y\)、\(Z\) 扇区两两配对且互不相交。取 \(L=5M\) 份拷贝，以 \(L\) 次单位根做 Fourier 线性代换，使存活项满足 \(u-v+2(g-h)=0\)；再给变量赋权 \(g^2\)、\(hu-h^2\)、\(-hv\)，则存活项的总权恰为 \((g-h)^2\ge0\)。退化取权零部分后只有 \(g=h\) 的正确标签存活，得到完整直和 \(\bigoplus_h(A_h\otimes B_X(M))\)——每块还附带一个 \(M\) 维点积。配合固定频率计数与 Stirling 公式，得熵不等式 \(\lambda(T)\ge e^{p_XH(q)}\prod_i\lambda(T_i)^{q_i}\)。这里难点在于"共享变量的块无法直接直和"，Fourier 投影与平方失配权重的组合恰好把共享腿撕开，而输出块数在指数尺度上补偿了拷贝代价。

接着把熵不等式用于多项式乘法张量 \(C(a,b)=\sum x_iy_jz_{i+j}\)，其秩恰为 \(a+b-1\)。对六种腿置换取几何平均定义对称化轮廓 \(P(a,b)\)，则 \(P(1,b)=b\)、\(P(a,b)\le(a+b-1)^{1/t}\)。再添两条组合性质：其一用基于一次 Clebsch–Gordan 正合列的行列式滤波（determinant filtration）构造退化，得离散凹性 \(2P(a,b)\ge P(a,b+1)+P(a,b-1)\)；其二把指标区间切成左中右三扇区、对中间扇区赋 \(\pm1\) 权，得平移三倍式 \(P(a,3h+a-1)\ge3P(a,h)\)。

最后是纯离散推理：凹性使相邻增量不增，三倍式迫使归一化对角增量 \(H_a\ge\prod_{m<a}(1+1/3m)\)，再用初等不等式 \((1+1/3m)^3\ge1+1/m\) 放大得 \(P(a,a)\ge a^{4/3}\)。与上界比较并令 \(a\to\infty\) 得 \(t\le3/4\)，于是每个特征满足 \(\lambda(T_d)\le d^{9/4}\)；由探测引理即 \(\nu\le9/4\)。收尾的算术转换是标准的：固定一个维数 \(u\) 的精确秩分解做递归，即得 \(O_\varepsilon(n^{9/4+\varepsilon})\) 算法。

## 可信度与备注
论文宣称的主结果已有 Lean 形式化证明，可信等级最高。它是结果族 107 的旗舰篇：姊妹篇"低于 2.258 的复矩阵乘法与矩形界"给出特征零域上的 \(\omega<2.258\)、\(\alpha>0.465\) 及矩形界并做正特征转移，另一篇"错峰抽取"在所有固定域上给出 \(\omega<2.371055\)；三者的共同主题都是"以辅助代价换取共享变量的分离"。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主定理已形式化，可放心引用，但证明为存在性论证，未给出可实现的算法常数。

{% endraw %}
