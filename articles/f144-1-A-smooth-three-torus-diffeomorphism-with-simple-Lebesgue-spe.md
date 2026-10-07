---
layout: default
title: "A smooth three-torus diffeomorphism with simple Lebesgue spectrum"
family: "144"
discipline: "Dynamical systems and ergodic theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A smooth three-torus diffeomorphism with simple Lebesgue spectrum

> 结果族 144：Banach's simple Lebesgue-spectrum problem　·　学科：Dynamical systems and ergodic theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
本文在三维环面 `@@M@@\T^3@@` 上构造出保持标准体积的 `@@M@@C^\infty@@` 微分同胚（diffeomorphism）`@@M@@T@@` 及实观测函数 `@@M@@f@@`，使 `@@M@@\{f\circ T^n\}_{n\in\Z}@@` 恰为均值零空间 `@@M@@L^2_0@@` 的标准正交基，从而在光滑保测系统内解决了 Banach 简单 Lebesgue 谱问题的保概率形式。

## 问题背景
对保测变换（measure-preserving transformation）`@@M@@T@@`，Koopman 算子（Koopman operator）`@@M@@U_Tg=g\circ T@@` 把动力系统编码为酉算子，其谱是遍历论的核心不变量。最"混沌"的谱型是 Lebesgue 谱（Lebesgue spectrum）：算子西等价于 `@@M@@L^2(S^1)@@` 上的坐标乘法 `@@M@@w@@`。Banach 的问题（由 Ulam 1960 年的书记录）询问此类系统是否存在；Rokhlin（1949）进一步要求遍历自同构具有简单（simple）或至少有限重的 Lebesgue 谱。此前诸结果均未达此目标：Helson–Parry（1978）与 Mathew–Nadkarni（1984）只得到某些分量或二重分量；Fayad（2001）的光滑环面微分同胚有简单谱但非 Lebesgue 型；Prikhod'ko（2020）、Fayad–Forni–Kanigowski（2021）等是连续时间流，而简单 Lebesgue 流的非零时间映射只会产生可数无穷重的谱，给不出离散时间结论。真正的卡点在于：没有任何已知机制能让光滑、保标准体积的系统中一条双边轨道张满整个中心化空间。

## 主要结果
主定理（Theorem 1.1）：存在 `@@M@@C^\infty@@` 保体积微分同胚 `@@M@@T\colon\T^3\to\T^3@@`（不变测度就是标准体积 `@@M@@\mu@@`）与实函数 `@@M@@f\in L^2_0(\T^3,\mu)@@`，使 `@@M@@\{f\circ T^n:n\in\Z\}@@` 构成 `@@M@@L^2_0(\T^3,\mu)@@` 的标准正交基（orthonormal basis）。等价地，`@@M@@U_T@@` 在整个均值零空间上西等价于 `@@M@@L^2(S^1,m)@@` 上的乘法算子 `@@M@@w@@`：谱型与重数同时被控制。注意 `@@M@@f@@` 只需属于 `@@M@@L^2@@`，不必光滑。推论（Corollary 6.1）：`@@M@@T@@` 任意阶混合（mixing of all orders，其中 3 阶以上引用姊妹篇的多重混合定理）、Kolmogorov–Sinai 熵 `@@M@@h_\mu(T)=0@@`、三个 Lyapunov 指数（Lyapunov exponents）几乎处处全为零。

## 证明思路
构造沿 Anosov–Katok 式逐次逼近展开，但用显式的保体积"通道"（passage）而非外部共轭定理。先取可积扭转（integrable twist）`@@M@@S(\theta,u,a)=(\theta+\phi(u),u,a)@@` 为中间系统，观测量写成"包"（packet）`@@M@@A(u,a)\ee(m\theta)@@` 的有限和并按颜色（color）分组；单个包的谱测度是 `@@M@@|A|^2\,\dd u\,\dd a@@` 在 `@@M@@m\phi\bmod 1@@` 下的推前（pushforward），故谱密度光滑。目标是让一个向量的平移"读出"每组的标签 `@@M@@b_r@@`。

第一步是通道引理：坐标慢速轮换后新扭转的速度为 `@@M@@\sigma_N(a)=N^{-1}+N^{-2}J(a)@@`，其中 `@@M@@J@@` 实现"抖动"（jitter）定律；对相位 `@@M@@mH_N(u)-ju@@` 用驻相法（stationary phase）逐项算出新包与精细尺度的谱密度，而给 `@@M@@\phi@@` 的提升加大整数 `@@M@@c@@` 使不同包的角度指标彻底分离。第二步构造信号：用平方 sinc 平均给出严格正的基定律，配以模 `@@M@@P@@` 的素数筛（`@@M@@P@@` 为不超过 `@@M@@L@@` 的素数之积，筛除全部高次谐波），使每色谱密度获得微弱正弦偏置 `@@M@@1+2\lambda\operatorname{Re}\{d_r(z)\ee(-Nz)\}@@`——系数由包的规范化角度指标读出，强度 `@@M@@\lambda@@` 可任意小且与尺度无关；"中性"通道则先让各剩余类均分每色质量。第三步是核心的有限预测（Proposition 4.1）：把许多微弱偏置组成块，块内固定中心函数 `@@M@@q@@` 逼近密度加权平均 `@@M@@\beta(z)=\sum_r b_r p_r(z)/p(z)@@`。估计量 `@@M@@D=q+(n\lambda)^{-1}\sum_i\ee(L_iz)@@` 在倾斜密度下对标签 `@@M@@b_r@@` 无偏，均方误差 `@@M@@O(1/\delta)@@`；而由不等式 `@@M@@\sqrt{x}\ge 1+(x-1)/2-(x-1)^2@@`，每块 `@@M@@\int\sqrt p@@` 的损失仅 `@@M@@O(\delta^2)@@`（预算取 `@@M@@\delta/2\le n\lambda^2\le\delta@@`）。叠 `@@M@@K@@` 块后误差 `@@M@@O((K\delta)^{-1})@@`、总损失 `@@M@@O(K\delta^2)@@`：先取小 `@@M@@\delta@@` 再取大 `@@M@@K@@`，两者同时达标；"相位检验"引理（本质是 `@@M@@L^1@@` 傅里叶系数趋于零）把高维环面平均转移到对角频率。最后（第 5 节）把任意观测 `@@M@@h@@` 打包成带标签的矩形颜色，经预测后用"漂白"（whitening）`@@M@@f'=(\1_{E^c}/\sqrt p)(U)G+\1_E(U)v@@` 把谱密度精确恢复为 1；对稠密测试族 `@@M@@(h_n)@@` 逐阶段归纳，容差取 `@@M@@2^{-n}@@`、弧余集取 `@@M@@4^{-n}@@`，取光滑极限得 `@@M@@T@@` 与 `@@M@@f@@`：每阶段密度恰为 1 保证极限轨道标准正交，弧余集几何缩小使每个测试进入轨道闭包，稠密性即得 `@@M@@L^2_0@@` 上的完备性。

## 可信度与备注
据任务元数据，本篇主结果暂无 Lean 形式化证明，请以社区核验为准（家族描述中的 Lean 链接是族级信息，非本篇已验证）。主定理与遍历性的证明自足；任意阶混合推论额外引用同族姊妹篇的多重混合定理，而零熵与 Lyapunov 指数全零只依赖主定理（经 Rokhlin 有限重熵定理与 Pesin–Mañé 公式）。按 OpenAI 官方声明，未经形式化的结果可能存在问题，阅读时宜以原文与后续社区核验为准。

{% endraw %}
