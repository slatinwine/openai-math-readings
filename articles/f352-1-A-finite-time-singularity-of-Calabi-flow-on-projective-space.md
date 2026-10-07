---
layout: default
title: "A finite-time singularity of Calabi flow on projective space"
family: "352"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A finite-time singularity of Calabi flow on projective space

> 结果族 352：A finite-time singularity of Calabi flow　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在 \(\mathbb{CP}^{10}\) 的 Fubini–Study 类中构造出光滑 Kähler 度量，其 Calabi 流在有限时刻 \(T_*\) 前数量曲率按 \((T_*-t)^{-1/2}\) 爆破，推翻 Chen 的 Calabi 流光滑长时间存在猜想——即使在含常数量曲率度量的类中也会产生奇性。

## 问题背景

Calabi 流（Calabi flow）是 Calabi 于 1982 年提出的四阶抛物方程 \(\partial_t\phi=S(\omega(t))-\bar S\)，目的是在固定 Kähler 类中寻找典则度量。曲面上已由 Chruściel（1991）、Chen（2001）、Struwe（2002）证明整体存在并收敛；高维只有 Chen–He（2008）的短时存在、唯一性与近常数量曲率度量的稳定性，以及若干延拓判据：数量曲率或 Ricci 曲率一致有界即可延拓（Chen–He、Chen–Cheng），更弱的 \(L^p\) 判据见 Li–Zhang–Zheng 等。Chen 的猜想断言：从任意光滑初始度量出发，流对所有正时间光滑存在。此前高维既无证明也无反例；弱解理论（Streets 的最小移动解；Berman–Darvis–Lu 的 \(d_1\) 收敛）也不保证穿过有限时刻的光滑延拓。本文给出第一个反例。

## 主要结果

主定理：存在 \(\mathbb{CP}^{10}\) 上光滑的 \(U(10)\)-不变 Kähler 形式 \(\omega_0\in[\omega_{\mathrm{FS}}]\)，其极大光滑 Calabi 流的存在区间为 \([0,T_*)\)，\(0<T_*<\infty\)，且有点 \(p\) 与常数 \(a>0\) 使数量曲率（scalar curvature）满足 \(S(\omega(t))(p)\sim a(T_*-t)^{-1/2}\)（\(t\uparrow T_*\)）。由于 Fubini–Study 度量本身具有常数量曲率（constant scalar curvature），这同时否定了 Chen–Cheng 特别关注的"类中含 cscK 度量时光滑整体存在"的问题。推论：与常数量曲率的平稳因子作乘积，在一切复维数 \(n\geq10\) 的 \(\mathbb{CP}^{10}\times\mathbb{CP}^{n-10}\) 上、含 Kähler–Einstein 度量的类中同样出现有限时间奇性。

## 证明思路

全文策略是：先把流约化为标量方程，再造平坦极限的精确收缩解，最后在紧流形上修正并读出奇性。

先做几何约化。沿 Calabi 径向 ansatz 与 Hwang–Singer 动量表述（momentum formulation），取动量坐标 \(x=\Phi'(\log|Z|^2)\in(0,1)\)，写 \(v=x(1-x)+x^2(1-x)^2H\)，Calabi 流等价于标量四阶方程 \(H_t+(1+v_*H)^2\mathcal{A}H=0\)。关键恒等式是核心点处 \(S(t,p)=110(1-H(t,0))\)：只需让 \(H(t,0)\) 爆破。区间端点的正则性条件被吸收进辅助球面 \(\Sigma=S^{29}\) 上的光滑椭圆算子 \(\mathcal{A}\)，其核心处的平坦极限是双调和算子 \(\hat{\mathcal{A}}=\frac1{16}\Delta^2\)。

再构造自相似轮廓。设 \(F(t,x)=\rho^{-1}h(x/\rho)\)，\(\rho=\sqrt{-t}\)，\(h(y)=(G(y)-1)/y\)，平坦方程化为轮廓 ODE \(Q(y\partial_y)(G-1)=\frac{y^2}{2}(\frac1G-\frac1c)\)。文中证明存在光滑正、上下有界的 \(G\)，满足 \(G(0)=1\)、\(G'(0)<0\)、原点解析、在无穷远有 \(y^{-2}\) 渐近展开：原点的两参数解析族经"精确有理算术证书"认证的有限射击（validated Taylor integration 框架）推进到 \(s=56\)，与半直线上由压缩不动点得到的衰减尾通过 Brouwer 不动点匹配。于是 \(F(t,0)=\rho^{-1}G'(0)\) 按 \((-t)^{-1/2}\) 发散。

然后在紧流形上修正 \(H=F+V\)。先为平坦线性化构造"古代"右逆（定义在全部负时间）：相似坐标下时间一演化算子是常数系数演化的紧扰动，解析 Fredholm 理论给出离散谱；谱分解后，稳定模由过去递归求解，有限个不稳定模由"未来"的强迫确定——因不指定初值，这一选择无需任何稳定性定理。再作内外拼接：外层正向 Cauchy 问题的源被安排得恰好抵消内层截断换位子，剩余误差由缩小核心半径 \(\beta\) 与时间参数 \(\eta=T/\beta^4\) 而变小；Neumann 级数给出一致右逆，随后在控制四阶空间导数及其时间 Hölder 半范（不含时间导数）的空间中作压缩不动点，缺失的时间导数由方程本身找回。正性由恒等式 \(1+v_*F=x+(1-x)G(x/\rho)\) 保证，且 \(V(t,0)=O(\rho^{-1+\delta})\)，不遮蔽主项。

最后取 \(t=-T/2\) 的切片为初始度量。由 Chen–He 的唯一性，任何光滑流必与构造的流重合；若越过 \(T_*\) 仍光滑，紧流形上数量曲率应有界，与爆破矛盾。故极大存在时间恰为 \(T_*\)，速率 \(a=-110\,G'(0)>0\)。

## 可信度与备注

本文暂无形式化证明；但附录提供了可执行的精确算术证书（仅用 Python 标准库与整数运算），完整认证轮廓构造中有限射击的全部不等式，属可复现的计算机辅助证明，其余部分为传统的抛物估计、谱理论与不动点论证。本结果族（352）仅此一篇手稿；其结论与 Chen–He、Chen–Cheng、Li–Zhang–Zheng 的延拓判据相洽——奇性恰以数量曲率 \(L^\infty\) 爆破的形式出现，未被任何已知判据排除。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
