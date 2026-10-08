---
layout: default
title: "Average sensitivity of polynomial threshold functions"
family: "127"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Average sensitivity of polynomial threshold functions

> 结果族 127：Average sensitivity of polynomial threshold functions　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

想象一场只答"是/否"的电子投票:规则先给选票打分,再看分数正负定结论。如果随机改一票就常让结论翻盘,这规则就太"神经质"。论文证明:凡是由 `@@M@@d@@` 次多项式打分的规则,其神经质程度(平均灵敏度)至多 `@@M@@8d\sqrt n@@`——这正是悬了三十多年的 Gotsman–Linial 猜想的渐近形式。

**关键词卡片**

- 多项式阈值函数(polynomial threshold function):用至多 `@@M@@d@@` 次多项式打分、按符号输出是/否的函数 `@@M@@f=\operatorname{sgn}(p)@@`。
- 平均灵敏度(average sensitivity):随机输入下,翻转单个坐标会改变输出的坐标数期望,又叫总影响。
- 布尔立方体(Boolean cube):所有 `@@M@@n@@` 位 0/1 串组成的集合,函数的定义域。
- 半空间(halfspace):`@@M@@d=1@@` 的特例,最常见的线性打分规则。
- 噪声灵敏度(noise sensitivity):输入被随机扰动后结论翻转的概率,由主定理直接控制。

**看个具体例子**

三人多数票 `@@M@@f=@@`"至少两票为 1",画在三维布尔立方体上:

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="330" y="24" text-anchor="middle" font-size="15" fill="#333">三人多数票函数,画在三维布尔立方体上</text><circle cx="28" cy="50" r="7" fill="#fff" stroke="#333" stroke-width="2"/><text x="44" y="55" font-size="12" fill="#333">输出 0</text><circle cx="28" cy="72" r="7" fill="#333"/><text x="44" y="77" font-size="12" fill="#333">输出 1</text><line x1="20" y1="94" x2="42" y2="94" stroke="#c0392b" stroke-width="4"/><text x="48" y="99" font-size="12" fill="#c0392b">敏感边(共 6 条)</text><line x1="190" y1="215" x2="310" y2="215" stroke="#aaa" stroke-width="2"/><line x1="310" y1="215" x2="310" y2="95" stroke="#c0392b" stroke-width="4"/><line x1="310" y1="95" x2="190" y2="95" stroke="#c0392b" stroke-width="4"/><line x1="190" y1="95" x2="190" y2="215" stroke="#aaa" stroke-width="2"/><line x1="250" y1="170" x2="370" y2="170" stroke="#c0392b" stroke-width="4"/><line x1="370" y1="170" x2="370" y2="50" stroke="#aaa" stroke-width="2"/><line x1="370" y1="50" x2="250" y2="50" stroke="#aaa" stroke-width="2"/><line x1="250" y1="50" x2="250" y2="170" stroke="#c0392b" stroke-width="4"/><line x1="190" y1="215" x2="250" y2="170" stroke="#aaa" stroke-width="2"/><line x1="310" y1="215" x2="370" y2="170" stroke="#c0392b" stroke-width="4"/><line x1="310" y1="95" x2="370" y2="50" stroke="#aaa" stroke-width="2"/><line x1="190" y1="95" x2="250" y2="50" stroke="#c0392b" stroke-width="4"/><circle cx="190" cy="215" r="15" fill="#fff" stroke="#333" stroke-width="2"/><text x="190" y="219" text-anchor="middle" font-size="9">000</text><circle cx="310" cy="215" r="15" fill="#fff" stroke="#333" stroke-width="2"/><text x="310" y="219" text-anchor="middle" font-size="9">100</text><circle cx="310" cy="95" r="15" fill="#333"/><text x="310" y="99" text-anchor="middle" font-size="9" fill="#fff">110</text><circle cx="190" cy="95" r="15" fill="#fff" stroke="#333" stroke-width="2"/><text x="190" y="99" text-anchor="middle" font-size="9">010</text><circle cx="250" cy="170" r="15" fill="#fff" stroke="#333" stroke-width="2"/><text x="250" y="174" text-anchor="middle" font-size="9">001</text><circle cx="370" cy="170" r="15" fill="#333"/><text x="370" y="174" text-anchor="middle" font-size="9" fill="#fff">101</text><circle cx="370" cy="50" r="15" fill="#333"/><text x="370" y="54" text-anchor="middle" font-size="9" fill="#fff">111</text><circle cx="250" cy="50" r="15" fill="#333"/><text x="250" y="54" text-anchor="middle" font-size="9" fill="#fff">011</text><text x="280" y="252" text-anchor="middle" font-size="14" fill="#333">I(多数票) = 6/4 = 1.5 ≤ 8·1·√3 ≈ 13.9(定理上界)</text><text x="280" y="274" text-anchor="middle" font-size="13" fill="#666">红边两端恰好"一票之差",翻转该票即改变结论</text></svg>

</div>

红边是敏感边:恰好 6 条,故 `@@M@@I(f)=6/2^{3-1}=1.5@@`,远低于定理的 `@@M@@8\cdot1\cdot\sqrt3\approx13.9@@`。而取"中间 `@@M@@d@@` 层符号乘积"这类对称函数,灵敏度真能达到 `@@M@@\asymp d\sqrt n@@`,所以 `@@M@@d\sqrt n@@` 这个阶无法再改进。

**为什么值得关心**

多项式阈值函数是神经网络输出层、投票规则的数学缩影,灵敏度直接控制它们的可学习性与抗噪性。1994 年提出的猜想,精确形式已于 2018 年被反例推翻,渐近形式由本文完全确立。

> 已 Lean 形式化

## 一句话结论

本文证明：`@@M@@n@@` 维布尔立方体上次数至多 `@@M@@d@@` 的多项式阈值函数（polynomial threshold function），其平均灵敏度（average sensitivity）不超过 `@@M@@8d\sqrt n@@`，常数绝对、`@@M@@d@@` 可随 `@@M@@n@@` 增长。这确立了 Gotsman–Linial 猜想的渐近形式，并首次去掉了此前最佳界中的多对数损失。

## 问题背景

多项式阈值函数先用实多项式 `@@M@@p@@` 在布尔立方体 `@@M@@\{-1,1\}^n@@` 上求值、再取符号 `@@M@@f(x)=\sgn(p(x))@@`；次数 `@@M@@d=1@@` 时就是半空间（halfspace）。平均灵敏度又称总影响（total influence），`@@M@@I(f)=\sum_{i=1}^n\Pr\{f(X)\ne f(X^{\oplus i})\}@@`，度量随机输入下翻转单个坐标改变输出的期望次数，是布尔函数分析与学习理论的核心参数。Gotsman 与 Linial 在 1994 年猜想：`@@M@@n@@` 元、度至多 `@@M@@d@@` 的此类函数的灵敏度在某个以 `@@M@@x_1+\cdots+x_n@@` 为变量的对称函数处取到最大，量级为 `@@M@@d\sqrt n@@`。Chapman（2018）与 Kim–Maldonado–Wellens 各自构造反例，否定了其中"精确极值"的断言，但渐近界 `@@M@@O(d\sqrt n)@@` 一直悬而未决：此前最强的是 Kane 的 `@@M@@\sqrt n(\log n)^{O(d\log d)}2^{O(d^2\log d)}@@`，带有显著的多对数因子损失。本文一举消除该损失，给出对 `@@M@@d@@` 线性、对 `@@M@@n@@` 开方的干净界。

## 主要结果

**主定理**：设 `@@M@@n\ge1@@`、`@@M@@1\le d\le n@@`，`@@M@@p@@` 为度至多 `@@M@@d@@` 的实多重线性多项式（multilinear polynomial），`@@M@@f(x)=\sgn(p(x))@@`，约定 `@@M@@\sgn(0)=1@@`。则在均匀分布下 `@@M@@I(f)\le 8d\sqrt n@@`。常数 8 与 `@@M@@d,n@@` 均无关，`@@M@@d@@` 可随 `@@M@@n@@` 一起增长；`@@M@@p@@` 允许在立方体上取零，不施加任何正则性条件。阶是最优的：文中给出对称例子 `@@M@@p_J(x)=\prod_{j\in J}(t(x)-j-\tfrac12)@@`（`@@M@@t@@` 为取 `@@M@@+1@@` 的坐标个数，`@@M@@J@@` 为最靠近中心的 `@@M@@d@@` 个层指标），其灵敏度 `@@M@@I(\sgn p_J)\asymp d\sqrt n@@`，故在 `@@M@@1\le d\le\sqrt n@@` 范围内下界匹配。定理另有两个推论：其一，噪声灵敏度（noise sensitivity）满足 `@@M@@\operatorname{NS}_\eta(f)\le Cd\sqrt\eta@@`（`@@M@@0<\eta\le1/2@@`，`@@M@@C=8\sqrt2@@` 绝对常数），与 Kane 的高斯噪声结果相对应；其二，在输入边缘均匀、标签可任意对立的分布上，PTF 类有误差达 `@@M@@\mathrm{OPT}+\alpha@@` 的不可知学习（agnostic learning）算法，样本与时间关于 `@@M@@(n+1)^k@@`、`@@M@@1/\alpha@@`、`@@M@@\log(1/\delta)@@` 多项式，其中 `@@M@@k=\min\{n,\lceil Ad^2\alpha^{-2}\log(4/\alpha)\rceil\}@@`。

## 证明思路

证明由一个纯概率引理与一个有限维算子构造拼接而成，两者互不知晓对方存在，最后在装配步骤会合。

先看概率部件（第 2 节）：设 `@@M@@U,V@@` 同分布，有共同均值与方差 `@@M@@\sigma^2@@`，且几乎必然满足**单侧**约束 `@@M@@V-U\le a@@`（反方向不设限），则 `@@M@@\E(U-V)^2\le8a\sigma@@`。关键在取递增函数 `@@M@@g(t)=\tfrac12(t-m)|t-m|@@`（即 `@@M@@|t-m|@@` 的原函数），其增量控制平方位移：`@@M@@(v-u)^2/4\le g(v)-g(u)@@`；而同分布性保证 `@@M@@\E g(U)=\E g(V)@@`，正负增量相消，于是只需在 `@@M@@\{V>U\}@@` 上用单侧界与 Cauchy–Schwarz 收尾。全程不需要独立性。

再看算子部件（第 3–4 节）：在 `@@M@@\mathbb{C}^{\Omega}@@` 中以特征（character）`@@M@@\chi_S@@` 为基，令 `@@M@@V_k@@` 为度至多 `@@M@@k@@` 的特征张成的空间；乘以 `@@M@@\sqrt w@@`（`@@M@@w>0@@` 为任意权函数）后逐级取正交补，得到分级空间 `@@M@@E_k@@`，其维数固定为 `@@M@@\binom nk@@`。令 `@@M@@M=L-\tfrac n2\Id@@`（第 `@@M@@k@@` 级赋特征值 `@@M@@k-n/2@@`），其平方 Hilbert–Schmidt 范数恒为 `@@M@@n2^n/4@@`，与权无关；且乘以单个坐标只连接相等或相邻的级。无权时 `@@M@@M@@` 恰为立方体邻接阵的 `@@M@@-1/2@@` 倍，每条边的矩阵元素平方为 `@@M@@1/4@@`。带权时单个边元素可能缩水，作者借交换子（commutator）`@@M@@C_i=[M,Z_i]@@` 并用两个酉算子 `@@M@@J,W@@` 证明 `@@M@@\|C_i\|_{\op}\le1@@`，从而每个边元素平方仍 `@@M@@\le1/4@@`，且所有"亏损"之和被对角能量控制。由此，对乘以符号函数 `@@M@@h@@` 的算子 `@@M@@H@@`，反交换子（anticommutator）`@@M@@T=MH+HM@@` 的范数能"数出"同号边：`@@M@@|\mathcal{E}_h|\le2\|T\|_{\HS}^2@@`。

最后装配（第 5 节）：先给 `@@M@@p@@` 加一个小正常数消去零点（不改变 `@@M@@f@@`），取权 `@@M@@w=|p|@@`，令 `@@M@@h=\chi f@@`（`@@M@@\chi@@` 为全奇偶性 full parity）。奇偶性逐边变号，故 `@@M@@h@@` 的同号边恰是 `@@M@@f@@` 的敏感边。更妙的是，乘 `@@M@@\chi@@` 把 `@@M@@p@@` 的 Fourier 支集抬到度至少 `@@M@@n-d@@` 处，迫使块 `@@M@@\Pi_sH\Pi_r@@` 在 `@@M@@r+s<n-d@@` 时消失。把归一化的块范数平方视作随机指标 `@@M@@(R,S)@@` 的概率律，其两个边缘分布均为二项分布 `@@M@@\operatorname{Bin}(n,1/2)@@`；令 `@@M@@U=S@@`、`@@M@@V=n-R@@`，则二者同分布且 `@@M@@V-U\le d@@` 恰好是那个单侧约束。耦合引理（`@@M@@a=d@@`，`@@M@@\sigma=\sqrt n/2@@`）给出 `@@M@@\|T\|_{\HS}^2/N\le4d\sqrt n@@`，代入边数不等式即得 `@@M@@I(f)\le8d\sqrt n@@`。

## 可信度与备注

本文主定理已有 Lean 形式化证明（结果族 127 附有对应文档），是 OpenAI 此批手稿中验证等级最高的一类结果。本族仅含这一篇论文，没有姊妹篇交叉支撑，但噪声灵敏度与学习两个推论均由主定理经标准约化（随机分桶、`@@M@@L_1@@` 多项式回归）直接导出，内部自洽。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，推论细节仍建议以社区核验为准。

{% endraw %}
