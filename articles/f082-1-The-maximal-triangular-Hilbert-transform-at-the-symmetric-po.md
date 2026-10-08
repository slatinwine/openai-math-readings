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

## 入门导读 🐣

体检量血压，不管护士几点来量、袖带松紧如何，读数都不该爆表。数学里的"极大算子"就是这样的极限压力测试：它要求同一个控制函数，在每个点上同时压住所有可能截断选择下的读数。这篇论文证明三角 Hilbert 变换通过了这项测试，而且主结果已被计算机（Lean）逐行验证。

**关键词卡片**

- 三角 Hilbert 变换（triangular Hilbert transform）：`@@M@@\int_{\varepsilon<|t|<R}F(x{+}t,y)G(x,y{+}t)\frac{dt}{t}@@`，两个输入沿两个坐标方向平移后纠缠
- 极大算子（maximal operator）：`@@M@@B_*=\sup_{0<\varepsilon<R}|B_{\varepsilon,R}|@@`，所有截断读数的上包络
- 硬截断（hard truncation）：两端 `@@M@@\varepsilon@@`、`@@M@@R@@` 都是生硬边界，上确界同时遍历两者且可逐点选取
- 对称点（symmetric point）：指标恰取 `@@M@@L^3\times L^3\to L^{3/2}@@` 的最平衡位置，正是 Thiele 问题 13 所问
- Lean 形式化（formalization）：用定理证明器机器核验的证明，可信度最高的一档

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<path d="M60,160 C140,80 240,190 320,130 C400,80 460,150 500,120" stroke="#9ab" stroke-width="1.8" fill="none" stroke-dasharray="7 4"/>
<path d="M60,175 C140,120 240,205 320,150 C400,110 460,160 500,132" stroke="#9ab" stroke-width="1.8" fill="none" stroke-dasharray="7 4"/>
<path d="M60,168 C140,98 240,198 320,138 C400,92 460,154 500,126" stroke="#c33" stroke-width="3" fill="none"/>
<text x="70" y="50" font-size="14" fill="#333">不同截断 (ε,R) 下的读数曲线</text>
<text x="70" y="72" font-size="13" fill="#777">虚线：各种截断；粗红线：极限主值</text>
<text x="70" y="240" font-size="14" fill="#333">上包络 B_* 在 L^{3/2} 中被一致控制，</text>
<text x="70" y="262" font-size="14" fill="#333">曲线随 ε→0、R→∞ 安稳收敛到主值</text>
</svg>

</div>

数字版定理：`@@M@@\|B_*(F,G)\|_{L^{3/2}(\mathbb R^2)}\le C\|F\|_3\|G\|_3@@`，对一切复 `@@M@@L^3@@` 输入成立。它远强于"每个固定截断各自有界"；由此立刻得到联合主值 `@@M@@B=\lim_{\varepsilon\downarrow0,R\uparrow\infty}B_{\varepsilon,R}@@` 几乎处处且在 `@@M@@L^{3/2}@@` 中存在，并解决 Thiele 问题 13 的对称点情形。

**为什么值得关心**

三角 Hilbert 变换是"平坦平移"情形下最缺内禀抵消机制的样本，此前三十年只算得出随尺度增长的界；本文把它压成一致常数。主定理（含截断积分与极大输出的可测性）已由 Lean 形式化，是同族三篇中率先通过机器验证者。

> 已 Lean 形式化

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
