---
layout: default
title: "A Codimension-One Bound for the Singular Set of a Stationary Integral Varifold"
family: "346"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Codimension-One Bound for the Singular Set of a Stationary Integral Varifold

> 结果族 346：Sharp singular-set bounds for stationary integral varifolds　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：任意正维数与正余维数的平稳积分 `@@M@@m@@`-varifold，其奇异集 (singular set) 的 Hausdorff 维数 (Hausdorff dimension) 至多 `@@M@@m-1@@`，且该界无法改进——这解决了 Brena–Decio–De Lellis 记录的欧氏奇异集猜想。

## 问题背景

平稳积分 varifold (stationary integral varifold) 是极小子流形的测度论推广：面积泛函的一阶变分 (first variation) 在每个紧支撑形变下为零，同时允许整数重数 (multiplicity)、自交与奇点。经典理论早已给出"分层"结论：不含平面切锥 (tangent cone) 的奇异点集维数不超过 `@@M@@m-1@@`（Federer 的维数约化；Naber–Valtorta 进一步证明这些经典分层可求长），真正的困难在于以高重数平面为切锥的奇异点——Allard 的重数一正则性定理在那里完全失效。对面积极小电流 (area-minimizing current)，Almgren 与 De Lellis–Spadaro 的理论给出更强的 `@@M@@m-2@@` 界，但极小性假设排除了"两个平面相交"这类最基本的平稳例子，其方法不能照搬。Brena、Decio 与 De Lellis 于 2025 年将欧氏维数猜想记录为 Conjecture 1.1，本文在无任何附加假设的一般情形证明它。

## 主要结果

**定理（主定理）。** 设 `@@M@@V@@` 是开集 `@@M@@U\subset\R^{m+n}@@` 中的平稳积分 `@@M@@m@@`-varifold，`@@M@@m,n\ge1@@`，则

`@@M@@D\dim_{\mathcal H}\operatorname{Sing} V\le m-1 .@@`

其中奇异点指支撑中这样的点：其任何邻域内，varifold 都不等于"某个光滑嵌入极小 `@@M@@m@@`-子流形的固定正整数倍"。定理不要求稳定性、极小性、可定向性、密度上界或余维数假设。界是 sharp 的：取两个相交于 `@@M@@(m-1)@@`-平面的不同 `@@M@@m@@`-平面（各带重数一），其和仍是平稳的，奇异集恰为交线，维数恰为 `@@M@@m-1@@`。

## 证明思路

证明用反证法：设 `@@M@@\dim_{\mathcal H}\operatorname{Sing} V>m-1@@`，取 `@@M@@s@@` 严格介于两者之间。第一步（平坦尺度）只用单调性公式 (monotonicity formula) 与 Hausdorff 测度论：由 Frostman 型论证取出紧集 `@@M@@K@@`（满足 `@@M@@\mathcal H^s(K\cap\mathbf B_r)\le Cr^s@@`），在其一个正上密度点作切锥极限；一个"关于两个中心锥必导致平移不变"的几何论证表明该切锥必是 `@@M@@Q@@` 重平面，同时在尺度 `@@M@@L_i\downarrow0@@` 保留一批中心测度 `@@M@@\sigma_i@@`——支撑在密度恰为 `@@M@@Q@@` 的奇异点上，满足 `@@M@@\sigma_i(\mathbf B_u)\le Cu^s@@`，其极限不能落在任何 `@@M@@(m-1)@@`-维平面内。真正的挑战在于让这些中心在进一步的高度归一化极限中存活。

第二步（拟合与频率）：尺度 `@@M@@L_i@@` 只按几何收敛选出，并非按高度准则挑选。作者用姊妹篇 AE 的极小拟合构造，在每个"好起点"以局部极小图拟合支撑并粘合成参考图，在其上定义加权平方高度 `@@M@@H@@` 与带符号质量 `@@M@@A@@`，频率 `@@M@@P=A/H@@` 满足近似单调性 `@@M@@\dot P\gtrsim(n_*-1)(n_*-2P)@@`；再通过"重启"构造让拟合区间覆盖所有充分晚的 `@@M@@L_i@@`，从而在这些尺度上得到一致的高度倍增比较。

第三步（中心化爆破）把高度除以 `@@M@@a_i=\sqrt{H(r_i)}/r_i\downarrow0@@`：归一化二阶矩非零、一阶矩趋于零、参考图的平均曲率及其一阶法向导数为 `@@M@@o(a_i)@@`。这保证减去参考图后，极限既不被整体抹去、也不残留任意平移。

第四步把一阶变分与带符号超余 (signed excess) 传到极限平面，得到四个线性化测度：高度测度 `@@M@@\nu@@`、倾斜测度 `@@M@@\beta@@`、混合通量 `@@M@@f@@` 与带符号质量测度 `@@M@@\mathfrak m@@`，满足分块半正定、恒等式 `@@M@@\nabla\nu=2f@@`、`@@M@@\operatorname{div}f=\operatorname{tr}\beta@@`，以及单向不等式 `@@M@@2\mathfrak m\le\operatorname{tr}\beta@@`——后者正是 AE 带符号超余定理的极限形式。这一测度表述无需假设极限"叶层"可整体标号或表成单值函数。

第五步（密度中心存活）：普通径向比较在弯曲参考图上精度不足，作者改用按逆参考体积密度加权的测地径向场，把曲率误差对 `@@M@@\sigma_i@@` 逐半径向下平均，关键积分 `@@M@@\int_0^l t^{s-m}\,\mathrm dt<\infty@@` 恰好在 `@@M@@s>m-1@@` 时收敛，于是在每个极限中心得到密度比较 `@@M@@2l^2\int\phi_{x,l}\,\mathrm d\mathfrak m\ge\int\psi_{x,l}\,\mathrm d\nu@@`。

最后是抽象的维数约化 (dimension reduction) 命题：上述比较使频率在每个保留中心处单调且极限 `@@M@@\ge1/2@@`；若中心集维数仍大于 `@@M@@m-1@@`，再作第二次爆破，使频率在张成 `@@M@@\R^m@@` 的中心集上恒等于 `@@M@@P_0\ge1/2@@`；此时半正定矩阵测度中的等号迫使高度测度 `@@M@@\nu\equiv0@@`，与归一化 `@@M@@\nu\ne0@@` 矛盾，定理得证。

## 可信度与备注

本文主结果尚无形式化证明。证明的两个关键输入——带符号超余定理与拟合、频率局部估计——直接取自同族姊妹篇《Almost-everywhere regularity of stationary integral varifolds》（该文证得奇异集的 `@@M@@m@@` 维测度为零）；本文进一步把零测度强化为维数不超过 `@@M@@m-1@@`，而零测度本身并不蕴含维数界。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
