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

## 一句话结论

本文证明"换行比较定理"：把参与挑选有限消息的高斯行整体换成全新独立行，关于信号的剩余条件互信息至多增加 \(Cd\)；据此推出 \(o(d^2)\) 比特记忆的学习器达到 \(3/5\) 成功率、角精度 \(0<\epsilon\le1/10\) 需要 \(\Omega(d\log(1/\epsilon))\) 个精确观测。

## 问题背景

从数据中选出的有限消息会改变这些数据的条件分布：条件在消息 \(W\) 上，曾用于挑选 \(W\) 的那些高斯行通常是有偏的。这正是记忆受限推断（memory-constrained inference）的核心困难——Raz（2016）的分支程序（branching program）下界、Steinhardt–Duchi（2015）的记忆依赖极小极大界、Sharan–Sidford–Valiant（2019）的连续回归框架都要面对它。无噪标签比噪声标签信息更多，SSV 的噪声下界因此不够用。另一方面，Russo–Zou（2016）与 Xu–Raginsky（2017）关于"自适应选择的统计量与独立参考之比较"的结果提示：选择本身要付信息代价，但代价几何此前未知。本文在与 \(d\) 成比例的行维下把这一代价精确到 \(O(d)\)，几何计算则属于 Mattila（1975）以逆距离控制投影能量的传统。

## 主要结果

主定理（临界半径比较，critical-radius comparison）：设 \(S\) 均匀分布于 \(S^{d-1}\)，\(m=\lfloor d/10\rfloor\)、\(\ell=\lfloor d/2\rfloor\)，\(A\) 为 \(m\) 行标准高斯矩阵且与 \(S\) 独立，\(W\) 为可数消息、可与 \((S,A)\) 有任意联合依赖、熵（entropy）\(H(W)\le d^2\)；\(C\) 为与一切独立的 \(\ell-m\) 行高斯矩阵，\(G\) 为与 \((S,W)\) 独立的 \(\ell\) 行高斯矩阵。则对充分大的 \(d\)，
\[I(S;W\mid G,GS)\le I(S;W\mid A,C,AS,CS)+Kd,\]
其中 \(K\) 为绝对常数：把"帮着选消息的行"换成新鲜行，条件互信息只多花 \(O(d)\)。流式推论：\(M(d)=o(d^2)\)、均匀球面角精度 \(0<\epsilon(d)\le1/10\)、成功概率至少 \(3/5\)、确定性有限视野（deterministic finite horizon）的 learner 必须满足 \(T=\Omega(d\log(1/\epsilon))\)。论文还发展另外两条比较路线——逐行替换的混合（hybrid）比较与固定纤维（fiber）测度比较——各自得到量级相同的流式端点。

## 证明思路

比较两个实验：对齐实验保留实际行 \(A\) 并追加独立行 \(C\)，独立实验只给全新行 \(G\)；两者保持信号—消息与信号—矩阵的边缘分布不变，仅全联合律不同。信息差中含一个负的条件行信息项；数据处理不等式把它与"实际条件标签律对后验（posterior）\(P_{S\mid W}\) 投影"的散度挂钩，剩下的只有独立投影的熵与一个对齐对数密度。控制这个密度是分析的枢纽。

为此先证明混合矩估计（mixed moment）：在 \(q\) 阶矩中，实际行被全部 \(q\) 个因子共享，而独立辅助行在各个因子中分别平均；高斯积分产生逆长度与信号差向量的逆 Gram 行列式，一条局部质量界控制相继张成周围的细管，另一条控制小径向尺度之和。这与 SSV 的高矩展开一脉相承，但多行、精确标签、局部质量的版本是新的。

真正让两项相消的是临界半径精细化：对每对 \((w,s)\)，在二进半径 \(R_j=2^{1-j}\) 中取使 \(R^{-\ell}F_w(B(s,R))\) 达到最大的"临界半径"，并记录其对数质量水平 \(q_w(s)=\lceil\log b_w(s)\rceil\)。在该半径上限制后验，独立实验的覆盖熵下降；同一个水平又把对齐投影密度抬高恰好相反的数量，于是两项对消。精细化标签的熵代价仅 \(H(E\mid W)\le C\log(d+1+H(W))\)，在 \(H(W)\le d^2\) 时为 \(O(\log d)\)，可被 \(Kd\) 吸收。

流式应用按块进行：定义信息位势 \(J(U)=I(S;U\mid G,GS)\)，每块 \(m=\lfloor d/10\rfloor\) 个样本后 \(J\) 至多增加 \(Kd\)，初始位势为零，故终态满足 \(J(W_f)\le Kd\lceil T/m\rceil\)。另一方面，残差球引理给出成功输出必须携带的信息量：\(J(W_f)\ge\frac{a-1}{2}(L-\log4)-\log2\ge c_0 dL\)，其中 \(L=\log(1/\epsilon)\)、\(a=d-\ell\)。两式相较即得 \(T\ge c\,dL\)。沿途另设两道闸门：输出容量估计 \(p\le(T+1)2^M\epsilon^{d-1}\) 迫使 \(L=o(d)\)；"白送全部数据"的对径式估计迫使 \(T>d/4\)，保证块数至少为一。

## 可信度与备注

主结果已 Lean 形式化（结果族 140 附 Lean 证明文档）。本文从信息论端（互信息比较）逼近族 140 的统一下界，姊妹篇《Projection moments…》与《Subsphere methods…》从几何测度论端给出互补证明，三者在模型与常数上互相校准。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文的流式下界主定理已形式化，混合与纤维两条辅助比较的显式常数以论文文本为准。

{% endraw %}
