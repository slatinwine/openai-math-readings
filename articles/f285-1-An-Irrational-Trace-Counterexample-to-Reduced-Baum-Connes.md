---
layout: default
title: "An irrational-trace counterexample to reduced Baum–Connes"
family: "285"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An irrational-trace counterexample to reduced Baum–Connes

> 结果族 285：Counterexamples to Baum–Connes and Kadison–Kaplansky　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

有些数学猜想像公司的"对账制度"：断言两条完全不同的流水线——一条看几何，一条看代数——算出的库存清单必然一致。这篇论文精心造出一个群，让两条流水线的账对不上：无系数版本的 Baum–Connes 猜想就此被推翻。

**关键词卡片**

- 群 C*-代数（group C*-algebra）：把群的元素当成可相乘的变换算子后，生成的整个代数世界
- 投影（projection）：满足 `@@M@@p^2=p@@` 的算子，像一个只会停在 0 和 1 的开关
- 迹（trace）：给算子称重的秤，投影称出的重量类似图形面积
- 装配映射（assembly map）：把几何侧清单搬进代数侧的对账通道，猜想称它为完美对账员

**看个具体例子**

决定性证据是一个投影 `@@M@@b_0@@`，它的迹是无理数。取 `@@M@@p=2@@`，这个迹形如 `@@M@@\sum_i 2^{-k_i}@@`：二进制小数里的 1 只出现在稀疏、间距越来越大的位置上，永不循环，所以无理。而 Lück 定理保证：装配映射像里所有元素称出来都只能是有理数。无理重量的 `@@M@@b_0@@`，进不了有理账本的门。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="20" y="40" width="180" height="64" fill="none" stroke="#333" stroke-width="2"/><text x="110" y="68" text-anchor="middle" font-size="15">几何侧：分类空间 K-理论</text><text x="110" y="90" text-anchor="middle" font-size="12">（拓扑清单）</text><line x1="202" y1="72" x2="350" y2="72" stroke="#333" stroke-width="2"/><polygon points="362,72 348,65 348,79" fill="#333"/><text x="280" y="60" text-anchor="middle" font-size="14">装配映射 μ</text><rect x="360" y="40" width="180" height="64" fill="none" stroke="#333" stroke-width="2"/><text x="450" y="68" text-anchor="middle" font-size="15">代数侧：K₀(Cr*(G))</text><text x="450" y="90" text-anchor="middle" font-size="12">（算子清单）</text><ellipse cx="390" cy="200" rx="150" ry="55" fill="#eef" stroke="#369" stroke-width="2"/><text x="390" y="196" text-anchor="middle" font-size="14">μ 的像</text><text x="390" y="218" text-anchor="middle" font-size="12">迹全为有理数</text><circle cx="150" cy="228" r="7" fill="#c33"/><text x="150" y="258" text-anchor="middle" font-size="13" fill="#c33">b₀：τ=1/2+1/128+… 无理</text><path d="M 162 224 L 246 210" stroke="#c33" stroke-width="2" stroke-dasharray="6,4" fill="none"/><polygon points="250,209 236,205 238,219" fill="#c33"/><text x="185" y="195" text-anchor="middle" font-size="12" fill="#c33">进不了像</text></svg>

</div>

**为什么值得关心**

从 Atiyah 1976 年追问"`@@M@@L^2@@` 不变量能否取无理值"起，无理迹一直是这类猜想的天然试金石；本文首次让这样的投影真正落进群 C*-代数，一个悬置多年的主流猜想被否定，算子代数与拓扑 K-理论的地图需要重画。

> 暂无形式化证明（AI 结果待核验）

## 由浅入深：从类比走向定理

**第一级台阶**

导读把猜想比作对账制度：几何侧有一条清单——分类空间上清点出来的指标类；代数侧有另一条清单——群所生成的算子世界里清点出来的投影类；装配映射是搬运工，猜想断言两边账目严格一致。现在把"算子世界"说清楚一点：对象是群元素当作平移算子后生成的整个代数，操作是给其中的开关式算子称重、并比较两侧清单。

**第二级台阶**

用本科术语精确化三个概念。群 C*-代数：把群元素实现为希尔伯特空间上的平移算子，取一切多项式的范数闭包所得的代数。投影：自乘等于自身的算子，对应"只取 0/1 的开关"。典范迹：读出算子表达式中恒等元前的系数，它在投影上的取值如同面积，落在 0 与 1 之间。装配映射则把分类空间的等变 K-同调类送进群 C*-代数的 K0 群，是几何指标进入代数世界的正规通道。

**第三级台阶**

定理在这个语境下陈述：Baum–Connes 猜想断言装配映射对一切可数离散群是同构，而 Lück 的迹定理先验地保证像中每个类的迹都是有理数——这挡住了"顺从"一侧的所有例子。论文取含挠的半直积群：灯模提供有限域结构，标记扩张子提供一致谱隙，二者合起来构造出真正落在约化群 C*-代数中的投影，其迹的二进制展开只在间距越来越大的位置出现 1，永不周期，因而是无理数。无理的重量进不了有理的账本：该投影的类落在装配像之外，满射性被否定。

## 一句话结论

本文构造了一个有限生成群 `@@M@@G_{\mathrm{sur}}@@`，其约化群 `@@M@@C^*@@`-代数中含有典范迹为无理数的投影 `@@M@@b_0@@`；由 Lück 迹定理，装配像中所有类的迹均为有理数，故 `@@M@@[b_0]@@` 落在装配映射的像之外——无系数约化 Baum–Connes 猜想对可数离散群被推翻（满射方向）。

## 问题背景

无系数约化 Baum–Connes 装配映射 `@@M@@\mu_j^G\colon K_j^G(\underline EG)\to K_j(C_r^*(G))@@` 把真作用分类空间（classifying space for proper actions）`@@M@@\underline EG@@` 的等变 `@@M@@K@@`-同调送到约化群 `@@M@@C^*@@`-代数的 `@@M@@K@@`-理论；猜想断言其为同构。正结果覆盖顺群与双曲群，反例此前只有 Higson–Lafforgue–Skandalis 的带系数与 groupoid 版本。无理迹是天然的满射障碍：Lück 证明对任意可数离散群，`@@M@@\mu_0^G@@` 像的迹全在 `@@M@@\mathbb Q@@` 中。这条线索历史悠久：Atiyah 1976 年问及覆盖的 `@@M@@L^2@@`-Betti 数可否无理，此后 Grigorchuk–Żuk 的灯群谱计算、Dicks–Schick、Austin 的无理核维数、Pichot–Schick–Żuk 的超越值相继推进；但 Grabowski 在顺群灯群上的超越核维数投影只活在 von Neumann 代数中——顺群满足 Baum–Connes，按 Lück 定理它们根本进不了 `@@M@@C^*@@`-代数。要让投影真正落入 `@@M@@C_r^*@@`，需要一致谱隙使 `@@M@@\mathbf 1_{\{0\}}@@` 在谱上连续（Li–Nowak–Pooya 机制），本文首次实现了这一点。

## 主要结果

**定理**：存在有限生成离散群 `@@M@@G_{\mathrm{sur}}@@` 与投影 `@@M@@b_0\in C_r^*(G_{\mathrm{sur}})@@`，使 `@@M@@\tau_{G_{\mathrm{sur}}}(b_0)=\sum_{i\ge1}p^{-k_i}\notin\mathbb Q@@` 为无理数，且
`@@M@@D[b_0]\notin\mu_0^{G_{\mathrm{sur}}}\bigl(K_0^{G_{\mathrm{sur}}}(\underline EG_{\mathrm{sur}})\bigr).@@`
特别地，无系数约化 Baum–Connes 猜想对可数离散群不成立，且障碍经有理化后仍然存在。该群是灯群型半直积 `@@M@@G_{\mathrm{sur}}=V\rtimes\Gamma@@`，其中灯模 `@@M@@V@@` 是有限域 `@@M@@\mathbb F_p@@` 上的向量空间，群因而含挠——与族内两篇无挠姊妹篇恰成分工：本篇主满射失效，另两篇分别主单射失效与投影猜想。

## 证明思路

群取半直积 `@@M@@G_{\mathrm{sur}}=V\rtimes\Gamma@@`：`@@M@@\Gamma@@` 由标记扩张子（labelled expanders，Gromov–Osajda 图形关系子）生成；`@@M@@V=\mathbb F_p^{(\Gamma)}/W_0@@` 是灯模，其关系子空间 `@@M@@W_0@@` 由所有平移 copy 上的对偶码字张成。先以 Osajda 标记定理取有限 `@@M@@d@@`-正则大围长扩张子 `@@M@@\Theta_i@@` 等距嵌入 `@@M@@\Gamma@@` 的 Cayley 图，再把每个 copy 锥化得到一致双曲图；关键的"同时相交估计"表明：相对任意根，一个 copy 与所有中心不更远的 copy 的交整体落入一个小内蕴树球。Gilbert–Varshamov 式计数给出 `@@M@@\mathbb F_p@@` 上既含指定模式 `@@M@@w_i@@`、本原与对偶距离又都超过 `@@M@@\eta n_i@@` 的码 `@@M@@C_i@@`；由此 `@@M@@V@@` 的紧对偶 `@@M@@\Omega@@` 上每个 copy 的模式分布恰是 `@@M@@C_P@@` 上的均匀分布——匹配概率精确等于 `@@M@@p^{-k_i}@@`，且不同 copy 间无需任何独立性。

算子取 `@@M@@T=dI-\sum_s f_su_sf_{s^{-1}}\in C_r^*(G_{\mathrm{sur}})\cong C(\Omega)\rtimes_r\Gamma@@`，其中 `@@M@@f_s@@` 是由坐标值决定"允许标签"的 clopen 投影。在每个赋值点 `@@M@@\omega@@`，`@@M@@\pi_\omega(T)=dI-\Adj(G_\omega)@@` 是"启用图"的图拉普拉斯算子：模式匹配的 valid copy 成为孤立的扩张子连通分支，其上核恰为常数函数；真正的难点是其余无穷部分上的一致谱隙。论文用圈秩（cycle rank）记账：Euler 恒等式 `@@M@@|E|=|Y|-\#\pi_0+b_1@@` 把谱亏缺化为圈维数上界，逐 copy 消去圈坐标并对两两不交的外顶点集收费，大围长保证外部附着点彼此远离；由此得一致亏缺 `@@M@@d|Y|-2|E(A)|\ge(c/2)|Y|@@`，再经水平集积分与 Cauchy–Schwarz 得 `@@M@@T\ge(c^2/8d)I@@`。于是谱含于 `@@M@@\{0\}\cup[\varepsilon,2d]@@`，连续泛函演算给出真投影 `@@M@@b_0=\chi(T)@@`。最后计算迹：恒等元落在某个 valid copy 时对角元为 `@@M@@1/n_i@@`，恰有 `@@M@@n_i@@` 个该类 copy 含恒等元且诸事件互斥，故 `@@M@@\tau(b_0)=\sum_ip^{-k_i}@@`；其 base-`@@M@@p@@` 展开的数字恰在位置 `@@M@@k_1<k_2<\cdots@@` 为 `@@M@@1@@`，而间距趋于无穷，不可能最终周期，从而无理。

## 可信度与备注

本文暂无形式化证明；谱隙、码分布与图几何互相咬合，核验成本高。族内姊妹篇从单射方向与投影猜想方向补全装配失效的整体图景。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

---

## 深入探讨：像审稿人一样追问 🔍

**问 1：证明中最关键也最脆弱的一步是什么？**

答：是"整个启用图上的一致谱隙"。引言明言：扩张子分支上的核是常数函数好算，"构造必须对其余全部图给出一致正下界"。论文靠圈秩记账加"同时相交估计"（任一 copy 与所有中心不更远 copy 的交整体落入一个小的内蕴树球）消去圈坐标，得到亏缺下界 `@@M@@d|Y|-2|E(A)|\ge(c/2)|Y|@@`，再积分得 `@@M@@T\ge(c^2/8d)I@@`。这两个组合引理的常数若失守，谱隙塌掉，投影就退回 von Neumann 世界，反例不成立。

**问 2：前人反例不少，这篇的真正新意在哪里？**

答：HLS 2002 的反例带交换系数或是 groupoid 版本，从未触及无系数群猜想；Austin、Pichot–Schick–Żuk 的无理核维数与 Grabowski 的超越核维数投影全部只活在群 von Neumann 代数中——顺群满足 Baum–Connes，按 Lück 迹定理它们根本进不了 `@@M@@C_r^*@@`。本文用一致谱隙使零点示征函数在谱上连续（Li–Nowak–Pooya 机制），首次把无理迹投影压进约化群 C*-代数。

**问 3：哪个假设最不能去掉？**

答：扩张子的"大围长+等距嵌入"（Osajda 标记定理）。圈秩收费依赖大围长使外部附着点彼此远离；没有它，同时相交不再受控，诸 copy 的有限圈空间不再是内直和，谱隙下界无从谈起。同理，`@@M@@k_i@@` 间距递增不能去掉，否则迹的 base-`@@M@@p@@` 展开可能最终周期而有理。

**问 4：迹为何恰好等于 `@@M@@\sum_i p^{-k_i}@@`？**

答：对偶紧空间上每个 copy 的模式分布恰是对偶码上的均匀分布（Gilbert–Varshamov 计数保证双距离条件），匹配概率精确为 `@@M@@p^{-k_i}@@`，无需任何 copy 间独立性；含恒等元的 `@@M@@n_i@@` 个 valid copy 互斥，对角元各 `@@M@@1/n_i@@`，求和即得。编码与概率的这步咬合是核验重点。

**问 5：这类 AI 生成证明最可能在哪里出错？**

答：典型风险在多级常数递推：圈秩不等式、水平集积分、Cauchy–Schwarz 三步的常数互相咬合，任何一步符号或常数 slips，谱隙命题仍在表述上"看着对"；此外从 Lück 的 `@@M@@\Lambda_G@@` 版本推有理性的短推导也值得逐行核对。论文未形式化，谱隙与码分布两章应优先核验。

**问 6：下游推论是什么，谁会用到？**

答：无系数约化 Baum–Connes 猜想对可数离散群在满射方向被否定，且障碍经有理化仍存在——拓扑 K-理论与算子代数的地图需重画。族内姊妹篇（单射失效与投影猜想）补全失效图景。论文未展开对 Kadison–Kaplansky 猜想的直接冲击：群含挠，与无挠 idempotent 猜想不直接冲突。

**总评**

若谱隙与编码两步经得起核验，这是教科书级的一击，终结一个四十年的主流猜想；最大风险集中在全图一致谱隙的组合论证，一处常数失守即满盘皆输。

{% endraw %}
