---
layout: default
title: "The Artinian Lex-Plus-Powers Betti Theorem"
family: "200"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Artinian Lex-Plus-Powers Betti Theorem

> 结果族 200：Eisenbud–Green–Harris and lex-plus-powers　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在任意特征为零的域上证明了 Eisenbud–Green–Harris 与 lex-plus-powers 猜想：包含正则序列（任意长度、次数 `@@M@@\ge 2@@`）的齐次理想，其 Hilbert 函数被对应的 lex-plus-powers 理想精确匹配，全部 graded Betti 数被同一理想逐项压制。

## 问题背景

Hilbert 函数（Hilbert function）记录分次商环每一层的维数；graded Betti 数进一步记录极小自由分辨（minimal free resolution）中生成元与各阶 syzygy 的数目，是衡量理想"关系复杂度"的基本不变量。无附加约束时，Bigatti–Hulett–Pardue 定理断言：固定 Hilbert 函数，字典序理想（lex ideal）使一切 Betti 数最大。若理想 `@@M@@I@@` 还包含次数为 `@@M@@a_1,\ldots,a_n@@` 的正则序列（regular sequence），直觉上次数信息应给出更紧的约束：EGH 猜想（源自 Eisenbud–Green–Harris 的高维 Castelnuovo 理论）预测可把正则序列换成纯幂 `@@M@@(x_1^{a_1},\ldots,x_n^{a_n})@@` 而不改变 Hilbert 函数；Charalambous–Evans 的 lex-plus-powers 猜想进一步断言对应 Betti 数的逐项上界。此前的一般性结果均附带条件：Caviglia–Maclagan、Caviglia–De Stefani、Caviglia–Sammartano 要求次数快速增长；Mermin–Peeva–Stillman、Murai、Mermin–Murai 处理单项式正则序列；Abedelfatah 要求型可分裂为线性因子。任意次数的一般情形已悬置三十余年。

## 主要结果

主定理（Theorem 1.1，在 `@@M@@\C@@` 上）：设 `@@M@@2\le a_1\le\cdots\le a_n@@`，`@@M@@P=(x_1^{a_1},\ldots,x_n^{a_n})@@`，齐次理想 `@@M@@I\subseteq\C[x_1,\ldots,x_n]@@` 包含次数为 `@@M@@a_i@@` 的正则序列。在每个次数 `@@M@@d@@` 取 `@@M@@J_d=L_d+P_d@@`，其中 `@@M@@L_d@@` 是使 `@@M@@\dim_\C J_d=\dim_\C I_d@@` 成立、由字典序最大单项式组成的 lex 段（lex segment）。定理断言这些 `@@M@@J_d@@` 存在并拼成一个齐次理想 `@@M@@J@@`，且对同一个 `@@M@@J@@` 同时有
`@@M@@D\dim_\C(S/J)_d=\dim_\C(S/I)_d\ (d\ge0),\qquad \beta^S_{p,j}(S/I)\le\beta^S_{p,j}(S/J)\ (p\ge0,\ j\in\Z),@@`
其中 `@@M@@\beta^S_{p,j}=\dim_\C\Tor^S_p(S/I,\C)_j@@`，`@@M@@p@@` 为同调次数、`@@M@@j@@` 为内次数；对 `@@M@@I@@` 其余生成元的次数与个数没有任何限制。推论 1.2 经 Caviglia–Maclagan 与 Caviglia–Kummini 的 Artinian 归约及系数域下降，把 Hilbert 等式与全部 Betti 不等式推广到任意特征零域、长度 `@@M@@c\le n@@` 的正则序列，涵盖非 Artinian 商环与非代数闭域。

## 证明思路

全文是一条四步传递链 `@@M@@I\to M\to H\to G@@`：每步保持 Hilbert 函数且不减小 Betti 数，最后识别 `@@M@@G@@` 恰为规定的 lex-plus-powers 理想。第一步是真正的创新：把整个极小分辨搬进除代数系数的多项式环。姊妹篇的构造给出域扩张 `@@M@@k/\C@@`、中心除代数（central division algebra）`@@M@@\Delta@@`，以及 `@@M@@N=\Delta[x_1,\ldots,x_n]@@` 中两两交换的线性型 `@@M@@t_1,\ldots,t_n@@`，满足三角幂恒等式 `@@M@@t_i^{a_i}=c_if_i+\sum_{\ell<i}B_{i\ell}f_\ell+\sum_{\ell>i}C_{i\ell}t_\ell@@`，且有序单项式 `@@M@@\{t^\alpha\}@@` 构成整个 `@@M@@N@@` 的左 `@@M@@\Delta@@`-基。令 `@@M@@T=k[y_1,\ldots,y_n]@@` 经 `@@M@@y_i\mapsto t_i@@` 右作用于 `@@M@@N@@`：`@@M@@N@@` 既是左 `@@M@@S@@`-自由模，又是秩 `@@M@@m=\dim_k\Delta@@` 的右 `@@M@@T@@`-自由模，故 `@@M@@S/I@@` 的极小分辨转移为 `@@M@@N/IN@@` 的极小 `@@M@@T@@`-分辨，所有 Betti 数同乘 `@@M@@m@@`。再取与三角恒等式适配的单项式序：`@@M@@IN@@` 的首项系数空间是 `@@M@@\Delta@@` 的左理想，只能是 `@@M@@0@@` 或整个 `@@M@@\Delta@@`，其非零位置便定义出单项式理想 `@@M@@M\supseteq P@@`。经滤波 Koszul 复形（filtered Koszul complex）的相关分次论证——取 associated graded 只会降低微分秩、从而放大同调——并约去因子 `@@M@@m@@`，得 `@@M@@\beta(S/I)\le\beta(S/M)@@`。这种分辨层的整体转移是姊妹篇 Hilbert 结论之外的新机制。第二步用单位根扰动（distraction）加初始理想，把 `@@M@@M@@` 改造成在指数盒 `@@M@@0\le u_i<a_i@@` 内对"把 `@@M@@x_\ell@@` 换成 `@@M@@x_h@@`（`@@M@@h<\ell@@`）"这类转移封闭的理想 `@@M@@H@@`。第三步在每个次数把盒中属于 `@@M@@H@@` 的单项式换成同数量的字典序最大单项式（保留 `@@M@@P@@`）得到 `@@M@@G@@`，并通过比较"有界影子"（乘一个变量后仍留在盒内的倍数）证明 `@@M@@G@@` 确为理想。第四步做 Betti 比较：设 `@@M@@z=x_n@@`，模 `@@M@@H/zH@@` 与 `@@M@@G/zG@@` 按 `@@M@@z@@` 的指数分层，稳定性使中间各层被其余变量零化，Koszul 微分秩为零，只有两端层有贡献。引入 Koszul 秩亏 `@@M@@D_{p,j}=\dim K_p-\beta_{p,j}@@`（恰为相邻两微分秩之和），它在取子模与商时单调不增，于是结合变量个数的归纳与两端层的包含关系得 `@@M@@D(B_H)\ge D(B_G)@@`；由 Hilbert 函数相等知 Koszul 项维数相等，相减即得所需的 Betti 上界。

## 可信度与备注

两篇姊妹篇均未提供 Lean 形式化证明，OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。本文的除代数构造完全引自《Commuting Division-Coefficient Forms and the Artinian Eisenbud–Green–Harris Conjecture》的 Theorem 1.1，而本文新增的分辨转移把 Hilbert 函数结论强化为完整 Betti 不等式；末段的单项式比较作者自陈结论并非全新（沿 Mermin–Murai 定理思路重写以求自足）。家族两篇合起来给出特征零上 EGH 与 lex-plus-powers 猜想的整体解决。

{% endraw %}
