---
layout: default
title: "The maximal triangular Hilbert transform at the symmetric point"
family: "082"
discipline: "Real and complex analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The maximal triangular Hilbert transform at the symmetric point

> 结果族 082：Annular variation and dyadic absolute bounds for the triangular Hilbert transform　·　学科：Real and complex analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了三角 Hilbert 变换的逐点极大算子满足 `@@M@@\|B_*(F,G)\|_{L^{3/2}}\le C\|F\|_3\|G\|_3@@`，上确界取遍两个硬截断端点且可逐点选取；由此得到联合几乎处处与 `@@M@@L^{3/2}@@` 主值收敛，并肯定地解决 Thiele 问题 13 的对称点情形。主结果已 Lean 形式化。

## 问题背景

三角 Hilbert 变换 `@@M@@B_{\varepsilon,R}(F,G)(x,y)=\int_{\varepsilon<|t|<R}F(x+t,y)G(x,y+t)\,\frac{\mathrm dt}{t}@@` 将两个输入沿两个坐标方向平移，是平坦平移（无曲率、无方向平均）情形下最缺少内蕴抵消机制的例子；与第三个输入配对得到的标量单纯形形式是纠缠奇异积分（entangled singular integral）的基本样本。对称点 `@@M@@L^3\times L^3\times L^3@@` 估计是 Thiele 问题 13。此前 Durcik–Kovač–Thiele（2019）的幂次型抵消经循环置换与插值只给出 `@@M@@\sqrt{\log(R/\varepsilon)}@@` 型、随尺度范围增长的界；带曲率或方向平均的变体依赖三角情形不具备的额外抵消。方法上的障碍同样古老：Kovač 的 Bellman 函数框架只适用于二部图，三角圈被明确列为障碍。

## 主要结果

主定理：存在绝对常数 `@@M@@C@@`，对一切复 `@@M@@F,G\in L^3(\mathbb R^2)@@`，
`@@M@@D\|B_*(F,G)\|_{L^{3/2}(\mathbb R^2)}\le C\|F\|_{L^3}\|G\|_{L^3},\qquad B_*=\sup_{0<\varepsilon<R<\infty}|B_{\varepsilon,R}(F,G)|,@@`
上确界同时取遍两个有限硬截断端点。这比"每个截断各自范数有界"强得多：同一个 `@@M@@L^{3/2}@@` 控制函数必须在每个点同时控制两端点的一切选取。由极大估计得联合主值 `@@M@@B(F,G)=\lim_{\varepsilon\downarrow0,R\uparrow\infty}B_{\varepsilon,R}(F,G)@@` 几乎处处且在 `@@M@@L^{3/2}@@` 中存在，且尾部极大振荡 `@@M@@\|\sup_{\varepsilon<1/n,\,R>n}|B_{\varepsilon,R}-B|\|_{3/2}\to0@@`。配对第三个 `@@M@@L^3@@` 输入得标量平形式（flat form）的端点一致界 `@@M@@\sup_{\varepsilon,R}|\mathcal L_{\varepsilon,R}|\le C_M\prod_v\|F_v\|_3@@`；经行列式为一的变量代换，单纯形形式（simplex form）`@@M@@\Lambda_{\varepsilon,R}@@` 有同样的界与联合标量主值，且两形式的最优常数相等——这肯定地解决了 Thiele 问题 13 的对称点情形。

## 证明思路

先经变量代换 `@@M@@x=-a,\ y=-b,\ t=a+b+c@@` 化到单纯形坐标，把两个输入与一个对偶输入采样到有限网格上；乘以高斯权后得到三个有限维矩阵 `@@M@@W_v:H_{v+1}\to H_v@@`，三个顶点空间对应采样的 `@@M@@a,b,c@@` 坐标，对偶数组的两个指标恰好记录输出位置。矩阵部分建立维数无关的混合迹不等式（mixed trace inequality），把循环迹 `@@M@@\tr(D_0W_0D_1W_1D_2W_2)@@` 控制为能量 `@@M@@\tr((R_v^*R_v)^{3/2})@@`（`@@M@@R_v=[\,W_v\ \ W_{v-1}^*\,]@@` 为行星）的 Hessian 二次代价。热流部分把三个能量沿中心满足 `@@M@@p_0+p_1+p_2=0@@` 的高斯中心平面积分，能量随方差增大的下降恰好控制估计带三个奇高斯窗的循环迹所需的全部代价。真正的新困难在逐点不同的截断：对偶数组的每个元素只在自己的两个尺度之间存在，于是能量在相邻开关尺度之间下降、在开关尺度处可能跳。关键估计控制跳跃绝对值之和：矩阵能量对元素的导数满足 `@@M@@|(R\sqrt{R^*R})_{ij}|\le\|\mathrm{row}_iR\|_2\|\mathrm{col}_jR\|_2@@`（该公式在秩改变时仍成立），高斯积分后行、列范数的乘积被一维 Hardy–Littlewood 极大函数沿切片控制，界与开关尺度的个数无关——"每个元素至多开关两次"是这里的杠杆。把跳跃与热流不等式沿尺度望远镜求和，即得允许任意输出相关掩模的耗散估计。最后，用有限菜单线性化光滑截断的有限极大值，经网格极限与有理端点穷举得光滑极大算子；其核与硬 Hilbert 核的逐点比较把估计过渡到紧支撑光滑输入的硬极大；再由密度与尾振荡消失论证推广到一切复 `@@M@@L^3@@` 输入，并建立联合主值与标量推论。

## 可信度与备注

主定理（含截断积分定义其上的公共满测集与极大输出的可测性）已 Lean 形式化（见合集 lean/docs/082.md 及 TriangularHilbert.lean）。族内另两篇为姊妹成果：dyadic 绝对界一文直接复用本文第二、三节的矩阵引理，环形变差一文把同一能量方法推进到全变差并重新导出本文的极大结论。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文中形式化覆盖的是极大估计本身，主值收敛与标量等价等推论仍属未经形式化部分。

{% endraw %}
