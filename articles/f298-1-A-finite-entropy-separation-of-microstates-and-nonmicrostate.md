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

## 入门导读 🐣

测量一个随机变量的"不确定性"，经典概率论只有一种熵，答案唯一。可在变量不满足乘法交换律的"自由世界"里，Voiculescu 给出两种测法：一是"数替身"——统计有多少组有限矩阵能惟妙惟肖地模仿这组变量（微状态熵 χ）；二是"量敏感度"——沿添加噪声的轨道积分一种反应力（非微状态熵 χ*）。单变量时两者相等；人们长期追问：两者都取有限值时是否必相等？本文构造反例：即便都是有限数，χ 仍可以比 χ* 小至少 1/2。

**关键词卡片**

- 自由熵（free entropy）：给不交换的"随机变量"（算子组）定义的不确定度
- 微状态（microstates）：能模仿这组变量各阶矩的有限矩阵组，像合格的替身演员
- 非微状态熵（nonmicrostates entropy）：不用矩阵替身、用共轭变量积分算出的熵
- 半圆变量（semicircular variable）：自由概率中扮演"标准正态"的变量
- 张量独立（tensor independence）：经典式的互不相干，与自由概率的"自由"是两种不同的独立

**看个具体例子**

反例骨架：取 p 个（可取 `@@M@@2^{64}@@`）两两自由的半圆变量 B，再让一个均匀取 p 个等距值的离散变量 Y 以"经典独立"的方式与它们同住。妙在 Y 与 B 交换而非自由：按 Y 的取值把空间切成 p 个块，每块权重约 1/p，B 超过四分之三的能量被锁在块内。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="38" font-size="15" text-anchor="middle">按 Y 的取值切块（示意 p=5）</text><rect x="60" y="80" width="440" height="90" fill="none" stroke="#333" stroke-width="2"/><line x1="148" y1="80" x2="148" y2="170" stroke="#333" stroke-width="1.5"/><line x1="236" y1="80" x2="236" y2="170" stroke="#333" stroke-width="1.5"/><line x1="324" y1="80" x2="324" y2="170" stroke="#333" stroke-width="1.5"/><line x1="412" y1="80" x2="412" y2="170" stroke="#333" stroke-width="1.5"/><path d="M84 125 q10 -12 20 0 t20 0" fill="none" stroke="#369" stroke-width="2"/><path d="M172 125 q10 -12 20 0 t20 0" fill="none" stroke="#369" stroke-width="2"/><path d="M260 125 q10 -12 20 0 t20 0" fill="none" stroke="#369" stroke-width="2"/><path d="M348 125 q10 -12 20 0 t20 0" fill="none" stroke="#369" stroke-width="2"/><path d="M436 125 q10 -12 20 0 t20 0" fill="none" stroke="#369" stroke-width="2"/><text x="104" y="195" font-size="13" text-anchor="middle">-1</text><text x="192" y="195" font-size="13" text-anchor="middle">-1/2</text><text x="280" y="195" font-size="13" text-anchor="middle">0</text><text x="368" y="195" font-size="13" text-anchor="middle">1/2</text><text x="456" y="195" font-size="13" text-anchor="middle">1</text><text x="280" y="230" font-size="13" text-anchor="middle">蓝色波纹：B 的能量被困在块内</text><text x="280" y="256" font-size="13" text-anchor="middle">矩阵替身难以兼顾块结构 ⇒ 两种熵拉开差距</text></svg>

</div>

这个"块结构"就是分歧的信号：矩阵替身很难同时模仿块结构与其余统计，于是 χ 与 χ* 拉开至少 1/2 的差距——这正是对"有限熵相等问题"的否定回答。

**为什么值得关心**

自由熵是自由概率的核心不变量，此结果表明"熵有限"这一良好性质远不足以统一两种定义，划出了一条真实存在的鸿沟。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文构造了一个有界自伴算子组，其微状态自由熵 `@@M@@\chi@@` 与非微状态自由熵 `@@M@@\chi^*@@` 均为有限值，却满足 `@@M@@\chi\leq\chi^*-\tfrac12@@`。这否定地回答了 Voiculescu 的有限熵相等问题：即使两种自由熵都有限，它们也可以严格不相等。

## 问题背景

自由熵 (free entropy) 是 Voiculescu 为研究自由概率与自由群因子引入的核心不变量，他给出两种定义：微状态熵 (microstates entropy) `@@M@@\chi(X)@@` 度量"矩逼近 `@@M@@X@@` 的矩阵组"的渐近体积；非微状态熵 (nonmicrostates entropy) `@@M@@\chi^*(X)@@` 则用共轭变量 (conjugate variables)——经典得分变量的自由类比——沿添加自由半圆噪声的轨道积分自由 Fisher 信息 (free Fisher information)。单变量情形二者相等；一般算子组上是否相等是 Voiculescu 统一问题的公开部分，Guionnet 明确陈述了有限熵版本：`@@M@@\chi(X)>-\infty@@` 是否蕴含 `@@M@@\chi(X)=\chi^*(X)@@`？已知一般比较 `@@M@@\chi\leq\chi^*@@` 成立（Biane–Capitaine–Guionnet 用矩阵布朗运动大偏差证明，Jekel–Pi 后给出初等证明），且在严格凸位势等正则情形下相等（Dabrowski、Jekel）；另一方面已存在 `@@M@@\chi=-\infty<\chi^*@@` 的不可逼近律。本文首次证明：两者都有限时仍可出现严格间隙。

## 主要结果

**主定理**：存在整数 `@@M@@n\geq2@@` 与带忠实正规迹态 (faithful normal tracial state) 的冯·诺依曼代数中的有界自伴元组 `@@M@@X=(X_1,\ldots,X_n)@@`，使得

`@@M@@D-\infty<\chi(X)\leq\chi^*(X)-\tfrac12<\infty,@@`

其中 `@@M@@\chi@@` 采用带算子范数截断 (operator-norm cutoff)、对矩阵维数取上极限 (limsup) 的原始定义。反例的变量个数 `@@M@@n=p+1@@` 很大但固定。这表明"微状态熵有限"这一正则性远不足以恢复两种自由熵的相等。

## 证明思路

证明骨架是"先造信号，再在两个噪声尺度上分头估计，最后用相对熵合围"。

先造信号。取 `@@M@@p@@` 个自由、方差为一的半圆变量 (semicircular variables) `@@M@@B_1,\ldots,B_p@@`，再在独立的张量因子上取均匀分布于 `@@M@@[-1,1]@@` 中 `@@M@@p@@` 个等距点上的 `@@M@@Y@@`，令 `@@M@@C=(B_1,\ldots,B_p,Y)@@`。妙处在于 `@@M@@Y@@` 与诸 `@@M@@B_i@@` 张量独立而非自由：自由性保证累积量稀疏，张量独立则使 `@@M@@Y@@` 与所有 `@@M@@B_i@@` 交换，按 `@@M@@Y@@` 的谱把空间分成 `@@M@@p@@` 个块，各块迹约 `@@M@@1/p@@`，前 `@@M@@p@@` 个坐标超过四分之三的 `@@M@@L^2@@` 能量被困在块内。加小噪声得 `@@M@@X=C+\sqrt h\,S@@`：块结构在扰动下稳定；再用显式矩阵模型加方差 `@@M@@h@@` 的 GUE 噪声（密度有上界）证得 `@@M@@\chi(X)>-\infty@@`。

再做双边估计。固定大 `@@M@@p@@`（可取 `@@M@@2^{64}@@`）与额外噪声时间 `@@M@@t=p^{3/4}@@`。分析侧借助 Speicher 非交叉累积量 (noncrossing cumulants) 与半圆 Wick 多项式的正交性，证明 Fisher 亏损的平方累积量上界：`@@M@@\Phi^*(V_u)@@` 超出同协方差半圆基准的部分被信号高阶累积量数组的平方 `@@M@@\ell^2@@` 范数控制；张量结构迫使 `@@M@@B@@` 位置做非交叉配对，得 `@@M@@\|\kappa_m(C)\|_2\le K^m p^{m/4}@@`，故 `@@M@@\chi^*(V_{h+t})@@` 距半圆熵基准 `@@M@@L(h+t)@@` 不足 `@@M@@\tfrac12@@`。矩阵侧选定一族体积渐近最优的截断微状态集，取其上一致分布 `@@M@@A^{(d)}@@`，加方差 `@@M@@t@@` 的独立 GUE 噪声：de Bruijn 恒等式把熵产生写成经典 Fisher 信息积分，分部积分把矩阵得分与共轭变量的变分公式衔接，经 Jekel–Pi 的经典—自由 Fisher 比较得下界 `@@M@@\limsup_d H_d\geq\chi_R(X)+\tfrac12\int_0^t\Phi^*(V_{h+s})\,ds@@`。关键在于始终保留这族具体终末系综——其熵的上极限不必等于极限律的微状态熵，间隙正源于此。结构侧定义"块事件"`@@M@@\mathcal E_d@@`：存在秩至多 `@@M@@2d/p@@` 的 `@@M@@p@@` 块单位分解，使前 `@@M@@p@@` 个坐标保留至少 `@@M@@\sqrt p/4@@` 的块内能量。演化后的微状态系综以 `@@M@@\ge\tfrac12@@` 的概率落入 `@@M@@\mathcal E_d@@`（初始谱分解作见证，噪声平均仅贡献 `@@M@@\le 2t@@`，由 `@@M@@32t/p<\tfrac18@@` 控制）；而同方差的独立 GUE 律落入的概率至多 `@@M@@e^{-4d^2}@@`——枚举至多 `@@M@@(d+1)^p@@` 种秩表、用西群的体积覆盖网与卡方尾估计，参数条件 `@@M@@p/(256(2+t))@@` 压倒覆盖开销，这正是选 `@@M@@t=p^{3/4}@@`（同时满足 `@@M@@t\gg\sqrt p@@` 与 `@@M@@t\log p/p\to0@@`）的原因。

最后合围。相对熵的数据处理不等式把两概率之差放大为 `@@M@@d^{-2}\mathrm{KL}\ge2@@`，代入熵的精确分解恒等式得 `@@M@@\limsup_d H_d\le L(h+t)-1@@`；与下界及自由熵流恒等式 `@@M@@\chi^*(V_{h+t})-\chi^*(V_h)=\tfrac12\int_0^t\Phi^*\,ds@@` 串联，即得 `@@M@@\chi(X)\leq\chi^*(X)-\tfrac12@@`。

## 可信度与备注

本结果暂无 Lean 形式化证明，属 OpenAI 2026 年 9 月发布的手稿；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。姊妹篇《An isomorphism of the free group factors》证明四种自由熵维数 `@@M@@\delta,\delta_0,\delta^*,\delta^\star@@` 在 `@@M@@L(\mathbb F_2)@@` 的生成元组上可取一切 `@@M@@\ge2@@` 的整数值，与本文从不同侧面展现自由熵的反直觉行为。技术上的一处巧思是绕开"上、下矩阵极限是否相等"的公开难题：只追踪选定系综的熵上极限，让有限时间的结构亏损直接产生严格间隙。

{% endraw %}
