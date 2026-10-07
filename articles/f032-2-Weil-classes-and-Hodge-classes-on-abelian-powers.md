---
layout: default
title: "Weil classes and Hodge classes on abelian powers"
family: "032"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Weil classes and Hodge classes on abelian powers

> 结果族 032：Hodge and Kuga–Satake results for all projective K3 surfaces　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
对带虚二次域作用的复阿贝尔簇，论文证明了两族"全体自幂"版本的有理 Hodge 猜想：双曲 `@@M@@(3,3)@@` 型的分裂 Weil 六维簇，以及一切维数不超过五的带虚二次作用阿贝尔簇；每个余维数、每个自幂都成立，且包含非单簇与带额外自同态的特殊周期。

## 问题背景
有理 Hodge 猜想对阿贝尔簇的"所有自幂"版本远强于单簇版本：自幂上会出现耦合多个拷贝的张量 Hodge 类。1979 年 Weil 的行列式构造给出了除子类之外最早的检验类：对带虚二次域 `@@M@@E@@` 作用、相伴 Hermite 型符号差为 `@@M@@(n,n)@@` 的 `@@M@@2n@@` 维阿贝尔簇，两个嵌入行列式生成一个 `@@M@@(n,n)@@` 型有理平面（Weil 平面）。此后的里程碑包括 Schoen 对 `@@M@@\Q(\sqrt{-3})@@` 四维簇的代数性证明、Floccari 对判别式 1 的 Weil 四维簇（经 Kuga–Satake）的全体自幂结论、Floccari–Fu 用 OG6 型奇异簇的另一证明，以及 Markman 用割线层（secant sheaf）构造证明分裂 Weil 六维簇的 Weil 平面处处代数。悬而未决的是：六维簇与低维簇在特殊周期（Hodge 群变小、出现额外张量）时的全体自幂 Hodge 猜想。

## 主要结果
定理 1.1（分裂 Weil 六维簇）：设 `@@M@@E@@` 虚二次，`@@M@@A@@` 为带 `@@M@@E@@` 作用的复阿贝尔六维簇，且某相容极化的有理同调 Hermite 型 `@@M@@h_E@@` 双曲、符号差 `@@M@@(3,3)@@`，则 `@@M@@A@@` 的每个自幂 `@@M@@A^m@@`、每个余维数上有理 Hodge 猜想成立。定理 1.2（低维）：维数 `@@M@@\le5@@` 且带虚二次作用的复阿贝尔簇同样结论。两条定理都允许非单簇、作用不必是完整自同态代数、也不必在重复因子上中心，并在有额外自同态的特殊周期上成立；低维情形无需单独挑选极化（可由任意 Riemann 型平均得到）。

## 证明思路
证明是三段式。其一是一个"行列式判据"（定理 2.5）：把 `@@M@@H=H^1(A,\Q)@@` 分解为环型（CM）部分与辛、正交、线性典型块，若 Hodge 群的导群在标量扩张后包含各块上 `@@M@@\operatorname{Sp}@@`、`@@M@@\operatorname{SO}@@`、`@@M@@\operatorname{SL}@@` 的标准作用，且满足平衡方程——每当若干顶外幂（行列式线）`@@M@@D(W_j)@@` 与 CM 嵌入线的失衡量 `@@M@@\epsilon_\gamma@@` 之和对每个 Galois 共轭 `@@M@@\gamma@@` 均为零时，乘积线 `@@M@@\bigotimes D(W_j)@@` 由 CM 阿贝尔簇的对应"供给"——则一切平衡张量代数，全体自幂的 Hodge 猜想成立。机制在于：经典不变量理论（辛、正交、特殊线性群的第一基本定理）把不变张量约化为配对与行列式线；配对是除子类（Lefschetz `@@M@@(1,1)@@`）；而供给子空间中的有理 Hodge 类可提升回 CM 源，由姊妹篇的 CM 定理（每个复 CM 阿贝尔簇的有理 Hodge 猜想）代数化。其二是几何输入：论文详细重做 Markman 的割线层构造，证明定理 3.1——每个双曲 Weil 六维簇的有理 Weil 平面在所有相容周期代数。做法是从三亏格 Jacobi 簇上不相交 Abel 轨道的理想层出发，经固定的 Fourier–Mukai 变换与对偶得到 `@@M@@X\times\widehat X@@` 上的凝聚层，其规范化陈特征为候选闭链类；再用 Hochschild–Atiyah 迹恒等式与等变 `@@M@@\Ext@@` 计算证明半正则性（求值像充满整个不变障碍空间且迹单射），经有限商下降、射影丛转化、形变论证、Hilbert 参数空间铺开与同源清除分母，达到所有双曲周期。其三是落地：按 Albert 分类枚举低维导群的可能块，加入 CM 椭圆因子供给小符号差（两符号均 `@@M@@\le3@@`）的行列式；Galois 平衡方程迫使净指数相等（`@@M@@n_1=n_2@@`，三次中心时 `@@M@@n_1=n_2=n_3@@`），剩下的恰好是全 `@@M@@E@@`-行列式，由 Weil 平面或低维供给引理覆盖。这一步正是容纳特殊周期上额外自同态的关键。

## 可信度与备注
本文主结果暂无 Lean 形式化证明。它以同日的 CM 阿贝尔簇有理 Hodge 定理为唯一外部猜想输入，并为同族的覆盖曲线篇提供张量工具；按 OpenAI 官方声明，未经形式化的结果可能有问题，读者应以社区核验为准。

{% endraw %}
