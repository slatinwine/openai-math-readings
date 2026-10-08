---
layout: default
title: "Approximation Paving over Arbitrary Maximal Abelian Subalgebras"
family: "300"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Approximation Paving over Arbitrary Maximal Abelian Subalgebras

> 结果族 300：Approximation and quadratic strong-operator paving　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一张巨大的表格（矩阵）里，对角线是"分内账目"，对角线外全是"串门噪音"。铺陈（paving）问题问：能否把行列编号分成很少几组，使每组内部的串门噪音微不足道？2015 年 Marcus–Spielman–Srivastava 在最标准的坐标（对角 MASA）下解决了它——即著名的 Kadison–Singer 问题。但任换一套"坐标系统"（极大交换子代数），直接分组会失败。本文证明 Popa–Vaes 的折中方案普遍可行：先把算子换成一个范数至多三倍的近似替身，再分组铺陈，对任何坐标系统、任何冯·诺依曼代数都成立。

**关键词卡片**

- 冯·诺依曼代数（von Neumann algebra）：对取极限封闭的一类算子代数
- 极大交换子代数（maximal abelian subalgebra, MASA）：代数内最大的一套两两交换的"坐标系统"
- 铺陈（paving）：用坐标投影切分成少数块，令块间残留噪音很小
- 块压缩（pinching）：C_P(y)=Σp_iyp_i，剪掉 y 的跨块联系只留块内部分
- 条件期望（conditional expectation）：把算子压回坐标系统的"取平均"操作

**看个具体例子**

数值版主定理：任意 0<ε<1，投影个数不超过 C·ε^{-6}（C 为通用常数）；误差减半，分组数约增 64 倍。分块压缩的示意：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="32" font-size="15" text-anchor="middle">分成三组后逐块压缩</text><line x1="130" y1="48" x2="130" y2="240" stroke="#999"/><line x1="162" y1="48" x2="162" y2="240" stroke="#999"/><line x1="194" y1="48" x2="194" y2="240" stroke="#999"/><line x1="226" y1="48" x2="226" y2="240" stroke="#999"/><line x1="258" y1="48" x2="258" y2="240" stroke="#999"/><line x1="290" y1="48" x2="290" y2="240" stroke="#999"/><line x1="322" y1="48" x2="322" y2="240" stroke="#999"/><line x1="130" y1="48" x2="322" y2="48" stroke="#999"/><line x1="130" y1="80" x2="322" y2="80" stroke="#999"/><line x1="130" y1="112" x2="322" y2="112" stroke="#999"/><line x1="130" y1="144" x2="322" y2="144" stroke="#999"/><line x1="130" y1="176" x2="322" y2="176" stroke="#999"/><line x1="130" y1="208" x2="322" y2="208" stroke="#999"/><line x1="130" y1="240" x2="322" y2="240" stroke="#999"/><rect x="130" y="48" width="64" height="64" fill="none" stroke="#b33" stroke-width="3"/><rect x="194" y="112" width="64" height="64" fill="none" stroke="#b33" stroke-width="3"/><rect x="258" y="176" width="64" height="64" fill="none" stroke="#b33" stroke-width="3"/><text x="352" y="84" font-size="13">p1（块 1）</text><text x="352" y="148" font-size="13">p2（块 2）</text><text x="352" y="212" font-size="13">p3（块 3）</text><text x="280" y="264" font-size="13" text-anchor="middle">块压缩 C_P(y)=Σp_i y p_i 后，跨块噪音 ≤ ε·‖y‖</text></svg>

</div>

两个关键点：误差以替身自身的范数为尺度（相对误差），且定理不要求代数可分、也不要求存在条件期望——这是以往所有版本都迈不过去的一般性门槛。

**为什么值得关心**

它把 Kadison–Singer 问题的精神推广到任意坐标系统，完整兑现 Popa–Vaes 在 2015 年提出的逼近铺陈猜想。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了 Popa–Vaes 的逼近铺陈（approximation paving）猜想：任何冯·诺依曼代数中的自伴算子，都可先在强算子拓扑下用范数至多三倍的算子逼近，再对任意极大交换子代数以相对误差 `@@M@@\varepsilon@@` 完成范数铺陈，投影个数不超过 `@@M@@C\varepsilon^{-6}@@`，且完全不需要可分性或条件期望假设。

## 问题背景

1959 年 Kadison 与 Singer 提出纯态延拓问题，其铺陈版本（Anderson，1979）问：能否用有限个对角投影把 `@@M@@\mathcal B(\ell^2)@@` 中算子的非对角部分切成小范数块？Marcus–Spielman–Srivastava（2015）以混合特征多项式（mixed characteristic polynomial）解决了对角情形。但对一般 MASA（maximal abelian subalgebra，极大交换子代数），直接铺陈原算子过于苛刻：Popa 与 Vaes 在 2015 年证明，在可分预对偶（separable predual）情形，范数铺陈恰好等价于代数为 I 型且 MASA 是某个正规条件期望（normal conditional expectation）的值域。为此他们提出允许先做有界扰动的逼近铺陈与允许强拓扑压缩的 so-铺陈两个弱化版本，并猜想任意 MASA 都具有这两种性质（Conjecture 2.8）。此前逼近铺陈只在 I 型代数、amenable 代数或 profinite 作用产生的 Cartan 子代数、以及奇异有限 MASA 等特例上得到验证，一般情形（尤其无期望情形）悬而未决。

## 主要结果

主定理：存在通用常数 `@@M@@C_{\mathrm{ap}}>0@@`，对每个 `@@M@@0<\varepsilon<1@@` 有整数 `@@M@@R(\varepsilon)\le C_{\mathrm{ap}}\varepsilon^{-6}@@`，使得对任何复冯·诺依曼代数 `@@M@@M\subseteq\mathcal B(H)@@`、任何 MASA `@@M@@A\subseteq M@@`、任何自伴元 `@@M@@x=x^*\in M@@`、任何有限向量集 `@@M@@F\subset H@@` 与 `@@M@@\delta>0@@`，存在自伴元 `@@M@@y\in M@@`、`@@M@@A@@` 中 `@@M@@R(\varepsilon)@@` 个投影构成的单位分割 `@@M@@\mathcal P=(p_i)@@` 以及自伴元 `@@M@@a\in A@@`，满足
`@@M@@D\|y\|\le 3\|x\|,\qquad \|(y-x)\xi\|<\delta\ (\xi\in F),\qquad \|a\|\le\|y\|,\qquad \|C_{\mathcal P}(y)-a\|\le\varepsilon\|y\|,@@`
其中 `@@M@@C_{\mathcal P}(y)=\sum_i p_iyp_i@@` 是块压缩（pinching）。要点有二：误差以近似算子 `@@M@@y@@` 自身的范数为尺度；投影个数与代数、其表示、算子乃至强邻域全都无关。推论一：当 `@@M@@A@@` 是正规条件期望的值域时，由此得到相应的强算子铺陈；推论二：该情形下投影个数可改进为 `@@M@@N(\varepsilon)\le C\varepsilon^{-2}@@` 的二次方阶。

## 证明思路

证明分为"测度论一半"与"算子代数一半"。测度论一半建立单边可测铺陈定理：对可数非奇异 Borel 等价关系上、支撑在有限度图内的厄米矩阵系统，只要颜色数 `@@M@@r@@` 满足 `@@M@@2\sqrt{2/r}+2/r<b@@`，就有 `@@M@@r+1@@` 色可测染色使 `@@M@@(T_{\mathrm{pav}}-(Kb)\mathbf 1)_+^2@@` 的对角积分任意小。其组合内核是铺陈多项式（paving polynomial）：把随机染色下的期望特征多项式与局部谱概率测度、谱移位函数（spectral-shift function）联系起来，稳定性由 MSS 式的半平面论证给出；关键的"缓冲钉住引理"（buffered pinning）在固定某个顶点的颜色、同时把它的对角罚项放大固定倍数 `@@M@@K@@` 时，控制正根质量的增量，且常数与矩阵大小和以往选择无关。非奇异性是第一道难关：作者把关系提升到 Maharam 延拓，在附加高度坐标后测度不变、质量传输公式（mass transport）可用；再用权重 `@@M@@e^s@@` 缩放矩阵，恰好抵消密度 `@@M@@e^{-s}@@`，使不同高度"石板"上的谱代价可用普通平均比较，钉住决策从而下降为底空间上的单一染色。最后做稀疏钉住：对图的距离幂取有限 Borel 辅助染色，独立 Bernoulli 抽取待钉顶点，使每个局部球内"同时被抽中两个以上"的概率仅为 `@@M@@O(\alpha^2)@@`，一阶响应因此可加；正部函数 `@@M@@x_+@@` 先用多项式逼近以绕开对根个数的依赖，迭代后总成本与未染色集测度都任意小。

算子代数一半先处理 `@@M@@A@@` 落在忠实正规态 `@@M@@\varphi@@` 的中心化子（centralizer）中的情形。分解 `@@M@@x-E_Ax=Y+Z@@`：`@@M@@Y=E_Nx-E_Ax@@` 属于群子正规化子生成的代数 `@@M@@N@@`，经 Feldman–Moore 表示化为可测等价关系的代数，交给可测铺陈定理；`@@M@@Z=x-E_Nx@@` 具有扩散的左右核，作者改造 Popa–Vaes 的自由积矩阵膨胀（free-product dilation），用随机对角相位获得关于非迹态的渐近自由性，矩及其集中都不依赖迹性，模群（modular group）通过解析右乘处理。随后用可分性约化去掉可分预对偶假设：可数地生成一个包含逼近分割的子代数，其 MASA 性质靠压缩网收敛验证。最关键的一步是去掉条件期望假设：在中心化正规正泛函的支撑 `@@M@@e@@` 的角上存在正规期望，可直接铺陈；在补角上，利用标准形式自然锥中近两两正交的随机共轭态向量（随机单位根标签）构造对角压缩极小的正压缩，再以三角（three-corner）拼装保持全部非对角元直到最终选定分割。误差归一化到 `@@M@@y@@` 自身范数，则由取范数测试向量与最终裁剪（clipping）论证完成。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准。同族姊妹篇《Quadratic Strong-Operator Paving over Arbitrary Maximal Abelian Subalgebras》以相互独立的证明给出原算子的二次 so-铺陈；本文则对邻近的有界近似算子做范数铺陈，不宣称二次率，两文从不同侧面兑现 Popa–Vaes 猜想。按 OpenAI 官方声明，未经形式化的结果可能存在问题，阅读时宜保持审慎。

{% endraw %}
