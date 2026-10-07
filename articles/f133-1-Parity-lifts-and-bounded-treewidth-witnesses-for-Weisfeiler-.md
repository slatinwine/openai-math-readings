---
layout: default
title: "Parity lifts and bounded-treewidth witnesses for Weisfeiler–Leman equivalence"
family: "133"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Parity lifts and bounded-treewidth witnesses for Weisfeiler–Leman equivalence

> 结果族 133：The computational complexity of Weisfeiler–Leman refinement　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
对每个固定 `@@M@@k\ge 4@@`，本文构造两张无色简单图，使 `@@M@@k@@` 维 Weisfeiler–Leman 等价当且仅当一个给定的有限域"选择系统"没有兼容选择；结合稀疏化，在正率 ETH 下推出判定 `@@M@@k@@`-WL 等价没有 `@@M@@O(n^{ck})@@` 时间的确定性算法，且难度在两轮迭代之内已经出现。

## 问题背景
Weisfeiler–Leman 细化（Weisfeiler–Leman refinement）源于 1968 年 Weisfeiler 与 Leman 关于图规范化（graph canonization）的工作：对顶点组反复重着色来比较图。维数 `@@M@@k@@` 固定时直接实现耗时 `@@M@@n^{O(k)}@@`，自然的问题是：这个随 `@@M@@k@@` 增长的指数能否被完全不同的算法避开？此前 Grohe、Lichter、Neuen、Schweitzer 的压缩 CFI 构造证明某些图对需要 `@@M@@\Omega(n^{k/2})@@` 轮细化，但那约束的是细化过程本身，并不排除用其他方法快速判定最终的等价关系；Lichter、Raßmann、Schweitzer 猜想等价判定没有 `@@M@@n^{o(k)}@@` 时间算法，并建议基于 ETH 证明。本文实现了这一条件性下界，而且把它推进到"两轮直方图"这么早的阶段。

## 主要结果
论文先定义选择系统（choice system）：有限域 `@@M@@D_1,\dots,D_t@@`，每对 `@@M@@i<j@@` 附标签集 `@@M@@L_{ij}@@` 与映射 `@@M@@\lambda_{ij}^i:D_i\to L_{ij}@@`、`@@M@@\lambda_{ij}^j:D_j\to L_{ij}@@`；成功选择（successful choice）是使每对标签一致的 `@@M@@(d_1,\dots,d_t)\in\prod_i D_i@@`。奇偶归约定理：取 `@@M@@t=k+1@@`（joint 约定）或 `@@M@@t=k@@`（separate 约定），可从任意选择系统显式构造同阶无色简单图 `@@M@@X_0,X_\star@@`，使
`@@M@@DX_0\equiv_k X_\star\iff\text{选择系统没有成功选择}，@@`
且当成功选择存在时，两张图在 joint 两轮或 separate 一轮后直方图即不同。ETH 推论定理：在正率指数时间假设（positive exponential-rate ETH）下，存在常数 `@@M@@c>0@@` 与 `@@M@@K\ge 4@@`，使每个固定 `@@M@@k\ge K@@` 都没有判定两张 `@@M@@n@@` 顶点图 `@@M@@k@@`-WL 等价的 `@@M@@O(n^{ck})@@` 时间确定性算法（多带图灵机模型），即使只要求比较两轮（或一轮）后的直方图也一样；在更弱的"无非一致 `@@M@@2^{o(N)}@@` 的 3-SAT 算法"假设下，还有算法以 `@@M@@k@@` 为输入的统一版本。

## 证明思路
构造分三层。第一层是模板（template）`@@M@@T_t@@`：`@@M@@t@@` 个主顶点构成团，每对 `@@M@@i<j@@` 与每个第三主顶点 `@@M@@\ell@@` 配一个邻接于 `@@M@@i,j,\ell@@` 的辅助顶点（helper）；基图 `@@M@@G@@` 把主类型换成域 `@@M@@D_i@@`、辅助类型换成标签拷贝，边恰好编码"标签一致"。第二层是奇偶提升（parity lift，近承 Roberson 的奇偶图构造）：`@@M@@X_b@@` 的顶点为 `@@M@@(u,z)@@`，`@@M@@z@@` 是以模板邻居类型为下标的 `@@M@@\mathbb F_2@@` 比特向量，其总和的奇偶性规定为 `@@M@@b(\tau(u))@@`；相邻要求两向量在互相面对的坐标上相等。`@@M@@X_0@@` 与 `@@M@@X_\star=X_{e_1}@@` 只在主类型 `@@M@@1@@` 的奇偶上不同。第三层是同态计数接口（Dvořák；Dell–Grohe–Rattan）：若所有 bag 大小至多 `@@M@@t@@`（即树宽至多 `@@M@@t-1@@`）的源图 `@@M@@F@@` 都满足 `@@M@@\hom(F,X_0)=\hom(F,X_\star)@@`，则两图 `@@M@@k@@`-WL 等价；而模板 `@@M@@T_t@@` 的计数在 joint 第二轮或 separate 第一轮直方图中已被确定。
正方向先做线性代数：固定投影 `@@M@@\phi:F\to G@@` 后，提升到 `@@M@@X_0@@` 的同态是某二元线性系统的解核，提升到 `@@M@@X_\star@@` 者或为空或为核的平移，故 `@@M@@\hom(F,X_0)\ge\hom(F,X_\star)@@`，且严格不等当且仅当存在满足一组对偶恒等式的顶点权 `@@M@@s@@` 与边权 `@@M@@r@@`（`@@M@@\mathbb F_2@@` 上）。成功选择把模板映入所选顶点、所有权取一，立即得到严格不等。
反方向是难点：设某个小 bag 的 `@@M@@F@@` 产生差异，对偶权把树分解的每条树边朝"权质量为 1"的一侧定向，汇点 bag 必含每个主类型恰一个代表；再利用 helper 的耦合结构做全局失配检验：若某对代表标签不合，所构造的谓词在整个图上取值 1，却在 bag 与所有外侧同时为零，矛盾。于是代表两两兼容，提取出成功选择。
最后做复杂度：用稀疏化引理把 3-CNF 化为至多 `@@M@@2^{\epsilon N}@@` 个 `@@M@@O(N)@@` 子句的析取，把子句均分 `@@M@@t@@` 组得到域大小 `@@M@@2^{O(N/t)}@@` 的选择系统，输出图阶 `@@M@@n\le b_k 2^{6CN/t}@@`；若 `@@M@@k@@`-WL 有 `@@M@@O(n^{ck})@@` 算法，取 `@@M@@c=\delta/(24Cq)@@` 便得到 `@@M@@2^{\delta N/2}@@` 时间的 3-SAT 算法，与 ETH 矛盾。

## 可信度与备注
本文结果未经形式化验证，请以社区核验为准。同族姊妹篇《Unconditional time lower bounds for Weisfeiler–Leman equivalence》证明了更强的无条件 `@@M@@n^{\Omega(k)}@@` 下界，就稳定等价而言取代本文的条件性定理；但作者强调本文的显式选择归约与基于 helper 的有界 bag 提取自成一体，其证明不使用姊妹篇定理。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
