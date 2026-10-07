---
layout: default
title: "Sharpness of the Cyclic Integral Floer Bound Below the Stable Morse Number"
family: "347"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Sharpness of the Cyclic Integral Floer Bound Below the Stable Morse Number

> 结果族 347：Counterexamples to stable-Morse and strong Arnold fixed-point bounds　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
本文构造出实维 \(3332\)、极小陈数为 \(1\) 的单连通闭凯勒流形上的哈密顿微分同胚：其 \(1\,872\,232\) 个非退化不动点恰好取等 Bai–Xu 的循环分次整 Floer 下界，却仍比稳定 Morse 数 \(1\,872\,264\) 少 \(32\) 个——证明更强的稳定 Morse 下界即便在现有整 Floer 下界取等的极端情形下依然失效。

## 问题背景
Arnold 不动点问题的整系数细化把"下界"分成了两支。一支是几何的、猜想性的：稳定 Morse 数（stable Morse number）\(\SM(W)\) 保留整同调分度，由 Smale 定理在单连通高维流形上等于 \(\lambda(W)=b(W)+2\sum_i t_i(W)\)（\(t_i\) 为挠子群最少生成元数），Golovko 2020 年明确把它写成非退化哈密顿不动点的下界猜想。另一支是已证的：Abouzaid–Blumberg 给出任意正特征域上的下界，Bai–Xu 进一步得到纳入全部素数挠的整 Floer 下界，但其同调按极小陈数（minimal Chern number）的两倍取模分次——极小陈数为 \(1\) 时即按奇偶合并，不同整度上的挠类进入同一群、可以共享生成元。这两个计数何时真正不同？差多少？本文给出一个精确到个位数的回答。

## 主要结果
记 \(\beta^{\mathrm{cyc}}_\Z(W)=b(W)+2\sum_{\bar i\in\Z/2}d\bigl(\Tor\overline H_{\bar i}(W;\Z)\bigr)\)，其中 \(\overline H_{\bar i}\) 是把同一奇偶性的整同调合并后的群、\(d\) 为最少生成元数。主定理：存在复维 \(1666\) 的单连通闭凯勒（Kähler）流形 \((M,\omega)\)，满足 \(c_1(TM)(\pi_2(M))=\Z\)（即极小陈数为 \(1\)），以及光滑 1-周期哈密顿量 \(H\)，使所有不动点非退化（nondegenerate）、轨道闭路可缩，且
\[\#\Fix(\phi^1_H)=\#\Fix_0(\phi^1_H;H)=\beta^{\mathrm{cyc}}_\Z(M)=1\,872\,232,\qquad \SM(M)=\beta^{\mathrm{cyc}}_\Z(M)+32=1\,872\,264.\]
由于极小陈数为 \(1\) 时 Bai–Xu 下界恰为 \(\beta^{\mathrm{cyc}}_\Z\)，本例同时说明两件事：该整 Floer 下界是可达的（sharp），而稳定 Morse 下界恰差 \(32\) 失效。

## 证明思路
框架沿用族内母篇的三大部件。其一，\(\SM\geq\lambda\) 的几何下界（截断到紧区域、侧边界取切向梯度式场、Morse 胶粘、Smith 正规形秩不等式）与 Smale 定理（维数足够高的单连通流形上取等 \(\lambda\)）。其二，双椭圆曲面（bielliptic surface）\(S_2\)、\(S_3\) 供应 \((\Z/2)^2\) 与 \(\Z/3\) 挠，整爆破公式 \(H_i(\widehat A;\Z)\cong H_i(A;\Z)\oplus\bigoplus H_{i-2j}(Z;\Z)\) 把挠原样搬进爆破流形。其三，\(Y=\CP^1\times\CP^1\) 四角爆破上对角圆作用的半转是哈密顿对合（Hamiltonian involution），不动集为 4 条例外直线；小扰动 \(\psi^\epsilon\circ g\) 的不动点恰为 4 份不动分支 \(C=X\times\CP^1\) 上 Morse 函数的临界点（短周期引理排除其余，全部非退化）。于是不动点数 \(=4\lambda(C)\)，问题化为设计 \(X\) 的逐度挠重数，使 \(4\lambda(C)=\beta^{\mathrm{cyc}}(M)<\lambda(M)\)。

\(X\) 的构造是本文精华。取 \(N=1664\)，在 \(\CP^N\) 里放七个两两不交的中心：2 份 \(S_2\times\CP^1\)、3 份 \(S_3\)、2 份 \(S_3\times\CP^2\)。由 Segre 嵌入，它们的接受向量维数分别为 \(90,165,495\)，而 \(2\cdot90+3\cdot165+2\cdot495=1665=N+1\) 恰好铺满 \(\C^{N+1}\) 的一个直和分解，从而中心两两不交。整爆破公式给出逐度挠重数 \(a_j=4f_1(j)\)、\(q_j=3f_0(j)+2f_2(j)\)，其差 \(\delta=a-q\) 在支撑上恒为 \(-1\)、仅在 \(j=2\) 与 \(j=L-1\)（\(L=1661\)）两处为 \(+1\)——这是刻意设计的"几乎处处被 3-素压倒"格局。

比较两个卷积核便是全部机密。奇偶合并后 3-素总重数 \(Q=14937\) 超过 2-素总数 \(A=13280\)，故 \(\beta^{\mathrm{cyc}}(M)=8b(X)+32Q\)。与 \(\CP^1\) 的核 \((1,1)\) 卷积后，\(\delta_j+\delta_{j-1}\) 逐项 \(\leq0\)——每个 \(+1\) 都被相邻的 \(-1\) 吞掉——于是 \(C\) 的每个度上都是 3-素重数达到最大值，\(\lambda(C)=2b(X)+8Q\)，从而 \(4\lambda(C)\) 恰等于 \(\beta^{\mathrm{cyc}}(M)\)：Floer 界取等。而与 \(Y\) 的核 \((1,6,1)\) 卷积后，中间权重 \(6\) 使 \(j=3\) 处出现 \(-1+6-1=+4\) 的正超额（由对称性 \(j=L\) 处亦然，其余指标至多 \(-4\)），逐度和为 \(8Q+8\)；两个奇偶类与 \(\lambda\) 中的因子 2 合计，得 \(\lambda(M)=8b(X)+32Q+32\)，恰比 \(\beta^{\mathrm{cyc}}\) 多 \(32\)。代入 \(b(X)=174281\) 即得 \(\lambda(C)=468058\)、\(\beta^{\mathrm{cyc}}=1\,872\,232\)、\(\SM=1\,872\,264\)。这一步完全是有限序列的组合演算，与几何实现干净分离；极小陈数 \(1\) 则来自 \(Y\) 中例外直线的切度 \(2\) 减法度 \(-1\)。

## 可信度与备注
本文暂无形式化证明。它与族内另两篇共享同一"混合素挠 + 哈密顿对合"机制：母篇给出首例（差 \(16\)、维数 \(1412\)），姊妹篇把亏额推到无界（\(16m\)、实维固定 \(22\)），本文进一步表明现有最强的循环整 Floer 下界在反例上精确取等——说明稳定 Morse 界的失效不是 Floer 界"不够紧"的巧合，而是整数分度确实携带循环分次看不见的信息。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
