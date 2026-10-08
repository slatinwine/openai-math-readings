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

## 入门导读 🐣

低温下的齐舞：温度够低时，气体里的粒子不再各自即兴，而是一大部分同步踏进同一个"标准舞步"。这就是玻色–爱因斯坦凝聚。这篇论文首次严格证明：对固定的硬球气体和足够稀薄的密度，存在一个与容器大小无关的正温度，让这种齐舞在精确的统计平衡态中必然发生。

**关键词卡片**

- 玻色–爱因斯坦凝聚（Bose–Einstein condensation）：宏观比例的粒子占据同一个单粒子量子态。
- 硬球势（hard-sphere potential）：粒子是刚体小球，两两中心距离不得小于 a。
- 正则 Gibbs 态（canonical Gibbs state）：温度 T 下的量子统计平衡态 `@@M@@e^{-H/T}/\mathrm{Tr}\,e^{-H/T}@@`。
- 热力学极限（thermodynamic limit）：粒子数与容器体积同时趋于无穷，密度 ρ 固定。
- 一阶密度矩阵（one-particle density matrix）：描述"平均每个粒子处在什么态"的算符。

**看个具体例子**

定理的数字版：`@@M@@\liminf \frac{\langle u_0,\gamma^{(1)}u_0\rangle}{N}>0@@`，其中 `@@M@@u_0=L^{-3/2}@@` 是常值波。取 `@@M@@N=10^6@@` 个粒子：无论盒子多大，至少有某个与体积无关的固定比例——至少几万、几十万个粒子——挤在同一个波上；在动量图上，这表现为 `@@M@@k=0@@` 处的巨型尖峰。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="40" y="30" font-size="14">动量空间占据数 n(k)：k=0 处的巨型尖峰 = 凝聚体</text>
  <line x1="90" y1="230" x2="510" y2="230" stroke="#333" stroke-width="1.5"/>
  <line x1="90" y1="230" x2="90" y2="55" stroke="#333" stroke-width="1.5"/>
  <path d="M 110 208 Q 300 186 490 208" fill="none" stroke="#4a7ebb" stroke-width="2"/>
  <polygon points="288,207 300,80 312,207" fill="#f2d5cf" stroke="#b3442e" stroke-width="2"/>
  <text x="316" y="95" font-size="13" fill="#b3442e">凝聚体：宏观比例的粒子</text>
  <text x="316" y="180" font-size="13" fill="#4a7ebb">热激发粒子（少量）</text>
  <text x="280" y="252" font-size="13">k = 0</text>
  <text x="440" y="252" font-size="13">动量 k →</text>
  <text x="48" y="70" font-size="13">n(k)</text>
</svg>

</div>

**为什么值得关心**

以往的严格正温凝聚定理都要借助某种"耦合极限"（比如让相互作用随容器一起缩小）；本文把排除距离、密度、温度三者固定，只让体积增大——教科书式的设定第一次被拿下。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明三维稀薄硬球玻色气体在严格正温度下发生玻色–爱因斯坦凝聚：固定排除距离并取足够小的密度，存在与体积无关的正温度，使精确正则 Gibbs 态在热力学极限下凝聚体占比为正，且凝聚在常值轨道上。

## 问题背景

玻色–爱因斯坦凝聚（Bose–Einstein condensation）的统计根源是 Bose 与 Einstein 在 1920 年代对理想气体的计数；Penrose 与 Onsager 在 1956 年把相互作用体系的凝聚定义为一阶密度矩阵（one-particle density matrix）的宏观特征值。此后的严格凝聚定理大多限于某种耦合极限：Lieb–Seiringer 的束缚气体 Gross–Pitaevskii 极限、Deuchert–Seiringer–Yngvason 的正温 GP 标度结果（其散射长度按 `@@M@@L/N@@` 消失）、或盒子尺寸随稀薄度增长的绑定极限。硬球气体的能量理论虽已完整到 Lee–Huang–Yang 阶，但能量不等于占据：盒子增大时单粒子动能谱隙趋于零，热力学能量无法对单一轨道的占据给出体积一致的下界。把排除距离、密度、温度三者全部固定而让体积任意增长、并对精确正则 Gibbs 态（canonical Gibbs state）证明凝聚，正是本文补上的空缺。

## 主要结果

在环面 `@@M@@\Lambda_L=(\mathbb R/L\mathbb Z)^3@@` 上，硬球哈密顿量 `@@M@@H_{N,L,a}@@` 由二次型 `@@M@@q[f]=\sum_{i=1}^N\int_{\Omega_{N,L,a}}|\nabla_i f|^2@@` 定义，其中允许构型集 `@@M@@\Omega_{N,L,a}@@` 要求任意两粒子距离超过排除距离 `@@M@@a@@`，波函数满足 Dirichlet 边界且对称。正温度 `@@M@@T@@` 的正则 Gibbs 态为 `@@M@@\Gamma_{N,L,T}=e^{-H_{N,L,a}/T}/\Tr e^{-H_{N,L,a}}@@`，其一阶密度矩阵为 `@@M@@\gamma^{(1)}_{N,L,T}@@`。主定理（Theorem 1.1）：对每个 `@@M@@a>0@@` 存在 `@@M@@\rho_*(a)>0@@`，使得对每个固定 `@@M@@0<\rho<\rho_*(a)@@`，存在正温度 `@@M@@T(a,\rho)>0@@`，满足

`@@M@@D\liminf_{\substack{L\to\infty\\ N/L^3\to\rho}}\frac{\langle u_{0,L},\gamma^{(1)}_{N,L,T}u_{0,L}\rangle}{N}>0,@@`

其中 `@@M@@u_{0,L}=L^{-3/2}@@` 是常值轨道。平移不变性保证常值轨道是 `@@M@@\gamma^{(1)}@@` 的特征向量，故这恰是 Penrose–Onsager 意义的凝聚。证明所得温度偏低，不用于定位相变点；其价值在于：只要气体参数 `@@M@@\rho a^3@@` 足够小，温度就可以取正且与体积无关。

## 证明思路

整体策略是把零温硬球基态的短路径比较方法移植到正温度的混合态。先做尺度变换：取单位使每个单位格含 `@@M@@D\gg1@@` 个粒子、硬核半径为 `@@M@@r=\alpha/D@@`，在此证核心估计"占据占比 `@@M@@B_{\rm occ}\ge c_*@@`"。第一步是关键恒等式：把 Gibbs 核经平方根 `@@M@@\Phi@@` 分解，凝聚占比恰等于"两个因子共享同一浴构型 `@@M@@X'@@` 与保留构型 `@@M@@W'@@`、而标志粒子从 `@@M@@x@@` 走到 `@@M@@y@@`"的积分；再把 `@@M@@\Phi^2@@` 实现为短 Brown 时段上中点构型与 `@@M@@W'@@` 的联合律，其条件律是避开硬核的 Brown 桥（Brownian bridge）乘积测度。于是占据问题被转化为路径水平的比较问题。接着建立联合局域估计：用熵与能量双管齐下——相对熵不等式控制密度的对角变化，一族带一致框架界的规范化插入映射控制添加粒子的自由能代价，即使存在有界吸引场也成立；再对违规路径打标记、赋予辅助粒子种类并解除其硬核约束，经热半群迹估计与外幂（exterior powers）控制一切正迹幂，得到缺陷格点数目的指数联合界。几何比较分三层推进：桥估计表明多数格点含有大量标签，其路径能以一致正概率穿过任意邻格；分组并暴露组外路径后，可用随机路线（unpredictable paths）连接大量格点对，两条独立路线相遇的指数矩有界，绕障借助 Kesten 外边界连通性定理（Timár 形式）。最终比较：沿一条路线构造中点错位的两份路径构型，从两份中各删去一个不同的标志粒子，恰好留下同一浴中点与同一 `@@M@@W'@@`，匹配重叠恒等式；对路线先平均再取密度的二阶矩，条件归一在两次路线相遇之外相消，使费用由相遇而非路线长度控制，格点估计把它压小，共同测度不等式对正比例的格点对给出正重叠。顺序至关重要：路径时长与组大小先于密度阈值固定，再让体积趋于无穷；最后一节换回物理单位，直接验证 `@@M@@T_{\rm phys}@@` 与体积无关。

## 可信度与备注

本篇暂无形式化证明，结论以社区核验为准。论文是自足的：所需的桥估计、格点路线与测度比较论证均随文附证明；其起点是两篇姊妹工作——零温硬球基态凝聚论文提供确定性短路径比较机制，有界有限程排斥势的正温凝聚论文提供热轨迹与格点路线估计——本文把二者改造为对硬核正则 Gibbs 态一阶密度矩阵的控制。同族两篇零温损耗论文与本篇共享尺度设置与路线技术，互相支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
