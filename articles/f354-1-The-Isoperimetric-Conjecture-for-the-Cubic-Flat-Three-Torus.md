---
layout: default
title: "The Isoperimetric Conjecture for the Cubic Flat Three-Torus"
family: "354"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Isoperimetric Conjecture for the Cubic Flat Three-Torus

> 结果族 354：The isoperimetric profile of the cubic three-torus　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文完整证明了立方平坦三环面 \(\mathbb{R}^3/\mathbb{Z}^3\) 上的等周猜想：任何体积下最小周长区域必为球、绕最短闭测地线的圆管、坐标板或其补，并在两个转变体积 \(4\pi/81\) 与 \(1/\pi\) 处穷尽全部等号情形。

## 问题背景

等周问题（isoperimetric problem）问：固定体积的区域何时边界面积最小？欧氏空间里答案是球，但紧流形上的拓扑约束会让答案彻底改变。立方平坦三环面（cubic flat three-torus）\(\mathbb{R}^3/\mathbb{Z}^3\) 是最简单的紧平坦三维流形，其上的等周猜想预测了简洁的三段式答案——球、圆管、板——由 Hauswirth、Pérez、Romon 与 Ros 明确提出。此前已知若干片段：Morgan–Johnson 证明小体积时球最优，Acerbi–Fusco–Morini 证明半体积附近坐标板唯一；Milman 给出有效区间，并把猜想约化为只需在 \(V_1=4\pi/81\) 与 \(V_2=1/\pi\) 两个转变体积处排除"非标准"共同最小化子。本文正面解决了这一卡点。

## 主要结果

定理：设 \(V\in(0,1)\)，\(v=\min(V,1-V)\)。三环面上体积为 \(V\) 的有限周长（finite perimeter）子集的最小周长为
\[I_{\rm unit}(V)=\min\{(36\pi)^{1/3}v^{2/3},\ 2\sqrt{\pi v},\ 2\}.\]
当 \(0<V\le1/2\)，每个最小化区域在等距与零测集意义下恰为下列之一：\(0<V\le4\pi/81\) 时是半径 \((3V/(4\pi))^{1/3}\) 的球（ball）；\(4\pi/81\le V\le1/\pi\) 时是绕最短闭测地线、半径 \(\sqrt{V/\pi}\) 的实心圆管（solid circular tube）；\(1/\pi\le V\le1/2\) 时是两平行坐标环面之间宽度为 \(V\) 的板（slab）。相邻区间公共端点处两类同时取到，别无其他等号情形；\(V>1/2\) 时取补集。

## 证明思路

证明分约化、对称化、截面化、排除四步，在周期 2 环面上归一化。经典结构定理（HPRR）表明：非标准最小化边界必连通、亏格（genus）至少为 2，且曲率和 \(h\) 满足 \(h^2A\le\pi\)。标准竞争者给出包络 \(F\)；平行变分（parallel variation）的上支撑函数满足 \(C^2C''=-h^2C+\pi(1-g)\)，与各分支的 \(F''+(F')^2/F\ge0\) 相抵，得"两体积约化"：只需在 \(V_1,V_2\) 排除非标准最小化子即可。

再把候选者逼进单位立方体的角落。先证区域关于六个坐标环面反射对称：平分体积的切割环面两侧分别反射，两个竞争者的平均周长仍是最小值，再由解析延拓与原边界重合。法向分量 \(N_i\) 经 Jacobi 方程结点域（nodal domain）论证得严格单调性 \(N_i>0\)，区域成为下集（down-set）；顶点模式把候选压缩为三、四顶点两种。

截面恒等式是核心工具：通量 \(\int_{\partial E_z}\alpha\,d\ell=b_zA+h(v(z)-V)\)、投影 \(s-r\le A\sqrt{1-b_z}\) 与 coarea 公式。四顶点模式在两转变体积处被"角区反射＋平面等周不等式＋标量不等式"排除；三顶点模式在 \(V_1\) 处由纯标量估计排除，均用有理数界验证。

最后一步最难：\(V_2\) 处三顶点模式，即论文核心创新——嵌套截面（nested sections）的定量使用。截面恒等式锁定 \(0.64\le h\le2.25\)，但基础估计 \(B(h)\) 在中等曲率区间 \([1.02,1.62]\) 变负。补救：用向量场标定底部角补截面的两条边缘延伸，得 \(hs\ge(1-s)/L+\pi L/4\)，同时控制两方向；中间截面都含于底部截面（嵌套），迫使带状截面（strip）小端点受上界约束，在宽 \(\delta\) 的面积区间把周长下界提升到 \(p^2\ge1+c\delta^2H(q)\)；再经 Jensen 不等式与导数估计把周长增益换成面积增益 \(C_0\delta^3\)，最终得 \(A-1\ge B(h)+S(h)\)；附录用有理算术验证其恒正，与板竞争者的 \(A\le1\) 矛盾，定理得证。

## 可信度与备注

按任务元数据，本文主结果尚无 Lean 形式化证明（族描述虽附 Lean 文档链接，以本文标注 formalized=false 为准），请以社区核验为准；论文声明可复现的精确有理计算随源码提供。它是结果族 354 本批次唯一手稿，独立承担该族全部结论；论证显式引用既有文献（HPRR、Ritoré–Ros、Milman 等），新贡献集中在嵌套截面排除技术。按 OpenAI 官方声明，未经形式化的结果可能有问题，宜以社区核验为最终依据。

{% endraw %}
