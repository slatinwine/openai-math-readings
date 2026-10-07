---
layout: default
title: "Fourfold nonvanishing by minimal metrics and moving jets"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Fourfold nonvanishing by minimal metrics and moving jets

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了光滑连通射影复四维簇的典范非消失：`@@M@@K_X@@` 伪有效即有 `@@M@@H^0(X,mK_X)\ne 0@@`；不设数值维数、非正则度或欧拉示性数条件，经 Hashizume 约化进一步给出四维 log canonical pair 的非消失，补齐四维对数丰性的第一截面缺口。

## 问题背景
典范非消失（canonical nonvanishing）问：光滑射影簇上伪有效（pseudo-effective）的典范丛是否真有非零多典范截面？由 BDPP 定理，`@@M@@K_X@@` 伪有效等价于 `@@M@@X@@` 不被有理曲线覆盖，故此问题即"每个非单有理簇上找多重典范形式"。它弱于丰性（abundance，要求 nef 除子半充盈），但得到第一个截面是独立且著名的困难。三维由 Miyaoka、Kawamata 解决；四维已知零散结果：Fujino 处理正非正则度的典范四维簇，Lazić–Peternell 处理典范数值维数为一且 `@@M@@\chi\ne 0@@` 的终端极小簇，Ambro 的典范丛公式处理 nef 维数偏低像的情形，Liu–Xu（2025）则要求非消失为假设且限制 `@@M@@\nu\le 1@@`。无任何附加假设的四维光滑非消失此前未知。

## 主要结果
主定理（Theorem 1.1）：`@@M@@X@@` 光滑连通射影复四维簇，`@@M@@K_X@@` 伪有效，则存在正整数 `@@M@@m@@` 使 `@@M@@H^0(X,mK_X)\ne 0@@`；定理不设数值维数、非正则度、全纯欧拉示性数条件，结论是定性的（对 `@@M@@m@@` 无一致界）。推论（Corollary 1.2）：`@@M@@(X,\Delta)@@` 为维数至多四的连通正规射影 log canonical 复 pair，`@@M@@\Delta\ge 0@@` 有理、`@@M@@D=K_X+\Delta@@` 为 nef 的 `@@M@@\mathbb{Q}@@`-Cartier 除子，则对每个使 `@@M@@rD@@` Cartier 的 `@@M@@r@@` 有 `@@M@@H^0(X,\mathcal{O}_X(mrD))\ne 0@@`；结合配套的"从伴随丛既约支撑提升截面"一文即得四维对数丰性（该推论不进入证明本身）。

## 证明思路
证明用反证法，先固定一个"最坏"的极小模型。设非消失失败：跑典范 MMP（翻转存在性由 BCHM 给出，伪有效四维的终止由 Chen–Tsakanikas 定理给出，且伪有效排除 Mori 纤维化终点），得射影 `@@M@@\mathbb{Q}@@`-factorial 终端极小模型 `@@M@@Y@@`：`@@M@@K=K_Y@@` nef、`@@M@@\kappa=-\infty@@`、`@@M@@K^4=0@@`；若 `@@M@@q(Y)>0@@` 则 Fujino 的四维结果使 `@@M@@K@@` 半充盈，矛盾，故 `@@M@@q(Y)=0@@`；若 nef 维数低于四，Ambro 典范丛公式加低维丰性同样导出矛盾，故 nef 维数满；由 nef reduction 的曲线性质，过极一般点的每条整曲线 `@@M@@K\cdot C>0@@`，固定 Cartier 指标 `@@M@@\iota@@` 后一致有下界 `@@M@@K\cdot C\ge 1/\iota@@`；再用 Hilbert 概形参数化与分歧/终端性论证，过极一般点的每个真正维子簇均为一般型（general type）。这两条性质将控制后续 jet 论证的移动中心。

第一步是数量级 jet 估计：取逼近 `@@M@@K@@` 的 nef 射线的充足极化，缩放使其体积小而过极一般轨迹的曲线度数趋于无穷。若某截面在移动点处消没过高，会在 jet 系统的基轨迹中产生持续分量；用 Ein–Küchle–Lazarsfeld 的参数微分法控制沿该分量的重数（作用于满足 jet 条件的整个截面空间，从而控制分量理想的各次幂），交集理论界定其次数与典范交，一般型造出有界度数曲线，与所选缩放矛盾。由此得到对所有允许 Cartier 度数截面一致的消没上界。

第二步是"双槽"jet：在 `@@M@@Z=\mathbb{P}(\mathcal{O}_{Y\times Y}(S_{0,1})\oplus\mathcal{O}_{Y\times Y}(S_{0,2}))@@`（`@@M@@S_0=\iota K@@`，下标表示从相应因子拉回）上，对称幂公式记录张量幂在两因子间的分配，两个和式给出两个特殊截面；通过 Seshadri 常数证明 `@@M@@Z@@` 在避开它们的极一般点处生成大量 jet。移动基分量的处理中有一个硬情形：限制到一个基底坐标固定的切片后，异于两个特殊截面的多截面与它们相交于除子，其差表示 `@@M@@K@@` 的倍数——这正是"带号代表"（signed representative，系数可正可负）；须证其完全支撑的消解上对数伴随为大（big）。此处引入姊妹篇《Minimal metrics…》的两个解析输入：nef 射影 klt 伴随拉回的极小度量零 Lelong 数，及端点度量下的 `@@M@@H^1@@` 内部单射。上同调单射使到整个既约非 klt 边界的限制满射，低维丰性与导子（conductor）粘合在边界上供给截面，继而 Gongyo–Matsumura 四维准则（非消失加零 Lelong 度量）给出半充盈，从而排除该多截面；其余支配有限对应由固定分支补集与典范度数为正排除。

最后是秩矛盾：固定极化、光滑消解、终止于曲线的一般超平面截面旗、有限 jet 系统及爆破点上的一条固定可动曲线，把这些有限数据铺开后模足够大的素数约化。普通 jet 给出通秩很大的赋值矩阵；而对角线上，典范 Frobenius 滤过（Sun、Kitadai–Sumihiro；曲线情形源于 Raynaud 与 Joshi–Ramanan–Xia–Yu）经 Mustață–Schwede 的普通幂与 Frobenius 幂局部比较，把取值空间表示为余切丛截断幂的截面；单个旗估计界定这些空间维数之和，迫使对角线上秩小得多。非零极大行列式必在对角点高阶消没，而其两个因子上的行列式线丛类被固定可动曲线控制，界定约化后每个截面的消没阶——小行列式阶与秩差所迫的高阶不相容，得矛盾。有限数据 Frobenius 比较定理本身在配套文献中独立证明，不依赖任何丰性或次可加性结论。

## 可信度与备注
本篇主结果暂无 Lean 形式化证明。它是族 034 的四维支柱：向上接《Log abundance in characteristic zero》的全维数归纳（后者把同一 jet–Frobenius 骨架推到任意维），向下用《Minimal metrics…》的零 Lelong 度量与单射定理处理带号代表这一硬情形，四维对数丰性另需"既约支撑提升截面"一文补全。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
