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

## 入门导读 🐣

乐器若完全不会自我干扰（没有杂音回授），直觉上它该是一件"标准乐器"。Tachikawa 在 1973 年猜想在"自带完美隔音房"的自内射代数里，无自我干扰的模块必是标准件。这篇论文造出一件不标准却毫无自我杂音的乐器，还让一排相连的猜想像多米诺骨牌般接连倒下。

**关键词卡片**

- 对称代数（symmetric algebra）：与自身对偶同构的有限维代数，天然自内射
- 自内射代数（self-injective algebra）：每个内射模都投射的代数，"自带隔音房"
- 自正交模（self-orthogonal module）：所有正阶 `@@M@@\operatorname{Ext}(M,M)@@` 为零的模块，即无自我干扰
- 支配维数（dominant dimension）：衡量代数离自内射有多远的刻度，反例的推论里它可无穷大

**看个具体例子**

构造是一条层层放大的流水线：从 10 维出发代数 `@@M@@C@@`，做平凡扩张得 20 维对称代数 `@@M@@T@@`，张量起来得 400 维对称代数 `@@M@@E@@`，最终造出对称代数 `@@M@@A@@` 与非投射模 `@@M@@M@@`，满足

`@@M@@D\operatorname{Ext}^i_A(M,M)=0\quad\text{对一切 } i>0 .@@`

由于对称代数自内射，`@@M@@\operatorname{Ext}^i_A(M,A)@@` 自动为零，同一例子也是 Auslander–Reiten 猜想对称情形的反例。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="55" y="55" font-size="14" fill="#888">系数域 k = F₂(q,H₁,H₂) 全程不变</text>
<rect x="30" y="105" width="95" height="60" fill="#eef3ff" stroke="#35a"/>
<text x="52" y="130" font-size="15" fill="#235">C：10 维</text>
<text x="52" y="150" font-size="12" fill="#556">出发代数</text>
<line x1="125" y1="135" x2="163" y2="135" stroke="#555" stroke-width="2"/>
<polygon points="165,135 155,130 155,140" fill="#555"/>
<rect x="168" y="105" width="95" height="60" fill="#f2f7ee" stroke="#4a3"/>
<text x="186" y="130" font-size="15" fill="#253">T：20 维</text>
<text x="183" y="150" font-size="12" fill="#455">平凡扩张</text>
<line x1="263" y1="135" x2="301" y2="135" stroke="#555" stroke-width="2"/>
<polygon points="303,135 293,130 293,140" fill="#555"/>
<rect x="306" y="105" width="105" height="60" fill="#fdf3ee" stroke="#c53"/>
<text x="316" y="130" font-size="14" fill="#532">E=T⊗T：400 维</text>
<text x="330" y="150" font-size="12" fill="#655">对称代数</text>
<line x1="411" y1="135" x2="449" y2="135" stroke="#555" stroke-width="2"/>
<polygon points="451,135 441,130 441,140" fill="#555"/>
<rect x="454" y="105" width="80" height="60" fill="#f6f0fa" stroke="#84a"/>
<text x="474" y="130" font-size="15" fill="#53a">A：反例</text>
<text x="468" y="150" font-size="12" fill="#75a">对称代数</text>
<text x="55" y="210" font-size="14" fill="#888">成果：Ext^i_A(M,M)=0 对一切 i＞0，但 M 非投射</text>
<text x="55" y="235" font-size="14" fill="#888">多米诺倒下：经典/广义/强 Nakayama、Auslander–Gorenstein、</text>
<text x="55" y="258" font-size="14" fill="#888">Wakamatsu tilting 猜想接连失败</text>
</svg>

</div>

**为什么值得关心**

一个模块同时击倒 Tachikawa 第二猜想与 Auslander–Reiten 猜想的对称情形，其自同态代数又推倒一整排 Nakayama 型猜想——同调猜想之间的联动从未如此清晰。

> 已 Lean 形式化

## 一句话结论
本文否定 Tachikawa 第二猜想：在 `@@M@@k=\mathbb F_2(q,H_1,H_2)@@` 上构造有限维对称代数 `@@M@@A@@` 与非投射模 `@@M@@M@@`，使 `@@M@@\Ext^i_A(M,M)=0@@` 对一切 `@@M@@i>0@@`；其自同态代数进而使经典、广义、强 Nakayama 猜想、Auslander–Gorenstein 猜想与 Wakamatsu tilting 猜想一并失败，且对一切域扩张稳健。

## 问题背景
Tachikawa 第二猜想出自 Tachikawa 1973 年关于拟 Frobenius 代数（quasi-Frobenius algebra）与支配维数的专著：有限维自内射代数（self-injective algebra）上的自正交模（self-orthogonal module，即 `@@M@@\Ext^i(M,M)=0@@` 对一切 `@@M@@i>0@@`）必为投射模。它与 Auslander–Reiten 猜想关系密切：自内射时 `@@M@@\Ext^i(M,A)@@` 自动为零，故本猜想恰是 Auslander–Reiten 猜想的自内射情形。此前正面结果限于小 radical 类：Zhang–Zhou 处理 radical 立方零的可裂代数与 Igusa–Todorov 代数，Xia 处理量子完全交；Erdmann 的分类表明量子外代数类代数只有"高阶自扩张消尽"的模；Böhmler–Marczinzik 的交换例子也仅前两阶自扩张为零。Schulz 的无自扩张非投射模则生活在除环上，不属于域上有限维代数。Enomoto–Marczinzik 还证明二重平凡扩张上的 Tachikawa 第二猜想蕴含原代数的 Auslander–Reiten 猜想，可见该情形是关键试验场。真正的卡点：在对称代数上没有任何已知机制能同时消尽全部正阶自扩张。

## 主要结果
主定理：取 `@@M@@k=\mathbb F_2(q,H_1,H_2)@@`（三参数代数无关），存在有限维对称代数（symmetric algebra，即 `@@M@@A\simeq DA@@` 作为双模同构，必自内射）`@@M@@A@@` 与非投射有限维模 `@@M@@M@@`，满足 `@@M@@\Ext^i_A(M,M)=0@@` 对一切 `@@M@@i>0@@`。这直接否定 Tachikawa 第二猜想；又因 `@@M@@A@@` 自内射时 `@@M@@\Ext^i(M,A)@@` 自动为零，同一例子也是 Auslander–Reiten 猜想的对称反例。
推论一（同调猜想）：对任意域扩张 `@@M@@K/k@@`，令 `@@M@@\Gamma_K=\End_{A_K}(A_K\oplus M_K)^{\mathrm{op}}@@`，则 (1) `@@M@@\Gamma_K@@` 的极小内射分解每一项都投射，但自内射维数无穷——经典 Nakayama 猜想失败；(2) 存在非零单模 `@@M@@S@@` 使 `@@M@@\Ext^i_{\Gamma_K}(S,\Gamma_K)=0@@` 对一切 `@@M@@i\ge0@@`——广义与强 Nakayama 猜想失败；(3) 存在投射且内射的 Wakamatsu tilting 模 `@@M@@W@@` 不是 tilting 模——Wakamatsu tilting 猜想失败；Auslander–Gorenstein 猜想同样失败。
推论二（finitistic 维数）：对每个 `@@M@@n\ge1@@` 有投射维数恰为 `@@M@@n@@` 的有限模 `@@M@@C_n@@`，故 `@@M@@\Gamma_K@@` 的小、大左 finitistic 维数均为无穷。
推论三、四：`@@M@@\Gamma_K^{\mathrm{op}}@@` 上存在具有无穷多两两不同构不可分解补的投射几乎完全 tilting 模（经由 Buan–Solberg 定理）；对每个 `@@M@@L\ge1@@` 存在具长至少 `@@M@@L@@` 幂等分层（idempotent stratification）的辅助不可分解对称代数及相应导出范畴 recollement 链（经由 Chen–Fang–Xi 的镜像反射构造）。

## 证明思路
证明先立"转移原理"再造数据，最后经自同态代数收割推论。
先证转移原理（对任意有限维代数成立）：若 `@@M@@\Lambda@@` 上有完全无环（totally acyclic，即 `@@M@@\Hom@@` 到 `@@M@@\Lambda@@` 后仍正合）复形 `@@M@@P_Z@@`，其余核 `@@M@@Z@@` 非投射，且完全自扩张复形满足双侧消没 `@@M@@H^a\Hom_\Lambda(P_Z,Z)=0@@` 对 `@@M@@a>0@@` 及 `@@M@@a\le-2@@`，则平凡扩张 `@@M@@A=\Lambda\ltimes D\Lambda@@`（自动对称）与诱导模 `@@M@@M=A\otimes_\Lambda Z@@` 即所求。关键在于 `@@M@@A@@` 作为右 `@@M@@\Lambda@@`-模分解为 `@@M@@\Lambda\oplus D\Lambda@@`，故 `@@M@@M@@` 限制后为 `@@M@@Z\oplus N@@`；归纳–限制伴随把 `@@M@@\Ext_A(M,M)@@` 拆成 `@@M@@\Ext_\Lambda(Z,Z)\oplus\Ext_\Lambda(Z,N)@@`，前项由 `@@M@@a>0@@` 的消没控制，后项经对偶 `@@M@@D H^{-a-1}\Hom_\Lambda(P_Z,Z)@@` 恰由 `@@M@@a\le-2@@` 的消没控制——这正是比姊妹篇多做负阶控制的原因。
再造数据：沿用同一 10 维代数 `@@M@@C@@` 及平凡扩张 `@@M@@T=C\ltimes DC@@`，单模 `@@M@@s@@` 满足 `@@M@@\Ext_T^*(s,s)=k[\tau]@@`、`@@M@@|\tau|=3@@`；导出归纳 `@@M@@\mathcal J=T\otimes_C^{\mathbf L}s@@` 落在三角形 `@@M@@s[2]\to\mathcal J\to s\xrightarrow{\tau}s[3]@@` 中。取 `@@M@@E=T\otimes T@@`（对称）、`@@M@@X=s\otimes s@@`，自扩张代数为 `@@M@@k[\tau_1,\tau_2]@@`。张量两个三角形算出 `@@M@@E\otimes_B^{\mathbf L}X\simeq\mathcal J\otimes\mathcal J@@`（`@@M@@B=C\otimes C@@`）：非负稳定自映射上得到双变量 Koszul 序列，负向由对称稳定对偶（Tate 对偶）得到其对偶，最终只剩两个一维空间。`@@M@@E\otimes_B^{\mathbf L}E@@` 的 bar 复形给出双侧投射的有限双模 `@@M@@Y@@`，其稳定 Hom 画像 `@@M@@W^a@@` 仅在 `@@M@@a\in\{-3,0\}@@` 处为 `@@M@@k@@`。对 `@@M@@H\in k^\times@@`，扭曲 `@@M@@h_H@@` 固定 `@@M@@C@@` 而缩放 `@@M@@DC@@`，得右扭曲 `@@M@@U_H@@`；一个关于特征标映射 `@@M@@B\to DB@@` 的迹障碍（trace obstruction）结合对称对偶，制造出真正的双模范射 `@@M@@g_H:U_H\to Y@@` 且在 `@@M@@X@@` 上取值非零——单有模映射给不出双模纤维，这是本文独有的难关。归一化 `@@M@@H_1,H_2@@` 的映射并取有限纤维得 `@@M@@F@@` 与稳定映射 `@@M@@v:X\to F\otimes_E X@@`；两个扭曲在每个非零齐次自映射空间（不论正负度）上以相异标量作用，使比较映射在所需区间可逆。在三角代数 `@@M@@\Lambda=\begin{pmatrix}E&0\\F&E\end{pmatrix}@@` 上作锥，得到具双侧消没画像的完全无环分解（边界度 `@@M@@1@@` 与 `@@M@@-2@@` 单独验证），转移原理随即给出对称反例 `@@M@@(A,M)@@`。
最后收割推论：`@@M@@G=A\oplus M@@` 是无正自扩张的生成余生成模，Mueller 判据给出 `@@M@@\Gamma=\End(G)^{\mathrm{op}}@@` 的支配维数（dominant dimension）无穷；直接论证 `@@M@@\Gamma@@` 非自内射，否则经 `@@M@@\Hom_A(G,-)@@` 函子反推 `@@M@@M@@` 投射，矛盾，故自内射维数无穷。全投射的极小内射分解必然漏掉某个不可分解内射模 `@@M@@J@@`，由 `@@M@@J@@` 与 `@@M@@S=\soc J@@` 分别否定广义与强 Nakayama；全体不可分解投射-内射模之和 `@@M@@W@@` 是 Wakamatsu tilting 而非 tilting；内射分解的逐次余核 `@@M@@C_n@@` 由 Ext 判据归纳得 `@@M@@\pd C_n=n@@`。域扩张下 Ext 与纯量扩张交换且忠实，一切结论对每个 `@@M@@K/k@@` 保持。

## 可信度与备注
据任务元信息，本文主定理及同调推论已附 Lean 形式化证明。它与姊妹篇（八单模三角代数上的 Auslander–Reiten 反例）共用同一个 10 维出发代数与锥、三角模机制，但对称化的转移原理、负阶完全扩张控制与迹障碍均为本文独立完成，两文各自包含完整证明、互相印证结构断言。仍应留意 OpenAI 官方声明"未经形式化的结果可能有问题"；本文核心已形式化，风险较低，而推论三、四引用的外部定理（Buan–Solberg、Chen–Fang–Xi）以原文为准。

{% endraw %}
