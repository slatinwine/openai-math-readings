---
layout: default
title: "Linear Variance of the Random 3-SAT Hitting Time"
family: "235"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Linear Variance of the Random 3-SAT Hitting Time

> 结果族 235：Limiting random SAT thresholds, sharp variance and computability　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对 `@@M@@n@@` 个变量上的随机 3-SAT，证明了首个不可满足前缀下标 `@@M@@H_n@@` 的方差恰为 `@@M@@\Theta(n)@@`：新证明的上界 `@@M@@\operatorname{Var}(H_n)\le Cn@@` 去掉了姊妹篇 `@@M@@O(n\log n)@@` 估计中的对数损失，下界由 Wilson 转移宽度定理给出，从而确定随机 3-SAT 相变窗口的正确尺度是 `@@M@@\sqrt n@@`。

## 问题背景

随机 `@@M@@k@@`-SAT 的相变研究不只问"阈值在哪里"，还问"窗口有多宽"。Friedgut 证明转移是尖锐的；Wilson（2002）证明 `@@M@@k\ge3@@` 时可满足概率从一个固定水平降到另一个固定水平至少需要 `@@M@@\Omega_k(\sqrt n)@@` 条子句，即窗口不能太窄；Carenini 的并发工作得到 `@@M@@O_{k,\eta}(n^{1/2+1/k})@@` 的窗口上界与 `@@M@@O_k(n^{1+2/k})@@` 的方差上界。窗口宽度由方差控制，但方差还取决于尾部，固定中心窗口的界并不足以给出方差界。同族姊妹篇对一般 `@@M@@k@@` 证明 `@@M@@\Theta_k(n)@@`（`@@M@@k\ge4@@`），却在 `@@M@@k=3@@` 留下 `@@M@@n@@` 与 `@@M@@n\log n@@` 之间的对数空隙；本文专攻三文字子句，把这个空隙闭合。

## 主要结果

模型为独立、均匀符号、三变量互异、有放回抽样的 proper 3-clause 过程。定理：存在绝对常数 `@@M@@C<\infty@@` 使 `@@M@@\operatorname{Var}(H_n)\le Cn@@`（`@@M@@n\ge3@@`）；另有绝对常数 `@@M@@c>0@@` 与 `@@M@@n_0@@` 使 `@@M@@\operatorname{Var}(H_n)\ge cn@@`（`@@M@@n\ge n_0@@`），故 `@@M@@\operatorname{Var}(H_n)=\Theta(n)@@`。推论：对每个固定 `@@M@@0<\eta<1/2@@`，可满足概率从 `@@M@@1-\eta@@` 降到 `@@M@@\eta@@` 的中心窗口宽度为 `@@M@@\Theta_\eta(\sqrt n)@@`。上界是全新贡献，下界由 Wilson 定理的短推导得到。值得注意的是全文不需要阈值位置的任何信息，只围绕有限尺寸期望 `@@M@@\mathbb E H_n@@` 集中。

## 证明思路

先把 `@@M@@H_n@@` 截断在 `@@M@@L=10n@@`，记 `@@M@@T=\min(H_n,L)@@`，用坐标删除形式的 Efron--Stein 不等式把 `@@M@@\operatorname{Var}(T)@@` 归结为 `@@M@@\sum_i\mathbb E D_i^2@@`，其中 `@@M@@D_i@@` 是删去第 `@@M@@i@@` 条子句（保留其余子句原时间指标）带来的延迟。新引擎是一个势函数（potential）：对任意指派集合 `@@M@@S\subseteq\{0,1\}^u@@`，令 `@@M@@q_j(S)@@` 为 `@@M@@j@@` 条随机 proper 2-子句"杀死"`@@M@@S@@`（即无成员满足全部子句）的概率，`@@M@@P_d(S)=\sum_{j<d}q_j(S)@@` 有界且随 `@@M@@S@@` 缩小而增。基于冻结坐标（frozen coordinate）计数 `@@M@@b@@` 的精确杀伤公式 `@@M@@h_a(S)=(b)_a/(2^a(u)_a)@@`，一条 2-子句与一条 3-子句的杀伤概率满足 `@@M@@h_2^{3/2}\le 3h_3+u^{-3}@@`；对 `@@M@@j@@` 求和得势漂移引理：`@@M@@q_d(S)^{3/2}@@` 被 `@@M@@P_d@@` 在一条随机 3-子句下的期望增量控制。再把固定 `@@M@@C_i@@` 的三个变量称为根（root），其余子句按与根的接触分为普通、测试（test）与碰撞（collision）三类；暴露静态信息后，测试子句的非根部分仍是独立的 2-子句。若恢复 `@@M@@C_i@@` 会破坏可满足性，则每个可用根的翻转都必须被该根的测试子句拦截，无碰撞时给出三个独立测试同时杀伤当前非根解集 `@@M@@S_m@@` 的概率 `@@M@@p_m^3@@`。势漂移则把"`@@M@@S_m@@` 停留在高水平"的总时间压到 `@@M@@O(d^{3/2})@@`。关键的调制技巧在于条件作用分层：剩余时长的估计需要知道删除事件是否已发生（用较大 `@@M@@\sigma@@` 域 `@@M@@\mathcal H_m@@`），但其上界 `@@M@@W_m@@` 只依赖较小的 `@@M@@\sigma@@` 域 `@@M@@\mathcal G_m@@`，故可与给定 `@@M@@\mathcal G_m@@` 的独立测试概率相乘；恒等式 `@@M@@3-3/2=3/2@@` 使乘积恰好落回势函数可积的范围，得无碰撞时 `@@M@@\mathbb E[D_i^2\mid\mathcal E]\le 2K^2d^3@@`。最后用根入射计数 `@@M@@d@@` 的一致有界矩与碰撞稀有概率（`@@M@@O(n^{-2})@@`）平均掉碰撞情形，得 `@@M@@\mathbb E D_i^2=O(1)@@`，对 `@@M@@i@@` 求和即 `@@M@@\operatorname{Var}(T)=O(n)@@`；再用一阶矩尾部 `@@M@@2^n(7/8)^m@@` 以指数速度去掉截断。下界由 Wilson 分位数分离定理：`@@M@@3/4@@` 与 `@@M@@1/4@@` 水平的整数分位点相距 `@@M@@\ge c_0\sqrt n@@`，取两个独立副本比较即得 `@@M@@\operatorname{Var}(H_n)\ge c_0^2n/16@@`。

## 可信度与备注

本文主结果暂无形式化证明，OpenAI 官方声明未经形式化的结果可能有问题，请以社区核验为准。文中完整重证并沿用了同族姊妹篇（一般 `@@M@@k@@` 方差）的删除–根测试框架，仅替换 `@@M@@k=3@@` 处关键的占位估计，从而闭合对数空隙；姊妹篇则提供 `@@M@@k\ge4@@` 的 `@@M@@\Theta_k(n)@@` 对照结果，两文合成"每个固定 `@@M@@k\ge3@@` 方差均为 `@@M@@\Theta_k(n)@@`"的完整图景。作者将解决可满足性猜想的优先权归于 Carenini 的并发工作；本文处理的是更精细的涨落问题。

{% endraw %}
