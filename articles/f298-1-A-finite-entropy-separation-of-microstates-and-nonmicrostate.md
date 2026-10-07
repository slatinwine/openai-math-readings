---
layout: default
title: "A finite-entropy separation of microstates and nonmicrostates free entropy"
family: "298"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A finite-entropy separation of microstates and nonmicrostates free entropy

> 结果族 298：Two notions of free entropy differ even when both are finite　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造了一个有界自伴算子组，其微状态自由熵 \(\chi\) 与非微状态自由熵 \(\chi^*\) 均为有限值，却满足 \(\chi\leq\chi^*-\tfrac12\)。这否定地回答了 Voiculescu 的有限熵相等问题：即使两种自由熵都有限，它们也可以严格不相等。

## 问题背景

自由熵 (free entropy) 是 Voiculescu 为研究自由概率与自由群因子引入的核心不变量，他给出两种定义：微状态熵 (microstates entropy) \(\chi(X)\) 度量"矩逼近 \(X\) 的矩阵组"的渐近体积；非微状态熵 (nonmicrostates entropy) \(\chi^*(X)\) 则用共轭变量 (conjugate variables)——经典得分变量的自由类比——沿添加自由半圆噪声的轨道积分自由 Fisher 信息 (free Fisher information)。单变量情形二者相等；一般算子组上是否相等是 Voiculescu 统一问题的公开部分，Guionnet 明确陈述了有限熵版本：\(\chi(X)>-\infty\) 是否蕴含 \(\chi(X)=\chi^*(X)\)？已知一般比较 \(\chi\leq\chi^*\) 成立（Biane–Capitaine–Guionnet 用矩阵布朗运动大偏差证明，Jekel–Pi 后给出初等证明），且在严格凸位势等正则情形下相等（Dabrowski、Jekel）；另一方面已存在 \(\chi=-\infty<\chi^*\) 的不可逼近律。本文首次证明：两者都有限时仍可出现严格间隙。

## 主要结果

**主定理**：存在整数 \(n\geq2\) 与带忠实正规迹态 (faithful normal tracial state) 的冯·诺依曼代数中的有界自伴元组 \(X=(X_1,\ldots,X_n)\)，使得

\[-\infty<\chi(X)\leq\chi^*(X)-\tfrac12<\infty,\]

其中 \(\chi\) 采用带算子范数截断 (operator-norm cutoff)、对矩阵维数取上极限 (limsup) 的原始定义。反例的变量个数 \(n=p+1\) 很大但固定。这表明"微状态熵有限"这一正则性远不足以恢复两种自由熵的相等。

## 证明思路

证明骨架是"先造信号，再在两个噪声尺度上分头估计，最后用相对熵合围"。

先造信号。取 \(p\) 个自由、方差为一的半圆变量 (semicircular variables) \(B_1,\ldots,B_p\)，再在独立的张量因子上取均匀分布于 \([-1,1]\) 中 \(p\) 个等距点上的 \(Y\)，令 \(C=(B_1,\ldots,B_p,Y)\)。妙处在于 \(Y\) 与诸 \(B_i\) 张量独立而非自由：自由性保证累积量稀疏，张量独立则使 \(Y\) 与所有 \(B_i\) 交换，按 \(Y\) 的谱把空间分成 \(p\) 个块，各块迹约 \(1/p\)，前 \(p\) 个坐标超过四分之三的 \(L^2\) 能量被困在块内。加小噪声得 \(X=C+\sqrt h\,S\)：块结构在扰动下稳定；再用显式矩阵模型加方差 \(h\) 的 GUE 噪声（密度有上界）证得 \(\chi(X)>-\infty\)。

再做双边估计。固定大 \(p\)（可取 \(2^{64}\)）与额外噪声时间 \(t=p^{3/4}\)。分析侧借助 Speicher 非交叉累积量 (noncrossing cumulants) 与半圆 Wick 多项式的正交性，证明 Fisher 亏损的平方累积量上界：\(\Phi^*(V_u)\) 超出同协方差半圆基准的部分被信号高阶累积量数组的平方 \(\ell^2\) 范数控制；张量结构迫使 \(B\) 位置做非交叉配对，得 \(\|\kappa_m(C)\|_2\le K^m p^{m/4}\)，故 \(\chi^*(V_{h+t})\) 距半圆熵基准 \(L(h+t)\) 不足 \(\tfrac12\)。矩阵侧选定一族体积渐近最优的截断微状态集，取其上一致分布 \(A^{(d)}\)，加方差 \(t\) 的独立 GUE 噪声：de Bruijn 恒等式把熵产生写成经典 Fisher 信息积分，分部积分把矩阵得分与共轭变量的变分公式衔接，经 Jekel–Pi 的经典—自由 Fisher 比较得下界 \(\limsup_d H_d\geq\chi_R(X)+\tfrac12\int_0^t\Phi^*(V_{h+s})\,ds\)。关键在于始终保留这族具体终末系综——其熵的上极限不必等于极限律的微状态熵，间隙正源于此。结构侧定义"块事件"\(\mathcal E_d\)：存在秩至多 \(2d/p\) 的 \(p\) 块单位分解，使前 \(p\) 个坐标保留至少 \(\sqrt p/4\) 的块内能量。演化后的微状态系综以 \(\ge\tfrac12\) 的概率落入 \(\mathcal E_d\)（初始谱分解作见证，噪声平均仅贡献 \(\le 2t\)，由 \(32t/p<\tfrac18\) 控制）；而同方差的独立 GUE 律落入的概率至多 \(e^{-4d^2}\)——枚举至多 \((d+1)^p\) 种秩表、用西群的体积覆盖网与卡方尾估计，参数条件 \(p/(256(2+t))\) 压倒覆盖开销，这正是选 \(t=p^{3/4}\)（同时满足 \(t\gg\sqrt p\) 与 \(t\log p/p\to0\)）的原因。

最后合围。相对熵的数据处理不等式把两概率之差放大为 \(d^{-2}\mathrm{KL}\ge2\)，代入熵的精确分解恒等式得 \(\limsup_d H_d\le L(h+t)-1\)；与下界及自由熵流恒等式 \(\chi^*(V_{h+t})-\chi^*(V_h)=\tfrac12\int_0^t\Phi^*\,ds\) 串联，即得 \(\chi(X)\leq\chi^*(X)-\tfrac12\)。

## 可信度与备注

本结果暂无 Lean 形式化证明，属 OpenAI 2026 年 9 月发布的手稿；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。姊妹篇《An isomorphism of the free group factors》证明四种自由熵维数 \(\delta,\delta_0,\delta^*,\delta^\star\) 在 \(L(\mathbb F_2)\) 的生成元组上可取一切 \(\ge2\) 的整数值，与本文从不同侧面展现自由熵的反直觉行为。技术上的一处巧思是绕开"上、下矩阵极限是否相等"的公开难题：只追踪选定系综的熵上极限，让有限时间的结构亏损直接产生严格间隙。

{% endraw %}
