---
layout: default
title: "The ℓ¹-Bass Conjecture for Discrete Groups"
family: "207"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The ℓ¹-Bass Conjecture for Discrete Groups

> 结果族 207：The ℓ¹-Bass conjecture for all discrete groups　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文对任意离散群证明了 `@@M@@\ell^1@@`-Bass 猜想：`@@M@@\ell^1(G)@@` 上幂等矩阵的 Hattori–Stallings 迹只在有限多个有限阶元素共轭类上非零。这去掉了 Berrick–Chatterji–Mislin 此前证明所依赖的"Bost 装配映射有理满射"条件，把猜想推广到一切离散群。

## 问题背景

对离散群 `@@M@@G@@`，`@@M@@\ell^1(G)@@` 是系数绝对可和的函数在卷积下构成的复 Banach 群代数。幂等矩阵 `@@M@@e\in M_q(\ell^1(G))@@` 代表 `@@M@@\ell^1(G)@@` 上的有限生成射影模（projective module），其 Hattori–Stallings 迹（Hattori–Stallings trace）按共轭类 `@@M@@C@@` 取系数 `@@M@@\tau_C(e)=\sum_{g\in C}\sum_i e_{ii}(g)@@`，是"秩"的精细加细。Bass 自 1976 年起对整群环 `@@M@@\mathbb{Z}G@@` 提出的迹支撑问题是群环 `@@M@@K@@` 理论的经典难题。Berrick、Chatterji 与 Mislin 于 2004 年把问题移植到 `@@M@@\ell^1@@` 代数并表述为有限支撑形式，但只在 Bost 装配映射（assembly map）零次有理满射的可数群上证得；借助 Lafforgue 的 Banach 代数 `@@M@@K@@` 理论可覆盖顺从群（amenable group）。一般离散群上没有任何装配假设可用，且 `@@M@@\ell^1@@` 幂等元的系数可散布在字长任意大的群元素上——群环情形"非零乘积只涉及固定有限集"的论证完全失效，这正是此前卡住的地方。

## 主要结果

主定理：设 `@@M@@G@@` 是任意离散群，`@@M@@q\ge1@@`，`@@M@@e\in M_q(\ell^1(G))@@` 幂等。则存在有限子集 `@@M@@F\subset\mathcal C_{\rm fin}(G)@@`（`@@M@@\mathcal C_{\rm fin}(G)@@` 记有限阶元素共轭类全体），使得对一切 `@@M@@C\notin F@@` 有 `@@M@@\tau_C(e)=0@@`。等价地，迹映射 `@@M@@\operatorname{HS}^1\colon K_0(\ell^1(G))\to\ell^1(\mathcal C(G))@@` 的像含于代数直和 `@@M@@\bigoplus_{C\in\mathcal C_{\rm fin}(G)}\mathbb C[C]@@`。要注意"有限支撑"是结论的实质部分：迹系数虽然绝对可和，"只有有限多个类非零"并非自动成立，证明必须给出与所考察共轭类无关的统一几何截断。

## 证明思路

证明分四步。先做归约：取有限支撑矩阵 `@@M@@a@@` 逼近 `@@M@@e@@`，令 `@@M@@b=4(a-a^2)@@`，用收敛幂级数 `@@M@@Q=(1-b)^{-1/2}@@` 构造 `@@M@@p=\frac12 I+(a-\frac12 I)Q@@`，它在矩阵 Banach 代数中幂等且与 `@@M@@e@@` 相似；迹泛函满足 `@@M@@T_C(ab)=T_C(ba)@@`，故相似不改变任何迹系数。再利用指数权范数 `@@M@@\|v\|_c=\sum|v(h)|_1e^{c|h|}@@` 的次乘性，把问题挪进有限生成子群并得到 `@@M@@\sum|p(h)|_1e^{c|h|}<\infty@@`——`@@M@@p@@` 未必有限支撑，但具有指数矩。第二步把迹系数写成循环权重：固定 `@@M@@g@@`，记其中心化子为 `@@M@@H@@`，对轨道组 `@@M@@\mathcal T_k(g)=H\backslash G^{k+1}@@` 赋权 `@@M@@\operatorname{tr}(\prod_i p(h_i^{-1}h_{i+1}))@@`，其总和恰为 `@@M@@\tau_{[g]}(p)@@`，幂等性 `@@M@@p^2=p@@` 使删去顶点时权重可合并。把组的有序时间视为单纯形，取时间平移不变、在平移向量上取值 `@@M@@1@@` 的"联络形式"（connection form），一个 Chern–Simons 式的循环 Stokes（transgression）论证表明：权重的曲率 Pfaffian 平均恰等于 `@@M@@(-1)^m\tau_{[g]}(p)@@`，且不依赖联络的选取。第三步构造平均曲率极小的联络：把带时间的组看作取值于 `@@M@@G@@` 的阶梯函数（`@@M@@f(u+1)=gf(u)@@` 带扭转），在多个时间尺度上磨光其 Dirac 测度，用辅助标签上的光滑次概率分布做"空间摘要"，配以奇时间核得到一次形式；各尺度的贡献望远镜式相消，末端的"等子核"探测到扭转 `@@M@@g@@` 并留下严格正的缩并，据此归一化为联络。曲率估计分三段：初始尺度用"曲率分量仅当两时刻接近时非零"的稀疏性配合占据数估计，中间尺度用时间核短支撑给出的 Hilbert–Schmidt 界，末尺度归结为奇异值满足 `@@M@@s_\nu\le C/\nu@@` 的顺序核；合并得 `@@M@@\mathbb E|\Pf(d\alpha)|\le C_RQ_R^n\prod_il_i@@`，其中 `@@M@@Q_R=CS^{3/2}R^{-1/10}@@`。收官时次序至关重要：先一次性选定空间半径 `@@M@@R@@` 使 `@@M@@Q_RM_p<1@@` 对所有共轭类一致成立，再令单纯形维数 `@@M@@n\to\infty@@`，得 `@@M@@\tau_{[g]}(p)=0@@` 对一切无限阶 `@@M@@g@@`；幸存的有限阶类必有共轭代表落在有限球 `@@M@@B(1,4r)@@` 内，因此只有有限多个。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准。同族姊妹篇《The Bass trace conjecture and the characteristic-zero Kaplansky idempotent conjecture》已声明主结果完成 Lean 形式化，其群环版本（第 7–8 节）的"加权循环组＋Pfaffian 探测"策略正是本文方法的出发点；本文全部估计自含证明，不以该定理为输入，两篇在机制上互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题，本文结论宜待同行核验后再行引用。

{% endraw %}
