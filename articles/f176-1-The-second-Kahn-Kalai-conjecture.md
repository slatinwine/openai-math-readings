---
layout: default
title: "The second Kahn–Kalai conjecture"
family: "176"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The second Kahn–Kalai conjecture

> 结果族 176：The second Kahn–Kalai conjecture with an edge-count bound　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了卡恩–卡莱第二猜想：任意有 \(h\ge1\) 条边、至多 \(n\) 个顶点的图 \(H\)，其在 \(G(n,p)\) 中的出现阈值不超过 \(C\,p_{\mathrm E}(n,H)(1+\log_2 h)\)，\(C\) 为普适常数——期望阈值与真实阈值只差一个依赖边数的对数因子。

## 问题背景

随机图 \(G(n,p)\) 在每对顶点间独立以概率 \(p\) 连边。经典问题是：给定目标图 \(H\)（可随 \(n\) 增长），\(p\) 多大时 \(G(n,p)\) 以恒定概率包含 \(H\) 的一份拷贝？这可追溯到 Erdős–Rényi 与 Bollobás 的经典阈值理论。显然的必要条件是每个子图 \(F\subseteq H\) 的期望拷贝数不太小；使所有子图期望拷贝数至少为 \(1/2\) 的最小密度称为图期望阈值（graph expectation threshold）\(p_{\mathrm E}(n,H)\)，以概率 \(1/2\) 包含 \(H\) 的最小密度称为包含阈值（containment threshold）\(p_{\mathrm c}(n,H)\)，恒有 \(p_{\mathrm E}\le p_{\mathrm c}\)。Kahn 与 Kalai 猜想两者只差一个对数因子（第二猜想）。对数差距确属必要：完美匹配的 \(p_{\mathrm E}=\Theta(1/n)\) 而 \(p_{\mathrm c}=\Theta(\log n/n)\)，多出的对数用于消除宿主图的孤立顶点。此前最好结果是 Dubroff–Kahn–Park 的 \(O(p_{\mathrm E}\log^3 n)\) 与 Tran 的 \(O(p_{\mathrm E}\log^2(2e(H)))\)，单对数版本仅在树和平均度不低于最大度对数的图上获证。

## 主要结果

主定理：对每个 \(n\ge2\) 及每个恰有 \(h=e(H)\ge1\) 条边、至多 \(n\) 个顶点的有限简单图 \(H\)，

\[p_{\mathrm c}(n,H)\le\min\{1,\;2048\,\mathrm e^{50}\,p_{\mathrm E}(n,H)\,(1+\log_2 h)\}.\]

由 \(h\le n^2\) 立得 \(p_{\mathrm c}(n,H)\le6144\,\mathrm e^{50}\,p_{\mathrm E}(n,H)\log_2 n\)。拷贝按普通拷贝（ordinary copy）计，不要求导出，允许所选顶点间有额外边；\(p_{\mathrm E}(n,H)\) 是使每个子图 \(F\subseteq H\) 的期望拷贝数都 \(\ge1/2\) 的最小密度。常数显式而普适，\(H\) 可随 \(n\) 变化；把基准 \(1/2\) 换成原文的 \(1\) 只差常数因子。

## 证明思路

证明分三步：先把 \(H\) 剖分成记录全部扩展历史的概率树（probability tree），再用重采样同时削减各层，最后迭代取并。

先建图层级。记 \(q=p_{\mathrm E}(n,H)\)、\(\sigma=128q\)。对非空边集 \(I\subseteq H\)，在其子图中选 \(S\) 最大化 \(R_\sigma(I,S)=\sigma^{-|S|}\Pr(S_0\subseteq\boldsymbol I)\)，\(\boldsymbol I\) 为 \(I\) 的均匀拷贝。期望约束与计数估计迫使选出的 \(S\) 满足 \(|S|<|I|/17\)，反复选取得嵌套链 \(\varnothing=H_0\subset\cdots\subset H_k=H\)。再以副本为节点建树：子节点是包含它的 \(H_i\) 副本，弧标签为新增边；沿任一路径标签两两不交，并为 \(H\) 的副本，相邻层新增边数按 16 倍递增。\(R_\sigma\) 的极大性给出 \(\Pr(J\subseteq A)\le\sigma^{|J|}\)，即每层子分布是 \(\sigma\)-spread（分散）的，此步即 Tran 的 spread-link 构造。

再做整树同削：用 Mossel–Niles-Weed–Sun–Zadik 的种植—后验重采样（planted posterior resampling），把源标签种进独立随机集 \(W\sim\mu_\rho\)，按后验概率选目标标签，保留碎片 \(T=A_b\setminus W\)。局部引理表明：在 spread 且 \(a/\rho\le\mathrm e^{-50}\) 时，碎片长度以 \(\ge1-\mathrm e^{-9m}\) 的概率减半，并附带控制 \(W\) 在目标外坐标上测度畸变的不等式。难点是同一份 \(W\) 被全树复用带来的依赖——Tran 的耦合猜想（coupling conjecture）想以此只付一次对数代价；本文绕开该猜想，改用树归约：任一子树内的标签都与进入该子树的弧标签不交，故其递归势函数只依赖 \(W\) 在该标签之外的表现，畸变不等式恰好适用。自叶向根的势函数估计证明根"变坏"概率 \(<1/4\)：单次抽取以 \(\ge3/4\) 的概率把每层容量减半，spread 至多退化 \((1-\mathrm e^{-m_j})^{-1}\) 倍。

最后迭代：每次成功后换新的独立 \(W\)，各层容量降为 \(\lfloor\ell_i/2^t\rfloor\)；因容量按几何级数增长，spread 累计退化乘积小于 \(4\)。\(s=\lfloor\log_2\ell_k\rfloor+1\) 次成功后所有容量归零，回溯可知历次抽取之并含某条完整路径的标签并，即 \(H\) 的一个副本。预设 \(4s\) 次抽取取并，密度至多 \(16\,\mathrm e^{50}\sigma(1+\log_2\ell_k)\)，成功概率 \(\ge2/3\)；代回 \(\sigma=128q\)、\(\ell_k\le h\) 即得主定理。

## 可信度与备注

主结果已提供 Lean 形式化（见结果族 176 的 Lean 文档），正文从局部重采样、树覆盖到图层级逐环给出完整证明。本文是系列工作的收官：Park–Pham 以最小片段论证解决抽象版第一猜想，Dubroff–Kahn–Park 与 Tran 逐步压缩对数损失，此处补上最后一环；文中提及的同项目"积分/分数期望阈值等价"定理是平行的姊妹结果，但作者明确声明本证明并未使用它。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，可信度较高，常数细节以论文与形式化代码为准。

{% endraw %}
