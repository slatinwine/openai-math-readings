---
layout: default
title: "Bose–Einstein condensation at positive temperature in the dilute hard-sphere gas"
family: "267"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Bose–Einstein condensation at positive temperature in the dilute hard-sphere gas

> 结果族 267：Positive-temperature Bose–Einstein condensation and exact quantum depletion　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明三维稀薄硬球玻色气体在严格正温度下发生玻色–爱因斯坦凝聚：固定排除距离并取足够小的密度，存在与体积无关的正温度，使精确正则 Gibbs 态在热力学极限下凝聚体占比为正，且凝聚在常值轨道上。

## 问题背景

玻色–爱因斯坦凝聚（Bose–Einstein condensation）的统计根源是 Bose 与 Einstein 在 1920 年代对理想气体的计数；Penrose 与 Onsager 在 1956 年把相互作用体系的凝聚定义为一阶密度矩阵（one-particle density matrix）的宏观特征值。此后的严格凝聚定理大多限于某种耦合极限：Lieb–Seiringer 的束缚气体 Gross–Pitaevskii 极限、Deuchert–Seiringer–Yngvason 的正温 GP 标度结果（其散射长度按 \(L/N\) 消失）、或盒子尺寸随稀薄度增长的绑定极限。硬球气体的能量理论虽已完整到 Lee–Huang–Yang 阶，但能量不等于占据：盒子增大时单粒子动能谱隙趋于零，热力学能量无法对单一轨道的占据给出体积一致的下界。把排除距离、密度、温度三者全部固定而让体积任意增长、并对精确正则 Gibbs 态（canonical Gibbs state）证明凝聚，正是本文补上的空缺。

## 主要结果

在环面 \(\Lambda_L=(\mathbb R/L\mathbb Z)^3\) 上，硬球哈密顿量 \(H_{N,L,a}\) 由二次型 \(q[f]=\sum_{i=1}^N\int_{\Omega_{N,L,a}}|\nabla_i f|^2\) 定义，其中允许构型集 \(\Omega_{N,L,a}\) 要求任意两粒子距离超过排除距离 \(a\)，波函数满足 Dirichlet 边界且对称。正温度 \(T\) 的正则 Gibbs 态为 \(\Gamma_{N,L,T}=e^{-H_{N,L,a}/T}/\Tr e^{-H_{N,L,a}}\)，其一阶密度矩阵为 \(\gamma^{(1)}_{N,L,T}\)。主定理（Theorem 1.1）：对每个 \(a>0\) 存在 \(\rho_*(a)>0\)，使得对每个固定 \(0<\rho<\rho_*(a)\)，存在正温度 \(T(a,\rho)>0\)，满足

\[\liminf_{\substack{L\to\infty\\ N/L^3\to\rho}}\frac{\langle u_{0,L},\gamma^{(1)}_{N,L,T}u_{0,L}\rangle}{N}>0,\]

其中 \(u_{0,L}=L^{-3/2}\) 是常值轨道。平移不变性保证常值轨道是 \(\gamma^{(1)}\) 的特征向量，故这恰是 Penrose–Onsager 意义的凝聚。证明所得温度偏低，不用于定位相变点；其价值在于：只要气体参数 \(\rho a^3\) 足够小，温度就可以取正且与体积无关。

## 证明思路

整体策略是把零温硬球基态的短路径比较方法移植到正温度的混合态。先做尺度变换：取单位使每个单位格含 \(D\gg1\) 个粒子、硬核半径为 \(r=\alpha/D\)，在此证核心估计"占据占比 \(B_{\rm occ}\ge c_*\)"。第一步是关键恒等式：把 Gibbs 核经平方根 \(\Phi\) 分解，凝聚占比恰等于"两个因子共享同一浴构型 \(X'\) 与保留构型 \(W'\)、而标志粒子从 \(x\) 走到 \(y\)"的积分；再把 \(\Phi^2\) 实现为短 Brown 时段上中点构型与 \(W'\) 的联合律，其条件律是避开硬核的 Brown 桥（Brownian bridge）乘积测度。于是占据问题被转化为路径水平的比较问题。接着建立联合局域估计：用熵与能量双管齐下——相对熵不等式控制密度的对角变化，一族带一致框架界的规范化插入映射控制添加粒子的自由能代价，即使存在有界吸引场也成立；再对违规路径打标记、赋予辅助粒子种类并解除其硬核约束，经热半群迹估计与外幂（exterior powers）控制一切正迹幂，得到缺陷格点数目的指数联合界。几何比较分三层推进：桥估计表明多数格点含有大量标签，其路径能以一致正概率穿过任意邻格；分组并暴露组外路径后，可用随机路线（unpredictable paths）连接大量格点对，两条独立路线相遇的指数矩有界，绕障借助 Kesten 外边界连通性定理（Timár 形式）。最终比较：沿一条路线构造中点错位的两份路径构型，从两份中各删去一个不同的标志粒子，恰好留下同一浴中点与同一 \(W'\)，匹配重叠恒等式；对路线先平均再取密度的二阶矩，条件归一在两次路线相遇之外相消，使费用由相遇而非路线长度控制，格点估计把它压小，共同测度不等式对正比例的格点对给出正重叠。顺序至关重要：路径时长与组大小先于密度阈值固定，再让体积趋于无穷；最后一节换回物理单位，直接验证 \(T_{\rm phys}\) 与体积无关。

## 可信度与备注

本篇暂无形式化证明，结论以社区核验为准。论文是自足的：所需的桥估计、格点路线与测度比较论证均随文附证明；其起点是两篇姊妹工作——零温硬球基态凝聚论文提供确定性短路径比较机制，有界有限程排斥势的正温凝聚论文提供热轨迹与格点路线估计——本文把二者改造为对硬核正则 Gibbs 态一阶密度矩阵的控制。同族两篇零温损耗论文与本篇共享尺度设置与路线技术，互相支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
