---
layout: default
title: "Lipschitz Equivalent Separable Banach Spaces Need Not Be Linearly Isomorphic"
family: "324"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Lipschitz Equivalent Separable Banach Spaces Need Not Be Linearly Isomorphic

> 结果族 324：Lipschitz equivalent Banach spaces need not be linearly isomorphic　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

构造出可分实 Banach 空间 \(X,Y\) 与双射 \(\Psi:X\to Y\)，满足双侧 Lipschitz 界 \(\frac{4}{21}\|s-t\|_X\le\|\Psi(s)-\Psi(t)\|_Y\le\frac{76}{25}\|s-t\|_X\)，但二者不线性同构——对悬置近五十年的可分 Lipschitz 同构问题给出否定回答。

## 问题背景

Banach 空间的范数同时定义线性结构与度量。有界线性同构必然在常数倍意义下保持度量，但反过来：一个两侧都有 Lipschitz 界的双射（双 Lipschitz 等价，bi-Lipschitz equivalence）是否强迫两空间线性同构？1976 年 Ribe 证明一致同胚（uniformly homeomorphic）的赋范空间具有相同的有限维线性结构；1978 年 Aharoni 与 Lindenstrauss 构造了双 Lipschitz 等价却不线性同构的不可分例子，并明确要求可分反例。此后学界得到多个可分的一致同胚反例（Ribe；Johnson–Lindenstrauss–Schechtman），但可分的 Lipschitz 问题始终悬置：Kalton 在 2008 年综述中列为问题 3，2025 年 12 月在线发表的论文仍称其公开。另一方面，Godefroy–Kalton–Lancien 的刚性结果（与 \(c_0\) 双 Lipschitz 等价则线性同构）与 Godefroy–Kalton 的提升定理说明该问题不能由一致反例直接移植，需要全新构造。

## 主要结果

主定理：存在可分实 Banach 空间 \(X,Y\) 及双射 \(\Psi:X\to Y\)，使所有 \(s,t\in X\) 满足

\[\frac{4}{21}\|s-t\|_X\le\|\Psi(s)-\Psi(t)\|_Y\le\frac{76}{25}\|s-t\|_X.\]

并且 \(X\) 含有 \(c_0(\ell_2)\)（每个坐标是一个 \(\ell_2\) 块、以上确界为范数的零序列空间）的线性等距拷贝，而 \(Y\) 不含任何与 \(c_0(\ell_2)\) 线性同构的闭子空间。因此 \(X\) 与 \(Y\) 双 Lipschitz 等价却不线性同构。注意障碍刻意取"块值"：定理不断言 \(Y\) 不含普通 \(c_0\)，Hilbert 块是下述论证的关键。

## 证明思路

整体分三步：先在 Hilbert 空间造一个接近等距的非线性换元，再经 Lipschitz 自由空间把它线性化为完全连续算子，最后用加权图空间装配出反例并读出线性障碍。

先看 Hilbert 换元。设 \(M=U\oplus_2V\)（\(V=\ell_2\)，\(U\) 是有限维块 \(U_n\) 的 Hilbert 直和），要造双射 \(h:M\to U\)，保零且 \(\frac{24}{25}\|x-x'\|\le\|h(x)-h(x')\|\le\frac{26}{25}\|x-x'\|\)。机制是"槽"（slot）：每块选定单位向量 \(\xi_n\) 后，冻结重排 \(L_\xi\) 把各块的垂直分量留在原块、老槽系数移入偶数块、\(V\) 的标量填入奇数块，这是到上的线性等距。再让槽 \(w_n(x)\) 随输入移动：在每块内按"阶段"（stage）布置网格函数，使任意有限个不同点各自的小邻域内，充分高块的槽的坐标支撑两两不交——此即局部正交性（local orthogonality）。运动幅度用 \(\gamma(r)=c/(r\log(1/r))\) 型预算控制：这个函数一次积分发散（允许无限多次旋转），加权平方积分却有限（总扰动受控），从而 \(\sum_na_n(x)^2\|Dw_n(x)\|^2\le c^2\)（\(c=1/100\)）。于是有限截断 \(h_N\) 的导数与某个冻结等距之差至多 \(4c\)；在有限维纤维上它是固有局部微分同胚，经覆盖空间论证得全局双射。最后用逆像的尾估计（偶、奇槽项恰好相消）与对角抽取取极限，得 \(h\) 满足双侧界且到上。

再看线性化。取 Lipschitz 自由空间（Lipschitz-free space）\(E=\mathcal F(M)\)：\(\delta:M\to E\) 等距，保零 Lipschitz 映射皆有有界线性化，故 \(D=h-\pi_U\) 给出 \(q:E\to U\)，\(q\delta(u,v)=h(u,v)-u\)。局部正交性恰在此处进入：论文证明它使 \(q\) 完全连续（completely continuous，弱零列映为范数零列）。直观地，若弱零列的像不趋零，便产生一致 Lipschitz 的标量测试函数；正交性使只有有限多点保有大的极限局部 Lipschitz 常数，切除这些点的邻域后，剩余部分经 Aliaga–Noûs–Petitjean–Procházka 的紧化定理化到紧集上，由有限覆盖控制，导出矛盾。

最后装配。定义三角换元 \(B(e,v)=e+\delta(qe,v)\)，核心恒等式 \(qB=hQ_1\)（其中 \(Q_1(e,v)=(qe,v)\)）配上由 \(h^{-1}\) 写出的显式逆公式，给出双 Lipschitz 双射。对有界线性 \(Q\) 定义加权图空间（graph space）\(Z_Q\)：元素为满足 \(\sum_i2^{-i}\|s_i\|<\infty\) 且 \((Qs_i)\in c_0\) 的序列，范数为 \(\max\{\sum_i2^{-i}\|s_i\|,\sup_i\|Qs_i\|\}\)。取 \(X=Z_{Q_1}\)、\(Y=Z_q\)，逐坐标施加 \(B\) 得双射 \(\Psi\)，两条界分别由 \(B\) 的 Lipschitz 界与 \(h\) 的界控制，装配节算出常数 \(76/25\) 与 \(21/4\)。线性障碍如下：映射 \(v\mapsto((0,v_i))\) 把 \(c_0(V)=c_0(\ell_2)\) 等距嵌入 \(X\)；而在 \(Y\) 中，\(q\) 的完全连续性使假想拷贝的每个固定输出坐标沿块内正交序列趋于零，配合不交支撑论证，幸存的拷贝将把普通 \(c_0\) 嵌入 \(\ell_1(E)\)，这被 \(E=\mathcal F(M)\) 的弱序列完备性（\(M\) 超自反）排除。

## 可信度与备注

主定理已通过 Lean 形式化验证。同族姊妹篇以普通 \(c_0\) 为障碍并给出同一空间的"吸收"现象，与本文的 \(c_0(\ell_2)\) 障碍方法独立而结论互证，共同坐实"双 Lipschitz 等价不决定可分空间的线性同构类"。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本文主结果已形式化，具体常数与中间引理仍以论文文本与社区核验为准。

{% endraw %}
