---
layout: default
title: "An integral scalar curvature bound for real simplicial volume"
family: "335"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An integral scalar curvature bound for real simplicial volume

> 结果族 335：Gromov's integral scalar-curvature bound for simplicial volume　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Gromov 1986 年提出的积分标量曲率不等式：对每个 \(n\ge 3\) 有常数 \(a_n\gt 0\)，使任意闭定向光滑 \(n\)-流形上任一黎曼度量都满足 \(\int_M(\mathrm{Scal}_g^-)^{n/2}\,dV_g\ge a_n\|M\|\)，把单纯体积这一拓扑复杂度与负标量曲率的总量直接定量挂钩。

## 问题背景

闭定向流形 \(M\) 的**单纯体积** (simplicial volume) \(\|M\|\) 定义为实基本类 \([M]_{\R}\) 在 \(\ell^1\)-半范数下的下确界，即用实奇异循环表示基本类所需系数绝对值之和的最小值，它度量流形的拓扑复杂度。Gromov 在 1982 年借助有界上同调 (bounded cohomology) 把这个不变量与 Ricci 曲率下界控制的黎曼体积联系起来。标量曲率 (scalar curvature) 远弱于 Ricci 曲率，几乎不保留方向信息，因此"标量曲率下界仍能控制单纯体积"是局部几何与整体拓扑之间出人意料的强联系。Gromov 在 1986 年明确提出本文所证的积分形式（原文 Conjecture 3.A 的式 \((8')\)）：用标量曲率负部的 \(n/2\) 次幂的积分给单纯体积一个只依赖维数的上界。此前只有条件性结果：Braun–Sauer 在万有覆盖单位球体积一致有界时证明宏观版本；Ma–Wang–Xie–Yu–Zhu 证明万有覆盖为 spin 时非负标量曲率迫使单纯体积为零；Min–Zheng–Zhu 对每个闭 Kähler 曲面（及一族辛四流形）证明了积分估计。

## 主要结果

**主定理**：对每个整数 \(n\ge 3\)，存在常数 \(a_n\gt 0\)（只依赖 \(n\)），使得每个闭连通定向光滑 \(n\)-流形 \(M\) 与其上任意光滑黎曼度量 \(g\) 满足

\[\int_M(\mathrm{Scal}_g^-)^{n/2}\,dV_g\ge a_n\|M\|,\]

其中 \(\mathrm{Scal}_g^-=\max\{0,-\mathrm{Scal}_g\}\) 是标量曲率的负部，\(\|M\|\) 是实单纯体积。该积分在度量的常值缩放下不变，同时记录负曲率的大小与集中程度，允许负曲率集中在小区域内。直接推论：若 \(\mathrm{Scal}_g\ge -n(n-1)\)，则 \(\mathrm{Vol}_g(M)\ge a_n\,[n(n-1)]^{-n/2}\|M\|\)，且常数对所有流形与所有度量一致。

## 证明思路

先做共形约化：设 \(\|M\|\gt 0\)，姊妹篇的消失定理（非负标量曲度 \(\Rightarrow\) 实单纯体积为零）迫使每个共形类的 Yamabe 极小化度量 (Yamabe minimizer) 具有负标量曲率，归一化为 \(\mathrm{Scal}_h=-1\)；再由 Hölder 不等式得 \(\mathrm{Vol}_h(M)\le\int_M(\mathrm{Scal}_g^-)^{n/2}dV_g\)。于是只需证 \(\mathrm{Scal}_g=-1\) 时 \(\|M\|\le C_n\mathrm{Vol}_g(M)\)。再搭建检测器：由 \(\ell^1\)-半范数与上确界范数的对偶性及映射定理，取范数 \(\le 1\) 的齐次交错闭上链 \(c\)，其与基本类的配对值 \(I\ge\|M\|/2\)；把 \(c\) 实现为概率单纯形上的闭 \(n\)-形式 \(\eta\)，由万有覆盖上的等变根概率映射 (root probability map) \(F\)（\(\sum_\ell F_\ell^2=1\)）拉回，积分恰为 \(I\)。然后用图变形做"熵式"迭代：同时改造叶上度量 \(h\) 与权 \(\phi\) 而保持测度 \(e^{\phi}dV_h\)，核心量是 Perelman 修正标量曲率 \(\mathcal S(h,\phi)=\mathrm{Scal}_h-2\Delta_h\phi-|d\phi|_h^2\)；反复变形后得到叶式不等式 \(\mathcal S(h,\phi)\ge -C_n+2W-n\log E+E\,\mathfrak e\)，其中 \(W=\log(dV_h/\rho)\)、保留密度 \(\rho\le dV_g\)、\(\mathfrak e=e_h(F)\) 是映射能量，大系数 \(E\) 放大能量项。配套的度数定理用 \(\mu\)-泡泛函 (\(\mu\)-bubble functional) 的极小边界逐坐标降维，估计到立方体的映射度；高维奇异超曲面以加权距离势函数把残差映射推离奇异集来处理。最后是转移步骤：在随机旋转的立方网格上取胞腔系数 \(\int_C\eta\)，做无偏舍入 (unbiased rounding) 保持闭上链关系且期望不变，用 Gaifullin 的反射 permutohedral 消解 (reflected permutohedral resolution) 把对偶立方链加倍并光滑化为带测度流形族；比较映射 \(G\) 的度数期望恰为 \(D_0I\)。切、法两个比较长度 \(L_T=b_*\sqrt E\)（\(m\) 个切向）与 \(L_N=b_*\sqrt{qE}\)（\(n\) 个法向）的选取让 \(E\) 的全部幂与体积密度精确相消，得 \(b_*^{-n}q^{-n/2}\rho\)；旋转平均配上形式的 Hilbert 范数界与球面矩的指数矩估计，缝合 (seam) 部分用其小坐标体积吸收，最终得 \(I\le C_n\int\rho\le C_n\mathrm{Vol}_g(M)\)。对 \(E\) 的下界要求只是 \(q\) 的初等函数（固定高度指数塔），故常数只依赖 \(n\)。

## 可信度与备注

本文与姊妹篇《Positive scalar curvature forces rational inessentiality》构成闭环：那篇的消失定理（非负标量曲率 \(\Rightarrow\) 实单纯体积为零）是本文唯一未自证的外部输入，本文在其上完成从定性消失到定量不等式的提升，两文合起来给出 Gromov 猜想的完整证明。两篇均无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
