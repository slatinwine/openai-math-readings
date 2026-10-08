---
layout: default
title: "The Bass trace conjecture and the characteristic-zero Kaplansky idempotent conjecture"
family: "207"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Bass trace conjecture and the characteristic-zero Kaplansky idempotent conjecture

> 结果族 207：The ℓ¹-Bass conjecture for all discrete groups　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

群环像"群的记账本"，幂等元 `@@M@@e^2=e@@` 是只会全开或全关的开关。Kaplansky 猜想知道：无挠群（除单位元外没人转有限圈回家）的账本里，这种开关是否只有 0 和 1。本文先证更精细的 Bass 迹猜想——迹只在有限阶元素的共轭类上记账——再把这个开关问题一口气回答掉。

**关键词卡片**

- 群环（group ring）：系数与群元素的形式和构成的代数，如 `@@M@@\mathbb CG@@`。
- Hattori–Stallings 迹（Hattori–Stallings trace）：秩的逐共轭类加细，比一个数字详细得多的流水单。
- 无挠群（torsion-free group）：除单位元外没有有限阶元素的群。
- 幂等元（idempotent）：`@@M@@e^2=e@@`；猜想说不存在"半心半意"的中间状态。
- Kaplansky 幂等猜想（Kaplansky idempotent conjecture）：无挠群的群环中幂等元只有 `@@M@@0@@` 与 `@@M@@1@@`。

**看个具体例子**

公式卡——取无挠群 `@@M@@G=\mathbb Z@@`（整数加群）、`@@M@@R=\mathbb C@@`，群环就是 Laurent 多项式环：

`@@M@@D\mathbb C[\mathbb Z]\cong\mathbb C[t^{\pm1}],\qquad e(t)^2=e(t)\ \Rightarrow\ e(t)\equiv 0\ \text{或}\ 1.@@`

这个特例看首末项系数就能明白；定理的威力在于对一切无挠群、一切特征零整环都成立——绝大多数群根本没有这么好的交换结构可用。证明一半是代数：把迹系数编成高维循环上的权重；另一半是几何：证明高维不变量必为零。两半合拢，无限阶元素上的账目全部清零，开关只剩全开与全关。

**为什么值得关心**

1976 年前后的 Bass 迹猜想与特征零 Kaplansky 幂等猜想同时解决，不设任何顺从、装配或维数假设，还附带流形上同伦幂等映射的不动点结论。

> 已 Lean 形式化

## 一句话结论

论文对任意离散群证明了复群环上的 Bass 迹猜想：`@@M@@K_0(\mathbb CG)@@` 的 Hattori–Stallings 迹只在有限阶共轭类上非零；并由此推出无挠群（torsion-free group）在任意特征零交换幺整环上的 Kaplansky 幂等猜想：群环 `@@M@@RG@@` 中幂等元只有 `@@M@@0@@` 与 `@@M@@1@@`。

## 问题背景

群环上射影模的 Hattori–Stallings 迹（Hattori–Stallings trace）把"秩"加细为逐共轭类的信息，是群环 Euler 示性数的基本成分。Bass 在 1976 年前后提出迹支撑猜想：整群环 `@@M@@\mathbb ZG@@` 的迹应集中在单位元处，复群环 `@@M@@\mathbb CG@@` 版本允许有限阶类。此前它只对若干特殊群类成立：Bass 的线性群、Farrell–Linnell 的初等顺从群、Berrick–Chatterji–Mislin 借助 Bost 装配映射（assembly map）得到的顺从群，以及被 Farrell–Jones 猜想蕴含的情形。平行的主线是 Kaplansky 幂等猜想：无挠群在任意域上的群环除 `@@M@@0,1@@` 外没有幂等元。Burger–Valette 曾证明数量迹取 `@@M@@[0,1]@@` 中的有理数，但有理数仍容许 `@@M@@0@@` 与 `@@M@@1@@` 之间的中间值，纯代数途径就此卡住。本文同时解决这两件事，且不设任何装配、顺同或同调维数假设。

## 主要结果

定理一（复 Bass 迹猜想）：对任意离散群 `@@M@@G@@`、任意 `@@M@@x\in K_0(\mathbb CG)@@` 与任意无限阶元素 `@@M@@g@@`，迹系数 `@@M@@\HS_G(x)([g]_G)=0@@`；等价地 `@@M@@\HS_G(K_0(\mathbb CG))\subseteq\bigoplus_{C\in\con_{\rm fin}(G)}\mathbb CC@@`。定理二（整 Bass 迹猜想）：`@@M@@K_0(\mathbb ZG)@@` 的迹集中在单位类 `@@M@@[1]_G@@`——除定理一外还需 Linnell 的有限阶系数限制（Berrick–Hesselholt 复证）。推论（无挠群）：(i) 幂等矩阵的数量迹等于增广秩（augmentation rank），且 `@@M@@\tau_{G,*}(K_0(\mathbb CG))=\mathbb Z@@`；(ii) 对任意特征零交换幺整环 `@@M@@R@@`，`@@M@@RG@@` 中幂等元只有 `@@M@@0@@` 与 `@@M@@1@@`，此即特征零情形的 Kaplansky 幂等猜想。文中还经由 Berrick–Chatterji–Mislin 的等价定理导出不动点结论：维数大于二的连通闭光滑可定向流形上的同伦幂等映射（homotopy idempotent）必自由同伦于恰有一个不动点的映射。

## 证明思路

证明分代数、几何两半，几何先证。代数侧：设 `@@M@@G@@` 有限生成，取幂等元 `@@M@@e@@` 与无限阶元 `@@M@@g@@`。`@@M@@e@@` 的有限个非零群系数确定一个有限步集，沿"从 `@@M@@h@@` 到 `@@M@@gh@@` 的路径"连乘矩阵系数再取迹，得到有限元素组上的复权重；幂等性使对中间顶点求和即删去该顶点，迹的循环性给出"末顶点乘 `@@M@@g@@`"的扭转移位恒等式。把顶点投影到陪集集 `@@M@@Y=\langle g\rangle\backslash G@@`，商群 `@@M@@H=C_G(g)/\langle g\rangle@@` 自由作用于 `@@M@@Y@@`；在每个正偶数维 `@@M@@2m@@` 上，这些权重定义出模 `@@M@@H@@` 的单纯循环，其单形是固定有界度图中的连通顶点集。探测器是一个 Pfaffian 上闭链：取记录提升之间相对 `@@M@@g@@` 幂次的反对称函数 `@@M@@\beta@@`，令 `@@M@@p_m=\Pf(\beta(h_i,h_j))@@`；扭转旋转下按末列展开给出递推 `@@M@@q_m=\tfrac12q_{m-1}@@`，故该上闭链在循环上的取值为 `@@M@@2^{-m}\lambda@@`，而 `@@M@@\lambda@@` 正是待消的迹系数。几何侧的稀疏链定理断言：维数足够高时，任何 `@@M@@H@@` 不变上闭链在此类循环上都取零。做法是逐次把支撑复形切成有界直径的块，分离集选得接近最小面积；用一个带自由作用的紧概率空间分离交叠的平移，从而无需顺从性；每个顶单形有自己的平均欧氏面积泛函，在公共面上不必吻合。由生成树得出的 `@@M@@1/n!@@` 体积因子与重复切制产生的阶乘在比较中相消，按固定度数界选半径后剩余体积比随 `@@M@@n@@` 趋于零，局部替换把这一严格体积余量转化为零维层期望点数任意小，等变链同伦保持取值不变。收官时次序关键：先固定由幂等元决定的图，再取足够大的偶维迫使 `@@M@@\lambda=0@@`；一般离散群经子群共轭类上的精确求和归约到有限生成情形。最后在无挠情形，迹只剩单位类系数，等于增广秩；数量情形的秩只能是 `@@M@@0@@` 或 `@@M@@1@@`，在群 von Neumann 代数 `@@M@@\mathcal N(G)@@` 中经忠实迹的相似论证（`@@M@@a=e^*e+(1-e)^*(1-e)@@` 正可逆，`@@M@@p=ses^{-1}@@` 为投影）逼出 `@@M@@e=0@@` 或 `@@M@@1@@`；一般特征零整环再把有限生成的系数域嵌入 `@@M@@\mathbb C@@` 归约到复情形。

## 可信度与备注

任务信息标注本文主结果已有 Lean 形式化证明。族内姊妹篇《The ℓ¹-Bass Conjecture for Discrete Groups》把同一"加权循环组＋Pfaffian 探测"策略推进到 `@@M@@\ell^1@@` 群代数（该篇引言明言其第 7–8 节思路源于本文群环论证），两篇在核心机制上互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题：本文虽已形式化，姊妹篇尚未，交叉引用时请分别核验各自状态。

{% endraw %}
