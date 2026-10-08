---
layout: default
title: "A counterexample to the nearby Lagrangian conjecture"
family: "340"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to the nearby Lagrangian conjecture

> 结果族 340：A counterexample to the nearby Lagrangian conjecture　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一根绷直的琴弦悬在无穷长圆筒的正中。猜想曾认为：筒里任何一根与它"外形完全相同、松紧规矩全对"的新弦，都能不撞筒壁地连续滑回原位。这篇论文造出反例——外形再标准，也可能永远滑不回去。

**关键词卡片**

- 余切丛（cotangent bundle）：把每个位置点上所有可能动量打包而成的空间，物理里的相空间。
- 拉格朗日子流形（Lagrangian submanifold）：余切丛中与底空间同维、松紧与位置严格匹配的子空间。
- 精确（exact）：辛形式限制在其上可写成某个函数的微分，即"绕圈不做功"。
- 哈密顿同痕（Hamiltonian isotopy）：由能量函数驱动、可连续执行的一串形变。
- 零截面（zero section）：动量处处为零的那根弦，即底空间在相空间中的标准嵌入。

**看个具体例子**

取底流形 `@@M@@Q=S^9\times S^{N-1}@@`（`@@M@@N@@` 为充分大的偶数），论文构造出闭、精确、光滑嵌入的拉格朗日子流形 `@@M@@L@@`：它与 `@@M@@Q@@` 微分同胚（外形一样），却不能由零截面经任何紧支撑哈密顿同痕得到——障碍不在拓扑，而在嵌入相空间的方式。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<rect x="60" y="50" width="440" height="170" fill="#f7f7ff" stroke="#345" stroke-width="3"/>
<text x="170" y="38" font-size="15" fill="#345">余切丛 T*Q（相空间圆筒）</text>
<path d="M75 115 Q110 75 145 115 T215 115 T285 115 T355 115 T425 115 T485 115" stroke="#c33" stroke-width="4" fill="none"/>
<text x="175" y="70" font-size="14" fill="#c33">拉格朗日 L（外形与 Q 相同）</text>
<path d="M180 125 C190 155 210 165 230 178" stroke="#999" stroke-width="2" stroke-dasharray="6 5" fill="none"/>
<line x1="216" y1="160" x2="236" y2="180" stroke="#c33" stroke-width="2.5"/>
<line x1="236" y1="160" x2="216" y2="180" stroke="#c33" stroke-width="2.5"/>
<text x="255" y="175" font-size="14" fill="#999">任何紧支撑哈密顿同痕</text>
<text x="255" y="196" font-size="14" fill="#999">都无法把它送回零截面</text>
<line x1="75" y1="215" x2="485" y2="215" stroke="#345" stroke-width="4"/>
<text x="150" y="248" font-size="14" fill="#345">零截面 Q_0（绷直的琴弦）</text>
</svg>

</div>

**为什么值得关心**

推翻 Arnold 1986 年提出的辛几何核心猜想，说明既有必要条件在高维不足以为凭，为"拉格朗日纽结"划出真实边界。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明：存在充分大的偶数 `@@M@@N@@`，使 `@@M@@T^*(S^9\times S^{N-1})@@` 中有闭的、精确的、光滑嵌入的拉格朗日子流形，它与底流形微分同胚，却不能由零截面经紧支撑哈密顿同痕得到——推翻了无限制版的邻近拉格朗日猜想。

## 问题背景

设 `@@M@@Q@@` 为闭光滑流形，其余切丛（cotangent bundle）`@@M@@T^*Q@@` 带有典范刘维尔形式 `@@M@@\lambda@@`。阿诺德（Arnold）1986 年讨论"拉格朗日纽结"时提出邻近拉格朗日猜想（nearby Lagrangian conjecture）：`@@M@@T^*Q@@` 中每个闭的、精确（exact，`@@M@@\lambda|_L=df@@`）嵌入拉格朗日子流形（Lagrangian submanifold）是否都哈密顿同痕（Hamiltonian isotopy）于零截面？这是辛刚性理论的核心检验问题。此前已知的多是必要条件：Hofer 与 Laudenbach–Sikorav 的相交定理、Abouzaid–Kragh 的单同伦等价定理、法向不变量（normal invariant）为 `@@M@@2@@`-挠等；低维也有肯定结果，如 Hind 关于 `@@M@@T^*S^2@@` 中拉格朗日球的定理，但一般情形只约束投影的拓扑。最近 Álvarez-Gavela–Igusa–Sullivan 在射流空间 `@@M@@J^1Q=T^*Q\times\R@@` 中构造出管挠率（tube torsion）非平凡而底投影同伦于微分同胚的勒让德子流形，但遗忘最后一维会引入双点，不构成余切丛反例。本文补上了从双点到嵌入的最后一步。

## 主要结果

定理 1：存在充分大的偶数 `@@M@@N@@`，取 `@@M@@Q=S^9\times S^{N-1}@@`，则 `@@M@@T^*Q@@` 中存在闭（紧致无边界）、精确、光滑嵌入的拉格朗日子流形 `@@M@@L@@`，使 `@@M@@L@@` 微分同胚于 `@@M@@Q@@`，且没有任何紧支撑哈密顿同痕把零截面 `@@M@@Q_0@@` 送到 `@@M@@L@@`。注意 `@@M@@Q@@` 与 `@@M@@L@@` 都连通且单连通：障碍不在 `@@M@@L@@` 的抽象拓扑，而在其嵌入余切丛的方式。构造以生成函数（generating family）语言给出：正则函数 `@@M@@F(q,w)@@` 的临界点集经 `@@M@@(q,w)\mapsto(q,d_qF)@@` 生成精确拉格朗日浸入，再辅以整体单射性论证即得嵌入。

## 证明思路

证明分四步。先制造"不可见但非平凡"的无穷远数据：二次型 `@@M@@q_{k,l}=-\|x\|^2+\|y\|^2@@` 在球面上的负区域（同伦型 `@@M@@S^{k-1}\times D^l@@`）称为光滑管（smooth tube），管函数经双参数稳定化构成稳定管空间 `@@M@@\mathbf T@@`，其负区域自带由 `@@M@@\gamma:\mathbf T\to BG@@` 分类的稳定球面纤维化（stable spherical fibration）。Waldhausen 管纤维化给出 `@@M@@H^s(*)\to\mathbf T\to BG@@`，结合参数化 h-余边缘（h-cobordism）定理 `@@M@@H^s(*)\simeq\Omega\mathrm{Wh}^{\mathrm{diff}}(*)@@`、Bott 周期律与 Adams 的 J-同态（J-homomorphism）单射性，代入 Rognes 算出的 `@@M@@\pi_{10}\mathrm{Wh}^{\mathrm{diff}}(*)@@`（二的幂部分阶 `@@M@@32@@`）与 `@@M@@\pi_9^S@@`（阶 `@@M@@8@@`），阶数比较表明连接同态不满，故有非零类 `@@M@@a\in\pi_9\mathbf T@@` 满足 `@@M@@\gamma_*a=0@@`：管族非平凡而球面纤维化已平凡。

再证核心障碍命题：`@@M@@S^9@@` 上齐次无穷远、每根纤维恰有一个非退化临界点、球面类为零的函数族，其稳定管类必为零。先用莫尔斯理论（Morse theory）把临界点处的负特征球与无穷远负区域做成纤维同伦等价，并把局部归一化为固定二次型；再在内、外球之间取正则零水平集，得一族 h-余边缘 `@@M@@C_b@@`，乘一个区间做稳定化并延拓进固定柱体 `@@M@@Y=S^{k+l-1}@@`，用带符号流场证明补集为乘积；由 Igusa 稳定性与连通度估计（维数 `@@M@@\geq38@@` 保证 `@@M@@\pi_9@@` 层面单射）反推原族为零，末以多重 jet 横截性（multijet transversality）把管核经嵌入同伦缩到固定标准管。

第三步把类 `@@M@@a@@` 实现为拉格朗日量：取 `@@M@@F(b,v,w)=G_b(w)-R(b)\beta(\|w\|/T)\langle v,w\rangle@@`，临界方程恰为 `@@M@@\nabla g_b(w)=R(b)v@@`，由齐次性，临界轨迹由 `@@M@@S^9\times S^{N-1}@@` 参数化。嵌入性靠两次"动量分离"：球面动量相等迫使重合分支之差落在 `@@M@@v@@` 张成的直线上；尺度 `@@M@@R(b)=\Lambda e^{K\theta(b)}@@` 随 `@@M@@b@@` 变化，条件 `@@M@@K\delta_0>C_1/c@@` 使底动量分离其余情形，而高度函数临界点附近族已是标准二次型、解唯一。紧致单射浸入即嵌入。

末步反证：若哈密顿同痕把零截面送到 `@@M@@L@@`，逆向同痕可紧支撑地扩张到 `@@M@@T^*\R^d@@`，使柱化后的 `@@M@@\mathcal L_0@@` 在中心板上成为零截面。把同痕细分为小步，每步生成新莫尔斯族并添加分裂型 `@@M@@(d,d)@@` 二次变量，对数截断与磨光引理保证无穷远数据的稳定类不变。最终族在中心板每点恰有一个非退化临界点；限制到固定 `@@M@@S^9@@` 切片后满足障碍命题全部假设，管类应为零——但仍等于 `@@M@@a\neq0@@`，矛盾。

## 可信度与备注

本文是 OpenAI 2026 年 9 月的预印本，主结果暂无 Lean 形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。结果族 340 现仅此一篇手稿，论证系统性倚重近年"生成函数—管空间—Waldhausen 代数 K-理论"主线的既有成果（Rognes 的 Whitehead 群计算、Igusa 稳定性、AIS 与 Courte–Porcelli 的技术工具）。全文构造、障碍、传输三部分互相咬合、结构自洽；个别步骤（如多重 jet 横截性的参数化应用）技术性较强，此处从略，宜对照原文核验。

{% endraw %}
