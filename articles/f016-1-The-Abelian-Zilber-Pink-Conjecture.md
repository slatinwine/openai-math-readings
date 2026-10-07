---
layout: default
title: "The abelian Zilber–Pink conjecture"
family: "016"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The abelian Zilber–Pink conjecture

> 结果族 016：Zilber–Pink in abelian varieties and the Siegel threefold　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文在 `@@M@@\overline{\mathbb Q}@@` 上证明了完整的阿贝尔簇（abelian variety）版 Zilber–Pink 猜想：任意子簇 `@@M@@X@@` 相对其最小包含的特殊子簇只有有限多个极大非典型子簇，即"不大可能交点"不会太多。这是该猜想首次在任意维阿贝尔簇、不设任何附加几何或高度假设下获证。

## 问题背景

在阿贝尔簇 `@@M@@A@@` 中，"特殊子簇"（special subvariety）指阿贝尔子簇平移一个挠点（torsion point）得到的余集。维数计数预言：子簇 `@@M@@X@@` 与特殊子簇 `@@M@@T@@` 的交一般不超过 `@@M@@\dim X+\dim T-\dim S@@`；一旦交意外"过大"，就叫不大可能交点（unlikely intersection）。Zilber（2002）对半阿贝尔簇提出、Pink（2005）系统表述的 Zilber–Pink 猜想断言：即便 `@@M@@T@@` 可以变动，这类交也只可能有有限多个"极大坏例子"。挠点情形即 Raynaud 的 Manin–Mumford 定理；曲线情形由 Habegger–Pila（2016）解决，后被 Barroero–Kühne–Schmidt 推广到半阿贝尔簇。高维此前只有带"商维数条件"或高度界的非稠密结果（Rémond、Habegger、Viada、Habegger–Pila），极大非典型有限性只做到余维 1 和 `@@M@@E^g@@` 中的余维 2。卡壳的根源是：交点的 Néron–Tate 高度（canonical height）在不同方向可以以悬殊速率增长，且点的次数无界，经典 Galois 覆盖论证无法直接使用。

## 主要结果

**主定理**：对任意数域 `@@M@@K@@`、任意定义于 `@@M@@K@@` 的阿贝尔簇 `@@M@@A@@`、任意不可约子簇 `@@M@@X\subseteq A_{\bar K}@@`，记 `@@M@@S=\langle X\rangle_{\mathrm{sp}}@@` 为含 `@@M@@X@@` 的最小特殊子簇，则 `@@M@@X@@` 在 `@@M@@S@@` 中的极大非典型子簇（atypical subvariety，即 `@@M@@X\cap T@@` 的某不可约分支 `@@M@@Y@@`，满足 `@@M@@\dim Y>\dim X+\dim T-\dim S@@`，按包含关系取极大）只有有限多个；等价地，有限多个真子簇 `@@M@@Y_1,\dots,Y_m@@` 即可吸纳所有非典型交。定理不设 `@@M@@A@@` 的单性、自同态或复乘（complex multiplication）假设。证明分两级：先证普适的非稠密性（non-density）定理——若 `@@M@@X@@` 不含于任何真挠余集，则 `@@M@@X\cap A^{[\dim X+1]}@@`（`@@M@@A^{[r]}@@` 为余维数（codimension）至少 `@@M@@r@@` 的特殊子簇之并）不在 `@@M@@X@@` 中 Zariski 稠密；再用 Barroero–Dill 的最优子簇约化升格为有限性。附带的推论给出 Pink 猜想 5.2 的代数点情形：`@@M@@X(\Qbar)\cap(A^{[d+1]}(\Qbar)+\Gamma)@@` 不稠密，其中 `@@M@@\Gamma@@` 为有限秩（finite rank）子群，可含挠子群与可除闭包；`@@M@@d=1@@` 时该交有限。

## 证明思路

核心是反证：假设存在一列 Zariski 一般的高余交点。先做"高度尺度分解"：反复取"点的高度变小"的极大维数商，把 `@@M@@A@@`（差一个同构）拆成至多一个有界层（低因子，`@@M@@H_{i0}=1@@`）与有限多个逐级放大的无界层（高因子），相邻尺度之比 `@@M@@H_{i\ell}/H_{i\ell'}\to0@@`。将每层点除以 `@@M@@\sqrt{H_{i\ell}}@@` 得到有界向量族，它们含于挠余集的关系收敛为一个实自同态投影 `@@M@@P@@`，其余投影 `@@M@@\Phi@@` 在极限下把归一化向量杀为零。于是问题化为"辅助序列定理"：条件 `@@M@@\codim_{\Lie(W)}V>\sum_\ell m_\ell@@` 与 `@@M@@\|\Phi(q_i)\|\to0@@` 不可能并存。

再对环境维数作极小反例归纳。"投影排除"引理说：若某非零积方向 `@@M@@C@@` 在标记点处贡献过大的局部纤维维数，商掉它就得到更小的反例。借助 Ax 的解析子群定理（analytic subgroup theorem）与固定母簇中测地最优（geodesic-optimal）方向只有有限多个的事实（Habegger–Pila），把切向失效转化为这种可商方向，从而得到一致的切向正性：对所有过标记点的子积 `@@M@@Z=\prod_\ell Z_\ell@@`，积分 `@@M@@P_Z(g)=\int_Z(g^*\omega)^{\dim Z}@@` 在 `@@M@@\Phi@@` 的邻域内一致为正，且对逐差映射（consecutive-difference map）`@@M@@\Delta\Phi@@` 的对应积分亦为正。

全部为高因子时，套用 Dill 推广的 Vojta–Rémond 高度不等式（源自 Vojta 曲线法与 Faltings 的阿贝尔簇方法）。关键在常数次序：不等式的乘法常数 `@@M@@c_1@@` 不依赖对 `@@M@@\Phi@@` 的有理逼近精度，故可先固定 `@@M@@c_1@@`，再取足够精的有理逼近 `@@M@@f/e@@`；用二进倍数 `@@M@@v_{i\ell}=u2^k@@` 平衡各因子的高度尺度，使源高度占比不小于 `@@M@@\frac14\sum_\ell\kappa_\ell@@`，而像高度不超过 `@@M@@c_1C^2\eta^2@@`，取 `@@M@@\eta@@` 足够小即矛盾。

存在低因子时改走算术路线：选取度数与定义域次数一致有界、维数最小的辅助积 `@@M@@Z_i=\prod_\ell Z_{i\ell}@@`（标记点本身的次数仍可任意大）。决定性的一步是比较固定低因子上的两个极限测度：分别输出（separate-output）测度在对角点处密度为正，而逐差测度在该点密度为零；若算术交 `@@M@@(\bar E_i^{d+1}\cdot Z_i)@@` 的下极限趋零，则由算术基本不等式与算术 Siu 不等式（Yuan、Yuan–Zhang 的算术正性框架）产生的小点会迫使这两个测度重合，矛盾。由此得到无穷远处范数不超过 `@@M@@\exp(-cn_iM_i^2)@@` 的小截面，其在标记点有一致正的加权消没指数（weighted vanishing index）；最后用 Faltings 乘积定理（Evertse 显式形式）切出一个过标记点的真因子，其度数与 Galois 共轭个数被多重性计算控制，与 `@@M@@Z_i@@` 的最小性矛盾。序列定理成立后，普适非稠密定理经 Barroero–Dill 约化（配合"极大非典型蕴含最优"的引理）升级为主定理的有限性。

## 可信度与备注

本文主结果尚无 Lean 形式化证明；按 OpenAI 官方声明，"未经形式化的结果可能有问题"，请以社区核验为准。论文自陈不给出极大非典型子簇个数的有效或一致界，结论是纯粹的存在性有限。同族另两篇姊妹篇把 Zilber–Pink 的曲线情形推进到 Siegel 三维簇 `@@M@@\mathcal A_2@@`（分别处理 `@@M@@E\times\mathrm{CM}@@` 分量与四元数除环分量），与本文的阿贝尔簇一般定理互相印证，合成结果族 016 的完整图景。

{% endraw %}
