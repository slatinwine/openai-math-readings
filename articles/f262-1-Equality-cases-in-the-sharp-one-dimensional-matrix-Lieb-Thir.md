---
layout: default
title: "Equality cases in the sharp one-dimensional matrix Lieb–Thirring inequality"
family: "262"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Equality cases in the sharp one-dimensional matrix Lieb–Thirring inequality

> 结果族 262：Sharp finite-matrix Lieb–Thirring inequalities and all equality cases　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把势能井想成捕鱼装置：投入材料（势能），收获能量（被捕获的粒子）。不等式说收获有上限；本文回答的是：效率百分之百的装置长什么样？当粒子有 m 条内部通道、井还可以随位置变形转向时，答案意外地干净：在某个固定方向下，每条通道独立挖一口标准形状的井，每口恰好捕住一条"鱼"；想让通道边走边转、或一口井捕多条鱼，统统办不到。

**关键词卡片**

- Lieb–Thirring 不等式（Lieb–Thirring inequality）：束缚能总和不超过"势的花费"乘最优常数。
- 束缚态（bound state）：被井捕获的负特征值所对应的粒子态。
- sech² 孤子（sech² soliton）：唯一能取等的井形，双曲正割平方轮廓。
- 酉基（unitary basis）：不随位置变化的通道方向；取等势必须在此基下呈对角。
- 直和（direct sum）：各通道的井互不混合的拼装方式。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="40" y="32" font-size="12">固定酉基下取对角：W = U·diag(w₁,…,w_k,0,…,0)·U*</text>
  <line x1="60" y1="110" x2="510" y2="110" stroke="#333" stroke-width="2"/>
  <path d="M120 110 C 155 106, 168 38, 205 38 C 242 38, 255 106, 290 110" fill="none" stroke="#369" stroke-width="2.5"/>
  <text x="66" y="100" font-size="13">通道 1</text>
  <text x="120" y="66" font-size="13">w₁ = 3a₁²·sech²(2a₁(x−x₁))</text>
  <text x="330" y="66" font-size="13">唯一特征值 −a₁²</text>
  <line x1="60" y1="215" x2="510" y2="215" stroke="#333" stroke-width="2"/>
  <path d="M345 215 C 372 212, 380 162, 398 162 C 416 162, 424 212, 452 215" fill="none" stroke="#c33" stroke-width="2.5"/>
  <text x="66" y="205" font-size="13">通道 2（尺度、中心独立）</text>
  <text x="320" y="150" font-size="13">w₂ = 3a₂²·sech²(2a₂(x−x₂))</text>
  <text x="60" y="258" font-size="14">通道互不混合，每口井恰一个束缚态 ⇒ 极值势至多 m 个负特征值</text>
</svg>

</div>

数字版（`@@M@@\gamma=1@@`、`@@M@@m=2@@`）：`@@M@@W=\operatorname{diag}(w_1,w_2)@@`，`@@M@@w_j=3a_j^2\operatorname{sech}^2\!\big(2a_j(x-x_j)\big)@@`，两通道特征值各为 `@@M@@-a_1^2@@`、`@@M@@-a_2^2@@`，尺度与中心完全自由。

**为什么值得关心**

它与端点情形"同一通道可容纳多个束缚态"的 KdV 多孤子结构形成鲜明对比，完整画出一维矩阵取等势的肖像。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对 `@@M@@1/2<\gamma<3/2@@` 与任意有限矩阵维数，本文把一维矩阵 Lieb–Thirring 不等式（Lieb–Thirring inequality）的取等势完全分类：在某个不随位置变化的酉基下，取等势恰是有限个标量 `@@M@@\mathrm{sech}^2@@` 孤子的直和加零通道，各孤子尺度与中心彼此独立，每个非零通道恰含一个束缚态，故极值势至多有 `@@M@@m@@` 个负特征值。

## 问题背景

Lieb–Thirring 不等式把薛定谔算子（Schrödinger operator）`@@M@@H_W=-d^2/dx^2-W@@` 的负特征值矩与势的积分幂作比较；等号问题追问：势必须怎样组织，才能让束缚能达到最优。一维标量单束缚态优化子具有双曲正割轮廓，其显式形式可追溯到 Keller 1961 年的单态变分问题与 Lieb–Thirring 1975–76 年关于费米子动能与物质稳定性的工作。当波函数有多个分量时，势成为矩阵，若干标量轮廓可以占据相互正交的内部通道；悬而未决的是，等号是否还允许随位置旋转的通道，或同一通道内多个束缚态的相互作用。端点对照令人警醒：Frank–Gontier–Lewin 已证明在 `@@M@@\gamma=3/2@@` 处标量优化子是 KdV 多孤子（multisoliton），同一标量通道可容纳多个束缚态。本文证明：在整个开区间上，等号情形一律是固定基下的独立标量轮廓。

## 主要结果

设 `@@M@@m\ge 1@@`、`@@M@@1/2<\gamma<3/2@@`、`@@M@@p=\gamma+1/2@@`，`@@M@@W:\mathbb R\to\mathbb C^{m\times m}@@` 可测、Hermitian、半正定，且 `@@M@@\int_{\mathbb R}\operatorname{tr}(W^p)\,dx<\infty@@`。记 `@@M@@\operatorname{Tr}(H_W)_-^\gamma=\sum_{\lambda_j<0}|\lambda_j|^\gamma@@`（计入重数）。定理断言

`@@M@@D\operatorname{Tr}(H_W)_-^\gamma\le C_\gamma\int_{\mathbb R}\operatorname{tr}(W^p),\qquad C_\gamma=\Big(\frac{\gamma-1/2}{\gamma+1/2}\Big)^{\gamma-1/2}\frac{\Gamma(\gamma+1)}{\sqrt\pi\,\Gamma(\gamma+3/2)}，@@`

且等号成立当且仅当存在 `@@M@@k\in\{0,\dots,m\}@@`、常值酉矩阵（unitary matrix）`@@M@@U@@`、正数 `@@M@@a_1,\dots,a_k@@` 与实数 `@@M@@x_1,\dots,x_k@@`，使得几乎处处

`@@M@@DW(x)=U\,\operatorname{diag}\big(w_1,\dots,w_k,0,\dots,0\big)\,U^*,\qquad w_j(x)=(r+1)\,a_j^2\,\mathrm{sech}^2\!\big(ra_j(x-x_j)\big)，@@`

其中 `@@M@@r=(\gamma-1/2)^{-1}@@`。各非零通道恰有一个负特征值 `@@M@@-a_j^2@@`，于是极值势的负特征值个数（计重数）至多为 `@@M@@m@@`；`@@M@@k=0@@` 对应零势。分类依赖严格不等式 `@@M@@r>1@@`，故仅对开区间断言。

## 证明思路

证明分四步。先在矩阵姊妹篇的作用方法（action method）之上强化下界：除平方项 `@@M@@\|A'-BA\|_{\mathrm{HS}}^2@@` 外，还保留同时控制换位子（commutator）`@@M@@[B,K^2]@@` 与余项 `@@M@@K^2-B^2-(AA^{\mathsf T})^r@@` 的定量亏量，其系数只依赖最大束缚能与指数、与试验函数个数无关——这一一致性必不可少，因为事先并不知道极值势只有有限个负特征值；所需的两个非负平方来自积分迹恒等式（integrated trace identity）。再证固定列数下的紧性：试验列表增长时 `@@M@@A@@` 的行数增加但列数固定为 `@@M@@m@@`，密度 `@@M@@AA^{\mathsf T}@@` 的秩至多 `@@M@@m@@`；保留亏量用尾部的小束缚能控制尾行，于是即使负特征值有无穷多个，也能得到强逐点收敛，并在极限中提取精确代数关系，把能量不同的行分开；极限关系还附带给出极值势的连续代表元，各块矩阵为 `@@M@@C^2@@`，并满足行特征函数方程 `@@M@@G_\alpha''=\alpha^2G_\alpha-G_\alpha W@@`。然后证通道固定并求解：由 `@@M@@G_\alpha'=B_\alpha G_\alpha@@` 与算子范数界，经 Gronwall 不等式知各能量块的核空间与位置无关，不同能量的行空间相互正交，非零方向至多 `@@M@@m@@` 个；在每个非零块上，`@@M@@B_0=D'D^{-1}@@` 满足矩阵 Riccati 方程 `@@M@@B_0'=r(B_0^2-\alpha^2 I)@@`，在一点对角化后由常微分方程解的唯一性始终保持对角，标量解为 `@@M@@b_j(x)=-\alpha\tanh\big(r\alpha(x-y_j)\big)@@`，代回 `@@M@@q(\alpha^2-b_j^2)@@` 即得 `@@M@@\mathrm{sech}^2@@` 轮廓。复 Hermitian 情形先实化为 `@@M@@W\oplus\overline W@@`（两边各量同时加倍，等号保持），用实情形结论加投影论证还原。最后验证充分性：取 `@@M@@w=a\tanh\big(ra(x-x_0)\big)@@`、`@@M@@Q=\partial_x+w@@`，一阶分解给出 `@@M@@Q^*Q=H+a^2@@` 与 `@@M@@QQ^*\ge a^2@@`（用到 `@@M@@r>1@@`），而 `@@M@@\ker Q@@` 一维，故 `@@M@@-a^2@@` 是唯一的负特征值；beta 积分算得 `@@M@@\operatorname{Tr}(H)_-^\gamma=a^{2\gamma}=C_\gamma\int V^p@@`，直和与酉共轭保持等号。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。结果族中标量常数篇的主结果已 Lean 形式化，矩阵不等式篇则给出本文所分类的这条不等式，三篇共享同一套作用方法、互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文与端点 `@@M@@\gamma=3/2@@` 处 KdV 多孤子结构的鲜明对比，尤其值得专家细察。

{% endraw %}
