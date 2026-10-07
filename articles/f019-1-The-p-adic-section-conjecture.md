---
layout: default
title: "The p-adic section conjecture"
family: "019"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The p-adic section conjecture

> 结果族 019：The local <i>p</i>-adic section conjecture and global consequences　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明局部 \(p\) 进截面猜想：对 \(\mathbb Q_p\) 任一有限扩域上亏格至少 2 的光滑正常几何连通曲线，有理点与算术平展基本群的截面共轭类一一对应；结合既有有限下降定理，还推出 \(X_0(N)\)、\(X_1(N)\) 等曲线上 Grothendieck 整体截面猜想。

## 问题背景
1983 年 Grothendieck 在致 Faltings 的信中提出截面猜想（section conjecture）：数域上亏格至少 2 的曲线 \(C\) 的有理点，应恰对应算术平展基本群（arithmetic étale fundamental group）正合列 \(1\to\pi_1(C_{\bar F})\to\pi_1(C)\to G_F\to1\) 的连续分裂截面（section）在几何基本群共轭下的类。每个有理点给出一个"几何截面"，猜想问能否纯用群论恢复出几何点。局部版本把数域换成 \(\mathbb Q_p\) 的有限扩域，同时保留完整的算术群与几何群。此前 Koenigsmann 证明了双有理版本（截面必落入某有理点的分解群 decomposition group），Pop–Stix 证明任一截面可局部化到某个延拓 \(p\) 进赋值的分解群，Bresciani 则证明非几何截面必有指标被 \(p\) 整除的有限平展邻域。真正卡住的一步是：从"截面落在某赋值的分解群中"推进到"该赋值来自有理点"。这需要比较代数闭包与通用平展覆盖塔在同一赋值处的分解群，正是本文的几何核心。

## 主要结果
定理 A（局部截面猜想）：对每个素数 \(p\)、每个有限扩张 \(k/\mathbb Q_p\)、每条亏格至少 2 的光滑正常几何连通曲线 \(X/k\)，映射
\[X(k)\longrightarrow\{\text{连续群同态截面 }s:G_k\to\pi_1(X)\}\big/\pi_1(X_{\bar k})\text{-共轭}\]
是双射。定理 B（完备化定理，几何核心）：设 \(K=k(X)\)，\(\widetilde K\subset K^{\rm sep}\) 为所有连通有限平展覆盖函数域的合成；对 \(K\) 上任一延拓归一化 \(p\) 进范数的实值 rank-one 范数及其到 \(K^{\rm sep}\) 的延拓，记 \(H=\widehat{\widetilde K}\subset E=\widehat{K^{\rm sep}}\)，则 \(K^{\rm sep}\subset H\)。整体推论：全局截面的定位像恰为有限覆盖下降轨迹 \(C(\mathbb A_K)_\bullet^{\mathrm{f\text{-}cov}}\)；当该轨迹等于 \(C(K)\) 时整体截面猜想成立，特别地对 \(\mathbb Q\) 上亏格至少 2 的模曲线（modular curve）\(X_0(N)\)、\(X_1(N)\) 成立，也适用于映射到 Mordell–Weil 群有限且 Tate–Shafarevich 群可除部分为零的 Abel 簇（abelian variety）的曲线。

## 证明思路
证明骨架：两阶段取根，赋值排除，Kummer 单射。

粘合引擎（第 3 节）：分歧覆盖在分枝点 \(b\) 处局部形如 \(t_b=z_c^{e_c}\)（用 \(p\) 进对数与指数开单位方根，无需 \(p\nmid e_c\)）。若另一覆盖在环形邻域 \(A_b\) 的整个逆像上给出 \(t_b\) 的 \(m_b\) 次解析根（\(m_b\) 为 \(b\) 上方分歧指数的公倍数），就把圆盘内部换成平凡覆盖、外部拉回粘合，经 proper GAGA 代数化得平展覆盖。关键在根须落在逆像每一页，否则无法平凡化整个覆盖。

第一阶段（第 4 节，tame 根）：固定奇素数 \(\ell\ne p\)。借助 ABBR 把度量复形 tame 覆盖实现为曲线覆盖的提升定理与 Mochizuki–Tsujimura 奇点消解，把节点环坐标的 \(\ell\) 次根安在有限平展覆盖上；粘合后，凡水平分歧指数整除 \(\ell\) 的有限 Galois 扩张，函数域都落入 \(H\)。

第二阶段（第 5 节，任意次根）：为处理被 \(p\) 整除的指数，取循环覆盖 \(y^\ell=T(T-1)/(T-\alpha)\)，其稳定骨架是两顶点 \(\ell\) 条平行边，节点环为 \(\{|\alpha|<|T|<1\}\)。其 Jacobi 完全退化（totally degenerate），有 Raynaud 式环面一致化（uniformization）\(q:\mathbb T^{\rm an}\to J^{\rm an}\)；由 Baker–Rabinoff 的热带 Abel–Jacobi 相容性，沿环得斜率 1 的特征 \(u_j=c'_jT(1+h_j)\)，且中段领圈上 \(|h_j|\) 很小。在 Jacobi 上作乘 \(m\) 拉回：除法引理（周期格无挠使提升粘合成整体）给出特征的 \(m\) 次根，剩余单位再用 \(p\) 进对数与指数开方（不要求 \(p\nmid m\)），故坐标 \(T\) 在整个逆环上有 \(m\) 次根。辅助覆盖自身水平指数仍整除 \(\ell\)，故已在 \(H\) 中；再一次粘合把任意有限 Galois 扩张实现于 \(H\)，得定理 B。

从完备化到截面（第 7 节）：定理 B 给出分解群同构 \(D_{w^{\rm sep}}(K^{\rm sep}/K)\cong D_{\widetilde w}(\widetilde K/K)\)。若该分解群到 \(G_k\) 有截面，则提升为 \(G_K\) 的截面；Koenigsmann 定理又把它放进有理点 \(a\) 的 \(\operatorname{ord}_a\) 分解群。固定域于是带两个不等价的 henselian rank-one 赋值——一个延拓 \(p\) 进赋值，一个在常数上平凡——与 F. K. Schmidt 唯一性矛盾（含 \(p=2\)）。满射性：Pop–Stix 定位把截面局部化到某赋值 \(w\)，超越不等式给 \(\operatorname{rank}w\le2\)。rank-one 已排除；rank-two 归结到 rank-one 粗化 \(u\)：非平凡于 \(k\) 者被排除，平凡者由本征性中心在闭点 \(a\) 且等价于 \(\operatorname{ord}_a\)（type-\(2h\)），满射到 \(G_k\) 又迫使 \(k(a)=k\)，截面即点截面。单射性：Abel–Jacobi 映射与乘 \(n\) torsor 的 Kummer 论证给出 \(i_a(b)\in\bigcap_n nJ(k)\)；而 \(J(k)\) 是紧 \(p\) 进解析群，含 \(\mathbb Z_p^{g[k:\mathbb Q_p]}\) 型开子群，交为零迫使 \(i_a(b)=0\)；\(a\ne b\) 会给出度 1 映射 \(X\to\mathbb P^1\)，与亏格至少 2 矛盾。

整体推论（第 8 节）：局部定理与实截面定理（Bresciani–Vistoli）给出到修正阿代尔集（modified adelic set）的定位映射；Harari–Stix 下降桥证定位像恰为有限覆盖下降轨迹。当 Stoll 判据保证该轨迹恰为有理点（\(X_0(N)\)、\(X_1(N)\)，或有限 Mordell–Weil 加零可除 Sha 的 Abel 目标）时，结合 Stix 有限支撑定理得整体双射；椭圆目标另引同族的 Selmer 逆定理。文中还证定位像含于线性下降集与 Brauer–Manin 集；数域不含 CM 子域时各有限处局部像有限（Betts–Stix）。

## 可信度与备注
本文主结果暂无形式化证明，请以社区核验为准。它是结果族 019 的主打论文：局部定理（定理 A）是全部整体推论的引擎，且大量步骤建立在外部文献（Koenigsmann、Pop–Stix、Stix、Stoll、Harari–Stix、ABBR、Mochizuki–Tsujimura 等）之上，可靠性亦系于这些引用。同族姊妹篇《Étale covers with a prescribed exterior sheet》发展了"外部完全分裂、圆盘上方 \(p\) 重"的覆盖构造，属同一工具箱，但本文正文未直接引用它；椭圆目标推论则依赖同发布族的 Selmer 逆定理。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
