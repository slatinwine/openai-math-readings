---
layout: default
title: "Critical mixing in the Sherrington–Kirkpatrick model"
family: "227"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Critical mixing in the Sherrington–Kirkpatrick model

> 结果族 227：Critical SK autocorrelation processes and dynamics across the temperature transition　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

搅一锅恰好停在结冰点的汤要多久？姊妹篇证明了"少于 n^(2/3) 搅不匀"，这篇补上匹配的上界并配平指数：即使在最严苛的标准（对手挑最坏起点）下，临界点的混合时间也恰是 n^(2/3)——幂次一点不差。

**关键词卡片**

- 混合时间（mixing time）：从最坏起点出发，总变差距离降到 1/4 以下所需的时间。
- 离散更新时钟（discrete updates）：每步均匀挑一枚自旋重掷；n 次尝试约合连续时间 1 单位，故幂次差一个因子 n。
- 松弛时间（relaxation time）：谱隙的倒数，链条"遗忘"初态的特征时间。
- 对数 Sobolev 常数（logarithmic Sobolev constant）：控制熵耗散快慢的经典常数。
- 记号 n^(2/3+o(1))：幂次恰为 2/3，误差不超过任意小的幂。

**看个具体例子**

n=10^6 枚自旋、温度恰为 β=1：连续搅拌约需 (10^6)^(2/3)=10^4 个时间单位；按"每步挑一枚"计数则需 (10^6)^(5/3)=10^10 次尝试。同一个指数还同时控制松弛时间与对数 Sobolev 常数。也就是说，难度按幂律温和增长：10 枚自旋约需 10^(2/3)≈4.6 个单位，100 万枚也只需 1 万个单位，远非低温区的指数爆炸。下图把整条温度轴的"搅拌难度"画在一起。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="140" y="24" font-size="15" fill="#333">搅拌多久才搅匀？——混合时间随温度变化</text><line x1="70" y1="235" x2="530" y2="235" stroke="#555" stroke-width="2"/><line x1="70" y1="235" x2="70" y2="50" stroke="#555" stroke-width="2"/><text x="24" y="150" font-size="12" fill="#555" transform="rotate(-90 24 150)">log(混合时间)</text><line x1="280" y1="235" x2="280" y2="55" stroke="#bbb" stroke-dasharray="5 5"/><text x="66" y="255" font-size="13" fill="#555">0</text><text x="276" y="255" font-size="13" fill="#555">1</text><text x="486" y="255" font-size="13" fill="#555">2</text><text x="430" y="272" font-size="12" fill="#555">温度参数 β</text><path d="M70,222 C140,224 200,220 250,205 C272,197 277,180 280,172 C283,180 291,183 300,174 C330,142 352,85 420,58 C452,46 492,42 522,42" fill="none" stroke="#333" stroke-width="2.5"/><circle cx="280" cy="172" r="5" fill="#c62828"/><text x="100" y="210" font-size="13" fill="#2e7d32">高温区：多项式搅匀</text><text x="216" y="140" font-size="13" fill="#c62828">临界点：恰为 n^(2/3)</text><line x1="262" y1="145" x2="276" y2="164" stroke="#c62828" stroke-width="1"/><text x="360" y="80" font-size="13" fill="#1565c0">低温区：伸展指数 e^(n^…)</text></svg>

</div>

**为什么值得关心**

把严格混合结果从高温区第一次推进到相变点本身，而且一次定齐四个基本量（两种混合时间、松弛时间、对数 Sobolev 常数）的精确指数。

> 暂无形式化证明（AI 结果待核验）。

# 过渡段 | Critical mixing in the Sherrington–Kirkpatrick model

## 由浅入深：从类比走向定理

**第一级台阶**

导读问"搅一锅恰好停在结冰点的汤要多久"，并强调本篇换了更严苛的考官：不再从典型冰块出发，而是允许对手专门挑一份最难搅匀的初始清单。对象仍是磁针指向清单加随机相互作用矩阵，操作仍是一次翻一枚磁针；问题变成：在相变温度上，哪怕最坏情况，搅匀所需的时间按系统规模以什么速度增长。答案是一个温和的幂律——既非高温区的快速多项式，也非低温区的指数爆炸。

**第二级台阶**

精确化：`@@M@@n@@` 个 `@@M@@\pm1@@` 自旋、高斯耦合、零场、临界 `@@M@@\beta=1@@`，得吉布斯律 `@@M@@\mu_J@@`；生成元 `@@M@@\mathcal L_J=\sum_i(Q_i-I)@@` 的热浴链让每个站点率一更新。最坏起点混合时间 `@@M@@t_{\mathrm{mix},J}@@` 是让所有初始组态的总变差距离都降到 `@@M@@1/4@@` 的最早时刻；离散版本 `@@M@@k_{\mathrm{mix},J}@@` 数均匀选点的更新尝试。松弛时间 `@@M@@R_J@@` 是谱隙倒数（Poincaré 常数），对数 Sobolev 常数 `@@M@@C_{\mathrm{LS},J}@@` 则控制熵耗散 `@@M@@\Ent_{\mu_J}(f^2)\le C_{\mathrm{LS},J}\,\mathcal D_J(f)@@`。记号 `@@M@@X_n=n^{a+o(1)}@@` 指对任意 `@@M@@\delta>0@@`，`@@M@@X_n@@` 以高概率落在 `@@M@@n^{a\pm\delta}@@` 之间。

**第三级台阶**

定理 1.1 在临界点陈述：依无序概率，`@@M@@t_{\mathrm{mix},J}@@` 与 `@@M@@k_{\mathrm{mix},J}@@`、松弛时间 `@@M@@R_J@@`、对数 Sobolev 常数 `@@M@@C_{\mathrm{LS},J}@@` 全部为 `@@M@@n^{2/3+o(1)}@@`（离散为 `@@M@@n^{5/3+o(1)}@@`，多出的因子 `@@M@@n@@` 来自两种时钟换算）。高斯无序假设让 GOE 谱边缘几何可用——极限谱密度在边缘按距离平方根衰减，宽 `@@M@@u@@` 的窗口约含 `@@M@@nu^{3/2}@@` 个维度，这是全部尺度的来源；下界输入直接来自姊妹篇的线性 Rayleigh 商与实现初态结论，本文的贡献全在上界。结论刻意止于指数：不断言 cutoff、混合窗口或领先常数。

## 一句话结论
论文定出 SK 模型临界点 `@@M@@\beta=1@@` 处最坏初态混合时间的精确指数：连续时间（每站点更新率 1）为 `@@M@@n^{2/3+o(1)}@@`，离散尝试更新为 `@@M@@n^{5/3+o(1)}@@`；同一指数还控制松弛时间与经典对数 Sobolev 常数，把严格混合界从高温区域推进到临界温度本身。

## 问题背景
SK 模型（Sherrington–Kirkpatrick model）的平衡态在临界逆温度 `@@M@@\beta=1@@` 处发生自旋玻璃转变，而动力学在临界点附近如何弛豫是老问题：Kirkpatrick–Sherrington 早在 1978 年就用线性化平均场与蒙特卡洛研究单自旋 Glauber 弛豫，Sompolinsky–Zippelius（1982）发展了软自旋 Langevin 图像；数值上 Billoire–Campbell（2011）测得平衡自相关符合标度形式 `@@M@@q_c(n,t)\sim n^{-1/3}F(t/n^{2/3})@@`，暗示 `@@M@@n^{2/3}@@` 时标。严格结果此前都限于高温相：Bauerschmidt–Bodineau 的对数 Sobolev 不等式、Eldan–Koehler–Zeitouni 的谱判据（`@@M@@\beta<1/4@@`），Wang 与 Boban–Li–Oveis Gharan 推到 `@@M@@\beta<1/2@@` 及其邻域，谱隙姊妹篇覆盖每个固定 `@@M@@\beta<1@@`——但都无法取极限到 `@@M@@\beta=1@@`。临界姊妹篇定出线性观测量与"实现初态"的慢尺度为 `@@M@@n^{2/3}@@`，本文补上与之匹配的上界，从而确定指数。

## 主要结果
定理 1.1：对每个固定 `@@M@@\varepsilon\in(0,1/2)@@`，在无序变量（disorder）概率意义下
`@@M@@Dt_{\mathrm{mix},J}(\varepsilon)=n^{2/3+o(1)},\quad k_{\mathrm{mix},J}(\varepsilon)=n^{5/3+o(1)},\quad R_J=n^{2/3+o(1)},\quad C_{\mathrm{LS},J}=n^{2/3+o(1)},@@`
其中 `@@M@@X_n=n^{a+o(1)}@@` 意为对任意 `@@M@@\delta>0@@` 都有 `@@M@@\mathbb P\{n^{a-\delta}\le X_n\le n^{a+\delta}\}\to1@@`。`@@M@@t_{\mathrm{mix}}@@` 是生成元 `@@M@@\mathcal L_J=\sum_i(Q_i-I)@@`（每站点率一）的最坏初态混合时间，`@@M@@k_{\mathrm{mix}}@@` 是每次均匀选点尝试更新的步数，`@@M@@R_J@@` 是松弛时间（relaxation time，即 Poincaré 常数、谱隙倒数），`@@M@@C_{\mathrm{LS},J}@@` 是经典对数 Sobolev 不等式（logarithmic Sobolev inequality）常数。推论还给出熵产生常数 `@@M@@C_{\mathrm{EP},J}=n^{2/3+o(1)}@@`：对任意初始律 `@@M@@\nu@@` 有 `@@M@@\mathrm{KL}(\nu e^{t\mathcal L_J}\Vert\mu_J)\le e^{-t/C_{\mathrm{EP},J}}\mathrm{KL}(\nu\Vert\mu_J)@@`。下界来自姊妹篇：线性 Rayleigh 商 `@@M@@R_{\mathrm{lin},J}=n^{2/3+o(1)}@@`，以及"实现初态"结论——凡 `@@M@@t_n=o(n^{2/3})@@`，Gibbs 质量中距离仍超 `@@M@@1/4@@` 的初态占比趋于 1。本文只断言指数，不断言存在 cutoff（突变式混合）、混合窗口或领先常数。

## 证明思路
贡献全在上界，且给出两条独立路线，共同锚定在 GOE 谱边缘几何上：极限谱密度在边缘 2 附近按到边缘距离的平方根衰减，故宽 `@@M@@u@@` 的边缘窗口约含 `@@M@@nu^{3/2}@@` 个维度；球面自旋律可视为条件高斯，其预解式把边缘几何直接翻译为协方差估计。路线一（各向同性观测）：用高斯随机定位（Gaussian stochastic localization）在精度 `@@M@@s@@`（记 `@@M@@r=\sqrt s@@`，`@@M@@k=ns^{3/2}@@`）下逐步观测自旋，先经 Comets 型与 Du–Huang 的临界态立方–球面比较建立参照；再对 TAP 型方程 `@@M@@y+(1-q)m-Jm=h_s@@`、`@@M@@m=\tanh y@@`、`@@M@@q=\|m\|^2/n@@` 做条件 Kac–Rice 分析，条件矩阵计算分离出三个特殊方向（`@@M@@m@@`、`@@M@@\mathbf 1@@` 的正交分量、根场残量），其余方向留 Haar 旋转，四项符号组合 `@@M@@\mathcal R_{pp}-\mathcal R_{pg_0}-\mathcal R_{g_0p}+\mathcal R_{g_0g_0}@@` 相消公共误差，得到多数定向满足协方差 `@@M@@\|\Sigma_s\|\le(1+\epsilon)/s@@`；沿观测路径做放大（向后方差传输加集中），多对数窗口改用无约束旋转比较，底层尺度用带交错求和的有限 replicas 展开最后化为统一的支撑轮廓（support profile）：对一切支撑质量 `@@M@@p\le\frac12@@` 的检验函数 `@@M@@f@@`，`@@M@@\D_J(f)\ge c\,n^{-2/3-\omega}\log(1/p)\,\mu_J(f^2)@@`。路线二（谱帽）：只观测软边缘方向，`@@M@@B_p=(p^2-d)_+@@`，活跃帽秩约 `@@M@@np^3@@`；关键增益是"径向亏损"——位势 `@@M@@\phi_p=\log Z_{J_p}(h)@@` 的 Hessian 相对冻结预解式的修正 `@@M@@p^2(K_p-R_p)@@` 在径向有 `@@M@@\le-0.30@@` 的负项；精确高斯卷积把子尺度位势用父尺度表出，Brascamp–Lieb 上界与 Fisher 信息变分下界夹逼，配合仍隐藏特征标架的 Haar 压缩，从大帽向小帽归纳（初始化靠小场 TAP 展开与辅助位势），降至 `@@M@@np^3\asymp\sqrt{\log n}@@`，再经熵保持与分层论证得经典对数 Sobolev 不等式 `@@M@@\Ent_{\mu_J}(f^2)\le n^{2/3+\rho}\D_J(f)@@`。最后动力学转化：支撑轮廓经截断机制（密度 `@@M@@L^2@@` 范数大时 `@@M@@V'=-2\D@@` 指数下降、之后靠谱隙收尾），对数 Sobolev 经超压缩性（hypercontractivity）平滑；由 `@@M@@\mathcal L_J=n(P_J-I)@@` 保持两种时钟间的因子 `@@M@@n@@`，最小 Gibbs 质量 `@@M@@\ge\exp(-(3+\log2)n)@@`；下界用最慢特征函数测试，`@@M@@\mathrm{TV}\ge\frac12e^{-t/R_J}@@`。两条路线参数独立，结论互为印证。

## 可信度与备注
主结果暂无 Lean 形式化证明；上界依赖两份姊妹篇（临界伙伴的线性/实现初态下界、高温谱隙伙伴的 TAP 型场方程与字词估计工具，后者在 `@@M@@j=1@@` 处仅在验证假设后使用，并非取 `@@M@@\beta\uparrow1@@` 极限），请以社区核验为准。本篇与低温典型初态篇、障碍篇共同刻画跨温度转移的混合行为。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

---

# 深入探讨 | Critical mixing in the Sherrington–Kirkpatrick model

## 深入探讨：像审稿人一样追问 🔍

**问 1：`@@M@@n^{2/3+o(1)}@@` 里的 `@@M@@o(1)@@` 是什么意思，为什么不直接写清常数？**

（答：按论文约定，`@@M@@X_n=n^{a+o(1)}@@` 指对任意 `@@M@@\delta>0@@`，`@@M@@\mathbb P\{n^{a-\delta}\le X_n\le n^{a+\delta}\}\to1@@`——只锁幂次，不锁窗口。论文明言不断言 cutoff、混合窗口或领先常数；要把 `@@M@@o(1)@@` 收紧到 `@@M@@\log@@` 级甚至常数，需要全新精度的谱边缘控制，本文不触及。）

**问 2：下界是本文证的吗？**

（答：不是。定理 1.1 的下界直接调用临界姊妹篇的两个结果：线性 Rayleigh 商 `@@M@@R_{\mathrm{lin},J}=n^{2/3+o(1)}@@` 与"实现初态"慢混合（凡 `@@M@@t_n=o(n^{2/3})@@`，慢起点 Gibbs 质量趋于 1）。本文的全部贡献在上界，且给出两条彼此独立的路线。）

**问 3：两条上界路线里最脆弱的一步各在哪里？**

（答：路线一（各向同性观测）靠高斯随机定位逐步观测自旋，对 TAP 型方程做条件 Kac–Rice 分析，四项符号组合 `@@M@@\mathcal R_{pp}-\mathcal R_{pg_0}-\mathcal R_{g_0p}+\mathcal R_{g_0g_0}@@` 精确相消公共误差后还要沿观测路径放大（向后方差传输加集中），多对数窗口的无约束旋转比较最紧。路线二（谱帽）的关键增益是径向亏损——位势 Hessian 修正 `@@M@@p^2(K_p-R_p)@@` 在径向有 `@@M@@\le-0.30@@` 的负项，再靠精确高斯卷积从大帽向小帽归纳至 `@@M@@np^3\asymp\sqrt{\log n}@@`；那个 `@@M@@-0.30@@` 是硬数值，差一点正负号即翻转。）

**问 4：为什么不能拿高温谱隙结果取 `@@M@@\beta\uparrow1@@` 极限了事？**

（答：高温姊妹篇的谱隙在 `@@M@@\beta\uparrow1@@` 时本身塌缩，其 TAP 型场方程工具在 `@@M@@j=1@@` 处只在验证假设后才被本文使用，而非取极限——临界点的新困难（软边缘维度 `@@M@@nu^{3/2}@@`、球面–立方体比较）在固定 `@@M@@\beta<1@@` 的框架里根本不出现。这也是此前所有严格结果（Bauerschmidt–Bodineau、EKZ、Wang、BLO）止步高温的原因。）

**问 5：与已有工作相比真正的新意是什么？**

（答：这是第一个把严格混合界推进到 SK 相变点本身的结果，且一次定齐四个基本量——两种时钟的最坏混合时间、松弛时间、经典对数 Sobolev 常数（外加熵产生常数）——指数全部为 `@@M@@2/3@@`。物理侧 Billoire–Campbell 的标度形式 `@@M@@q_c(n,t)\sim n^{-1/3}F(t/n^{2/3})@@` 首次获得最坏起点、总变差层面的定理对应。）

**问 6：AI 生成证明最可能出错的模式是什么？**

（答：两条路线都重度依赖符号相消与多尺度归纳：Kac–Rice 条件矩阵计算中三个特殊方向与其余 Haar 旋转的分离、谱帽路线的 Brascamp–Lieb 上界与 Fisher 信息变分下界的夹逼，任何一步规范化错位都会在指数上留下痕迹。全文未形式化，且依赖姊妹篇未证伪的输入，建议社区先核支撑轮廓（support profile）那一条主引理。）

**问 7：这个结果谁会用到？**

（答：临界点采样与模拟的人据此校准成本——`@@M@@n=10^6@@` 只需约 `@@M@@10^4@@` 时间单位或 `@@M@@10^{10}@@` 次尝试，幂律温和；对数 Sobolev 与熵产生估计可直接用于其他马氏链收敛分析。与高温 cutoff 篇、低温伸展指数篇合起来，整条温度轴的混合图景就此闭合。）

**总评**

这是把临界混合指数从物理标度猜测升级为最坏起点严格定理的关键一环，四量齐定、双路线互证，分量十足；最大风险是未形式化且依赖姊妹篇输入链，Kac–Rice 相消与径向亏损两处硬常数是复核的首要目标。

{% endraw %}
