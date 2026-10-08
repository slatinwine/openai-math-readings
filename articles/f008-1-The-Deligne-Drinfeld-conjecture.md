---
layout: default
title: "The Deligne-Drinfeld conjecture"
family: "008"
discipline: "Number theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Deligne-Drinfeld conjecture

> 结果族 008：The Deligne–Drinfeld conjecture　·　学科：Number theory　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

数学里有一间神秘房间：里面的"家具"是满足三条极短方程（反对称、三词、五边形）的多项式解，它们刻画"带括号辫子"的无穷小对称。房间看似住着无数件家具，Deligne 与 Drinfeld 却猜：真正独立的家具只在权重 `@@M@@3,5,7,\ldots@@` 各出现一件，其余家具全是它们的括号组合。本文证明：房间确实这么简洁。

**关键词卡片**

- Grothendieck–Teichmüller 李代数（Grothendieck–Teichmüller Lie algebra）：上述三条方程的解空间 `@@M@@W@@` 配上 Ihara 括号得到的代数。
- 权重（weight）：多项式中 `@@M@@x,y@@` 的字数，用来给解分层；三条方程同时压在所有权重上。
- Ihara 括号（Ihara bracket）：解之间的一种特殊乘法 `@@M@@\{\psi,\phi\}@@`；"`@@M@@W@@` 对它封闭"本身就是定理的结论之一。
- 自由李代数（free Lie algebra）：没有任何多余关系的李代数，"一件独立家具配一个旋钮"的代数化身。
- 权重完备化（weight completion）：允许无穷权重级数后的极限版本；同构在完备化后仍连续成立。

**看个具体例子**

定理给出同构 `@@M@@\Lie_{\mathbb{Q}}\langle e_3,e_5,e_7,\ldots\rangle\cong(W,\{,\})@@`，每个奇权一个生成元 `@@M@@\sigma_{2k+1}@@`。括号让权重相加：`@@M@@\{\sigma_3,\sigma_5\}@@` 落在权重 `@@M@@3+5=8@@`，而 `@@M@@\{\sigma_3,\sigma_3\}=0@@`。生成元真实存在来自显式构造：其深度一分量 `@@M@@[x^{n-1}y]@@` 的系数在奇权 `@@M@@n@@` 处等于 `@@M@@2\lambda^n\zeta(n)\neq0@@`——例如权重 3 处是 `@@M@@2\lambda^3\zeta(3)@@`（`@@M@@\zeta(3)\approx1.202@@`），一个不折不扣的非零数。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="60" y1="190" x2="510" y2="190" stroke="#333" stroke-width="2"/><line x1="80" y1="184" x2="80" y2="196" stroke="#333" stroke-width="2"/><line x1="130" y1="184" x2="130" y2="196" stroke="#333" stroke-width="2"/><line x1="180" y1="184" x2="180" y2="196" stroke="#333" stroke-width="2"/><line x1="230" y1="184" x2="230" y2="196" stroke="#333" stroke-width="2"/><line x1="280" y1="184" x2="280" y2="196" stroke="#333" stroke-width="2"/><line x1="330" y1="184" x2="330" y2="196" stroke="#333" stroke-width="2"/><line x1="380" y1="184" x2="380" y2="196" stroke="#333" stroke-width="2"/><line x1="430" y1="184" x2="430" y2="196" stroke="#333" stroke-width="2"/><line x1="480" y1="184" x2="480" y2="196" stroke="#333" stroke-width="2"/><text x="80" y="213" font-size="15" text-anchor="middle" fill="#222">3</text><text x="130" y="213" font-size="15" text-anchor="middle" fill="#222">5</text><text x="180" y="213" font-size="15" text-anchor="middle" fill="#222">6</text><text x="230" y="213" font-size="15" text-anchor="middle" fill="#222">7</text><text x="280" y="213" font-size="15" text-anchor="middle" fill="#222">8</text><text x="330" y="213" font-size="15" text-anchor="middle" fill="#222">9</text><text x="380" y="213" font-size="15" text-anchor="middle" fill="#222">10</text><text x="430" y="213" font-size="15" text-anchor="middle" fill="#222">11</text><text x="480" y="213" font-size="15" text-anchor="middle" fill="#222">12</text><circle cx="80" cy="100" r="11" fill="none" stroke="#2a9d4f" stroke-width="3"/><circle cx="130" cy="100" r="11" fill="none" stroke="#2a9d4f" stroke-width="3"/><circle cx="230" cy="100" r="11" fill="none" stroke="#2a9d4f" stroke-width="3"/><circle cx="330" cy="100" r="11" fill="none" stroke="#2a9d4f" stroke-width="3"/><text x="420" y="106" font-size="16" fill="#2a9d4f">……</text><text x="80" y="72" font-size="15" text-anchor="middle" fill="#222">σ₃</text><text x="130" y="72" font-size="15" text-anchor="middle" fill="#222">σ₅</text><text x="230" y="72" font-size="15" text-anchor="middle" fill="#222">σ₇</text><text x="330" y="72" font-size="15" text-anchor="middle" fill="#222">σ₉</text><rect x="270" y="140" width="20" height="20" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><rect x="370" y="140" width="20" height="20" fill="none" stroke="#2a5fd6" stroke-width="2.5"/><line x1="172" y1="142" x2="188" y2="158" stroke="#d64545" stroke-width="2.5"/><line x1="172" y1="158" x2="188" y2="142" stroke="#d64545" stroke-width="2.5"/><text x="280" y="132" font-size="13" text-anchor="middle" fill="#2a5fd6">{σ₃,σ₅}</text><text x="380" y="132" font-size="13" text-anchor="middle" fill="#2a5fd6">{σ₃,σ₇}</text><text x="180" y="132" font-size="13" text-anchor="middle" fill="#d64545">{σ₃,σ₃}=0</text><line x1="88" y1="110" x2="268" y2="140" stroke="#bbb" stroke-width="1.5" stroke-dasharray="4 3"/><line x1="128" y1="110" x2="290" y2="140" stroke="#bbb" stroke-width="1.5" stroke-dasharray="4 3"/><line x1="92" y1="110" x2="368" y2="140" stroke="#bbb" stroke-width="1.5" stroke-dasharray="4 3"/><line x1="238" y1="110" x2="388" y2="140" stroke="#bbb" stroke-width="1.5" stroke-dasharray="4 3"/><text x="285" y="243" font-size="15" text-anchor="middle" fill="#222">权重（= 多项式的字数）</text><text x="285" y="30" font-size="16" text-anchor="middle" fill="#222">每个奇权一个生成元，括号让权重相加（示意）</text></svg>

</div>

**为什么值得关心**

它一举刻画了这个对称空间的全部结构，并（经 Willwacher 的同构）顺带算清图复形的 `@@M@@H^0(\mathrm{GC}_2)@@`；结论还通过了机器检验，属于最可靠的一类新定理。

> 已 Lean 形式化

## 一句话结论

论文证明了 Deligne–Drinfeld 猜想：有理 Grothendieck–Teichmüller 李代数（Grothendieck–Teichmüller Lie algebra）——带括号辫子的无穷小对称代数——在 Ihara 括号（Ihara bracket）下由权重 `@@M@@3,5,7,\ldots@@` 各一个生成元自由生成，且权重完备化后同构依然成立。

## 问题背景

Grothendieck–Teichmüller 李代数记录"带括号辫子"（parenthesized braids）的结合与换位约束的无穷小对称。它在二元自由李代数 `@@M@@L=\Lie_{\mathbb{Q}}\langle x,y\rangle@@`（按字数分次，称为权重 weight）上由三条方程定义：反对称（antisymmetry）、三词关系（three-term relation）与 `@@M@@\mathfrak t_4@@` 中的五边形关系（pentagon）。方程极短，却对所有权重同时施压。Deligne 在三刺直线基本群的动机研究中、Drinfeld 在 associator 论文中提出猜想：解空间应恰好是每个奇权重（`@@M@@\ge3@@`）一个生成元的自由李代数。此前只知"半边"：奇权元素的存在性归于 Ihara，Drinfeld 给出 associator 证明；Brown 借混泰特动机（mixed Tate motives）给出一个自由李子代数；Willwacher 证明 `@@M@@x^{2k}y@@` 系数非零的奇权解族必自由。缺口是"没有额外解"的全权重维数上界，此前仅靠 Naef–Willwacher 对线性化 Kashiwara–Vergne 代数的计算验证到权重 29。

## 主要结果

记 `@@M@@W=\bigoplus_n W_n@@` 为满足

`@@M@@D\psi(x,y)+\psi(y,x)=0,\qquad
\psi(x,y)+\psi(y,-x-y)+\psi(-x-y,x)=0@@`

及 `@@M@@\mathfrak t_4@@` 中五边形关系的多项式全体。令 `@@M@@D_\psi(x)=0,\ D_\psi(y)=[y,\psi]@@`，定义 Ihara 括号
`@@M@@D\{\psi,\phi\}=D_\psi(\phi)-D_\phi(\psi)+[\psi,\phi].@@`

**定理（主结果）**：存在齐次元素 `@@M@@\sigma_{2k+1}\in W_{2k+1}@@`（`@@M@@k\ge1@@`），使 `@@M@@e_{2k+1}\mapsto\sigma_{2k+1}@@` 给出分次李代数同构
`@@M@@D\Lie_{\mathbb{Q}}\langle e_3,e_5,e_7,\ldots\rangle\ \cong\ (W,\{\,,\,\}),@@`
且按权重完备化后是连续分次同构。生成元不典范；"`@@M@@W@@` 在 Ihara 括号下封闭"是证明的结论而非假设。结合 Willwacher 的同构，立得图复形（graph complex）的零阶上同调 `@@M@@H^0(\mathrm{GC}_2)@@` 等于该自由李代数的权重完备化。

## 证明思路

整条证明是"上界—构造—夹逼"的长链：先证全权重上界 `@@M@@\dim W_n\le d_n@@`（`@@M@@d_n@@` 为奇权自由李代数的维数），再构造摸到上界的解。

先取上界，主场转到特征 2。作换元 `@@M@@A=x^2,\ C=[x,y],\ B=y@@`，按 `@@M@@B@@` 出现次数过滤；五边形关系的"首项"（`@@M@@B@@` 计数最小的部分）被转移到二水平分圆超平面排列（level-two cyclotomic hyperplane arrangement）的包络代数中检验。关键是不在两个代数间建立同态，而是并排运行同一套确定性"排序程序"：源侧（辫子代数）排序不减 `@@M@@u@@` 计数，目标侧排序不增，两边保计数的项完全相同，于是四项首项关系成立，无需目标代数的独立性。

再用删除算子（deletion operators）把首项关系读成逐字方程：构造整系数算子 `@@M@@T_H@@`（特化 Hirose–Sato 的代数微分算子），给出排列李代数的整数表示；模 2 后，字与算子的配对自动消去计数偏低的余项。若首项在 `@@M@@A=0@@` 后为零：混合 `@@M@@A,C@@` 的项先被字级检验排除；剩下的 `@@M@@P(A,B)@@` 由特殊恒等式加反对称处理——系数在交换任一 `@@M@@A@@` 位与 `@@M@@B@@` 位下不变，而特征 2 中"三个 `@@M@@C@@` 位"给出 `@@M@@3\lambda=\lambda@@`，逼其归零；仅剩两个小情形用 `@@M@@x\leftrightarrow y@@` 对称性排除。于是首项投影 `@@M@@\chi\mapsto\chi(0,C,B)@@` 单射。

继而定像：偶指标约束（源自 `@@M@@x,y@@` 对称）与平移不变性 `@@M@@f(C,B+s(C))=f(C,B)@@`，经 Vandermonde 论证把像钉进 `@@M@@g_k=\ad_C^k B@@`（`@@M@@k\ge1@@`）生成的自由李代数，其生成元权重恰为 `@@M@@3,5,7,\ldots@@`，上界到手。

下界靠构造。在括号弦范畴上，相容导子在重接箭头上的取值自动落入 `@@M@@W@@`，其像 `@@M@@V@@` 在 Ihara 括号下封闭；正则化和乐（regularized holonomy）给出自同构 `@@M@@S=H_-H_+^{-1}@@`，`@@M@@\delta=\log S@@` 的齐次分量提供有理值。对实重接路径比较两种传输规则得 `@@M@@\delta(\alpha)\equiv\Phi(-x,-y)-\Phi(x,y)\pmod{J^2}@@`，而 `@@M@@[x^{n-1}y]\Phi=-\lambda^n\sum_{q\ge1}q^{-n}@@` 是正项收敛级数，奇权重时值 `@@M@@2\lambda^n\zeta(n)\neq0@@`——只用正性，不诉诸算术独立性。

最后夹逼：在 `@@M@@\mathbb{Z}_{(2)}@@` 饱和格上逐权重归纳，已选生成元的 Hall 字约化后线性无关，而 Ihara 括号使深度（depth）相加、长字无深度一分量，新造的深度一值独立于它们；每个权重达到 `@@M@@d_n@@`，单满同时到手，完备化按权重连续延拓。

## 可信度与备注

主结果已由官方 Lean 形式化（仓库 `lean/docs/008.md`）：形式化覆盖有理解空间——反对称、三词、五边形方程配 Ihara 括号——的自由生成与权重完备化后的连续同构；正则化和乐命题与图复形推论不在形式化范围内。本结果族仅此一篇手稿，内部"上界"与"构造"两半互为支撑，并实质引用 Willwacher、Brown、Naef–Willwacher 等已发表结论。请注意 OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
