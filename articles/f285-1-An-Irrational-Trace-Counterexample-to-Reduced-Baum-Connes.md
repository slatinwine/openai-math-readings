---
layout: default
title: "An irrational-trace counterexample to reduced Baum–Connes"
family: "285"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An irrational-trace counterexample to reduced Baum–Connes

> 结果族 285：Counterexamples to Baum–Connes and Kadison–Kaplansky　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造了一个有限生成群 \(G_{\mathrm{sur}}\)，其约化群 \(C^*\)-代数中含有典范迹为无理数的投影 \(b_0\)；由 Lück 迹定理，装配像中所有类的迹均为有理数，故 \([b_0]\) 落在装配映射的像之外——无系数约化 Baum–Connes 猜想对可数离散群被推翻（满射方向）。

## 问题背景

无系数约化 Baum–Connes 装配映射 \(\mu_j^G\colon K_j^G(\underline EG)\to K_j(C_r^*(G))\) 把真作用分类空间（classifying space for proper actions）\(\underline EG\) 的等变 \(K\)-同调送到约化群 \(C^*\)-代数的 \(K\)-理论；猜想断言其为同构。正结果覆盖顺群与双曲群，反例此前只有 Higson–Lafforgue–Skandalis 的带系数与 groupoid 版本。无理迹是天然的满射障碍：Lück 证明对任意可数离散群，\(\mu_0^G\) 像的迹全在 \(\mathbb Q\) 中。这条线索历史悠久：Atiyah 1976 年问及覆盖的 \(L^2\)-Betti 数可否无理，此后 Grigorchuk–Żuk 的灯群谱计算、Dicks–Schick、Austin 的无理核维数、Pichot–Schick–Żuk 的超越值相继推进；但 Grabowski 在顺群灯群上的超越核维数投影只活在 von Neumann 代数中——顺群满足 Baum–Connes，按 Lück 定理它们根本进不了 \(C^*\)-代数。要让投影真正落入 \(C_r^*\)，需要一致谱隙使 \(\mathbf 1_{\{0\}}\) 在谱上连续（Li–Nowak–Pooya 机制），本文首次实现了这一点。

## 主要结果

**定理**：存在有限生成离散群 \(G_{\mathrm{sur}}\) 与投影 \(b_0\in C_r^*(G_{\mathrm{sur}})\)，使 \(\tau_{G_{\mathrm{sur}}}(b_0)=\sum_{i\ge1}p^{-k_i}\notin\mathbb Q\) 为无理数，且
\[[b_0]\notin\mu_0^{G_{\mathrm{sur}}}\bigl(K_0^{G_{\mathrm{sur}}}(\underline EG_{\mathrm{sur}})\bigr).\]
特别地，无系数约化 Baum–Connes 猜想对可数离散群不成立，且障碍经有理化后仍然存在。该群是灯群型半直积 \(G_{\mathrm{sur}}=V\rtimes\Gamma\)，其中灯模 \(V\) 是有限域 \(\mathbb F_p\) 上的向量空间，群因而含挠——与族内两篇无挠姊妹篇恰成分工：本篇主满射失效，另两篇分别主单射失效与投影猜想。

## 证明思路

群取半直积 \(G_{\mathrm{sur}}=V\rtimes\Gamma\)：\(\Gamma\) 由标记扩张子（labelled expanders，Gromov–Osajda 图形关系子）生成；\(V=\mathbb F_p^{(\Gamma)}/W_0\) 是灯模，其关系子空间 \(W_0\) 由所有平移 copy 上的对偶码字张成。先以 Osajda 标记定理取有限 \(d\)-正则大围长扩张子 \(\Theta_i\) 等距嵌入 \(\Gamma\) 的 Cayley 图，再把每个 copy 锥化得到一致双曲图；关键的"同时相交估计"表明：相对任意根，一个 copy 与所有中心不更远的 copy 的交整体落入一个小内蕴树球。Gilbert–Varshamov 式计数给出 \(\mathbb F_p\) 上既含指定模式 \(w_i\)、本原与对偶距离又都超过 \(\eta n_i\) 的码 \(C_i\)；由此 \(V\) 的紧对偶 \(\Omega\) 上每个 copy 的模式分布恰是 \(C_P\) 上的均匀分布——匹配概率精确等于 \(p^{-k_i}\)，且不同 copy 间无需任何独立性。

算子取 \(T=dI-\sum_s f_su_sf_{s^{-1}}\in C_r^*(G_{\mathrm{sur}})\cong C(\Omega)\rtimes_r\Gamma\)，其中 \(f_s\) 是由坐标值决定"允许标签"的 clopen 投影。在每个赋值点 \(\omega\)，\(\pi_\omega(T)=dI-\Adj(G_\omega)\) 是"启用图"的图拉普拉斯算子：模式匹配的 valid copy 成为孤立的扩张子连通分支，其上核恰为常数函数；真正的难点是其余无穷部分上的一致谱隙。论文用圈秩（cycle rank）记账：Euler 恒等式 \(|E|=|Y|-\#\pi_0+b_1\) 把谱亏缺化为圈维数上界，逐 copy 消去圈坐标并对两两不交的外顶点集收费，大围长保证外部附着点彼此远离；由此得一致亏缺 \(d|Y|-2|E(A)|\ge(c/2)|Y|\)，再经水平集积分与 Cauchy–Schwarz 得 \(T\ge(c^2/8d)I\)。于是谱含于 \(\{0\}\cup[\varepsilon,2d]\)，连续泛函演算给出真投影 \(b_0=\chi(T)\)。最后计算迹：恒等元落在某个 valid copy 时对角元为 \(1/n_i\)，恰有 \(n_i\) 个该类 copy 含恒等元且诸事件互斥，故 \(\tau(b_0)=\sum_ip^{-k_i}\)；其 base-\(p\) 展开的数字恰在位置 \(k_1<k_2<\cdots\) 为 \(1\)，而间距趋于无穷，不可能最终周期，从而无理。

## 可信度与备注

本文暂无形式化证明；谱隙、码分布与图几何互相咬合，核验成本高。族内姊妹篇从单射方向与投影猜想方向补全装配失效的整体图景。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
