---
layout: default
title: "Absolutely Continuous Spectrum for Weak-Disorder Anderson Models in Dimensions at Least Three"
family: "261"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Absolutely Continuous Spectrum for Weak-Disorder Anderson Models in Dimensions at Least Three

> 结果族 261：Localization and delocalization in the Anderson model　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对格点 Anderson 模型，本文证明：在每个固定维数 \(d\ge3\)、无序强度 \(\lambda\) 充分小且固定时，几乎必然存在一个不依赖 \(\lambda\) 的开能量区间，谱在其上纯绝对连续且质量非零——正面解决了 Simon 问题 1 的纯绝对连续能段部分。

## 问题背景

1958 年 Anderson 提出随机格点模型，解释杂质如何抑制量子输运：无序足够强时波函数局域化，材料表现为绝缘体。物理相图预期三维及以上在弱无序时仍有延展态（金属相），但如何在 \(\mathbb{Z}^d\) 上严格证明"延展"是最著名的公开难题之一——谱论语言中，延展对应绝对连续谱（absolutely continuous spectrum），局域对应纯点谱（pure-point spectrum）。此前的严格结果都在别处：强无序与谱边端的局域化由 Fröhlich–Spencer 的多尺度分析（multiscale analysis）与 Aizenman–Molchanov 的分数矩方法（fractional moment method）建立；绝对连续谱只在 Bethe 树等分叉几何上可得（Klein、Aizenman–Warzel、Aggarwal–Lopatto），Euclidean 格点上一直没有。Simon 在 2000 年的问题 1 中明确要求：对 \(d\ge3\)、独立均匀格点势、适当的无序宽度，证明存在纯绝对连续的能量区间。本文补上了这块拼图。

## 主要结果

模型是 \(\ell^2(\mathbb{Z}^d)\) 上的最近邻跳跃加随机对角势：
\[(H_{\lambda,\omega}\psi)(x)=-\sum_{j=1}^d\bigl(\psi(x+\mathbf e_j)+\psi(x-\mathbf e_j)\bigr)+\lambda V_x(\omega)\psi(x),\]
其中 \(V_x\) 独立、均匀分布于 \([-1,1]\)。

**主定理**：存在固定小常数 \(e_2\in(0,1/100)\)，使得对每个固定维数 \(d\ge3\) 都存在阈值 \(\lambda_d>0\)：只要固定 \(0<\lambda<\lambda_d\)，几乎必然地，区间
\[I_d=\begin{cases}(-6+e_2/2,\,-6+e_2),&d=3,\\ (-2d+1/200,\,-2d+1/100),&d\ge4\end{cases}\]
含于谱中，且 \(H_{\lambda,\omega}\) 在 \(I_d\) 上的谱限制是纯绝对连续的、谱投影非零。关键在于 \(I_d\) 只依赖 \(d\)、不依赖 \(\lambda\)。\(d\ge4\) 时阈值可写成 \(\lambda_d=\sqrt3\,2^{-n_*(d)}\)，但 \(n_*(d)\) 由有限矩阵的条件族隐式给出、无有效数值界；\(d=3\) 时仅证明阈值存在。

**谱共存推论**：结合 Elgart–Klein 的固定无序谱边局域化定理，在同一耦合下，谱下端某小区间上几乎必然是纯点谱且特征函数指数衰减，而 \(I_d\) 上是纯绝对连续谱——同一算子内局域与延展并存，正是迁移率边（mobility edge）的严格实例。

## 证明思路

整个证明围绕一个"有限体积预解式（resolvent）证书"展开：在边长 \(L=4^{20m}\) 的大环面上，以趋于 1 的概率构造出一个至少占一半格点的集合 \(A\) 与带小虚部的阻尼系数 \(r_i\)，使阻尼预解式 \(\widehat G=(H_m-E-\eta\,\diag_A r)^{-1}\) 存在且对角虚部 \(\Im\widehat G_{ii}\ge c>0\)，而 \(H_m\) 的势全部是真实随机势。

构造从自由算子出发。先每个均匀势按二进制展开成一串独立随机符号，再一比特一比特地"揭示"真随机性，用真随机性替换人工阻尼：活跃格点保留阻尼，看全了真实势的终端格点经 Schur 补（Schur complement）永久消元。为控制演化中的矩阵，全程维护三个量：预解式元素的复平方（用于线性化对角自洽方程的更新）、行四阶矩（防止一行的质量集中于少数格点，限制单次更新的影响）、以及把 Ward 恒等式（Ward identity）作用于模方得到的精确拉普拉斯方程——其逆形式提供累加局部修改所需的空间能量范数。初始界由自由预解式的傅里叶估计给出。普通更新只在有限"瓷砖"上做测试，失败即回滚数值并保守地把整块格点标记为 pending；随后用酉散射矩阵交叉块的投影范数清理小块 pending 集。一条确定性归纳合并所有已承诺的局部修改、保持至少半数格点活跃并闭合自洽重置；一条概率归纳追踪保留的信息，按确定性排序的标签逐次条件化压住失败概率。最后一次扫描把剩余真实比特完整装入，活跃格点只剩极小的最终阻尼。

最后一步把证书转成谱论结论：先用窄谱投影截断与"本点平均"（own-site averaging，Simon–Wolff 型秩一谱平均）控制近特征值的影响并界定期望秩，再取无穷体积边界值；遍历性与单点势的秩一扰动把对角虚部的正性传播到每个格点；对"挖掉一个格点"后的算子条件化，使例外能量集不依赖该格点的剩余变量，在余集上得绝对连续，再用谱平均抹去例外集上的质量——纯性由此而来。维数 \(d\ge3\) 通过三处估计进入：故意减弱的傅里叶界保留三维插值增益、pending 分量的尺度指数取为与 \(1/d\) 成比例、历史递归按维度分离尺度。

## 可信度与备注

本文与姊妹篇（二维任意正无序的纯点谱）同日发布，互补地印证 Anderson 相图的维度对比：二维全无序局域，三维以上弱无序存在延展能段。两篇主结果目前均无 Lean 形式化证明，且证明依赖大量精细构造（如 \(n_*(d)\) 无有效数值界），按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。结论限于独立均匀单点分布，不涉及 Simon 问题 3 的扩散问题。

{% endraw %}
