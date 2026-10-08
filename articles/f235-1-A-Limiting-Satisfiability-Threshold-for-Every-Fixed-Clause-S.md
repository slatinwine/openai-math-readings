---
layout: default
title: "A Limiting Satisfiability Threshold for Every Fixed Clause Size"
family: "235"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Limiting Satisfiability Threshold for Every Fixed Clause Size

> 结果族 235：Limiting random SAT thresholds, sharp variance and computability　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

往一台机器里一条条塞随机"要求"（子句），起初它总能全部满足；塞到某个密度，机器突然全面崩溃。三十多年前数学家猜测：崩溃点会收敛到一个固定密度 α_k。本文证明这个"可满足性猜想"对每个 k ≥ 3 都成立——猜想的优先权属 Carenini 的并发工作，本文给出一条技术路线独立的证明。

**关键词卡片**

- 随机 k-SAT（random k-SAT）：n 个布尔变量；每条子句随机挑 k 个互异变量并各自随机加正负号。
- 阈值（threshold）α_k：子句密度低于它时渐近可满足，高于它时渐近不可满足。
- 相变（phase transition）：可满足概率随密度从 1 骤降到 0，像水结冰。
- 尖锐窗口（sharp threshold）：Friedgut 定理保证转移在 o(n) 条子句内完成。
- 集中性（concentration）：证明的核心：关键随机量围绕其期望只有微小波动。

**看个具体例子**

k = 2 时早已知道 `@@M@@\alpha_2=1@@`。对 k ≥ 3，定理保证 `@@M@@\alpha_k@@` 存在且落在 `@@M@@[a_0,\,2^k+1]@@`：例如 k = 3 时 `@@M@@\alpha_3\in(0,9)@@`——注意定理只承诺"存在"，不告诉你具体数值。证明骨架是"先集中、再锚定、最后排除漂移"：先证截断命中时间的方差只有 `@@M@@O_k(n^{1+2/k})@@`，把转移窗口压窄；再用匹配论证把中心锚定在正区间内；最后用近似超可加性排除中心随 n 漂移的可能。论文还附赠单侧逼近速率 `@@M@@\mu_s\le\alpha_k+C_k s^{-\delta_k}@@`，其中 `@@M@@\delta_k=\dfrac{k-2}{4k}@@`（k = 3 时为 1/12）。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="15">可满足概率随子句密度的相变</text>
  <line x1="60" y1="230" x2="520" y2="230" stroke="#555" stroke-width="1.5"/>
  <line x1="60" y1="60" x2="60" y2="230" stroke="#555" stroke-width="1.5"/>
  <path d="M60 90 L320 90 C350 90 355 220 385 220 L520 220" fill="none" stroke="#c62828" stroke-width="3"/>
  <line x1="360" y1="65" x2="360" y2="230" stroke="#888" stroke-dasharray="5 4"/>
  <text x="376" y="112" font-size="15">α_k</text>
  <text x="150" y="80" font-size="12">概率 ≈ 1</text>
  <text x="450" y="212" font-size="12">概率 ≈ 0</text>
  <text x="48" y="95" font-size="12">1</text>
  <text x="48" y="234" font-size="12">0</text>
  <line x1="335" y1="242" x2="385" y2="242" stroke="#333" stroke-width="1.5"/>
  <line x1="335" y1="238" x2="335" y2="246" stroke="#333" stroke-width="1.5"/>
  <line x1="385" y1="238" x2="385" y2="246" stroke="#333" stroke-width="1.5"/>
  <text x="418" y="246" font-size="11">窗口宽 o(n)</text>
  <text x="280" y="268" text-anchor="middle" font-size="13">子句密度 c（每变量摊到的子句数）</text>
</svg>

</div>

**为什么值得关心**

可满足性猜想是随机约束满足领域的中心问题；本文的集中性估计比并发结果更锋利，直接被族内另两篇方差论文拿来使用。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了固定 `@@M@@k\ge3@@` 的随机 `@@M@@k@@`-SAT 存在有限的极限阈值密度 `@@M@@\alpha_k@@`：子句密度低于它时公式渐近可满足，高于它时渐近不可满足。这一三十余年悬置的可满足性猜想的解决优先权属 Carenini，本文给出一条技术路线独立的完整证明。

## 问题背景

往 `@@M@@n@@` 个布尔变量上逐条加入随机子句（clause），问可满足概率何时从接近 `@@M@@1@@` 跌到接近 `@@M@@0@@`。Friedgut（附 Bourgain 附录）的尖锐阈值定理早已表明转移在 `@@M@@o(n)@@` 窗口内完成，但只给出一列随 `@@M@@n@@` 变化的临界密度；这列位置是否收敛到单一极限 `@@M@@\alpha_k@@`，是 Chv\'atal 与 Reed 明确提出的著名猜想。`@@M@@k=2@@` 已知 `@@M@@\alpha_2=1@@`（Chv\'atal–Reed、Goerdt 独立证明）；`@@M@@k@@` 充分大时 Ding–Sly–Sun 证明阈值存在且等于统计物理的 1RSB 预测；而所有固定的中等 `@@M@@k@@` 始终留有缺口。Gaia Carenini 于 2026 年 10 月 5 日公开的 ECCC 报告率先解决该猜想，作者在文中明确把优先权归于她；本文的价值在于给出一条不同的证明，且其集中性估计比并发结果更便于族内其他论文使用。

## 主要结果

考虑 proper `@@M@@k@@`-clause 模型：每条子句在 `@@M@@n@@` 个变量中均匀选取 `@@M@@k@@` 个互异变量，文字符号独立公平，整条子句有放回抽样；记 `@@M@@P_n(m)@@` 为前 `@@M@@m@@` 条子句的合取可满足的概率。主定理：对每个固定整数 `@@M@@k\ge3@@`，存在 `@@M@@\alpha_k\in(0,\infty)@@`，使得 `@@M@@\lim_{n\to\infty}P_n(\lfloor cn\rfloor)=1@@`（当 `@@M@@0\le c<\alpha_k@@`）、`@@M@@=0@@`（当 `@@M@@c>\alpha_k@@`）。定理不断言 `@@M@@c=\alpha_k@@` 处的概率值，也不识别 `@@M@@\alpha_k@@` 的大小；文中另说明 `@@M@@k=2@@` 时 `@@M@@\alpha_2=1@@`、`@@M@@k=1@@` 时线性尺度上阈值为 `@@M@@0@@`，与之分开。证明还附赠单侧有限尺寸信息：`@@M@@\mu_s\le\alpha_k+C_ks^{-\delta_k}@@`。

## 证明思路

骨架是"先集中、再锚定、最后排除漂移"。设 `@@M@@H_n@@` 为首个不可满足前缀的下标，截断 `@@M@@V_n=\min(H_n-1,2^{k+1}n)@@`，取中心 `@@M@@\mu_n=\mathbb E V_n/n@@`。第一步控制强制变量（forced，即可满足指派都给它同一值的变量）：删除含 `@@M@@x_n@@` 的子句并抹去其文字，得到 `@@M@@(k-1)@@`-子句；替换引理证明一条 `@@M@@(k-1)@@`-子句的杀伤力可用 `@@M@@g=O_k(n^{1/k})@@` 条普通 `@@M@@k@@`-子句以误差 `@@M@@\varepsilon=n^{-(k-1)/k}@@` 模拟，且对任意背景公式一致成立，核心是 `@@M@@q_k\ge x^{k/(k-1)}/k@@` 的幂次比较。再对前缀长度做望远镜求和，得积分型估计 `@@M@@\sum_j\mathbb E\,b(F_{n,j})/n=O_k(n^{1/k})@@`。第二步做集中性：删去第 `@@M@@i@@` 条子句而保留其余时间指标，延迟平方按 pivotal 对展开；"后一个 pivotal 时刻仍存活"要求中间每条子句都避开杀伤当前解集，给出几何衰减 `@@M@@(1-q_m)^{\ell-m}@@`；用 `@@M@@\min\{Mq,1\}\le(Mq)^{1/k}@@` 取 `@@M@@k@@` 次根接回强制比例，代入 Efron--Stein 型方差不等式得 `@@M@@\operatorname{Var}(V_n)=O_k(n^{1+2/k})@@`，Chebyshev 不等式给出次线性窗口 `@@M@@n^{1-\delta_k}@@`，其中 `@@M@@\delta_k=(k-2)/(4k)@@`。第三步锚定中心：低密度用 Hall 定理把子句匹配到互异变量给下界 `@@M@@a_0>0@@`，高密度用指派一阶矩给上界 `@@M@@2^k+1@@`。最后排除中心漂移：在允许变量重复的辅助 Poisson 模型中对两族子句均值做插值求导（Bayati–Gamarnik–Tetali 冻结变量方法的 Poisson 形式），导数符号由 `@@M@@z\mapsto z^k@@` 的凸性决定，得乘积不等式 `@@M@@s_{r+s}(c)\ge s_r(c)s_s(c)@@`；经 Poisson 细化与 proper 模型互相转移（重复子句的期望数有界）后，低侧转移界是固定正概率而高侧趋零，二者比较化为近似超可加不等式 `@@M@@x_{r+s}\ge\min\{x_r,x_s\}-4\min\{r,s\}^{-\delta}@@`；最后沿平衡二叉树自叶向根累加几何衰减的误差（Abbe–Montanari 论证的确定性形式），得 `@@M@@\mu_n@@` 收敛于某 `@@M@@\alpha_k\in[a_0,2^k+1]@@`，再由集中性把概率极限推到两侧密度。

## 可信度与备注

本文主结果暂无形式化证明，OpenAI 官方声明未经形式化的结果可能有问题，请以社区核验为准。族内姊妹篇互相支撑：本文的截断方差界与集中性技术同方差姊妹篇共享删除–pivotal 框架，而方差姊妹篇（`@@M@@k\ge4@@` 时 `@@M@@\Theta_k(n)@@`、3-SAT 时 `@@M@@\Theta(n)@@`）把本文的涨落估计磨到最优；反过来本文给出的极限位置 `@@M@@\alpha_k@@` 为她们提供了中心的语言。需注意证明只给单侧逼近率 `@@M@@\mu_s\le\alpha_k+C_ks^{-\delta_k}@@`，没有逼近 `@@M@@\alpha_k@@` 的有效双侧速度；猜想的解决优先权属 Carenini 的并发工作。

{% endraw %}
