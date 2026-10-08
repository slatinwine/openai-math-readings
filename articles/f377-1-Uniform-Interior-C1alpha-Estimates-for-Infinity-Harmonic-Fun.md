---
layout: default
title: "Uniform Interior $C^{1,\\alpha}$ Estimates for Infinity-Harmonic Functions"
family: "377"
discipline: "Partial differential equations"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform Interior `@@M@@C^{1,\alpha}@@` Estimates for Infinity-Harmonic Functions

> 结果族 377：Interior `@@M@@C^{1,\alpha}@@` regularity for infinity-harmonic functions　·　学科：Partial differential equations　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

在两根高矮不同的桩子之间铺一块"最省料"的坡面板，要求任何一段都无法被偷偷换成更平缓的——这样的极限省料坡面就是无穷调和函数。这篇论文证明：在三维及更高维空间里，拿放大镜看这种坡面的任何一点，它都越来越像一张倾斜的平面——坡度不但存在，还随位置连续变化，永不出现折角。

**关键词卡片**

- 无穷调和函数（infinity-harmonic function）：满足 `@@M@@\Delta_\infty u=0@@` 的函数；方程只管"沿坡面下坡方向"的弯曲，是最优 Lipschitz 延拓的极限形态。
- 拔河博弈（tug-of-war）：两队轮流随机拉动一个点的博弈，这场游戏的公平价值函数恰好无穷调和。
- Hölder 半范数（Hölder seminorm）：给 `@@M@@|f(x)-f(y)|@@` 与距离的 `@@M@@\alpha@@` 次方之比设上限，是"变化速度"的量化刻度。
- 振幅（oscillation）：函数在区域上的最大值减最小值；定理中唯一出现的"大小"。
- `@@M@@C^{1,\alpha}@@` 正则性（`@@M@@C^{1,\alpha}@@` regularity）：导数存在，且以距离的 `@@M@@\alpha@@` 次方速率连续变化——比"可微"再高一档的光滑度。

**看个具体例子**

Aronsson 经典例子 `@@M@@u(x_1,x_2)=|x_1|^{4/3}-|x_2|^{4/3}@@` 是无穷调和的：在原点附近挪动 `@@M@@h=0.001@@`，坡度就变化约 `@@M@@h^{1/3}\approx 0.1@@`——这个立方根关系说明指数不可能超过 `@@M@@1/3@@`。论文定理的数字版：若 `@@M@@u@@` 在单位球 `@@M@@B_1@@` 上无穷调和、振幅为 1，则对 `@@M@@x,y\in B_{1/2}@@`
`@@M@@D|\nabla u(x)-\nabla u(y)|\le C_d\,|x-y|^{\alpha_d},\qquad \alpha_d\in(0,\tfrac13]@@`
常数 `@@M@@C_d@@` 与指数 `@@M@@\alpha_d@@` 只依赖维数，对所有这样的 `@@M@@u@@` 一致成立。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="35" y1="235" x2="255" y2="235" stroke="#bbb" stroke-width="1.5"/>
<line x1="35" y1="235" x2="35" y2="45" stroke="#bbb" stroke-width="1.5"/>
<path d="M40,210 C80,150 110,190 145,150 C180,110 205,160 250,120" fill="none" stroke="#3a76b8" stroke-width="2.5"/>
<circle cx="145" cy="150" r="5" fill="#c0392b"/>
<text x="153" y="143" font-size="13" fill="#c0392b">P</text>
<rect x="128" y="135" width="34" height="30" fill="none" stroke="#e0a030" stroke-width="1.5"/>
<text x="90" y="45" font-size="13" fill="#888">任意点 P 处逐级放大</text>
<line x1="128" y1="135" x2="298" y2="32" stroke="#e0a030" stroke-width="1"/>
<line x1="162" y1="165" x2="443" y2="122" stroke="#e0a030" stroke-width="1"/>
<rect x="298" y="32" width="145" height="90" fill="none" stroke="#666" stroke-width="1.5"/>
<text x="370" y="24" font-size="13" text-anchor="middle" fill="#888">放大：弯曲明显变缓</text>
<path d="M303,100 C335,55 360,80 390,55 C415,35 430,60 438,48" fill="none" stroke="#3a76b8" stroke-width="2.5"/>
<rect x="352" y="50" width="26" height="22" fill="none" stroke="#e0a030" stroke-width="1.5"/>
<line x1="352" y1="50" x2="298" y2="150" stroke="#e0a030" stroke-width="1"/>
<line x1="378" y1="72" x2="535" y2="250" stroke="#e0a030" stroke-width="1"/>
<rect x="298" y="150" width="240" height="105" fill="none" stroke="#666" stroke-width="1.5"/>
<line x1="315" y1="225" x2="520" y2="180" stroke="#3a76b8" stroke-width="2.5"/>
<line x1="315" y1="229" x2="520" y2="184" stroke="#c0392b" stroke-width="1.2" stroke-dasharray="6,5"/>
<text x="418" y="268" font-size="13" text-anchor="middle" fill="#555">再放大：几乎是一张倾斜平面（坡度连续变化）</text>
<text x="145" y="258" font-size="13" text-anchor="middle" fill="#555">无穷调和函数 u 的图像</text>
</svg>

</div>

**为什么值得关心**

自 2011 年已知任意维数中这种函数处处可微，但导数是否连续在 `@@M@@d\ge 3@@` 一直悬而未决；本文补上了这块拼图，而且整套光滑标尺只看维数、不看具体解。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明：任意维数 `@@M@@d\ge3@@` 中，有界无穷调和函数（infinity-harmonic）满足只依赖维数的一致内部 `@@M@@C^{1,\alpha_d}@@` 估计（`@@M@@\alpha_d\in(0,1/3]@@`）：梯度在 `@@M@@B_{1/2}@@` 上的上确界范数与 Hölder 半范数被 `@@M@@B_1@@` 上振幅乘以维数常数控制，从而高维无穷调和函数都局部 `@@M@@C^1@@`。

## 问题背景

无穷拉普拉斯方程 `@@M@@\Delta_\infty u=\langle D^2u\,\nabla u,\nabla u\rangle=\sum_{i,j}u_iu_ju_{ij}@@` 只含沿梯度方向的二阶导数，源自 Aronsson 1967 年关于绝对极小化子（absolute minimizer，即局部最优 Lipschitz 扩张）的工作，也是随机"拔河博弈"（tug-of-war）值函数的方程。Jensen 于 1993 年建立其粘性解（viscosity solution）理论与 Dirichlet 问题唯一性，Crandall–Evans–Gariepy 的锥比较（comparison with cones）给出局部 Lipschitz 界。但方程的极端退化性使梯度正则性成为难题：平面情形 Savin（2005）证得梯度连续，Evans–Savin（2008）给出内部 `@@M@@C^{1,\alpha}@@` 估计；Evans–Smart（2011）证明任意维数处处可微，但导数的连续性在 `@@M@@d\ge3@@` 一直悬而未决。Aronsson 的经典例子 `@@M@@|x_1|^{4/3}-|x_2|^{4/3}@@` 是无穷调和的，其梯度恰以 `@@M@@|h|^{1/3}@@` 速率变化，表明指数不可能超过 `@@M@@1/3@@`。

## 主要结果

主定理：对每个整数 `@@M@@d\ge3@@`，存在 `@@M@@\alpha_d\in(0,1/3]@@` 与有限常数 `@@M@@C_d@@`，使得单位球 `@@M@@B_1\subset\mathbb{R}^d@@` 上每个有界无穷调和函数 `@@M@@u\in C(B_1)@@` 属于 `@@M@@C^{1,\alpha_d}(B_{1/2})@@`，且
`@@M@@D\|\nabla u\|_{L^\infty(B_{1/2})}+[\nabla u]_{C^{0,\alpha_d}(B_{1/2})}\le C_d\,\mathrm{osc}_{B_1}u,@@`
其中 `@@M@@\mathrm{osc}_{B_1}u=\sup u-\inf u@@` 为振幅（oscillation），`@@M@@[\cdot]_{C^{0,\alpha}}@@` 为 Hölder 半范数。常数与指数只依赖维数，对所有解一致。指数由紧性论证产生、并不显式；论文不主张端点 `@@M@@\alpha=1/3@@` 或任何边界正则性。直接推论：`@@M@@d\ge3@@` 时每个开集上的无穷调和函数都局部 `@@M@@C^1@@`，填补了 Evans–Smart"处处可微但导数连续性未知"留下的空缺。

## 证明思路

整体是"紧性归约 + Liouville 刚性"的反证框架。先归一化振幅不超过 `@@M@@1@@`，并添加线性坐标把 `@@M@@u@@` 提升为 `@@M@@U(y,b)=u(y)+b@@`——提升后仍是无穷调和函数，且保证拟合斜率非零。锥比较给出解族一致 Lipschitz 界，经典爆破引理保证固定中心的仿射爆破（affine blow-up）是线性函数；论文新证的"三点估计"是第一关键：对接近仿射函数的中点亏损用 Ishii–Lions 的和的定理（theorem of sums）做粘性检验，检验函数中的凹项 `@@M@@f(r)=r-\tfrac18r^{3/2}@@` 二阶导数趋于 `@@M@@-\infty@@`，从而把慢尺度上的仿射逼近一致地压到快得多的尺度，得到整个归一化解族的一致（定性）平坦性 `@@M@@b(s)\to0@@`。

其次在轴向半径 `@@M@@r@@`、横向半径 `@@M@@\sqrt\lambda r@@` 的细圆柱上测量平坦性，容许误差 `@@M@@\lambda r@@`。若对一切指数幂率都失效，则可选取尺度使得 `@@M@@\lambda_i@@` 在 `@@M@@(z_i,r_i)@@` 处不可行、而 `@@M@@32\lambda_i@@` 在一切邻近中心与半径一致可行；经各向异性伸缩（Evans–Savin 伸缩）`@@M@@U_i\bigl(z_i+r_i(\sqrt{\lambda_i}x,t)\bigr)=U_i(z_i)+r_ic_i\bigl(t+\lambda_iv_i(x,t)\bigr)@@` 取极限，得到整个空间上的极限解 `@@M@@v@@`，满足极限方程 `@@M@@F[v]=D^2v[(\nabla_xv,1)]=0@@`，且在每点、每半径都容许带剪切的仿射拟合；若 `@@M@@v@@` 仿射，则当初失败的拟合反而成立，故 `@@M@@v@@` 非仿射。

核心是 Liouville 定理：这种"处处可拟合"的整解必为仿射。先对水平 Jensen 亏损（加权平均值超出重心值的盈余，除以构型的均方根半径）取上确界得 `@@M@@\kappa>0@@`，经再中心化得到极值解；其重心包络 `@@M@@\Cenv_t v@@`（对水平切片加权平均、减去方差项 `@@M@@\frac{r^2}{2t}@@` 的上确界）满足 `@@M@@W=\Cenv_t v-\tfrac{\kappa^2t}{2}\le v@@`，仍是极限方程的次解（subsolution），且在正时刻接触 `@@M@@v@@` 并保留正间隙 `@@M@@\kappa^2/2@@`——方差惩罚沿粘性检验方向是仿射的，故次解性质在平均化后存活。前后向二次包络的斜率关于长度单调、有公共极限 `@@M@@H_v@@`。随后构造"公平游走"：每步以对等方式在前向优化子与后向优化子之间选择，漂移不等式控制两个速度与公共参考速度之差的平方和，该量在拟合标架变换下不变，且参考速度有对数界；游走把接触传播到一列递减的正时刻，并凝聚到一个 `@@M@@H_v@@` 有限的终点。在终点处按接触尺度反复重新归一化再取极限，其包络斜率在一切长度上恒为常数，刚性引理（前向与后向等式速度重合，配合有向二次比较）迫使极限仿射，与保留的正间隙矛盾。最后，幂率 `@@M@@b(s)\le Bs^\gamma@@` 使相邻尺度的拟合斜率以 `@@M@@r^{\gamma/2}@@` 速率收敛，而内切球半径 `@@M@@\sqrt\lambda r@@` 与拟合误差 `@@M@@\lambda r@@` 之比给出 `@@M@@\alpha_d=\gamma/(2+\gamma)\le1/3@@`。

## 可信度与备注

本文暂无 Lean 形式化证明；按 OpenAI 官方声明，"未经形式化的结果可能有问题"，结论请以社区核验为准。结果族 377 目前仅此一篇，无姊妹篇直接互证，但论证环环相扣：锥比较、三点估计、各向异性紧性、包络接触与刚性各自承担一环，且立足于 Jensen、Crandall–Evans–Gariepy、Evans–Savin、Evans–Smart 等经过检验的经典理论。文中还与 2026 年 Brustad、Xu 的平面端点 `@@M@@1/3@@` 结果互相呼应：平面端点与高维非显式指数恰是同一图景的两块拼图。

{% endraw %}
