---
layout: default
title: "Generalized Cartan–Hadamard isoperimetry and Euclidean equality rigidity"
family: "337"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Generalized Cartan–Hadamard isoperimetry and Euclidean equality rigidity

> 结果族 337：Sharp Cartan–Hadamard isoperimetry and rigidity　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文在所有维数证明了广义 Cartan–Hadamard 等周猜想：截面曲率不超过 `@@M@@\kappa\le 0@@` 的完备单连通流形中，任何有限体积、有限周长的集合，其周长不小于曲率 `@@M@@\kappa@@` 模型空间中等体积球的面积；欧氏情形取等当且仅当该区域（带诱导度量）等距于标准欧氏球。

## 问题背景

Cartan–Hadamard 流形（Cartan–Hadamard manifold）指截面曲率（sectional curvature）非正的完备单连通黎曼流形。负曲率使空间"张开"，直观上围住同样体积应耗费更多边界面积，由此产生猜想：若 `@@M@@\mathrm{Sec}\le\kappa\le 0@@`，则任何区域的边界面积不小于曲率 `@@M@@\kappa@@` 的单连通空间形式（模型空间）中等体积测地球的面积。二维情形由 Weil（1926）与 Beckenbach–Radó 的次调和函数方法解决，Bol（1941）处理了非零模型曲率；Kleiner（1992）证明三维（含取等），Croke（1984）证明四维欧氏比较。更高维数长期卡住：任意区域边界的平均曲率（mean curvature）完全不可控，仅有的测地球体积比较无法比较形状各异的区域。近年推进仍带限制——Chen–Ghomi–Wang 做到 3–9 维，Wheeler 需要负曲率尺度受控变差，Agnoletto 等人只得小体积情形——全维数、任意 `@@M@@\kappa@@` 的无限制结论此前并未成立。

## 主要结果

**主定理**：设 `@@M@@n\ge2@@`、`@@M@@\kappa\le0@@`，`@@M@@(M^n,g)@@` 完备、单连通、光滑且 `@@M@@\mathrm{Sec}_g\le\kappa@@`。则每个体积与周长都有限的可测集 `@@M@@E\subset M@@` 满足
`@@M@@DP_g(E)\ge \mathcal I_{\sqrt{-\kappa}}\bigl(\operatorname{Vol}_g(E)\bigr),@@`
其中周长取环境周长（ambient perimeter）`@@M@@P_g(E)=|D\chi_E|_g(M)@@`，即指示函数的变差测度；`@@M@@\mathcal I_b@@` 是曲率 `@@M@@-b^2@@` 模型空间的等周轮廓（isoperimetric profile），即等体积球的面积函数。`@@M@@\kappa=0@@` 时即经典形式 `@@M@@P_g(E)\ge n\omega_n^{1/n}\operatorname{Vol}_g(E)^{(n-1)/n}@@`。不等式对无界的有限体积集也成立，比较的是全部周长（含与证明中限制球的接触部分）；模型空间中的球取等。

**欧氏取等刚性**：`@@M@@\kappa=0@@` 时，有界、正有限体积、有限周长的集合取等，当且仅当它在零测集意义下等于一个开区域，且该区域带诱导黎曼度量等距于标准欧氏球。刚性确定了整个取等区域上的度量，但不要求区域外的流形平坦。

**推论**：对 `@@M@@1<p<\infty@@`，有模型球 Faber–Krahn 与 Saint–Venant 比较 `@@M@@\lambda_{1,p}(D)\ge\lambda_{1,p}(B_\kappa(|D|))@@`、`@@M@@T_p(D)\le T_p(B_\kappa(|D|))@@`，由等周输入配合 Nobili–Violo 的等测径向重排得到。

## 证明思路

全文的解析引擎是一条超曲面上的临界 Sobolev 不等式：在 `@@M@@\mathrm{Sec}\le-b^2@@`（`@@M@@b\in\{0,1\}@@`）的流形中，对 `@@M@@m=n-1\ge3@@` 的局部 `@@M@@C^{1,1}@@` 浸入超曲面 `@@M@@\Sigma@@`，
`@@M@@D\int_\Sigma\bigl(c|\nabla_\Sigma v|^2+m(h^2-b^2)v^2\bigr)\,d\sigma\ge Y_m\Bigl(\int_\Sigma|v|^q\,d\sigma\Bigr)^{2/q},@@`
其中 `@@M@@h@@` 为归一化平均曲率，`@@M@@Y_m=ms_m^{2/m}@@` 正是 Aubin–Talenti 的锐欧氏临界 Sobolev 常数。证明先构造取值于单位球面、带正权重的径向映射，其对数 Hessian 与映射微分满足相容的曲率比较界，代入超曲面能量后配成完全平方；若临界商低于欧氏阈值，局部紧性加 Brézis–Lieb 分裂会产生一个 Dirichlet 极小化子，以球面坐标作变分（与 Li–Yau 共形体积论证同源的中心与坐标变分）逼出一阶恒等式，其带权零延拓梯度为零而质量非零，与 Dirichlet 条件矛盾。

有了这条不等式，再正面处理"任意边界平均曲率不可控"的障碍：采用 Kleiner 的受限轮廓（confined profile）策略，在大测地球内固定体积极小化周长，并沿用 Ghomi–Spruck 的正则性框架——极小边界分解为正则部分 `@@M@@\Sigma@@` 与奇异集 `@@M@@S@@`，全部周长落在 `@@M@@\Sigma@@` 上；自由变分识别出 `@@M@@h=I'(v)/m@@`，内变分控制与限制球接触处的曲率。为让常数测试函数合法（`@@M@@\Sigma@@` 可能不紧），先用"删除小球、再以固定自由补块上的流修补体积"的论证得到奇异点附近的面积增长 `@@M@@\sigma(\Sigma\cap B_r)\le Cr^m@@`，再利用奇异维数不超过 `@@M@@n-8@@`（故 `@@M@@\mathcal H^{m-2}(S)=0@@`）构造 Dirichlet 能量趋零的截断函数。常数测试代入后得到一条标量微分不等式
`@@M@@DI'(v)\ge m\sqrt{b^2+\bigl(s_m/I(v)\bigr)^{2/m}},@@`
其积分恰好就是模型比较：直接验证逆轮廓函数 `@@M@@\mathcal W_b@@` 的导数与右端互为倒数，用链式法则积分即得。二维、三维由经典输入补足，配合严格 BV 逼近、有限体积截断与度量缩放处理任意 `@@M@@\kappa<0@@`。

刚性部分先用已证比较把有界取等集化为局部几乎极小化子，经 Antonelli–Pasqualetto–Pozzetta 正则性与差商论证得到 `@@M@@C^{1,1}@@` 边界，各分量带同一常数平均曲率。`@@M@@m\ge3@@` 时取等使常数测试成为锐谱间隙 `@@M@@\int|\nabla_\Sigma\phi|^2\ge\frac{m}{R^2}\int\phi^2@@`；在平方距离重心 `@@M@@p@@` 处取对数坐标（`@@M@@d\log_p@@` 压缩）得上二阶矩估计，径向通量恒等式给下二阶矩估计，两界相夹强迫外法向径向且半径恒定，边界落入测地球面；二维改用周期 Wirtinger 不等式，三维改用穿孔径向通量，得到切空间中球心可能偏心的球面。最后由 BV 相位常值性识别出内部区域，指数映射的拉回度量处处支配欧氏度量而体积相等，迫使体积密度恒为 1，于是拉回度量本身是欧氏的——整个取等区域等距于欧氏球。

## 可信度与备注

本文主结果暂无形式化证明。同族姊妹篇《Sharp integral fillings in CAT(0) spaces》以积分流方法独立推出维数 `@@M@@\ge3@@` 的欧氏 Cartan–Hadamard 猜想，与本文的光滑方法结论交叠、相互印证；本文则进一步覆盖任意 `@@M@@\kappa\le0@@`、无界有限体积集与完整的取等分类。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
