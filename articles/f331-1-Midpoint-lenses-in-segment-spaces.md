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

## 入门导读 🐣

两枚同样大的硬币交叠，公共部分是一枚"透镜"。在无穷维空间里，透镜收集的是所有"以 `@@M@@x@@` 为中点、两端都不越出半径 `@@M@@R@@`"的位移。这篇论文对两棵无穷大的家谱树造出的空间证明了一条干净的几何事实：中心 `@@M@@x@@` 越贴近球面，透镜在扔掉任意有限多个坐标之后剩下的"尾巴"就越薄，按平方根的速度收缩。这条尾巴不等式是整个结果族的发动机。

**关键词卡片**

- 对称透镜（symmetric lens）：`@@M@@\{y:\|x+y\|\le R,\ \|x-y\|\le R\}@@`，两个球相交的公共部分。
- 尾部估计（tail estimate）：投影掉有限头部坐标 `@@M@@H@@` 后，剩余部分 `@@M@@Q_Hy@@` 的大小上界。
- 线段范数（segment norm）：用两两不相交线段上取值的平方和定义长度，James 树空间的刻度。
- 渐近中点一致凸（AMUC）：透镜随中心贴近球面而（渐近地）变薄，即中点版圆度。
- 渐近一致凸（AUC）：更强的单向圆度；本文两个空间都换不出等价的 AUC 范数。

**看个具体例子**

主不等式 `@@M@@\|Q_Hy\|\le2\sqrt{R^2-\|x\|^2}@@`，取 `@@M@@R=1@@` 代入具体数字：`@@M@@\|x\|=0.8@@` 时尾部 `@@M@@\le2\sqrt{0.36}=1.2@@`；`@@M@@\|x\|=0.99@@` 时尾部 `@@M@@\le2\sqrt{1-0.9801}\approx0.28@@`；`@@M@@\|x\|\to1@@` 时尾部趋于 `@@M@@0@@`。中心只差百分之一贴到球面，尾巴就被压掉四分之三以上——无论位移 `@@M@@y@@` 怎么选、扔掉的坐标集 `@@M@@H@@` 怎么选都成立。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="28" font-size="15" fill="#222">对称透镜：中心 x 越贴近球面，远处越薄</text>
  <circle cx="200" cy="150" r="95" fill="none" stroke="#2f5fd0" stroke-width="2"/>
  <circle cx="310" cy="150" r="95" fill="none" stroke="#2f5fd0" stroke-width="2"/>
  <path d="M 200 55 A 95 95 0 0 1 200 245 A 95 95 0 0 1 200 55" fill="#dce8fb" fill-opacity="0.8"/>
  <circle cx="255" cy="150" r="5" fill="#d64545"/>
  <text x="262" y="143" font-size="14" fill="#d64545">中点 x</text>
  <line x1="255" y1="150" x2="255" y2="62" stroke="#d64545" stroke-width="1.5" stroke-dasharray="5 4"/>
  <line x1="255" y1="150" x2="255" y2="238" stroke="#d64545" stroke-width="1.5" stroke-dasharray="5 4"/>
  <text x="130" y="55" font-size="13" fill="#2f5fd0">半径 R 的球</text>
  <text x="360" y="55" font-size="13" fill="#2f5fd0">半径 R 的球</text>
  <text x="340" y="255" font-size="14" fill="#222">透镜 = 两球公共部分</text>
  <text x="20" y="200" font-size="13" fill="#666">尾部 ≤ 2√(R²−‖x‖²)</text>
  <text x="20" y="222" font-size="13" fill="#666">R=1，‖x‖=0.99：</text>
  <text x="20" y="244" font-size="13" fill="#666">尾部 ≤ 0.28</text>
</svg>

</div>

**为什么值得关心**

这条尾部不等式正是姊妹篇把菱形失真下界改进到 `@@M@@\sqrt{1+k/4}@@` 的直接输入；AMUC 与 AUC 的分界线又被精确地画深了一笔。

> 主结果已 Lean 形式化

## 一句话结论

对有限高线段森林对偶 `@@M@@X=J^*@@` 与无穷高坐标预对偶 `@@M@@B_\infty@@` 两个 James 树型空间，证明对称透镜中任意位移的尾部满足 `@@M@@\|Q_Hy\|\le2\sqrt{R^2-\|x\|^2}@@`；两个范数均渐近中点一致凸，却都无等价渐近一致凸范数。

## 问题背景

对范数空间 `@@M@@Y@@`、向量 `@@M@@x@@` 与半径 `@@M@@R@@`，对称透镜 (symmetric lens) `@@M@@\mathcal L(x,R)=\{y:\|x+y\|\le R,\ \|x-y\|\le R\}@@` 收集以 `@@M@@x@@` 为中点、两端点都在 `@@M@@R@@`-球内的一切偏差。当 `@@M@@\|x\|@@` 接近 `@@M@@R@@` 时凸性会压缩透镜；在无穷维空间里可以问：投影掉有限多个坐标后透镜还剩多大。Dilworth–Kutzarova–Randrianarivony–Revalski–Zhivkov（2016）正是用近似中点透镜的非紧性刻画渐近中点一致凸性 (asymptotic midpoint uniform convexity, AMUC)。Perreau（2021）进一步提问：可数分支 James 树空间的典则预对偶是否 AMUC？本文研究两个模型——高度有限但无界的树森林在线段范数下的对偶 `@@M@@X=J^*@@`（自反）与无穷树 `@@M@@T_\infty=\mathbb N^{<\omega}@@` 上的闭坐标张成 `@@M@@B_\infty\subset J_\infty^*@@`（Ghoussoub–Maurey–Schachermayer 式坐标预对偶）——并对两者证明统一的尾部估计。作为对照，Girardi 曾证明经典二元 James 树空间的预对偶与全对偶都是 AUC 的；本文改用可数分支与有限而无界的分量高度，呈现出截然不同的行为，且局部相消估计均为本文就所给范数直接证明，而非从二元树结果移植。

## 主要结果

主定理（联合预算）：设 `@@M@@Y@@` 为 `@@M@@X=J^*@@` 或 `@@M@@B_\infty@@` 之一，`@@M@@H@@` 为有限祖先集 (ancestral set)，`@@M@@x=P_Hx@@`，且 `@@M@@\|x\pm y\|\le R@@`，则
`@@M@@D\|Q_Hy\|\le2\sqrt{R^2-\|x\|^2}.@@`
关键是同一个头部 `@@M@@H@@` 控制透镜中的一切位移——这正是单个中心拥有无穷多个可能中点时所需要的性质。推论由此给出两个模型的显式平均渐近中点模，故两个给定范数都 AMUC；同时两个空间都无可重赋范 (renormable) 的等价 AUC（渐近一致凸, asymptotically uniformly convex）范数；且有限高森林对偶 `@@M@@X@@` 自反。

## 证明思路

先建原子表示：有限头部 `@@M@@P_HB_\infty@@` 的单位球恰是"表示原子"`@@M@@\sum_i a_id_{S_i}@@`（`@@M@@d_S@@` 为不相交线段 (segment) 上的示性泛函、`@@M@@\sum_i a_i^2\le1@@`）的凸包，Carathéodory 定理保证至多 `@@M@@|H|+1@@` 个原子的有限表示；`@@M@@H@@` 之外则按门 (gate) 分解为 `@@M@@\ell_2@@` 直和。证明核心是联合预算论证：把两个端点 `@@M@@x\pm y@@` 表示为原子的凸组合，再以等概率随机符号 `@@M@@\sigma@@` 混合成一个随机原子 `@@M@@A@@`，使 `@@M@@\mathbb EA=x@@`、`@@M@@\mathbb E(\sigma A)=y@@`；然后用近乎赋范头部的测试 `@@M@@p@@`（`@@M@@x(p)=r=\|x\|@@`）预测每个原子系数，即把 `@@M@@a_i@@` 换成 `@@M@@b_i=rp(S_i)@@`。这一替换产生两笔非负误差：系数误差 `@@M@@V=\sum_i(a_i-b_i)^2@@` 与未用尽的头部测试能量 `@@M@@L=r^2-\sum_ib_i^2@@`，而二者期望之和恰好被平方半径亏损控制：`@@M@@\mathbb EV+\mathbb EL\le R^2-r^2@@`。真正的难点在相消：两个原子若从头部同一顶点离开且带相反符号的和，则它们的头线段必然嵌套，把较长者切开会增大其平方线段测试，于是反号乘积被测试"未满一"的差额吸收；由此得到门口质量估计 `@@M@@\|m\|_2\le\sqrt{\eta+2\theta}@@`（其中 `@@M@@m(g)=\mathbb E|b(g)|@@`，`@@M@@\eta=\mathbb EV@@`、`@@M@@\theta=\mathbb EL@@`）。最后每个锥上的项范数不超过 `@@M@@m(g)@@`，锥的 `@@M@@\ell_2@@` 分解给出 `@@M@@\|Q_Hy\|\le\sqrt\eta+\sqrt{\eta+2\theta}\le2\sqrt{R^2-r^2}@@`。至于 AUC 障碍，则利用空间的另一特征：根路径泛函 `@@M@@d_{[o,v]}@@` 范数为 1，而子增量 `@@M@@e^*_{v^\frown n}@@` 是弱零 (weakly null) 单位向量；正的单侧渐近模会迫使范数沿路径几何式增长，与路径范数的一致有界矛盾。无穷树上还有不需要迭代的版本：取全体路径范数的上确界 `@@M@@M@@`，同样的增益论证给出 `@@M@@M\ge(1+\gamma)M@@`，自相矛盾。

## 可信度与备注

主结果已 Lean 形式化。本篇是族内枢纽：其尾估计正是姊妹篇《Distortion of countably branching diamonds…》推出 `@@M@@D^2\ge1+k/4@@` 的直接输入；另一姊妹篇（自反树空间）在 `@@M@@X@@` 上用自身的成对引理得常数 `@@M@@1/12@@`，本篇的联合预算机制更强。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，具体常数以论文陈述为准。

{% endraw %}
