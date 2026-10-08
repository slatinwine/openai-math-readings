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

## 入门导读 🐣

量一条无限曲折的海岸线有多长？用米尺得到一个数，换毫米尺得到更大的数——尺子越细、长度越大，答案永远定不下来。这篇论文为一种著名的随机曲线（SLE）量身打造了一把"补正过的尺子"：刻度函数经过精心设计，用它量出的长度既不是 0，也不是无穷。

**关键词卡片**

- SLE（Schramm–Loewner evolution）：统计物理中反复出现的随机曲线，参数 κ 越大越蜿蜒，是二维临界现象的通用语言。
- 豪斯多夫测度（Hausdorff measure）：用一堆小圆盘盖住曲线、按刻度 h(r) 计代价，再对所有覆盖取下确界。
- 规范（gauge）：刻度函数 h(r)；普通尺子 h(r)=r，量分形必须特制。
- 豪斯多夫维数（Hausdorff dimension）：SLE 轨迹维数 d=1+κ/8（Beffara 定理）；但只知维数不够——用 r^d 去量，测度仍是 0。
- Schramm 问题（Schramm's problem, 2006）：是否存在规范，使每段轨迹的测度都正且有限。

**看个具体例子**

取 κ=4：维数 d=1.5，但已有结果证明 r^1.5 刻度下测度为零。本文构造只依赖 κ 的确定性规范 h_κ（由有限批次的阈值与半径作"二次包络"的下确界定义），证明几乎必然对每段轨迹 γ([s,t]) 的测度都介于 0 与 ∞ 之间，且整条轨迹在每个有界方盒内的期望测度有限。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="24" font-size="14" fill="#333" text-anchor="middle">用圆盘"盖住"随机曲线，数总代价</text><path d="M55,225 C85,205 60,150 105,120 C150,90 125,165 185,150 C245,135 215,70 275,85 C335,100 300,175 360,165 C420,155 390,95 450,105 C490,112 495,60 525,72" fill="none" stroke="#333" stroke-width="2"/><circle cx="105" cy="120" r="30" fill="none" stroke="#1565c0" stroke-width="1.5" stroke-dasharray="5 4"/><circle cx="185" cy="150" r="18" fill="none" stroke="#1565c0" stroke-width="1.5" stroke-dasharray="5 4"/><circle cx="275" cy="85" r="10" fill="none" stroke="#1565c0" stroke-width="1.5" stroke-dasharray="5 4"/><circle cx="360" cy="165" r="6" fill="none" stroke="#1565c0" stroke-width="1.5" stroke-dasharray="5 4"/><circle cx="450" cy="105" r="14" fill="none" stroke="#1565c0" stroke-width="1.5" stroke-dasharray="5 4"/><text x="66" y="86" font-size="12" fill="#777">大盘</text><text x="372" y="192" font-size="12" fill="#777">小盘</text><text x="280" y="242" font-size="12" fill="#333" text-anchor="middle">普通刻度 r^d：量出的总代价要么 0 要么 ∞</text><text x="280" y="264" font-size="12" fill="#1565c0" text-anchor="middle">特制刻度 h_κ：总代价被夹在中间——正且有限</text></svg>

</div>

**为什么值得关心**

在全部 0&lt;κ&lt;8 范围内肯定回答了 Schramm 的豪斯多夫测度存在性问题；姊妹篇随后给出显式闭式规范，两篇相互独立又互相印证。

> 暂无形式化证明（AI 结果待核验）。

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
