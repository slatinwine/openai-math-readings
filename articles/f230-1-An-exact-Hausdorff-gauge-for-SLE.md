---
layout: default
title: "An exact Hausdorff gauge for SLE"
family: "230"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An exact Hausdorff gauge for SLE

> 结果族 230：Exact Hausdorff gauges for SLE　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对每个 `@@M@@0<\kappa<8@@`，本文构造出只依赖 `@@M@@\kappa@@` 的确定性豪斯多夫规范（Hausdorff gauge）`@@M@@h_\kappa@@`，使弦 `@@M@@\mathrm{SLE}_\kappa@@` 任一非平凡紧段 `@@M@@\gamma([s,t])@@` 的 `@@M@@h_\kappa@@`-豪斯多夫测度几乎必然既正又有限，肯定地回答了 Schramm 的测度存在性问题。

## 问题背景

Beffara（2008）证明了弦 `@@M@@\mathrm{SLE}_\kappa@@`（chordal Schramm–Loewner evolution）轨迹的几乎必然维数是 `@@M@@d=1+\kappa/8@@`，但知道维数并不等于能"量出"这条随机曲线：临界幂 `@@M@@r^d@@` 未必赋予它非零测度。Schramm（2006）问轨迹是否有 `@@M@@\sigma@@`-有限的豪斯多夫测度（Hausdorff measure），并建议 `@@M@@r^d\log\log(1/r)@@` 作为候选规范；Rezaei（2018）证明 `@@M@@r^d@@` 本身给出的测度为零。难点在于豪斯多夫测度要对任意空间覆盖取下确界，而自然参数化（natural parametrization）等基于有序时间分割的工具并不直接适用，此前无人能构造出使每段轨迹测度均正且有限的规范。

## 主要结果

定理 1.1：设 `@@M@@\gamma@@` 是上半平面 `@@M@@\mathbb H@@` 中从 `@@M@@0@@` 到 `@@M@@\infty@@`、按半平面容量 `@@M@@2t@@` 参数化的弦 `@@M@@\mathrm{SLE}_\kappa@@`。存在仅依赖 `@@M@@\kappa@@` 的确定性规范 `@@M@@h_\kappa@@`，使在一个概率为一的事件上，同时对所有实数 `@@M@@0<s<t<\infty@@` 有
`@@M@@D0<\mathcal H^{h_\kappa}(\gamma([s,t]))<\infty .@@`
此外，对方盒 `@@M@@B_m=[-m,m]+i[0,m]@@` 与 `@@M@@\Gamma=\gamma([0,\infty))@@`，有 `@@M@@\mathbb E\,\mathcal H^{h_\kappa}(\Gamma\cap B_m)<\infty@@`，即整条轨迹在每个有界盒中的期望测度有限。规范由"有限批次"显式定义：对每个矩阶 `@@M@@n@@` 列出阈值 `@@M@@b_{ni}@@` 与半径 `@@M@@r_{ni}@@`，令
`@@M@@Dh_\kappa(r)=\inf_{n,i}\ b_{ni}r_{ni}^{\,d}\max\{1,(r/r_{ni})^2\},\qquad h_\kappa(0)=0,@@`
系数由圆盘质量模型各阶矩的确定性迭代积分给出；该表达式完全确定，但其小尺度渐近形态不必规则。

## 证明思路

证明分四步，核心是"全阶矩"机制：中等大小的质量提供反复试探的机会，而超过更高阈值的概率总和可和，因此无需精确的尾渐近。

第一步在轨迹上构造典型质量 `@@M@@\mu_t@@`：沿 Lawler–Sheffield 的格林位势（Green potential）路线，对水平权逼近式取共同的凸组合极限，得到递增适应测度，其增量由对应轨迹段承载，且在任一停时 `@@M@@S@@` 处剩余质量的条件均值为格林密度 `@@M@@G_S(x)=R_{H_S}(x)^{-\alpha}\sin^{8/\kappa-1}\theta_S(x)@@` 乘面积（`@@M@@\alpha=2-d@@`）。配套的多点估计——`@@M@@m@@` 个内点各自到达指定共形半径（conformal radius）的概率不超过 `@@M@@C\prod_i(e_i/b_i)^\alpha@@`——用逐点冻结的乘积上鞅（product supermartingale）直接证明，从而一切紧矩有限且测度无原子。

第二步换律并建立圆盘模型：在标记点的共形半径水平处停时并按格林权重之比重加权，把曲线"偏向"该点，得到中心化律（centered law）；标记点辐角在此律下是不变密度 `@@M@@\propto\sin^{4a}\theta@@`（`@@M@@a=2/\kappa@@`）的扩散，等待足够"内时间"后辐角近似混合。把标记点放在单位圆盘中心，考察 `@@M@@1/4@@` 子盘内累积的质量 `@@M@@L_\ell\uparrow L@@`：对混合后的中心化律，各阶矩满足 `@@M@@0<m_n<\infty@@`，且由确定性迭代积分显式给定。

第三步把矩变成批次与规范：对每阶 `@@M@@n@@` 取有限水平 `@@M@@\ell_n@@` 保住该矩的四分之三，再以重数 `@@M@@N_{nk}@@` 重复二进阈值 `@@M@@A_k=2^k@@`。两个反向估计同时成立——超阈值概率 `@@M@@\mathbb P^*\{L\ge 16A_k\}@@` 的加权和在 `@@M@@n@@` 上可和，而成功机会 `@@M@@\mathbb P^*\{L_{\ell_n}\ge A_k\}@@` 的加权和至少 `@@M@@2^n/8@@`，即"失败便宜、机会众多"；每批末尾附加的清扫条目为漏检付账。规范取全部条目二次包络的下确界，二次因子 `@@M@@\max\{1,(r/r_{ni})^2\}@@` 正是平面剖分的代价。

第四步证两个豪斯多夫不等式。下界用严格过去质量恒等式：把"超满方格"的期望质量化为中心化律下质量阈值先于首达被超过的概率，尾估计使其在所有批次上可和，故几乎每点在足够晚的批次后不再落入坏格；在剩余集上限制增量测度得 `@@M@@\nu@@`，满足 `@@M@@\nu(U)\le C\,h_\kappa(\mathrm{diam}\,U)@@`，从而任何可数覆盖的总代价 `@@M@@\ge\nu(\mathbb H)/C>0@@`。上界：沿真实曲线的试探用确定性内时间隔开，辐角混合使每次试探的条件成功概率不低于混合律的一半，迭代条件期望（无需测试间独立性）给出全部试探失败的概率 `@@M@@\le e^{-2^n/16}@@`；贪心选取的两两不相交候选球由同一有界区域内同一个真实质量 `@@M@@\mu_\infty@@` 支付费用，漏检格与实轴底部行由清扫条目覆盖，最后用 Fatou 引理得期望有限。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。外部几何输入仅有 Rohde–Schramm 的轨迹连续性定理与经典 Koebe 估计，其余换律、质量与覆盖论证均在文内自证。姊妹篇《An explicit exact Hausdorff gauge for SLE》随后给出规则闭式规范 `@@M@@r^d(\log\log(1/r))^{(2-d)/2}@@`，与本文的矩定义规范相互独立；两篇合起来既证明存在性又给出显式公式，但两个精确规范之间的渐近关系仍是公开问题。

{% endraw %}
