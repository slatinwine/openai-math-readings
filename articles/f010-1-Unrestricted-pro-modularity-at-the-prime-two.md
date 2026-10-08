---
layout: default
title: "Unrestricted pro-modularity at the prime two"
family: "010"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Unrestricted pro-modularity at the prime two

> 结果族 010：Unrestricted pro-modularity at the prime two　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

数论里有两座城市：一座住着伽罗瓦表示——描述有理数域对称性的"密码机"，在每个素数处能读出两个数；另一座住着模形式——极规整的周期函数。几十年的大计划是证明：够好的密码机都能在模形式城查到户籍。这篇论文在最难的素数 2 处把门槛降到最低：密码机只要连续、奇、绝对不可约、只在有限多处"卡顿"，就一定出现在某本"完整 Hecke 大名录"里。

**关键词卡片**

- 伽罗瓦表示（Galois representation）：连续同态 `@@M@@r:G_{\mathbb Q}\to\mathrm{GL}_2@@`，在素数 `@@M@@\ell@@` 处给出 `@@M@@\operatorname{tr}r(\mathrm{Frob}_\ell)@@` 与 `@@M@@\det r(\mathrm{Frob}_\ell)@@`。
- 奇（odd）：复共轭的行列式为 `@@M@@-1@@`；来自几何的表示天然满足这个符号条件。
- 完整 Hecke 代数（completed Hecke algebra）：把一切权的模形式特征值体系粘在一起的大代数，"模形式户籍总册"。
- pro-模性（pro-modularity）：`@@M@@r@@` 的特征值体系出现在总册的谱中；注意这不断言经典模性。
- 剩余表示（residual representation）：`@@M@@r@@` 模 2 后的粗糙版本；本文对它零要求，标量与可约情形照单全收。

**看个具体例子**

定理的数字版是一张"对账单"：存在奇数 `@@M@@N@@` 与同态 `@@M@@\lambda:\mathbb T_2(N)\to\mathcal O_E@@`，使得对一切 `@@M@@\ell\nmid 2N@@`，

`@@M@@D\lambda(T_3)=\operatorname{tr}r(\mathrm{Frob}_3),\qquad \lambda(T_5)=\operatorname{tr}r(\mathrm{Frob}_5),\qquad \lambda(\ell S_\ell)=\det r(\mathrm{Frob}_\ell),\ \ldots@@`

即总册里有一页，逐素数与密码机的读数完全吻合。

**为什么值得关心**

此前的定理都要求 `@@M@@p>2@@` 或剩余表示不可约，素数 2 上一直没有无条件结果。本文把 `@@M@@p=2@@` 处的模性从"带一串附加条件"推进到"无限制"，是同族姊妹篇（`@@M@@p=2@@` 的 Fontaine–Mazur 定理，即真正的经典模性）的发动机。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明：任何连续、奇（odd）、绝对不可约的二维 `@@M@@2@@`-adic 伽罗瓦表示 `@@M@@r:G_{\mathbb Q}\to\GL_2(E)@@`，只要在有限多个素数外不分歧，就必定出现在某个奇数水平的完整 `@@M@@2@@`-adic Hecke 代数中。这在 `@@M@@p=2@@` 处彻底取消了剩余表示与 de Rham 条件的全部限制。

## 问题背景

数论的经典范式断言：来自几何的伽罗瓦表示应源于自守形式。Fontaine–Mazur 猜想（Fontaine–Mazur conjecture，1995）预言：二维、在 `@@M@@p@@` 处 de Rham 且分歧有限的奇表示必与经典模形式相伴；Skinner–Wiles、Emerton、Pan 等在奇素数或剩余可约等附加条件下逐步逼近。但若连 `@@M@@p@@` 处的 Hodge 条件也放弃，问题就换了一副面孔：把一切权的模形式的 Hecke 特征值粘合起来，会得到一个 `@@M@@p@@`-adic 大代数，问表示是否落在这个大代数的谱中？这就是 Emerton 记录的 pro-模性（pro-modularity）期望。此前的定理都要求 `@@M@@p>2@@`、剩余表示不可约或局部剩余限制，素数 `@@M@@2@@` 上一直没有无条件结果——`@@M@@2@@`-adic 局部表示分类与形变理论在 `@@M@@2@@` 处的特殊困难是主要障碍。

## 主要结果

固定奇数 `@@M@@N@@`。令 `@@M@@T_{\le k}^{(2)}(N)@@` 为作用在水平 `@@M@@\Gamma_1(N)@@`、权不超过 `@@M@@k@@` 的全模形式空间（含 Eisenstein 形式）上、由 `@@M@@T_\ell@@` 与 `@@M@@\ell S_\ell@@` 生成的 Hecke 代数，并定义完整 `@@M@@2@@`-adic Hecke 代数（completed Hecke algebra）`@@M@@\mathbb T_2(N)=\varprojlim_k(\mathbb Z_2\otimes T_{\le k}^{(2)}(N))@@`。

主定理：设 `@@M@@E/\mathbb Q_2@@` 有限，`@@M@@r:G_{\mathbb Q}\to\GL_2(E)@@` 连续、绝对不可约、在有限多个素数外不分歧，且奇——`@@M@@\det r(c)=-1@@`，`@@M@@c@@` 为复共轭。则存在奇数 `@@M@@N@@`（含尽 `@@M@@r@@` 的所有奇分歧素数）与连续 `@@M@@\mathbb Z_2@@`-代数同态 `@@M@@\lambda:\mathbb T_2(N)\to\mathcal O_E@@`，使对每个 `@@M@@\ell\nmid 2N@@` 有 `@@M@@\lambda(T_\ell)=\operatorname{tr}r(\operatorname{Frob}_\ell)@@`、`@@M@@\lambda(\ell S_\ell)=\det r(\operatorname{Frob}_\ell)@@`。

作者称此结论为 pro-模性。它对剩余表示（residual representation）不加任何条件——标量与可约剩余情形都包括在内；水平 `@@M@@N@@` 允许添加辅助素数；对 `@@M@@r@@` 在 `@@M@@2@@` 处不设任何 de Rham 假设。要注意：这是"出现在完整 Hecke 代数中"的发生性结论，论文明确说明它不断言经典模性。

## 证明思路

先归一化。由类域论分离 `@@M@@\det r@@` 的 `@@M@@2@@`-adic 部分与奇导子部分，经一次连续分圆扭（cyclotomic twist）可设 `@@M@@\det r=\chi=\delta\varepsilon^w@@`，且 `@@M@@w@@` 足够大，使 `@@M@@\chi@@` 恰为某个非 CM 正则尖点模表示的行列式（尖点维数随权线性增长而 CM 形式有界）。再过 `@@M@@r@@` 取固定行列式形变空间的整分量 `@@M@@B@@` 及其迹像 `@@M@@D@@`：奇性使实局部形变环光滑二维，绝对不可约性给出关系估计 `@@M@@g-r\ge 3@@`，故 `@@M@@\dim B\ge 6@@`、`@@M@@\dim D\ge 3@@`；对二面体与 `@@M@@A_4,S_4,A_5@@` 型可解轨迹的维数估计保证族的泛表示绝对不可约。

继而做可解全实基变换：以剩余表示的正则尖点提升为"种子"，经 Jacquet–Langlands 转移到定四元数模形式取得 Hecke 支持，再用姊妹篇的局部化传播定理沿特征 `@@M@@2@@` 曲线把支持扩到全族。所取全实域在 `@@M@@2@@` 完全分裂，故族的 `@@M@@b=[F:\mathbb Q]@@` 个 `@@M@@2@@`-adic 局部参数全相同——此即"对角"结构。由 Paškūnas–Tung 的块等价（block equivalence，含标量剩余块），乘积群上先得可容许（admissible）紧对象；关键的局部新意是把可容许性降到单个因子：若单因子对象的 `@@M@@K@@`-不变量余空间无穷维，其支持便含特征 `@@M@@2@@` 曲线，而曲线泛点处角幂等元为满、所有单模的余空间消没判定一致（两诱导特征在行列式一的稳定子上取值互逆），故可对 `@@M@@b@@` 个因子逐一检验，得乘积对象在该曲线上纤维非零，与乘积可容许性矛盾。

随后制造正则点。以 Iwasawa 代数 `@@M@@\mathcal O[[K]]@@` 上模的 Hilbert 增长次数为尺，沿 `@@M@@D@@` 内饱和素链做 `@@M@@\dim D-1@@` 次素特化，每次至少降一次，末端纤维无穷维迫使增长次数达到最大值 `@@M@@4@@`，从而该对象有正 Iwasawa 秩。正秩产生局部代数向量，其类型为 `@@M@@\sigma\otimes U@@`，`@@M@@\sigma@@` 是 `@@M@@\GL_2(\mathbb F_2)\cong S_3@@` 的符号特征（有限群的尖点型），它排除一切可约伽罗瓦参数，又对应深度零超尖表示；于是公共特征点 `@@M@@x@@` 处的 `@@M@@r_x@@` 在 `@@M@@2@@` 处绝对不可约、正则 de Rham、Weil–Deligne 参数在野惯性上平凡，由姊妹篇的正则 Fontaine–Mazur 定理知 `@@M@@r_x@@` 经 Tate 扭后来自经典尖点形式。

最后收口。Newton–Thorne 的伴随 Selmer 群消没（野惯性平凡恰好排除 CM 域含于 `@@M@@\mathbb Q(\zeta_{2^\infty})@@` 的情形）与 Bloch–Kato 局部公式给出切空间界 `@@M@@\dim H^1(G_\mathbb Q,\operatorname{ad}r_x)\le 3@@`；另一姊妹篇证得 Hecke 代数每个不可约分量维数为 `@@M@@4@@`，在系数点局部化后恰为 `@@M@@3@@`。两数相等迫使变行列式整体形变环在 `@@M@@x@@` 处正则，其到 Hecke 代数的核局部化为零；`@@M@@D@@` 是整环，核必整体为零，于是全族连同原表示的点都落在 `@@M@@\mathbb Q@@` 上的 Hecke 支持中。撤销最初的 twist（连续分圆扭保持 Hecke 点），即得主定理。

## 可信度与备注

主结果暂无 Lean 形式化证明，请以社区核验为准。本文是同族三篇之一，且深度依赖两位姊妹篇：Hecke 代数每个不可约分量维数为 `@@M@@4@@` 的维数定理，以及基变换、局部化传播与正则 Fontaine–Mazur 定理，都是本文证明的关键输入，三篇互相支撑构成闭环。按 OpenAI 官方声明，未经形式化的结果可能有问题，阅读时请以此为前提。

{% endraw %}
