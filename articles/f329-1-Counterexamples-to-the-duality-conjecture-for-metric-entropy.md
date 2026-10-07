---
layout: default
title: "Counterexamples to the duality conjecture for metric entropy"
family: "329"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Counterexamples to the duality conjecture for metric entropy

> 结果族 329：A counterexample to metric-entropy duality　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文推翻了 Pietsch 1972 年提出的度量熵对偶猜想：对任意提议的普适常数 \(a,b\ge1\)，都能构造中心对称凸体 \(K\) 与立方体 \(L=[-1,1]^n\)，使 \(\log N(K,L)>b\log N(L^\circ,a^{-1}K^\circ)\)。这一悬置五十余年的猜想由此得到否定的回答。

## 问题背景

覆盖数 (covering number) \(N(A,B)\) 是覆盖集合 \(A\) 所需的 \(B\) 的平移的最少个数，其对数量化一个集合的"度量复杂度"。1972 年 Pietsch 在研究算子的熵数 (entropy numbers) 时提出对偶猜想 (duality conjecture)：是否存在绝对常数 \(a,b\ge1\)，使一切维数、一切中心对称凸体 (origin-symmetric convex body) \(K,L\) 都满足 \(\frac1b\log N(L^\circ,aK^\circ)\le\log N(K,L)\le b\log N(L^\circ,a^{-1}K^\circ)\)，其中 \(K^\circ\) 是极体 (polar body)。直观地说，它问"取极"这一对偶操作能否在普适的尺度与常数变化下保持覆盖复杂度。此前所有正面结果都限于特殊情形：一边是椭球时猜想成立（Artstein–Milman–Szarek 2004）；凸化堆积 (convexified packing) 的相应对偶成立（AMSTJ 2004）；一般对称凸体只有带对数损失的比较（E. Milman 2007）。普适常数对究竟是否存在，五十余年无人能证、也无人能否——本文给出否定答案。

## 主要结果

**定理 1（主定理）**　对任意 \(a,b\ge1\)，存在正整数 \(n\) 与 \(\R^n\) 中的中心对称凸体 \(K\)，使得取立方体 \(L=[-1,1]^n\) 时
\[\log N(K,L)>b\log N(L^\circ,a^{-1}K^\circ).\]
于是猜想中的上界对每一对候选常数都失效，双边猜想整体不成立——而且反例里覆盖体已经是最简单的立方体。两点澄清：反例的维数 \(n\) 随参数 \(a,b\) 增长，论文不对任何固定维数下断言；\(K\) 具有非空内部，是货真价实的凸体。论文还给出渐近版本：固定 \(a\)、让参数 \(r\) 增大时，两个熵的对数比 \(\log N(L_r^\circ,a^{-1}K_r^\circ)/\log N(K_r,L_r)\to0\)，悬殊程度可任意大。文末的推论进一步把普通覆盖熵与凸化堆积熵 \(\widehat M\) 分离：对任意 \(A,C\ge1\) 存在 \(K\) 使 \(\log N(K,L)>C\log\widehat M(K,L/A)\)，说明 AMSTJ 的凸化堆积对偶定理救不回普通版本。

## 证明思路

证明是一条四步流水线：几何转换、组合压缩、有限域构造、参数选择。

先做矩阵到凸体的转换（第 2 节）。设一个实矩阵的行为 \(R_x\)，两两在 sup 范数下距离 \(\ge1\)，列的绝对凸包 (absolutely convex hull) 有大小为 \(M\) 的 \(\varepsilon\)-一致逼近表。令 \(K=3\absconv\{R_x\}+tB_\infty^Y\)，\(L=B_\infty^Y\)。一方面，\(L\) 的每个平移直径为 \(2\)，装不下相距 \(3\) 的两点 \(3R_x\)，故 \(N(K,L)\ge|X|\)；另一方面，支撑函数 (support function) 恰为 \(h_K(\delta)=3\|f_\delta\|_{\infty,X}+t\|\delta\|_1\)，把逼近表按"最先命中"分成 \(M\) 簇并各选一个真实系数向量作代表，即得 \(N(L^\circ,(6\varepsilon+2t)K^\circ)\le M\)。于是反例归结为：造一个行很多、列凸包的逼近表却很短的矩阵。

再证压缩定理（第 3 节），这是全文最可复用的一步。设有限集 \(X\) 带 \(u\) 个至多 \(q\) 类的划分；两点若在某划分 \(i\in T\) 中同类则相连，得图距离 \(d_T\)；列取对数轮廓 (logarithmic profile) \(g_{(v,T)}(x)=\phi_h(d_T(x,v))\)。断言：总质量 \(\le1\) 的非负列组合有一致逼近表，\(\log Q\le hs\log q+C_{h,\theta,u}\)，关键在于代价只依赖标签数 \(q\) 而与 \(|X|\) 无关。证明先用平均论证找到一个除 \(\theta\) 质量外都在场的公共划分 \(i_0\)；再在每个距离层用贪心法选至多 \(s=\lceil1/\theta\rceil\) 个支点，捕获每个点处除 \(\theta\) 外的全部质量；点睛之笔是把支点替换成它在 \(i_0\) 划分中的类代表——编码只需存储标签而非原点，代价是距离从 \(j\) 膨胀到 \(3j+2\)，而对数轮廓恰好把该膨胀的误差压到 \(\log3/\log(h+1)\le\theta\)；最后把权重舍入到固定粒度再计数。符号情形拆 \(\lambda=\lambda^+-\lambda^-\)，得长 \(Q^2\)、误差 \(6\theta\) 的逼近表。

然后用有限域造划分并分离行（第 4 节）。取 \(X\) 为 \(\F_p^r\) 上全体对称 \(h\) 线性型 (symmetric \(h\)-linear form)，\(|X|=p^{D_h}\)，\(D_j=\binom{r+j-1}{j}\)；随机取方向 \(t_1,\ldots,t_u\)，划分取收缩 (contraction) \(L_i(x)=x(t_i,\cdot,\ldots,\cdot)\)，标签至多 \(q=p^{D_{h-1}}\) 个，而 \(D_{h-1}/D_h=h/(r+h-1)\to0\)。Schwartz–Zippel 多项式零点估计配合对角多项式恢复与联合界表明：以正概率，每个非零型删去 \(\theta\) 份额的方向后，在剩余指标的任意 \(h\) 元组（允许重复）上取值非零。假如图中存在长度 \(\le h\) 的路径连接相异两点 \(x,y\)，则 \(Z=y-x\) 分解为沿路径的增量之和，每个增量都被路径上某方向杀死，由对称性 \(Z\) 在由这些方向拼成的 \(h\) 元组上必为零——矛盾。故 \(d_T(x,y)>h\)，行分离恰为 \(1\)。

最后按依赖顺序选参数（第 5 节）：先固定 \(\theta=1/(1000a)\)、\(h\) 与 \(r\)（使 \(r+h-1>8bh^2s\)），最后取足够大的素数 \(p\) 把全部编码常数 \(C\) 吸收掉，得 \(\log(Q^2)/\log|X|<1/(2b)\)，与前面的估计拼起来正是 \(b\log N(L^\circ,a^{-1}K^\circ)<\log N(K,L)\)。素数最后才选——这一依赖顺序是压垮对偶猜想的最后一击。

## 可信度与备注

本文主定理已有 Lean 形式化证明（结果族 329，见 lean/docs/329.md），属验证等级最高的一档；论证链的四个环节在文中均自足给出，不依赖外部黑箱。本结果族目前仅此一篇手稿，其结论与文献中的正面结果并不矛盾——椭球情形与凸化堆积情形的定理恰好不覆盖此处的一般对称凸体，反例正落在缝隙里。按 OpenAI 官方声明，"未经形式化的结果可能有问题"；本篇主定理已形式化，不在此列，但文中渐近形式与推论是否同在形式化范围内，请以社区核验为准。

{% endraw %}
