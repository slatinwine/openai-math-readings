---
layout: default
title: "A Torsion-Free Group Algebra with Zero Divisors"
family: "196"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Torsion-Free Group Algebra with Zero Divisors

> 结果族 196：A counterexample to Kaplansky's zero-divisor conjecture　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

整数世界有条铁律：两数相乘为零，必有一个是零。可有些代数系统不守规矩——钟表算术里 `@@M@@2\times3=0@@`（模 6）。把一个群的乘法表"线性摊开"成代数，就得到群代数：元素是群元素的"形式和"，乘法按分配律展开。Kaplansky 猜了八十多年：只要群没有有限阶元素，群代数就该像整数一样规矩。此前所有正面结果都限于特殊群类，本文造出了一般无挠群的反例。

**关键词卡片**

- 群代数（group algebra）：以群元素为基、按群乘法相乘的代数。
- 零因子（zero divisor）：相乘得零的一对非零元素。
- 无挠群（torsion-free group）：没有有限阶元素的群。
- 有限展示（finitely presented）：有限个生成元加有限条关系就能写清的群。
- `@@M@@\mathbb F_2@@`：只有 0 和 1 的域，`@@M@@1+1=0@@`，"奇偶相消"的舞台。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="32" text-anchor="middle" font-size="14">构造骨架：玫瑰 F + 两个锥</text>
<path d="M150 150 C 105 95 60 95 60 150 C 60 205 105 205 150 150" fill="none" stroke="#222" stroke-width="2"/>
<path d="M150 150 C 195 95 240 95 240 150 C 240 205 195 205 150 150" fill="none" stroke="#222" stroke-width="2"/>
<circle cx="150" cy="150" r="5" fill="#222"/>
<text x="150" y="243" text-anchor="middle" font-size="13">玫瑰 F：生成元所在</text>
<line x1="245" y1="128" x2="332" y2="98" stroke="#555" stroke-width="1.5" stroke-dasharray="5 4"/>
<line x1="245" y1="172" x2="332" y2="202" stroke="#555" stroke-width="1.5" stroke-dasharray="5 4"/>
<text x="288" y="112" font-size="12" fill="#555">浸入</text>
<text x="288" y="200" font-size="12" fill="#555">浸入</text>
<ellipse cx="405" cy="85" rx="70" ry="38" fill="none" stroke="#3050a0" stroke-width="2"/>
<text x="405" y="80" text-anchor="middle" font-size="13" fill="#3050a0">图 Γ_A 的锥</text>
<text x="405" y="99" text-anchor="middle" font-size="13" fill="#3050a0">α = Σ g_x</text>
<ellipse cx="405" cy="215" rx="70" ry="38" fill="none" stroke="#b03030" stroke-width="2"/>
<text x="405" y="210" text-anchor="middle" font-size="13" fill="#b03030">图 Γ_B 的锥</text>
<text x="405" y="229" text-anchor="middle" font-size="13" fill="#b03030">β = Σ h_y⁻¹</text>
<text x="280" y="268" text-anchor="middle" font-size="13">奇偶设计 ⇒ 在 F₂ 上 α·β = 0，而 α、β ≠ 0，且 G 无挠</text>
</svg>

</div>

对照：若元素 `@@M@@g@@` 有 3 阶，`@@M@@(1-g)(1+g+g^2)=1-g^3=0@@`，零因子唾手可得；难的正是群无挠。构造如上图：两幅图浸入同一朵"玫瑰"，各自加锥粘成二维复形并取基本群得 `@@M@@G@@`；奇偶设计让乘积在 `@@M@@\mathbb F_2@@` 中成对相消，得 `@@M@@\alpha\beta=0@@`。

**为什么值得关心**

八十多年的老猜想被推翻，而且证明已通过 Lean 形式化机器验证——颠覆性结果配上机器检查，可信度极高。不过构造是概率式的存在性证明：它保证合适的图匹配存在，尚未给出能直接读出具体群展示与显式零因子的匹配。

> 已 Lean 形式化

## 一句话结论

本文构造了一个有限展示且无挠（torsion-free）的群 `@@M@@G@@`，并给出 `@@M@@\mathbb F_2[G]@@` 中非零元素 `@@M@@\alpha,\beta@@` 使 `@@M@@\alpha\beta=0@@`，推翻了悬置八十余年的 Kaplansky 零因子猜想；`@@M@@G@@` 还拥有有限二维分类空间，无挠性一并坐实。

## 问题背景

群代数（group algebra）`@@M@@K[G]@@` 以群元素为基、乘法由群律双线性扩张而成。若 `@@M@@g@@` 有有限阶 `@@M@@m>1@@`，则 `@@M@@(1-g)(1+g+\cdots+g^{m-1})=0@@` 给出显然的零因子（zero divisor）；Kaplansky 零因子猜想（问题源自 Higman 1940 年博士论文，Kaplansky 1957 年正式列出）断言：`@@M@@G@@` 无挠、`@@M@@K@@` 为域时不存在其他零因子。此前的正面结果都限于特殊群类：Higman 的每个非平凡子群都能满射到 `@@M@@\mathbb Z@@` 的群、Kropholler–Linnell–Moody 的无挠初等可解群（elementary amenable）、Fisher–Sánchez-Peralta 的三维流形群等。Rips 与 Segev 1987 年造出不具唯一乘积性质（unique-product property）的无挠群，但在 `@@M@@\mathbb F_2@@` 上非唯一乘积只保证重数大于一，未必为偶数，故不直接给出零因子。一般情形的症结在于：缺少一个能让系数完全成对相消的机制。

## 主要结果

定理：存在有限展示（finitely presented）的无挠群 `@@M@@G@@` 及非零的 `@@M@@\alpha,\beta\in\mathbb F_2[G]@@`，使 `@@M@@\alpha\beta=0@@`；而且 `@@M@@G@@` 容许一个有限的二维分类空间（classifying space）`@@M@@X@@`，即 `@@M@@G=\pi_1(X)@@` 且万有覆盖可缩。由此 `@@M@@G@@` 自然不具唯一乘积性质。须注意：这是概率式的存在性证明——它保证合适的图匹配存在，但未给出能从中读出具体群展示与显式零因子的匹配。

## 证明思路

构造分三层：代数机制、奇偶设计、双重保障。

先建机制。取两个有限图 `@@M@@\Gamma_A,\Gamma_B@@`，各自浸入（immersion）一朵"玫瑰"`@@M@@F@@`——每对互逆生成元占一条边的单顶点图——每条边读一个带符号标号。把每个连通分量的抽象锥（abstract cone）沿标号映射粘到 `@@M@@F@@` 上，得到二维复形 `@@M@@X@@`，令 `@@M@@G=\pi_1(X)@@`。加锥恰好杀死图中所有闭路的标号，于是从根 `@@M@@x_A@@` 到分量内任一点 `@@M@@x@@` 的路标号 `@@M@@g_x@@` 与路径选取无关。令 `@@M@@\alpha=\sum_{x\in A'}g_x@@`，`@@M@@\beta=\sum_{y\in B'}h_y^{-1}@@`。

再做相消。规定每个顶点的出边标号集 `@@M@@S_x@@`，使 `@@M@@|S_x\cap S_y|@@` 对每对 `@@M@@x\in A@@`、`@@M@@y\in B@@` 皆为奇数：这用 `@@M@@q=128@@` 的有限射影平面（projective plane）实现——`@@M@@v=q^2+q+1=16513@@` 条线两两交于 `@@M@@1@@` 或 `@@M@@129@@` 点，再配三个附加字母按精确比例 `@@M@@p=(q+1)/v@@` 分布。奇偶性由"类型"内建，随机匹配只负责几何。在 `@@M@@A'\times B'@@` 上以"同一标号 `@@M@@t@@` 同步各走一步"建图：一步把 `@@M@@g_xh_y^{-1}@@` 换成 `@@M@@(g_xt)(h_yt)^{-1}=g_xh_y^{-1}@@`，保持不变；每个顶点度数是奇数 `@@M@@|S_x\cap S_y|@@`，由度数和公式每个连通分量含偶数个顶点，而同分量各顶点对 `@@M@@\alpha\beta@@` 贡献同一群元素，在特征 `@@M@@2@@` 下成对抵消，故 `@@M@@\alpha\beta=0@@`。

最后补两大保障。其一，`@@M@@\alpha,\beta\ne0@@`：需证从根到任一别的顶点的标号非平凡（根分离），使根成为恒等系数的唯一贡献者。其二，`@@M@@G@@` 无挠：需证 `@@M@@\pi_2(X)=0@@`，使 `@@M@@X@@` 成为分类空间。二者均归结为排除成对路径出现的特定平面构型。概率侧：以围长（girth）`@@M@@\ge L=\lfloor c\log n\rfloor@@` 条件化随机匹配，利用平方词衰减 `@@M@@\sum_W P(W)^2\le e^{-2\delta h}@@`（`@@M@@\delta=1/600@@` 可行）的"有界模式估计"——固定界 `@@M@@K,C,I@@` 后，至多 `@@M@@K@@` 条路、总长 `@@M@@L\le H\le CL@@`、至多 `@@M@@I@@` 个区间对、未配对位置 `@@M@@b\le\varepsilon H@@` 的系统出现概率趋于零；诀窍是按边的遍历重数分层，使各层 `@@M@@n@@` 的指数总和不超过零，再用网格分块与鸽笼对齐把区间配对化为词约束，最后把各阶段期望上界相乘以选出一个期望极小的阶段，全程不要求层间独立性。拓扑侧：取边界总长极小的锥图（cone picture），玫瑰边内点的横截原像给出字母的完全逆配对；若某弧连接同一条被提升边的两次出现，带状手术（band surgery）可使边界长严格减二，与极小性矛盾，故配对必落在不同的底层边上——所得"约化球面排布"恰是概率侧排除的有界模式。收尾：万有覆盖可缩；若 `@@M@@G@@` 含素数阶元，循环群的周期上同调与长度为二的自由 `@@M@@\mathbb ZG@@`-分解矛盾，故 `@@M@@G@@` 无挠，主定理证毕。

## 可信度与备注

论文标注主结果已通过 Lean 形式化验证，这对颠覆性结果是极强的可信度信号。本批次中结果族 196 仅收录本文一篇，论证自成体系；它与 Gardam 的单位猜想反例、Mineyev 的几何判据等同方向工作互为参照，但既不依赖也未复用其结论。依 OpenAI 官方声明，未经形式化的结果可能有问题；本文核心定理已形式化，但概率构造只证存在性、未产出具体的群展示与显式零因子，寻求显式例子是自然的后续课题。

{% endraw %}
