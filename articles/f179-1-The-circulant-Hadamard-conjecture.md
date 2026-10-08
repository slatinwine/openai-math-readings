---
layout: default
title: "The circulant Hadamard conjecture"
family: "179"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The circulant Hadamard conjecture

> 结果族 179：The circulant Hadamard and Barker-sequence conjectures　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

一支仪仗队方阵，每人举 +1 或 −1 的牌子，要求任意两行牌子"对齐一半、错开一半"（数学上叫正交）。如果每一行都只是第一行整体向右挪一格（循环移位），这种方阵能有多大？答案悬置了六十多年，这篇论文给出终审：只有 1×1 和 4×4 两种，别无分店。此前最强的计算证据已把 4×10³⁰ 以内的候选阶排除到只剩 4489 个，但完整证明始终缺位，本文补上了最后一环。

**关键词卡片**

- Hadamard 矩阵（Hadamard matrix）：元素全为 ±1 且行两两正交的方阵，满足 `@@M@@HH^{\mathsf T}=nI@@`。
- 循环矩阵（circulant matrix）：每行都由上一行循环移位一格得到。
- 周期自相关（periodic autocorrelation）：序列与自身错位相乘再求和；正交等价于一切非零移位处取零。
- Barker 序列（Barker sequence）：非周期自相关绝对值不超过 1 的 ±1 序列，雷达理想波形的数学化身。

**看个具体例子**

唯一的非平凡例子是 4 阶：首行 `@@M@@(1,1,1,-1)@@`，其余各行依次右移一格。下图黑格记 +1、白格记 −1，白格恰好排成一条反对角线；可直接验证 `@@M@@P_h(t)=0@@` 对一切 `@@M@@1\le t<4@@` 成立：两行正交意味着同号位置恰好占一半，比如错位一格相乘得 `@@M@@-1、+1、+1、-1@@`，正负相抵总和为零。主定理断言 n=1、4 之外再无可能，并顺带证明 Barker 序列只在长度 2, 3, 4, 5, 7, 11, 13 存在。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="280" y="34" fill="#555" font-size="14" text-anchor="middle">首行 (1, 1, 1, -1)，每行右移一格</text>
<rect x="188" y="50" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="230" y="50" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="272" y="50" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="314" y="50" width="42" height="42" fill="#fff" stroke="#333" stroke-width="1.5"/>
<rect x="188" y="92" width="42" height="42" fill="#fff" stroke="#333" stroke-width="1.5"/>
<rect x="230" y="92" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="272" y="92" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="314" y="92" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="188" y="134" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="230" y="134" width="42" height="42" fill="#fff" stroke="#333" stroke-width="1.5"/>
<rect x="272" y="134" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="314" y="134" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="188" y="176" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="230" y="176" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<rect x="272" y="176" width="42" height="42" fill="#fff" stroke="#333" stroke-width="1.5"/>
<rect x="314" y="176" width="42" height="42" fill="#333" stroke="#333" stroke-width="1.5"/>
<text x="280" y="246" fill="#555" font-size="13" text-anchor="middle">黑 = +1，白 = -1：白格恰排成一条反对角线</text>
<text x="280" y="268" fill="#555" font-size="13" text-anchor="middle">任意两行正交：P_h(t) = 0（1 ≤ t < 4）</text>
</svg>

</div>

**为什么值得关心**

一篇论文同时终结两个六十余年的名题（循环 Hadamard 猜想与 Barker 序列猜想），且证明经机器核验，含金量极高。

> 已 Lean 形式化

## 一句话结论

本文证明了循环 Hadamard 矩阵猜想：实循环 Hadamard 矩阵（circulant Hadamard matrix）的阶只能是 `@@M@@1@@` 或 `@@M@@4@@`；并顺势证明 Barker 序列猜想——长度大于 `@@M@@1@@` 的 Barker 序列恰在 `@@M@@2,3,4,5,7,11,13@@` 七个长度存在，一举终结两个悬置六十余年的组合难题。

## 问题背景

Hadamard 矩阵（Hadamard matrix）是元素全为 `@@M@@\pm1@@` 且行两两正交的方阵，即满足 `@@M@@HH^{\mathsf T}=nI_n@@`；若每行都是首行的循环移位，则称为循环 Hadamard 矩阵。这一猜想传统上归于 Ryser（1963 年前后）：这种矩阵的阶只能是 `@@M@@1@@` 和 `@@M@@4@@`。它之所以重要，是因为与循环差集（cyclic difference set）和 Barker 序列（Barker sequence）深刻等价——后者源自雷达与通信理论中理想脉冲压缩序列的设计，而长度大于 `@@M@@2@@` 的偶长 Barker 序列经循环移位恰好构成循环 Hadamard 矩阵。此前最强进展包括 Turyn 1965 年的分圆特征和方法（证明大阶必为 `@@M@@4u^2@@`、`@@M@@u@@` 为奇的非素数幂）、Schmidt 的域下降（field descent）与 Leung–Schmidt 的群环分解，以及 Logan–Mossinghoff 2017 年的大规模计算——把 `@@M@@4\cdot 10^{30}@@` 以内的候选阶排除到只剩 `@@M@@4489@@` 个。完整证明始终缺位，本文补上了最后一环。

## 主要结果

**主定理**：`@@M@@n@@` 阶实循环 Hadamard 矩阵存在当且仅当 `@@M@@n\in\{1,4\}@@`。四阶例子的首行是 `@@M@@(1,1,1,-1)@@`：记周期自相关（periodic autocorrelation）`@@M@@P_h(t)=\sum_{j=0}^{n-1}h_jh_{j+t\bmod n}@@`，Hadamard 条件恰等价于 `@@M@@P_h(t)=0@@` 对一切 `@@M@@1\le t<n@@` 成立，而该行满足此条件。

**推论（Barker 序列长度分类）**：对 `@@M@@n>1@@`，Barker 序列——即非平凡非周期自相关（aperiodic autocorrelation）`@@M@@C_a(t)=\sum_{j=0}^{n-t-1}a_ja_{j+t}@@` 满足 `@@M@@|C_a(t)|\le 1@@` 的 `@@M@@\pm1@@` 序列——存在当且仅当 `@@M@@n\in\{2,3,4,5,7,11,13\}@@`。奇数长度部分是 Turyn–Storer（1961）与 Schmidt–Willms 的经典结论（论文直接引用后者得到精确列表）；偶数长度 `@@M@@n>2@@` 时，Barker 不等式经奇偶性论证逼出所有非平凡周期自相关为零，循环移位便构成循环 Hadamard 矩阵，于是被主定理压到 `@@M@@n=4@@`。

## 证明思路

全文按"先压阶数、再造交错积、最后模 `@@M@@2@@` 出矛盾"三步推进。

先在素数 `@@M@@2@@` 上下降。把首行写成群环（group ring）元素 `@@M@@h=\sum_jh_jX^j\in\Z[C_n]@@`，正交性等价于范数恒等式 `@@M@@hh^*=n@@`；增广逼出 `@@M@@n=h(1)^2@@` 是平方数，行间内积为零又逼出 `@@M@@n@@` 为偶数，故 `@@M@@n=2^{2s}u^2@@`。要证 `@@M@@s=1@@`，先把 `@@M@@h@@` 投影到 2-准素分量，得到系数全为奇数的 `@@M@@T@@`，满足 `@@M@@TT^*=2^{2s}u^2@@`。核心工具是一条分圆可除性引理：在合适的局部化（localization）中，本原 `@@M@@2^k@@` 次根处的特征值的赋值（valuation）等价于其分圆余式各系数的公共整除性。据此每做一次"群阶折半、范数除以 `@@M@@4@@`"的下降，新元素系数仍全为奇数；`@@M@@s-1@@` 步后得到 `@@M@@2^{s+1}@@` 个奇数系数，其平方和等于 `@@M@@4u^2@@`。但奇数平方模 `@@M@@8@@` 余 `@@M@@1@@`，`@@M@@s\ge2@@` 时个数 `@@M@@2^{s+1}@@` 被 `@@M@@8@@` 整除，平方和应模 `@@M@@8@@` 余 `@@M@@0@@`，而 `@@M@@4u^2@@` 模 `@@M@@8@@` 余 `@@M@@4@@`——矛盾。故 `@@M@@n=4u^2@@`、`@@M@@u@@` 奇，这正是 Turyn 下降的群环化简写。

再构造交错特征积。设 `@@M@@u>1@@`，`@@M@@P=C_{u^2}@@`，`@@M@@I@@` 为 `@@M@@u@@` 的素因子集。对每个 `@@M@@p\in I@@` 固定本原 `@@M@@p@@` 次单位根 `@@M@@\rho_p@@`，对子集 `@@M@@S\subseteq I@@` 令 `@@M@@x_S@@` 为相应特征下的取值，定义交错积 `@@M@@\Delta(x)=\prod_Sx_S^{(-1)^{|S|}}@@`。范数 `@@M@@xx^*=u^2@@` 保证 `@@M@@|x_S|=u@@`。关键的比较引理（又一场"投影、除以 `@@M@@p@@`"的归纳下降）表明：因标量 `@@M@@u^2@@` 中 `@@M@@p@@` 的赋值恰与 `@@M@@p@@`-分量的阶指数吻合，相邻比值 `@@M@@x_{S\cup\{p\}}/x_S@@` 在含 `@@M@@p@@` 的每个极大理想（maximal ideal）处是剩余（residue）为 `@@M@@1@@` 的单位；按 `@@M@@p@@` 方向配对所有因子，便知 `@@M@@\Delta(x)@@` 在这些素理想处剩余 `@@M@@1@@`，在其余素理想处范数保证整性。交错指数总和为零使它在每个复嵌入下绝对值为 `@@M@@1@@`，由 Kronecker 判据（Kronecker's criterion）它是单位根（root of unity），而剩余 `@@M@@1@@` 又把它的阶逼成 `@@M@@p@@` 的幂——总之是奇数阶。

最后模 `@@M@@2@@` 出矛盾。分解 `@@M@@C_{4u^2}=C_4\times P@@`，取三个归一化部分赋值 `@@M@@c=\tfrac12h|_{Z=1}@@`、`@@M@@d=\tfrac12h|_{Z=-1}@@`、`@@M@@g=\tfrac12h|_{Z=i}@@`；共同的符号系数保证 `@@M@@c,d@@` 整属于 `@@M@@\Z[P]@@`、`@@M@@g@@` 整属于 `@@M@@\Z[i][P]@@`，且范数均为 `@@M@@u^2@@`，故 `@@M@@R=\Delta(d)/\Delta(c)@@`、`@@M@@W=\Delta(g)/\Delta(c)@@` 是奇数阶单位根。在含 `@@M@@2@@` 的极大理想处局部化：奇范数使各 `@@M@@c_S@@` 为单位，特征 `@@M@@2@@` 下 `@@M@@i\equiv1@@`。符号结构给出差式 `@@M@@d-c@@` 含因子 `@@M@@2@@`、`@@M@@g-c@@` 含因子 `@@M@@1+i@@`（关键恒等式 `@@M@@H_2+iH_3=(1+i)J+2U@@`，其中 `@@M@@J=\sum_{z\in P}z@@`），故比值 `@@M@@d_S/c_S\in1+2O@@`、`@@M@@g_S/c_S\in1+(1+i)O@@`，剩余均为 `@@M@@1@@`；奇数阶在剩余特征 `@@M@@2@@` 处逼出 `@@M@@R=W=1@@`。一阶项映射 `@@M@@\lambda_t(1+tL)=L\bmod\mathfrak n@@` 把乘法群同态到加法群，对两个等于 `@@M@@1@@` 的交错积展开并相加，公共的 `@@M@@b_S@@` 项恰好相消，只剩 `@@M@@\sum_S(-1)^{|S|}J_S/c_S\equiv0@@`。但每个非平凡特征都消灭 `@@M@@J_S@@`，交错和里仅剩 `@@M@@S=\varnothing@@` 一项 `@@M@@u^2/c_\varnothing@@`——它是个单位，剩余非零，矛盾。故 `@@M@@u>1@@` 不可能，猜想得证。

## 可信度与备注

本文主结果已完成 Lean 形式化证明，可信度属于最高档；按 OpenAI 官方声明，未经形式化的结果可能有问题，而主定理与 Barker 推论均在形式化覆盖之内。族内逻辑上，本篇与 Turyn–Storer、Schmidt–Willms 的经典奇长度分类互相拼合，才合成完整的 Barker 长度列表。值得留意的是，作者在引言中明确列出了多份此前声称完整证明该猜想的文献——这一领域的历史教训恰恰凸显了形式化验证的价值。

{% endraw %}
