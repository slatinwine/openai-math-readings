---
layout: default
title: "Rational homology and Quillen's conjecture"
family: "310"
discipline: "Topology"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Rational homology and Quillen's conjecture

> 结果族 310：Quillen's conjecture in rational homology　·　学科：Topology　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文对一切有限群与一切素数证明了 Quillen 猜想（Quillen's conjecture）：若最大正规 `@@M@@p@@`-子群 `@@M@@O_p(G)@@` 平凡，则初等交换 `@@M@@p@@`-子群偏序集 `@@M@@\mathcal A_p(G)@@` 的增广约化有理同调非零、必不缩拢——比原猜想更强的有理同调形式。

## 问题背景

1978 年 Quillen 研究 `@@M@@G@@` 的初等交换 `@@M@@p@@`-子群偏序集 `@@M@@\mathcal A_p(G)@@`（顶点为同构于 `@@M@@(\mathbb Z/p\mathbb Z)^r@@` 的子群），猜测其单纯复形缩拢当且仅当 `@@M@@O_p(G)@@` 非平凡。这把"是否含正规 `@@M@@p@@`-结构"与"子群偏序集的拓扑"直接挂钩。他本人解决了可解群、`@@M@@p@@`-秩至多二与定义特征的 Lie 型群；Aschbacher–Kleidman（1990）与 Aschbacher–Smith（1993）相继处理殆单情形与 `@@M@@p>5@@`；Piterman–Smith（2025）与 Díaz–Ramos（2026）合力完成全部奇素数。剩余的硬骨头是 `@@M@@p=2@@`：消去工作已把极小反例的分量压缩到特征至少五的典型群，本文补上最后一击。

## 主要结果

主定理：对每个有限群 `@@M@@G@@` 与素数 `@@M@@p@@`，若 `@@M@@O_p(G)=1@@`，则增广约化同调 `@@M@@\widetilde H_*(\mathcal A_p(G);\Q)\ne0@@`（空偏序集约定 `@@M@@\widetilde H_{-1}=\Q@@`）。非空可缩复形的约化同调为零，空复形不可缩，故定理蕴含 Quillen 猜想，且无素数与合成因子限制。由万有系数定理（universal coefficient theorem），结论对任意域系数同样成立；反向地，`@@M@@O_p(G)\ne1@@` 时 `@@M@@\Ap(G)@@` 缩拢。于是"在任一固定域上零调（acyclic）"恰好刻画"存在非平凡正规 `@@M@@p@@`-子群"。

## 证明思路

证明分奇素数与 `@@M@@p=2@@` 两支，共用框架循环（frame cycles）与传播引理（propagation lemma）两台引擎。

先造循环。对典型群的模空间取线的框架分解（frame）：各线符号生成初等交换射影子群，其全子群旗支撑公寓链（apartment chain）。在仅差一个平面内结构的框架间强加线性关系，使公寓链边界相消，得循环空间 `@@M@@\mathcal Z(W)@@`。核心是定量估计：维数 `@@M@@h@@` 增长而基域固定时 `@@M@@\dim\mathcal Z(W)\ge F_h\,|\mathfrak F(W)|(h-1)!@@`，对称情形 `@@M@@F_h\ge(17/25)^h@@`。框架线合并树编码为李超代数（Lie superalgebra）超括号，经 Poincaré–Birkhoff–Witt 论证与"带标记因子"级数比较（近于 Golod–Shafarevich）把平面框架计数化为维数下界，分次保留、下降后仍可用；维数富余再以线性条件消去邻接交换自同构的新边界面，终得全旗上的非零循环。

再把循环送回 `@@M@@G@@`。构造可能先落在比 `@@M@@H=LA@@` 更大的自同构群：限制引理选交指标最大的支撑初等群，取留数（residue）后与 `@@M@@H@@` 相交，单射保住非零全旗系数。传播引理在 `@@M@@p=2@@` 极小反例中取极大忠实配置：先删去忠实的初等扩群（上区间缩拢），再把该循环与中心化子中归纳给出的非边缘循环作 shuffle 积，饱和留数检测出中心化子同调类，在 `@@M@@\Ap(G)@@` 中非零。

最后组装。奇素数经归约化为 `@@M@@\PSU_n(q)@@`（`@@M@@n\ge5@@`，`@@M@@p\mid q+1@@`）初等 `@@M@@p@@`-扩张的 Quillen 维数性质（Quillen dimension property，最大次数同调非零），作者以框架法直接证明、不假设分裂。`@@M@@p=2@@` 极小反例必有特征 `@@M@@\ge5@@` 的典型单分量：线性、酉群（维数 `@@M@@\ge5@@`）与辛群逐一排除，四维线性与酉群经 `@@M@@\mathrm P\Omega_6^{\pm}(q)@@` 同构并入正交类，仅剩 `@@M@@\F_5@@` 上平方判别式六维空间即 `@@M@@\PSL_4(5)@@`，以等价偏序集构造处理。清单耗尽，矛盾。

## 可信度与备注

主结果尚无 Lean 形式化证明；OpenAI 官方声明未经形式化的结果可能有问题，全文应以社区核验为准。归约骨架建立在已发表文献上（如 Piterman 2026 定理 B、Piterman–Smith 2025 定理 1.4），新贡献集中在框架循环、PBW 维数估计与传播机制；第六至九章各典型群的逐案验证技术性较强，此处从略。本文与 Díaz–Ramos（2026）的酉群定理互为印证、彼此支撑。

{% endraw %}
