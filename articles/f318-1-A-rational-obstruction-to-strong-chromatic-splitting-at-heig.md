---
layout: default
title: "A rational obstruction to strong chromatic splitting at height three"
family: "318"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A rational obstruction to strong chromatic splitting at height three

> 结果族 318：Chromatic splitting: filtrations and counterexamples　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明对所有素数 \(p\geq5\)，典范映射 \(L_0L_{K(3)}S\to L_0L_{K(2)}L_{K(3)}S\) 在 \(\pi_{-3}\) 上非零，据此推翻高度三的强色谱分裂公式——把反例从 \(p=2\) 推进到一切奇素数 \(p\geq5\)，连不指定和项映射的底层谱等价都不存在。

## 问题背景

色谱分裂猜想（Hopkins 提出、Hovey 记录、Barthel–Beaudry 修订）在高度三预言：重叠 \(L_2L_{K(3)}S\) 等价于楔和 \(\mathcal W_3=L_2(S_p^\wedge\vee\Sigma^{-1}S_p^\wedge)\vee L_1(\Sigma^{-3}S_p^\wedge\vee\Sigma^{-4}S_p^\wedge)\vee L_0(\Sigma^{-5},\Sigma^{-6},\Sigma^{-8},\Sigma^{-9}S_p^\wedge)\)。此前图景：高度一成立；高度二在 \(p\gt3\) 由 Hopkins 依 Shimomura–Yabe 得到、\(p=3\) 由 Goerss–Henn–Mahowald 证明、\(p=2\) 被 Beaudry 推翻（后有 Beaudry–Goerss–Henn 修正版）。高度三悬置。一个表面困难是：BSSW 已算出 \(K(n)\)-局部球面的有理同伦是外代数，高度三的次数 \(0,-1,-3,-4,-5,-6,-8,-9\) 恰好就是 \(\mathcal W_3\) 中的位移，所以维数层面分不出真假。论文找到一条能区分它们的自然变换：由 \(K(2)\)-局部化单位诱导的典范映射 \(\tau_X:L_0X\to L_0L_{K(2)}X\)，并证明它在实际对象上非零、在预言的楔和上必为零。

## 主要结果

主定理：对每个素数 \(p\geq5\)，典范映射 \(\tau_{L_{K(3)}S}:L_0L_{K(3)}S\to L_0L_{K(2)}L_{K(3)}S\) 在 \(\pi_{-3}\) 上非零。推论：不存在 \(E(2)\)-局部谱的等价 \(L_2L_{K(3)}S\simeq\mathcal W_3\)，故高度三强分裂公式在此范围为假——无论是否要求和项映射与指定单位相容。理由是一个形式论证（楔和障碍引理）：若 \(Z\simeq A\vee B\)、\(L_{K(2)}B=0\) 且 \(\pi_dL_0A=0\)，则 \(\pi_d(\tau_Z)=0\)。在 \(\mathcal W_3\) 中取 \(A\) 为前两个高位块：\(\pi_{-3}L_0A=0\)；其余块由 Bousfield 类论证是 \(K(2)\)-无环的。再由 \(T=L_{K(3)}S\to L_2T\) 的余纤维同时有理与 \(K(2)\)-无环，自然性方块中的竖直映射都是等价，任何假设的等价都会强迫 \(\tau_T\) 在 \(\pi_{-3}\) 上为零，与主定理矛盾。论证全程不对假设等价在各和项上的行为做任何规定。

## 证明思路

证明要完成两件事：造一个从 \(L_{K(3)}S\) 到普通 \(K(2)\)-局部谱的映射，并证明它保持某个非零的有理 \(-3\) 次类；局部性届时自动使该映射穿过典范局部化单位分解。检测谱（detector）的构造：在高度三形变空间的高度恰为二的层 \(k((u_2))\) 上，Gross–Torii 扩张把连通高度二形式群等同于 Honda 群，其赋值域完备化 \(\widehat L\) 带有 \(G=P_3\times P_2\)（两个稳定子群之积）的作用；用 Barthel–Mann–Ray–Schlank–Senger–Weinstein–Zhou 的 solid Lubin–Tate 理论得完备理论 \(\widehat B^\square\)，取不动点再求值得 \(\mathcal D\)，它是 \(K(2)\)-局部的。由两个等变映射 \(E_3^\square\to\widehat B^\square\leftarrow E_2^\square\) 得 \(g:L_{K(3)}S\to\mathcal D\)，且 \(g=\bar g\eta\)，\(\eta\) 为典范单位。类这边，起点是次数三的上同调类 \(e_{P_n}\in H^3_{\mathrm{cts}}(P_n,\Qp)\)：经有理 Lie 比较，它由不变双型的经典上闭链 \((U,V,W)\mapsto\mathrm{tr}_{\mathrm{red}}(U[V,W])\) 代表。比较除环类与线性群的类用的是秩 \(n\)、次数一的 Fargues–Fontaine 丛 \(\mathcal O(1/n)\) 的线修改（line modification）模叠 \(\mathcal M_n\simeq[\mathbb P^{n-1,\diamondsuit}/P_n]\simeq[\Omega_C^{n-1,\diamondsuit}/J_n]\)（Faltings 的 Lubin–Tate/Drinfeld 对偶，Scholze–Weinstein 周期映射与 Fargues–Scholze 的旋子）：投影丛公式在 \(H^3_{\mathrm b}(\mathcal M_n)\) 中孤立出一条 Galois 不变直线，含 \(e_{P_n}\) 的像；再用 Colmez–Dospinescu–Nizioł 的整 Drinfeld 上同调定理与 Galois 权重证明线性类 \(e_{J_n}\) 的像落在同一直线上，故两者成比例。完备塔上有秩三到秩二的丛满射，配一次公共线修改得到秩 \(1,3,2\) 的有理局部系统正合列，抛物限制给出 \(e_{P_3}|_{Y_C}=a\,e_{P_2}|_{Y_C}\)（\(a\in\Qp^\times\)）。非零性先经 Witt 系数反射与 BSSW 的连续加性收缩证明 \(c_3=a\,c_2\neq0\) 于 \(H^3(G,\pi_0\widehat B^\square)[1/p]\)。最后在检测步：对 \(g\) 用下降谱序列，有限上同调界给出每个同伦次数的有限整滤过；倒转 \(p\) 后中心纯量自同构杀死一切非零系数次 \(t\)，于是双次数 \((s,t)=(3,0)\) 的非零类存活到普通同伦的 \(-3\) 次，主定理得证。整条链上先取整上同调、后倒转 \(p\) 的顺序对所涉非紧群与空间是关键的。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准。它在结果族中扮演"反例引擎"：高度三显式滤过篇正是引用本文定理作为其"典范映射定理"，才证得首条高度一黏合映射非零；与两篇滤过存在性论文合看，图景完整——强楔和分裂在高度三、\(p\geq5\) 失败，但碎片清单仍以带非平凡黏合的有序滤过实现。按 OpenAI 官方声明，未经形式化的结果可能有问题，阅读时宜保持审慎。

{% endraw %}
