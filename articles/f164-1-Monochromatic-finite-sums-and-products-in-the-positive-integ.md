---
layout: default
title: "Monochromatic finite sums and products in the positive integers"
family: "164"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Monochromatic finite sums and products in the positive integers

> 结果族 164：Hindman's finite sums and products conjecture　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

给所有正整数涂色，红蓝随意。Ramsey 理论的老把戏是：规则再松，也总有"同色的巧合结构"跑不掉。这篇论文证明了 Hindman 在 1979 年提出的猜想：无论怎么涂，总能找到任意大的一小撮数 `@@M@@a_1,\dots,a_k@@`，使得从中随便挑几个加起来、随便挑几个乘起来，得到的数全是同一种颜色。加法与乘法这两种结构被一举同时锁进同一色桶。

**关键词卡片**

- 有限染色（finite coloring）：只用有限种颜色，给每个正整数各分配一色。
- 子集和 `@@M@@\mathrm{FS}(A)@@`（finite sums）：从 A 的所有非空子集求和得到的数集。
- 子集积 `@@M@@\mathrm{FP}(A)@@`（finite products）：同理，对非空子集求积。
- 单色（monochromatic）：所有元素同属一种颜色。
- nilsequence（幂零序列）：高等分析里"温和振动"的函数，证明中用来给颜色建立预测模型。

**看个具体例子**

取最小的非平凡情形 `@@M@@A=\{2,3\}@@`：非空子集和是 `@@M@@2,3,2+3=5@@`；非空子集积是 `@@M@@2,3,2\times 3=6@@`。定理要求这四个数全部同色。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="45" y1="140" x2="527" y2="140" stroke="#bbbbbb" stroke-width="2"/>
  <circle cx="70" cy="140" r="13" fill="#c9c9c9"/>
  <circle cx="118" cy="140" r="13" fill="#d84a3f"/>
  <circle cx="166" cy="140" r="13" fill="#d84a3f"/>
  <circle cx="214" cy="140" r="13" fill="#c9c9c9"/>
  <circle cx="262" cy="140" r="13" fill="#d84a3f"/>
  <circle cx="310" cy="140" r="13" fill="#d84a3f"/>
  <circle cx="358" cy="140" r="13" fill="#c9c9c9"/>
  <circle cx="406" cy="140" r="13" fill="#c9c9c9"/>
  <circle cx="454" cy="140" r="13" fill="#c9c9c9"/>
  <circle cx="502" cy="140" r="13" fill="#c9c9c9"/>
  <text x="70" y="145" font-size="13" text-anchor="middle" fill="#555555">1</text>
  <text x="118" y="145" font-size="13" text-anchor="middle" fill="#ffffff">2</text>
  <text x="166" y="145" font-size="13" text-anchor="middle" fill="#ffffff">3</text>
  <text x="214" y="145" font-size="13" text-anchor="middle" fill="#555555">4</text>
  <text x="262" y="145" font-size="13" text-anchor="middle" fill="#ffffff">5</text>
  <text x="310" y="145" font-size="13" text-anchor="middle" fill="#ffffff">6</text>
  <text x="358" y="145" font-size="13" text-anchor="middle" fill="#555555">7</text>
  <text x="406" y="145" font-size="13" text-anchor="middle" fill="#555555">8</text>
  <text x="454" y="145" font-size="13" text-anchor="middle" fill="#555555">9</text>
  <text x="502" y="145" font-size="13" text-anchor="middle" fill="#555555">10</text>
  <text x="280" y="195" font-size="14" text-anchor="middle" fill="#555555">A={2,3}：非空子集和 {2,3,5} 与非空子集积 {2,3,6} 全部同红</text>
  <text x="280" y="222" font-size="14" text-anchor="middle" fill="#333333">定理：任何有限染色里，这样的同色家族可以任意大</text>
</svg>

</div>

上图是某个"走运"的染色片段：2、3、5、6 恰好全红。定理讲的是普遍性：任何有限染色下，同色家族可以任意大（k 任意），且每个新成员都大过此前所有元素之和与积的任意指定幂。有趣的是，无穷版本反而不成立——Hindman 本人构造过反例染色——有限与无穷的分界正是此题迷人之处。

**为什么值得关心**

加性与乘性的 Ramsey 结构 47 年来首次被同时实现，是 Schur、Folkman、Hindman 这条经典谱系的收官之作。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了 Hindman 有限和积猜想：对正整数的任意有限染色与任意 `@@M@@k@@`，都存在 `@@M@@k@@` 元集合，使其全部非空子集和与非空子集积落在同一颜色中。加性与乘性 Ramsey 性质的同时实现这一 1979 年提出的问题首次得到肯定回答。

## 问题背景

Ramsey 理论的经典线索是：Schur 定理保证任意有限染色的 `@@M@@\mathbb N@@` 中有单色三元组 `@@M@@\{x,y,x+y\}@@`；Folkman–Rado–Sanders 有限和定理与 Hindman 无穷有限和定理把它推广到任意大有限集的全部非空子集和。染色经 `@@M@@n\mapsto\chi(2^n)@@` 转移即得纯乘法版本。但"和与积同时同色"是另一层次的问题：Hindman 在 1980 年构造了一个有限染色，使任何无穷集的元素、两两和与两两积都不同色，无穷版本由此失败；他在 1979 年提出有限猜想——任意有限染色下是否总有任意大的有限集 `@@M@@A@@` 使 `@@M@@\FS(A)\cup\FP(A)@@` 单色（Hindman–Strauss 著作 Question 17.18）。此前只在很小规模有结果：Moreira 证明任意有限染色含单色 `@@M@@\{x,x+y,xy\}@@`，Alweiss 给出多项式证明并在有理数域 `@@M@@\mathbb Q@@` 上证明完整的有限和积定理，Alweiss–Bowen–Sabok 处理两色的 `@@M@@\{x,y,xy,x+iy\}@@`。从有理数到整数的过渡是本质障碍：通分后的公共伸缩因子把和放大一次幂、把 `@@M@@j@@` 元积放大 `@@M@@j@@` 次幂，任意染色不必尊重这种不一致的缩放。

## 主要结果

主定理（Theorem 1.1）：设 `@@M@@r,m\ge1@@` 为整数，`@@M@@R\ge2@@`、`@@M@@D\ge1@@` 为实数。对任意染色 `@@M@@\chi:\mathbb N\to[r]@@`，存在互异正整数 `@@M@@a_1<\cdots<a_m@@` 与颜色 `@@M@@c@@`，使对每个非空 `@@M@@J\subseteq[m]@@` 有
`@@M@@D\chi\Big(\sum_{j\in J}a_j\Big)=\chi\Big(\prod_{j\in J}a_j\Big)=c,@@`
即 `@@M@@m@@` 元集 `@@M@@A@@` 的非空子集和集 `@@M@@\FS(A)@@` 与子集积集 `@@M@@\FP(A)@@` 之并单色；且可要求元素极度分离：`@@M@@a_1>R@@`，`@@M@@a_d>R\big(\sum_{k<d}a_k+\prod_{k<d}a_k\big)^D@@`。推论 1.2 由此得出：可使 `@@M@@|\FS(A)|=|\FP(A)|=2^m-1@@` 且 `@@M@@\FS(A)\cap\FP(A)=A@@`，即除单例外所有子集和与子集积两两互异。另一推论给出有限区间形式：存在 `@@M@@N@@`，使 `@@M@@[N]@@` 的任意 `@@M@@r@@` 染色都含此类配置，甚至可要求全部元素落在指定倍数集 `@@M@@q\mathbb N@@` 中。证明纯定性：参数的有限性与选取顺序是本质的，但不给最小配置任何数值界。

## 证明思路

证明先组合、后解析，拆成两个独立原理，最后合并。

第一步先做组合选择：把原始变量排成"块"`@@M@@B=T\cup\{i\}@@`（尾巴 `@@M@@T@@` 加主元 `@@M@@i@@`），链满足 `@@M@@T_1<\cdots<T_m<i_1<\cdots<i_m@@`，使每个较早的块恰是较晚块的"可加块"。对整数列 `@@M@@x_i=h_ib_it_i@@`，先用有限 Ramsey 定理按 `@@M@@A\mapsto\chi(x_A)@@` 染色子集得到齐次集，再用 Folkman–Rado–Sanders 有限和定理选出一条链，使全部非空块积已同色；剩余任务只是让各子集和也进入同一颜色。

第二步再建立预测原理（Prediction Principle）：为颜色示性函数构造有界的分段 nilsequence 模型 `@@M@@S_{B,a,c}@@`（Lipschitz 函数沿幂零李群轨道 `@@M@@F(g^kx)@@` 取值，分区间与剩余类定义）。要点有三：其一，块积是多个调和 `@@M@@W@@`-单位变量之积，分布异于单变量，作者用除子权 `@@M@@\nu_B(y)=\mathbb E_\sigma\,\sigma\mathbf 1_{\sigma\mid y}@@` 编码可除性，配合素数插入与保持乘积不变的"倒数伸缩"`@@M@@z_u\mapsto z_u/p,\ z_v\mapsto pz@@`，经带权 Cauchy–Schwarz 逐个剥去乘法掩码，把计数误差化归为单变量的加性立方检验；其二，计数需细尺度模型而对齐需粗尺度模型，对嵌套子空间的投影能量做 Ramsey 选择使两个要求兼容，幂零步数 `@@M@@s@@` 只依赖 `@@M@@m@@`；其三，用 Green–Tao–Ziegler 逆定理与 Tao–Ziegler 子群 Bessel 不等式把"细投影小"转为"立方均值小"，阈值与主索引个数无关。校准条款还保证颜色在中心真实出现时其模型值大概率不小于 `@@M@@2\tau@@`。

第三步建立对齐原理（Alignment Principle）：从固定有限的有理尺度表 `@@M@@\mathcal B@@` 中选出向量 `@@M@@b@@`，使每个中心的正预测经全部所需加性平移后仍为正，且成功概率有与模型复杂度无关的下界 `@@M@@\delta>0@@`——正是这一一致性允许校准容差最后才选定。难点是加性平移可能要求主变量作非整数改变：先做整数剩余校正 `@@M@@t_C(p+mr_e)+mM\Delta_e=t_Cp+mq_e@@`，再把剩余位移实现为 nilsequence 状态的变换；这些变换生成步数不超过 `@@M@@s@@` 的幂零群，在其上用幂零多项式递归（nilpotent polynomial recurrence）配合"逆向保护"式有限词计划选取尺度更新，使先前已确保的比较不被破坏。

最后合并：对齐与校准事件同时发生的概率至少 `@@M@@\delta/2@@`；在其上链选择给出乘积掩码全为 1、各中心模型值超过 `@@M@@2\tau@@`，对齐推论又给出每处和的模型值超过 `@@M@@\tau@@`，于是某加权计数沿超滤（ultrafilter）极限为正。取出使所有因子为正的具体元组即得配置；元素分离性由"每个尺度支配前序量的一切固定幂"直接保证。

## 可信度与备注

该主结果暂无 Lean 形式化证明，且论文自述所有参数均为定性、无显式数值界。论文明确声明所借用的外部深结果——Green–Tao–Ziegler 逆定理（含勘误）、Tao–Ziegler 拼接定理、Green–Tao 多项式等分布、Zorin–Kranich 幂零多项式递归——所需的特殊形式，其余传递、进度比较与提升论证均给出完整证明；但其中间步骤技术性很强，宣告解决一个悬置 47 年的猜想仍需社区逐行核验。本批次中结果族 164 仅此一篇手稿，未读到可交叉印证的姊妹篇。依据 OpenAI 官方声明，"未经形式化的结果可能有问题"，请以社区核验为准。

{% endraw %}
