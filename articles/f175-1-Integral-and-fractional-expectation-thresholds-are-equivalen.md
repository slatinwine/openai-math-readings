---
layout: default
title: "Integral and fractional expectation thresholds are equivalent"
family: "175"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Integral and fractional expectation thresholds are equivalent

> 结果族 175：Talagrand's expectation thresholds, discrete convexity, and graph decompositions　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了 Talagrand 2010 年的猜想：分数期望阈界与积分期望阈界至多相差普适常数 `@@M@@25\cdot512^4@@`，且两者使用同样的 `@@M@@1/2@@` 覆盖预算，彻底去掉了此前舍入结果中依赖集合尺寸或 `@@M@@\log\log@@` 的损失。

## 问题背景

有限集 `@@M@@X@@` 上的递增族（increasing family）`@@M@@\F@@` 称为 `@@M@@p@@`-small 的，若存在族 `@@M@@\mathcal G@@` 使每个 `@@M@@H\in\F@@` 包含某 `@@M@@S\in\mathcal G@@` 且 `@@M@@\sum_S p^{|S|}\leq1/2@@`；积分期望阈界 `@@M@@q(\F)@@` 是可行的最大 `@@M@@p@@`。Talagrand 引入的分数松弛允许把覆盖权 `@@M@@g(S)\in[0,1]@@` 分散给多个子集，只要每个成员收到的总权 `@@M@@\geq1@@`、总成本 `@@M@@\leq1/2@@`，由此得分数阈界 `@@M@@q_f(\F)@@`，并猜想两种阈界只差普适常数。此前最好结果各有残留：Dubroff–Kahn–Park 的舍入损失依赖加权集合的尺寸上界 `@@M@@t@@`，Pham 改进为 `@@M@@O(\log 2t)@@`，Park 得到 `@@M@@K\max\{1,\log\log(1/q)\}@@`——仍随 `@@M@@q\to0@@` 发散。该问题与 Kahn–Kalai 阈值猜想（Park–Pham 已证）交织，是随机离散结构阈值理论的中心课题。早期只能利用加权集合的结构逐案处理：Talagrand 本人解决了单点情形，DeMarco–Kahn 处理了团计数证书，Frankston–Kahn–Park 处理了任意二元权，Fischer 与 Person 又推广到近线性超图等多种情形。

## 主要结果

定理 1.1：对每个有限非空 `@@M@@X@@` 与每个非空真递增族 `@@M@@\F\subseteq2^X@@`，有
`@@M@@q_f(\F)\leq25\cdot512^4\,q(\F)@@`。
常数与 `@@M@@|X|@@`、`@@M@@\F@@` 最小元的尺寸、分数覆盖的支撑均无关，且结论保持覆盖预算：参数 `@@M@@r@@` 处成本至多 `@@M@@1/2@@` 的分数覆盖，可替换为参数 `@@M@@r/(25\cdot512^4)@@` 处成本至多 `@@M@@1/2@@` 的积分覆盖。推论 4.1 结合 Li 的分数离散凸性定理：若类 `@@M@@\mathcal A@@` 满足 `@@M@@\mu_p(\mathcal A)>1/2@@`，则不能含于两个成员之并的集合族在 `@@M@@p/(2C)@@` 处 small，去掉了 Park 结果中的双对数因子。

## 证明思路

核心是"多尺度选择子（selector）估计"加"期望矛盾"的舍入（rounding）。选择子定理断言：若 `@@M@@\F@@` 不是 `@@M@@p@@`-small 的，就给 `@@M@@X@@` 的元素独立染色，颜色 `@@M@@i@@` 的概率为几何递增的 `@@M@@\pi_i=D^ip@@`（`@@M@@D=256@@`），则以至少 `@@M@@9/10@@` 的概率存在单个 `@@M@@H\in\F@@` 同时在所有尺度被捕获，即对一切 `@@M@@i@@` 有 `@@M@@\lambda_H(A_i)\geq1-2^{-i}@@`，其中 `@@M@@\lambda_H@@` 是事先指定、支撑在 `@@M@@H@@` 上的概率质量。各级未捕获质量可求和，故该 `@@M@@H@@` 的平均颜色不超过 2；单尺度估计只能对不同 `@@M@@H@@` 分别成立，"同一个 `@@M@@H@@` 同时达标"正是新技术所在。

选择子定理的证明发展了 Park–Pham 的最小碎片法、Pham 的碎片塔与 Bednorz–Martynek–Meller 的极大截断（maximal truncation）：把顶点移到更早的颜色直至一组截断不等式可行，并使移动总级数最小；改变集合成覆盖，其成本与 非 `@@M@@p@@`-small 性矛盾。再按最终染色与各级间移动计数（profile）分组：profile 完全决定可行性检验，故每组有公共见证 `@@M@@H@@`；极大截断引理界住大质量顶点数 `@@M@@|R_i|\leq2^it@@`；最小性论证表明每个被移动的点必落在相应 `@@M@@R_i@@` 内，于是原始染色可被组合编码计数；加权 AM–GM 与多项式定理把坏染色概率压到 `@@M@@1/10@@` 以下。

舍入一步把分数权 `@@M@@g(S)@@` 均分给 `@@M@@S@@` 的顶点并归一化得到 `@@M@@\lambda_H@@`。选择子事件中平均颜色的加权均值不超过 2，Markov 不等式给出固定量的分数权落在"平均颜色 `@@M@@\leq4@@`"的集合上。取独立变量 `@@M@@Y_x=B^{4-a(x)}@@`（`@@M@@B=512@@`），在这些集合上 `@@M@@\prod_{x\in S}Y_x\geq1@@`，故 `@@M@@Z=\sum g(S)\prod_{x\in S}Y_x@@` 满足 `@@M@@\E Z\geq9/40@@`；另一方面各 `@@M@@Y_x@@` 的公共均值不超过 `@@M@@r/5@@`，独立性给 `@@M@@\E Z\leq1/10@@`。矛盾。关键在于最终比较只用到加权集合的非空性，其尺寸无需任何上界。

## 可信度与备注

本文主结果已由 Lean 形式化证明，是本族的枢纽：与 Li 的分数结果结合给出"两个并"的常数损失推论，离散凸性姊妹篇亦引用它，图分解篇再以上述结果为基石。按 OpenAI 官方声明，族内未经形式化的下游应用仍需以社区核验为准。

{% endraw %}
