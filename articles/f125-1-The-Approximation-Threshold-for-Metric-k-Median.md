---
layout: default
title: "The approximation threshold for metric $k$-median"
family: "125"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The approximation threshold for metric \(k\)-median

> 结果族 125：The metric \(k\)-median approximation threshold and recovery　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文对带指定候选设施的有限有理度量 \(k\)-中值给出任意固定 \(\varepsilon>0\) 的确定性多项式时间 \((1+2/e+\varepsilon)\)-近似算法；结合 Max-\(k\)-Coverage 的 \(1+2/e\) 硬度，在 \(P\ne NP\) 下该模型多项式时间近似的下确界因子恰为 \(1+2/e\)，近似阈值被完全确定。

## 问题背景

度量 \(k\)-中值（metric \(k\)-median）给定客户集 \(J\)、候选设施集 \(F\) 与整数 \(k\)，要求选至多 \(k\) 个设施最小化连接费用 \(\sum_{j\in J}d(j,S)\)。三十年主线包括 LP 舍入（Charikar–Guha–Tardos–Shmoys，首个常数因子）、Lagrange 松弛与原始-对偶（Jain–Vazirani）、对偶拟合（Jain 等）以及交换局部搜索（Arya 等，\(3+\varepsilon\)）；Li–Svensson 用"常数加性伪近似可转为真近似"的约化打开缺口，bi-point 舍入推进到 2.675 与 2.613，2025 年起 CGLSS 与 Byrka 等人的迭代图舍入双双达到 \(2+\varepsilon\)。下界方面，由 Feige 的覆盖缺口可继承 \(1+2/e\) 的不可近似性。悬而未决的问题是：\(2+\varepsilon\) 与 \(1+2/e\) 之间的大片空隙能否填满？本文给出肯定回答，而且算法是确定性的。

## 主要结果

主定理：对每个固定 \(\varepsilon>0\)，存在确定性算法，在输入二元编码长度的多项式时间（次数可依赖 \(\varepsilon\)）内返回 \(S\subseteq F\)、\(|S|\le k\)，使得 \(\sum_{j\in J}d(j,S)\le(1+2/e+\varepsilon)\operatorname{OPT}_k\)。推论：若 \(P\ne NP\)，该模型确定性多项式时间近似因子的下确界（infimum）恰为 \(1+2/e\)。硬度来自 Max-\(k\)-Coverage：把宇宙元素作客户、集合作设施，同类点距离取 2、关联对取 1、非关联取 3，则所选 \(k\) 个集合覆盖 \(c\) 个元素当且仅当连接费用为 \(3m-2c\)；完美覆盖的费用是 \(m\)，而完美完备情形下至多覆盖 \(1-1/e+\delta\) 比例，于是任何多项式算法都被挡在 \(1+2/e-2\delta\) 之外。

## 证明思路

证明分三段。第一段网格准备：先解标准指派 LP（开设变量 \(y_i\) 总质量至多 \(k\)、费用至多 \(\operatorname{OPT}_k\)），把开设量吸附为 \(g=1/\Delta\) 的整数倍（偶数 \(\Delta\) 只依赖精度），总质量至多增加 \(3g\)，每个客户的期望指派费用近无损；再以分离的代表客户定义互不相交的"捆"（bundle），把每捆的亏缺（deficit）与其供应者（supplier）一并做依赖舍入（dependent rounding），既控制开设预算又控制恢复整单位指派的费用，并允许一个供应者服务多个客户——因为指派质量不是共享容量。第二段锥形迭代舍入是心脏：把每个正网格开设视为若干质量 \(g\) 的副本，每轮由有向图规定"源副本开设时擦除哪些目标副本"，每个目标恰有 \(\Delta\) 个入源，入边概率随距离线性锥形递减；开设与擦除按质量配平，只需常数个额外设施，擦除量过大的"重源"直接强制开设。费用分析对每个客户追踪其初始指派单位中幸存的副本与一个持续的距离上界，构造系数随时间衰减（参数 \(x=e^{-\xi}\)）与幸存质量变化的势函数；当客户自己的副本开设时，继续追踪更便宜的幸存者，由此产生的减项恰好支付其他擦除。核心工具是一个有限比较不等式（finite comparison inequality），其解析函数 \(A(x)=1+2\int_0^1(1-e^{-tx})\,dt\)、\(P(x)=\int_0^1te^{-tx}\,dt\)、\(m(x)=A-1-2xP\) 满足 \(A(1)=1+2/e\)——阈值常数正是从这条指数时间表自然涌现。该不等式处理一个未必对称的比较矩阵：正行的贡献只允许向 \(D\) 值更小的列"转账"，数值上正行满足 \(D>0.4\) 而收款行满足 \(D<0.394\)，两类严格分离，接收行的负贡献逐行覆盖全部进账。重源的强制开设依赖实现图，证明先对每个实现图界定势变化、再对图取平均，避免对图依赖事件做条件化。舍入定理最终给出每个客户 \(\E d(j,O)\le(1+2/e+\tau)V_{j,0}\) 且 \(|O|\le M+C\)。第三段去随机化并回收预算：所有界只依赖各局部选择的指定低阶矩，故可构造保持这些矩的多项式规模有理分布（Carathéodory 型支撑缩减），对常数轮展开全部物理历史并取满足加性预算的最便宜输出，得到开至多 \(k+c\) 设施的确定性近似；最后用 Li–Svensson 约化以任意小的附加损失去掉常数剩余 \(c\)。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准；论文把关键标量不等式的每条估计都配了显式的有理多项式证书（附录），这部分可机器复核。姊妹篇《Single-exponential recovery and bounded-price strictness》在同一模型上独立给出随机的 \((2-\sigma)\)-近似且主结果已 Lean 形式化，两篇证明路线独立、互为印证。按 OpenAI 官方声明，未经形式化的结果可能有问题，本文的去随机化与有理算术细节尤待同行仔细核验。

{% endraw %}
