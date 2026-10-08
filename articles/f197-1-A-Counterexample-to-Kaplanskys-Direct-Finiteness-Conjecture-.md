---
layout: default
title: "A Counterexample to Kaplansky's Direct-Finiteness Conjecture in Characteristic Two"
family: "197"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Counterexample to Kaplansky's Direct-Finiteness Conjecture in Characteristic Two

> 结果族 197：A torsion-free group algebra that is not directly finite　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

想象两位翻译官：b 把明文译成密码，a 负责把密码还原。直觉上，"先 b 后 a"与"先 a 后 b"都应回到原文，两人互为完美搭档。这篇论文却锻造出一对偏心的翻译：一个方向天衣无缝，另一个方向悄悄露馅——由此推翻了 Kaplansky 悬置五十年的猜想。

**关键词卡片**

- 群代数（group algebra）：把群元素当"字母"，允许有限个"字母×系数"相加相乘得到的代数系统
- 直接有限性（direct finiteness）：环里 `@@M@@ab=1@@` 必蕴含 `@@M@@ba=1@@` 的性质；Kaplansky 猜想一切群代数都满足它
- sofic 群（sofic group）：能用有限图案任意逼真模拟的"温顺"无限群；这类群的群代数已知直接有限
- 元胞自动机（cellular automaton）：每个格子按邻居颜色同步变色的机器，如"生命游戏"

**看个具体例子**

线性代数里，方阵一旦 `@@M@@ab=1@@` 就必有 `@@M@@ba=1@@`（逆矩阵两边通用），所以反例只能藏在无限群中。论文取特征二的有限域 `@@M@@K@@` 与一个精心锻造的无限群 `@@M@@G@@`，显式写出有限和 `@@M@@a,b\in K[G]@@`，使得

`@@M@@Dab=1,\qquad ba\ne 1 .@@`

同一组元素还充当无限格子的"变色规则"：不同图案必变出不同图案（单射），却有一种图案永远变不出来（不满射）。整个构造分三层铸造：先设计一套有限的"点线"组合数据，再据此搭建群 `@@M@@G@@`，最后在群代数中把矩阵反例压成标量元素 `@@M@@a,b@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="30" y="35" font-size="16" fill="#222">先 b 后 a：完美复原</text>
<rect x="30" y="55" width="90" height="50" fill="#f6f6f6" stroke="#888"/>
<circle cx="55" cy="80" r="6" fill="#222"/><circle cx="75" cy="80" r="6" fill="#222"/><circle cx="95" cy="80" r="6" fill="#222"/>
<line x1="125" y1="80" x2="163" y2="80" stroke="#555" stroke-width="2"/>
<polygon points="165,80 155,75 155,85" fill="#555"/>
<rect x="170" y="55" width="60" height="50" fill="#eef3ff" stroke="#35a"/>
<text x="192" y="86" font-size="18" fill="#235">b</text>
<line x1="235" y1="80" x2="273" y2="80" stroke="#555" stroke-width="2"/>
<polygon points="275,80 265,75 265,85" fill="#555"/>
<rect x="280" y="55" width="60" height="50" fill="#eef3ff" stroke="#35a"/>
<text x="302" y="86" font-size="18" fill="#235">a</text>
<line x1="345" y1="80" x2="383" y2="80" stroke="#555" stroke-width="2"/>
<polygon points="385,80 375,75 375,85" fill="#555"/>
<rect x="390" y="55" width="90" height="50" fill="#f6f6f6" stroke="#888"/>
<circle cx="415" cy="80" r="6" fill="#222"/><circle cx="435" cy="80" r="6" fill="#222"/><circle cx="455" cy="80" r="6" fill="#222"/>
<text x="495" y="86" font-size="15" fill="#2a2">✓</text>
<text x="30" y="155" font-size="16" fill="#222">先 a 后 b：冒出杂质</text>
<rect x="30" y="175" width="90" height="50" fill="#f6f6f6" stroke="#888"/>
<circle cx="55" cy="200" r="6" fill="#222"/><circle cx="75" cy="200" r="6" fill="#222"/><circle cx="95" cy="200" r="6" fill="#222"/>
<line x1="125" y1="200" x2="163" y2="200" stroke="#555" stroke-width="2"/>
<polygon points="165,200 155,195 155,205" fill="#555"/>
<rect x="170" y="175" width="60" height="50" fill="#eef3ff" stroke="#35a"/>
<text x="192" y="206" font-size="18" fill="#235">a</text>
<line x1="235" y1="200" x2="273" y2="200" stroke="#555" stroke-width="2"/>
<polygon points="275,200 265,195 265,205" fill="#555"/>
<rect x="280" y="175" width="60" height="50" fill="#eef3ff" stroke="#35a"/>
<text x="302" y="206" font-size="18" fill="#235">b</text>
<line x1="345" y1="200" x2="383" y2="200" stroke="#555" stroke-width="2"/>
<polygon points="385,200 375,195 375,205" fill="#555"/>
<rect x="390" y="175" width="90" height="50" fill="#f6f6f6" stroke="#888"/>
<circle cx="415" cy="200" r="6" fill="#222"/><circle cx="435" cy="200" r="6" fill="#222"/><circle cx="455" cy="200" r="6" fill="#222"/>
<circle cx="475" cy="186" r="6" fill="#d33"/>
<text x="495" y="206" font-size="15" fill="#d33">✗</text>
</svg>

</div>

**为什么值得关心**

一篇论文同时否定 Kaplansky 直接有限性猜想与 Gottschalk 满射性猜想，还顺带证明所用的群 `@@M@@G@@` 不是 sofic 群——无限群的世界确实比想象中狂野。

> 已 Lean 形式化

## 一句话结论

在特征二有限域上构造有限展示群 `@@M@@G@@` 与 `@@M@@a,b\in K[G]@@`，使 `@@M@@ab=1@@` 而 `@@M@@ba\ne1@@`，否定 Kaplansky 直接有限性猜想；同组元素又给出单而不满的元胞自动机，连带否定 Gottschalk 满射性猜想。

## 问题背景

Kaplansky 猜想问：群代数 `@@M@@K[G]@@` 中 `@@M@@ab=1@@` 是否必蕴含 `@@M@@ba=1@@`？sofic 群上答案肯定（Elek–Szabó 的稳定有限性定理），故反例群必非 sofic——而"是否每个群都 sofic"本身是著名未决问题。另一条线是 Gottschalk 1973 年的 surjunctivity 猜想：群上每个单射元胞自动机（cellular automaton）必满射；已知 surjunctive 群的群代数稳定有限（Phung 等），两个猜想在有限域上相通。技术难点在于：先造出矩阵反例 `@@M@@AB=I\ne BA@@` 并不自动给出标量反例；Dykema–Juschenko 证明可用与有限群的直积实现传递，本文首次给出完整而显式的实现。

## 主要结果

定理：存在特征二有限域 `@@M@@K@@`、含奇素数阶元的有限展示群 `@@M@@G@@`，以及由可终止的有限处方（terminating prescription）显式指定的 `@@M@@a_{\mathrm{out}},b_{\mathrm{out}}\in K[G]@@`，使得

`@@M@@Da_{\mathrm{out}}b_{\mathrm{out}}=1,\qquad b_{\mathrm{out}}a_{\mathrm{out}}\ne1 .@@`

两个乘积断言均有不依赖群字问题判定程序的代数证书。推论：该群非 sofic；以 `@@M@@b_{\mathrm{out}}@@` 的支集为记忆集、其系数为局部规则的元胞自动机 `@@M@@T_{b_{\mathrm{out}}}:K^G\to K^G@@` 单而不满，其像恰为 `@@M@@T_{b_{\mathrm{out}}a_{\mathrm{out}}}@@` 的不动点集——某个点指示构形 `@@M@@\delta_h@@` 不在像中，故 Gottschalk 猜想被否定。借同族嵌入定理，反例还可迁移到 `@@M@@F_\infty@@` 型群。

## 证明思路

证明沿"组合数据→群→代数元素"三层铸造。第一层是组合判据：取有限点集 `@@M@@V@@`（`@@M@@|V|=t@@`）与线族 `@@M@@\mathcal F@@`，使每点恰属 `@@M@@D=\ell+1@@` 条线（`@@M@@\ell@@` 为奇素数）、点线关联图围长（girth）`@@M@@\ge12@@`；再取向量 `@@M@@x_v\in K^m@@` 满足 `@@M@@\sum_{v\in V}x_vx_v^{\mathsf T}=-I_m@@`、每条线上 `@@M@@\sum_{v\in f}x_vx_v^{\mathsf T}=0@@`、以及 `@@M@@m<t\le m\ell^2@@`。满足这些有限数据即可铸出反例。

第二层由数据建群与元素。在每个点放加法群 `@@M@@\mathbb F_\ell^2@@` 的拷贝 `@@M@@K_v@@`、每条线放一维子群 `@@M@@L_f@@`，按长度至多三的零和关系生成群；平面平衡论证（欧拉公式配围长条件）保证子群真正嵌入。代数上取子群平均 `@@M@@P_v=\ell^{-2}\sum_{u\in K_v}u@@`（幂等元），用分解式 `@@M@@1+\sum_{f\ni v}\bigl(\sum_{u\in L_f}u-1\bigr)@@` 与向量配对式相乘，得矩形恒等式 `@@M@@UT=I_m@@`。为把 `@@M@@t@@` 个中间坐标压入 `@@M@@m@@` 个槽位，作 HNN 扩张（HNN extension）加入稳定字母 `@@M@@\tau_v@@` 实现特征扭转 `@@M@@\tau_v eP_v\tau_v^{-1}=eQ_{\alpha_v}@@`：中心特征幂等 `@@M@@e@@` 与两两正交的特征幂等 `@@M@@Q_\alpha@@` 使共享槽位的坐标互不串扰，从而得到方阵 `@@M@@a_{\rm mat}b_{\rm mat}=I_m@@`。检测反向缺陷最见功力：三明治计算 `@@M@@J_0(b_{\rm mat}a_{\rm mat}-I_m)C=e(TU-P)@@` 把问题拉回子群代数，再用特殊化同态 `@@M@@\varepsilon(nz^r)=\zeta^r@@` 化为 `@@M@@X^{\mathsf T}X-I_t@@`；因 `@@M@@t>m@@` 而秩亏，此矩阵非零。最后在有限群 `@@M@@F=(\mathbb Z/\ell)^m\rtimes S_m@@` 中构造矩阵单位 `@@M@@p_{ij}@@`，把矩阵代数单射嵌入群代数，补上正交补 `@@M@@1-\sum_i p_{ii}@@`，即得标量元素。

第三层供给组合数据。在 `@@M@@Q^n@@`（`@@M@@|Q|=q=2^h@@`）中删去洞集 `@@M@@O@@`；取 `@@M@@\ell@@` 为模 `@@M@@q^{100}@@` 同余 `@@M@@-1@@` 的最小素数（Linnik 定理保证其存在且不太大）。洞上的 Newton 插值多项式给出向量 `@@M@@x_v@@`：次数 `@@M@@\le q-2@@` 的多项式在整条仿射线上求和为零，而洞处的值为坐标单位向量，相减恰得 `@@M@@\sum_{v\in V}x_vx_v^{\mathsf T}=-I_m@@`。线系先按方向分块，再做局部交换——把过洞的 `@@M@@q@@` 条线换成 `@@M@@q-1@@` 条避开洞的平行线，保持每点度数不变；随机选取二维子空间并配合 Lovász 局部引理（文中自证）排除三角形、矩形、五边形等短关联圈。收尾用从 `@@M@@h=2@@` 起的字典序有限搜索确定全部选择，处方可终止。

## 可信度与备注

本文主结果已 Lean 形式化。它是本结果族的枢纽：行列式姊妹篇直接引用其定理作存在性输入，无挠姊妹篇再以独立构造去掉挠。注意构造显式使用奇阶挠与特征二（正则度 `@@M@@D=\ell+1@@` 在特征二为零，使线恒等式与总恒等式相容），系数域是有限域但未断言为 `@@M@@\mathbb F_2@@`；处方只证明了终止性而未实际执行。按 OpenAI 官方声明，未经形式化的结果可能有问题——本文主结果不在此列。

{% endraw %}
