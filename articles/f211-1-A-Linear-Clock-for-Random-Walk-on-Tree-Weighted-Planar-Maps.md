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

## 入门导读 🐣

换一种随机世界：地图不再按 Ising 规则加权，而是按"能长出多少棵生成树"计票——树越多的地图越常见。在这样抽出的地图上让醉汉走路，问老问题：录像要快进几倍才收敛？答案依旧干脆：恰好 `@@M@@n@@` 倍，极限是 `@@M@@\sqrt2@@`-量子球上的刘维尔布朗运动。两种材质不同的随机世界，调到同一个"`@@M@@\times n@@`"频道都很清晰。

**关键词卡片**

- 生成树（spanning tree）：连通全部顶点、不含环的一组边，地图的最小骨架。
- Mullin–Bernardi 模型：均匀抽取（地图，生成树）对，等价于地图按生成树数目加权。
- 淬火收敛（quenched convergence）：先固定随机环境、只看路径的收敛；本文连环境信息一并保留。
- 极值长度（extremal length）：共形不变的"电阻"式几何度量，用来排除电网退化。
- 速度测度（speed measure）：扩散在各点的局部时间流速，本文用格林函数估计加以控制。

**看个具体例子**

时钟由一条精确恒等式直接读出（数字版定理）：

`@@M@@D-\langle f,\,nL_nf\rangle_{L^2(\mu_n)}=\tfrac12\,\mathcal E_n(f)\quad\Longrightarrow\quad\text{时间加速常数}=1.@@`

即 `@@M@@n@@` 条边就加速恰 `@@M@@n@@` 倍。证明中最"手艺活"的是格林估计：把中心化逆拉普拉斯算子拆成树割之和，等值线双射把割的大小化成对偶树距离，再用 Dyck 游走估计控制——纯组合的有限图论证。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="120" y="45" font-size="14" text-anchor="middle" fill="#333">按生成树数加权的随机地图</text>
  <polygon points="195,150 166,104 120,72 63,93 50,150 68,202 120,216 171,201" fill="#f6f6f6" stroke="#999" stroke-width="1.5"/>
  <line x1="120" y1="150" x2="195" y2="150" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="120" y1="150" x2="166" y2="104" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="120" y1="150" x2="120" y2="72" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="120" y1="150" x2="63" y2="93" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="120" y1="150" x2="50" y2="150" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="120" y1="150" x2="68" y2="202" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="120" y1="150" x2="120" y2="216" stroke="#c0392b" stroke-width="2.5"/>
  <line x1="120" y1="150" x2="171" y2="201" stroke="#c0392b" stroke-width="2.5"/>
  <circle cx="120" cy="150" r="4" fill="#333"/>
  <circle cx="166" cy="104" r="3" fill="#333"/><circle cx="63" cy="93" r="3" fill="#333"/><circle cx="50" cy="150" r="3" fill="#333"/><circle cx="195" cy="150" r="3" fill="#333"/>
  <text x="120" y="248" font-size="13" text-anchor="middle" fill="#c0392b">红色星形＝一棵生成树</text>
  <line x1="212" y1="150" x2="240" y2="150" stroke="#333" stroke-width="2"/>
  <polygon points="240,145 250,150 240,155" fill="#333"/>
  <circle cx="285" cy="150" r="30" fill="none" stroke="#333" stroke-width="2.5"/>
  <line x1="285" y1="150" x2="285" y2="132" stroke="#333" stroke-width="3"/>
  <line x1="285" y1="150" x2="300" y2="158" stroke="#333" stroke-width="3"/>
  <circle cx="285" cy="150" r="3" fill="#333"/>
  <text x="285" y="205" font-size="13" text-anchor="middle" fill="#333">时钟恰为 × n</text>
  <line x1="322" y1="150" x2="350" y2="150" stroke="#333" stroke-width="2"/>
  <polygon points="350,145 360,150 350,155" fill="#333"/>
  <path d="M 507,150 Q 526,116 489,106 Q 479,69 445,88 Q 411,69 401,106 Q 364,116 383,150 Q 364,184 401,194 Q 411,231 445,212 Q 479,231 489,194 Q 526,184 507,150 Z" fill="#f6f6f6" stroke="#333" stroke-width="1.5"/>
  <path d="M 415,150 C 435,120 470,130 480,160 C 485,180 455,190 430,175" fill="none" stroke="#2e6bd6" stroke-width="2.5"/>
  <text x="445" y="45" font-size="14" text-anchor="middle" fill="#333">√2-量子球</text>
  <text x="445" y="258" font-size="13" text-anchor="middle" fill="#2e6bd6">刘维尔布朗运动</text>
</svg>

</div>

**为什么值得关心**

验证了族内方法可跨模型迁移；其中的格林估计可独立于能量识别单独复用，是可带走的技术输出。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明了按生成树数目加权的平面地图上的平稳随机游走，在时间加速恰好 `@@M@@n@@`（边数）倍后，其条件路径律连同度量-测度空间收敛到 `@@M@@\sqrt2@@`-量子球上的刘维尔布朗运动，时钟乘子精确为 1。

## 问题背景
随机曲面的度量与面积极限并不自动决定曲面上的粒子运动：逼近图的电导（conductance）可以改变极限扩散，而时间归一化是否收敛到单一确定性线性时钟，是独立的难题。本文处理按生成树数目加权的平面地图——即地图带均匀生成树装饰的 Mullin–Bernardi 情形，本族概述将其与 FK–Ising 并列为已证明扩散收敛的两个模型。其几何前提（等值线重构理论与度量-测度极限）已由姊妹篇给出，本文补上电网络能量识别与速度测度（speed measure）控制两块拼图，证明这种分离式策略恰好可行，因为两部分都不能单独由度量-测度收敛推出。

## 主要结果
`@@M@@(M_n,T_n)@@` 均匀取自 `@@M@@n@@` 条边、带一棵生成树的有根平面多重图对，故地图边缘分布权重正比于其生成树个数。游走在速率 1 的泊松时钟驱动下等概率选取关联半边（half-edge）并移动到另一端点，环不产生位移；其平稳可逆分布为度测度 `@@M@@\mu_n=\sum_{v\in V_n}\frac{\deg(v)}{2n}\delta_v@@`。连续极限是单位面积 `@@M@@\sqrt2@@`-刘维尔量子引力（LQG）球 `@@M@@(S,D_h,\mu_h)@@`，其上扩散为狄利克雷型（Dirichlet form）`@@M@@\cE_h(f,g)=\frac12\int\langle\nabla f,\nabla g\rangle\dd\vol@@` 在 `@@M@@L^2(\mu_h)@@` 上闭包所对应的刘维尔布朗运动（Liouville Brownian motion）。主定理：在确定性直径归一化 `@@M@@a_n@@` 下，四元组 `@@M@@(V_n,a_nd_n,\mu_n,Q_n^T)@@` 收敛到 `@@M@@(S,D_h,\mu_h,Q_h^T)@@`，其中 `@@M@@Q_n^T@@` 是给定地图时加速路径 `@@M@@(X^n_{nt})_{0\le t\le T}@@` 的条件律，`@@M@@Q_h^T@@` 是给定场 `@@M@@h@@` 时 `@@M@@B^h@@` 的条件律——即在曲线装饰的 Gromov–Hausdorff–Prokhorov 型拓扑下保留随机环境信息的淬火（quenched）联合收敛，时间加速常数 `@@M@@c=1@@`。同一论证还给出任意固定条条件独立平稳游走的联合收敛，完整保留共享环境的信息。

## 证明思路
证明刻意把"能量识别"与"速度测度"分开。能量方面，先证非退化性：若环域极值长度（extremal length）可以坍缩到零，低能流会留下非零的平均长度测度极限；局部性与场芽（field germ）平凡性使典型点处同时出现横穿的原始与对偶穿越流，而任何这样一对都要经过一条边及其对偶边，与流量范数趋于零矛盾；由此得到有界能量的截断函数与调和函数族的紧性。再识别能量：每个局部变分极限都形如 `@@M@@\lambda\int\abs{\nabla u}^2@@`，且原始与对偶网络共享同一确定性正标量 `@@M@@\lambda@@`；为定出 `@@M@@\lambda@@`，把环域上的电容器与其旋转电流的周期相比较，一个方向给出 `@@M@@\lambda\le1@@`，另一个方向借助角上同调（angular cochain）的恢复与原始–对偶带符号配对给出 `@@M@@\lambda\ge1@@`，故 `@@M@@\lambda=1@@`；继而通过内部游离密度把结果转移到固定面积球面，被略去的单个等值线端点因零索伯列夫容量（Sobolev capacity）而无影响。速度测度方面，关键是关于中心化逆图拉普拉斯的一致估计 `@@M@@\|G_nf\|_\infty\le A_n\,\mu_n(\abs f)^\rho@@`（`@@M@@0<\rho<1/2@@`，`@@M@@\sup_n\EE A_n<\infty@@`），其证明完全是有限地图上的组合论证：生成森林恒等式把中心化逆表示为树割之和，等值线双射把每个割的大小表示为 1 加一个对偶树距离，再由 Dyck 游走（Dyck excursion）估计控制区间和。最后的动力学部分：上述格林界与能量收敛、调和紧性共同满足一个确定性收敛判据；预解式（resolvent）一致收敛配合 `@@M@@\alpha R_\alpha f\to f@@` 的一致 Feller 型逼近，给出对一切起始顶点一致的出口时间估计，Aldous 判据给出紧性；平稳有限维分布经乘积拉普拉斯变换识别为极限扩散的对应量。时钟则由精确恒等式 `@@M@@-\langle f,nL_nf\rangle_{L^2(\mu_n)}=\frac12\en_n(f)@@` 结合 `@@M@@\lambda=1@@` 直接读出。

## 可信度与备注
主结果暂无形式化证明；依 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。本文与两篇 FK–Ising 姊妹篇结构平行（姊妹篇几何极限 + 本文能量与格林估计 + 路径收敛），验证了族 211 的方法跨模型可迁移；其格林估计可独立于能量识别单独使用，是可复用的技术输出。核验时应重点关注 `@@M@@\lambda=1@@` 的双向比较论证与格林估计的组合部分。

{% endraw %}
