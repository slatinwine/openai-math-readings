---
layout: default
title: "Topological triviality of $\\mu$-constant families of surface singularities"
family: "064"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Topological triviality of `@@M@@\mu@@`-constant families of surface singularities

> 结果族 064：Topological triviality of μ-constant surface singularities　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：`@@M@@\mathbb C^3@@` 中孤立超曲面奇点的全纯单参数族只要 Milnor 数（Milnor number）`@@M@@\mu@@` 恒定就必拓扑右平凡。`@@M@@\mu@@` 常数问题在唯一遗留的曲面维数上得到肯定答案——单凭 `@@M@@\mu@@` 这一个数，确实锁死了曲面奇点族的全部拓扑。

## 问题背景

Milnor 数 `@@M@@\mu@@` 是孤立超曲面奇点最基本的拓扑不变量：邻近光滑水平集（Milnor 纤维，Milnor fiber）同伦等价于一束球，球数恰为 `@@M@@\mu@@`。`@@M@@\mu@@` 常数问题问：全纯族 `@@M@@f_t@@` 中每个成员的 `@@M@@\mu@@` 都相同时，定义函数是否在拓扑上不随 `@@M@@t@@` 变化？Lê 与 Ramanujam 在 1976 年证明超曲面维数不等于二时答案肯定：高维借 `@@M@@h@@`-配边定理（`@@M@@h@@`-cobordism theorem）把纤维比较变成乘积，曲线情形归结为曲面拓扑，Timourian 与 King 随后补出相应的局部平凡化。唯独复二维——`@@M@@\mathbb C^3@@` 中的曲面奇点——此路不通：Milnor 纤维是实四维流形，四维拓扑使配边给不出乘积结构。更强的 Whitney 正则性需要全部截面 Milnor 数 `@@M@@\mu^{(1)}\le\mu^{(2)}\le\mu@@` 同时常数（Teissier 判据），而 Briançon–Speder 的例子表明 `@@M@@\mu@@` 常数的族中 `@@M@@\mu^{(2)}@@` 可以变动，拓扑平凡也不蕴含 Whitney 正则，故只假设 `@@M@@\mu@@` 的证明必须容忍这些现象。2024 年 Fernández de Bobadilla 与 Pełka 证明 `@@M@@\mu@@` 常数蕴含重数（multiplicity）常数，补上了 `@@M@@\mu^{(1)}@@` 一环，但 `@@M@@\mu^{(2)}@@` 仍无着落——这正是本文要绕开的缺口。

## 主要结果

主定理：设 `@@M@@F:(\mathbb C^3\times\Delta,\{0\}\times\Delta)\to(\mathbb C,0)@@` 全纯，记 `@@M@@f_t(x)=F(x,t)@@`。假设对每个 `@@M@@t@@` 均有 `@@M@@f_t(0)=0@@`、`@@M@@f_t@@` 在原点有孤立临界点，且 `@@M@@\mu(f_t,0)=\mu(f_0,0)@@`。则缩小参数圆盘与各代表元后，存在同胚芽

`@@M@@D\Phi(x,t)=(\phi_t(x),t),\qquad \phi_t(0)=0,\quad \phi_0=\mathrm{id},\qquad f_t(\phi_t(x))=f_0(x),@@`

且 `@@M@@\Phi@@` 与 `@@M@@\Phi^{-1}@@` 都在原点截面附近关于 `@@M@@(x,t)@@` 联合连续。这就是拓扑右平凡（topological right-triviality）：环境同胚保持参数、钉住原点截面，把每个 `@@M@@f_t@@` 搬回中心函数 `@@M@@f_0@@`。定理对参数依赖只要求全纯、不要求线性；曲面不必是对数典范（log canonical）奇点；证明里使用的有限参数覆盖在构造最终同胚前被拆除；同一批环境映射还同时把零点集与邻近非零水平集一并进行拓扑搬运。

## 证明思路

全篇按对数典范性（log canonicity）分流，随后数值比较、同步消解、环境搬运，四步走。

第一步分流。由 Varchenko–Steenbrink 的谱常数定理、Kollár 的阈值公式与 Kawakita 的伴随反转（inversion of adjunction）可知，"是否对数典范"沿 `@@M@@\mu@@` 常数族不改变。对数典范分支通过截面 Milnor 数处理：等重数定理供出 `@@M@@\mu^{(1)}@@` 的常数性，配合 Teissier 判据得到 Whitney 正则性，再由 Whitney 型搬运判据收尾；二重点（double point）情形则化归为平面曲线的经典 `@@M@@\mu@@` 常数问题。

真正的难点是非对数典范分支，核心是证明 Wahl 对数不变量 `@@M@@\beta=-P_{\mathrm{loc}}^2@@` 沿族常数：在好消解上把 `@@M@@K+E@@` 作相对 Zariski 分解，取与正部 `@@M@@P@@` 交数相同的那个例外有理闭链，其负平方即 `@@M@@\beta@@`。先利用孤立奇点的有限决定性给每个成员换成多项式代表，并在射流空间（jet space）的 `@@M@@\mu@@` 层上证明 `@@M@@g\mapsto\beta@@` 可构造且只取有限多个值，从而把断言归约到代数曲线上的多项式族。再把族高次紧化为只在指定点带该奇点的射影族（Steenbrink 构造），经半稳定约化与三对数极小模型程序（log minimal model program）得到既约特殊纤维 `@@M@@S_0+\sum_a S_a@@`：`@@M@@S_0@@` 支配中心曲面，附加射影面 `@@M@@S_a@@` 全部压在奇点之上，且每个 `@@M@@K_{S_a}+B_{S_a}@@` nef。

数值比较是一次欧拉示性数的对消。`@@M@@\mu@@` 常数使穿孔射影纤维的欧拉数恒定，扣除与 `@@M@@X_0\setminus\{0\}@@` 同构的 `@@M@@S_0^\circ@@` 的贡献后得 `@@M@@0=\sum_a\chi_c(S_a^\circ)+\delta@@`，Greuel–Steenbrink 定理给出 `@@M@@\delta\ge0@@`；Langer 的轨体（orbifold）Bogomolov–Miyaoka–Yau 不等式又给 `@@M@@0\le(K_{S_a}+B_{S_a})^2\le3\chi_c(S_a^\circ)@@`。两头夹逼迫使每个对数平方为零，再经基于希尔伯特多项式首项系数的相交数专门化引理，转出 `@@M@@\beta@@` 沿族常数。

由 `@@M@@\beta@@` 常数到同胚分两段。Okuma 定理在有限基变换 `@@M@@t=u^e@@` 后给出同时半好消解（simultaneous semigood resolution），例外限制是既约节点曲线；固定球的欧拉数恒等式迫使这些节点无一被光滑化——光滑化会让例外曲线的欧拉数掉一——于是例外除子相对正规相交。最后在消解后的管域上提升参数方向的向量场，压回穿孔零纤维，再扩张到环境非零水平并保持函数值；逆向搬运论证同胚及其逆在原点处的联合连续性；角缝拼接 `@@M@@\phi_t=H_{re^{i\theta/e}}\circ J_{r\theta/(2\pi)}@@` 把 `@@M@@e@@` 次覆盖精确粘回原圆盘，定理告成。

## 可信度与备注

本结果族（064）目前仅此一篇手稿，主结果尚无 Lean 形式化证明。论文把重量压在若干已发表的外部支柱上——Fernández de Bobadilla–Pełka 的等重数定理、Okuma 的同时消解定理、Greuel–Steenbrink 的欧拉非负性与 Langer 的轨体不等式——这些环节若逐一成立，最终合成是稳健的。按 OpenAI 官方声明，未经形式化的结果可能存在问题，读者宜以社区核验为准。

{% endraw %}
