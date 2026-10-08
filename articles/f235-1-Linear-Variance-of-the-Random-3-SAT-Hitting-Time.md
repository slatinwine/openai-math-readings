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

## 入门导读 🐣

阈值告诉你悬崖在哪里，方差告诉你悬崖有多宽。这篇论文证明：随机 3-SAT 里"崩溃时刻"（第一条压垮公式的子句出现的位置）的方差恰好正比于 n——悬崖宽度被精确钉在 √n 条子句，一步不多、一步不少。不同随机样本的崩溃点会散得多开？答案：标准差恰是 √n 的量级，再无悬念。

**关键词卡片**

- 命中时间（hitting time）H_n：逐条加入子句时，第一个不可满足时刻的编号。
- 方差（variance）：随机时刻散布多宽的度量；它直接决定相变窗口的宽度。
- Efron–Stein 不等式：把总体方差拆解为"删去一条子句造成延迟"的平方和。
- 势函数（potential）：给"解集有多脆"定价的新工具，专治 k = 3 的对数空隙。
- Wilson 转移宽度定理：2002 年的老结果——窗口至少 √n 宽；本文给出与之匹配的下界。

**看个具体例子**

数字版定理：`@@M@@\operatorname{Var}(H_n)=\Theta(n)@@`。设 n = 10^6 个变量：崩溃时刻的典型偏差约 `@@M@@\sqrt{n}=10^3@@` 条子句，只占总量的 0.1%；相应地，可满足概率从 99% 跌到 1% 也只需 `@@M@@\Theta(\sqrt n)@@` 条子句——悬崖很陡，但不是刀刃。上界 `@@M@@\operatorname{Var}(H_n)\le Cn@@` 是全新贡献，删去了姊妹篇 `@@M@@O(n\log n)@@` 估计里的对数损失；下界则由 Wilson 定理直接推出。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="15">崩溃时刻 H_n 的分布：宽度 ≈ √n</text>
  <line x1="60" y1="230" x2="520" y2="230" stroke="#555" stroke-width="1.5"/>
  <path d="M120 230 C170 230 195 95 300 95 C405 95 430 230 480 230 Z" fill="#dbe9f9" stroke="#1565c0" stroke-width="2.5"/>
  <line x1="300" y1="82" x2="300" y2="230" stroke="#c62828" stroke-dasharray="5 4"/>
  <text x="300" y="72" text-anchor="middle" font-size="13" fill="#c62828">均值 ≈ α_3·n</text>
  <line x1="250" y1="250" x2="350" y2="250" stroke="#333" stroke-width="1.5"/>
  <line x1="250" y1="245" x2="250" y2="255" stroke="#333" stroke-width="1.5"/>
  <line x1="350" y1="245" x2="350" y2="255" stroke="#333" stroke-width="1.5"/>
  <text x="300" y="268" text-anchor="middle" font-size="12">典型偏差 ~ √n（n = 10^6 时约 10^3 条子句）</text>
  <text x="455" y="222" font-size="11">H_n（子句条数）</text>
</svg>

</div>

**为什么值得关心**

与 k ≥ 4 的姊妹篇合成完整图景：一切 k ≥ 3 的方差都是 `@@M@@\Theta(n)@@`；而且全程不需要知道阈值在哪里，只围绕有限尺寸期望做文章。

> 暂无形式化证明（AI 结果待核验）

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
