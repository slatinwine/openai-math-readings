---
layout: default
title: "The additive indecomposability of the primes"
family: "013"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The additive indecomposability of the primes

> 结果族 013：Ostmann's inverse Goldbach conjecture　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文完整证明了 Ostmann 逆 Goldbach 猜想：素数集经任意有限改动后，都不可能写成两个各含至少两个元素的非负整数集之和 \(A+B\)——素数在加法意义下不可分解。

## 问题背景

Goldbach 猜想问每个大偶数是否为两素数之和，Ostmann 则在 1956 年专著中提出反方向的逆 Goldbach 问题（inverse Goldbach problem）：素数集 \(\mathcal P\) 本身能否写成两个非负整数集之和？精确地说，\(\mathcal P\) 是否渐近加法不可分解（asymptotically additively indecomposable），即不存在 \(|A|,|B|\ge 2\) 使 \(A+B\) 与 \(\mathcal P\) 只差有限个元素。Laffer 与 Mann 在 1964 年证明假想的分解必有两个无限 summand；Elsholtz、Elsholtz–Harper 等随后用大筛法（large sieve）与更大筛把假想分解的计数函数压缩到平方根尺度 \(\sqrt{x}/(\log x\log\log x)\ll A(x),B(x)\ll\sqrt{x}\log\log x\)；Green 与 Harper 证明一个合适的逆筛猜想足以推出 Ostmann 猜想；Croot–Mao–Pohoata–Yip 又用加权熵论证给出"两 summand 必与整系数二次像有大交集"的必要条件。这些限制不断收紧，却都不足以导出矛盾——本文绕开任何分类定理，直接联用逐素数的剩余约束与"每个足够大的素数都被表示"这一覆盖条件完成证明。

## 主要结果

**定理（Ostmann 猜想）**：若 \(A,B\subseteq\mathbb N_0\) 满足 \(|A|,|B|\ge 2\)，则 \((A+B)\mathbin{\triangle}\mathcal P\) 是无限集。等价地，对素数集做任何有限修改（finite modification）所得的集合都不能分解为两个至少二元的集合之和。

证明分两步。第一步是"有限 summand"引理：若 \(A+B\) 与 \(\mathcal P\) 渐近相等且 \(|A|,|B|\ge 2\)，则 \(A,B\) 都是无限集——这重述并简证了 Laffer–Mann 定理。第二步是技术核心"两个无限 summand"定理：不存在无限集 \(A,B\subseteq\mathbb N_0\) 使 \((A+B)\mathbin{\triangle}\mathcal P\) 有限。

值得注意的是定理结论的双重性：既要最终覆盖所有大素数，又要最终排除所有合数，二者都不能换成密度条件。特别地，若 \(|A|,|B|\ge 2\) 且 \(A+B\) 含每个足够大的素数，则 \(A+B\) 必含无穷多个合数。

## 证明思路

反证法：设无限集 \(A,B\) 满足 \(\mathcal P\cap(N,\infty)\subseteq A+B\)（素数覆盖）且 \((A+B)\cap(N,\infty)\subseteq\mathcal P\)（排除合数），记 \(D=-B\)。先建立两个基础事实：其一，Elsholtz 的平方根界 \(\sqrt{Y}/(\log Y)^3\ll A(Y),B(Y)\ll\sqrt{Y}(\log Y)^2\)；其二，对每个素数 \(p\)，\(A\) 与 \(D\) 的远尾部模 \(p\) 剩余互不相交——否则 \(a-d=a+b\) 是超过 \(N\) 的 \(p\) 的倍数，与素性矛盾。据此把 \(\mathbb F_p\) 划分为互补剩余集 \(S_p,S_p^c\)；碰撞稳定性（collision stability）引理作为 Gallagher 更大筛的加权形式表明，按 \(\log p/p\) 加权平均，两个 summand 在各自剩余部分上近似均匀，且两边规模近似减半。

再排除与平移乘法特征（multiplicative character）的持续相关：二次特征情形用矩估计与 Poisson 求和迫使一个公共有理中心，再用二次大筛法把尾部囚禁进一小族二次核，以碰撞矛盾收场；高阶特征情形用反复 Cauchy–Schwarz 转移处理，锚变量区分被复制的项并供给控制对角项所需的特征抵消。两者合成混合特征去相关（mixed-character decorrelation）。

素数覆盖单独进场。供应（supply）命题断言：在某段 \(\log\log p\) 窗口内，剩余密度满足 \(1/3\le\sigma_p\le 2/3\) 且归一化加性变换 \(g_p\) 的 \(L^1\) 质量有下界的素数，其调和质量不可忽略。证明从稀疏 Fourier 谱构造收缩的张量核 \(W(n)\ge 0\)：大筛法给出 \(W\) 在 \(A\times D\) 上的平均的上界，Landau–Page 定理与 Montgomery 零点密度定理经显式公式算出其素数平均，而覆盖迫使每个大素数都有 \(A\times D\) 中的表示从而给出下界，两端矛盾。

最后构造正统计量并做二叉树转移：按对数胞腔先验独立抽取素数（一个来自"有利"块的巨型素数、\(m/2\) 个 bulk 素数、\(m/2\) 个旁观素数及若干顶部、补偿位置），Poisson 求和把它化为有下界的振幅 \(\eta_0\)，再逐层转移。有限域树比较引理只假设概率 \(L^2\) 界与混合特征小相关，允许高度非均匀的点值，恰好适配残差指示函数的精确 Fourier 变换，从而控制非对角项；重复素数标签、互素条件与可能的例外实特征在第 8 节的算术分离中处理。终局对 bulk 变量做置换对称化：坏排列对（重叠分量多于 \(3r/4\) 者）占比仅 \(\exp(-\tfrac34 rm\log r)\)，其总量连同中国剩余定理与素数等差数列估计给出的公共正则变换范数界，使 \(|\eta_k|^2\le\exp(-(2B+1)rm)\)，与转移递归保留下界 \(|\eta_k|^2\ge\exp(-2Brm)\) 矛盾。转移深度 \(k\) 先固定得足够大，再让尺度 \(L\to\infty\)。全程不需要 Green–Harper 的一般逆筛分类。

## 可信度与备注

本文暂无 Lean 形式化证明，请以社区核验为准；证明自含于九个章节，所引外部工具（Montgomery–Vaughan 大筛法、Gallagher 更大筛、Landau–Page 定理、Montgomery 零点密度定理与显式公式）均为解析数论经典结果。文中备注提到同批姊妹篇的零自由定理（非平凡零点实部至多 \(7/8\)）可简化供应一节，但正文只依赖上述经典估计。按 OpenAI 官方声明，未经形式化的结果可能有问题，读者宜以社区核验与后续形式化为最终判据。

{% endraw %}
