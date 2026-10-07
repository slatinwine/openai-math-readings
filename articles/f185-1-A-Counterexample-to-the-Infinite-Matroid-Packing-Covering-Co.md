---
layout: default
title: "A Counterexample to the Infinite Matroid Packing/Covering Conjecture"
family: "185"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Counterexample to the Infinite Matroid Packing/Covering Conjecture

> 结果族 185：Counterexamples to infinite matroid intersection and packing/covering　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

在 ZFC 中构造出可数无穷集上一对自对偶的分拆拟阵 (partitional matroids)：它们既没有独立覆盖，也没有 packing/covering 划分，从而同时推翻无限拟阵 packing/covering 猜想与无限制拟阵交 (Matroid Intersection) 猜想，并否定回答 Joó 的问题。

## 问题背景

拟阵 (matroid) 把"线性无关"抽象成满足交换公理的集族；Bruhn、Diestel、Kriesell、Pendavingh、Wollan 在 2013 年的无限拟阵公理使限制、收缩与对偶 (duality) 在无穷地面集上依然成立。有限情形的经典定理——拟阵交定理与装箱/覆盖定理——能推广多远，随之成为中心问题：Nash-Williams 就有限性 (finitary) 拟阵提出交猜想；Bowler 与 Carmesin 于 2015 年提出无限制的 packing/covering 猜想，并证明它与交猜想等价联动。Joó 证明了"任一无限拟阵拼上有限个一致拟阵直和"的交定理后追问：两个分拆拟阵（一致拟阵的直和）在可数公共地面集上是否满足交？正面结果此前均依赖 finitary/cofinitary 假设，而 ZFC 中无穷秩与余秩一致拟阵的存在性本身即是公开问题，本文顺带跨越。

## 主要结果

**主定理**：ZFC 中存在可数无穷集 `@@M@@E@@` 与其上两个无限拟阵 `@@M@@M_0,M_1@@`，使 `@@M@@M_i^*=M_i@@`（同一标号地面集上），且对任意 `@@M@@M_0@@`-独立集 `@@M@@I_0@@` 与 `@@M@@M_1@@`-独立集 `@@M@@I_1@@` 均有 `@@M@@I_0\cup I_1\ne E@@`，即无独立覆盖；该对也没有 packing/covering 划分（`@@M@@E=P\dot\cup C@@` 中 `@@M@@P@@` 上放两把不交生成集 (spanning sets)、`@@M@@C@@` 被两族独立集覆盖）。故无限拟阵 packing/covering 猜想不成立。

**交推论**：同一对 `@@M@@(M_0,M_1)@@` 是分拆拟阵却不满足交——对每个双独立的 `@@M@@J@@` 与每个划分 `@@M@@J=J_0\dot\cup J_1@@`，都有 `@@M@@\cl_{M_0}(J_0)\cup\cl_{M_1}(J_1)\ne E@@`。于是无限制交猜想为假，Joó 的问题被否定回答。

**附带收获**：局部构造给出 ZFC 中的可数自对偶一致 (uniform) 拟阵 `@@M@@Q@@`，每个基及其补皆无穷，肯定回答上述存在性问题；`@@M@@M_0,M_1@@` 既非 finitary 亦非 cofinitary，且无非空的此类直和项，故 Nash-Williams 的原始 finitary 猜想不受影响。

## 证明思路

**自对偶归约**：对自对偶对排除独立覆盖即可。由 `@@M@@M_i.C=(M_i\upharpoonright C)^*@@`，混合划分中 `@@M@@P@@` 上的生成集与 `@@M@@C@@` 内独立集的补拼成两把不交生成集，其补恰为覆盖 `@@M@@E@@` 的独立集对；交的否定由 Bowler–Carmesin 等价（`@@M@@(M,N)@@` 满足交当且仅当 `@@M@@(M,N^*)@@` 有 packing/covering 划分）随自对偶性导出。

**超滤与序数秩**：把可数集 `@@M@@D@@` 切成大小 `@@M@@2^{2^m}@@` 的速增有限块；占比趋零的集成理想 `@@M@@\mathcal J@@`，独立二进制列生成更大理想 `@@M@@\mathcal K@@`，取避开 `@@M@@\mathcal K@@` 的超滤 (ultrafilter) `@@M@@\mathcal U@@`，其成员称大集。令 `@@M@@\rho(X)=\min\{\xi:F_\xi\subseteq_{\mathcal K}X\}@@`（`@@M@@(F_\xi)@@` 枚举大集），它对包含反向单调；升秩稀释引理保证小集与大集之间总有秩超过任意 `@@M@@\gamma<\mathfrak c@@` 的大集。

**类内基族**：在 `@@M@@D@@` 的两个标号拷贝 `@@M@@L,R@@` 上，以探针 `@@M@@f_n^T@@`＝前缀计数加尾部密度上下确界之和，对每个原型 `@@M@@T@@` 的类筛选：下极限规则收取 `@@M@@-1<\ell_T\le 0@@` 者，上极限规则互补。平衡有限修改恰把探针平移净基数，基交换立判；分级删除、损失可和的插值论证保证区间两端间必能造基——此即最大扩张公理 (IM) 的来源。

**全局组装**：称 `@@M@@X@@` 容许 (admissible)，若两切片同时大时 `@@M@@\rho(X_L)>\rho(D\setminus X_R)@@`、同时小时 `@@M@@\rho(D\setminus X_L)>\rho(X_R)@@`；Upper、Lower 两单调区域与容许集三分幂集。沿长度 `@@M@@\mathfrak c@@` 的递归逐一满足无限间隙区间，预留引理保持新旧原型双向正差、基族成反链。验证独立集公理后得自对偶一致拟阵 `@@M@@Q@@`，每个基 `@@M@@B@@` 满足：`@@M@@B_L@@` 大时 `@@M@@D\setminus B_R@@` 亦大且 `@@M@@\rho(B_L)>\rho(D\setminus B_R)@@`。

**序数下降**：把 `@@M@@D@@` 的拷贝作为束沿整数顶点铺成双向无穷路 (double ray)，每顶点放一份 `@@M@@Q@@`（`@@M@@L@@` 坐标指向中央束），偶、奇顶点直和成 `@@M@@M_0,M_1@@`。反设独立覆盖存在，改为划分 `@@M@@E=J_0\dot\cup J_1@@`；中央束恰有一端分得大标签集，自该端向外递推，每步把指派扩张成基，得 `@@M@@\rho(x_k)\ge\rho(u_k)>\rho(y_k)\ge\rho(x_{k+1})@@`——无穷严格递降序数列不可能，矛盾。

## 可信度与备注

本文主结果已有 Lean 形式化证明，否定性核心结论有机器验证背书。同一对例子一石三鸟：同时否定 packing/covering 猜想、交猜想与 Joó 问题，并经普适等价推出单独的 Covering、Packing 猜想也为假。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇属已形式化之列，故结论可信度较高。

{% endraw %}
