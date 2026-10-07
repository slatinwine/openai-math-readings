---
layout: default
title: "A uniformly discrete counterexample to bounded approximation in Lipschitz-free spaces"
family: "330"
discipline: "Functional analysis"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A uniformly discrete counterexample to bounded approximation in Lipschitz-free spaces

> 结果族 330：A uniformly discrete counterexample to bounded approximation in Lipschitz-free spaces　·　学科：Functional analysis　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

构造出可数且一致离散的度量空间，其 Lipschitz 自由空间有逼近性质（AP）却无有界逼近性质（BAP），否定回答了 Kalton 的公开问题，并顺带得到实 \(\ell_1\) 上不具度量逼近性质的等价范数。

## 问题背景

对点 \(x\) 的赋值泛函 \(\delta_x\) 张成的 Banach 空间 \(\mathcal{F}(M)\) 称为 Lipschitz 自由空间（Lipschitz-free space），源自 Arens 与 Eells 的分子空间，是 Godefroy–Kalton 研究度量线性化问题的核心工具。Banach 空间 \(X\) 有逼近性质（approximation property, AP），指恒等算子在每个紧集上可被有限秩算子一致逼近；有界逼近性质（bounded approximation property, BAP）进一步要求这些算子的范数共用一个有限上界。Kalton 在 2004 年证明一致离散空间的自由空间必有 AP，并追问 BAP 是否也成立；该问题被 Godefroy–Ozawa 以及 Godefroy 的综述反复重申。困难在于已知的安全区太宽：Dalet 证明可数真空间（proper，闭球皆紧）的自由空间甚至有度量逼近性质，而 Smith 此前的反例只是离散、缺少公共距离下界，一致离散的情形一直悬而未决。

## 主要结果

主定理：存在可数、无界、非真的点基度量空间（pointed metric space）\((M,d,o)\)，相异点距离 \(\ge1\)，使 \(\mathcal{F}(M)\) 有 AP，但对每个有限 \(\lambda\ge1\) 都不满足 \(\lambda\)-BAP。核心是块定理：对每个整数 \(p\ge1\)，构造有界块 \(M_p\)（直径 \(\le B_p=300p^2+150p+5\)，分离 \(\ge1\)）与有限锚点集（anchor）\(A_p\)，使得任何范数 \(\le p\) 的有界有限秩算子 \(T_0\) 必在某个锚点上出错：\(\max_{a\in A_p}\|T_0\delta_a-\delta_a\|\ge\frac12\)。注意每个块自身却具有 \(2B_p\)-BAP——障碍只针对小范数算子。由系数识别 \(\mathcal{F}(M_p)\cong\ell_1\) 得推论：实 \(\ell_1\) 上存在等价范数 \(\|\cdot\|_p\) 满足 \(\frac12\|c\|_1\le\|c\|_p\le B_p\|c\|_1\)，具有 \(2B_p\)-BAP 却不满足 \(p\)-BAP；取 \(p=1\) 即得到不具度量逼近性质（MAP）的等价范数，直接否定回答了"\(\ell_1\) 的每个等价范数是否都有 MAP"。再由 Kalton 的网定理推出：同一空间 \(\mathcal{F}(M)\) 虽有 AP，在非线性意义下却不可逼近（approximable）。

## 证明思路

证明围绕"固定的有限锚点集击败一切范数 \(\le p\) 的有限秩算子"展开，选择顺序极其讲究：先固定全部确定性数据，再接待算子。

先造块。取参数 \(L=10p\)、\(R=30p\) 等；用 Friedman 的独立置换模型构造确定性的 \(\Delta\)-正则多重图列 \(G_m\)，以初等探索论证加二阶矩证明其经验根邻域统计收敛到独立均匀染色的 \(\Delta\)-正则树（Benjamini–Schramm 视角，不用谱估计）。每个源顶点以"到各颜色类的截断距离"为标签（label），同标签顶点经长 \(R\) 的边挂到同一锚点，锚点之间再互连，得到有界而分离 \(\ge1\) 的度量块；半径 \(2L\) 的小球仍困在单个源图内且点数有限。

再把算子化为测度。有限秩算子经微扰后范数至多 \(2p\)，且像落在有限支撑 \(S\) 的评价张成上；把 \(T\delta_x\) 的系数看作 \(S\) 上的带号测度（signed measure）\(\mu_x\)，总质量为 \(1\)、总变差 \(\le V=1+4pB\)。由标签定义的凸起函数 \(b_x\)（值域 \([0,L]\)，斜率 \(\le L/K\le1\)）在锚点 \(a(x)\) 处取峰值 \(L\)，结合范数控制与锚点逼近得 \(\int b_x\,d\mu_x\ge\frac{3L}{4}\)：测度质量被迫集中在标签相近处，且符号可任意。

然后证明匹配行走稀少。所谓匹配行走（matched walk），是每步都有标签相容且相距 \(\le2L\) 的支撑点跟随的非回溯行走。极限树上非回溯行走沿途颜色相互独立，而每个支撑点只容许至多 \(H\) 种颜色、\(Q\) 个后继，颜色总数 \(k>2\Delta QH\) 使长度 \(n\) 的匹配行走比例随 \(n\) 指数衰减，故可选 \(n\) 与足够大的图，使坏顶点占比 \(<\frac1{20V}\)。

接着造测试函数。在好顶点上，对每个支撑状态记录各方向最长匹配行走的长度，唯一严格最大者称例外方向（exceptional direction），每状态至多一个；关键组合引理是：若一条边的两端各有一个相容且相近的支撑点，则至少一端的配置必须放弃，否则两个有限记录会互相严格超过对方而矛盾。据此在关联 \(e:x\to y\) 上规定测试一端取 \(b_x\)、另一端取 \(-b_y\)，用 McShane 公式加截断得 1-Lipschitz 函数 \(f_e:M_p\to[-L,L]\)。

最后平均导出矛盾。测试给出 \(\int f_e\,d(\mu_x-\mu_y)\ge\frac{3L}{2}-2L\times(\text{例外质量})\)，而范数给出上界 \(\le2p\)；对均匀随机关联取期望，好顶点上每状态至多一个例外方向使例外质量平均 \(\le\frac{V}{\Delta}<\frac1{20}\)，坏顶点贡献 \(<\frac1{20}\)，于是下界平均 \(\ge\frac{11L}{10}=11p>2p\)，矛盾。最后把各块在公共基点粘成楔形（wedge）：每块的收缩诱导自由空间上的收缩复合，故整体的 BAP 必传给每个块而撞上块障碍；AP 则先保留有限块、再用各块自身的 \(2B_p\)-BAP，允许范数上界随紧集增大而增长。

## 可信度与备注

本结果族在本批次仅此一篇手稿，主结果尚无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。文中与既有文献的互相定位可作旁证：Smith 的离散反例缺公共距离下界，本文补足一致离散性；Dalet 的真空间定理解释了反例为何必须非真；Cúth–Kalenda 证明的一致离散自由空间量化 Schur 性质则约束此类空间的序列行为。图极限与组合平均环节技术性较强，此处从略，建议读者对照原文核验细节。

{% endraw %}
