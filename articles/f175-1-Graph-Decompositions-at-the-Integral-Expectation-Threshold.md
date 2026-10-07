---
layout: default
title: "Graph Decompositions at the Integral Expectation Threshold"
family: "175"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Graph Decompositions at the Integral Expectation Threshold

> 结果族 175：Talagrand's expectation thresholds, discrete convexity, and graph decompositions　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Ascoli–He–Park–Talagrand 图分解猜想：任何图的边都可预先拆成常数多块，每块的普通包含阈界不超过原图积分期望阈界的普适常数倍，从而在"分块"意义下彻底消除了 Kahn–Kalai 型阈值比较中的对数损失。

## 问题背景

随机图 \(G(n,p)\) 中何时出现给定图 \(H\) 的拷贝？普通阈界 \(p_c(H;n)\) 是使包含概率达到 \(1/2\) 的参数，而积分期望阈界（integral expectation threshold）\(q(H;n)\) 衡量"用小集合便宜地覆盖所有包含事件"的能力，总有 \(q\leq p_c\)。Kahn 与 Kalai 在 2007 年猜想两者只差一个对数因子，Park 与 Pham 于 2024 年证明了 \(p_c(H;n)\leq Cq(H;n)\log|E(H)|\)。对数损失能否去掉？Ascoli、He、Park、Talagrand 于 2026 年提出图分解猜想：只要允许把目标图拆成不依赖随机宿主的常数块，每块的阈界就可控制在 \(O(q)\)。他们证明了有界退化度的情形，以及退化度与最大度同时受限的另一些情形，并在其论文第 8 节指出高、低度顶点之间的二部边是剩余的主要困难。

## 主要结果

定理 1.1：存在绝对整数 \(k\geq2\) 与绝对常数 \(L\geq1\)，对每个 \(n\geq2\) 与每个至多 \(n\) 个顶点的图 \(H\)，其边集有划分 \(E(H)=E(H_1)\,\dot\cup\,\cdots\,\dot\cup\,E(H_k)\)，使每块满足 \(p_c(H_i;n)\leq Lq(H;n)\)。这里 \(q(H;n)\) 是使覆盖族 \(\mathcal C\) 的成本 \(c_p(\mathcal C)=\sum_{S}p^{|S|}\leq1/2\) 的最大参数 \(p\)。要点有三：块数与常数绝对有效；划分只依赖 \(H,n\)，在采样之前确定；各块的嵌入互不相干——共享顶点不必映到同一位置。定理意味着每个固定块都在密度 \(Lq\) 处以至少 \(1/2\) 的概率出现于 \(G(n,p)\)。

## 证明思路

先取 \(r=2q\)，调用同族姊妹篇"离散凸性定理"（常数 \(K_0=2^{75}\)）的推论：对任何高概率类 \(\mathcal D\)（\(\mu_r(\mathcal D)\geq1-1/K_0\)），必有一个 \(H\) 的标号拷贝落在 \(K_0\) 个 \(\mathcal D\) 中成员的并里。把每条边指派给一个包含它的典型图，得到 \(K_0\) 份初始块，这是整个构造的骨架。初始块各自含于一个指定的典型图中，为后续传递论证保存了"源"信息。

再按退化度（degeneracy）\(d\) 分治。大退化度情形：先把度超过 \(\sqrt n\) 的顶点集逐步扩大成 \(Y\)，使外部每点在 \(Y\) 内至多 \(2d\) 个邻居且 \(|Y|\leq n^{2/3}\)，于是边被切成"Y 内、Y 外、跨切口"三部分。Y 内与 Y 外的边经退化度分裂成最大度不超过 \(n^{2/3}\)、支撑很小的块，由分层贪心匹配的直接嵌入命题处理。跨切口的二部（bipartite）边是真正的难点：固定 \(Y\) 嵌入时需为每个外部顶点找到相邻于其至多 \(s\) 个指定邻居的不同像点，Hall 准则要求对任意候选集都有足够像点，单一典型类无法保证。作者的压缩引理（compression lemma）先把任意需求族压缩成至多 \(\lceil2r^{-s}\rceil\) 个"代表需求"，再对一切小 \(Y\) 与小需求族同时做 Hoeffding 集中来定义 \(\mathcal D\)，使"源和"与"目标和"两类检验对所有测试同时成立；配合密度放大 \(r_*=1-(1-r)^{32}\)，Hall 定理给出匹配（matching），得 \(p_c\leq32r=64q\)。有界退化度情形则把图拆成森林，按深度奇偶分裂成星森林（star forest），逐块用"新鲜中心"贪心嵌入，阈界不超过 \(2Aq\)，再由单调性 \(q(J;n)\leq q(H;n)\) 即得 \(p_c\leq Lq\)。最后清点，各情形块数均不超过 \(k\)。

## 可信度与备注

本文主结果尚未形式化；其关键输入——离散凸性定理——在同族姊妹篇中已有 Lean 形式化证明，其余图分解与嵌入论证均在本文内自包含给出。按 OpenAI 官方声明"未经形式化的结果可能有问题"，读者宜以社区核验为准。

{% endraw %}
