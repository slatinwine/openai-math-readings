---
layout: default
title: "Midpoint lenses in segment spaces"
family: "331"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Midpoint lenses in segment spaces

> 结果族 331：Reflexive midpoint convexity and diamond distortion　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

对有限高线段森林对偶 \(X=J^*\) 与无穷高坐标预对偶 \(B_\infty\) 两个 James 树型空间，证明对称透镜中任意位移的尾部满足 \(\|Q_Hy\|\le2\sqrt{R^2-\|x\|^2}\)；两个范数均渐近中点一致凸，却都无等价渐近一致凸范数。

## 问题背景

对范数空间 \(Y\)、向量 \(x\) 与半径 \(R\)，对称透镜 (symmetric lens) \(\mathcal L(x,R)=\{y:\|x+y\|\le R,\ \|x-y\|\le R\}\) 收集以 \(x\) 为中点、两端点都在 \(R\)-球内的一切偏差。当 \(\|x\|\) 接近 \(R\) 时凸性会压缩透镜；在无穷维空间里可以问：投影掉有限多个坐标后透镜还剩多大。Dilworth–Kutzarova–Randrianarivony–Revalski–Zhivkov（2016）正是用近似中点透镜的非紧性刻画渐近中点一致凸性 (asymptotic midpoint uniform convexity, AMUC)。Perreau（2021）进一步提问：可数分支 James 树空间的典则预对偶是否 AMUC？本文研究两个模型——高度有限但无界的树森林在线段范数下的对偶 \(X=J^*\)（自反）与无穷树 \(T_\infty=\mathbb N^{<\omega}\) 上的闭坐标张成 \(B_\infty\subset J_\infty^*\)（Ghoussoub–Maurey–Schachermayer 式坐标预对偶）——并对两者证明统一的尾部估计。作为对照，Girardi 曾证明经典二元 James 树空间的预对偶与全对偶都是 AUC 的；本文改用可数分支与有限而无界的分量高度，呈现出截然不同的行为，且局部相消估计均为本文就所给范数直接证明，而非从二元树结果移植。

## 主要结果

主定理（联合预算）：设 \(Y\) 为 \(X=J^*\) 或 \(B_\infty\) 之一，\(H\) 为有限祖先集 (ancestral set)，\(x=P_Hx\)，且 \(\|x\pm y\|\le R\)，则
\[\|Q_Hy\|\le2\sqrt{R^2-\|x\|^2}.\]
关键是同一个头部 \(H\) 控制透镜中的一切位移——这正是单个中心拥有无穷多个可能中点时所需要的性质。推论由此给出两个模型的显式平均渐近中点模，故两个给定范数都 AMUC；同时两个空间都无可重赋范 (renormable) 的等价 AUC（渐近一致凸, asymptotically uniformly convex）范数；且有限高森林对偶 \(X\) 自反。

## 证明思路

先建原子表示：有限头部 \(P_HB_\infty\) 的单位球恰是"表示原子"\(\sum_i a_id_{S_i}\)（\(d_S\) 为不相交线段 (segment) 上的示性泛函、\(\sum_i a_i^2\le1\)）的凸包，Carathéodory 定理保证至多 \(|H|+1\) 个原子的有限表示；\(H\) 之外则按门 (gate) 分解为 \(\ell_2\) 直和。证明核心是联合预算论证：把两个端点 \(x\pm y\) 表示为原子的凸组合，再以等概率随机符号 \(\sigma\) 混合成一个随机原子 \(A\)，使 \(\mathbb EA=x\)、\(\mathbb E(\sigma A)=y\)；然后用近乎赋范头部的测试 \(p\)（\(x(p)=r=\|x\|\)）预测每个原子系数，即把 \(a_i\) 换成 \(b_i=rp(S_i)\)。这一替换产生两笔非负误差：系数误差 \(V=\sum_i(a_i-b_i)^2\) 与未用尽的头部测试能量 \(L=r^2-\sum_ib_i^2\)，而二者期望之和恰好被平方半径亏损控制：\(\mathbb EV+\mathbb EL\le R^2-r^2\)。真正的难点在相消：两个原子若从头部同一顶点离开且带相反符号的和，则它们的头线段必然嵌套，把较长者切开会增大其平方线段测试，于是反号乘积被测试"未满一"的差额吸收；由此得到门口质量估计 \(\|m\|_2\le\sqrt{\eta+2\theta}\)（其中 \(m(g)=\mathbb E|b(g)|\)，\(\eta=\mathbb EV\)、\(\theta=\mathbb EL\)）。最后每个锥上的项范数不超过 \(m(g)\)，锥的 \(\ell_2\) 分解给出 \(\|Q_Hy\|\le\sqrt\eta+\sqrt{\eta+2\theta}\le2\sqrt{R^2-r^2}\)。至于 AUC 障碍，则利用空间的另一特征：根路径泛函 \(d_{[o,v]}\) 范数为 1，而子增量 \(e^*_{v^\frown n}\) 是弱零 (weakly null) 单位向量；正的单侧渐近模会迫使范数沿路径几何式增长，与路径范数的一致有界矛盾。无穷树上还有不需要迭代的版本：取全体路径范数的上确界 \(M\)，同样的增益论证给出 \(M\ge(1+\gamma)M\)，自相矛盾。

## 可信度与备注

主结果已 Lean 形式化。本篇是族内枢纽：其尾估计正是姊妹篇《Distortion of countably branching diamonds…》推出 \(D^2\ge1+k/4\) 的直接输入；另一姊妹篇（自反树空间）在 \(X\) 上用自身的成对引理得常数 \(1/12\)，本篇的联合预算机制更强。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，具体常数以论文陈述为准。

{% endraw %}
