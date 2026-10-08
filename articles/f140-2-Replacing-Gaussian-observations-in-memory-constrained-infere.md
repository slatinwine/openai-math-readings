---
layout: default
title: "Replacing Gaussian observations in memory-constrained inference"
family: "140"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Replacing Gaussian observations in memory-constrained inference

> 结果族 140：Memory–sample lower bounds for noiseless Gaussian regression　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

你用第一批顾客的评价挑出了想收藏的评论，然后反复研究这批"被选中的"评价——它们天生带着幸存者偏差；若换成一批全新的顾客，结论会差多少？这篇论文证明：差价极小，至多 `@@M@@O(d)@@`。这条"换新对比定理"直接锁死了小内存学习器的样本需求。

**关键词卡片**

- 条件互信息（conditional mutual information）：在已知辅助数据的前提下，消息还额外泄露多少信号情报
- 自适应偏差（adaptivity bias）：用"帮着做选择的那批数据"自己证明自己，必然有偏
- 熵（entropy）：消息有多少种可能取值，本文允许它大到 `@@M@@d^2@@`
- 临界半径（critical radius）：在每个点上找到信息最"浓缩"的尺度，让新旧两侧的偏差恰好对消
- 信息位势（information potential）：`@@M@@J(U)=I(S;U\mid G,GS)@@`，随观测块数线性增长，却被成功输出逼出下界

**看个具体例子**

比较两个实验：左边让"旧数据"参与挑选消息，右边换成全新独立数据——

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><rect x="25" y="55" width="225" height="170" fill="#f6f8fa" stroke="#333" stroke-width="2"/><rect x="310" y="55" width="225" height="170" fill="#f6f8fa" stroke="#333" stroke-width="2"/><text x="137" y="45" font-size="14" fill="#333" text-anchor="middle">对齐实验（旧数据）</text><text x="422" y="45" font-size="14" fill="#333" text-anchor="middle">独立实验（全新数据）</text><rect x="52" y="72" width="170" height="26" fill="#fff" stroke="#c0392b"/><text x="137" y="90" font-size="13" fill="#333" text-anchor="middle">信号 S（球面均匀）</text><rect x="52" y="118" width="170" height="26" fill="#fff" stroke="#333"/><text x="137" y="136" font-size="13" fill="#333" text-anchor="middle">旧高斯行 A 参与挑选</text><rect x="52" y="164" width="170" height="26" fill="#fff" stroke="#333"/><text x="137" y="182" font-size="13" fill="#333" text-anchor="middle">消息 W（熵 ≤ d²）</text><line x1="137" y1="98" x2="137" y2="118" stroke="#333" stroke-width="2"/><line x1="137" y1="144" x2="137" y2="164" stroke="#333" stroke-width="2"/><rect x="337" y="72" width="170" height="26" fill="#fff" stroke="#c0392b"/><text x="422" y="90" font-size="13" fill="#333" text-anchor="middle">信号 S（同一分布）</text><rect x="337" y="118" width="170" height="26" fill="#fff" stroke="#333"/><text x="422" y="136" font-size="13" fill="#333" text-anchor="middle">全新独立行 G</text><rect x="337" y="164" width="170" height="26" fill="#fff" stroke="#333"/><text x="422" y="182" font-size="13" fill="#333" text-anchor="middle">同一消息 W 的信息</text><line x1="422" y1="98" x2="422" y2="118" stroke="#333" stroke-width="2"/><line x1="422" y1="144" x2="422" y2="164" stroke="#333" stroke-width="2"/><text x="280" y="110" font-size="13" fill="#c0392b" text-anchor="middle">信息差</text><text x="280" y="130" font-size="13" fill="#c0392b" text-anchor="middle">≤ K·d</text><text x="280" y="250" font-size="13" fill="#333" text-anchor="middle">两个实验的剩余信息之差 ≤ K·d：d=1000 时只差约 1000K nats</text></svg>

</div>

差价是 `@@M@@Kd@@`，而达到角精度 `@@M@@\epsilon@@` 所需的信息约 `@@M@@c\,d\log(1/\epsilon)@@`（`@@M@@d=1000@@`、`@@M@@\epsilon=10^{-6}@@` 时约 `@@M@@13800\,c@@` nats）——差价只占零头。于是每消化一块（`@@M@@d/10@@` 条）观测，净信息至多涨 `@@M@@Kd@@`，逼出 `@@M@@T=\Omega(d\log(1/\epsilon))@@`。记账方式很直观：把"还剩多少不知道"当成水位，每块观测后水位至多升一格固定的 `@@M@@Kd@@`，而成功输出要求水位灌到 `@@M@@c\,d\log(1/\epsilon)@@` 那么高，块数不够就注定灌不满。

**为什么值得关心**

它把"选择偏差要付多少信息代价"从哲学疑问变成了带绝对常数的定理，并以此为小内存学习器钉死了样本下界。

> 已 Lean 形式化

## 一句话结论

本文证明"换行比较定理"：把参与挑选有限消息的高斯行整体换成全新独立行，关于信号的剩余条件互信息至多增加 `@@M@@Cd@@`；据此推出 `@@M@@o(d^2)@@` 比特记忆的学习器达到 `@@M@@3/5@@` 成功率、角精度 `@@M@@0<\epsilon\le1/10@@` 需要 `@@M@@\Omega(d\log(1/\epsilon))@@` 个精确观测。

## 问题背景

从数据中选出的有限消息会改变这些数据的条件分布：条件在消息 `@@M@@W@@` 上，曾用于挑选 `@@M@@W@@` 的那些高斯行通常是有偏的。这正是记忆受限推断（memory-constrained inference）的核心困难——Raz（2016）的分支程序（branching program）下界、Steinhardt–Duchi（2015）的记忆依赖极小极大界、Sharan–Sidford–Valiant（2019）的连续回归框架都要面对它。无噪标签比噪声标签信息更多，SSV 的噪声下界因此不够用。另一方面，Russo–Zou（2016）与 Xu–Raginsky（2017）关于"自适应选择的统计量与独立参考之比较"的结果提示：选择本身要付信息代价，但代价几何此前未知。本文在与 `@@M@@d@@` 成比例的行维下把这一代价精确到 `@@M@@O(d)@@`，几何计算则属于 Mattila（1975）以逆距离控制投影能量的传统。

## 主要结果

主定理（临界半径比较，critical-radius comparison）：设 `@@M@@S@@` 均匀分布于 `@@M@@S^{d-1}@@`，`@@M@@m=\lfloor d/10\rfloor@@`、`@@M@@\ell=\lfloor d/2\rfloor@@`，`@@M@@A@@` 为 `@@M@@m@@` 行标准高斯矩阵且与 `@@M@@S@@` 独立，`@@M@@W@@` 为可数消息、可与 `@@M@@(S,A)@@` 有任意联合依赖、熵（entropy）`@@M@@H(W)\le d^2@@`；`@@M@@C@@` 为与一切独立的 `@@M@@\ell-m@@` 行高斯矩阵，`@@M@@G@@` 为与 `@@M@@(S,W)@@` 独立的 `@@M@@\ell@@` 行高斯矩阵。则对充分大的 `@@M@@d@@`，
`@@M@@DI(S;W\mid G,GS)\le I(S;W\mid A,C,AS,CS)+Kd,@@`
其中 `@@M@@K@@` 为绝对常数：把"帮着选消息的行"换成新鲜行，条件互信息只多花 `@@M@@O(d)@@`。流式推论：`@@M@@M(d)=o(d^2)@@`、均匀球面角精度 `@@M@@0<\epsilon(d)\le1/10@@`、成功概率至少 `@@M@@3/5@@`、确定性有限视野（deterministic finite horizon）的 learner 必须满足 `@@M@@T=\Omega(d\log(1/\epsilon))@@`。论文还发展另外两条比较路线——逐行替换的混合（hybrid）比较与固定纤维（fiber）测度比较——各自得到量级相同的流式端点。

## 证明思路

比较两个实验：对齐实验保留实际行 `@@M@@A@@` 并追加独立行 `@@M@@C@@`，独立实验只给全新行 `@@M@@G@@`；两者保持信号—消息与信号—矩阵的边缘分布不变，仅全联合律不同。信息差中含一个负的条件行信息项；数据处理不等式把它与"实际条件标签律对后验（posterior）`@@M@@P_{S\mid W}@@` 投影"的散度挂钩，剩下的只有独立投影的熵与一个对齐对数密度。控制这个密度是分析的枢纽。

为此先证明混合矩估计（mixed moment）：在 `@@M@@q@@` 阶矩中，实际行被全部 `@@M@@q@@` 个因子共享，而独立辅助行在各个因子中分别平均；高斯积分产生逆长度与信号差向量的逆 Gram 行列式，一条局部质量界控制相继张成周围的细管，另一条控制小径向尺度之和。这与 SSV 的高矩展开一脉相承，但多行、精确标签、局部质量的版本是新的。

真正让两项相消的是临界半径精细化：对每对 `@@M@@(w,s)@@`，在二进半径 `@@M@@R_j=2^{1-j}@@` 中取使 `@@M@@R^{-\ell}F_w(B(s,R))@@` 达到最大的"临界半径"，并记录其对数质量水平 `@@M@@q_w(s)=\lceil\log b_w(s)\rceil@@`。在该半径上限制后验，独立实验的覆盖熵下降；同一个水平又把对齐投影密度抬高恰好相反的数量，于是两项对消。精细化标签的熵代价仅 `@@M@@H(E\mid W)\le C\log(d+1+H(W))@@`，在 `@@M@@H(W)\le d^2@@` 时为 `@@M@@O(\log d)@@`，可被 `@@M@@Kd@@` 吸收。

流式应用按块进行：定义信息位势 `@@M@@J(U)=I(S;U\mid G,GS)@@`，每块 `@@M@@m=\lfloor d/10\rfloor@@` 个样本后 `@@M@@J@@` 至多增加 `@@M@@Kd@@`，初始位势为零，故终态满足 `@@M@@J(W_f)\le Kd\lceil T/m\rceil@@`。另一方面，残差球引理给出成功输出必须携带的信息量：`@@M@@J(W_f)\ge\frac{a-1}{2}(L-\log4)-\log2\ge c_0 dL@@`，其中 `@@M@@L=\log(1/\epsilon)@@`、`@@M@@a=d-\ell@@`。两式相较即得 `@@M@@T\ge c\,dL@@`。沿途另设两道闸门：输出容量估计 `@@M@@p\le(T+1)2^M\epsilon^{d-1}@@` 迫使 `@@M@@L=o(d)@@`；"白送全部数据"的对径式估计迫使 `@@M@@T>d/4@@`，保证块数至少为一。

## 可信度与备注

主结果已 Lean 形式化（结果族 140 附 Lean 证明文档）。本文从信息论端（互信息比较）逼近族 140 的统一下界，姊妹篇《Projection moments…》与《Subsphere methods…》从几何测度论端给出互补证明，三者在模型与常数上互相校准。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文的流式下界主定理已形式化，混合与纤维两条辅助比较的显式常数以论文文本为准。

{% endraw %}
