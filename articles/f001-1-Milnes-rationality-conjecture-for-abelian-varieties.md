---
layout: default
title: "Milne's rationality conjecture for abelian varieties"
family: "001"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Milne's rationality conjecture for abelian varieties

> 结果族 001：Milne's rationality conjecture and algebraic specialization　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Milne 有理性猜想对 `@@M@@\overline{\mathbb Q}@@` 上具好约化的阿贝尔簇成立（含剩余特征 2）：任一有理 Hodge 类特化到约化簇后，与互补除子乘积的配对在所有 `@@M@@\ell\ne p@@` 的 `@@M@@\ell@@`-adic 实现与晶体上同调中等于同一个有理数，且可由单个有理代数闭链表示。

## 问题背景

设 `@@M@@A/\overline{\mathbb Q}@@` 是在某 `@@M@@p@@`-进位相处有好约化 (good reduction) 的阿贝尔簇 (abelian variety)。有理代数闭链的类与除子的交点数天然是有理数，且每种上同调实现算出同一个数；但若手里只有一个有理 Hodge 类 (Hodge class)，麻烦在于好约化可能"新增"不提升回 `@@M@@A@@` 的除子。Deligne 的绝对 Hodge 定理保证了该类在各实现间相容，却不能把它与这些新除子的配对识别为某个有理闭链的度数。Milne 在研究 Shimura 簇约化与 Langlands–Rapoport 猜想时提出这一有理性猜想（Milne 2000, Conjecture 6.1(A)；配对形式见其 AIM 讲义及 Milne 2009, Conjecture 4.1），并证明其对所有 CM 阿贝尔簇成立等价于特征 `@@M@@p@@` 中"有理 Tate 类的好理论"的存在性；此前已知的正例是具单普通约化 (simple ordinary reduction) 的 CM 簇及其全部幂（Milne 2009, Example 4.2）。

## 主要结果

主定理（Theorem 1.1）：设 `@@M@@A/\overline{\mathbb Q}@@` 为 `@@M@@d@@` 维阿贝尔簇，在位相 `@@M@@w@@` 处有好约化 `@@M@@A_0/\overline{\mathbb F}_p@@`，`@@M@@\gamma\in H^{2r}(A(\mathbb C),\mathbb Q(r))@@` 为有理 Hodge 类。则对 `@@M@@A_0@@` 上任意 Cartier 除子 `@@M@@D_1,\ldots,D_{d-r}@@`，存在同一个 `@@M@@q\in\mathbb Q@@`，使得在每个 `@@M@@\ell\ne p@@` 的 `@@M@@\ell@@`-adic 实现中 `@@M@@\Tr_\ell\bigl(\gamma_{0,\ell}c_{1,\ell}(D_1)\cdots c_{1,\ell}(D_{d-r})\bigr)=q@@`，同时在晶体上同调 (crystalline cohomology) 扩到 `@@M@@C_w@@` 后也有 `@@M@@\Tr_p\bigl(\gamma_{0,p}c_{1,\mathrm{cris}}(D_1)\cdots\bigr)=q@@`。由线性性，同一结论对任何互补余维的有理 Lefschetz 类 (Lefschetz class，即除子类的有理多项式) 成立，且对一切剩余特征（包括 `@@M@@p=2@@`）成立。两个推论：其一（Corollary 6.3），每个有理 Hodge 类的特化唯一地落入一个事先固定的有理 Tate 类好理论 `@@M@@\mathcal R@@`；其二（Corollary 6.4），结合姊妹篇的 CM Hodge 定理 [OpenAICMHodge2026, Theorem 1.1]，该特化类由单个有理代数闭链 `@@M@@z_\gamma\in\CH^r(A_0)_{\mathbb Q}@@` 在上述所有实现中同时表示。

## 证明思路

证明分四步，先搬运、再化归、然后二分、最后提升。第一步把一般 Hodge 类搬到 CM 簇上：以 `@@M@@A@@` 的 Mumford–Tate 群 (Mumford–Tate group) 为起点，经强容许 Hodge 型整模型与 Kisin–Zhou 的特殊点定理，得到 CM 阿贝尔簇 `@@M@@B/\overline{\mathbb Q}@@`、特殊纤维上的拟同源 (quasi-isogeny) `@@M@@a:A_0^n\to B_0@@` 及 Hodge 类 `@@M@@\kappa@@`，使 `@@M@@\gamma_0=(aj)^*\kappa_0@@` 在每个实现中同时成立。关键在"有理归一"：局部张量先只给出各实现的相似比 `@@M@@\lambda_v@@`，而用同一特殊纤维上有理除子的交数比 `@@M@@\lambda=\deg(a^*\theta_{B,0}\cdot\theta_*^{D-1})/\deg(\theta_*^{D})@@` 说明所有 `@@M@@\lambda_v@@` 是同一个有理数，从而搬运的是原类本身，而非每个上同调理论各自的局部倍数。

第二步把 CM 类拆成平衡 Weil 类 (Weil class)：在 CM 簇的幂上用有理幂等元切出因子 `@@M@@B_i@@`，使其同调在某个 CM 域 `@@M@@K@@` 上秩为 `@@M@@2r@@`、每个嵌入处 Hodge 符号为 `@@M@@(r,r)@@`、极化诱导 `@@M@@K@@` 上复共轭；这些因子的 Weil 类（分裂后为各特征空间上的顶阶交错形式）经拉回生成原类。由于"Lefschetz 配对性质"在有理拉回与有理线性组合下封闭，只需对平衡 Weil 类证明即可。

第三步是核心的二分法（Proposition 5.2）。设 `@@M@@\dagger@@` 为约化极化的 Rosati 对合 (Rosati involution)，考虑 `@@M@@\mathcal U=\{u\in\End^0(Z_0):u^\dagger=u,\ ue=\bar e u\}@@`。若 `@@M@@\mathcal U@@` 无可逆元，则用反证法：非零配对会迫使某个除子形式在单个 `@@M@@E@@`-特征空间上非退化，经有理点的 Zariski 稠密性得到有理 `@@M@@u\in\mathcal U@@`；若 `@@M@@u@@` 不可逆，其核含非零 `@@M@@E@@`-稳定阿贝尔子簇，其特征多项式在各实现中是同一有理多项式、共轭根重数相等，故该子簇的 `@@M@@H_1@@` 在每个嵌入处非零，与形式非退化矛盾——因此所有互补配对为零。若 `@@M@@\mathcal U@@` 含可逆元 `@@M@@u@@`，则除子 `@@M@@D^u(x,y)=\psi_0(x,uy)@@` 在每个特征空间上非退化；接着在固定晶体模上构造同时稳定于 `@@M@@E@@`、`@@M@@u@@` 与极化的弱容许滤过 (weakly admissible filtration)：先用"全亏格"的超模性论证找出唯一极大 destabilizing 子对象，从而把弱容许检验约化到 `@@M@@E,u@@`-稳定子对象；再在各辛块上选取与一切子空间最小相交的 Lagrangian 子空间，并用一个巧妙的"有界次数规避"引理（取 `@@M@@\theta^q=p@@` 的适度扩张，令全部次数不超过 `@@M@@b@@` 的多项式同时非零）把无穷多条件压缩到一次有限扩张内完成。

最后一步实现并提升：用带标架的局部 Shimura 簇点（Pappas–Rapoport 整一致化定理，所需的 `@@M@@(U_x)@@` 条件由 Gleason–Lim–Xu 供给）把该滤过实现为局部辅助簇 `@@M@@B@@` 的 Hodge 滤过；再用滤过 Dieudonné 模的完全忠实性、Tate 扩张定理与 Serre–Tate 形变理论，把特殊纤维上的投影子、`@@M@@E@@`-作用和除子一并提升到 `@@M@@B@@`。在 `@@M@@B@@` 的 Betti 实现中对多项式 `@@M@@(\sum_\tau x_\tau^2D_\tau)^s@@` 做系数提取：`@@M@@x_\tau^{2s}@@` 的系数恰是非退化的 `@@M@@D_\tau^s@@`，配合 `@@M@@E@@` 的有理点 Zariski 稠密，得出 Weil 类是有理除子幂线性组合的恒等式；该恒等式以相同的有理系数特化到每个实现，经拉回即完成主定理。

## 可信度与备注

本文主结果未经 Lean 形式化，属 OpenAI 批量产出的手稿之一，官方已声明"未经形式化的结果可能有问题"，请以社区核验为准。主定理的证明本身不依赖 CM Hodge 定理；代数性推论（单个有理闭链同时表示所有实现）则需额外输入——姊妹篇证明的 CM 阿贝尔簇 Hodge 定理 [OpenAICMHodge2026]，族概述称与 032 号结果合用即对一切剩余特征得到该结论。另需注意：本文只讨论固定约化位相的特殊纤维，既未断言特征 0 的 Hodge 猜想，也未把闭链 `@@M@@z_\gamma@@` 提升回原簇。

{% endraw %}
