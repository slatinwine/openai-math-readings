---
layout: default
title: "Sharp One-Third Stability of Brenier Maps"
family: "374"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Sharp One-Third Stability of Brenier Maps

> 结果族 374：Sharp one-third stability of Brenier maps　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对紧凸体上的均匀源测度，二次最优传输映射（Brenier 映射）关于目标测度一致地满足 `@@M@@\|T_\mu-T_\nu\|_{L^2(\rho)}\le C\,W_2(\mu,\nu)^{1/3}@@`，且指数 `@@M@@1/3@@` 最优：固定立方体上的三原子目标族推翻了 Letrouit 猜想的一致平方根估计。

## 问题背景

最优传输 (optimal transport) 问：把源测度搬运到目标测度，如何使运输总代价最小？在二次代价 (quadratic cost) 下，Brenier 定理断言最优映射 `@@M@@T_\mu@@` 是某个凸势能 (convex potential) 的梯度，且在零测集外唯一。定量稳定性追问：目标 `@@M@@\mu@@` 微扰时，`@@M@@T_\mu@@` 在 `@@M@@L^2(\rho)@@` 中以何种 Hölder 指数最多移动多少——这关乎 PDE 正则性与统计中的映射估计。此前目标一致 (target-uniform) 的界各有局限：Mérigot–Delalande–Chazal 与 Delalande–Méridot 先后得到 `@@M@@W_1^{2/15}@@` 与 `@@M@@W_1^{1/6}@@`；Divol–Niles-Weed–Pooladian 对非退化有限目标证得 `@@M@@W_2^{1/3}@@`，但常数依赖原子数、质量下界与位点间距。Letrouit 对非凸源证明指数不能超过 `@@M@@1/3@@`，并猜想均匀凸源有一致的平方根稳定性。卡点：目标可为质量趋零、位置趋同的退化原子测度，依赖非退化性的常数都会爆炸。

## 主要结果

主定理（文中 Theorem 1.1）：设 `@@M@@d\ge2@@`，`@@M@@K\subset\R^d@@` 为内部非空的紧凸体，`@@M@@\rho=\mathbf 1_K\,dx/|K|@@` 为其上的均匀概率测度，`@@M@@Y\subset\R^d@@` 为紧集。则存在有限常数 `@@M@@C(K,Y)@@`，使对一切支撑在 `@@M@@Y@@` 上的 Borel 概率测度 `@@M@@\mu,\nu@@`，
`@@M@@D\|T_\mu-T_\nu\|_{L^2(\rho)}\le C(K,Y)\,W_2(\mu,\nu)^{1/3},@@`
其中 `@@M@@W_2@@` 为 2-Wasserstein 距离 (2-Wasserstein distance)。目标可为原子、奇异或绝对连续测度；常数不依赖原子数、质量、间距或密度界；`@@M@@K@@` 无需光滑或严格凸，`@@M@@Y@@` 无需凸，文中给出显式常数。指数不可改进：即使 `@@M@@K=Y=[-1,1]^d@@` 且目标恰有三原子，任何 `@@M@@\alpha>1/3@@` 都使该界失效。这否证了 Letrouit 的平方根猜想，确认 `@@M@@1/3@@` 为该源类上的精确指数。

## 证明思路

论文分两半。反例取三个仿射函数的极大值 `@@M@@u_a=\max\{-x_1,x_1,a\}@@` 与 `@@M@@\widetilde u_a=\max\{-x_1,x_1,a+bx_2\}@@`（`@@M@@b=a/2@@`），由对偶判据，其梯度即到各自像测度的唯一最优映射。倾斜让中心胞腔从 `@@M@@|x_1|<a@@` 变为 `@@M@@|x_1|<a+bx_2@@`：中心质量不变，却令一条源点带在中心与外侧斜率（相差一阶）间切换。两目标均为立方体内三原子测度，`@@M@@W_2=a^{3/2}/2@@`，映射差为 `@@M@@\frac{\sqrt a}{2}\sqrt{1+a^2}@@`，故 `@@M@@a\downarrow0@@` 时二者之比按 `@@M@@a^{(1-3\alpha)/2}@@` 发散。

上界链分四步。第一步是半离散传输 (semi-discrete transport) 的 Laguerre 胞腔 (Laguerre cells) 演算：凸函数 `@@M@@\max_i\{x\cdot y_i+c_i\}@@` 把源分成胞腔；固定正质量 `@@M@@m_i@@` 时截距唯一且 `@@M@@C^1@@` 依赖位点；质量 `@@M@@M_i@@` 与一阶矩 `@@M@@B_i@@` 的微分由公共面面积分表出，质量微分算子为加权图拉普拉斯 (graph Laplacian)，核为常向量，不需其逆的定量界。第二步是核心矩估计：位点固定、截距沿方向 `@@M@@q@@` 扰动时，
`@@M@@D\sum_i\frac{|DB_i[q,0]|^2}{M_i}\le 162\,R^2\sum_i\frac{|DM_i[q,0]|^2}{M_i},@@`
常数 `@@M@@162@@` 与胞腔个数、质量、间距无关。证明先建立中点耦合引理：两凸集上的均匀律有耦合使中点分布被 `@@M@@dx/\sqrt{|U||V|}@@` 控制（Knothe 三角重排 (Knothe rearrangement) 的分位数构造，亦为 McCann 位移凹性 (displacement concavity) 的推论）；再以 `@@M@@\Phi=R^2-|x|^2@@` 为测试函数，用恒等式 `@@M@@\Phi(\frac{X+Z}{2})=\frac{\Phi(X)+\Phi(Z)}{2}+\frac{|X-Z|^2}{4}@@` 把位移平方和压入质量变化二次型。第三步令两组位点沿目标间最优耦合移动、耦合质量固定：由面系数对称性得对偶恒等式，选截距方向 `@@M@@q@@` 使 `@@M@@DM_i[q,0]=m_ir_i@@`（`@@M@@r_i@@` 为截距速度），代入矩估计得 `@@M@@(\sum_i m_ir_i^2)^{1/2}\le\sqrt{162}\,R\,W_2@@`，对时间积分得线性势能估计 `@@M@@\|u_0-u_1\|_{L^2(\rho)}\le(1+\sqrt{162})R\,W_2@@`。最后从势能回到梯度：坐标切片的凸梯度插值不等式给出
`@@M@@D\|\nabla u_0-\nabla u_1\|_{L^2(\rho)}^2\le\frac{12d}{h^2}\|u_0-u_1\|_{L^2(\rho)}^2+\frac{28L^2P_K}{|K|}\,h,@@`
取 `@@M@@h=W_2^{2/3}@@` 平衡两项得 `@@M@@1/3@@` 指数；再以有限 `@@M@@\varepsilon@@`-网逼近、Arzelà–Ascoli 紧性与 Fenchel 不等式验证延拓到一切 Borel 目标，顺带给出最优映射的存在唯一性。反例上势能差恰与 `@@M@@W_2@@` 成正比（系数 `@@M@@\sqrt5/4@@`），可见 `@@M@@1/3@@` 的损失全在"势能→梯度"一步。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。本结果族（374）目前仅此一篇手稿，但定理两半互相锁定：反例排除 `@@M@@1/3@@` 以上的全部指数，上界封住 `@@M@@1/3@@`，精确指数由此确定。证明对源只用凸性与紧性、对目标不加非退化条件，关键常数 `@@M@@162@@` 与 `@@M@@C_*@@` 显式可查，便于复核。

{% endraw %}
