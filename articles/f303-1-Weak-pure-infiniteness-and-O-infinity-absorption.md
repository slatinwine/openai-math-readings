---
layout: default
title: "Weak pure infiniteness and O-infinity absorption"
family: "303"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Weak pure infiniteness and O-infinity absorption

> 结果族 303：Weak pure infiniteness and Cuntz-algebra absorption　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明：复 `@@M@@C^*@@`-代数中每个正元都真无限（properly infinite）即蕴含强纯无限（strongly purely infinite），解决了 Kirchberg–Rørdam 比较问题的"普通→强"部分；对精确代数，固定放大 `@@M@@n@@` 的弱条件即足够，从而可分核代数必吸收 `@@M@@\mathcal O_\infty@@`。

## 问题背景

纯无限性（pure infiniteness）刻画 `@@M@@C^*@@`-代数的正元在 Cuntz 比较（Cuntz comparison，`@@M@@u\precsim v@@` 指 `@@M@@u@@` 是 `@@M@@v@@` 的渐进压缩像）下自我复制的能力，源自 Cuntz 1978 年的工作。Kirchberg–Rørdam（2002）在非单、非幺的一般框架下区分出弱、普通、强三个层次：普通指每个正元 `@@M@@h@@` 真无限（`@@M@@h\oplus h\precsim h@@`）；弱指存在先取定的 `@@M@@n@@` 使每个 `@@M@@h^{\oplus n}@@` 真无限；强则要求任意两个正元可被同时"对角化"且混合项任意小。他们证明强⇒普通⇒弱，而反方向蕴含是否成立即著名的比较问题（Question 9.5，问题清单 STW99 之 Problem LXXII）。此前正面答案只覆盖单代数、实秩零、本原理想空间（primitive ideal space）Hausdorff、理想性质及拓扑维数零等特殊情形。问题要紧，是因为在可分核范畴强纯无限性等价于吸收 Cuntz 代数 `@@M@@\mathcal O_\infty@@` 这一张量正则性。

## 主要结果

**定理 A**：设复 `@@M@@C^*@@`-代数 `@@M@@C@@` 满足条件 (P)——每个 `@@M@@h\in C_+@@` 真无限。则对任意 `@@M@@a,b\in C_+@@`、`@@M@@c\in C@@` 与 `@@M@@\varepsilon>0@@`，存在 `@@M@@s,t\in C@@` 使
`@@M@@D\|s^*as-a\|<\varepsilon,\qquad \|t^*bt-b\|<\varepsilon,\qquad \|s^*ct\|<\varepsilon.@@`
混合项 `@@M@@c@@` 可完全任取；取 `@@M@@(a,b,c)=(x^2,y^2,xy)@@` 即得强纯无限性的标准定义，故 `@@M@@C@@` 强纯无限，且系数范数有与混合精度无关的一致界。

**定理 B**：若 `@@M@@C@@` 精确（exact，即极小张量积保持短正合列），且对某个固定 `@@M@@n\ge 1@@` 每个 `@@M@@h\in C_+@@` 的 `@@M@@h^{\oplus n}@@` 都真无限（弱纯无限性，记 (F`@@M@@_n@@`)），则每个正元已真无限，`@@M@@C@@` 强纯无限——放大数 `@@M@@n@@` 可被彻底去掉。

**推论**：可分核（nuclear）代数只要满足某个 (F`@@M@@_n@@`)，就有 `@@M@@A\cong A\otimes_{\min}\mathcal O_\infty@@`。因此在可分核范畴内，弱纯无限=纯无限=强纯无限=`@@M@@\mathcal O_\infty@@`-吸收彼此等价，全程不需单性或单位元；连无投影的锥 `@@M@@C_0((0,1])\otimes\mathcal O_\infty@@` 这类例子也在覆盖之列。

## 证明思路

全文由两条互补路线组成，公共工具是"切割后运输"（foundations 一节）：谱切割后的 Cuntz 比较可由双对偶中的矩形偏等距 `@@M@@w@@`（`@@M@@w^*w=e_h@@`，`@@M@@ww^*\le e_v@@`）实现，共轭把遗传子代数（hereditary subalgebra）`@@M@@\mathrm{Her}(h)@@` 整体嵌入 `@@M@@\mathrm{Her}(v)@@`，并保持 Cuntz 类与一切矩阵水平上的表示范数，因而可把若干正交拷贝连同整组有限元组一起搬运。

先看 (P)⇒强纯无限。目标是在 `@@M@@\mathrm{Her}(a)@@`、`@@M@@\mathrm{Her}(y)@@` 中找正压缩 `@@M@@p,q@@`：保住"输入表示范数超过 `@@M@@1/2@@` 处范数为 1"的信号，同时 `@@M@@\|e_pce_q\|<1@@`。图构造（graph 一节）把 `@@M@@a@@` 的切割装成 `@@M@@k+2@@` 个正交拷贝，自由参数 `@@M@@S_1,\dots,S_k@@` 后选，而"测量" `@@M@@X,B_i@@` 先行算定；若缺陷 `@@M@@y(1-c^*p^2c)y@@` 在检测 `@@M@@y@@` 的表示中消失，则强制 `@@M@@\pi(B_i)=\pi(S_i)@@`——失败被压缩为有限个显式等式。继而在 (P) 下排除这组等式：一对变量借 Blackadar–Cuntz 缩放元（scaling element）逼出带非零缺陷的等距，另一对被同时拉进又推出该缺陷（此节技术性较强，此处从略），经理想切割得 `@@M@@\|e_pce_q\|<1@@`。分离一节（separation）再把依赖输入的界一致化：(P) 在有界积中保持且比较行有一致界，取积作反证得一致常数 `@@M@@\theta<1@@`；迭代使 `@@M@@\|e_pce_q\|\le\theta^k@@` 任意小而信号不丢；最后把 `@@M@@a,b@@` 的高谱部分比较进分离角，系数范数 `@@M@@\le\delta^{-1/2}@@` 与混合精度无关，完成定理 A。

再看精确情形去掉放大数 `@@M@@n@@`。万有收缩代数 `@@M@@\mathcal U=C^*(1,u)@@` 不精确：它内嵌 `@@M@@C^*(\mathbb F_2)@@`，文中给出自足证明——对角态的 GNS 恰为左右正则表示，而 4-正则树邻接算子范数 `@@M@@\le 2\sqrt3<4@@`，产生矛盾。有限词压缩把不精确性化为一致间隙 `@@M@@\gamma>0@@`：精确代数中的收缩不可能同时近似约化地包含每个有限矩阵收缩。与 (F`@@M@@_n@@`) 结合得扰动命题：单个扰动可同时在范数切片 `@@M@@\{P:\|h_P\|\ge r\}@@`（拟紧，无需 Hausdorff）的所有本原商中阻止相消，下界与切片及 `@@M@@n@@` 无关。局部化一节（localization）用三次"有限耦合"造出平方零元（square-zero）`@@M@@x@@`：先造支撑空间上非标量的自伴元，再分离谱窗并删除窄对角块逼出正负部皆非零，最后耦合得 `@@M@@x^2=0@@` 且逐点非零。平方零元的两个正交平方 Cuntz 等价，于是在同一切片上反复减半得 `@@M@@z_j^{\oplus 2^j}\precsim a@@`；取 `@@M@@2^j\ge n@@`，配合 (F`@@M@@_n@@`) 与理想比较得 `@@M@@((a-r)_+)^{\oplus 2}\precsim a@@`，令 `@@M@@r\downarrow 0@@` 即得 (P)，由定理 A 收尾。核路线（nuclear 一节）另用矩阵障碍元组与"核商必精确"的矛盾独立重现该结论，再由中心序列（central sequence）吸收判据导出 `@@M@@\mathcal O_\infty@@`-吸收推论。

## 可信度与备注

任务文件标注 formalized 为 false：主结果暂无 Lean 形式化证明，本手稿系 OpenAI 未发表预印本（2026-09-25 版），请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。结果族 303 即以本文为代表，文内 exact 与 nuclear 两条路线互为独立印证，后者绕开了"精确性传给商"的深层定理。论证高度模块化（运输—图—分离—一致间隙—局部化），各节可分别查验，但整体技术密度很高，完整可信度仍有待同行评议确认。

{% endraw %}
