---
layout: default
title: "A torsion-free counterexample to the Kadison–Kaplansky projection conjecture"
family: "285"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A torsion-free counterexample to the Kadison–Kaplansky projection conjecture

> 结果族 285：Counterexamples to Baum–Connes and Kadison–Kaplansky　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造了一个有限生成无挠群 `@@M@@G_{\mathrm{proj}}@@`，其约化群 `@@M@@C^*@@`-代数中有投影 `@@M@@e@@` 满足 `@@M@@0<\tau(e)<\tfrac12@@`，既非零也非单位元——Kadison–Kaplansky 投影猜想由此被否定。

## 问题背景

Kadison–Kaplansky 投影猜想断言：无挠离散群 `@@M@@H@@` 的约化群 `@@M@@C^*@@`-代数 `@@M@@C_r^*(H)@@`（左正则群代数的算子范数闭包）不含 `@@M@@0@@` 与 `@@M@@1@@` 之外的投影（projection）。问题可溯至 Kaplansky 关于单 `@@M@@C^*@@`-代数幂等元的提问；Pimsner–Voiculescu 通过计算自由群约化交叉积的 `@@M@@K@@`-理论证明了自由群情形。一条主路线是积分性：若典范迹 `@@M@@\tau_H@@` 在 `@@M@@K_0@@` 上取整值则必无投影，而对无挠群，Lück 证明迹在装配像上整值，故 Baum–Connes 满射蕴含无投影。这解释了猜想为何对顺群（Higson–Kasparov）与双曲群（Mineyev–Yu、Lafforgue）成立，也意味着反例必须出自装配失效、几何全新的群。此前 Austin 曾造出无理 von Neumann 核维数，但核投影未必落在 `@@M@@C^*@@`-代数里；本文靠"一致分离谱带＋连续泛函演算"跨过这道门槛。

## 主要结果

**定理**：存在有限生成无挠离散群 `@@M@@G_{\mathrm{proj}}@@` 与投影 `@@M@@e\in C_r^*(G_{\mathrm{proj}})@@`，使 `@@M@@0<\tau_{G_{\mathrm{proj}}}(e)<\tfrac12@@`；特别地 `@@M@@e\ne0,1@@`。群由无限图形呈现再与有限生成自由群作自由积得到，所有参数有限（不寻求规模界），标记表与边电压由有限分布经"同时存在"命题选取。附带两个推论：非整迹把矩阵投影类 `@@M@@[p_0]@@` 排除出 `@@M@@G_{\mathrm{base}}@@` 的无系数约化装配像；同伴论文另证 `@@M@@\mathbb C[G_{\mathrm{proj}}]@@` 无非平凡幂等元，故 `@@M@@e@@` 属于完备化而不属于群环本身。

## 证明思路

分两步走：先造一个未归一化迹严格介于 `@@M@@0@@` 与 `@@M@@1/2@@` 的矩阵投影（矩阵目标），再用自由积把它压缩成标量投影。

矩阵目标要"分离谱带与小迹兼得"。先造二部塔：层 `@@M@@A_i,B_i@@`（`@@M@@i\in\mathbb Z@@`）只在相邻层间有二部关联，归一化关联算子把常向量映为常向量、在正交补上以 `@@M@@\rho<1@@` 收缩。塔备两份：`@@M@@Y^0@@` 供扩张、`@@M@@Y^\#@@` 供长路的有限字母恢复，删去一致小比例顶点后二者一致；幸存图 `@@M@@Y@@` 上作电压覆盖 `@@M@@P@@`。电压群取整上单位三角矩阵群的仿射扩张再取中心积所得的可数幂零群 `@@M@@F@@`，它一身二任：闭路上读出的短 holonomy 字（和乐字）经 Magnus 展开的矩阵截断检测，保证呈现的大围长与无挠；其中心 Fourier 纤维上又有 Schwartz 卷积幂等元（Rieffel 式核实现），加权的 Riemann 和格点化给出离散扭曲投影 `@@M@@p_\theta@@`，迹 `@@M@@\le C|\theta|^{n_{\mathrm f}}@@`。以中心 Fourier 变量 `@@M@@t@@` 为参数，两因子的有效扭曲分别是 `@@M@@t@@` 与 `@@M@@t-\delta@@`（后者靠一个 `@@M@@N@@` 维有限磁表示吸收，模 `@@M@@q@@` 约化使其在格上平凡），故 `@@M@@0<t<\delta@@` 时纤维投影非零且迹 `@@M@@\le CNt^{n_{\mathrm f}}(\delta-t)^{n_{\mathrm f}}@@`：`@@M@@t@@` 趋向任一端点时支撑层都逃向塔的一端，迹在两端同时变小。相邻层常向量的归一化组合给出特征值 `@@M@@+1@@`，扩张性分离其余正谱。几何侧用公共根排序把每个 copy 与更早 copy 的交限制进一个有限树球，删去后剩互斥域、其余 Cayley 边成森林；删球损失由迹估计控制，森林范数估计控制剩余边，分离谱带遂保持到有限矩阵 `@@M@@T\in M_N(\mathbb C[G_{\mathrm{base}}])@@`，连续泛函演算给出上投影 `@@M@@p_0@@`。

标量压缩则是干净的一步：取 `@@M@@G_{\mathrm{proj}}=G_{\mathrm{base}}*\mathbb F_N@@`，令 `@@M@@U=(\lambda(t_1),\dots,\lambda(t_N))@@` 为自由生成元的行算子，则
`@@M@@De=(Up_0)\,(p_0U^*Up_0)^{-1}\,(Up_0)^*\in C_r^*(G_{\mathrm{proj}})@@`
是标量投影且 `@@M@@\tau(e)=\tau_{G_{\mathrm{base}},N}(p_0)@@`。关键下界 `@@M@@\|U\xi\|\ge c_a\|\xi\|@@` 用自由积正规形把"坏位置"的电荷全部记到迹 `@@M@@a<1/2@@` 的账上；自由积保持有限生成与无挠。

## 可信度与备注

本文暂无形式化证明，论证横跨图形小消去、幂零群调和分析与自由积迹估计，核验成本高。族内姊妹篇分别破装配的单射与满射，本篇的非平凡投影正是满射失效的直接表征。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
