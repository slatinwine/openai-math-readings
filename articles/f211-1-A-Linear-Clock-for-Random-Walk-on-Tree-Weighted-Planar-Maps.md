---
layout: default
title: "A Linear Clock for Random Walk on Tree-Weighted Planar Maps"
family: "211"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Linear Clock for Random Walk on Tree-Weighted Planar Maps

> 结果族 211：The geometric phase diagram, diffusion, and spectra of random planar maps　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明了按生成树数目加权的平面地图上的平稳随机游走，在时间加速恰好 \(n\)（边数）倍后，其条件路径律连同度量-测度空间收敛到 \(\sqrt2\)-量子球上的刘维尔布朗运动，时钟乘子精确为 1。

## 问题背景
随机曲面的度量与面积极限并不自动决定曲面上的粒子运动：逼近图的电导（conductance）可以改变极限扩散，而时间归一化是否收敛到单一确定性线性时钟，是独立的难题。本文处理按生成树数目加权的平面地图——即地图带均匀生成树装饰的 Mullin–Bernardi 情形，本族概述将其与 FK–Ising 并列为已证明扩散收敛的两个模型。其几何前提（等值线重构理论与度量-测度极限）已由姊妹篇给出，本文补上电网络能量识别与速度测度（speed measure）控制两块拼图，证明这种分离式策略恰好可行，因为两部分都不能单独由度量-测度收敛推出。

## 主要结果
\((M_n,T_n)\) 均匀取自 \(n\) 条边、带一棵生成树的有根平面多重图对，故地图边缘分布权重正比于其生成树个数。游走在速率 1 的泊松时钟驱动下等概率选取关联半边（half-edge）并移动到另一端点，环不产生位移；其平稳可逆分布为度测度 \(\mu_n=\sum_{v\in V_n}\frac{\deg(v)}{2n}\delta_v\)。连续极限是单位面积 \(\sqrt2\)-刘维尔量子引力（LQG）球 \((S,D_h,\mu_h)\)，其上扩散为狄利克雷型（Dirichlet form）\(\cE_h(f,g)=\frac12\int\langle\nabla f,\nabla g\rangle\dd\vol\) 在 \(L^2(\mu_h)\) 上闭包所对应的刘维尔布朗运动（Liouville Brownian motion）。主定理：在确定性直径归一化 \(a_n\) 下，四元组 \((V_n,a_nd_n,\mu_n,Q_n^T)\) 收敛到 \((S,D_h,\mu_h,Q_h^T)\)，其中 \(Q_n^T\) 是给定地图时加速路径 \((X^n_{nt})_{0\le t\le T}\) 的条件律，\(Q_h^T\) 是给定场 \(h\) 时 \(B^h\) 的条件律——即在曲线装饰的 Gromov–Hausdorff–Prokhorov 型拓扑下保留随机环境信息的淬火（quenched）联合收敛，时间加速常数 \(c=1\)。同一论证还给出任意固定条条件独立平稳游走的联合收敛，完整保留共享环境的信息。

## 证明思路
证明刻意把"能量识别"与"速度测度"分开。能量方面，先证非退化性：若环域极值长度（extremal length）可以坍缩到零，低能流会留下非零的平均长度测度极限；局部性与场芽（field germ）平凡性使典型点处同时出现横穿的原始与对偶穿越流，而任何这样一对都要经过一条边及其对偶边，与流量范数趋于零矛盾；由此得到有界能量的截断函数与调和函数族的紧性。再识别能量：每个局部变分极限都形如 \(\lambda\int\abs{\nabla u}^2\)，且原始与对偶网络共享同一确定性正标量 \(\lambda\)；为定出 \(\lambda\)，把环域上的电容器与其旋转电流的周期相比较，一个方向给出 \(\lambda\le1\)，另一个方向借助角上同调（angular cochain）的恢复与原始–对偶带符号配对给出 \(\lambda\ge1\)，故 \(\lambda=1\)；继而通过内部游离密度把结果转移到固定面积球面，被略去的单个等值线端点因零索伯列夫容量（Sobolev capacity）而无影响。速度测度方面，关键是关于中心化逆图拉普拉斯的一致估计 \(\|G_nf\|_\infty\le A_n\,\mu_n(\abs f)^\rho\)（\(0<\rho<1/2\)，\(\sup_n\EE A_n<\infty\)），其证明完全是有限地图上的组合论证：生成森林恒等式把中心化逆表示为树割之和，等值线双射把每个割的大小表示为 1 加一个对偶树距离，再由 Dyck 游走（Dyck excursion）估计控制区间和。最后的动力学部分：上述格林界与能量收敛、调和紧性共同满足一个确定性收敛判据；预解式（resolvent）一致收敛配合 \(\alpha R_\alpha f\to f\) 的一致 Feller 型逼近，给出对一切起始顶点一致的出口时间估计，Aldous 判据给出紧性；平稳有限维分布经乘积拉普拉斯变换识别为极限扩散的对应量。时钟则由精确恒等式 \(-\langle f,nL_nf\rangle_{L^2(\mu_n)}=\frac12\en_n(f)\) 结合 \(\lambda=1\) 直接读出。

## 可信度与备注
主结果暂无形式化证明；依 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。本文与两篇 FK–Ising 姊妹篇结构平行（姊妹篇几何极限 + 本文能量与格林估计 + 路径收敛），验证了族 211 的方法跨模型可迁移；其格林估计可独立于能量识别单独使用，是可复用的技术输出。核验时应重点关注 \(\lambda=1\) 的双向比较论证与格林估计的组合部分。

{% endraw %}
