---
layout: default
title: "Reconstruction from Milnor K-theory modulo the characteristic"
family: "009"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Reconstruction from Milnor K-theory modulo the characteristic

> 结果族 009：Function-field reconstruction from Milnor K-theory and Galois data　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

从域的"模 `@@M@@\ell@@` 快照"重建域，在 `@@M@@\ell@@` 不等于特征时只能认出完美闭包——好比照片只够认出双胞胎。可当模数恰好取域自己的特征 `@@M@@p@@` 时，照片突然变清晰：本文证明，只凭一阶 Milnor K 群模 `@@M@@p@@` 加上二阶 Steinberg 关系，就能直接认出本人——原原本本的域，连同常数域，一个不缺。

**关键词卡片**

- 特征 `@@M@@p@@`（characteristic `@@M@@p@@`）：域中 `@@M@@p@@` 个 1 相加等于 0 的算术环境，例如有限域上的函数域。
- Milnor K 群模 `@@M@@p@@`（`@@M@@K^{\mathrm M}_1/p@@`）：`@@M@@V_F=F^\times/(F^\times)^p@@`；因 `@@M@@(F^\times)^p=(F^p)^\times@@`，元素的等价类恰是射影空间的点。
- Steinberg 关系（Steinberg relations）：`@@M@@[f]\otimes[1-f]=0@@`，本文只需要二阶的这一层关系。
- 射影几何基本定理（fundamental theorem of projective geometry）：保直线的双射必来自唯一的半线性提升——从几何走回代数的桥。
- 导子（derivation）：像微分那样的求导算子，用来检测"谁在谁的 `@@M@@p@@` 次幂扩张里"。

**看个具体例子**

零符号判据：若 `@@M@@s\notin F^p@@` 且 `@@M@@\{s,t\}=0@@`，则 `@@M@@t\in F^p(s)@@`。取 `@@M@@F=k(x,y)@@`、`@@M@@s=x@@`：与 `@@M@@x@@` 配为零的 `@@M@@t@@` 恰好是只含 `@@M@@x@@` 的有理函数——一条"射影直线"被认了出来。再算规模：`@@M@@[F:F^p]=p^{\operatorname{trdeg}}@@`，超越次数 2 时为 `@@M@@p^2\ge4@@`，刚好够射影几何施展拳脚。定理断言

`@@M@@D\operatorname{Isom}(K,k;L,l)\ \longrightarrow\ \operatorname{Isom}_{\mathrm M}(V_K,V_L)/\mathbb F_p^{\times}\quad\text{是双射}，@@`

且 Frobenius 在 `@@M@@V_F@@` 上诱导零映射，连 Frobenius 歧义都不存在。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="60" y1="140" x2="230" y2="50" stroke="#2a5fd6" stroke-width="2"/><line x1="90" y1="185" x2="250" y2="185" stroke="#2a9d4f" stroke-width="2"/><circle cx="80" cy="129" r="5" fill="#2a5fd6"/><circle cx="140" cy="98" r="5" fill="#2a5fd6"/><circle cx="200" cy="66" r="5" fill="#2a5fd6"/><circle cx="110" cy="185" r="5" fill="#2a9d4f"/><circle cx="170" cy="185" r="5" fill="#2a9d4f"/><circle cx="230" cy="185" r="5" fill="#2a9d4f"/><line x1="330" y1="140" x2="500" y2="50" stroke="#2a5fd6" stroke-width="2"/><line x1="360" y1="185" x2="520" y2="185" stroke="#2a9d4f" stroke-width="2"/><circle cx="350" cy="129" r="5" fill="none" stroke="#2a5fd6" stroke-width="2"/><circle cx="410" cy="98" r="5" fill="none" stroke="#2a5fd6" stroke-width="2"/><circle cx="470" cy="66" r="5" fill="none" stroke="#2a5fd6" stroke-width="2"/><circle cx="380" cy="185" r="5" fill="none" stroke="#2a9d4f" stroke-width="2"/><circle cx="440" cy="185" r="5" fill="none" stroke="#2a9d4f" stroke-width="2"/><circle cx="500" cy="185" r="5" fill="none" stroke="#2a9d4f" stroke-width="2"/><line x1="86" y1="129" x2="336" y2="129" stroke="#999" stroke-width="1.5" stroke-dasharray="4 4"/><polygon points="336,124 348,129 336,134" fill="#999"/><line x1="146" y1="98" x2="396" y2="98" stroke="#999" stroke-width="1.5" stroke-dasharray="4 4"/><polygon points="396,93 408,98 396,103" fill="#999"/><line x1="206" y1="66" x2="456" y2="66" stroke="#999" stroke-width="1.5" stroke-dasharray="4 4"/><polygon points="456,61 468,66 456,71" fill="#999"/><text x="66" y="148" font-size="13" fill="#333">a</text><text x="126" y="117" font-size="13" fill="#333">b</text><text x="186" y="85" font-size="13" fill="#333">c</text><text x="104" y="174" font-size="13" fill="#333">d</text><text x="164" y="174" font-size="13" fill="#333">e</text><text x="224" y="174" font-size="13" fill="#333">f</text><text x="155" y="222" font-size="14" text-anchor="middle" fill="#222">K 的射影点</text><text x="435" y="222" font-size="14" text-anchor="middle" fill="#222">L 的射影点</text><text x="280" y="252" font-size="15" text-anchor="middle" fill="#222">Θ 修正后保直线 ⇒ 射影几何基本定理 ⇒ 域同构（示意）</text><text x="280" y="30" font-size="16" text-anchor="middle" fill="#222">直线映成直线（示意）</text></svg>

</div>

**为什么值得关心**

它补上了 Milnor K 重建纲领在"模特征"一侧的缺口，而且证明只靠导子计算与射影几何，出奇地初等；与族内另两篇姊妹工作（模 `@@M@@\ell@@` 情形与 Galois 数据情形）互相印证。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在特征 `@@M@@p@@` 的函数域上，一阶 Milnor K 群模 `@@M@@p@@` 连同二阶 Steinberg 关系（Steinberg relations）足以重构域本身及其代数闭常数域：每个相容同构都是唯一域同构所诱导，只差一个 `@@M@@\mathbb F_p^\times@@` 标量。不同于模 `@@M@@\ell\ne p@@` 情形只能找回完备闭包，这里直接找回原来的域。

## 问题背景

Milnor K 理论（Milnor K-theory）把域的乘法连同加法导出的 Steinberg 关系编码成一族群 `@@M@@K^{\mathrm M}_n(F)@@`，而"重构问题"问：这些群能在多大程度上反推域本身，其同构是否都来自域同构？这类问题属于 Bogomolov 学派的几何重构纲领：Bogomolov–Tschinkel（2009）在特征零从 Milnor K 环重构函数域，Cadoret–Pirutka（2021）推广到完美域上的正则扩张；Topaz（2016、2023）对与特征互素的 `@@M@@\ell@@` 证明模 `@@M@@\ell@@` 数据可重构完备闭包（perfect closure），但需超越次数（transcendence degree）至少 5 及额外输入。而在约去特征本身（`@@M@@\ell=p@@`）的情形，此前没有仅从 `@@M@@V_F=F^\times/(F^\times)^p@@` 与 Steinberg 关系出发、不借助有理子群或代数相关性数据的重构定理——本文补上的正是这块缺口。

## 主要结果

设 `@@M@@K/k@@`、`@@M@@L/l@@` 为代数闭域上有限生成的扩张，特征 `@@M@@p@@`，超越次数均至少 2。记 `@@M@@V_F=F^\times/(F^\times)^p=K^{\mathrm M}_1(F)/p@@`（加法记号），`@@M@@R_F\subset V_F\otimes_{\mathbb F_p}V_F@@` 为由 `@@M@@[f]\otimes[1-f]@@` 张成的 Steinberg 关系子空间，商 `@@M@@W_F=(V_F\otimes V_F)/R_F@@` 即 `@@M@@K^{\mathrm M}_2(F)/p@@`。称 `@@M@@\mathbb F_p@@`-线性同构 `@@M@@\Theta:V_K\to V_L@@` 相容（compatible），若 `@@M@@(\Theta\otimes\Theta)(R_K)=R_L@@`。主定理断言典范映射

`@@M@@D\Isom(K,k;L,l)\longrightarrow\Isom_{\mathrm M}(V_K,V_L)/\mathbb F_p^\times@@`

是双射。换言之：数据 `@@M@@(V_F,R_F)@@`——等价地，`@@M@@K^{\mathrm M}_1/p@@`、`@@M@@K^{\mathrm M}_2/p@@` 及其乘法配对——确定域 `@@M@@F@@` 及其指定常数域；每个相容 `@@M@@\Theta@@` 等于唯一域同构 `@@M@@\alpha@@` 的诱导 `@@M@@\alpha_*@@` 乘以一个非零标量，且 `@@M@@\alpha@@` 自动把 `@@M@@k@@` 映到 `@@M@@l@@`。此处没有 Frobenius 歧义：Frobenius 映射在 `@@M@@V_F@@` 上诱导零映射，论文注记对此作了澄清。

## 证明思路

先换视角，把不变量看成射影几何。因 `@@M@@(F^\times)^p=(F^p)^\times@@`，类 `@@M@@[f]@@` 恰是 `@@M@@F@@` 在 `@@M@@C=F^p@@` 上的一维子空间 `@@M@@Cf@@`，故 `@@M@@V_F@@` 的底层集合就是射影空间 `@@M@@\mathbb P_C(F)@@` 的点集，群运算 `@@M@@[f]+[g]=[fg]@@` 则另行记录乘法。论文先证 `@@M@@[F:C]=p^{\trdeg(F/\kappa)}@@` 有限（对 `@@M@@p@@`-单项式基计数并作塔式消去），于是超越次数至少 2 时维数不小于 `@@M@@p^2\ge4@@`，射影几何论证有了立足点。

再提取零符号的域论含义：若 `@@M@@s\notin F^p@@` 且 `@@M@@\{s,t\}_F=0@@`，则 `@@M@@t\in F^p(s)@@`。证法是把 `@@M@@p@@`-无关对扩充成 `@@M@@p@@`-基（p-basis），取交换的 Euler 导子（Euler derivation），用对数导数搭配出双线性型，直接验证它杀死 Steinberg 关系、却在无关对上取值 1。这只是 Bloch–Gabber–Kato 定理的坐标化影子，但完全初等。

然而 `@@M@@F^p(s)@@` 未必是二维子空间，要得到射影直线 `@@M@@C+Cx@@` 须作幂次修正。关键的交命题：对 `@@M@@p@@`-无关的 `@@M@@X,Y@@` 与非单项式的 `@@M@@U\in C(X)^\times@@`、`@@M@@V\in C(Y)^\times@@`，若乘法平移 `@@M@@X\,C(Y/X)^\times@@` 与 `@@M@@U\,C(V/U)^\times@@` 相交，则存在唯一的 `@@M@@1\le n<p@@` 使 `@@M@@U^n\in C+CX^n@@` 且 `@@M@@V^n\in C+CY^n@@`。证明构造两个导子分别杀死交中元素的两种表达，比较其特征坐标得 `@@M@@A_X=c_XX^m@@`、`@@M@@A_Y=c_YY^m@@` 共享指数 `@@M@@m@@`，再以 `@@M@@n=p-m@@` 解对数导数方程完成"积分"。

接着把 Steinberg 关系变成交。在源空间取仿射构型 `@@M@@u=x+a@@`、`@@M@@v=y+b@@`、`@@M@@z=bx-ay=bu-av@@`，得四个零符号；经 `@@M@@\Theta@@` 传送并由前一步得 `@@M@@Z\in X\,C(Y/X)\cap U\,C(V/U)@@`，交命题遂给出局部修正指数。由该指数的唯一性沿一张连通图（任两点路径长不超过 2）传播，得到统一标量 `@@M@@n@@` 使 `@@M@@\Psi=n\Theta@@` 把直线映入直线；对逆映射重复论证，并用"非平凡标量不保直线"的二项式系数引理，推出 `@@M@@\Psi@@` 把直线映满直线且 `@@M@@n@@` 唯一。

最后从直线回到域。论文自含地证明射影几何基本定理（fundamental theorem of projective geometry）：维数至少 3 时保直线的双射来自唯一的半线性提升，得到加性双射 `@@M@@S:K\to L@@` 与域同构 `@@M@@\sigma:K^p\to L^p@@`；群律迫使 `@@M@@w\mapsto S(fw)@@` 与 `@@M@@w\mapsto S(f)S(w)@@` 诱导同一射影映射且在 `@@M@@1@@` 处相等，由唯一性二者相等，故 `@@M@@S@@` 保乘法、是域同构。再用 Eisenstein 判别法证 `@@M@@\bigcap_{m\ge1}F^{p^m}=\kappa@@`，从而 `@@M@@S(k)=l@@`；定理的单射性最后仍调用标量引理收尾。

## 可信度与备注

本篇与同族姊妹篇互相支撑：模 `@@M@@\ell@@`（`@@M@@\ell\ne p@@`）一篇只能重构完备闭包及其常数域，本篇在模特征情形直接重构原域，两者恰好覆盖两种约化；第三篇则从 pro-`@@M@@\ell@@` Galois 数据证明 Bogomolov–Pop 重构。三篇均无 Lean 形式化证明；论文对交命题与射影提升定理均给出完整初等证明，但按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
