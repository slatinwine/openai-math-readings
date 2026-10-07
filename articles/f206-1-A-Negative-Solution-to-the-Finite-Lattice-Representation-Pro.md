---
layout: default
title: "A negative solution to the finite lattice representation problem"
family: "206"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A negative solution to the finite lattice representation problem

> 结果族 206：Finite lattice representation and undecidability　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
本文构造出一个有限格，证明它不可能作为任何有限群子群格的区间出现；借助 Pálfy–Pudlák 等价，这否定了几十年悬而未决的有限格表示问题——并非每个有限格都是有限代数的全同余格。

## 问题背景
Grätzer–Schmidt 表示定理（1963）说每个代数格（algebraic lattice）都是某个代数的同余格（congruence lattice），但表示用的代数可以无限；当格本身有限时能否找到有限代数，自 1980 年 Pálfy–Pudlák 以来一直是公开问题。他们证明两条全局断言等价："每个有限格都是有限代数的同余格"与"每个有限格都是某有限群子群格的区间 `@@M@@[D,G]@@`"。此后 Pudlák–Tůma（1980）只能把有限格嵌入有限集合的分拆格（保交并的嵌入而非全格实现），Repnitskiĭ–Tůma（2008）在可数局部有限群中实现了区间——有限性始终是卡点。Baddeley–Lucchini、Börner、Aschbacher 与 Pálfy 发展了把区间问题约化到几乎单群（almost simple group）的工具，但均未给出答案。本文给出否定解。

## 主要结果
**定理 1**（Theorem main:group）：存在有限格 `@@M@@L@@`，对不同构于任何子群区间 `@@M@@[D,G]=\{X: D\le X\le G\}@@`（按包含排序）。所构造的障碍格是自对偶的；它同样不能实现为有限可分扩张 `@@M@@E/F@@` 的中间域格——由 Galois 对应，这种表示会经反同构变成一个被禁止的子群区间表示。
**定理 2**（Theorem main:congruences）：存在有限非空格 `@@M@@L@@`，使 `@@M@@L\not\cong\operatorname{Con}(A)@@` 对一切有限非空代数 `@@M@@A@@`、一切有限签名（signature）成立。它由定理 1 经 Pálfy–Pudlák 全局等价导出；等价是整体的，两定理不必使用同一个格。该否定不限制簇、不限载体规模，是完全一般的。

## 证明思路
证明分两大阶段。第一阶段是"链刚性定理"（Theorem cls:chain-rigidity）：先在格论层面引入栅栏（fence）测试——区间中每个内部元都有两个可比较的补——由此每个被栅栏化的顶点 `@@M@@X@@` 模去核 `@@M@@\operatorname{core}_X(D)@@` 后有唯一极小正规子群 `@@M@@S_X\cong T_X^{m_X}@@`，其非交换单群因子 `@@M@@T_X@@` 称为该顶点的标签（label）。再建立两种运输机制：相邻同标签顶点经"子直子群（subdirect subgroup）必为对角带（diagonal strip）之积"的经典刻画传递；变标签顶点则可投影为几乎单群 `@@M@@\operatorname{Aut}(T_Y)@@` 中的真子群区间，从而能调用有限单群分类的重炮——Burness–Liebeck–Shalev 的极大子群主因子（chief factor）个数的界、Aschbacher 的极大子群分类、Larsen–Pink、Landazuri–Seitz 界与 Seitz–Cavallin–Testerman 不可约三元组分类——再配合有限 Ramsey 论证，最终得到关键结论：只要测试链两端标签不同，链长就被一个不依赖实现群的绝对常数界住。第二阶段构造障碍格：取秩四 Boolean 格 `@@M@@B_4@@` 与一个"探测器"组件，对每对请求顶点做私有插入（private insertion）——加长的标记链、两步捷径、栅栏插入、精确的 `@@M@@M_{16}@@` 区间与余原子见证——链长按第一阶段的绝对界预先选定，先于任何群；四个组件与其反序拷贝水平求和，得到自对偶的有限格 `@@M@@L_N@@`。最后归约到矛盾：若 `@@M@@L_N\cong[D,G]@@` 且 `@@M@@|G|@@` 最小，全局栅栏给出基座（socle）`@@M@@S\cong T^I@@` 且 `@@M@@G=DS@@`；正向测试把全部 Boolean 顶点的标签锁成同一个 `@@M@@T@@`，而 `@@M@@D@@`-不变子直子群恰好对应同态扩张 `@@M@@\beta:U\to\operatorname{Aut}(T)@@`，把反向滤子实现为真实的群区间 `@@M@@[A,U_Y]@@`。终局是 Boolean 粘合矛盾：先证一个判据——各扩张域核的像含内自同构群时，公共扩张必然存在；再证每个原子的核必有此性质，否则穿过该原子的三个秩二面会拼出被禁止的公共扩张；此性质经取交集传到两个秩三面 `@@M@@z=\{1,2,3\}@@` 与 `@@M@@w=\{2,3,4\}@@`，而 `@@M@@z\cup w@@` 恰为全集，于是被构造明确禁止的公共扩张被迫存在，矛盾完成证明。

## 可信度与备注
两篇主定理均暂无 Lean 形式化证明，请以社区核验为准。本篇是结果族 206 的构造核心：姊妹篇《Finite congruence lattices: characterization and undecidability》用仿射几何测试格独立给出反例，并进一步证明判定问题的不可判定性，两文从不同路径互相印证否定答案。证明第一阶段重度依赖有限单群分类及其表示论，属技术密集型论证，独立核验成本较高。OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
