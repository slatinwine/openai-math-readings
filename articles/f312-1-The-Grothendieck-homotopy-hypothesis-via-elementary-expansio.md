---
layout: default
title: "The Grothendieck homotopy hypothesis via elementary expansions"
family: "312"
discipline: "Topology"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Grothendieck homotopy hypothesis via elementary expansions

> 结果族 312：The Grothendieck homotopy hypothesis　·　学科：Topology　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文对 Ara–Henry 约定下的每个 Grothendieck 余凝子证明了同伦假设（homotopy hypothesis）：其弱球状 ∞-群胚与拓扑空间经 Quillen 等价互相再现，纯代数对象完整刻画空间的同伦论；关键一步是肯定回答 Henry 的推出猜想——初等扩张保持一切同伦群。

## 问题背景

同伦假设源自 Grothendieck 1983 年手稿《Pursuing Stacks》：能否用弱球状 ∞-群胚（weak globular ∞-groupoids）——带高阶凝聚运算的纯代数对象——刻画拓扑空间的同伦论？Maltsiniotis 随后用余凝子（coherator）精确记录这些运算的选择。难点有二：严格球状 ∞-群胚在同伦群保持的实现下只能表出 Eilenberg–Mac Lane 空间之积（Ara 2013），故"弱化"是实质性的；而不同余凝子给出不同的代数范畴，须逐个验证。Henry 在 2016 年把问题归结为推出猜想（pushout conjecture）：对由球状胞腔粘成的 `@@M@@X@@`，任选 `@@M@@n@@`-胞腔 `@@M@@a@@`，自由地添加平行胞腔 `@@M@@a'@@` 及连接胞腔 `@@M@@a\to a'@@`，所得 `@@M@@X\to X^+@@` 是否为弱等价？这一自由构造会连带产生无穷多个复合与凝聚胞腔，控制它们的同伦类正是卡点；Henry 已证明由它即可导出典范半模型结构及与空间的比较。

## 主要结果

先定义初等扩张（elementary expansion）：在 `@@M@@\Mod(\mathcal C)@@` 中沿 `@@M@@a:D_n\to X@@` 取源嵌入 `@@M@@s_n:D_n\to D_{n+1}@@` 的推出，得 `@@M@@i:X\to X^+@@`。

主定理：固定 Ara–Henry 约定下任意 Grothendieck 余凝子 `@@M@@\mathcal C@@`，`@@M@@X@@` 为胞腔式（cellular）`@@M@@\mathcal C@@`-∞-群胚（由初始模型经超穷次边界粘贴得到），`@@M@@n\ge 0@@`，`@@M@@a@@` 可为任一胞腔——包括复合或凝聚胞腔——则 `@@M@@i@@` 是弱等价（weak equivalence），即在分量（components）`@@M@@\pi_0@@` 上双射、在一切基点同伦群（based homotopy groups）`@@M@@\pi_r@@` 上同构。这肯定了 Henry 推出猜想，且直接处理任意胞腔式对象。

推论有二。其一，`@@M@@\Mod(\mathcal C)@@` 承载典范的余纤维生成左半模型结构（left semi-model structure）：弱等价恰为上述 `@@M@@\mathcal W@@`，余纤维为 `@@M@@I@@`-余纤维，所有对象皆 fibrant。其二，几何实现（geometric realization）与基本 ∞-群胚（fundamental ∞-groupoid）的伴随 `@@M@@|-|:\Mod(\mathcal C)\rightleftarrows\Spaces:\Pi_\infty@@` 是 Quillen 等价（Quillen equivalence），故 `@@M@@\Mod(\mathcal C)[\mathcal W^{-1}]\simeq\operatorname{Ho}(\Spaces)@@`——同伦假设对每个这样的余凝子成立，所得同伦论也不依赖于余凝子的选择。

## 证明思路

全文贯穿三个"阶"：固定截断 `@@M@@q@@` 时对扩张指标 `@@M@@n@@` 作下降归纳；每一步内对圆柱维数 `@@M@@j@@` 作上升归纳；解释运算时沿用 `@@M@@\mathcal C@@` 原有的自由生成阶，绝不按输出维数重排。

第一步把弱等价改写为精确边界判据（Ara 的检验法）：`@@M@@f\in\mathcal W@@` 当且仅当对每个指定边界 `@@M@@b:\partial D_r\to X@@` 与 `@@M@@Y@@` 中边界为 `@@M@@fb@@` 的 `@@M@@r@@`-胞腔 `@@M@@y@@`，存在边界恰为 `@@M@@b@@` 的 `@@M@@r@@`-胞腔 `@@M@@x@@` 及一个 `@@M@@(r+1)@@`-胞腔 `@@M@@fx\to y@@`。配合除法演算与换基引理，论证从此只与单个胞腔及其连接同伦打交道。

第二步设截断反射 `@@M@@R_q@@`：反射到 `@@M@@q@@`-余骨架（`@@M@@q@@`-coskeletal）模型，即高于 `@@M@@q@@` 维的每个边界有唯一填充；单位映射保持不超过 `@@M@@q@@` 维的全部胞腔。由于一次边界检验只涉及有限多个维数，最后取 `@@M@@q\ge\max\{n+1,k+1\}@@`，检验盘与其同伦见证都活在截断之内，结论即可搬回原范畴。

第三步是核心的下降归纳。顶端 `@@M@@n=q@@` 由单元收缩与唯一高维填充直接给出。归纳步设高于 `@@M@@n@@` 的扩张皆为弱等价，先证"上部胞腔分裂"引理：仅用 `@@M@@j>n@@` 的边界粘贴构造出的弱等价可分裂（容许收缩），且在胞腔式推出后仍是弱等价。再证树图可缩性：把有限树与同顶点的线性串比较，复合比较在生成边上同伦于恒等；随后用已被归纳覆盖的 `@@M@@J_{n+1}@@` 扩张复制顶部生成元，借助自由性与三分律（two-out-of-three）把逐条同伦升格为整个树模型的可缩性。

第四步构造部分圆柱（partial cylinders）`@@M@@P_j@@`：低于 `@@M@@n@@` 维一律不动，`@@M@@n@@` 维的圆柱就是一个 `@@M@@(n+1)@@`-胞腔，更高维则用上部边界粘贴经小对象构造补全，使相容数据沿公共面拼合。骨架粘合公式把表示相容圆柱组的对象逐维拼出，配合分裂引理证得它们皆可缩；于是能按 `@@M@@\mathcal C@@` 的原自由顺序解释全部运算，得到路径函子 `@@M@@\mathcal P@@` 及端点 `@@M@@p_0,p_1@@`：单个端点提升一切边界嵌入 `@@M@@I_j@@`，联合 `@@M@@(p_0,p_1)@@` 提升当前的 `@@M@@J_n@@`——其表示对象是四点树 `@@M@@y_0\!-\!x_0\!-\!x_1\!-\!y_1@@` 上的自由模型，恰为可缩。收尾：`@@M@@p_0@@` 的截面给出自映射 `@@M@@u=p_1h\in\mathcal W@@`；联合提升把比较扩张到 `@@M@@Y@@` 得 `@@M@@v=iur\in\mathcal W@@`；`@@M@@iu@@` 是 `@@M@@v@@` 的收缩，由收缩封闭性与三分律最终推出 `@@M@@i\in\mathcal W@@`。

## 可信度与备注

按任务标注，主结果已配 Lean 形式化（结果族附 Lean 文档），验证状态较强。本篇是结果族的基石：扩张定理补上了 Henry 框架缺失的一环，半模型结构与 Quillen 等价两条推论随即落地，并把三维情形（Henry–Lanari 2023）推广到任意维、任意余凝子。依 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，细节仍宜以社区核验为准。

{% endraw %}
