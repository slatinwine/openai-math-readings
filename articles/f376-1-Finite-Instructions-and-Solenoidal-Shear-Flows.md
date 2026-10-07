---
layout: default
title: "Finite Instructions and Solenoidal Shear Flows"
family: "376"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Finite Instructions and Solenoidal Shear Flows

> 结果族 376：Universal computation in forced Navier–Stokes flows　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在固定平坦环面、固定正粘度、零初速的强迫 Navier–Stokes 流中，本文给出一个终止的编译器，把任意图灵机与输入变成光滑、无散度、零均值的外力，使固定粒子在有限时刻进入固定开带当且仅当机器停机，从而该"固定粒子事件"不可判定。

## 问题背景

停机问题（halting problem）的不可判定性是计算的边界；能否让一个具体物理系统"演示"这一边界？Cardona–Miranda–Peralta-Salas–Presas 在适配的黎曼三球面上构造了模拟图灵机的定常欧拉流，Dyhr 等人又用 Hodge 粘性得到无外力定常 Navier–Stokes 的图灵完备性，但两者都要改动几何、且用非零初速。悬而未决的是：在固定平坦环面（flat torus）`@@M@@\T^3@@`、固定正粘度 `@@M@@\nu@@`、流体从静止出发的强迫体系里能否实现通用计算。障碍有二：机器指令可能抹除信息，而光滑流的有限时间映射必可逆；一条指令的源区域也可能与另一条指令的目标区域重叠。本文以"保留历史＋分层高度"逐一化解，给出一条从普通机器到流体的完整构造链。

## 主要结果

主定理（定理 1.1，initialized computation by a solenoidal force）：固定正的可计算粘度 `@@M@@\nu@@`，存在算法把带头移动限于 `@@M@@\{-1,0,1\}@@` 的单带确定图灵机 `@@M@@M@@` 与有限输入 `@@M@@w@@` 编译为有效光滑外力 `@@M@@f_{M,w}@@`，满足：(i) `@@M@@f_{M,w}@@` 无散度（solenoidal）且零空间均值，方程 `@@M@@u_t+(u\cdot\nabla)u=-\nabla p+\nu\Delta u+f@@`、`@@M@@u(0)=0@@` 有全局光滑解 `@@M@@(u,p)=(U,0)@@`——压强恒为零——且在古典类中唯一；(ii) `@@M@@U@@` 与 `@@M@@f_{M,w}@@` 的一切混合导数全局有界，动能一致有界，两场自 `@@M@@t\ge1@@` 起周期为一，周期机制只依赖 `@@M@@M@@`；(iii) 固定粒子标签 `@@M@@a_*=(1/8,3/8,1/2)@@` 在某有限时刻进入固定开带 `@@M@@O=\{(x,y,z):1/2<x<1\}@@`，当且仅当 `@@M@@M@@` 停机于 `@@M@@w@@`（含初始即停机的情形）。推论：对该编译器产出的一切力，无算法能判定固定粒子事件。

## 证明思路

构造分四步。第一步可逆化：仿照 Bennett 的可逆模拟（reversible simulation），设计七行转移表的单头记录器（recorder），其带符号 `@@M@@(a,\ell,m)@@` 同时携带工作符号、历史与返回标记；每执行一条原始指令，就把其编号抄写到不断右移的历史前沿上，第 `@@M@@n@@` 个检查点（checkpoint）精确代表原机第 `@@M@@n@@` 步后的构形，每步耗时 `@@M@@2(r_0+n-h')+4@@` 个微步，且该表在其整个定义域上可由"目标状态＋写下的符号"唯一回溯前驱。第二步位置编码：取 Moore 广义移位（generalized shifts）视角，把带头两侧的带子写成 `@@M@@B@@` 进制小数，状态方块按 `@@M@@x@@` 分置（非终态在 `@@M@@1/8\le x<3/16@@`，终态在 `@@M@@3/4\le x<13/16@@`），每条记录器指令化为互逆仿射映射（reciprocal affine map），线性部分为 `@@M@@\diag(\lambda_i,\lambda_i^{-1})@@`、`@@M@@\lambda_i=B^{-d_i}@@`；引理证明源矩形族与目标矩形族各自两两分离，但源与目标允许重叠。第三步剪切实现：七个时间上依次分离的脉冲完成"抬升—四剪切—平移—下降"：先把源矩形抬到该分支专属高度 `@@M@@z_i@@`，再用四个剪切 `@@M@@\mathsf Y(-\lambda),\ \mathsf X(\lambda^{-1}-1),\ \mathsf Y(1),\ \mathsf X(\lambda-1)@@` 精确实现 `@@M@@(r,s)\mapsto(\lambda r,s/\lambda)@@`，平移至目标中心后降回 `@@M@@z_0@@`。关键的偏移估计（excursion estimate）断言中间各坐标偏离不超过 `@@M@@2h@@` 且与 `@@M@@\lambda@@` 无关；每段速度都横向于自身变化的方向，故对流项（convective term）`@@M@@(V\cdot\nabla)V\equiv0@@`，压强恒为零，`@@M@@f=\partial_tV-\nu\Delta V@@` 自动无散度、零均值；源与目标的重叠因使用时刻不同、中间隔有专属高度而互不干扰。第四步装载与归纳：一次性装载流把 `@@M@@a_*@@` 沿两段直线送到有理的输入编码，此后周期机制重复；归纳证明每个微步粒子恰落在一个源矩形内并被送到正确的后继编码。不停机的运行始终处于非终态，全程 `@@M@@x\le 9/32<1/2@@`，绝不触发探测带；停机则在有限个周期后进入 `@@M@@x\ge3/4@@` 的终态方块。解的唯一性由 Leray 式能量比较（energy comparison）加 Gronwall 不等式得到。

## 可信度与备注

本文暂无形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。同族两篇姊妹篇分别以"普通机器＋第三坐标历史"和"可逆记录表＋空间时钟"独立实现同类事件等价，三篇共享"编译器→预设速度→残差力→能量法唯一性"的骨架，互为印证；本文独有的亮点是压强恒为零、外力无散度且初始化后周期。结论针对精确物质轨线（material trajectory）的可达性，编码使用精确实坐标，不含有限精度鲁棒性。

{% endraw %}
