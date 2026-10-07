---
layout: default
title: "Velocity-Field Detection of Computation in Forced Navier–Stokes Flows"
family: "376"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Velocity-Field Detection of Computation in Forced Navier–Stokes Flows

> 结果族 376：Universal computation in forced Navier–Stokes flows　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
在平坦三维区域上为从静止出发、粘性 `@@M@@\nu>0@@` 固定的不可压 Navier–Stokes 流构造光滑外力，使得只看速度场的固定检验——环面某带内 `@@M@@u_3>\tfrac12@@`，或 `@@M@@\mathbb R^2\times\mathbb T@@` 上半平面积分 `@@M@@>\tfrac12@@`——恰好等价于给定图灵机停机；由此这类速度事件不可判定。

## 问题背景

"流体能否计算"此前有两条主线：Cardona、Miranda、Peralta-Salas 与 Presas（2021）在选定黎曼度量的三维球上用定常 Euler 流让示踪粒子读取计算；Dyhr 等人（2026）在适配流形上构造无外力的定常 Navier–Stokes 场。这些结果的观测者都是拉格朗日式的：跟随一个物质粒子（material particle），且几何是被定制的。本文提出更苛刻的欧拉式（Eulerian）观测：不跟踪任何粒子，只在固定位置检测演化中的速度场本身；几何固定为平坦环面 `@@M@@\mathbb T^3@@` 或柱面 `@@M@@\mathbb R^2\times\mathbb T@@`，粘性固定且可计算，初速度为零，机器与输入只进入外力。难点是双重的：速度分量携带的信息会被粘性扩散抹平，而不可压流搬运信息时又必须保持面积。Turing（1936）的符号打印不可判定性提供最终的逻辑阻碍。

## 主要结果

主定理：对每个正的可计算 `@@M@@\nu@@`，任给确定性图灵机与有限输入，可有效地决定下列两个外力之一，使其在指定的经典比较类中有唯一整体光滑解（压力为零）。

（1）在 `@@M@@\mathbb T^3@@` 上，事件
`@@M@@D\exists t\ge0,\ \exists(x,y,z):\ 1/32<y<1/8,\quad u_3(t,x,y,z)>\tfrac12@@`
成立当且仅当机器停机；外力的水平支集含于与时间无关的紧集 `@@M@@K\times\mathbb T@@`（`@@M@@K\subset(0,1)^2@@`）。

（2）在 `@@M@@\mathbb R^2\times\mathbb T@@` 上，外力及其全部混合导数全局有界（每个有限时段内水平支集紧），事件
`@@M@@D\exists t\ge0:\ \int_{\{X_2>0\}\times\mathbb T}u_3\,\mathrm dX\,\mathrm dz>\tfrac12@@`
成立当且仅当停机。

两个检验的区域与阈值 `@@M@@\tfrac12@@` 均与机器、输入无关。推论：不存在算法能对本构造产生的每个外力描述判定上述固定速度事件，否则即可判定停机问题。外力无需无散或零均值。

## 证明思路

先做"三角化"降维。对二维无散场 `@@M@@a(t,Y)@@` 与标量源 `@@M@@h@@`，令 `@@M@@F=\partial_ta+(a\cdot\nabla_Y)a-\nu\Delta_Ya@@`、`@@M@@f=(F,h)@@`，则 `@@M@@u=(a,w)@@`、`@@M@@p=0@@` 满足方程，其中竖向分量 `@@M@@w@@` 解对流–扩散方程（advection–diffusion equation）`@@M@@\partial_tw+a\cdot\nabla_Yw=\nu\Delta_Yw+h@@`、`@@M@@w(0)=0@@`。速度场检验于是化为标量检验，外力公式完全显式、不含未知解；唯一性由经典的差能量比较（Leray 型）配合截断取极限给出。

环面构造采用"注入–搅动–等待"分块（injection, stirring and waiting）。平面哈密顿处理器 `@@M@@V@@`（由姊妹篇的编译器定理供给）在整数相位执行可逆化的机器：停机时轨道于某整数相位进入目标带 `@@M@@E=\{1/32<y<1/8\}@@`，不停机时整条轨道与 `@@M@@E@@` 的距离至少 `@@M@@2d@@`。第 `@@M@@n@@` 块先在初始码处注入高度为 1、宽度 `@@M@@b_n=10^{-6}(2R)^{-n}@@` 的窄 bump，总质量 `@@M@@M_0<10^{-11}@@`；再在极短时段 `@@M@@\delta_n@@` 内快放 `@@M@@V@@` 的 `@@M@@n@@` 个周期，时间压缩把扩散误差压到 `@@M@@2\delta_nD_n<1/50@@`，其中 `@@M@@D_n@@` 由流的一、二阶变分估计界定；随后等待超过一个单位热时间，让旧注入按热核上界 `@@M@@H@@` 均匀变小。停机时新鲜 bump 被精确搬运到检测带上，`@@M@@w>15/16>1/2@@`；不停机时 bump 支集与 `@@M@@E@@` 距离至少 `@@M@@d@@`，旧贡献不超过 `@@M@@HM_0@@`，误差至多 `@@M@@1/16@@`，合计严格小于 `@@M@@1/2@@`，且对所有物理时刻成立，不存在过渡期的假检测。

柱面构造改用"以空间换有界"。把带子编码为整数栈 `@@M@@(x,y)@@`（基数 `@@M@@b@@`），第 `@@M@@n@@` 层有 `@@M@@K_n=NB_n^2@@` 个地址；水平无散场为一切已定义的单步转移同时安装平移门（translation gate）`@@M@@W=\nabla^\perp[\chi(\xi/R_n)(G_1\xi_2-G_2\xi_1)]@@`，门在半径 `@@M@@R_n@@` 内恰为所需平移（平台性质）。半径 `@@M@@R_n=R_0\Lambda^n@@` 与时段 `@@M@@T_n@@` 的几何增长吸收地址数的增长，使 `@@M@@f@@` 的每个混合导数一致有界。初始的单位竖向脉冲产生质量为 1 的标量 `@@M@@\rho@@`；跟随所选计算的移动截断（moving cutoff）`@@M@@\varphi_R(X-c(t))@@` 经分部积分给出扩散损失率不超过 `@@M@@\nu C_*R^{-2}@@`，尺度选取使累计逃逸质量 `@@M@@\delta<1/24@@`。终态地址位于正高度行 `@@M@@S_n@@`，故停机时半平面积分超过 `@@M@@3/4@@`；不停机时轨道始终留在负行，积分不超过 `@@M@@\delta@@`。两个方向以严格余量分开，且解的构造从不执行机器——力只安装全部局部转移，由解本身完成计算。

## 可信度与备注

本文主结果未形式化，请以社区核验为准（族元数据提及配套 Lean 文档页，但本篇标记为未形式化）。族内三篇互相咬合：本文的平面处理器与单头编译器直接引自姊妹篇《Scalar Potentials and Slow Clocks for Forced Fluid Computation》，而该篇的速度检测又显式回调本文的注入–搅动–等待定理。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
