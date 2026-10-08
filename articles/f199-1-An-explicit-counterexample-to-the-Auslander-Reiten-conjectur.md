---
layout: default
title: "An explicit counterexample to the Auslander-Reiten conjecture"
family: "199"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An explicit counterexample to the Auslander-Reiten conjecture

> 结果族 199：Counterexamples to Auslander–Reiten, Tachikawa and related homological conjectures　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

医院里若一个人所有体检指标全部正常，医生会断定他健康。代数里也有类似信条：一个模块若各项"扩张指标"全为零，它就该是标准件（投射模）。Auslander 与 Reiten 五十年前猜想必是如此；这篇论文造出一个"体检全正常却查出病灶"的模块，把猜想推翻。

**关键词卡片**

- 有限维代数（finite-dimensional algebra）：作为向量空间只有有限维的乘法系统
- 投射模（projective module）：同调意义上"最规整"的模块，标准件
- Ext 群（Ext group）：给两个模块之间"互相嵌套的方式"计数的尺子；全为零表示毫无扩张余地
- Gorenstein 投射模（Gorenstein-projective module）：比投射稍弱的一类规整模块，由双向无限的标准件正合列产生

**看个具体例子**

定理：在 `@@M@@k=\mathbb F_2(q,H_1,H_2)@@`（三个代数无关的参数）上，存在有限维代数 `@@M@@\Lambda@@` 与非投射模 `@@M@@Z@@`，使得

`@@M@@D\operatorname{Ext}^i_\Lambda(Z,Z)=\operatorname{Ext}^i_\Lambda(Z,\Lambda)=0\quad(\forall\, i\ge1),\qquad Z\ \text{非投射}.@@`

这座代数完全可以点名：`@@M@@\Lambda/\operatorname{rad}\Lambda\cong k^8@@`（恰有 8 个单模），`@@M@@\operatorname{rad}^4\Lambda\ne0@@`（故意避开已知的"小根基"正面类），`@@M@@\dim_k\Lambda=800+\dim_k F@@`（`@@M@@F@@` 为构造中的双模），且 `@@M@@\Lambda@@` 非交换。构造从 10 维小代数出发，其角上是量子外代数——正是此前唯一已知"高阶自扩张消尽"现象的发生地。指标全零，病灶仍在；任何域扩张下反例都不消失，特征二的代数闭域上同样成立。

**为什么值得关心**

同一样本同时否定 Auslander–Reiten 猜想与 Gorenstein 投射猜想，"扩张消失逼出投射性"这条纲领失去普遍性；生成元版本（`@@M@@Z\oplus\Lambda@@`）也随之失效。

> 已 Lean 形式化

## 一句话结论
本文构造出 Auslander–Reiten 猜想的显式反例：在特征 2 的有理函数域 `@@M@@\mathbb F_2(q,H_1,H_2)@@` 上给出有限维代数 `@@M@@\Lambda@@` 与非投射模 `@@M@@Z@@`，使 `@@M@@Z@@` 的所有正阶自扩张及到 `@@M@@\Lambda@@` 的扩张全部为零；同一样本还否定 Gorenstein 投射猜想，且在任何域扩张下反例依然成立。

## 问题背景
Auslander–Reiten 猜想源自 Auslander 与 Reiten 1975 年关于广义 Nakayama 猜想的工作：Artin 代数（Artin algebra，含域上有限维代数）上的有限生成模 `@@M@@M@@` 若满足 `@@M@@\Ext^i_R(M,M\oplus R)=0@@` 对一切 `@@M@@i>0@@`，是否必为投射模？这是同调代数中"扩张消失逼出投射性"纲领的代表性难题，悬置半个世纪。此前只有正面结果：完备交上（Auslander–Ding–Solberg）、含 `@@M@@\mathbb Q@@` 的优 Cohen–Macaulay 正规整环上（Huneke–Leuschke）、满足 Auslander 条件的环上（Christensen–Holm），以及 radical 立方零的代数上（Ringel–Zhang、Zhang–Zhou 等）。Schulz 1994 年构造过无自扩张的非投射模，但它生活在除环上，不在 Artin 代数范畴内。卡点在于：已知正面类都靠"小 radical"或交换性提供控制，而猜想在一般有限维代数上毫无约束手段。

## 主要结果
定理（主定理）：取 `@@M@@k=\mathbb F_2(q,H_1,H_2)@@`，其中 `@@M@@q,H_1,H_2@@` 代数无关。存在有限维 `@@M@@k@@`-代数 `@@M@@\Lambda@@` 与有限维非投射左模 `@@M@@Z@@`，使得
`@@M@@D\Ext^i_\Lambda(Z,Z)=0=\Ext^i_\Lambda(Z,\Lambda),\quad \forall i\ge 1.@@`
`@@M@@Z@@` 还是 Gorenstein 投射（Gorenstein-projective）模——即由有限投射模组成的双边无限正合复形的余核，且对 `@@M@@\Hom(-,R)@@` 保持正合——因此 Gorenstein 投射猜想（此类模若无正阶自扩张则必投射）也被同一反例否定。结构上：`@@M@@\Lambda/\rad\Lambda\simeq k^8@@`（可裂、八个单模），`@@M@@\rad(\Lambda)^4\ne0@@`（故意避开 radical 立方零这一已知正面类），`@@M@@\Lambda@@` 非交换，`@@M@@\dim_k\Lambda=800+\dim_k F@@`。所有结论在 `@@M@@k@@` 的任意域扩张下保持，特别地在特征 2 的代数闭域上成立。生成元版本同样失败：`@@M@@Z\oplus\Lambda@@` 是没有正阶自扩张的非投射生成元。

## 证明思路
证明分独立两层：先证与具体例子无关的"转换原理"，再造出满足其条件的代数数据。

先建立转换原理：设 `@@M@@A@@` 是特征 2 域上的有限维对称代数（symmetric algebra），`@@M@@F@@` 是双侧投射的 `@@M@@A@@`-双模，`@@M@@X@@` 有限模，`@@M@@v:X\to F\otimes_A X@@` 是稳定范畴（stable category，模掉投射分解意义的映射）中的映射。定义比较映射 `@@M@@\delta^a(g,j)=F(g)v+v[a]j@@`；若 `@@M@@\delta^0@@` 满射且有非零核、且 `@@M@@\delta^a@@` 对一切 `@@M@@a>0@@` 是同构，则三角矩阵代数 `@@M@@\Lambda=\begin{pmatrix}A&0\\F&A\end{pmatrix}@@` 上存在有限非投射的 Gorenstein 投射模 `@@M@@Z@@`，其正阶 Ext 双双为零。其证明用完全分解（complete resolution）与锥构造：取 `@@M@@X@@` 的完全无环复形 `@@M@@P_\bullet@@`，经两个列函子得 `@@M@@G_0,G_1@@`，把 `@@M@@v@@` 提升为链映射 `@@M@@V@@` 后作锥 `@@M@@P_Z=\mathrm{Cone}(V)@@`，它仍完全无环且零度余核恰是 `@@M@@Z@@`；短正合列 `@@M@@0\to\coker\delta^{a-1}\to \Ext^a_\Lambda(Z,Z)\to\ker\delta^a\to 0@@` 把自扩张彻底交给 `@@M@@\delta@@` 控制，`@@M@@\delta@@` 的两条性质恰好使 `@@M@@a>0@@` 时两端为零，而 `@@M@@\delta^0@@` 的非零核产生非零稳定自同态，排除投射性。

再构造数据：从 10 维代数 `@@M@@C@@` 出发（其 `@@M@@eCe@@` 角是量子外代数 `@@M@@k\langle x,y\rangle/(x^2,y^2,xy-qyx)@@`，正是 Schulz 参数移动机制的发生地），取平凡扩张（trivial extension）`@@M@@T=C\ltimes DC@@` 得 20 维对称代数，其单模 `@@M@@s@@` 满足 `@@M@@\Ext_T^*(s,s)=k[\tau]@@`，`@@M@@\tau@@` 为 3 次类，由一张显式 Hochschild 3-上闭链表实现，并带有与扭曲相容的边界恒等式。令 `@@M@@A=T\otimes T@@`（400 维）、`@@M@@X=s\otimes s@@`，自扩张代数变成多项式环 `@@M@@k[\tau_1,\tau_2]@@`，集中在 3 的倍数度。对非零标量 `@@M@@H@@`，自同构 `@@M@@h_H@@` 固定 `@@M@@C@@` 而把 `@@M@@DC@@` 缩放 `@@M@@H@@` 倍，对应的右扭曲 `@@M@@U_H@@` 在 `@@M@@3m@@` 次自扩张上的作用恰是乘 `@@M@@H^{-m}@@`。取两个 3 次类的锥得双模 `@@M@@\mathcal C@@`，使 `@@M@@X@@` 到 `@@M@@(\mathcal C\otimes_A X)[a]@@` 的稳定映射仅在 `@@M@@a=0,3@@` 处为一条直线，这给两个不同扭曲的映射提供了共同靶。将 `@@M@@U_{H_1},U_{H_2}@@` 提升到 `@@M@@\mathcal C[3]@@` 并重新缩放，使二者在 `@@M@@X@@` 上取值相同，再取其有限纤维（finite fiber）得 `@@M@@F@@`：双侧投射，且存在稳定映射 `@@M@@v:X\to F\otimes_A X@@`，两个投影都是 `@@M@@\id_X@@`。在 `@@M@@3m>0@@` 度处，`@@M@@\delta@@` 的矩阵为 `@@M@@\begin{pmatrix}H_1^{-m}&1\\H_2^{-m}&1\end{pmatrix}\otimes\id@@`，行列式 `@@M@@H_1^{-m}+H_2^{-m}\neq0@@`——这正用到 `@@M@@H_1,H_2@@` 的代数无关性，且论证在 `@@M@@m@@` 被 2 整除时同样成立；非 3 倍数度的自扩张本身为零。至此转换原理的全部条件验证完毕，得到 `@@M@@\Lambda@@` 与 `@@M@@Z@@`。最后，域扩张下 Ext 与纯量扩张交换（`@@M@@K@@` 平坦），非投射性经由不分裂的投射覆盖序列保持，反例于是对所有扩张稳健。

## 可信度与备注
据任务元信息，本文主结果已附带 Lean 形式化证明；正文各步（转换原理、根的结构、基扩张）均为完整证明，有限的乘法表与上闭链恒等式收录于附录并经机器核验。同族的姊妹篇（Tachikawa 第二猜想反例）在同一域上以不同的双模构构造独立得到反例并发展出对称代数版本，两篇文章各自包含完整证明、互相印证结构性断言。仍需留意 OpenAI 官方声明："未经形式化的结果可能有问题"；本文核心结论因已形式化而风险较低，但交换环版本的反例构造仍是公开问题。

{% endraw %}
