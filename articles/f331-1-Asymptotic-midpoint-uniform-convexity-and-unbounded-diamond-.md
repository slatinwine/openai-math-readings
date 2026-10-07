---
layout: default
title: "Asymptotic midpoint uniform convexity and unbounded diamond distortion in a reflexive tree space"
family: "331"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Asymptotic midpoint uniform convexity and unbounded diamond distortion in a reflexive tree space

> 结果族 331：Reflexive midpoint convexity and diamond distortion　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

构造出可分自反 Banach 空间 \(X=J^*\)：其天然范数渐近中点一致凸（模 \(\ge\sqrt{1+t^2/12}-1\)），却无任何等价的渐近一致凸范数；深度 \(k\) 的可数分支菱形图嵌入 \(X\) 失真必 \(\ge\sqrt{1+k/12}\)，否定自反情形的菱形反问题。

## 问题背景

渐近凸性 (asymptotic convexity) 度量"扔掉有限多个方向后还剩多少凸性"。Dilworth–Kutzarova–Randrianarivony–Revalski–Zhivkov（2016）引入渐近中点一致凸性 (asymptotic midpoint uniform convexity, AMUC)，在 \(\ell_2\) 上造出 AMUC 而非 AUC 的范数，并问：AMUC 能否通过重赋范 (renorming) 得到渐近一致凸 (asymptotically uniformly convex, AUC) 的等价范数？Baudier（2026）用 Kadets–Werner 修正的 Bourgain–Rosenthal 空间给出否定回答，但该空间不自反。另一条线索是度量嵌入：Baudier 等（2017）证明 AMUC 范数排除可数分支菱形图 (countably branching diamonds) 的一致嵌入，并在"自反＋无条件渐近结构"假设下证明非 AUC 可重赋范反而蕴涵菱形一致嵌入。无条件结构这一假设能否去掉（Baudier–Lancien 书稿中记录的问题 39），正是本文要回答的：不能。

## 主要结果

取可数分支、高度有限但无界的树之森林 \(\mathcal F=\coprod_{h\ge1}(\{h\}\times\mathbb N^{\le h})\)，对有限支撑实函数用 James 的不相交线段平方和范数 \(\rho(u)=\sup(\sum_i u(S_i)^2)^{1/2}\)（上确界取遍两两不交线段 (segment) 的有限族），完备化得 \(J\)，令 \(X=J^*\)。主定理：\(X\) 无穷维、可分、自反 (reflexive)，且不容许任何等价 AUC 范数；其原始范数满足平均中点模 \(\widehat\delta_X(t)\ge\sqrt{1+t^2/12}-1\)，故为 AMUC；并且对每个整数 \(k\ge0\)，深度 \(k\) 的可数分支菱形 \(D_k\) 到 \(X\) 的任何嵌入的失真 (distortion) 至少为 \(\sqrt{1+k/12}\)。换言之：即便加上自反性，中点一致凸也不强迫菱形图有一致有界嵌入。

## 证明思路

论证分四步。先建坐标结构：高 \(h\) 的分量上是 Hilbert 型的（\(\|u\|_2\le\rho(u)\le\sqrt{h+1}\|u\|_2\)），故 \(J\) 是各分量的 \(\ell_2\) 直和，其对偶仍是 \(\ell_2\) 直和，两次运用即得 \(X\) 自反；对有限祖先集 (ancestral set) \(H\) 的坐标投影 \(P_H\) 是压缩的，而 \(H\) 之外的余部分按"门"（gate，即 \(H\) 外的极小顶点）分解为 \(\ell_2\) 直和。再证无 AUC 重赋范：沿根路径求和的泛函 \(p_v\) 范数恰为 1，其子增量 \(e^*_{v^\frown j}\) 是弱零 (weakly null) 的单位向量（因 \(X^*=J\) 而 \(J\) 中坐标平方可和）。假设某等价范数 \(N\) 的单侧渐近模在某半径为正，则借助有限维商空间逼近，可把有限余维子空间中的增益转移到某个真实子方向上，使范数沿路径每步至少乘以 \(1+\gamma/2\)；取足够高的树逐层迭代便突破范数的上界，矛盾——故每个等价范数的模在 \(\alpha/(2\beta)\) 处为零。第三步是核心的成对扩张引理：设 \(x=P_Hx\)、\(y=Q_Hy\)，先取头部与尾部各自近乎赋范的线段测试 \(f,k\)，朴素的 \(f\pm sk\) 会在跨越 \(H\) 边界的线段上产生失控的正交叉项；作者改为在首出口顶点（门）处添加同一个修正向量 \(c\)，其符号与过大的头部后缀和相反，使得修正后两个测试都满足 \(\rho^2\le1+12s^2\)，而两个端点的赋值取平均时 \(c\) 的贡献恰好相消，由此得 \((\|x+y\|+\|x-y\|)/2\ge\sqrt{\|x\|^2+\|y\|^2/12}\)，对参数 \(s\) 调优即得模下界。最后处理菱形：先由有限维紧性把无穷多个两两分离的近似中点配出一对投影任意接近者，其半差经交叉凸组合仍留在同一透镜 (lens) 中且尾部不小，代入成对引理得 \(R^2-\|x\|^2\ge\varepsilon^2/48\)；对每层定义斜率上确界 \(L_m\)，每次边替换至少损失 \(1/12\)，即 \(L_m^2\le L_{m+1}^2-1/12\)，逐层求和得 \(D^2\ge L_0^2+k/12\ge1+k/12\)。

## 可信度与备注

主结果已 Lean 形式化（家族文档 lean/docs/331.md）。本族三篇互相支撑：本文自成体系地给出 \(X\) 上常数 \(1/12\)；姊妹篇《Midpoint lenses in segment spaces》证明更一般的透镜尾估计并把结论推广到无穷高模型；《Distortion of countably branching diamonds…》用该尾估计把 \(X\) 上的下界改进为 \(\sqrt{1+k/4}\)。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，数值常数以论文陈述为准。

{% endraw %}
