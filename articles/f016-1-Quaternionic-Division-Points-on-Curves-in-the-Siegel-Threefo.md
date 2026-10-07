---
layout: default
title: "Quaternionic division points on curves in the Siegel threefold"
family: "016"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quaternionic division points on curves in the Siegel threefold

> 结果族 016：Zilber–Pink in abelian varieties and the Siegel threefold　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Siegel 三重态 `@@M@@\mathcal A_2@@` 中任何 Hodge 一般代数曲线上，全几何自同态代数恰为 `@@M@@\Q@@` 上不定四元数除代数的点只有有限多个——Zilber–Pink 猜想在 `@@M@@\mathcal A_2@@` 曲线情形的四元数分量由此无条件成立，不施加任何边界或约化假设。

## 问题背景

Siegel 模空间（Siegel moduli variety）`@@M@@\mathcal A_2@@` 参数化主极化阿贝尔曲面（principally polarized abelian surface），是三维代数簇，故称 Siegel 三重态。一点所代表的阿贝尔曲面，其全自同态代数 `@@M@@\End^0(A)=\End_{\Qbar}(A)\otimes_{\Z}\Q@@` 除一般型与复乘外，还可能是 `@@M@@\Q@@` 上的不定四元数除代数（indefinite quaternion division algebra）；这类点恰好落在 `@@M@@\mathcal A_2@@` 的特殊曲线上。Zilber（2002，半阿贝尔簇情形）与 Pink（2005，Shimura 簇情形）提出的 Zilber–Pink 猜想断言：Hodge 一般曲线与全部特殊曲线之并只交于有限多个点——三维空间里两条曲线相交的预期维数为负，每个交点都是"非可能交点"（unlikely intersection）。此前 Daw 与 Orr 仅在曲线闭包触及 Baily–Borel 紧化零维边界时证得四元数情形，一般曲线还需假设大伽罗瓦轨道估计；Papas 的系列结果要么仍依赖退化或边界条件，要么其高度估计要按超奇异邻近位置的个数计账。边界与约化假设一直是绕不开的门槛，本文将其全部去除。

## 主要结果

主定理：设 `@@M@@C\subset\Acal_{2,\Qbar}@@` 是既约、不可约、闭的 Hodge 一般代数曲线（Hodge generic，即不含于任何真特殊子簇，也不含于其 Hecke 平移），则
`@@M@@D\Sigma_{\mathrm{QM}}(C)=\{\,s\in C(\Qbar):\ \End^0(A_s)\ \text{是}\ \Q\ \text{上的不定四元数除代数}\,\}@@`
是有限集。注意条件是全几何有理自同态代数**恰好等于**一个四元数除代数：这排除了分裂代数 `@@M@@M_2(\Q)@@`，也不允许换成"容许四元数嵌入"之类的较弱条件。四元数代数本身、其判别式与自同态阶（endomorphism order）都允许随点变化，所有四元数特殊曲线上的点被一并计数；对 `@@M@@C@@` 的边界、对点的约化类型（包括超奇异约化）不设任何假设。

## 证明思路

全文先做几何编码：把曲线提升到固定的精细层（fine level）覆盖 `@@M@@S\to C@@`，取一个内部 QM 点作为中心 `@@M@@t_0@@`，用局部参数 `@@M@@a=x(t)@@` 度量目标点与中心的偏离。四元数乘法被编码为秩五二次局部系统 `@@M@@\mathbb V@@`——一阶上同调上迹零、Rosati 对称的算子，配对 `@@M@@\pair{T}{U}=\tfrac14\Tr(TU)@@`、符号差 `@@M@@(3,2)@@`：QM 点的自同态在其中张成正定有理平面 `@@M@@E_t@@`；由 André 的单值定理，单色群（monodromy）是整个 `@@M@@\SO_5@@`。

再做算术构造：由 Masser–Wüstholz 自同态估计，每个目标点可配上两个 Rosati 范数受 `@@M@@(dh)^c@@` 控制的无关整向量 `@@M@@P@@`，与中心的固定向量对 `@@M@@B@@` 经水平输运（horizontal transport）`@@M@@Y(a)@@` 比较；当目标与中心在某个素点处邻近（即有共同良好约化）时，晶体–de Rham 比较给出迹关系 `@@M@@\pair{B}{Y(a)P}=T_v\in\mathrm M_2(\Q)@@`。有理矩阵 `@@M@@T_v@@` 随素数变化，但把它与自身的 Frobenius 共轭（第二个参数取 `@@M@@b=aR@@`）相减即可消去，经多项式次分组后仍保留足够的局部邻近度总和。

第三步的插值定理属 Bombieri–André 辅助函数传统：把公共关系的泰勒截断加入图坐标 `@@M@@q=f/a^m@@`，逐层构造低次多项式 `@@M@@P@@`，使其在选定赋值处的取值带因子 `@@M@@|a_*|^n@@`、且消失阶与次数之比 `@@M@@n/L@@` 可超过 `@@M@@d@@` 的任何固定多项式；乘积公式便迫使 `@@M@@P@@` 在目标处为零，交与投影逐步降低包含目标的代数簇的维数，归纳得到高度界 `@@M@@h(t)\le C_1[K(t):K]^{C_2}@@`。最难的输入是"非恒等性"：单变量关系与独立变化的点对由 `@@M@@\SO_5@@` 单色性排除，例外点对只能落在支配两条固定曲线的同构对应（isogeny correspondence）上，而这类对应只有有限条。对此论文预先选定辅助素数 `@@M@@\ell@@` 与 `@@M@@\ell@@` 级标记覆盖（由 `@@M@@\Sp_4@@` 单色群的强逼近实现），安排中心与目标的两个平面模 `@@M@@\ell@@` 恰张成退化的四维空间；此时泛函恒等式会迫使 Frobenius 拟同构 `@@M@@u@@`（极化乘子 `@@M@@p/m@@`）以同一符号 `@@M@@\varepsilon=\pm1@@` 同时作用两个平面：正号推出 `@@M@@u=c\cdot\mathrm{id}@@`，但 `@@M@@c^2=p/m@@` 的 `@@M@@p@@`-进赋值为奇数，矛盾；负号使秩四格成为 unimodular 格的正交直和项、其模 `@@M@@\ell@@` 约化必须非退化，又与上述安排矛盾。

最后用 Pila–Zannier 式的 o-极小计数收尾：周期线位于三维二次曲面 `@@M@@Q_V@@` 且垂直于平面 `@@M@@E_t@@`，两个 Hodge 向量的整坐标由 Schmid 的范数估计多项式控制；若目标有无穷多，Habegger–Pila 的路径计数给出一条可定义路径，扫出维数至多为二的代数子集，而完全单色使周期像在 `@@M@@Q_V@@` 中 Zariski 稠密，矛盾。Northcott 定理完成有限性，再经覆盖下降回原来的粗模空间曲线。

## 可信度与备注

本篇 formalized 标注为 false：主结果暂无 Lean 形式化证明，请以社区核验为准，且按 OpenAI 官方声明，"未经形式化的结果可能有问题"。它是结果族 016 的第三篇：第一篇证明 `@@M@@\overline{\Q}@@` 上一般阿贝尔簇的 Zilber–Pink 猜想，第二篇处理 `@@M@@\mathcal A_2@@` 中曲线的 E×CM 分量，本篇补齐四元数除法分量，三者合起来支撑族概述所宣称的 `@@M@@\mathcal A_2@@` 全曲线情形。证明综合了 Masser–Wüstholz 估计、Schmid 范数与退化定理、André 单色性定理及 Pila–Wilkie 计数等既有工具，其关键新意在于高度估计完全不依赖超奇异邻近位置的个数——这正是越过 Daw–Orr 与 Papas 框架中边界假设的所在。

{% endraw %}
