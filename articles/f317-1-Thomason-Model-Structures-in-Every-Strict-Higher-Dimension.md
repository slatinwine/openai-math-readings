---
layout: default
title: "Thomason Model Structures in Every Strict Higher Dimension"
family: "317"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Thomason Model Structures in Every Strict Higher Dimension

> 结果族 317：Thomason model structures in all strict higher dimensions　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明 Ara–Maltsiniotis 高维 Thomason 猜想：对每个 `@@M@@1\le n\le\infty@@`，小严格球状（globular）`@@M@@n@@`-范畴上存在真（proper）的组合式模型结构，弱等价由 Street 神经检测，并与单纯集 Quillen 等价——严格高阶范畴在一切维度都实现空间的同伦理论。

## 问题背景

1980 年 Thomason 证明小范畴（`@@M@@n=1@@`）经神经函子承载空间的同伦理论；Street 的 oriental 随后把神经推广到严格高阶范畴。Ara–Maltsiniotis 2014 年建立抽象转移定理并完成 `@@M@@n=2@@`（更早的二维构造提案有缺口，2016 年勘误）。转移框架把一般维度的猜想归结为两个充分条件：偏序集神经上的单位比较（已由 Ara–Maltsiniotis 2015 与 Gagna 2018 解决），以及特定偏序集等价在任意范畴推出下的保持性（Scholie 5.14 条件 (d`@@M@@'@@`)）。后者须真正控制范畴层面的推出，且小对象论证允许把生成胞腔附着到任意目标（不必自由生成、不必余纤维），这是卡住多年的最后一步；Ara 2023 与 Guetta–Maltsiniotis 2024 都明确记录了该猜想。

## 主要结果

主定理（Theorem 1.1）：对 `@@M@@n=\infty@@` 取 `@@M@@\nCat=\omCat@@`。Street 神经 `@@M@@N_n@@` 由 `@@M@@(N_nX)_m=\Hom_{\omCat}(\mathcal O_m,X)@@` 定义（`@@M@@\mathcal O_m@@` 为第 `@@M@@m@@` 个 oriental），`@@M@@c_n\dashv N_n@@`；记 `@@M@@U_E=c_nN E@@`（`@@M@@N@@` 为普通神经）、`@@M@@L_n=c_n\Sd^2@@`、`@@M@@R_n=\Ex^2N_n@@`。规定 `@@M@@W_n=N_n^{-1}(W_{\mathrm{KQ}})@@`、`@@M@@F_n=R_n^{-1}(\mathrm{Fib}_{\mathrm{KQ}})@@`、`@@M@@C_n={}^{\perp}(F_n\cap W_n)@@`，则对每个 `@@M@@n\in\{1,2,\ldots\}\cup\{\infty\}@@`，`@@M@@(C_n,W_n,F_n)@@` 是 `@@M@@\nCat@@` 上真且组合式（combinatorial）的模型结构，由 `@@M@@(L_nI,L_nJ)@@`（边界与角包含的二次细分像）余生成，且 `@@M@@L_n\dashv R_n@@` 是到 Kan–Quillen 单纯集的 Quillen 等价。关键中间结果是余泛性（couniversality）定理：若偏序集间的筛（sieve，即下闭全子偏序集）含入 `@@M@@A\hookrightarrow E@@` 具有右伴随收缩（right adjoint retraction），则对任意附着 `@@M@@U_A\to X@@`，推出 `@@M@@X\to X\amalg_{U_A}U_E@@` 都是 Thomason 等价（Street 神经为弱同伦等价）——恰补上 Ara–Maltsiniotis 框架缺失的条件 (d`@@M@@'@@`)。

## 证明思路

证明的核心是"驻定柱"（stationary cylinder）。设 `@@M@@f,g:E\to E@@` 单调、`@@M@@f\le g@@`、在筛 `@@M@@A@@` 上相等、且 `@@M@@g@@` 在 `@@M@@E\setminus A@@` 上常值，则在链层面定义正映射 `@@M@@[w_0,\ldots,w_p]\otimes u\mapsto[fw_0,\ldots,fw_p,gw_p]@@`；经 Steiner 的增广有向复形（augmented directed complex）理论——`@@M@@\nu@@` 函子把强 Steiner 复形送到由原子自由生成的严格 `@@M@@\omega@@`-范畴——以及 Gray 张量积比较 `@@M@@\nu K\otimes\nu L\cong\nu(K\otimes L)@@`，得到严格函子 `@@M@@P_{f,g}:U_E\otimes D_1\to U_E@@`，它在整个旧部分 `@@M@@U_A@@` 上沿区间方向恒定，此即"驻定"。再借助右内 Hom `@@M@@H(Y)@@`（`@@M@@Y@@` 为 `@@M@@n@@`-范畴时它仍是 `@@M@@n@@`-范畴），把柱转置为 `@@M@@B\to H(Y)@@`，从而沿任意附着把柱粘合到整个推出上；Alexander–Whitney 对角进而把严格柱转化为 Street 神经上的单纯同伦。证明余泛性时，先处理 `@@M@@E\setminus A@@` 有最大元的情形：恒等 `@@M@@\id_E@@` 与压缩 `@@M@@k@@` 未必逐点可比，但都位于公共常值映射 `@@M@@g@@` 之下，两条棱柱拼出 `@@M@@\id_Y\to G\leftarrow jp@@` 的锯齿形同伦，与收缩 `@@M@@p:Y\to X@@` 相配即得 `@@M@@j@@` 是 Thomason 等价。一般有限偏序集删去两个不同极大元，得到覆盖 `@@M@@E@@` 的两个筛，相应的附着推出是全筛子范畴、其交恰为公共子偏序集的推出，于是神经沿单射组成单纯形推出，用"单腿粘合引理"归纳粘合弱等价——各局部的收缩无需彼此相容。任意偏序集再用滤过余极限（稳定于 `@@M@@q=ir@@` 的有限子集）化归到有限情形。最后，二次细分把每个生成边界或角包含识别为偏序集神经含入 `@@M@@NA\hookrightarrow NB@@`（`@@M@@A@@` 为筛，上闭包的收缩为 `@@M@@r(\sigma)=\sigma\cap P_K@@`），仿照 Thomason 的 Dwyer 映射分解得到附着比较命题：神经的推出逼近推出的神经。由此得角附着非循环（acyclic）、边界附着不变，经小对象论证与超限归纳凑齐模型公理与左右真性；单位比较沿单纯形的胞腔分解归纳，最终给出 Quillen 等价。

## 可信度与备注

本文是 OpenAI 发布的手稿，主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。作者声明不使用 Steiner 2004 中证明未完成的定理 7.3，改用 Ara–Maltsiniotis 2020 已完成的扩张定理，并注明附录 B（方法语境）并非证明输入。作为结果族 317 的代表篇目，本文补上转移框架仅剩的推出条件，与既有的偏序集单位条件（Ara–Maltsiniotis 2015、Gagna 2018）拼合成完整猜想；族内姊妹文献可提供独立的交叉核验。

{% endraw %}
