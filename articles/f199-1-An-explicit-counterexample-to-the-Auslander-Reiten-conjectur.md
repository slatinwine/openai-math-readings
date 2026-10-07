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

## 一句话结论
本文构造出 Auslander–Reiten 猜想的显式反例：在特征 2 的有理函数域 \(\mathbb F_2(q,H_1,H_2)\) 上给出有限维代数 \(\Lambda\) 与非投射模 \(Z\)，使 \(Z\) 的所有正阶自扩张及到 \(\Lambda\) 的扩张全部为零；同一样本还否定 Gorenstein 投射猜想，且在任何域扩张下反例依然成立。

## 问题背景
Auslander–Reiten 猜想源自 Auslander 与 Reiten 1975 年关于广义 Nakayama 猜想的工作：Artin 代数（Artin algebra，含域上有限维代数）上的有限生成模 \(M\) 若满足 \(\Ext^i_R(M,M\oplus R)=0\) 对一切 \(i>0\)，是否必为投射模？这是同调代数中"扩张消失逼出投射性"纲领的代表性难题，悬置半个世纪。此前只有正面结果：完备交上（Auslander–Ding–Solberg）、含 \(\mathbb Q\) 的优 Cohen–Macaulay 正规整环上（Huneke–Leuschke）、满足 Auslander 条件的环上（Christensen–Holm），以及 radical 立方零的代数上（Ringel–Zhang、Zhang–Zhou 等）。Schulz 1994 年构造过无自扩张的非投射模，但它生活在除环上，不在 Artin 代数范畴内。卡点在于：已知正面类都靠"小 radical"或交换性提供控制，而猜想在一般有限维代数上毫无约束手段。

## 主要结果
定理（主定理）：取 \(k=\mathbb F_2(q,H_1,H_2)\)，其中 \(q,H_1,H_2\) 代数无关。存在有限维 \(k\)-代数 \(\Lambda\) 与有限维非投射左模 \(Z\)，使得
\[\Ext^i_\Lambda(Z,Z)=0=\Ext^i_\Lambda(Z,\Lambda),\quad \forall i\ge 1.\]
\(Z\) 还是 Gorenstein 投射（Gorenstein-projective）模——即由有限投射模组成的双边无限正合复形的余核，且对 \(\Hom(-,R)\) 保持正合——因此 Gorenstein 投射猜想（此类模若无正阶自扩张则必投射）也被同一反例否定。结构上：\(\Lambda/\rad\Lambda\simeq k^8\)（可裂、八个单模），\(\rad(\Lambda)^4\ne0\)（故意避开 radical 立方零这一已知正面类），\(\Lambda\) 非交换，\(\dim_k\Lambda=800+\dim_k F\)。所有结论在 \(k\) 的任意域扩张下保持，特别地在特征 2 的代数闭域上成立。生成元版本同样失败：\(Z\oplus\Lambda\) 是没有正阶自扩张的非投射生成元。

## 证明思路
证明分独立两层：先证与具体例子无关的"转换原理"，再造出满足其条件的代数数据。

先建立转换原理：设 \(A\) 是特征 2 域上的有限维对称代数（symmetric algebra），\(F\) 是双侧投射的 \(A\)-双模，\(X\) 有限模，\(v:X\to F\otimes_A X\) 是稳定范畴（stable category，模掉投射分解意义的映射）中的映射。定义比较映射 \(\delta^a(g,j)=F(g)v+v[a]j\)；若 \(\delta^0\) 满射且有非零核、且 \(\delta^a\) 对一切 \(a>0\) 是同构，则三角矩阵代数 \(\Lambda=\begin{pmatrix}A&0\\F&A\end{pmatrix}\) 上存在有限非投射的 Gorenstein 投射模 \(Z\)，其正阶 Ext 双双为零。其证明用完全分解（complete resolution）与锥构造：取 \(X\) 的完全无环复形 \(P_\bullet\)，经两个列函子得 \(G_0,G_1\)，把 \(v\) 提升为链映射 \(V\) 后作锥 \(P_Z=\mathrm{Cone}(V)\)，它仍完全无环且零度余核恰是 \(Z\)；短正合列 \(0\to\coker\delta^{a-1}\to \Ext^a_\Lambda(Z,Z)\to\ker\delta^a\to 0\) 把自扩张彻底交给 \(\delta\) 控制，\(\delta\) 的两条性质恰好使 \(a>0\) 时两端为零，而 \(\delta^0\) 的非零核产生非零稳定自同态，排除投射性。

再构造数据：从 10 维代数 \(C\) 出发（其 \(eCe\) 角是量子外代数 \(k\langle x,y\rangle/(x^2,y^2,xy-qyx)\)，正是 Schulz 参数移动机制的发生地），取平凡扩张（trivial extension）\(T=C\ltimes DC\) 得 20 维对称代数，其单模 \(s\) 满足 \(\Ext_T^*(s,s)=k[\tau]\)，\(\tau\) 为 3 次类，由一张显式 Hochschild 3-上闭链表实现，并带有与扭曲相容的边界恒等式。令 \(A=T\otimes T\)（400 维）、\(X=s\otimes s\)，自扩张代数变成多项式环 \(k[\tau_1,\tau_2]\)，集中在 3 的倍数度。对非零标量 \(H\)，自同构 \(h_H\) 固定 \(C\) 而把 \(DC\) 缩放 \(H\) 倍，对应的右扭曲 \(U_H\) 在 \(3m\) 次自扩张上的作用恰是乘 \(H^{-m}\)。取两个 3 次类的锥得双模 \(\mathcal C\)，使 \(X\) 到 \((\mathcal C\otimes_A X)[a]\) 的稳定映射仅在 \(a=0,3\) 处为一条直线，这给两个不同扭曲的映射提供了共同靶。将 \(U_{H_1},U_{H_2}\) 提升到 \(\mathcal C[3]\) 并重新缩放，使二者在 \(X\) 上取值相同，再取其有限纤维（finite fiber）得 \(F\)：双侧投射，且存在稳定映射 \(v:X\to F\otimes_A X\)，两个投影都是 \(\id_X\)。在 \(3m>0\) 度处，\(\delta\) 的矩阵为 \(\begin{pmatrix}H_1^{-m}&1\\H_2^{-m}&1\end{pmatrix}\otimes\id\)，行列式 \(H_1^{-m}+H_2^{-m}\neq0\)——这正用到 \(H_1,H_2\) 的代数无关性，且论证在 \(m\) 被 2 整除时同样成立；非 3 倍数度的自扩张本身为零。至此转换原理的全部条件验证完毕，得到 \(\Lambda\) 与 \(Z\)。最后，域扩张下 Ext 与纯量扩张交换（\(K\) 平坦），非投射性经由不分裂的投射覆盖序列保持，反例于是对所有扩张稳健。

## 可信度与备注
据任务元信息，本文主结果已附带 Lean 形式化证明；正文各步（转换原理、根的结构、基扩张）均为完整证明，有限的乘法表与上闭链恒等式收录于附录并经机器核验。同族的姊妹篇（Tachikawa 第二猜想反例）在同一域上以不同的双模构构造独立得到反例并发展出对称代数版本，两篇文章各自包含完整证明、互相印证结构性断言。仍需留意 OpenAI 官方声明："未经形式化的结果可能有问题"；本文核心结论因已形式化而风险较低，但交换环版本的反例构造仍是公开问题。

{% endraw %}
