---
layout: default
title: "Annular variation of the triangular Hilbert transform at the symmetric point"
family: "082"
discipline: "Real and complex analysis"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Annular variation of the triangular Hilbert transform at the symmetric point

> 结果族 082：Annular variation and dyadic absolute bounds for the triangular Hilbert transform　·　学科：Real and complex analysis　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

医生看心电图，不只看某一刻的读数，还要看整条曲线的"起伏总量"——起伏有限，心跳才规律。这篇论文研究一个著名奇异积分（三角 Hilbert 变换）在所有可能截断下的读数序列，证明其 `@@M@@r@@`-变差（起伏总量）能被输入牢牢控制——读数不但有界，而且收敛得非常安分，不会反复横跳。

**关键词卡片**

- 三角 Hilbert 变换（triangular Hilbert transform）：`@@M@@\int F(x{+}t,y)G(x,y{+}t)\frac{dt}{t}@@`，两个函数沿两个方向平移后以 `@@M@@1/t@@` 为核纠缠在一起
- 环形截断（annular truncation）：只积分 `@@M@@\varepsilon<|t|<R@@` 的"圆环"部分以避开奇点
- r-变差（r-variation）：把序列切成若干段，各段增量绝对值的 `@@M@@r@@` 次方和开 `@@M@@r@@` 次方，衡量抖动的剧烈程度
- 极大算子（maximal operator）：一切截断读数中的最大值，"一把尺子管住所有时刻"
- 主值（principal value）：截断端点 `@@M@@\varepsilon\to0@@`、`@@M@@R\to\infty@@` 时的极限值

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="60" y1="150" x2="500" y2="150" stroke="#bbb"/>
<path d="M60,150 C110,60 160,230 210,110 C260,40 300,220 350,120 C400,60 440,200 490,140" stroke="#369" stroke-width="2.5" fill="none"/>
<line x1="150" y1="90" x2="150" y2="215" stroke="#c33" stroke-width="2"/>
<line x1="260" y1="70" x2="260" y2="205" stroke="#c33" stroke-width="2"/>
<line x1="380" y1="70" x2="380" y2="185" stroke="#c33" stroke-width="2"/>
<text x="128" y="245" font-size="13" fill="#c33">|Δ₁|</text>
<text x="248" y="245" font-size="13" fill="#c33">|Δ₂|</text>
<text x="368" y="245" font-size="13" fill="#c33">|Δ₃|</text>
<text x="80" y="40" font-size="14" fill="#333">读数随截断参数变化的"心电图"</text>
<text x="80" y="265" font-size="13" fill="#333">变差 = (|Δ₁|ʳ+|Δ₂|ʳ+…)^(1/r) 被输入控制 ⟹ 读数收敛</text>
</svg>

</div>

数字版定理：对一切 `@@M@@r>2@@` 与复值 `@@M@@F,G\in L^3(\mathbb R^2)@@`，`@@M@@\|V_r(F,G)\|_{L^{3/2}}\le C_r\|F\|_3\|G\|_3@@`；分割可随输出点任取，段数不加限制。有限变差强于收敛：由此免费得到双端点极大估计与联合主值，并解决 Thiele 问题 13 的对称点情形。

**为什么值得关心**

三角圈不是二部图，此前的 Bellman 函数框架明确处理不了它，是纠缠奇异积分领域公认的硬骨头；变差估计是比有界性、极大值都更强的一揽子结论，一个定理收编三样。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了三角 Hilbert 变换的环形 `@@M@@r@@`-变差（annular `@@M@@r@@`-variation）估计：对一切 `@@M@@r>2@@`，变差算子 `@@M@@V_r@@` 从复 `@@M@@L^3\times L^3@@` 有界映到 `@@M@@L^{3/2}@@`，且变差分割可随输出点任取。由此得到双端点极大估计与联合主值，并在对称点解决了 Thiele 的标量三角 Hilbert 变换问题。

## 问题背景

三角 Hilbert 变换把两个函数沿不同坐标方向平移后耦合：`@@M@@B_{\varepsilon,R}(F,G)(x,y)=\int_{\varepsilon<|t|<R}F(x+t,y)G(x,y+t)\,\frac{\mathrm dt}{t}@@`。它等价于单纯形坐标下的标量形式 `@@M@@\Lambda_{\varepsilon,R}(G_0,G_1,G_2)=\iiint_{\varepsilon<|a+b+c|<R}G_0(a,b)G_1(b,c)G_2(c,a)\,\frac{\mathrm da\,\mathrm db\,\mathrm dc}{a+b+c}@@`：三个输入各依赖三个变量中的一对、首尾相接成三角循环，是最基本的纠缠奇异积分（entangled singular integral）之一，由 Demeter–Thiele 与 Kovač–Thiele–Zorin-Kranich 等系统研究。Thiele 在 2017 年问题列表的问题 13 中提出对称点 `@@M@@L^3\times L^3\times L^3@@` 估计。此前最好的硬截断结果（Durcik–Kovač–Thiele 2019 的幂次型抵消，经置换与插值）只给出随尺度范围增长如 `@@M@@\sqrt{\log(R/\varepsilon)}@@` 的界；Walsh 模型的结果则要求第三个输入带特殊结构。更深的障碍在于三角图不是二部图，Kovač 的 Bellman 函数框架明确指出无法直接处理三角圈。

## 主要结果

主定理（完整环形变差）：对每个实数 `@@M@@r>2@@` 存在有限常数 `@@M@@C_r@@`，使
`@@M@@D\|V_r(F,G)\|_{L^{3/2}(\mathbb R^2)}\le C_r\|F\|_{L^3}\|G\|_{L^3}@@`
对一切复 `@@M@@F,G\in L^3(\mathbb R^2)@@` 成立，其中 `@@M@@V_r(F,G)(x,y)=\sup(\sum_{j=1}^J|B_{t_{j-1},t_j}(F,G)(x,y)|^r)^{1/r}@@`，上确界取遍一切有理分割 `@@M@@0<t_0<\cdots<t_J@@`，分割可随输出点逐点选取，对二进尺度区间内的端点个数也不加限制。实质核心是不交环计数估计（disjoint-annulus count estimate）：`@@M@@\|\mathcal S_n(F,G)\|_{3/2}\le C\sqrt n\log(2+n)\|F\|_3\|G\|_3@@`，其中 `@@M@@\mathcal S_n@@` 是至多 `@@M@@n@@` 个两两不交环上增量绝对值之和的逐点上确界。推论：硬极大算子 `@@M@@B_*=\sup_{0<\varepsilon<R}|B_{\varepsilon,R}|@@` 满足同一乘积界；联合主值 `@@M@@B=\lim_{\varepsilon\downarrow0,R\uparrow\infty}B_{\varepsilon,R}@@` 几乎处处且在 `@@M@@L^{3/2}@@` 中存在，尾部以极大意义收敛到零；与第三个 `@@M@@L^3@@` 输入配对，得到平的与单纯形两种标量三线性形式的一致界与联合标量主值，且两形式的最优常数相等——这肯定地解决了 Thiele 问题 13 的对称点情形。

## 证明思路

全文的实质是计数估计，变差由它经秩分组导出。先处理光滑环：把截断核写成三个一元高斯导数窗卷积的尺度积分，固定三个窗中心（其和为零）后，三个窗因子分别只依赖 `@@M@@a,b,c@@`；在有限网格上，采样出的成对输入给出三个矩阵 `@@M@@W_v@@`，窗因子给出对角插入，局部和成为循环矩阵迹（cyclic matrix trace）`@@M@@\tr(D_0W_0D_1W_1D_2W_2)@@`。在每个顶点把两条邻接矩阵并排成行星（row star）`@@M@@R_v=[\,W_v\ \ W_{v-1}^*\,]@@`，赋能量 `@@M@@\Phi(P)=\tr(P^{3/2})@@`——它与三线性形式同为三次齐次标度。核心的混合迹不等式（mixed trace inequality）把循环积的模控制为三个 Hessian 二次代价之和的常数倍；矩阵固定后，热流恒等式把累积的代价用初始能量控制，而对中心积分后的能量又被立方 `@@M@@L^3@@` 范数之和控制。从单个环到多个环有两类损失。光滑环上，对偶矩阵的元素在自选端点处开关，对能量跳跃（energy jump）逐元估计后对对偶输入重标度，得 `@@M@@\sqrt n@@` 因子；硬环上逐端点估计会线性损失，改为按二进半径区间分组，环的两两不交性保证每组具有一致的大小与导数界。另一新工具是频率块估计（frequency-block estimate），处理系数同时依赖尺度、频率与输出点的调制高斯窗：收窄一个高斯方差并平均其中心平移，把振荡插入表示为窄高斯导数的平均，仅保留一条输入边的辅助热流控制多余的导数项，再用二维高斯估计控制尺度区间端点处的能量变化。组装时，先把硬线性化写成光滑线性化减端点误差，对固定的有限"菜单"用矩形逼近与可测选取、`@@M@@L^3@@` 对偶得到界，再经稠密性过渡到一般复 `@@M@@L^3@@` 输入并穷举全部有理环列。最后把每个分割的增量按绝对值降序排列、按秩二进分组，得 `@@M@@V_r\le\sum_{j\ge0}2^{j/r-j}\mathcal S_{2^j}@@`，其通项如 `@@M@@(1+j)2^{j(1/r-1/2)}@@`，级数恰在 `@@M@@r>2@@` 时收敛——结论中对增量个数与端点的二进限制都不复存在。

## 可信度与备注

本文暂无形式化证明。姊妹篇《The maximal triangular Hilbert transform at the symmetric point》的主定理已 Lean 形式化，其核心矩阵引理与本文第三节同源（同样的能量 `@@M@@\tr(P^{3/2})@@` 与混合迹不等式，本文自成体系地给出全部证明）；另一篇 dyadic 模型论文则直接复用极大一文的矩阵引理。按 OpenAI 官方声明，未经形式化的结果可能有问题，本文的变差与计数定理应以社区核验为准。

{% endraw %}
