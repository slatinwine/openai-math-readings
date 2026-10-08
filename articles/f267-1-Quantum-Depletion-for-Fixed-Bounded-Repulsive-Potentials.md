---
layout: default
title: "Quantum Depletion for Fixed Bounded Repulsive Potentials"
family: "267"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quantum Depletion for Fixed Bounded Repulsive Potentials

> 结果族 267：Positive-temperature Bose–Einstein condensation and exact quantum depletion　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

换一副柔软的手套：把硬邦邦的"小球"换成一片有限高、有限范围、只推不拉的光滑力场，被挤出舞池的比例会变吗？这篇论文证明：不变。损耗只认"散射长度"这一个数，力场的具体形状无关紧要——Bogoliubov 损耗定律的普适性，就此拿到第二块拼图。

**关键词卡片**

- 有界排斥势（bounded repulsive potential）：有限高度、有限范围、处处非负的径向相互作用 `@@M@@v\ge 0@@`。
- 散射长度（scattering length）a_v：由零能散射方程定义的"有效半径"，是唯一进入损耗公式的位势参数。
- 量子损耗（quantum depletion）：零温基态中处于常值轨道之外的粒子比例。
- 基态密度矩阵：最低本征空间上的迹一正算符；结论对一切这样的密度矩阵一致，不挑基向量。
- 迭代极限：位势全程固定，先取热力学极限再取稀薄极限。

**看个具体例子**

数字版定理：对每个这样的位势 `@@M@@v@@`，比值 `@@M@@\frac{1-B_\Gamma}{\sqrt{\rho a_v^3}}@@` 沿一切热力学聚积值都落入 `@@M@@\frac{8}{3\sqrt\pi}\approx 1.5045@@` 的 `@@M@@\epsilon@@`-邻域——硬球的"墙"与有界势的"鼓包"殊途同归。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="30" y="28" font-size="14">硬球：不可逾越的墙</text>
  <line x1="60" y1="180" x2="230" y2="180" stroke="#333" stroke-width="1.5"/>
  <line x1="60" y1="180" x2="60" y2="70" stroke="#333" stroke-width="1.5"/>
  <path d="M 100 180 L 145 180 L 145 80 L 185 80" fill="none" stroke="#b3442e" stroke-width="2.5"/>
  <text x="150" y="70" font-size="13" fill="#b3442e">V = ∞（r &lt; a）</text>
  <text x="192" y="197" font-size="13">r = a</text>
  <text x="70" y="215" font-size="12">确定性几何约束</text>
  <text x="320" y="28" font-size="14">有界势：有限高的鼓包</text>
  <line x1="310" y1="180" x2="520" y2="180" stroke="#333" stroke-width="1.5"/>
  <line x1="310" y1="180" x2="310" y2="70" stroke="#333" stroke-width="1.5"/>
  <path d="M 330 180 Q 415 50 500 180" fill="none" stroke="#4a7ebb" stroke-width="2.5"/>
  <text x="352" y="105" font-size="13" fill="#4a7ebb">0 ≤ v ≤ J，有限范围</text>
  <text x="330" y="215" font-size="12">Boltzmann 软权重</text>
  <text x="105" y="252" font-size="14">两者给出同一个损耗公式：8/(3√π) · √(ρa³)</text>
</svg>

</div>

**为什么值得关心**

硬球（确定性几何约束）与有界势（Boltzmann 软权重）的难点互为对偶；两篇姊妹工作共用"盒内变化＋盒间平均变化"的拆分与删除测度技术，共同确立损耗只依赖散射长度的普适性。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

把 Bogoliubov 量子损耗定律推广到固定有界排斥位势：对三维径向、非负、有限程位势 `@@M@@v@@`（散射长度 `@@M@@a_v@@`），基态在常值轨道之外的占比沿一切热力学聚积值均为 `@@M@@\frac{8}{3\sqrt\pi}\sqrt{\rho a_v^3}+o(\sqrt{\rho a_v^3})@@`；位势固定，先取热力学极限再取稀薄极限，对一切基态密度矩阵一致。

## 问题背景

Bogoliubov 理论预言稀薄玻色气体的主导损耗只通过散射长度（scattering length）依赖相互作用，与位势形状无关。硬球情形由同族姊妹篇处理；本文考虑固定的有界径向排斥位势，两者难点互为对偶：硬球是无限强的确定性几何约束，而有界势虽柔和，其路径权重却是 Boltzmann 因子，硬球论证里的确定性避碰估计不再可用。此前固定密度下的占据与损耗结果多处于耦合极限（如单盒、散射长度量级 `@@M@@N^{-1}@@`），固定密度普通热力学极限下的有界势损耗一直未定。附带一点：有界性使有限体积热半群保持 positivity improving，基态实际唯一；但定理仍以密度矩阵表述，不依赖基向量的选取。

## 主要结果

设 `@@M@@v:\mathbb R^3\to[0,\infty)@@` 有界可测、径向、紧支撑且在正测度集上非零，其散射长度 `@@M@@a_v>0@@` 由零能散射方程 `@@M@@(-\Delta+\tfrac12v)f=0@@`、`@@M@@f(x)=1-\frac{a_v}{|x|}@@`（大 `@@M@@|x|@@` 处）确定。环面哈密顿量 `@@M@@H^v_{N,L}=\sum_j(-\Delta_j)+\sum_{i<j}v_L(x_i-x_j)@@` 作用在对称波函数上，`@@M@@\mathcal G^v_{N,L}@@` 是其最低本征空间上的迹一正算子集合，`@@M@@B_\Gamma@@` 为常值轨道占据占比。定理 1.1：对每个这样的位势 `@@M@@v@@` 与 `@@M@@\epsilon>0@@`，存在 `@@M@@\rho_0(v,\epsilon)>0@@`，使得固定 `@@M@@0<\rho<\rho_0@@` 后，沿一切 `@@M@@N_k/L_k^3\to\rho@@` 的序列，

`@@M@@D\limsup_{k\to\infty}\ \sup_{\Gamma\in\mathcal G^v_{N_k,L_k}}\left|\frac{1-B_\Gamma}{\sqrt{\rho a_v^3}}-\frac8{3\sqrt\pi}\right|\le\epsilon.@@`

位势在两个极限中完全固定；结论覆盖占据的每个热力学聚积值，不要求固定正密度下占据极限存在；也不假设位势的径向单调性或 Fourier 变换正性。

## 证明思路

沿用硬球姊妹篇的拆分 `@@M@@1-B=\langle\Psi,(1-P_\ell)_1\Psi\rangle+\|(P_\ell-P_0)_1\Psi\|^2@@`，即"盒内变化加盒间平均变化"，但每一步都要为有界位势重做。能量部分直接处理有界势：采用散射长度重整化的正平方项、Neumann 盒局域化与 Bogoliubov 对角化；其中 Neumann 镜像相互作用与原相互作用的比较改为在期望层面用两粒子界完成，绕开了硬球论证中的逐点径向单调比较；局域下界同时保留动能隙与正的准粒子项，以便把能量计算传递到拆分式中的单体可观测量。第二块同样用删除测度 `@@M@@s_v@@`（按粒子在盒 `@@M@@v@@` 中的出现权重选出一个粒子并积掉其位置的浴分布）控制空间变化，但路径构造面对的是 Boltzmann 权重：把每个权重表示为一个辅助均匀变量的测试，并把这些测试保留在每个条件归一化中，既得到精确的相互作用律，又能沿用为硬球发展的碰撞估计；硬球的确定性计数界则由有界势姊妹篇（正温度、有界相互作用的凝聚论文）的密度尾估计替代——后者对温度一致，经 Gibbs 态随温度趋于零的迹范收敛直接用于基态。精度分两级：相邻小盒间的四阶矩比较实现从细平均到粗平均的过渡（核心不等式 `@@M@@(\sqrt{\mathbb E y^2}-\mathbb Ey)^2\le\frac12\mathbb E\frac{|y-y'|^4}{y^2+y'^2}@@`）；远盒间的二阶矩比较控制整环面上的剩余变化，路线可任意长，故费用只按两条独立抽样路线的相遇计费，而非每步固定损失；Hilbert 值数组上的远对谱隙引理（有限 Fourier 变换加 Parseval）解释了为何必须对宏观分离的盒对取平均。组装阶段：远盒比较给出均方根的方差 `@@M@@o(D^{-1})@@`，微观尺度上能量估计给出 `@@M@@\mathbb E\|s_v-m_v\|^2\le D^{-1}(\epsilon_j+o(1))@@`，四阶矩比较再把均方根换算为投影所需的算术平均；指数条件 `@@M@@w<u/10000@@` 保证 `@@M@@R^6D^{-1-u/8}=o(D^{-1})@@`，第二块被压到损耗标度之下。

## 可信度与备注

本篇暂无形式化证明，结论以社区核验为准。它是本族框架的第三块拼图：密度尾输入来自有界势正温度凝聚的姊妹篇，路线构造与局部、远距比较承接硬球损耗姊妹篇（其有限体积路线定理被直接引用），但硬球损耗定理本身并不是输入；三篇在尺度层级与路径技术上互相印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
