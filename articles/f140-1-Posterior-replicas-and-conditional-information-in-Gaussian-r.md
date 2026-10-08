---
layout: default
title: "Posterior replicas and conditional information in Gaussian regression"
family: "140"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Posterior replicas and conditional information in Gaussian regression

> 结果族 140：Memory–sample lower bounds for noiseless Gaussian regression　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

还是猜方向的游戏，这次换"信息账本"来审：一整块 `@@M@@d@@` 条精确证词被浓缩成一页摘要后，这页摘要里究竟还剩多少关于真相的信息？论文的妙招是造"平行宇宙"——读完数据后，从自己的信念里再抽几份信号副本，然后度量这些副本之间互通了多少情报。

**关键词卡片**

- 互信息（mutual information）：一条消息里到底含有多少关于信号的信息量。
- 后验副本（posterior replicas）：读完数据后从后验信念中抽出的平行信号副本。
- 总相关性（total correlation）：副本之间"互通情报"的程度。
- 消息（message）：学习者从一块观测算出的有限比特摘要 `@@M@@W@@`。
- 条件信息（conditional information）：把一份独立侧投影公开后，摘要里剩余的信息。

**看个具体例子**

公式卡——主定理：`@@M@@I(S;W\mid B,BS)\le H(W)/t+C\,d+C\log(2+\log L)@@`，其中 `@@M@@t\asymp d@@`。代入摘要 `@@M@@H(W)=10^6@@` 比特、`@@M@@d=1000@@`：剩余条件信息 `@@M@@\lesssim 10^3+10^3@@` 比特量级——再厚的摘要也被 `@@M@@d@@` 条观测摊薄。妙处还有两处：先验密度上界 `@@M@@L@@` 只以双对数进入，条件化在极稀有状态上也不怕；侧投影是独立抽取、先于摘要公开的。逐块累加即得流式下界：`@@M@@o(d^2)@@` 比特的学习者需 `@@M@@\Omega(d\log(1/\epsilon))@@` 个无噪样本。

**为什么值得关心**

它为同一下界补上纯信息论的第二条独立路线，与"倒推"姊妹篇互相印证——同族几篇文章从互不相同的技术抵达同一结论；其等标签测度定理还被第三篇直接引用为解析输入。

> 已 Lean 形式化

## 一句话结论

本文用"后验副本"（posterior replicas）耦合证明：一整块精确高斯观测在向分析师披露一条独立侧投影后只剩 `@@M@@O(H(W)/d+d+\log(2+\log L))@@` 条件信息，进而导出 `@@M@@o(d^2)@@` 比特流式学习者需 `@@M@@\Omega(d\log(1/\epsilon))@@` 个无噪样本。

## 问题背景

无噪高斯回归的内存–样本权衡，除了"倒推成功概率"路线外，还有一条更信息论的表述：从一块精确观测算出的有限值消息（message）`@@M@@W@@` 到底能保留多少关于信号的互信息（mutual information）？答案不能只靠样本数控制——若先前消息已把信号浓缩进小区域，后续消息会利用这种浓缩，因此先验分布的"几何铺开性"必须进入估计。Steinhardt–Duchi、Raz 与 Sharan–Sidford–Valiant（SSV）处理过带噪或离散情形；SSV 在微噪模型中得到 `@@M@@\Omega(d\log r)@@`，但其 `@@M@@\Omega(d\log\log(1/\epsilon))@@` 精度推论限制在极小精度区间。精确标签、亚二次内存下的单对数精度代价 `@@M@@\Omega(d\log(1/\epsilon))@@` 仍缺一条纯信息论证明。技术难点在于：精确观测的后验支在低维"等标签纤维"（equal-label fiber）上，常规密度方法失效。本文与两篇姊妹篇（同族的《Memory and precision…》及《Replacing Gaussian observations…》）互补分工。

## 主要结果

主定理（高斯副本块估计）说：设先验 `@@M@@p=f\sigma_d@@` 的密度 `@@M@@f\le L@@` 有界，`@@M@@A@@` 是 `@@M@@k\asymp d@@` 行标准高斯矩阵，从数据 `@@M@@(A,AS)@@` 产生有限值消息 `@@M@@W@@`；再独立抽取 `@@M@@B@@`（`@@M@@\asymp d@@` 行）并向分析师披露投影 `@@M@@(B,BS)@@`，则 `@@M@@I(S;W\mid B,BS)\le H(W)/t+Cd+C\log(2+\log L)@@`，其中 `@@M@@t\asymp d@@`。消息熵代价被 `@@M@@\Theta(d)@@` 摊薄；对 `@@M@@L@@` 只有双对数依赖——这点至关重要，因为条件化在一个概率为 `@@M@@p_v@@` 的稀有状态上会得到高达 `@@M@@1/p_v@@` 的密度界。流式推论：状态数 `@@M@@M(d)=o(d^2)@@`、确定性停止时限的学习者，在球面均匀先验下以 `@@M@@\ge 2/3@@` 概率达到角度误差 `@@M@@\epsilon\le1/10@@`，则必有 `@@M@@T\ge c\,d\log(1/\epsilon)@@`，`@@M@@c@@` 为绝对常数。论文另外发展了四条块比较路线（距离箱、Haar 框架、合成高斯、Stiefel 关联），各自独立支撑流式迭代。

## 证明思路

证明有两根支柱。第一根是副本信息不等式：给定数据 `@@M@@(A,AS)@@`，从后验独立抽取 `@@M@@S_1,\ldots,S_t@@`，且给定数据后与 `@@M@@W@@` 独立——由 Nishimori 恒等式（Nishimori identity），每一对 `@@M@@(S_i,W)@@` 都保持原来的信号–消息联合 law，但忘掉数据后副本彼此依赖（共享标签 `@@M@@AS_i@@`）。记 `@@M@@K@@` 为副本间的总相关性（total correlation，Watanabe），`@@M@@K'@@` 为经独立矩阵 `@@M@@B@@` 投影后仍可见的相关性；链式法则的精确整理给出 `@@M@@tI(S;W\mid B,BS)\le H(W)+K-K'@@`，因此核心是控制"相关性损失"`@@M@@K-K'@@`，单边上界 `@@M@@K@@` 会丢掉分析师仍能看见的几何依赖。第二根支柱是精确的等标签测度：论文证明一个有限测度恒等式——"先选矩阵与公共标签（按密度 `@@M@@p_A^t@@` 加权），再在纤维上取独立点"与"先取独立信号、再取零化其差矩阵 `@@M@@D@@` 的高斯行"两种描述，相差权重 `@@M@@(2\pi)^{-km/2}J^{-k}@@`，其中 `@@M@@J=\det(D^{\mathsf T}D)^{1/2}@@` 是各点到前驱仿射张成的逐次距离之积（单纯体积）。由此得副本似然的显式公式，其分母 `@@M@@p_A^{m}@@` 与逆体积因子 `@@M@@J^{-k}@@` 的对数可积性由卡方分解与管道估计（tube estimate）保证，并给出总相关上界。最后对剩余投影密度比做二进分解，用投影副本的可观测检验配出匹配的逆体积项，几何项相消后只剩 `@@M@@O(d)@@`。流式证明则条件在当前状态上逐块套用该估计并对状态取平均：独立投影留下一个维度 `@@M@@\asymp d@@` 的剩余球面，在其上精确恢复仍需 `@@M@@\Omega(d\log(1/\epsilon))@@` 条件信息，逐块累加即得样本下界。

## 可信度与备注

据任务文件，本文主结果已有 Lean 形式化证明。它与同族《Memory and precision…》（倒推路线）以完全不同的技术证明同一下界，互为印证；其等标签测度定理（Theorem 3.3）还被姊妹篇《Localization costs…》直接引用为解析输入。按 OpenAI 官方声明，未经形式化的结果可能有问题，读者应以形式化主定理为准。

{% endraw %}
