---
layout: default
title: "Approximate counting of common bases of two matroids"
family: "114"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Approximate counting of common bases of two matroids

> 结果族 114：Approximate counting of common integer polymatroid bases　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文在独立集预言机模型下，对任意两个同秩拟阵的公共基计数给出 FPRAS，每次执行的预言机调用与比特运算均多项式有界，肯定回答了 Liu 博士论文记录的公开问题，并连带解决公共独立集的计数与采样。

## 问题背景

拟阵（matroid）是线性无关性的组合抽象：独立集族含空集、对取子封闭并满足扩充公理；基（basis）是极大独立集。独立集预言机（independence oracle）回答查询子集是否独立。Edmonds 证明拟阵交的优化问题在预言机模型下有多项式算法，计数却艰难得多：两拟阵取同，即得单拟阵基计数；在二部图边集上对两侧顶点各施加划分拟阵约束，公共基恰为完美匹配——Jerrum–Sinclair–Vigoda 的 permanent FPRAS 正好覆盖后一特例。单拟阵计数经历了 Feder–Mihail 的均衡拟阵、强 Rayleigh 分布的快速混合，直到 Anari–Liu–Oveis Gharan–Vinzant 用对数凹多项式与高维游走彻底解决。然而两个拟阵的公共基分布一般不再具有负相关性：Anari–Oveis Gharan–Vinzant 只得到 \(2^{O(r)}\) 因子近似，Cryan–Guo–Mousa 明确提出快速收敛马氏链的存在性问题，Liu 的博士论文把它记录为公开问题。本文给出肯定回答。

## 主要结果

定理 1.1：存在单一随机预言机算法，对 \([n]\) 上任意两个秩 \(r\) 拟阵 \(M_1,M_2\)（各由固定精确独立集预言机给出）与有理数 \(\varepsilon,\delta\in(0,1)\)，输出非负有理数 \(\widehat Z\) 满足
\[\mathbb P\bigl[(1-\varepsilon)Z(M_1,M_2)\le\widehat Z\le(1+\varepsilon)Z(M_1,M_2)\bigr]\ge1-\delta,\]
其中 \(Z=|\mathcal B(M_1)\cap\mathcal B(M_2)|\)；若 \(Z=0\) 恒输出零。每次执行中，预言机调用次数与其余比特运算数都被 \(n,\ell,\varepsilon^{-1},\log\delta^{-1}\) 的固定多项式界定（\(\ell\) 为 \(n,r,\varepsilon,\delta\) 的二进制编码长）。算法只用无偏随机比特，不需要任何拟阵的显式表示。推论 9.1 更进一步：两拟阵秩可以不同，指定基数、任意基数与最大基数三种公共独立集族均有 FPRAS 与几乎均匀采样器（总变差距离 \(\le\theta\)），空性判定是精确的。

## 证明思路

先做配对归约（paired reduction）：把 \([n]\) 复制成 \(n\) 对元素 \(\{x_i,y_i\}\)，取直和 \(K=M_1\oplus M_2^*\)（\(M_2^*\) 为对偶拟阵），秩为 \(n\)。恰含每对一元的 \(n\) 元集称为横截集（transversal），而 \(A\) 是公共基当且仅当对应横截集是 \(K\) 的基。给秩亏 \(d(S)=n-\rank_K(S)\) 赋权 \(f_q(S)=q^{d(S)}\)：\(q=1\) 时横截总权已知为 \(2^n\)，\(q\) 退火到指数小时非基横截的权被压没，总权趋于 \(Z\)；秩值用贪婪扫描、每次至多 \(n\) 个独立集查询即可算出。

纯正权不足以给出定量混合界，于是扩充状态空间：允许恰一个空对与一个满对的缺陷态，其有序指标为缺陷类型 \(ij\)，每类配一个正乘子 \(w_{ij}\) 平衡总权，链以 Metropolis 规则做单元素交换。代数输入是 Brändén–Huh 的 Lorentzian 多项式理论（齐次 Tutte 定理）：由二次签名性质——偏导加非负代换所得二次型的 Hessian 至多一个正特征值——对选元素多项式 \(F\) 与省略元素多项式 \(F^\vee\) 分别应用，经反向 Cauchy–Schwarz 得到缺陷总量间的乘性不等式；再证运输不等式（transport inequality），把缺不同槽的两个条件分布的均值差控制为符号流的能量：递归指派平衡需求，分裂槽的代价由至多一个正方向的二次型界定，最后在叶团内以流实现。由此得到横截方差界与缺陷均值转移界。

关键一步是承认局限：这些工具只控制横截上的变异与缺陷类型的均值，看不见类型内部的任意波动。因此论文对迹链（trace，记录相继回访横截）证明逆谱隙至多 \(18n^4\) 的混合，而对算法真正平均的类型指示与比值可观测量建立分区限制的 Poincaré 不等式 \(\Var_\pi(\mathsf QH)\le 2000n^6\calE(H)\)；热起始（warm start）由退火表上的独立重启供给。最后沿 \(q_j=\rho^j\) 的几何退火表逐相位估计相邻质量比与类型频率，按 \(w_{ij}\mapsto w_{ij}\cdot\widehat p_0/\widehat p_{ij}\) 学习乘子，连乘得 \(\widehat Z=2^n\prod_j\widehat R_j\)；有理数位长与抽样次数均设上限，多次独立运行取中位数放大成功率。

## 可信度与备注

主结果（含公共独立集推论）已由 Lean 形式化（结果族 114 的形式化文档）。本文是族内母篇：姊妹篇《An FPRAS for Common Integer Polymatroid Bases with Binary Capacities》正是把本文的运输与迹链框架推广到二进制容量整多拟阵的产物（该篇暂未形式化）。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已通过形式化这一关。

{% endraw %}
