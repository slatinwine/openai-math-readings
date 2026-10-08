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

## 入门导读 🐣

把同一个甜甜圈 A 复制 m 份排成一排，影子之间会出现"跨份关联"——同时纠缠好几份拷贝的规整影子，这是 Hodge 猜想最狡猾的对手。本文证明：两大类带虚数乘法对称性的阿贝尔簇——双曲 `@@M@@(3,3)@@` 型的六维 Weil 簇，以及一切维数不超过五的同类——的所有自幂上，这些关联影子全部来自"真骨头"。

**关键词卡片**

- Weil 类（Weil classes）：1979 年 Weil 用行列式造出的例外影子，光靠除子（最简单的骨头）怎么乘都拼不出来。
- 虚二次作用（imaginary-quadratic action）：坐标允许被 `@@M@@\Q(\sqrt{-d})@@` 里的数整体相乘。
- 自幂（self-power）：`@@M@@A\times A\times\cdots\times A@@`，m 份拷贝的乘积。
- 符号差 (3,3)（signature (3,3)）：相伴度量形式正、负惯性指数各半，正是 Weil 类出没的舞台。
- Hodge 群（Hodge group）：影子对称性大小的量度；它越小，例外影子越多。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<circle cx="110" cy="110" r="54" fill="none" stroke="#333" stroke-width="1.8"/>
<ellipse cx="110" cy="110" rx="16" ry="8" fill="none" stroke="#333" stroke-width="1.5"/>
<circle cx="280" cy="110" r="54" fill="none" stroke="#333" stroke-width="1.8"/>
<ellipse cx="280" cy="110" rx="16" ry="8" fill="none" stroke="#333" stroke-width="1.5"/>
<circle cx="450" cy="110" r="54" fill="none" stroke="#333" stroke-width="1.8"/>
<ellipse cx="450" cy="110" rx="16" ry="8" fill="none" stroke="#333" stroke-width="1.5"/>
<path d="M 135 66 C 200 28 360 28 425 66" fill="none" stroke="#888" stroke-width="1.6" stroke-dasharray="6,4"/>
<path d="M 135 154 C 200 196 360 196 425 154" fill="none" stroke="#888" stroke-width="1.6" stroke-dasharray="6,4"/>
<text x="280" y="26" font-size="14" text-anchor="middle">同时纠缠多份拷贝的"张量影子"（难点）</text>
<text x="280" y="216" font-size="14" text-anchor="middle" fill="#555">自幂 A^m = A × A × … × A</text>
<text x="280" y="244" font-size="14" text-anchor="middle">定理 1.1：六维双曲 (3,3) 型；定理 1.2：维数 ≤ 5</text>
<text x="280" y="266" font-size="14" text-anchor="middle">这些 A 的所有自幂、所有余维数上，影子全有真骨头</text>
</svg>

</div>

难点很直观：单份拷贝上的影子早有办法，纠缠两三份拷贝的张量类才麻烦。定理 1.1：对带虚二次作用、度量型双曲 `@@M@@(3,3)@@` 的六维簇，全部自幂、全部余维数上猜想成立；定理 1.2：维数不超过五的带虚二次作用簇同样成立。连"非单簇"（几块甜甜圈拼成的）和带额外对称的特殊成员也包括在内。

**为什么值得关心**

六维与低维的全覆盖补上了 Markman 之后留下的空档；证明只依赖同族姊妹篇的 CM 定理这一个外部输入，是整个结果族证明网络的关键一环。

> 暂无形式化证明（AI 结果待核验）

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
