---
layout: default
title: "A Pivotal Amplitude for Voronoi Percolation from Cardy's Formula"
family: "224"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Pivotal Amplitude for Voronoi Percolation from Cardy's Formula

> 结果族 224：Critical and quenched near-critical universality for Poisson–Voronoi percolation　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在 Cardy 公式的前提下，本文证明 Voronoi 渗流单位方块跨越的期望颜色 pivotal 数有精确渐近 `@@M@@\mathbb{E}N_\varepsilon\sim c_V\varepsilon^{-3/4}@@`（`@@M@@c_V\in(0,\infty)@@`），把近临界理论的归一化尺度确定为带正常数的纯幂律，且全程不需要 Cardy 公式的任何收敛速率。

## 问题背景

三角格点临界渗流的交替四臂指数（four-arm exponent）为 `@@M@@5/4@@`，于是微观尺度 `@@M@@\varepsilon@@` 下 pivotal 位点数的自然标度是 `@@M@@\varepsilon^{-2}\cdot\varepsilon^{5/4}=\varepsilon^{-3/4}@@`。但指数级估计 `@@M@@\varepsilon^{-3/4+o(1)}@@` 允许缓慢变化甚至振荡的乘法修正；要得到振幅（amplitude，即严格的极限常数）必须另辟蹊径——三角格点情形由 Du–Gao–Li–Zhuang 的精确臂概率渐近解决。对 Voronoi 渗流，同族姊妹篇已从标量 Cardy 假设推出整套淬火近临界理论，但其归一化始终由"期望 pivotal 计数"自身定义，是否为几何网格的纯幂并不自知。本文的任务就是证明：这个归一化其实是欧氏网格的纯幂，系数为正。

## 主要结果

在标量 Cardy 极限假设（每个有界 Jordan 四边形的临界跨越概率收敛到 Cardy 共形值，不含任何速率）下，存在常数 `@@M@@c_V\in(0,\infty)@@`，使得当泊松点强度为 `@@M@@\varepsilon^{-2}@@` 时，单位方块黑跨越的颜色 pivotal（color-pivotal）核点数 `@@M@@N_\varepsilon@@`（含胞与方块相交的外部核点，期望同时平均几何与颜色）满足 `@@M@@\lim_{\varepsilon\downarrow0}\varepsilon^{3/4}\mathbb{E}N_\varepsilon=c_V@@`，等价地逆期望 pivotal 数 `@@M@@\sim c_V^{-1}\varepsilon^{3/4}@@`。常数依赖指定的方块、跨越事件、强度约定与计数方式；定理是条件性的，不证明 Cardy 公式本身。

## 证明思路

证明分三个阶段，核心机制发生在环域（annulus）上。第一阶段构造环域传输极限并建立两条关键估计。连接状态（connection state）记录环域两侧哪些边界色段经由内部相连，等价于界面间的非交叉配对；比较两侧的连接状态差，除非至少四条界面穿过环域，传输差为零；恰有四条幸存界面时，两侧可能的内部状态只差一个标量——这就是长环域传输"秩一（rank-one）逼近"的来源。更强的一条估计利用对称性：添加一个公平染色的泊松点所产生的带符号变化在颜色反转与旋转下不变，在此对称类中首阶四界面贡献相消，显式谱计算表明剩余传输衰减快于环域尺度比的平方之逆。这个阈值是命门：插入点遍历二维平面，插入效应必须关于位置可积，而指数 `@@M@@5/4@@` 的无符号四臂界恰恰给不出这种可积性。第二阶段（transfer）把上述估计对任意带符号边界数据一致化，并在离散泊松模型中迭代。第三阶段对泊松强度求导：在单位强度下设 `@@M@@f(R)@@` 为原点插入一点后在放大矩形 `@@M@@RQ_0@@` 中成为颜色 pivotal 的概率，姊妹篇的输入给出 `@@M@@f(R)=R^{-5/4+o(1)}@@`，故只须证明 `@@M@@R^{5/4}f(R)@@` 有正极限。强度微分恒等式 `@@M@@\frac{R}{2}f'(R)=\int_{\mathbb{R}^2}K_R(y)\,dy@@` 把 `@@M@@f@@` 的对数导数表为插入差核 `@@M@@K_R@@` 的积分：远处插入由可积的符号插入估计控制，近处插入由秩一估计在两个外尺度下比较其归一化效应，两者合并给出对数导数与 `@@M@@-5/4@@` 之差可求和，从而 `@@M@@R^{5/4}f(R)@@` 收敛到正极限。值得强调的是，所有定量估计都不依赖 Cardy 假设的收敛速率：先取大而固定的环域比，用定性收敛在足够大的起始尺度之后获得所需的压缩性，然后才进行迭代。

## 可信度与备注

主结果未形式化。本文站在同族两篇姊妹成果之上：Cardy 公式提供假设输入，淬火近临界理论提供 `@@M@@f(R)=R^{-5/4+o(1)}@@` 等 pivotal 标度估计；三角格点上 Du–Gao–Li–Zhuang 的臂振幅定理是其格点类比。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
