---
layout: default
title: "Triangular minimality for planar Coulomb renormalized energy"
family: "090"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Triangular minimality for planar Coulomb renormalized energy

> 结果族 090：Triangular-lattice optimality, long-range Riesz and Coulomb energies, and spherical logarithmic energy　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

超导体里的磁通涡旋像一群同极小磁铁，被一层均匀的正面"中和背景"包裹后，会自发排成整齐的三角阵——物理课本里的 Abrikosov 格子。这篇论文证明：在一切可能的排法中，三角阵的静电能确实最低；顺带还精确锁定了"球面上撒电荷"能量公式里的一个神秘常数。

**关键词卡片**

- 重整化能量（renormalized energy）：无穷电荷系统的总能量发散，先扣除每个电荷的对数"自能"再取极限，剩下的净能量。
- Abrikosov 格子（Abrikosov lattice）：超导涡旋自发排成的三角周期点阵，实验照片里的六角花纹。
- Voronoi 胞腔（Voronoi cell）：每个点独占的"地盘"，即平面上离它最近的区域。
- 格林函数（Green function）：环面上对数库仑相互作用的位势。
- 渐近展开（asymptotic expansion）：粒子数 `@@M@@n\to\infty@@` 时最小能量公式的逐项精确表达。

**看个具体例子**

公式卡（数字版定理）：球面 `@@M@@S^2@@` 上放 `@@M@@n@@` 个点，两两对数能量之和的最小值满足
`@@M@@DE_{\log}(n)=\Big(\tfrac12-\log 2\Big)n^2-\tfrac n2\log n+C_{\mathrm{BHS}}\,n+o(n),\qquad C_{\mathrm{BHS}}=2\log 2+\tfrac12\log\tfrac23+3\log\tfrac{\sqrt\pi}{\Gamma(1/3)}\approx-0.056 .@@`
比如 `@@M@@n=10^6@@` 时线性项约贡献 `@@M@@-5.6\times10^4@@`——这个系数完全由"平面上三角阵是否能量最低"决定，本文给出了肯定答案。平面这边的证明思路是：先靠周期逼近把整个平面的问题化归到方环面，再给每个电荷划出 Voronoi"地盘"，逐格与三角格的六边形地盘比能量，最后两个关键的标量不等式交给区间算术程序严格验证——连一点浮点误差都不许有。

**为什么值得关心**

它一举解决 Sandier–Serfaty 猜想（超导涡旋的能量基态）与 Brauchart–Hardin–Saff 猜想的二维情形，把物理直觉变成严格定理。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明 Sandier–Serfaty 猜想：在单位均匀背景的二维库仑（对数）重整化能量中，协体积为一的三角形格子的周期场达到最小，任何容许无旋场的能量都不低于它；结合 Bétermin–Sandier 渐近公式，还确定了球面对数能量最优值的线性项常数，解决 Brauchart–Hardin–Saff 猜想的二维情形。

## 问题背景

二维库仑相互作用是对数式的：无穷多个等量点电荷配上均匀中和背景（jellium"凝胶"模型），总静电能发散。Sandier 与 Serfaty 在研究 Ginzburg–Landau 涡旋（第二类超导体中的 Abrikosov 格子）时定义了重整化能量（renormalized energy）`@@M@@W(E)@@`：在每个电荷处减去对数自能，再取单位面积能量的上极限。他们猜想密度一时其最小子恰为三角形格子（triangular lattice，即 Abrikosov 格子）；此前数值证据充分、也只在周期构型内做过严格比较，一般证明缺失。另一条战线是球面 `@@M@@S^2@@` 上 `@@M@@n@@` 点对数能量（Thomson 问题的对数版本）最小值的渐近展开（asymptotic expansion）：Brauchart–Hardin–Saff（2012）猜想其线性项系数；Bétermin–Sandier（2018）证明该系数等于一个显式常数，当且仅当三角形格子最小化上述平面重整化能量。两条线在此汇合：证明前者即同时解决后者。

## 主要结果

记 `@@M@@\Lambda_\triangle=\sqrt{2/\sqrt3}\,\bigl(\mathbb{Z}(1,0)+\mathbb{Z}(\tfrac12,\tfrac{\sqrt3}{2})\bigr)@@` 为协体积（covolume）为一的三角形格子，`@@M@@E_\triangle@@` 为其周期位势的梯度场。容许类 `@@M@@\mathcal A_1@@` 由满足 `@@M@@\operatorname{div}E=2\pi(\nu_\Lambda-1)@@`、`@@M@@\curl E=0@@` 且电荷计数有二次增长界的无旋场组成。

**定理 1（全平面）**：对每个容许场 `@@M@@W(E)\ge W(E_\triangle)@@`，且下确界被 `@@M@@E_\triangle@@` 实现；对竞争者不加任何分离性、周期性或胞腔有界性假设，也排除 `@@M@@W(E)=-\infty@@`。

**定理 2（方环面）**：在方环面（square torus）`@@M@@T_n=\mathbb{R}^2/(\sqrt n\,\mathbb{Z}^2)@@` 上，任意 `@@M@@n@@` 个不同点的格林函数（Green function）位势能量满足 `@@M@@\mathcal W_n(h)\ge n\,W(E_\triangle)@@`。

**推论（球面对数能量）**：令 `@@M@@E_{\log}(n)@@` 为 `@@M@@S^2@@` 上 `@@M@@n@@` 点有序对（ordered pairs）对数能量和的最小值，则

`@@M@@DE_{\log}(n)=\Bigl(\tfrac12-\log2\Bigr)n^2-\tfrac n2\log n+C_{\mathrm{BHS}}\,n+o(n),\qquad C_{\mathrm{BHS}}=2\log2+\tfrac12\log\tfrac23+3\log\frac{\sqrt\pi}{\Gamma(1/3)}.@@`

这证明了 Brauchart–Hardin–Saff 猜想的 `@@M@@d=2@@` 情形。

## 证明思路

证明分四步：全平面化归、有限环面几何、对偶校准恒等式、计算机验证的标量不等式。

先做化归。利用 Sandier–Serfaty 的周期逼近定理，把对任意全平面场的下界化为方环面上的一致下界；关键在核对两套归一化的换算（差 `@@M@@2\pi@@` 因子与 `@@M@@\tfrac14\log(2\pi)@@` 修正），并处理固定宽度的方形截断：借助质量转移方法（mass-displacement method）与 Struwe 型 `@@M@@L^r@@` 估计控制边界带误差，并由此推出电荷密度渐近为一。

再做有限环面几何。环面上极小构型存在；用带屏蔽项的位势（在半径 `@@M@@r_\ast=1/\sqrt\pi@@`、面积恰为一的圆盘外消失）配合极小值原理（minimum principle）证明极小构型中任两点距离至少 `@@M@@r_\ast@@`。分离性只用于极小构型——其他构型由极小性自动继承下界，这就是主定理无需分离假设的原因。于是各点 Voronoi 胞腔（Voronoi cell）为凸多边形，Euler 计数给出平均每点至多六个面—边扇区（sector），且全部扇区面积之和为 `@@M@@n@@`、角度之和为 `@@M@@2\pi n@@`。

核心是构造拼合的对偶试验位势（trial potential）。用同一组径向函数 `@@M@@B,D_i@@` 在每个扇区写出 `@@M@@H@@`，它在相邻胞腔共享的 Voronoi 边与顶点射线上的迹自动匹配，在每个电荷附近 `@@M@@H=-\log r+O(r^2)@@` 且常数项为零。由此得到精确恒等式 `@@M@@\mathcal W_n(h)=\sum_S J(S)+\tfrac12\int|\nabla(h-H)|^2\ge\sum_S J(S)@@`，把无穷维变分问题化为逐扇区的标量泛函估计，对偶项中匹配的对数奇性恰好消去、只剩非负平方。径向函数取自三角形格林函数的展开（`@@M@@z^{6m}@@` 模式，系数为格点和），使 `@@M@@H@@` 在正六边形内恰为 `@@M@@h_\triangle-C_\triangle@@`；选常数 `@@M@@\lambda,\mu@@` 使校准后的原函数 `@@M@@g_d(x)@@` 在正扇区代表点 `@@M@@(p,x_0)@@` 处驻定，并令 `@@M@@K=2g_p(x_0)<0@@`。在单点三角形环面上六片扇区全部正则且 `@@M@@\nabla H=\nabla h_\triangle@@`，非负项消失，得精确等式 `@@M@@6K+\lambda+2\pi\mu=W(E_\triangle)@@`。

难点在垂足落在边外的符号扇区（端点角可为负）。论文用两个标量不等式绕过：`@@M@@2g_d(x)\ge K@@` 与导数核 `@@M@@G@@` 的负部积分 `@@M@@\le -K@@`，二者合成 `@@M@@J(S)\ge K+\lambda A(S)+\mu\theta(S)@@` 对一切扇区成立。对至多 `@@M@@6n@@` 片扇区求和并用面积、角度恒等式，得 `@@M@@\mathcal W_n(h)\ge n(6K+\lambda+2\pi\mu)=nW(E_\triangle)@@`。

最后，两个标量不等式由严格区间算术（interval arithmetic）验证：整数区间分母 `@@M@@2^{144}@@`、三阶导数区间 jet、保留 38 个模式、被略模式用可求和解析尾界覆盖，中点求积与插值误差显式加回；在包含驻点的小矩形上验证海塞矩阵（Hessian）正定，凸性加驻定性给出该矩形上的最小值。程序 certificate.cpp 的一次完整受护运行记录于 verification/README.md。定理 2 与化归命题合并即得定理 1，再经 Bétermin–Sandier 的等价定理得球面常数。

## 可信度与备注

本篇主结果暂无形式化证明；标量不等式依赖区间算术程序的一次记录运行，论文明确区分程序输出与源码—公式对应关系的数学论证，后者仍需人工核验。论文不分类所有达到最小能量的构型，不含唯一性或缺陷排除断言，也不构造球面近似最优点集或给出算法。结果族 090 的姊妹篇（三角形格子对完全单调位势的普遍最优性、长程 Riesz 能量 `@@M@@`0\lt s\lt 2`@@` 等）与本文方法各自独立而结论互相印证，共同支撑三角形格子是二维最优点阵的图景。OpenAI 官方声明：未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
