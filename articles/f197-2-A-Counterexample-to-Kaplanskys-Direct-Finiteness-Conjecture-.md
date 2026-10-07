---
layout: default
title: "A Counterexample to Kaplansky's Direct-Finiteness Conjecture in Odd Characteristic"
family: "197"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Counterexample to Kaplansky's Direct-Finiteness Conjecture in Odd Characteristic

> 结果族 197：A torsion-free group algebra that is not directly finite　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 一句话结论

对一个显式确定的奇素数 `@@M@@p@@`，本文构造出 `@@M@@p^4@@` 元域 `@@M@@K@@`、含挠（torsion）的有限生成群 `@@M@@G@@` 及群代数元素 `@@M@@a,b\in K[G]@@`，满足 `@@M@@ab=1@@` 而 `@@M@@ba\ne1@@`，否定 Kaplansky 直接有限性猜想；同一组元素还给出单射而不满射的元胞自动机，连带否定 Gottschalk 猜想。

## 问题背景

含幺环称为直接有限的（directly finite），若 `@@M@@ab=1@@` 必蕴含 `@@M@@ba=1@@`；群代数（group algebra）`@@M@@K[G]@@` 由有限和 `@@M@@\sum_g c_g g@@` 构成。Kaplansky 在 1972 年提出猜想：对任意域 `@@M@@K@@` 与任意群 `@@M@@G@@`（包括有挠群），`@@M@@K[G]@@` 总是直接有限的；他本人用有限冯·诺依曼代数（von Neumann algebra）在特征零证明了更强的稳定有限性（stable finiteness），正特征成为遗留难题。此后 Ara–O'Meara–Perera 对 free-by-amenable 群（任意除环系数）、Elek–Szabó 对全部 sofic 群证明了稳定有限性——这把任何反例的群都逼到非 sofic 一侧。有限群的情形是平凡的有限维线性代数，真正的困难集中在"无限群 × 正特征"的组合上。同族工作已用另一机制给出特征二的反例，奇特征此前留白，本文将其补齐。

## 主要结果

主定理：令 `@@M@@m=\binom{1200}{600}@@`，`@@M@@p=\min\{h\in\mathbb Z:\ h>1,\ h\mid (m!)^2+1\}@@`，则 `@@M@@p@@` 是奇素数。存在阶为 `@@M@@p^4@@` 的域 `@@M@@K@@`（自 `@@M@@\F_p@@` 起的两层二次扩张塔 `@@M@@\F_p[\xi]/(\xi^2-\eta)@@` 再添加 `@@M@@\nu^2=\xi@@`）、含挠的有限生成群 `@@M@@G@@`，以及有限和 `@@M@@a,b\in K[G]@@` 使得 `@@M@@ab=1@@` 且 `@@M@@ba\ne1@@`。一切对象都是"specified"的：由有限公式与有序有限集上的选取完全确定，无需求解该群的字问题（word problem）。注意结论只针对这一个显示的素数，并不声称对所有奇素数成立。推论一：由 Elek–Szabó 定理反推，`@@M@@G@@` 必不是 sofic 群。推论二（动力学）：同样的 `@@M@@a,b@@` 定义全空间 `@@M@@K^G@@` 上的元胞自动机（cellular automaton）`@@M@@T_b@@`，它单射而不满射，缺失的像点由 `@@M@@ba-1@@` 的某个非零系数显式指定，故 Gottschalk 的 surjunctivity 猜想对该群不成立。

## 证明思路

证明分四步：先制造两个严格不等式，再完成三次纯秩不等式无法替代的结构跳板。

第一步造数据。图这边取 `@@M@@[1200]@@` 的全部 `@@M@@600@@`-子集为顶点、交集小于 `@@M@@200@@` 时连边，得无三角形的 threshold-Kneser 图；多项式方法（Alon–Babai–Suzuki 一脉，经 Haviv、Golovnev–Haviv）给出拟合分解 `@@M@@F_{ij}=\sum_T\alpha_i(T)\beta_j(T)@@`，项数比 `@@M@@t/m<1/100@@`。群这边取局部群 `@@M@@H=A_0\rtimes P@@`，其中 `@@M@@P=(\F_p)^3@@`、`@@M@@A_0=(\mathbb Z/M\mathbb Z)^P@@`、`@@M@@M=p^4-1@@`。在 `@@M@@P@@` 的正则表示中，用 Jennings 增广滤过（augmentation filtration）取高次单项式张成的子空间（占比逾 `@@M@@1/48@@`）作为被两侧零化的列空间 `@@M@@B@@`；再用对角加权 Gram 行列式配合 Schwartz–Zippel 多项式网格引理，证明超过一半的特征标"可容许"，并经 Fourier 特征标轨道（Clifford 理论）把投影真正实现为 `@@M@@K[H]@@` 中的幂等元 `@@M@@e@@`：其正则秩（regular rank）`@@M@@d/w>1/96@@`，且满足 `@@M@@(u(s)-1)^\ell e=0@@` 与 `@@M@@e(v(s)-1)^\ell=0@@`（`@@M@@\ell=(p-1)/2@@`）的定向双侧湮灭。

第二步粘合。沿每条边 `@@M@@i<j@@` 把相邻两个 `@@M@@H@@` 副本中的指定 `@@M@@p@@` 阶元素黏合，必须证明各顶点群不塌缩：按 C(4)–T(4) 图示复形的思想，把潜在关系编成带标号的球面映射，经一系列局部约化后每个面长与每个顶点度均不小于四，Euler 公式给出的总亏格 `@@M@@8@@` 无法容纳"恰有一个例外面"的极小反例，故粘合商 `@@M@@G_0@@` 仍嵌入全部 `@@M@@H_i@@`。随后在 `@@M@@K[\langle y\rangle]=K[X]/(X^p)@@` 中，由定向湮灭推出边乘积 `@@M@@e_ie_j=0@@`（关键在 `@@M@@p-\ell=\ell+1@@`），且只对 `@@M@@i<j@@` 的顺序成立——这一非对称性是后续三角计算的生命线。

第三步把秩不等式升级为环上的恒等式。在扩群 `@@M@@G_1@@` 的非零中心幂等元 `@@M@@f@@` 生成的环 `@@M@@S=fK[G_1]@@` 内，利用初等交换 `@@M@@p@@`-群稳定子的幂零增广理想做有限基变换，得到矩形恒等式 `@@M@@Y_iJ_i=fI_d@@`、`@@M@@J_iY_i=P_iI_w@@`。三角压缩引理处理 `@@M@@D_0C_0=\mathcal P+\mathcal N@@`：`@@M@@\mathcal N@@` 严格下三角且与对角幂等 `@@M@@\mathcal P@@` 交换，一个有限和把它消去，拼出 `@@M@@D_\sharp C_\sharp=fI_{md}@@`；不等式链 `@@M@@t/m<1/100<1/96<d/w@@` 强迫 `@@M@@wt<md@@`，得到"大模单射入小模且留下左逆"的悖论，并附带显式非零核向量 `@@M@@v_*@@` 作为反向失效的证书。

第四步压成标量并转移。按 Dykema–Juschenko 有限因子归约，在有限 Heisenberg 群的群代数中用移位—调制（Weyl 对）模型显式写出矩阵单元 `@@M@@\Omega_{uv}@@`，把方阵反例单射编码进 `@@M@@K[G_1\times\Lambda]@@`，再用互补幂等元补回整体单位元，得到标量 `@@M@@a,b@@`，即主定理。最后由 `@@M@@T_cT_d=T_{cd}@@` 完成转移：`@@M@@T_b@@` 单射、`@@M@@T_a@@` 为其左逆，而在 `@@M@@(ba-1)_h\ne0@@` 处的点示性函数 `@@M@@\delta_h@@` 连无限支撑的原像都没有——这正是满射性失效的直接证据。

## 可信度与备注

本篇主结果已有 Lean 形式化证明（见结果族 197 的形式化文档）；论文还强调所有选取都落在显式有限集内，`@@M@@ba\ne1@@` 由非零核向量与矩阵编码的单射性双重认证。族内姊妹篇互相支撑：特征二构造走关联结构与平面嵌入路线，与本文机制不同、互不依赖；族内主构造给出 `@@M@@\mathbb F_2@@` 上无挠非 sofic 群的反例，本篇则是"奇特征、含挠"的变体。按 OpenAI 官方声明，未经形式化的结果可能存在问题；阅读族内其余篇章时，请以各自的验证状态为准。

{% endraw %}
