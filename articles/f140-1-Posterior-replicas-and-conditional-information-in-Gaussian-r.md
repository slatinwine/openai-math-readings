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

## 一句话结论

本文用"后验副本"（posterior replicas）耦合证明：一整块精确高斯观测在向分析师披露一条独立侧投影后只剩 \(O(H(W)/d+d+\log(2+\log L))\) 条件信息，进而导出 \(o(d^2)\) 比特流式学习者需 \(\Omega(d\log(1/\epsilon))\) 个无噪样本。

## 问题背景

无噪高斯回归的内存–样本权衡，除了"倒推成功概率"路线外，还有一条更信息论的表述：从一块精确观测算出的有限值消息（message）\(W\) 到底能保留多少关于信号的互信息（mutual information）？答案不能只靠样本数控制——若先前消息已把信号浓缩进小区域，后续消息会利用这种浓缩，因此先验分布的"几何铺开性"必须进入估计。Steinhardt–Duchi、Raz 与 Sharan–Sidford–Valiant（SSV）处理过带噪或离散情形；SSV 在微噪模型中得到 \(\Omega(d\log r)\)，但其 \(\Omega(d\log\log(1/\epsilon))\) 精度推论限制在极小精度区间。精确标签、亚二次内存下的单对数精度代价 \(\Omega(d\log(1/\epsilon))\) 仍缺一条纯信息论证明。技术难点在于：精确观测的后验支在低维"等标签纤维"（equal-label fiber）上，常规密度方法失效。本文与两篇姊妹篇（同族的《Memory and precision…》及《Replacing Gaussian observations…》）互补分工。

## 主要结果

主定理（高斯副本块估计）说：设先验 \(p=f\sigma_d\) 的密度 \(f\le L\) 有界，\(A\) 是 \(k\asymp d\) 行标准高斯矩阵，从数据 \((A,AS)\) 产生有限值消息 \(W\)；再独立抽取 \(B\)（\(\asymp d\) 行）并向分析师披露投影 \((B,BS)\)，则 \(I(S;W\mid B,BS)\le H(W)/t+Cd+C\log(2+\log L)\)，其中 \(t\asymp d\)。消息熵代价被 \(\Theta(d)\) 摊薄；对 \(L\) 只有双对数依赖——这点至关重要，因为条件化在一个概率为 \(p_v\) 的稀有状态上会得到高达 \(1/p_v\) 的密度界。流式推论：状态数 \(M(d)=o(d^2)\)、确定性停止时限的学习者，在球面均匀先验下以 \(\ge 2/3\) 概率达到角度误差 \(\epsilon\le1/10\)，则必有 \(T\ge c\,d\log(1/\epsilon)\)，\(c\) 为绝对常数。论文另外发展了四条块比较路线（距离箱、Haar 框架、合成高斯、Stiefel 关联），各自独立支撑流式迭代。

## 证明思路

证明有两根支柱。第一根是副本信息不等式：给定数据 \((A,AS)\)，从后验独立抽取 \(S_1,\ldots,S_t\)，且给定数据后与 \(W\) 独立——由 Nishimori 恒等式（Nishimori identity），每一对 \((S_i,W)\) 都保持原来的信号–消息联合 law，但忘掉数据后副本彼此依赖（共享标签 \(AS_i\)）。记 \(K\) 为副本间的总相关性（total correlation，Watanabe），\(K'\) 为经独立矩阵 \(B\) 投影后仍可见的相关性；链式法则的精确整理给出 \(tI(S;W\mid B,BS)\le H(W)+K-K'\)，因此核心是控制"相关性损失"\(K-K'\)，单边上界 \(K\) 会丢掉分析师仍能看见的几何依赖。第二根支柱是精确的等标签测度：论文证明一个有限测度恒等式——"先选矩阵与公共标签（按密度 \(p_A^t\) 加权），再在纤维上取独立点"与"先取独立信号、再取零化其差矩阵 \(D\) 的高斯行"两种描述，相差权重 \((2\pi)^{-km/2}J^{-k}\)，其中 \(J=\det(D^{\mathsf T}D)^{1/2}\) 是各点到前驱仿射张成的逐次距离之积（单纯体积）。由此得副本似然的显式公式，其分母 \(p_A^{m}\) 与逆体积因子 \(J^{-k}\) 的对数可积性由卡方分解与管道估计（tube estimate）保证，并给出总相关上界。最后对剩余投影密度比做二进分解，用投影副本的可观测检验配出匹配的逆体积项，几何项相消后只剩 \(O(d)\)。流式证明则条件在当前状态上逐块套用该估计并对状态取平均：独立投影留下一个维度 \(\asymp d\) 的剩余球面，在其上精确恢复仍需 \(\Omega(d\log(1/\epsilon))\) 条件信息，逐块累加即得样本下界。

## 可信度与备注

据任务文件，本文主结果已有 Lean 形式化证明。它与同族《Memory and precision…》（倒推路线）以完全不同的技术证明同一下界，互为印证；其等标签测度定理（Theorem 3.3）还被姊妹篇《Localization costs…》直接引用为解析输入。按 OpenAI 官方声明，未经形式化的结果可能有问题，读者应以形式化主定理为准。

{% endraw %}
