---
layout: default
title: "A counterexample to Tachikawa's second conjecture"
family: "199"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to Tachikawa's second conjecture

> 结果族 199：Counterexamples to Auslander–Reiten, Tachikawa and related homological conjectures　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 一句话结论
本文否定 Tachikawa 第二猜想：在 \(k=\mathbb F_2(q,H_1,H_2)\) 上构造有限维对称代数 \(A\) 与非投射模 \(M\)，使 \(\Ext^i_A(M,M)=0\) 对一切 \(i>0\)；其自同态代数进而使经典、广义、强 Nakayama 猜想、Auslander–Gorenstein 猜想与 Wakamatsu tilting 猜想一并失败，且对一切域扩张稳健。

## 问题背景
Tachikawa 第二猜想出自 Tachikawa 1973 年关于拟 Frobenius 代数（quasi-Frobenius algebra）与支配维数的专著：有限维自内射代数（self-injective algebra）上的自正交模（self-orthogonal module，即 \(\Ext^i(M,M)=0\) 对一切 \(i>0\)）必为投射模。它与 Auslander–Reiten 猜想关系密切：自内射时 \(\Ext^i(M,A)\) 自动为零，故本猜想恰是 Auslander–Reiten 猜想的自内射情形。此前正面结果限于小 radical 类：Zhang–Zhou 处理 radical 立方零的可裂代数与 Igusa–Todorov 代数，Xia 处理量子完全交；Erdmann 的分类表明量子外代数类代数只有"高阶自扩张消尽"的模；Böhmler–Marczinzik 的交换例子也仅前两阶自扩张为零。Schulz 的无自扩张非投射模则生活在除环上，不属于域上有限维代数。Enomoto–Marczinzik 还证明二重平凡扩张上的 Tachikawa 第二猜想蕴含原代数的 Auslander–Reiten 猜想，可见该情形是关键试验场。真正的卡点：在对称代数上没有任何已知机制能同时消尽全部正阶自扩张。

## 主要结果
主定理：取 \(k=\mathbb F_2(q,H_1,H_2)\)（三参数代数无关），存在有限维对称代数（symmetric algebra，即 \(A\simeq DA\) 作为双模同构，必自内射）\(A\) 与非投射有限维模 \(M\)，满足 \(\Ext^i_A(M,M)=0\) 对一切 \(i>0\)。这直接否定 Tachikawa 第二猜想；又因 \(A\) 自内射时 \(\Ext^i(M,A)\) 自动为零，同一例子也是 Auslander–Reiten 猜想的对称反例。
推论一（同调猜想）：对任意域扩张 \(K/k\)，令 \(\Gamma_K=\End_{A_K}(A_K\oplus M_K)^{\mathrm{op}}\)，则 (1) \(\Gamma_K\) 的极小内射分解每一项都投射，但自内射维数无穷——经典 Nakayama 猜想失败；(2) 存在非零单模 \(S\) 使 \(\Ext^i_{\Gamma_K}(S,\Gamma_K)=0\) 对一切 \(i\ge0\)——广义与强 Nakayama 猜想失败；(3) 存在投射且内射的 Wakamatsu tilting 模 \(W\) 不是 tilting 模——Wakamatsu tilting 猜想失败；Auslander–Gorenstein 猜想同样失败。
推论二（finitistic 维数）：对每个 \(n\ge1\) 有投射维数恰为 \(n\) 的有限模 \(C_n\)，故 \(\Gamma_K\) 的小、大左 finitistic 维数均为无穷。
推论三、四：\(\Gamma_K^{\mathrm{op}}\) 上存在具有无穷多两两不同构不可分解补的投射几乎完全 tilting 模（经由 Buan–Solberg 定理）；对每个 \(L\ge1\) 存在具长至少 \(L\) 幂等分层（idempotent stratification）的辅助不可分解对称代数及相应导出范畴 recollement 链（经由 Chen–Fang–Xi 的镜像反射构造）。

## 证明思路
证明先立"转移原理"再造数据，最后经自同态代数收割推论。
先证转移原理（对任意有限维代数成立）：若 \(\Lambda\) 上有完全无环（totally acyclic，即 \(\Hom\) 到 \(\Lambda\) 后仍正合）复形 \(P_Z\)，其余核 \(Z\) 非投射，且完全自扩张复形满足双侧消没 \(H^a\Hom_\Lambda(P_Z,Z)=0\) 对 \(a>0\) 及 \(a\le-2\)，则平凡扩张 \(A=\Lambda\ltimes D\Lambda\)（自动对称）与诱导模 \(M=A\otimes_\Lambda Z\) 即所求。关键在于 \(A\) 作为右 \(\Lambda\)-模分解为 \(\Lambda\oplus D\Lambda\)，故 \(M\) 限制后为 \(Z\oplus N\)；归纳–限制伴随把 \(\Ext_A(M,M)\) 拆成 \(\Ext_\Lambda(Z,Z)\oplus\Ext_\Lambda(Z,N)\)，前项由 \(a>0\) 的消没控制，后项经对偶 \(D H^{-a-1}\Hom_\Lambda(P_Z,Z)\) 恰由 \(a\le-2\) 的消没控制——这正是比姊妹篇多做负阶控制的原因。
再造数据：沿用同一 10 维代数 \(C\) 及平凡扩张 \(T=C\ltimes DC\)，单模 \(s\) 满足 \(\Ext_T^*(s,s)=k[\tau]\)、\(|\tau|=3\)；导出归纳 \(\mathcal J=T\otimes_C^{\mathbf L}s\) 落在三角形 \(s[2]\to\mathcal J\to s\xrightarrow{\tau}s[3]\) 中。取 \(E=T\otimes T\)（对称）、\(X=s\otimes s\)，自扩张代数为 \(k[\tau_1,\tau_2]\)。张量两个三角形算出 \(E\otimes_B^{\mathbf L}X\simeq\mathcal J\otimes\mathcal J\)（\(B=C\otimes C\)）：非负稳定自映射上得到双变量 Koszul 序列，负向由对称稳定对偶（Tate 对偶）得到其对偶，最终只剩两个一维空间。\(E\otimes_B^{\mathbf L}E\) 的 bar 复形给出双侧投射的有限双模 \(Y\)，其稳定 Hom 画像 \(W^a\) 仅在 \(a\in\{-3,0\}\) 处为 \(k\)。对 \(H\in k^\times\)，扭曲 \(h_H\) 固定 \(C\) 而缩放 \(DC\)，得右扭曲 \(U_H\)；一个关于特征标映射 \(B\to DB\) 的迹障碍（trace obstruction）结合对称对偶，制造出真正的双模范射 \(g_H:U_H\to Y\) 且在 \(X\) 上取值非零——单有模映射给不出双模纤维，这是本文独有的难关。归一化 \(H_1,H_2\) 的映射并取有限纤维得 \(F\) 与稳定映射 \(v:X\to F\otimes_E X\)；两个扭曲在每个非零齐次自映射空间（不论正负度）上以相异标量作用，使比较映射在所需区间可逆。在三角代数 \(\Lambda=\begin{pmatrix}E&0\\F&E\end{pmatrix}\) 上作锥，得到具双侧消没画像的完全无环分解（边界度 \(1\) 与 \(-2\) 单独验证），转移原理随即给出对称反例 \((A,M)\)。
最后收割推论：\(G=A\oplus M\) 是无正自扩张的生成余生成模，Mueller 判据给出 \(\Gamma=\End(G)^{\mathrm{op}}\) 的支配维数（dominant dimension）无穷；直接论证 \(\Gamma\) 非自内射，否则经 \(\Hom_A(G,-)\) 函子反推 \(M\) 投射，矛盾，故自内射维数无穷。全投射的极小内射分解必然漏掉某个不可分解内射模 \(J\)，由 \(J\) 与 \(S=\soc J\) 分别否定广义与强 Nakayama；全体不可分解投射-内射模之和 \(W\) 是 Wakamatsu tilting 而非 tilting；内射分解的逐次余核 \(C_n\) 由 Ext 判据归纳得 \(\pd C_n=n\)。域扩张下 Ext 与纯量扩张交换且忠实，一切结论对每个 \(K/k\) 保持。

## 可信度与备注
据任务元信息，本文主定理及同调推论已附 Lean 形式化证明。它与姊妹篇（八单模三角代数上的 Auslander–Reiten 反例）共用同一个 10 维出发代数与锥、三角模机制，但对称化的转移原理、负阶完全扩张控制与迹障碍均为本文独立完成，两文各自包含完整证明、互相印证结构断言。仍应留意 OpenAI 官方声明"未经形式化的结果可能有问题"；本文核心已形式化，风险较低，而推论三、四引用的外部定理（Buan–Solberg、Chen–Fang–Xi）以原文为准。

{% endraw %}
