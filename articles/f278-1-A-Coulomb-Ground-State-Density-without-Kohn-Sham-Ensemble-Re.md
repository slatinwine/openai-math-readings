---
layout: default
title: "A Coulomb ground-state density without Kohn-Sham ensemble representation"
family: "278"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Coulomb ground-state density without Kohn-Sham ensemble representation

> 结果族 278：Failure of Kohn–Sham ensemble representation　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文严格构造了一个有限的三电子库仑分子（两个核电荷为相等的正整数 `@@M@@Z@@`），并证明其绝对基态密度无法由任何单个实、自旋无关的 `@@M@@L^{3/2}(\mathbb R^3)+L^\infty(\mathbb R^3)@@` 局域势下无相互作用电子的基态系综重现，从而在该势类中否定了 Kohn–Sham 系综可表示性。

## 问题背景

密度泛函理论（density functional theory）的变分框架始于 1964 年 Hohenberg 与 Kohn 的工作；次年 Kohn 与 Sham 提出用无相互作用电子在公共局域势中重现真实相互作用电子的基态密度，这成为现代电子结构计算的基石。随之而来的核心问题是 `@@M@@v@@`-可表示性（v-representability）：相互作用体系的基态密度是否总能由某个局域势的无相互作用基态——乃至允许混合简并基态的系综（ensemble）——产生？Levy 与 Lieb 的约束搜索（constrained search）表明"存在具有给定密度的态"与"存在使该密度能量极小的势"是两个问题，而允许系综会扩大后一类。此前，Wagner 等人给出的是人为直接指定的密度反例（内部尖点迫使逆势跑出势类），Trushin–Erhard–Görling 给出的只是原子密度反演的数值证据；而格点、一维区间与圆环上的可表示性定理均不覆盖三维库仑体系。真正的卡点是：没有一个解析证明的、来自真实有限库仑分子基态的密度反例。

## 主要结果

主定理：取 `@@M@@D=10^{200}@@`、`@@M@@e_z=(0,0,1)@@`。存在有限正整数 `@@M@@Z@@`——由一个仅含谱数据、密度与二中心辅助问题角度极小化的精确非数值公式给出，不声明数值值或有效上界——使得核电荷 `@@M@@Z,Z@@` 位于 `@@M@@(0,0,\pm D/Z)@@` 的三电子库仑哈密顿量

`@@M@@DH_C=\sum_{i=1}^3\Big(-\frac12\Delta_i-\frac{Z}{|r_i-(D/Z)e_z|}-\frac{Z}{|r_i+(D/Z)e_z|}\Big)+\sum_{1\le i<j\le 3}\frac1{|r_i-r_j|}@@`

在 `@@M@@S_z=1/2@@` 自旋扇区有可归一化的绝对基态 `@@M@@\Psi@@`，但不存在实、自旋无关势 `@@M@@v\in L^{3/2}(\mathbb R^3)+L^\infty(\mathbb R^3)@@`，使非相互作用哈密顿量 `@@M@@H_s(v)=\sum_i(-\tfrac12\Delta_i+v(r_i))@@` 的任何基态系综 `@@M@@\Gamma@@`（迹为 1、值域含于基态本征空间的正迹类算子）的自旋求和密度满足 `@@M@@n_\Gamma=n_\Psi@@` 几乎处处成立。定理对表示基态空间的简并度与系综里的复自旋态均无限制；对分布势、自旋相关势或非局域单体算子不作断言。作为推论，同一密度还排除了用该势类中的势表示系综 Hartree–交换–关联泛函（Hartree–exchange–correlation functional）沿公共有限能量密度域内任一线段的一阶变分。

## 证明思路

先做标度与微扰准备。把长度除以 `@@M@@Z@@`，体系变为单位电荷两核位于 `@@M@@\pm De_z@@`、电子排斥系数 `@@M@@\lambda=1/Z@@` 的问题。`@@M@@D@@` 很大时双中心算子最低两个轨道是正的偶轨道 `@@M@@b@@` 与奇轨道 `@@M@@e@@`，能级差 `@@M@@d_*<100/D@@` 可任意小；零耦合时三电子基态行列式占据 `@@M@@b\uparrow,b\downarrow,e\uparrow@@`，经 Kato 解析微扰延拓到小 `@@M@@\lambda>0@@`，得到绝对基态与自旋求和密度 `@@M@@n@@`。

再证关键的中面渐近。直接移除振幅（基态向离子基态投影得到的 Dyson 轨道分量）带一个简单的奇角零点，在中面 `@@M@@z=0@@` 上严格消失；但互补离子通道经多极展开与逐阶递推，在中面上给出非零密度尾 `@@M@@\sqrt{n(p,0)}\ge c\,A(p)\,p^{-4}@@`，其中 `@@M@@k=\sqrt{2(E_2-E_3)}@@` 是电离速率、`@@M@@A(r)=e^{-kr}r^\beta@@`。中面上的密度与体区同指数衰减，只额外压低一个多项式因子——这正是 Gori-Giorgi–Gál–Baerends 提出的节点面机制，本文首次对有限库仑体系给出严格且对小耦合一致的证明；自旋正交性防止通道间抵消，使常数不依赖小能级差 `@@M@@d_*@@`。远处的平移极限是 `@@M@@a^2z^2e^{-2k\omega\cdot x}@@`：极限在平面上二次消失，而真实密度只剩较小的非零尾，这一反差驱动全部后续论证。

然后构造轨道并颁发"系综动能证书"。在奇角度类上极小化 `@@M@@\int n|\nabla\theta|^2@@`（约束 `@@M@@\int n\sin^2\theta=1@@`），得 `@@M@@g=\sqrt n\cos\theta@@`、`@@M@@h=\sqrt n\sin\theta@@`（范数平方 2 与 1，一偶一奇），它们满足公共形式势 `@@M@@V=\Delta g/(2g)@@` 的两个方程 `@@M@@(-\tfrac12\Delta+V)g=0@@`、`@@M@@(-\tfrac12\Delta+V)h=dh@@`（`@@M@@d>0@@`）。技术核心是加权谱隙，即加权 Poincaré 不等式（weighted Poincaré inequality）：外区用一维条带比较函数与具负加权散度的向量场，内区用零耦合极限的偶宇称谱隙加紧性反证。结合 Pauli 约束 `@@M@@0\le\gamma_\Gamma\le\mathrm{id}@@` 逐轨道求和，可证行列式 `@@M@@\Phi_\theta=(\hat g\uparrow)\wedge(\hat g\downarrow)\wedge(h\uparrow)@@` 在一切具密度 `@@M@@n@@` 的系综中动能最小；于是任何表示势的基态空间必含 `@@M@@\Phi_\theta@@`，进而 `@@M@@v=V+\text{常数}@@` 几乎处处——形式势是唯一候选。

最后导出矛盾。设 `@@M@@V\in L^{3/2}+L^\infty@@`，把势平移到无穷远：`@@M@@L^{3/2}@@` 部分局部趋零，`@@M@@L^\infty@@` 部分子列弱星收敛；将平移轨道方程与密度平移极限一并取极限（Harnack 不等式把一支逼为零，另一支被识别为纯指数），可得任何有界极限势必为常数 `@@M@@c_\infty=d+k^2/2@@`。由此得外部形式强制性，Agmon 指数权重法给出 `@@M@@e^{a|x|}g\in H^1(\mathbb R^3)@@`（某个 `@@M@@a>k@@`）；`@@M@@H^1@@` 迹（trace）限制到中面得 `@@M@@\int e^{2ap}\,n(p,0)\,dp<\infty@@`，但中面尾下界使该积分因 `@@M@@a>k@@` 发散——矛盾，故 `@@M@@V\notin L^{3/2}+L^\infty@@`。收尾：固定 `@@M@@D=10^{200}@@`，对辅助耦合 `@@M@@t@@` 定义有限个定量测试（能级孤立单重、密度正性、能量窗口、振幅下界、漂移界 `@@M@@\eta_0=10^{-60}@@`、角度余量 `@@M@@\alpha@@`），坏集为 `@@M@@\mathcal B@@`，则 `@@M@@Z=2+\lceil\sup_{0<t\le1}t^{-1}\mathbf 1_{\mathcal B}(t)\rceil@@` 有限且按构造 `@@M@@1/Z\notin\mathcal B@@`，恰好通过固定参数版定理的全部假设，最后用伸缩酉等价送回物理核电荷 `@@M@@Z,Z@@`。

## 可信度与备注

本文是 OpenAI 于 2026 年 9 月 25 日发布的预印本，主结果暂无 Lean 形式化证明，请以社区核验为准。结果族 278 在本批次仅此一篇手稿，无同族姊妹篇互证；其机制承接 Gori-Giorgi–Gál–Baerends 的渐近分析，并把 Trushin–Erhard–Görling 的数值反例线索转化为解析定理，与既有文献方向一致。依 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
