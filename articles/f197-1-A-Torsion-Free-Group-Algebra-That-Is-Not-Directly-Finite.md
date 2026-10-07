---
layout: default
title: "A Torsion-Free Group Algebra That Is Not Directly Finite"
family: "197"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Torsion-Free Group Algebra That Is Not Directly Finite

> 结果族 197：A torsion-free group algebra that is not directly finite　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

构造出有限展示（finitely presented）且无挠（torsion-free）的群 \(G\)：在 \(\mathbb F_2[G]\) 中有 \(ab=1\) 而 \(ba\ne1\)，并附见证元 \(c\) 使 \(ac=0\)、\(c\ne0\)。这把 Kaplansky 直接有限性猜想的反例推进到无挠群，同时给出一个非 sofic 群。

## 问题背景

Kaplansky 在 1972 年提出直接有限性（direct finiteness）问题：群代数 \(K[G]\) 中 \(ab=1\) 是否必推出 \(ba=1\)？特征零情形由算子代数迹论证肯定；正特征下，Ara–O'Meara–Perera 对 free-by-amenable 群、Elek–Szabó 对 sofic 群给出肯定答案，因此反例群必非 sofic。同族此前的工作已在某特征二有限域上造出反例，但群含奇阶挠元。能否去掉挠、并直接用素域 \(\mathbb F_2\)？本文给出肯定回答，且所得群拥有有限二维分类复形（classifying complex）——几何上极其温顺的对象，反例却藏身其中。

## 主要结果

定理：存在有限展示的无挠群 \(G\) 及元素 \(a,b,c\in\mathbb F_2[G]\)，使得

\[ab=1,\qquad ac=0,\qquad c\ne0 .\]

于是 \(ba\ne1\)：若 \(ba=1\)，则 \(c=(ba)c=b(ac)=0\)，与 \(c\ne0\) 矛盾。元素 \(c\) 正是反向乘积失效的显式证书。附带结论：\(G\) 有限展示、万有覆叠可缩、维数至多为二，且由 Elek–Szabó 定理知 \(G\) 非 sofic。

## 证明思路

全文分代数、概率、拓扑三层，以"标记图＋锥"为骨架。

代数核心是一条奇偶判据。取两幅浸入（immersion）同一玫瑰 \(F\) 的有限无环图 \(\Gamma_A,\Gamma_B\)，把每个连通分量的抽象锥（cone）沿标记映射粘到 \(F\) 上得到二维复形 \(X\)，令 \(G=\pi_1(X)\)。锥把分量内一切闭路杀死，于是从根到顶点 \(x\) 的路标号给出完全确定的群元 \(g_x\)。令 \(a=\sum g_x\)、\(b=\sum g_x^{-1}\)、\(c=\sum h_y^{-1}\)。展开 \(ab\) 时考察同步步图（simultaneous-step graph）：顶点对 \((x,x')\) 沿公共出标签同步前进一步，而贡献的群元 \(g_xg_{x'}^{-1}\) 在此步下不变，每个顶点对的度数恰为出标签集之交的大小 \(|S_x\cap S_{x'}|\)。若除根 \((x_A,x_A)\) 外所有交均为奇数、且 \(|S_{x_A}|\) 为偶数，则由握手引理（奇度顶点必成偶数个），不含根的分量各含偶数个顶点，贡献在 \(\mathbb F_2\) 中整体相消；唯含根的分量留下常数贡献 \(1\)，得 \(ab=1\)。同理，\(A\times B\) 的一切交均为奇数，给出 \(ac=0\)。

标签设计取材于有限几何：用 \(q=128\) 的射影平面（\(v=q^2+q+1=16513\) 条线）作普通标签，顶点按线分类；再添七个附加字母，按 Fano 平面七条线的补集（四元集、两两交二元）均匀分发，使除根外一切交集为奇数，而根的标签数 \(129+7=136\) 为偶。边由随机匹配（random matching）选取并条件化在围长（girth）\(\ge L\) 上，交换论证与集合扩张估计保证分量直径为对数级。

拓扑层把随机图变成"好群"。若图中不存在简化球面排布（reduced spherical arrangement），则锥复形非球面（aspherical）且根受保护：从根出发到别的顶点的路标号在 \(G\) 中非平凡。证明用极小反例加带状手术（band surgery）：若某配对弧连接同一条图边的两次穿越，手术可把边界总长缩短二，与极小性矛盾。二维且 \(\pi_2(X)=0\) 推出万有覆叠可缩，进而 \(G\) 无挠（否则与循环群的周期自由消解的上同调相矛盾）。概率侧的收口是：先用加权计数排除"未配对比例很小"的有界路系统，再用 Lipton–Tarjan 平面分隔子递归地从任何球面排布中提取一个此类系统；参数依序选取，使一个局部计数估计即可排除全部排布。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。同族姊妹篇（特征二、带挠版本）主结果已形式化，是本族的存在性枢纽；本文则发展同族"无挠零因子"一文的图与锥方法，把结论强化到素域 \(\mathbb F_2\) 与无挠群。按 OpenAI 官方声明，未经形式化的结果可能有问题，故阅读时应以社区核验为准。

{% endraw %}
