---
layout: default
title: "A counterexample to integer-degree harmonic dimension comparison"
family: "361"
discipline: "Differential geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to integer-degree harmonic dimension comparison

> 结果族 361：Failure of integer-degree harmonic dimension comparison　·　学科：Differential geometry　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

在平地上，"无源无汇、平滑起伏"且增长不超过 k 次幂的函数只有调和多项式那么多，数目数得清。丘成桐曾猜测：凡是"里奇曲率非负"（不比平地更陡）的空间，这类函数的数目都不会超过平地。这篇论文造出一片 16 维的奇特地形，让同类函数的数目多得出格——猜想的整数版本被推翻。

**关键词卡片**

- 调和函数（harmonic function）：处处等于自身邻域平均值的函数，像无源稳态的温度分布。
- 里奇曲率非负（nonnegative Ricci curvature）：空间在各方向平均意义下不比欧氏空间更弯的曲率条件。
- 增长不超过 k（polynomial growth）：函数大小至多随"到原点的距离的 k 次幂"增长。
- 无穷远切锥（tangent cone at infinity）：站到无穷远处回望时，空间呈现的极限形状。
- Berger 度量（Berger metric）：把球面某个方向拉伸或压缩得到的度量的变体；本文让它随半径不断切换，是反例的发动机。

**看个具体例子**

欧氏空间的账本：在 `@@M@@\mathbb R^3@@` 中增长 `@@M@@\le k@@` 的调和函数恰好是次数 `@@M@@\le k@@` 的调和多项式，维数为 `@@M@@(k+1)^2@@`——比如 `@@M@@k=2@@` 时恰好 9 维。论文则在 `@@M@@\mathbb R^{16}@@` 上构造出 `@@M@@\operatorname{Ric}\ge 0@@` 的度量，使 `@@M@@k=50000@@` 时维数严格超过欧氏计数 `@@M@@\binom{16+49999}{49999}+\binom{16+49998}{49998}@@`。诀窍是"轮流驻留"：让同一个调和函数在不同半径段以不同的增长率生长，个别段超过 k 也无妨，只要按对数半径平均后低于 k。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="70" y1="240" x2="500" y2="240" stroke="#333" stroke-width="2"/><line x1="70" y1="240" x2="70" y2="45" stroke="#333" stroke-width="2"/><text x="80" y="58" font-size="15" fill="#333">增长率</text><text x="380" y="264" font-size="15" fill="#333">log r（对数半径）</text><line x1="70" y1="110" x2="490" y2="110" stroke="#999" stroke-width="1.5" stroke-dasharray="8 6"/><text x="76" y="103" font-size="15" fill="#555">k</text><path d="M70,75 L115,75 L115,150 L155,150 L155,65 L195,65 L195,155 L235,155 L235,70 L275,70" fill="none" stroke="#333" stroke-width="2.5"/><line x1="70" y1="130" x2="490" y2="130" stroke="#555" stroke-width="1.5" stroke-dasharray="2 6"/><text x="300" y="152" font-size="15" fill="#333">平均增长率 &lt; k</text></svg>

</div>

**为什么值得关心**

它说明仅凭"里奇非负"撑不起丘成桐的维数比较；反例在无穷远处没有唯一的切锥、渐近体积比严格小于 1，恰好点明以往正面定理里哪些假设是必不可少的。

> 已 Lean 形式化

## 一句话结论

论文在 `@@M@@\mathbb R^{16}@@`（一般地，某个偶数维 `@@M@@n\geq 8@@`）上构造了 `@@M@@\operatorname{Ric}\geq 0@@` 的完备光滑度量，使增长不超过 `@@M@@k=50000@@` 的调和函数空间维数严格超过欧氏计数，对丘成桐整数阶调和维数比较问题给出否定回答。

## 问题背景

设 `@@M@@(M^n,g)@@` 是完备的里奇曲率非负（nonnegative Ricci curvature）流形，`@@M@@h_k(M,g)@@` 记满足逐点增长条件 `@@M@@|u(x)|\leq C_u(1+d_g(o,x))^k@@` 的实调和函数空间的维数。丘成桐（Yau）在其著名问题清单中问：是否恒有 `@@M@@h_k(M,g)\leq h_k(\mathbb R^n,g_{\mathrm E})@@`？在欧氏空间上，整数增长 `@@M@@k@@` 的整体调和函数恰是次数至多 `@@M@@k@@` 的调和多项式，故 `@@M@@h_k(\mathbb R^n,g_{\mathrm E})=\binom{n+k-1}{k}+\binom{n+k-2}{k-1}@@`。Li 与 Tam 证明了线性增长的最优界 `@@M@@h_1\leq n+1@@`；Colding 与 Minicozzi 证明了各阶的有限维性以及随次数增长的最优阶 `@@M@@d^{n-1}@@`，但固定整数点上的精确欧氏计数始终悬而未决。Donnelly 曾在维数至少 5 时对介于 1 与 2 之间的非整数次数构造反例，可是整数端点上欧氏计数更大，无法直接类推；Cai 与 Lai 则证明附加局部共形平坦假设后严格比较成立。本文在纯 Ricci 假设下否定整数形式的比较。

## 主要结果

**主定理**：存在偶数 `@@M@@n\geq 8@@` 与整数 `@@M@@k\geq 2@@`（附录的精确有限谱选取允许取 `@@M@@n=16@@`、`@@M@@k=50000@@`），以及 `@@M@@\mathbb R^n@@` 上一个完备光滑度量 `@@M@@g@@`，使得 `@@M@@\operatorname{Ric}_g\geq 0@@` 且

`@@M@@Dh_k(\mathbb R^n,g)>h_k(\mathbb R^n,g_{\mathrm E})=\binom{n+k-1}{k}+\binom{n+k-2}{k-1}.@@`

该度量在原点附近是欧氏的，渐近体积比（asymptotic volume ratio）严格介于 0 与 1 之间，在无穷远处的切锥（tangent cone at infinity）不唯一，且不是局部共形平坦（locally conformally flat）的。这些附属几何性质解释了为何此前依赖唯一切锥谱（Huang）或共形平坦（Cai–Lai）的比较定理在此均不适用。

## 证明思路

度量取锥形式 `@@M@@g=dr^2+r^2\gamma(\log r)@@`，角度量 `@@M@@\gamma(t)@@` 是奇数维球面 `@@M@@S^m@@`（`@@M@@m=n-1@@`）上体积归一化的 Berger 度量 `@@M@@G(a,q,J)@@`：把 Hopf 方向拉伸 `@@M@@q@@` 倍再整体缩放 `@@M@@a@@`，并允许正交复结构 `@@M@@J@@` 随时间切换。核心思想是"会动的 link"：固定度量锥上，角特征值 `@@M@@\lambda@@` 只对应唯一的增长指数 `@@M@@d@@`（`@@M@@d(d+m-1)=\lambda@@`），而构造让同一个调和函数在多个增长率之间轮流驻留，使其按对数半径平均的增长率严格小于 `@@M@@k@@`——个别阶段可以超过 `@@M@@k@@`，只要平均值不超。

先算谱的账。Berger 度量下，`@@M@@l@@` 次球面调和函数空间 `@@M@@V_l@@` 上的特征值由 Hopf 荷 `@@M@@(2b-l)^2@@` 决定，其除以 `@@M@@l^2@@` 后依分布收敛于 `@@M@@\mathrm{Beta}(1/2,(m-1)/2)@@` 分布。结合一个加权分位数不等式（充分大的奇数 `@@M@@m@@` 满足 `@@M@@(m-1)\mathcal J_m>2@@`），可以选出方向组：每组的平均指数 `@@M@@\overline d_l<k@@`，而总数 `@@M@@\sum M_l@@` 严格超过欧氏计数。

再实现方向交换。在接近圆球的短"脉冲"内切换 `@@M@@J@@`：迹自由（trace-free）的 Hopf 生成元平方生成直和 `@@M@@\bigoplus_{2\leq l\leq L}\mathfrak{sl}(V_l)@@`，故可用指数乘积（"字"，word map）同时在各个 `@@M@@V_l@@` 中实现指定的带符号循环置换，且在字映射微分可逆的参数处取值。

几何排程上，第 `@@M@@j@@` 个周期由长 `@@M@@j^6@@` 的脉冲与长 `@@M@@j^7@@` 的各向异性驻留组成，累计时刻 `@@M@@t_j\sim j^8/8@@`。径向尺度 `@@M@@a@@` 的凹形尾巴 `@@M@@a'/a=-\mu(1+t)^{-5/4}@@` 提供约 `@@M@@j^{-10}@@` 阶的正径向曲率，压过脉冲各向异性带来的 `@@M@@O(j^{-12})@@` 负面项；切向分量用 link 的严格 Ricci 下界控制；混合分量因 Hopf 场是等长 Killing 场而为零。曲率估计对一切允许的控制序列一致成立。

传输是技术核心。`@@M@@V_l@@` 上的调和方程化为矩阵常微分方程，在原点处光滑的"中心正则"解由矩阵 Riccati 方程的解 `@@M@@P_l@@`（`@@M@@Y'=P_lY@@`）刻画，正障碍（barrier）保证 `@@M@@P_l@@` 一致有界，且每个周期起点都重置到 `@@M@@\theta_l I+O(j^{-2})@@`。整个周期的值传输被精确分解为 `@@M@@\mathcal T_{l,j}=s_{l,j}D_{l,j}\Pi_l@@`：先分离出长驻留产生的大对角增长 `@@M@@D_{l,j}@@`（`@@M@@\log(D_{l,j})_{ii}\sim j^7d_{l,i}@@`），关键引理证明剩余误差乘子一致有界、不随驻留长度放大，最后用压缩映照逐周期把归一化传输精确调到目标循环 `@@M@@\Pi_l@@`。

最后把循环化为增长估计：置换 `@@M@@\Pi_l@@` 让所选方向轮转，一整圈的增长贡献恰为均值加权和加上 `@@M@@O(J^7)@@` 误差，故 `@@M@@\log\|Y\|/t\to\overline d_l<k@@`；又因每个周期相对 `@@M@@t_j@@` 可忽略，该界在每个半径处成立。所选函数在球面上限制线性无关，于是维数 `@@M@@\geq\sum M_l@@` 严格超过欧氏计数。

## 可信度与备注

本篇在任务数据中标注为主结果已 Lean 形式化。同族的姊妹篇进一步把反例降到三维 `@@M@@\mathbb R^3@@`，对所有充分大的 `@@M@@k@@` 给出至少 `@@M@@(k+2)^2@@` 个独立调和函数（超过欧氏 `@@M@@(k+1)^2@@`），两篇共享"移动 Berger link＋周期排程＋精确传输"的同一骨架，谱盈余与控制方案互相印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇主定理已属形式化验证范围，姊妹篇则尚待形式化，宜以社区核验为准。

{% endraw %}
