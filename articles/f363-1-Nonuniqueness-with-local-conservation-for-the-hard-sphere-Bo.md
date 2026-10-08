---
layout: default
title: "Nonuniqueness with local conservation for the hard-sphere Boltzmann equation"
family: "363"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Nonuniqueness with local conservation for the hard-sphere Boltzmann equation

> 结果族 363：Nonuniqueness with local conservation for the hard-sphere Boltzmann equation　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

给同一杯稀薄气体拍下"出厂快照"，然后放开时间，直觉说未来只有一种剧本。这篇论文却构造出一杯特殊的气体：它有两个都合规的未来——演化各不相同，但每一处、每一刻的质量、动量、能量账本都分毫不差，连通常弱解里允许的"误差项"都没有。决定论的方程，交出了两份不同的答卷。

**关键词卡片**

- 硬球玻尔兹曼方程（hard-sphere Boltzmann equation）：稀薄气体分子自由飞行加两两弹性碰撞的基本方程。
- 熵解（entropy solution）：只要求质量、能量、熵有限的整体弱解；DiPerna–Lions 1989 年证明其存在。
- 局部守恒（local conservation）：守恒律对每个空间点逐点精确成立，不带缺陷项。
- 缺陷测度（defect measure）：弱解中可能"丢失"的那部分守恒量，以往理论无法排除它非零。
- 冷射流（cold jets）：初值中沿相反方向排列、尺度不断变细的极窄高速粒子束，非唯一性的发动机。

**看个具体例子**

定理代入：初值 `@@M@@F_0@@` 由几何递减尺度 `@@M@@s_j=s_0e^{-j\eta}@@` 的环状冷射流组成，沿 `@@M@@+z@@` 与 `@@M@@-z@@` 方向交替排布。它长出两个解 `@@M@@F@@` 与 `@@M@@G@@`：在正测度集上不同，但对五个碰撞不变量中的任何一个 `@@M@@\psi@@`（例如 `@@M@@\psi=1@@`，即质量）都精确满足 `@@M@@\int F\,\psi\,(\partial_t+v\cdot\nabla_x)\phi+\int F_0\,\psi\,\phi(0)=0@@`，没有任何缺陷项；能量与熵不等式同样成立。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="140" y="50" width="280" height="180" fill="none" stroke="#333" stroke-width="2"/><text x="200" y="255" font-size="15" fill="#333">三维周期盒子</text><line x1="280" y1="60" x2="280" y2="225" stroke="#999" stroke-width="1.5" stroke-dasharray="6 5"/><polygon points="280,50 275,60 285,60" fill="#333"/><text x="295" y="68" font-size="15" fill="#333">+e₃</text><polygon points="280,230 275,220 285,220" fill="#333"/><text x="295" y="222" font-size="15" fill="#333">−e₃</text><ellipse cx="280" cy="95" rx="60" ry="14" fill="none" stroke="#333" stroke-width="2"/><ellipse cx="280" cy="130" rx="38" ry="10" fill="none" stroke="#333" stroke-width="2"/><ellipse cx="280" cy="160" rx="22" ry="7" fill="none" stroke="#333" stroke-width="2"/><ellipse cx="280" cy="185" rx="12" ry="5" fill="none" stroke="#333" stroke-width="2"/><text x="350" y="92" font-size="15" fill="#555">尺度递减的冷射流环</text></svg>

</div>

**为什么值得关心**

它说明即使加上最严格的逐点守恒，DiPerna–Lions 解类仍不唯一——唯一性需要真正的正则性门槛，这个反例划出了边界。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了三维周期硬球玻尔兹曼方程（hard-sphere Boltzmann equation）存在一个初值，能同时派生出两个不同的整体熵解，且二者都逐点精确满足质量、动量、动能的局部守恒——非唯一性在最严格的守恒框架下依然成立。

## 问题背景

玻尔兹曼方程自 Boltzmann 1872 年的动理学理论起描述稀薄气体的自由输运与二体弹性碰撞：碰撞在每个空间点守恒质量、动量与动能，并使熵下降。对空间非齐次柯西问题，DiPerna 与 Lions 于 1989 年建立大初值的整体存在与弱稳定性理论（重整化解，renormalized solutions），但唯一性始终悬而未决。重整化是实质性的：仅凭质量、能量、熵有限不能保证二次碰撞项局部可积。而在这一正则性水平上，精确守恒是又一难题——Levermore 与 Masmoudi 的周期表述只给出局部质量守恒，动量平衡中允许一个非负矩阵值的缺陷（defect），总能量也有相应缺陷，均不自动为零。已知唯一性定理都需要更强控制：Kaniel–Shinbrot 的麦克斯韦上界类、Ukai 的麦氏附近小扰动理论、Duan–Huang–Wang–Yang 的大振幅小相对熵类。本文初值的振幅在收缩的空间尺度上无界，小相对熵不足以把它纳入这些唯一性类。本文也是 2026 年 9 月姊妹篇的直接强化：那篇已证熵解类中的非唯一性，但其延拓定理给不出本文所需的精确局部动量与能量恒等式。

## 主要结果

主定理：存在 `@@M@@R<\infty@@` 与非负初值 `@@M@@F_0@@`，速度支撑含于球 `@@M@@B_R(0)@@`，且
`@@M@@D\int F_0(1+|v|^2+|\log F_0|)\,dx\,dv<\infty@@`
（质量、能量、绝对熵均有限），使得方程 `@@M@@(\partial_t+v\cdot\nabla_x)F=Q^+(F,F)-Q^-(F,F)@@` 拥有两个"带局部守恒的整体熵解"，且在一组正 `@@M@@(t,x,v)@@`-测度集上不同。按论文引言中的定义，这类解满足：`@@M@@F\in C([0,\infty);L^1)@@` 并取初值；对一切满足 `@@M@@|\beta'(z)|\le C_\beta/(1+z)@@` 的 `@@M@@\beta@@` 成立重整化方程；每个时刻满足能量不等式与熵不等式 `@@M@@\mathcal H_M(F(t))+\int_0^t\mathcal D(F)\,ds\le\mathcal H_M(F_0)@@`；并且对五个碰撞不变量（collision invariants）`@@M@@\psi\in\{1,v_1,v_2,v_3,|v|^2/2\}@@` 与任意空间试验函数 `@@M@@\phi@@`，局部平衡
`@@M@@D\int_0^\infty\!\!\int F\,\psi\,(\partial_t+v\cdot\nabla_x)\phi\,dx\,dv\,dt+\int F_0\,\psi\,\phi(0)\,dx\,dv=0@@`
精确成立——不出现任何动量或能量缺陷测度。此外，两解的碰撞增益与损失 `@@M@@Q^\pm(F,F)@@` 在每个有限时段上带任意多项式速度权 `@@M@@\langle v\rangle^k@@` 可积，这正是让全部局部平衡通过取极限的决定性输入。

## 证明思路

先构造初值：在几何递减尺度 `@@M@@s_j=s_0e^{-j\eta}@@` 上，沿 `@@M@@\pm e_3@@` 轴放置薄环状冷射流（cold jets），速度宽度 `@@M@@d_s=d_0s^{10}@@` 极窄、幅度 `@@M@@K/s@@` 极大，但横截面积仅 `@@M@@O(s^2)@@`，故每个尺度的质量为 `@@M@@O(s^2)@@`、绝对熵为 `@@M@@O(s^2(1+|\log s|))@@`，几何求和收敛；两个速度方向按周期 `@@M@@s_j^2@@` 的细条纹交错分开。要把此机制延拓到全时间并保住全部局部守恒律，须跨过两道坎：薄射流终将撞上自身的周期像；熵界不足以让增益、损失分别可积。解法是给每个尺度设有限寿命：射流轴取二次无理方向 `@@M@@(1,\sqrt2,0)/\sqrt3@@`，利用 `@@M@@m^2-2k^2@@` 是非零整数证得格点的丢番图分离 `@@M@@|\bar n|\ge c/(1+|n|)@@`，于是尺度 `@@M@@s@@` 的射流在退役时间 `@@M@@L_s=s^{-1/2}@@` 前不会自交，到点后整体并入余量分量 `@@M@@w@@`。再放一个挖去轴旁空间洞、带速度截断的近麦克斯韦"浴"，使初始相对熵任意小；经 Duhamel 公式、双球几何与沿自由飞行的平均估计，它在短时刻 `@@M@@t_1@@` 之后提供与逼近指标无关的正碰撞频率 `@@M@@\kappa>0@@`，射流随之指数衰减，退役增量 `@@M@@J_s\le Cs^{-C}e^{-\kappa(s^{-1/2}-t_1)}@@` 可和。中心环节是整体延拓估计（第 7 节），由三个事实闭环：小速度质量使规范化增益变小；小相对熵控制超出麦克斯韦部分的空间 `@@M@@L^1@@` 范数；飞行平均引理把空间小性沿特征线化为逐点小盈余质量。由此二次增益 `@@M@@P^b(w,w)\le C_5H@@`，常数 `@@M@@C_5=\|P(\mu,\mu)\|_H+1@@` 与自举尺寸无关，Gronwall 不等式闭合自举，得到一切有限逼近的一致整体界。第 8 节去掉截断取极限：小尺度环形集上密度包络的平方一致可积（每个尺度贡献 `@@M@@\le C_\tau s@@`），同位置双粒子乘积因而一致可积；配合 Golse–Lions–Perthame–Sentis 速度平均引理识别出 `@@M@@Q_N^\pm\rightharpoonup Q^\pm(F,F)@@`，路径公式给出强 `@@M@@L^1@@` 连续代表，五个局部平衡不带缺陷地通过。非唯一性沿用姊妹篇的双族机制：无种子的休眠族（dormant）与带可消失种子的封顶族（cap，种子幅度含因子 `@@M@@m_T=T^p@@`）。在封顶时刻作时空伸缩，得到双流介质中线性方程的非零解 `@@M@@g@@`，分支增长强制其伸缩视界有限，故两种伸缩尺度可比；而休眠解在相应伸缩下于速度轴外消失。若两解在任意小的视界上重合，对角抽取将迫使 `@@M@@g=0@@`，与 `@@M@@g@@` 非零矛盾。

## 可信度与备注

本文暂无 Lean 形式化证明，请以社区核验为准。文章明确标注：射流机制、核估计、非零伸缩极限与分支增长均援引 2026 年 9 月姊妹篇并复现，新贡献是射流与周围气体在任意长时间上的相互作用估计，以及由此得到的精确局部守恒与整体 `@@M@@L^1@@` 强连续。姊妹篇提供机制、本文提供守恒强化，两篇互为支撑。按 OpenAI 官方声明，未经形式化的结果可能有问题，采纳前请以社区核验为准。

{% endraw %}
