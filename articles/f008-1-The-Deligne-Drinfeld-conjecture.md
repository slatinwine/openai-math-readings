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

## 一句话结论

论文证明了 Deligne–Drinfeld 猜想：有理 Grothendieck–Teichmüller 李代数（Grothendieck–Teichmüller Lie algebra）——带括号辫子的无穷小对称代数——在 Ihara 括号（Ihara bracket）下由权重 \(3,5,7,\ldots\) 各一个生成元自由生成，且权重完备化后同构依然成立。

## 问题背景

Grothendieck–Teichmüller 李代数记录"带括号辫子"（parenthesized braids）的结合与换位约束的无穷小对称。它在二元自由李代数 \(L=\Lie_{\Q}\langle x,y\rangle\)（按字数分次，称为权重 weight）上由三条方程定义：反对称（antisymmetry）、三词关系（three-term relation）与 \(\mathfrak t_4\) 中的五边形关系（pentagon）。方程极短，却对所有权重同时施压。Deligne 在三刺直线基本群的动机研究中、Drinfeld 在 associator 论文中提出猜想：解空间应恰好是每个奇权重（\(\ge3\)）一个生成元的自由李代数。此前只知"半边"：奇权元素的存在性归于 Ihara，Drinfeld 给出 associator 证明；Brown 借混泰特动机（mixed Tate motives）给出一个自由李子代数；Willwacher 证明 \(x^{2k}y\) 系数非零的奇权解族必自由。缺口是"没有额外解"的全权重维数上界，此前仅靠 Naef–Willwacher 对线性化 Kashiwara–Vergne 代数的计算验证到权重 29。

## 主要结果

记 \(W=\bigoplus_n W_n\) 为满足

\[\psi(x,y)+\psi(y,x)=0,\qquad
\psi(x,y)+\psi(y,-x-y)+\psi(-x-y,x)=0\]

及 \(\mathfrak t_4\) 中五边形关系的多项式全体。令 \(D_\psi(x)=0,\ D_\psi(y)=[y,\psi]\)，定义 Ihara 括号
\[\{\psi,\phi\}=D_\psi(\phi)-D_\phi(\psi)+[\psi,\phi].\]

**定理（主结果）**：存在齐次元素 \(\sigma_{2k+1}\in W_{2k+1}\)（\(k\ge1\)），使 \(e_{2k+1}\mapsto\sigma_{2k+1}\) 给出分次李代数同构
\[\Lie_{\Q}\langle e_3,e_5,e_7,\ldots\rangle\ \cong\ (W,\{\,,\,\}),\]
且按权重完备化后是连续分次同构。生成元不典范；"\(W\) 在 Ihara 括号下封闭"是证明的结论而非假设。结合 Willwacher 的同构，立得图复形（graph complex）的零阶上同调 \(H^0(\mathrm{GC}_2)\) 等于该自由李代数的权重完备化。

## 证明思路

整条证明是"上界—构造—夹逼"的长链：先证全权重上界 \(\dim W_n\le d_n\)（\(d_n\) 为奇权自由李代数的维数），再构造摸到上界的解。

先取上界，主场转到特征 2。作换元 \(A=x^2,\ C=[x,y],\ B=y\)，按 \(B\) 出现次数过滤；五边形关系的"首项"（\(B\) 计数最小的部分）被转移到二水平分圆超平面排列（level-two cyclotomic hyperplane arrangement）的包络代数中检验。关键是不在两个代数间建立同态，而是并排运行同一套确定性"排序程序"：源侧（辫子代数）排序不减 \(u\) 计数，目标侧排序不增，两边保计数的项完全相同，于是四项首项关系成立，无需目标代数的独立性。

再用删除算子（deletion operators）把首项关系读成逐字方程：构造整系数算子 \(T_H\)（特化 Hirose–Sato 的代数微分算子），给出排列李代数的整数表示；模 2 后，字与算子的配对自动消去计数偏低的余项。若首项在 \(A=0\) 后为零：混合 \(A,C\) 的项先被字级检验排除；剩下的 \(P(A,B)\) 由特殊恒等式加反对称处理——系数在交换任一 \(A\) 位与 \(B\) 位下不变，而特征 2 中"三个 \(C\) 位"给出 \(3\lambda=\lambda\)，逼其归零；仅剩两个小情形用 \(x\leftrightarrow y\) 对称性排除。于是首项投影 \(\chi\mapsto\chi(0,C,B)\) 单射。

继而定像：偶指标约束（源自 \(x,y\) 对称）与平移不变性 \(f(C,B+s(C))=f(C,B)\)，经 Vandermonde 论证把像钉进 \(g_k=\ad_C^k B\)（\(k\ge1\)）生成的自由李代数，其生成元权重恰为 \(3,5,7,\ldots\)，上界到手。

下界靠构造。在括号弦范畴上，相容导子在重接箭头上的取值自动落入 \(W\)，其像 \(V\) 在 Ihara 括号下封闭；正则化和乐（regularized holonomy）给出自同构 \(S=H_-H_+^{-1}\)，\(\delta=\log S\) 的齐次分量提供有理值。对实重接路径比较两种传输规则得 \(\delta(\alpha)\equiv\Phi(-x,-y)-\Phi(x,y)\pmod{J^2}\)，而 \([x^{n-1}y]\Phi=-\lambda^n\sum_{q\ge1}q^{-n}\) 是正项收敛级数，奇权重时值 \(2\lambda^n\zeta(n)\neq0\)——只用正性，不诉诸算术独立性。

最后夹逼：在 \(\Z_{(2)}\) 饱和格上逐权重归纳，已选生成元的 Hall 字约化后线性无关，而 Ihara 括号使深度（depth）相加、长字无深度一分量，新造的深度一值独立于它们；每个权重达到 \(d_n\)，单满同时到手，完备化按权重连续延拓。

## 可信度与备注

主结果已由官方 Lean 形式化（仓库 `lean/docs/008.md`）：形式化覆盖有理解空间——反对称、三词、五边形方程配 Ihara 括号——的自由生成与权重完备化后的连续同构；正则化和乐命题与图复形推论不在形式化范围内。本结果族仅此一篇手稿，内部"上界"与"构造"两半互为支撑，并实质引用 Willwacher、Brown、Naef–Willwacher 等已发表结论。请注意 OpenAI 官方声明：未经形式化的结果可能有问题。

{% endraw %}
