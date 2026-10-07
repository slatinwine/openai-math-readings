---
layout: default
title: "A counterexample to the coarse Novikov conjecture"
family: "307"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to the coarse Novikov conjecture

> 结果族 307：Failure of rational injectivity for maximal coarse assembly　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造有界几何的有限图粗不交并，并造出一度粗 K-同调中的无限阶类，其在约化 Roe 代数 K-理论中的装配像为零——通常粗装配映射整性与有理均不单射，有理粗 Novikov 猜想被推翻。

## 问题背景

非紧空间的大尺度几何通过粗指标理论与算子 K-理论相连。对一致离散、有界几何（bounded geometry）的 `@@M@@X@@`，粗 K-同调（coarse K-homology）`@@M@@KX_i(X)=\varinjlim_r K_i^{\lf}(P_r(X))@@` 由 Rips 复形（Rips complex）沿尺度的直极限（direct limit）定义；装配映射（assembly map）`@@M@@\mu_X@@` 把几何类送到约化 Roe 代数（reduced Roe algebra）`@@M@@C^*(X)@@`——有限传播、局部紧算子代数的算子范数闭包——的 K-理论。Higson–Roe 的粗 Baum–Connes 猜想（coarse Baum–Connes conjecture）预测 `@@M@@\mu_X@@` 是同构，其有理单射性即粗 Novikov 断言。难点在于必须穿过所有 Rips 尺度：某个尺度下的循环可在更大尺度充当边缘而只在直极限中代表零，因此反例类须在每次粗化下存活且指标为零。此前 Yu 证明了有限渐近维数与希尔伯特粗嵌入情形的同构，Skandalis–Tu–Yu 给出群胚框架，后续又推广到一致凸 Banach 空间与纤维化粗嵌入。反例方面，Yu 与 Dranishnikov–Ferry–Weinberger 的构造或无有界几何，或类在粗化下死亡；Higson–Lafforgue–Skandalis 的反例针对群装配与不满射；Willett–Yu 还证明围长趋于无穷的图并上装配单射。有界几何本身是否足够？本文给出否定回答。

## 主要结果

主定理：存在一致离散、有界几何的度量空间 `@@M@@X@@`——连通有限图的一致有界度粗不交并（coarse disjoint union）——与无限阶类 `@@M@@\alpha\in KX_1(X)@@`，使得
`@@M@@D\mu_X(\alpha)=0\in K_1(C^*(X)).@@`
因此 `@@M@@X@@` 上的通常粗装配映射整不单射，且在定义域与目标同时有理化后仍不单射。构造概要：取三角格点半径 `@@M@@j@@` 的圆盘 `@@M@@D_j@@`，边界圈 `@@M@@C_j@@` 长 `@@M@@6j@@`；顶点深度为 `@@M@@k_j(u)=j-\rho(u)@@`，深度 `@@M@@k@@` 处的纤维是同余商（congruence quotient）`@@M@@Q_k=\SL_3(\Z/2^k\Z)@@`，边界纤维平凡。纤维内为左 Cayley 边；相邻纤维之间按与固定射线的带号相交数 `@@M@@a(u,v)@@` 右乘扭转元 `@@M@@g_k^{a(u,v)}@@` 匹配，其中 `@@M@@g_k=\operatorname{diag}(t,t^{-1},1)\bmod 2^k@@`，`@@M@@t@@` 是超越于 `@@M@@\Q@@` 的 2-adic 单位。边界圈经 `@@M@@u\mapsto(u,1)@@` 嵌入 `@@M@@X_j@@`，其定向类族定义 `@@M@@\alpha\in KX_1(X)@@`。

## 证明思路

证明是"持久绕圈"与"指标消没"两条独立线索的汇合。先证 `@@M@@\alpha@@` 无限阶：小圈引理（small-loop lemma）断言，对每个长度界 `@@M@@A@@`，当 `@@M@@j@@` 充分大时 `@@M@@X_j@@` 中长度 `@@M@@\le A@@` 的闭路的电荷（charge，即投影步与射线带号相交数之和）为零。若某投影点离中心过远，取在其上达到 `@@M@@\rho@@` 的线性泛函，则整条闭路的投影落入开半平面，在其中可缩、环绕数为零，与非零电荷矛盾；故闭路位于深部。把纤维坐标约化到沿途最低深度的商 `@@M@@Q_\ell@@`，闭路给出 `@@M@@wzg_\ell^m=z@@`，即 `@@M@@g_\ell^m@@` 与短字 `@@M@@w^{-1}@@` 共轭、迹相等，而 `@@M@@t@@` 的超越性保证 `@@M@@\tr(g_\ell^m)\ne\tr(w)\pmod{2^\ell}@@`，矛盾。于是在每个尺度 `@@M@@r@@`，取充分靠后的分量 `@@M@@P_r(X_j)@@`：小圈引理使电荷成为良定义的整 1-上闭链（cocycle），边界圈上配出环绕数 1，经映射到 `@@M@@S^1@@` 得指标配对 `@@M@@\lambda_r(\alpha_r)=1@@`；任何非零整数倍因此在直极限中非零，`@@M@@\alpha@@` 无限阶、有理化后仍非零。再证指标为零：填满的圆盘可缩，`@@M@@K_1^{\lf}(W)=0@@`，边界类在 `@@M@@KX_1(D)@@` 中已经死亡，剩下的只是把 `@@M@@C^*(D)@@` 的指标移入 `@@M@@C^*(X)@@`。这里用转移判据（transfer criterion）：若各纤维常数向量上的投影可由有限传播压缩一致逼近，且近距纤维之间存在携带常向量的受控压缩，则平均等距 `@@M@@V:\delta_u\mapsto\xi_u@@` 的共轭 `@@M@@\Ad V@@` 是 Roe 代数间的 `@@M@@*@@`-同态。Kazhdan 性质 T（property (T)）恰好提供第一条：谱隙 `@@M@@\delta=\kappa^2/(2|S|)@@` 使惰性平均幂 `@@M@@(1-L_k/2)^n@@` 对所有纤维一致收敛到常数投影且传播 `@@M@@\le n@@`；图的边关系提供第二条。`@@M@@V@@` 不覆盖任何粗映射——纤维直径无界——但同态仍然成立。最后，边界纤维是单点，故在边界上 `@@M@@VE=I@@` 精确成立，`@@M@@\Phi\circ e_{\mathrm{Roe}}=i_{\mathrm{Roe}}@@`；装配的自然性接通链条：`@@M@@\mu_X(\alpha)=\Phi_*\mu_D(e_*\beta)=0@@`。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。同族姊妹篇把同一构造思想加强到极大 Roe 代数（结果族 307 的极大版反例）；论文还引用一篇独立姊妹工作，对无挠群的群装配给出有理不单射的反例。本文与 Willett–Yu 的大围长单射定理并不冲突：这里的纤维含短圈，大围长假设不成立。个别谱隙估计与迹分离引理的技术细节技术性较强，此处从略。

{% endraw %}
