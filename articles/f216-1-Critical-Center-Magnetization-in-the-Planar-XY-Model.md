---
layout: default
title: "Critical Center Magnetization in the Planar XY Model"
family: "216"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Critical Center Magnetization in the Planar XY Model

> 结果族 216：Critical and near-critical XY scaling and BKT universality　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一间方形大厅，四面墙上的指南针全被固定朝同一个方向；大厅正中央那枚自由的指南针会被带动多少？这篇论文算的就是这个数：在恰好"临界"的温度下，中心箭头的平均偏转正比于 `@@M@@n^{-1/8}@@`，再乘一个慢吞吞的因子 `@@M@@(\log n)^{1/16}@@`——大厅边长翻倍，偏转只缩小不到一成，慢得出奇。

**关键词卡片**

- 中心磁化（center magnetization）：边界全部对齐时，中心箭头平均朝边界方向偏转的幅度
- 边界条件（boundary condition）：预先规定边界自旋方向的"外部指令"
- 临界逆温度（critical inverse temperature）：温度参数的分界值 `@@M@@b_c@@`，此处关联恰不指数衰减
- 对偶高度模型（dual height model）：经 Fourier 展开把箭头模型翻译成的整值"台阶"模型
- 条件定理（conditional theorem）：显式引用三篇姊妹篇输入之后成立的定理

**看个具体例子**

设大厅边长为 `@@M@@n@@` 个格距，定理给出 `@@M@@a_n=A_{\rm XY}\,n^{-1/8}(\log n)^{1/16}@@`。数字版（`@@M@@A_{\rm XY}=1@@`、自然对数、`@@M@@n=10^6@@`）：`@@M@@n^{-1/8}=10^{-0.75}\approx 0.18@@`，`@@M@@(\log n)^{1/16}\approx 1.17@@`，合计 `@@M@@a_n\approx 0.21@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<rect x="180" y="30" width="220" height="220" fill="none" stroke="#444444" stroke-width="2"/>
<line x1="205" y1="44" x2="230" y2="44" stroke="#1a6faa" stroke-width="3"/>
<polygon points="230,39 240,44 230,49" fill="#1a6faa"/>
<line x1="265" y1="44" x2="290" y2="44" stroke="#1a6faa" stroke-width="3"/>
<polygon points="290,39 300,44 290,49" fill="#1a6faa"/>
<line x1="325" y1="44" x2="350" y2="44" stroke="#1a6faa" stroke-width="3"/>
<polygon points="350,39 360,44 350,49" fill="#1a6faa"/>
<line x1="205" y1="236" x2="230" y2="236" stroke="#1a6faa" stroke-width="3"/>
<polygon points="230,231 240,236 230,241" fill="#1a6faa"/>
<line x1="265" y1="236" x2="290" y2="236" stroke="#1a6faa" stroke-width="3"/>
<polygon points="290,231 300,236 290,241" fill="#1a6faa"/>
<line x1="325" y1="236" x2="350" y2="236" stroke="#1a6faa" stroke-width="3"/>
<polygon points="350,231 360,236 350,241" fill="#1a6faa"/>
<line x1="192" y1="100" x2="217" y2="100" stroke="#1a6faa" stroke-width="3"/>
<polygon points="217,95 227,100 217,105" fill="#1a6faa"/>
<line x1="192" y1="180" x2="217" y2="180" stroke="#1a6faa" stroke-width="3"/>
<polygon points="217,175 227,180 217,185" fill="#1a6faa"/>
<line x1="353" y1="100" x2="378" y2="100" stroke="#1a6faa" stroke-width="3"/>
<polygon points="378,95 388,100 378,105" fill="#1a6faa"/>
<line x1="353" y1="180" x2="378" y2="180" stroke="#1a6faa" stroke-width="3"/>
<polygon points="378,175 388,180 378,185" fill="#1a6faa"/>
<line x1="262" y1="140" x2="282" y2="140" stroke="#c0392b" stroke-width="3" stroke-dasharray="5,4"/>
<polygon points="282,136 292,140 282,144" fill="#c0392b"/>
<text x="408" y="48" font-size="14" fill="#1a6faa">边界箭头全对齐</text>
<text x="302" y="168" font-size="14" fill="#c0392b">中心：微弱偏转</text>
<text x="140" y="270" font-size="14" fill="#333333">aₙ ≈ A·n^(−1/8)·(log n)^(1/16)</text>
<text x="60" y="22" font-size="15" fill="#333333">边长 n 的大厅，中心偏转有多小？</text>
</svg>

</div>

**为什么值得关心**

这个 `@@M@@(\log n)^{1/16}@@` 正是姊妹篇"临界两点关联带 `@@M@@(\log r)^{1/8}@@`"的平方来源：中心磁化先带上 `@@M@@1/16@@` 次对数，平方后恰好变成 `@@M@@1/8@@`，三篇论文在同一个常数上互相咬合成完整证据链。证明要跨两道坎：高度模型的观测密度不能先验地假设很小，作者在相互重叠的有限尺度区间上引入截断观测来处理；带环量缺陷进入递归会产生难以估计的归一化因子，办法是让两个尺寸的方盒共用同一历史，使所有标量因子在比值中精确相消。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明：边界自旋全部对齐的方盒中，临界 XY 模型的中心磁化（center magnetization）满足 `@@M@@a_n=A_{\rm XY}n^{-1/8}(\log n)^{1/16}(1+o(1))@@`。在三篇姊妹篇的输入之上，它定出了此前未知的对数修正因子，为临界两点关联的 `@@M@@(\log r)^{1/8}@@` 提供了"平方"来源。

## 问题背景

临界点附近的二维 XY 模型没有自发磁化，但对外边界仍有响应：把方盒边界角度全钉在零，中心自旋的平均偏转即中心磁化。Berezinskii（1971）、Kosterlitz–Thouless（1973）与 Kosterlitz（1974）的重整化群分析预言了临界指数与对数修正；José–Kadanoff–Kirkpatrick–Nelson（1977）把模型与 Coulomb 气及周期场描述的联系显式化；Kenna–Irving 记录了磁化率的有限尺寸标度预言 `@@M@@\chi_N\asymp N^{7/4}(\log N)^{1/8}@@`。严格方法方面，Falco 在稀薄 Coulomb 气中构造了 `@@M@@1/j@@` 边缘轨迹并证明分数电荷关联的乘性对数，Dimock–Hurd 控制了 `@@M@@\beta>8\pi@@` 的 sine-Gordon 模型，但二者的观测对象均不能直接移植到磁学可观测量。对齐边界下的单点渐近从未被定出——幂律指数本身不能决定归一化，慢变乘子在固定比值的标度极限中不可见。

## 主要结果

定理（显式条件于三篇姊妹篇的输入）：在边长为 `@@M@@n@@`、边界角度全为零、内部键全保留的方盒中，于质量定义的临界逆温度（critical inverse temperature）`@@M@@b_c@@` 处，中心磁化 `@@M@@a_n=\E^0_{n,b_c}\cos\theta_0@@` 满足 `@@M@@a_n=A_{\rm XY}\,n^{-1/8}(\log n)^{1/16}(1+o(1))@@`，其中 `@@M@@A_{\rm XY}\in(0,\infty)@@` 为模型特定常数。论文特别强调：临界磁化收缩与标量因子的精确相消是在本文中证明的，并非低温磁流定理的推论。

## 证明思路

Fourier 对偶把 `@@M@@a_n@@` 写成整值高度模型（高度取值 `@@M@@2\pi\Z@@`、Bessel 增量权）的配分函数比：分子带绕中心 `@@M@@2\pi@@` 的环量，分母零环量。证明要跨过两道坎。第一道是高度模型的观测密度无法先验地假设在高斯大场范数下很小。办法是把证明组织在相互重叠的有限尺度区间上：目标指标 `@@M@@J@@` 很大时，在边长与 `@@M@@J^3@@` 同阶的胞上引入观测，用光滑截断剔除异常大的相邻观测差；截断误差是 `@@M@@e^{-J^3}@@` 量级，而历史中物理方盒的对数边长只有 `@@M@@J@@` 量级，于是剩余相互作用在高度映射的完整解析范数下变小。第二道是带环量缺陷进入递归时可能产生很大的归一化因子，而估计它是不必要的额外负担。办法是让边长 `@@M@@2n@@` 与 `@@M@@2Ln@@` 的两个对偶方盒共用同一历史、同一停止尺度：环量插入在整个精确分块代数中保持线性，插入附近产生的所有标量因子在两个方盒中完全相同，在比值中精确相消，其大小无关紧要；残留插入收缩足够快，配合姊妹篇自旋场论文给出的 `@@M@@a_n@@` 粗糙正下界，其贡献相对也可忽略。

轨迹控制：用物理高度律自身的两个可观测量——长波涨落的方差与平均高度的特征系数——在公共绝对尺度上比较不同历史的坐标，从而不依赖高度标度极限的速率；结合边缘递归得运行梯度系数 `@@M@@t_j=\frac{1}{2j\log L}+O(\frac{\log j}{j^2})@@`，其中 `@@M@@L@@` 为固定的二的幂。最后是纯高斯的终端计算：环量能量给出主幂 `@@M@@n^{-1/8}@@`，它与 `@@M@@t_j@@` 的耦合给出对数修正；对 `@@M@@n=L^j/2@@` 有 `@@M@@\log a_{Ln}-\log a_n=-\frac{\log L}{8}+\frac{1}{16j}+O(j^{-1-\epsilon})@@`。误差的绝对可求和性——而非对初始磁化归一化的任何估计——给出有限正幅度。终了用自旋场论文的比值极限把几何尺寸的结果转移到所有整数。

## 可信度与备注

这是明确的条件定理：引用姊妹篇的局部积分映射、临界高度系数 `@@M@@8\pi@@` 与混合几何高度极限、恒同嵌套比较（含 `@@M@@a_n@@` 的粗糙正下界与比值极限），缺一不可。它与批内第一篇互相印证：第一篇在自由盒子路线中独立推出同一中心渐近并用于两点关联，本文是对齐边界版本的系统陈述；自旋场一篇则以 `@@M@@a_n@@` 为归一化常数。结果未形式化；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
