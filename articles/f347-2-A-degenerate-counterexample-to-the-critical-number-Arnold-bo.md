---
layout: default
title: "Three fixed points on the symplectic quadric threefold"
family: "347"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Three fixed points on the symplectic quadric threefold

> 结果族 347：Counterexamples to stable-Morse and strong Arnold fixed-point bounds　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

设计山地地形时，无论怎么捏，驻点（山顶、谷底、鞍点）总数有下限；可这篇论文让地形随哈密顿流"动起来"之后，一个周期结束停在原处的点居然可以更少。舞台是一个非常具体的空间——复三维二次超曲面：任何函数都得要至少 4 个驻点，它却只有 3 个停点。

**关键词卡片**

- 二次超曲面（quadric threefold）：四维复射影空间中由二次方程定义的闭辛流形 `@@M@@Q^3@@`，实维六。
- 哈密顿微分同胚（Hamiltonian diffeomorphism）：哈密顿力学演化一个周期得到的空间变换。
- 临界数（critical number）：允许退化临界点时，所有光滑函数临界点数的最小值，此处为 4。
- 哈密顿对合（Hamiltonian involution）：施行两次等于恒等的对称变换，本文用翻转部分坐标实现。

**看个具体例子**

公式卡（数字版定理）：`@@M@@\#\operatorname{Fix}(\phi)=3<4=\operatorname{Crit}(Q^3)=\operatorname{cuplength}(Q^3)@@`，且至少一个不动点退化。下图的对比：左边是地形函数至少 4 个驻点，右边是本文映射的 3 个不动点。三还是最优计数——已有定理保证这类流形上任何哈密顿映射至少 3 个不动点，本例恰好触底。诀窍是先用一个"施行两次回到原样"的对称变换，其不动集是一块好处理的子空间；再叠加微小扰动，把不动点按需安放在这块子空间上。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><path d="M20 170 Q60 90 100 170 Q140 250 180 170 Q220 90 260 170 Q300 250 340 170" fill="none" stroke="#333" stroke-width="2"/><circle cx="60" cy="130" r="6" fill="#2980b9"/><circle cx="140" cy="210" r="6" fill="#2980b9"/><circle cx="220" cy="130" r="6" fill="#2980b9"/><circle cx="300" cy="210" r="6" fill="#2980b9"/><text x="34" y="40" font-size="13" fill="#333">Q³ 上任何函数：≥ 4 个驻点</text><ellipse cx="460" cy="170" rx="78" ry="62" fill="none" stroke="#8e44ad" stroke-width="2"/><circle cx="460" cy="112" r="6" fill="#c0392b"/><circle cx="402" cy="192" r="6" fill="#c0392b"/><circle cx="518" cy="192" r="6" fill="#c0392b"/><text x="368" y="40" font-size="13" fill="#333">本文哈密顿映射：仅 3 个不动点</text><text x="386" y="254" font-size="13" fill="#8e44ad">流形 Q³（实六维）</text></svg>

</div>

**为什么值得关心**

一个例子同时推翻 Arnold 猜想的临界数形式与有理杯长形式，而且是光滑反例中的首个；主结果已通过机器验证。

> 已 Lean 形式化

## 一句话结论

在复三维二次超曲面 `@@M@@Q^3@@`（实六维闭辛流形）上，本文构造出恰好有三个不动点的光滑哈密顿微分同胚，而该流形上任何光滑函数都至少有四个临界点——同时推翻 Arnold 猜想的临界数形式与有理杯长形式，且三是最优计数。

## 问题背景

Arnold 不动点猜想把哈密顿不动点与光滑函数的临界点作比较，其最强（无退化假设）形式断言：闭辛流形上任何哈密顿微分同胚（Hamiltonian diffeomorphism）的不动点数不少于临界数（critical number）`@@M@@\Crit(M)@@`，即允许退化临界点时所有光滑函数临界点数的最小值；其弱形式用有理杯长（cup length）替代。正结果集中于特殊情形：标准环面（Conley–Zehnder）、`@@M@@\CP^n@@`（Fortune）、`@@M@@\pi_2=0@@` 时的杯长界（Hofer）、`@@M@@[\omega]@@` 与 `@@M@@c_1@@` 在 `@@M@@\pi_2@@` 上为零（Rudyak–Oprea）。二次超曲面含正辛面积的球面，恰在这些假设之外。Ma 曾断言哈密顿不动点最小个数恒等于 `@@M@@\Crit(M)@@`；Buhovsky–Humilière–Seyfaddini 只对连续（`@@M@@C^0@@`）哈密顿同胚造出过单不动点例子。光滑反例此前一直缺失。

## 主要结果

主定理：取 `@@M@@Q^3=\{z_0^2+z_1^2+z_2^2+z_3^2+z_4^2=0\}\subset\CP^4@@`（带限制 Fubini–Study 辛形式），存在光滑哈密顿微分同胚 `@@M@@\phi@@` 使

`@@M@@D\#\Fix(\phi)=3<4=\Crit(Q^3)=\operatorname{cuplength}(Q^3;\mathbb Q),@@`

且至少一个不动点退化（degenerate）。三是最优的：Gong 证明复维数 `@@M@@n\ge2@@` 的标准二次超曲面上任何哈密顿微分同胚至少有 `@@M@@n@@` 个不动点，本例在 `@@M@@n=3@@` 时达到该界。由于计数涵盖全部不动点，附加轨道可缩条件也无法挽救不等式；非退化情形的同调 Arnold 不等式涉及不同假设，与本例相容。

## 证明思路

核心机制是"有限阶传递"：设 `@@M@@A@@` 为 `@@M@@m@@` 阶哈密顿映射，不动集 `@@M@@F@@` 是干净不动子流形（clean fixed set，即 `@@M@@T_qF=\ker(dA_q-\id)@@`）。先把 `@@M@@F@@` 上的函数 `@@M@@f@@` 任意延拓，再按有限群平均得到 `@@M@@A@@`-不变的 `@@M@@K@@`；平均算子是到 `@@M@@T_qF@@` 的投影，故 `@@M@@K@@` 在 `@@M@@F@@` 处的环境临界性等价于 `@@M@@f@@` 的临界性（对称临界性原理的有限群特例）。不变性使 `@@M@@K@@` 的哈密顿流 `@@M@@B_s@@` 与 `@@M@@A@@` 交换，于是 `@@M@@(A\circ B_\varepsilon)^m=B_{m\varepsilon}@@`；再用短周期引理（Lipschitz 估计排除短非平凡周期轨，Yorke 定理的初等版本）取足够小的 `@@M@@\varepsilon@@`，则 `@@M@@B_{m\varepsilon}@@` 的不动点恰为 `@@M@@K@@` 的临界点，最终得 `@@M@@\Fix(A\circ B_\varepsilon)=\Crit(f)@@`——不动点计数被完全转移到子流形上的临界点计数。

载体是二次超曲面上的哈密顿对合（involution）`@@M@@A[z_0:\cdots:z_4]=[z_0:-z_1:\cdots:-z_4]@@`：它是等速旋转流 `@@M@@\Phi_1^{\pi,\pi}@@`，显式哈密顿量 `@@M@@G_{a,b}@@` 保证其哈密顿性；不动集 `@@M@@F=Q^3\cap\{z_0=0\}@@` 经秩一矩阵实现同构于 `@@M@@S^2\times S^2@@`，切空间分解为 `@@M@@\pm1@@` 特征子空间，干净条件成立。

`@@M@@F@@` 上取显式函数 `@@M@@f(x,y)=e\cdot x+(x-p)\cdot y@@`（`@@M@@p@@` 为北极、`@@M@@e@@` 为赤道点，属 Takens 球面积构造的显式化）。Lagrange 乘子方程可完整解出：得退化孤立临界点 `@@M@@q_0=(p,-e)@@`（Hessian 特征值 `@@M@@1,-1,0,0@@`，秩 2）与两个非退化点 `@@M@@q_\pm@@`（函数值 `@@M@@\pm 3\sqrt3/2@@`），别无其他。

下界四的验证分两半：Lusternik–Schnirelmann 杯积引理（负梯度流把 `@@M@@k@@` 个临界值化成 `@@M@@k@@` 个开覆盖，其上正阶闭形式皆恰当，从而杀死 `@@M@@k@@` 重杯积）配合超平面类 `@@M@@h^3=2[\mathrm{pt}]\ne0@@` 给出下界 4；不等速旋转 `@@M@@G_{1,2}@@` 的临界点是其生成元 `@@M@@T=\operatorname{diag}(0,J,2J)@@` 的射影特征线，恰有四条落在 `@@M@@Q^3@@` 上，给出上界 4，两界相等。最后在 `@@M@@q_0@@` 处：Hessian 核向量 `@@M@@v@@` 满足 `@@M@@DX_f(q_0)v=0@@`，故 `@@M@@d\phi_{q_0}v=\exp(\varepsilon DX_f(q_0))v=v@@`，线性化出现特征值 1，退化性得证。

## 可信度与备注

本文主结果已 Lean 形式化（见结果族 347 的官方 Lean 文档）。姊妹篇在同一结果族中给出十二维、非退化、亏损无界的 Morse 数反例（暂无形式化证明），族内另有单连通闭 Kähler 流形上稳定 Morse 数亏损无界的构造，多篇互补地否定 Arnold 猜想的各无限制形式。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
