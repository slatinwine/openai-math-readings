---
layout: default
title: "The critical correlation exponent of the planar XY model"
family: "216"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The critical correlation exponent of the planar XY model

> 结果族 216：Critical and near-critical XY scaling and BKT universality　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明方格最近邻 XY 模型在质量定义的临界逆温度处，无穷体积自旋相关 `@@M@@C_{b_c}(n)=n^{-1/4+o(1)}@@`，即 `@@M@@\log C_{b_c}(n)/\log n\to-1/4@@`，精确证实了 BKT 理论五十余年前预言的临界相关指数 `@@M@@1/4@@`。

## 问题背景

二维 XY 模型在低温下存在一个没有自发磁化的"临界相"：相关呈幂律衰减且指数随温度连续变化。Berezinskii 与 Kosterlitz–Thouless 的理论预言，在该相的边界（临界点）处衰减指数恰为 `@@M@@1/4@@`。此前严格结果勾勒了相图轮廓：McBryan–Spencer（1977）给出幂律上界；Fröhlich–Spencer（1981）用库仑气（Coulomb gas）分析证明低温代数相；van Engelenburg–Lis（vEL）用定向电流与对偶高度给出指数–多项式二分法，并在临界处给出非尖锐的下界 `@@M@@C_{b_c}(n)\ge 1/(8n)@@`；Lammers 证明了 XY 质量与对偶高度质量的精确关系及定位二分法。但端点系数与磁相关指数这两个"硬数字"一直未被识别——本文正是补上这一缺口。

## 主要结果

模型与 vEL 相同：自由边界方盒 `@@M@@\Lambda_L@@` 上的角度测度 `@@M@@\dd\mu_{L,b}\propto\exp\{b\sum_{\{x,y\}}\cos(\theta_x-\theta_y)\}\prod_x\dd\theta_x/(2\pi)@@`。相关函数 `@@M@@C_b(n)@@` 先取 `@@M@@L\to\infty@@`、再取间距 `@@M@@n\to\infty@@`（涵盖全部整数间距），质量 `@@M@@m(b)=\lim_n-\frac1n\log C_b(n)@@`，`@@M@@b_c=\inf\{b:m(b)=0\}@@`。主定理：`@@M@@\lim_{n\to\infty}\frac{\log C_{b_c}(n)}{\log n}=-\frac14@@`；等价地，对任意 `@@M@@\varepsilon>0@@`，当 `@@M@@n@@` 充分大时 `@@M@@n^{-1/4-\varepsilon}\le C_{b_c}(n)\le n^{-1/4+\varepsilon}@@`。论文明确说明不断言 `@@M@@n^{1/4}C_{b_c}(n)@@` 收敛——族内另一篇证明的对数修正 `@@M@@(\log n)^{1/8}@@` 与此完全相容。

## 证明思路

骨架是对偶高度场（dual height field）：XY 自旋相关经自由边界对偶变为取值 `@@M@@2\pi\Z@@` 的高度模型，边权是 Bessel 权重 `@@M@@p_b(j)=e^{-b}I_j(b)@@`。定义自由高度系数 `@@M@@a=a(b)@@`——高度协方差为 `@@M@@aA^{-1}@@`（`@@M@@A@@` 为单位边拉普拉斯）。常数可沿一条短恒等式链读出：高度周期为 `@@M@@2\pi@@`，径向单位流的能量 `@@M@@(2\pi)^{-1}\log r+O(1)@@`，对各傅里叶扇区求和得到间隙 `@@M@@a\in\{0\}\cup[8\pi,\infty)@@`；而一对相反角奇点的能量为 `@@M@@4\pi\log n+O(1)@@`，由此得自旋上界指数 `@@M@@-2\pi/a@@`（`@@M@@a=0@@` 时衰减快于任何多项式）。证明分五步推进：先构造 `@@M@@a(b)@@` 并证间隙与上界指数；再证定位所需的混合边界与条件钉扎极限；然后证 `@@M@@a>0@@` 时匹配的下界指数，此时自旋质量为零；接着证开性（openness）——`@@M@@a(b)>8\pi@@` 蕴含其邻域内系数处处为正。最后组合（第 60 节）：若 `@@M@@a(b_c)=0@@`，上界给出 `@@M@@\limsup\log C_{b_c}/\log n=-\infty@@`，与 vEL 下界（`@@M@@\liminf\ge-1@@`）矛盾；若 `@@M@@a(b_c)>8\pi@@`，开性使某 `@@M@@\tilde b<b_c@@` 处 `@@M@@a(\tilde b)>0@@`，进而 `@@M@@m(\tilde b)=0@@`，与 `@@M@@b_c@@` 的定义矛盾。于是 `@@M@@a(b_c)=8\pi@@`，指数 `@@M@@2\pi/8\pi=1/4@@`。整个过程不假设未知函数 `@@M@@a(b)@@` 的连续性。相对伴侣篇（本批"BKT universality"一文，处理二次权重）还需要三项模型特异性转移：其一，用格点高斯链细分把有限比较搬到 Bessel 权重，但细分链的裸高斯方差界不转移，改用单位边流代价与任意高阶多项式矩替代（包括电缆探索与小钉扎概率之后）；其二，普通高度观测的收敛不能决定绕数扇区的配分比，改在几何环上做有限孤立展开（finite isolation expansion），每个环尺度只引入小误差；其三，在"平均值"而非微观高度上加一个正的二次形式，为开高斯区域提供大场储备，最后用方差比较把该形式移除，结论回到原始模型。

## 可信度与备注

本篇主结果暂无形式化证明；按 OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。家族内互相支撑：本篇把 vEL 的外部端点输入（非尖锐下界 `@@M@@1/(8n)@@`）当作唯一外来临界信息，工具箱（记号 \Bcite 引用的有限高斯比较、环形几何、局部解析映射）由本批"BKT universality for height and planar spin fields"一文供给；本篇证出的临界高度系数 `@@M@@8\pi@@` 又是族内"本质奇性"一文所依赖的临界输入。三篇在 `@@M@@8\pi@@` 这一普适常数上彼此印证。

{% endraw %}
