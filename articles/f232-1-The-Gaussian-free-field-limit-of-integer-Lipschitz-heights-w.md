---
layout: default
title: "The Gaussian free field limit of integer Lipschitz heights with two-arc boundary data"
family: "232"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Gaussian free field limit of integer Lipschitz heights with two-arc boundary data

> 结果族 232：Gaussian fields and interfaces for triangular-lattice Lipschitz heights　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一块圆蛋糕，边界上半圈写着 +1、下半圈写着 −1；往内部随机填充"高度"，要求相邻差只能是 0 或 2。切开看剖面：这块随机地形 = 一块确定的平滑斜坡 + 高斯自由场式的普适涨落。这正是 Schramm 2007 年问题清单第 2.2 问的"场"部分。

**关键词卡片**

- 奇整数高度（odd integer heights）：边界两弧取 +1/−1、相邻差为 0 或 2 的均匀随机填充。
- 调和延拓（harmonic extension）：边界值的"最公平"内插 `@@M@@\bar g@@`——每点的值恰等于周围平均值。
- 高斯自由场（Gaussian free field, GFF）：涨落部分；协方差由区域上的 Dirichlet Green 函数给出。
- 反射正性（reflection positivity）：关于某条格点行镜像时概率律满足的特殊正性，是提取谱信息的钥匙。
- 谱和规则（spectral sum rule）：论文导出的恒等式，把归一化常数逼成 `@@M@@c_*/|p|^2@@` 的形式。

**看个具体例子**

定理：`@@M@@h_\delta \Rightarrow \bar g+\sigma\Phi_D@@`，即随机高度 = 调和斜坡 `@@M@@\bar g@@` 加 `@@M@@\sigma@@` 倍 GFF。归一化 `@@M@@\sigma=4\pi\sqrt{c_*}@@`，而 `@@M@@c_*@@` 由一个绝对收敛的有限体积级数给出——级数每一项都是有限六角区域内构形的整数计数之比，原则上真能一步步算出来，且与区域大小无关。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="15">两弧边界 +1 / −1 的随机高度地形</text>
  <ellipse cx="280" cy="150" rx="200" ry="95" fill="#fcfcfc" stroke="#999" stroke-width="1"/>
  <path d="M80 150 A200 95 0 0 1 480 150" fill="none" stroke="#c62828" stroke-width="6"/>
  <path d="M80 150 A200 95 0 0 0 480 150" fill="none" stroke="#1565c0" stroke-width="6"/>
  <path d="M80 150 C150 100 210 200 280 150 C350 100 410 200 480 150" fill="none" stroke="#2e7d32" stroke-width="2.5" stroke-dasharray="7 5"/>
  <circle cx="80" cy="150" r="5" fill="#333"/>
  <circle cx="480" cy="150" r="5" fill="#333"/>
  <text x="64" y="140" font-size="14">a</text>
  <text x="490" y="140" font-size="14">b</text>
  <text x="280" y="45" text-anchor="middle" font-size="14" fill="#c62828">边界弧取 +1</text>
  <text x="280" y="262" text-anchor="middle" font-size="14" fill="#1565c0">边界弧取 −1</text>
  <text x="280" y="112" text-anchor="middle" font-size="13" fill="#2e7d32">高度 = 0 的等高线（围绕直径随机摆动）</text>
</svg>

</div>

**为什么值得关心**

它解决了 Schramm 问题 2.2 的场部分；更重要的是归一化常数第一次有了显式可算的公式——此前连它是否存在、是否依赖区域都无法确定。涨落常数只依赖单位格点模型本身，换区域、换边界逼近方式都不变，这是"普适性"最具体的一种兑现方式。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
证明了三角格点上边界两弧分别取 `@@M@@+1@@` 与 `@@M@@-1@@` 的均匀奇整数 Lipschitz 高度场，中心化后收敛到 Dirichlet 高斯自由场的普适倍数，归一化常数由绝对收敛的有限体积计数公式显式给出，从而解决 Schramm 问题 2.2 的场部分。

## 问题背景
Schramm 在 2006 年提出、2007 年发表的问题集之问题 2.2 问：光滑单连通域上、边界被两标记点分成两弧并分别赋值 `@@M@@+1@@` 与 `@@M@@-1@@` 的三角格点奇整数高度函数（相邻差为 `@@M@@0@@` 或 `@@M@@2@@`），其高度场与零等高线是否有高斯自由场与 SLE 型标度极限。此前 Glazman–Manolescu 为均匀整数 Lipschitz 模型建立了两自旋表示、正相联与回路尺度估计并证明对数涨落；Glazman–Lammers 随后在更大参数区间证明离域化（delocalization），并把 GFF 极限作为猜想讨论。困难在于：对数涨落只是方差层面的证据，不足以确定极限定律——还需在稀有钉扎条件下做比较、识别协方差常数、控制强加的两弧边界值并确定全部联合矩。光滑一致凸梯度势的已知场极限定理（Miller）不覆盖这种每条边都有硬约束的整数模型。

## 主要结果
主定理：设 `@@M@@D@@` 为带两个不同标记边界点的有界光滑单连通平面区域，`@@M@@D_\delta@@` 为标记边界参数化一致收敛的三角格点多边形逼近，`@@M@@h_\delta@@` 服从两弧边界的奇高度均匀律。则存在只依赖单位三角格点模型的常数 `@@M@@\sigma>0@@`，使得 `@@M@@h_\delta\Rightarrow\bar g+\sigma\Phi_D@@` 在 `@@M@@\mathcal D'(D)@@` 中成立，其中 `@@M@@\bar g@@` 是边界数据 `@@M@@+1/-1@@` 的有界调和延拓（bounded harmonic extension），`@@M@@\Phi_D@@` 是协方差为 `@@M@@G_D=(-\Delta_D)^{-1}@@` 的 Dirichlet 高斯自由场（Gaussian free field, GFF）；等价地，整数高度 `@@M@@H_\delta=(h_\delta-1)/2@@` 收敛到 `@@M@@m+\sqrt v\,\Phi_D@@`，且 `@@M@@\sigma^2=4v@@`、`@@M@@v=(2\pi)^2c_*@@`、`@@M@@\sigma=4\pi\sqrt{c_*}@@`。任意有限组检验函数的联合矩收敛。归一化由绝对收敛的有限体积级数给出：`@@M@@c_*=\frac1\pi\sum_j\bigl[b_{j0}+\sum_s(b_{j,s+1}-b_{js})\bigr]>0@@`，其中 `@@M@@b_{js}@@` 是指定光滑截断的 Fourier 系数乘以有限六角区域内双自旋构形对的均匀计数平均，全为有限整数计数之比，与区域无关。

## 证明思路
证明的主轴是识别子列极限 `@@M@@H@@` 的全部矩。第一步由反射正性（reflection positivity）提取谱信息：条件于一条格点行上的自旋值时，两侧构形独立且互为镜像，故 `@@M@@\E[\overline{\Theta F}F]@@` 是半正定 Hermitian 型；两个反射的复合给出步长 `@@M@@\sqrt3@@` 的法向平移，它在反射商完备化后是正自伴压缩算子。由此协方差可写成法向频率上 Cauchy 核的正混合。关键的谱和规则（spectral sum rule）在于：第四阶角调和函数在六次格点旋转下平均为零，而同一函数的 Cauchy 平均除一个可和格点误差外非负；两者相减得到非负可积的"色散缺陷"，迫使每个小频率谱极限的密度必为 `@@M@@c_*/|p|^2@@`；带符号角向求和再唯一确定 `@@M@@c_*@@`，并顺带导出上述有限体积归一化公式。同时，支撑在反射线一侧的 Laplace 检验与其镜像的协方差趋于零，得到"反射零化"恒等式。第二步移动稀有销钉（pin）：高度模 `@@M@@4@@` 编码为两个 `@@M@@\pm1@@` 自旋，边界销钉规定这些符号；由于典型插入点被边界销钉环绕而无法全部置于一条反射线之后，先在边界窗口开缺口、只钉住两个自旋之一，用分离钉扎事件的乘性比较控制反射范数，再借正转移算子的幂把平移在多个法向解析延拓（方法承袭六顶点模型的对应论证），让销钉移过插入点；承载规定符号的自旋回路随后闭合缺口，并迫使各不相连的钉扎弧取同一高度偏移。第三步恢复原始边界条件：附着估计从合成的均值比较推导出开水平线连接，停止规则保证未被检查区域的条件 Gibbs 律不变；在常值边界弧附近取参考平均，其在极限中收敛到规定值，恰好固定了局部高度差所遗留的加性常数。最后，矩函数在各变量远离碰撞点处调和、只有对数碰撞奇性；局部切割混合与平面协方差定出每个奇性系数，减去相应 Green 函数得到高斯矩递推（Wick 递推），而一致矩界同时提供紧性与从矩收敛到分布收敛的过渡。

## 可信度与备注
本结果暂无形式化证明；按 OpenAI 官方声明"未经形式化的结果可能有问题"，应以社区核验为准。族内姊妹篇互相支撑：本篇与零边界加权模型篇共用"反射正性—销钉移动—矩方法"骨架但各自独立成文、互不引用对方定理为前提；实值 Lipschitz 曲面篇则另辟路线解决 Schramm 问题 2.3。问题 2.2 的界面部分（零等高线的 SLE 收敛）不在本篇范围之内。

{% endraw %}
