---
layout: default
title: "A high-arity counterexample to Pixton completeness in Chow"
family: "053"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A high-arity counterexample to Pixton completeness in Chow

> 结果族 053：A counterexample to Pixton completeness in Chow　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

稳定曲线的模空间像一本极厚的账本，记录所有"带标记点的曲线家族"的相交数字；账本里只有少数标准科目（重言类），科目之间的恒等式就是记账规则。Pixton 在 2012 年给出了一整套规则，并被猜想是完备的——凡是真实账目中归零的条目，都能用这套规则解释掉。本文翻出一笔账：它确实归零，却怎么套用规则都解释不通，于是"规则手册完备"被推翻。

**关键词卡片**

- 模空间（moduli space）：把同形状曲线各记一格的分类大厅，`@@M@@\overline{\mathcal M}_{g,n}@@` 参数化亏格 `@@M@@g@@`、`@@M@@n@@` 个标记点的稳定曲线。
- 重言类（tautological class）：由余切类 `@@M@@\psi@@`、`@@M@@\kappa@@` 类与边界阶层生成的"标准科目"。
- Chow 环（Chow ring）：代数闭链按有理等价打包成的环，账本里的"真实账目"。
- Pixton 关系（Pixton relations）：Pixton 给出的稳定图公式关系组，曾被猜想完备。
- 稳定图（stable graph）：记录边界阶层形状的组合图，形式记账的骨架。

**看个具体例子**

取亏格 `@@M@@g=10^{60}@@`、标记点数 `@@M@@n=3\binom{10^{60}}{3}@@`，用 `@@M@@g@@` 种颜色按三元组构造因子相乘再反对称化，得到类 `@@M@@Y@@`。定理：`@@M@@q(Y)=0@@`（在 Chow 环中为零，有理上同调中也为零），但 `@@M@@Y\notin\mathcal P_{g,n}@@`（不在 Pixton 关系张成的子空间中）。图中 `@@M@@Y@@` 落在"真实为零"的大框内、却在"规则解释"的小框外：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <rect x="60" y="50" width="440" height="150" rx="14" fill="none" stroke="#333" stroke-width="2"/>
  <text x="280" y="42" text-anchor="middle" font-size="13" fill="#333">ker q：在 Chow 环（及有理上同调）中真的为零的关系</text>
  <rect x="100" y="80" width="210" height="90" rx="10" fill="none" stroke="#06c" stroke-width="2"/>
  <text x="205" y="118" text-anchor="middle" font-size="13" fill="#06c">Pixton 关系张成的空间 P</text>
  <text x="205" y="142" text-anchor="middle" font-size="12" fill="#06c">（曾被猜想就是全部）</text>
  <circle cx="400" cy="125" r="7" fill="#c00"/>
  <text x="400" y="105" text-anchor="middle" font-size="14" fill="#c00">Y</text>
  <text x="400" y="158" text-anchor="middle" font-size="12" fill="#c00">账面归零，规则解释不了</text>
  <text x="280" y="235" text-anchor="middle" font-size="13" fill="#333">参数：亏格 g = 10^60，标记点 n = 3·C(10^60, 3)</text>
</svg>

</div>

**为什么值得关心**

它同时推翻了 Pixton 完备性猜想的 Chow 形式与有理上同调形式，给 Mumford 相交理论划出精确边界；天文级的 `@@M@@g=10^{60}@@` 只是让组合论证够用，并非最小参数。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在亏格 `@@M@@g=10^{60}@@`、标记点数 `@@M@@n=3\binom{10^{60}}{3}@@` 的稳定曲线模空间上，本文显式构造了一个重言类 (tautological class) `@@M@@Y@@`：它在有理 Chow 环 (Chow ring) 中为零，却不属于 Pixton 原有关系系张成的子空间，从而同时推翻了 Pixton 完备性猜想的 Chow 形式与有理上同调形式。

## 问题背景

Mumford 于 1983 年开创了稳定曲线模空间的相交理论研究，对象是由 `@@M@@\psi@@` 类（余切类）、`@@M@@\kappa@@` 类 (kappa classes) 与边界阶层 (boundary strata) 生成的重言环 (tautological ring)。此后 Faber 与 Zagier 给出 `@@M@@\mathcal M_g@@` 上 `@@M@@\kappa@@` 类之间的超几何关系式，Pandharipande–Pixton 在 Chow 中证明了它们并猜想其完备；Pixton 2012 年把该系统推广为紧化空间 `@@M@@\overline{\mathcal M}_{g,n}@@` 上的稳定图 (stable graph) 公式，并猜想这组关系已经完备。Pandharipande–Pixton–Zvonkine 与 Janda 分别用 3-旋上同调场论与 `@@M@@\mathbb P^1@@` 的等变 Gromov–Witten 理论证明了这些关系在上同调与 Chow 中确实成立；但"完备性"——除它们之外再无其他关系——始终悬而未决。本文对此给出否定回答。

## 主要结果

记 `@@M@@S_{g,n}@@` 为带装饰稳定图的形式阶层代数 (strata algebra)，实现映射 `@@M@@q_{g,n}[\Gamma,\gamma]=\xi_{\Gamma*}\gamma@@` 把形式图类送入 `@@M@@A^*(\overline{\mathcal M}_{g,n};\mathbb Q)@@`；记 `@@M@@\mathcal P_{g,n}@@` 为 Pixton 图公式关系张成的子空间（它对粘合与遗忘运算封闭）。已知 `@@M@@\mathcal P_{g,n}\subseteq\ker q_{g,n}@@`，完备性猜想即断言 `@@M@@\ker q_{g,n}=\mathcal P_{g,n}@@` 对一切稳定对成立。

主定理：取 `@@M@@g=10^{60}@@`、`@@M@@D_*=\binom g3@@`、`@@M@@n=3D_*@@`。用 `@@M@@g@@` 种颜色，对每个递增颜色三元组 `@@M@@J=(a,b,c)@@` 取因子
`@@M@@DF^{\mathrm{st}}_J=\bar D_{ab}\bar D_{ac}-\tfrac12\,\beta^{\mathrm{st}}_J,@@`
其中 `@@M@@\bar D_{ab}=\sum_{T\supseteq\{a,b\}}D_T@@` 是截下有理尾巴 (rational tails) 的除子求和，`@@M@@\beta^{\mathrm{st}}_J@@` 是支撑在双节点有理桥 (rational bridges) 上的图和；把全部因子相乘，再对保持颜色字的置换取反对称化和，得到 `@@M@@Y\in S_{g,n}^{2D_*}@@`。定理断言
`@@M@@Dq_{g,n}(Y)=0,\qquad Y\notin\mathcal P_{g,n},@@`
即该等式对此稳定对失效。由于闭链类映射 (cycle class map) 与 Chern 类、乘积及正常前推交换，Chow 中的零化自动给出有理上同调中的零化，故 `@@M@@\mathcal P_{g,n}\subsetneq\ker q^H_{g,n}@@`：推论表明有理上同调形式的完备性同样不成立。值得注意：完备性不同于 Gorenstein 性质；Canning–Larson–Schmitt 此前在紧型 (compact type) 空间上证明的完备性不受影响，本反例位于完全稳定紧化上、针对原始完整关系系。

## 证明思路

证明分两条相互独立的支线（论文的证明结构图明确区分了这两件事）。第一条证"不在关系空间中"，纯形式、不经过 Chow 环：构造一个检测器 (detector)。系数环取外代数 `@@M@@R=\Lambda(\theta_{ijk})@@`，每个颜色三元组给一个独立奇生成元；状态空间是 `@@M@@R@@` 上的超交换 Frobenius 代数 (Frobenius algebra)，奇部分 `@@M@@W@@` 是 `@@M@@2g@@` 维纯奇辛空间 (symplectic space)，三线性型 `@@M@@\Phi(a_i,a_j,a_k)=\theta_{ijk}@@` 只在拉格朗日 (Lagrangian) 子空间 `@@M@@W_+@@` 上取值。检测器 `@@M@@t_m@@` 丢弃一切非有理尾巴的图，把有理分支按二维拓扑场论式的 Frobenius 乘法与余积求值，根顶点则用上述代数测试。先证 `@@M@@t_m@@` 湮灭整个 `@@M@@\mathcal P_{g,n}@@`：对标记数、次数、分拆长度作三重归纳，归约到全 1 指标情形后，计数显示每个存活项都需从 `@@M@@g@@` 维空间 `@@M@@W_+^\vee@@` 中取多于 `@@M@@g@@` 个坐标，必为零；再直接算出 `@@M@@t_n(Y)@@` 与颜色字的配对为 `@@M@@\pm\bigl(\binom{g-1}{2}!\bigr)^g\prod_{i<j<k}\theta_{ijk}\neq0@@`，故 `@@M@@Y\notin\mathcal P_{g,n}@@`。

第二条证"在 Chow 中为零"，是几何主线。先为光滑曲线族建立忠实张量模型 (faithful tensor model)：利用辛群表示论的第一、第二基本定理与 O'Sullivan 型半单张量重构，把曲线的全部相对 Chow 对应 (correspondences) 无损地装入 `@@M@@\mathfrak B\otimes(\mathbb Q1\oplus W_b\oplus\mathbb Qe)@@`；投影后的小对角线 (small diagonal) 成为带奇系数的交错三次型 `@@M@@\varphi@@`，即 Gross–Schoen 修正对角线的族版本。再取曲面 `@@M@@C\times C@@` 上带固定行列式的 Quot 概形 (Quot scheme)，用完美阻碍理论、虚拟局部化 (virtual localization) 与 Ellingsrud–Göttsche–Lehn 嵌套希尔伯特方案递归（本文推广到保留任意多个标记输出），得到等向三次的幂零恒等式 `@@M@@a\,T_\gamma^{t_0}=0@@`，其中 `@@M@@t_0=25(b-1)^2-1@@`；关键标量 `@@M@@a@@` 由生成级数与留数计算给出，且留数符号确定为正，故 `@@M@@a\neq0@@`、三次幂确实幂零。随后用辛 Lefschetz 分解的外理想引理，把等向测试升级为任意颜色输入的长乘积消失（模基中余维至少 `@@M@@b-1@@` 的支撑）。

最后过渡到紧化并收尾：借助 Hassett 权重稳定曲线与奇妙紧化 (wonderful compactification) 比较修正后的稳定三次与光滑三次，系数 `@@M@@-1/2@@` 的有理桥修正恰好抵消三重例外项，误差只剩"噪声项"（双槽运算乘单槽运算）与正余维基支撑。于是对基像维数作支撑归纳 (support induction)：重基初始维数 `@@M@@3g-3@@`，每次推进严格降维，至多 `@@M@@3g-2@@` 步；配合颜色预算分账（预留 `@@M@@4K+20@@` 个大小 `@@M@@m_0=2000g^{2/3}@@` 的色块，`@@M@@K=10^5@@`；亏格亏量小时用大顶点曲面测试消耗预留块，亏量大时用 Schur–Weyl 交错与辛收缩的重色测试），保证每一步都有足够条目可用，直到支撑为空，乘积在权重空间中为零；拉回并与 `@@M@@q_{g,n}(Y)@@` 比较即得消失。`@@M@@g=10^{60}@@` 这个骇人参数正是为了让有限分账始终够用，作者明确说明它并非最小参数。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，而 OpenAI 官方声明"未经形式化的结果可能有问题"；此文涉及大量组合分账与局部化计算，尤其需要社区逐行核验。本结果族（053）在本批文集中仅此一篇手稿，没有姊妹篇互相支撑。反例与紧型空间上的正面完备性结果、以及与 Gorenstein 性质的讨论均不冲突；参数远非最小，结论的定性部分（原始 Pixton 系不完备）是核心。

{% endraw %}
