---
layout: default
title: "Equivariant Jiang–Su Stability for Amenable Actions in the Unital Stably Finite Case"
family: "291"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Equivariant Jiang–Su Stability for Amenable Actions in the Unital Stably Finite Case

> 结果族 291：Cuntz comparison, nuclear dimension, and equivariant Jiang–Su stability　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了 Szabó 猜想 A 的单酉稳定有限情形：可数离散顺从群在简单、可分、单酉、无穷维、核、稳定有限且已 `@@M@@\mathcal Z@@`-稳定的 C*-代数上的任意作用，都在循环上同调共轭意义下自动吸收 Jiang–Su 代数上的平凡作用，对迹动力学毫无限制。

## 问题背景

Jiang–Su 代数（Jiang–Su algebra）`@@M@@\mathcal Z@@` 是 1999 年构造的无穷维单 C*-代数，其 Elliott 不变量与复数域相同；"`@@M@@\mathcal Z@@`-稳定性"（`@@M@@\mathcal Z@@`-stability）指 `@@M@@A\cong A\otimes\mathcal Z@@`，是核 C*-代数分类纲领的核心正则性条件。它有动力学对应物：群作用 `@@M@@\alpha:G\curvearrowright A@@` 应在循环上同调共轭（cocycle conjugacy）意义下吸收 `@@M@@\mathcal Z@@` 上的平凡作用。Szabó 2021 年的猜想 A 断言：顺从群在可分单核 `@@M@@\mathcal Z@@`-稳定代数上的作用自动等变 `@@M@@\mathcal Z@@`-稳定。此前已知情形（如 Szabó 定理 C）要求极值迹只有有限条射线、或很弱的比较条件；而一般作用可以把迹单形（tracial state simplex）上的迹任意搬动，外性（outerness）、Rokhlin、UCT 等假设一概没有，有限群与平凡作用也在范围之内。真正的卡点是：迹被搬动时，如何构造对整个迹空间一致的中心序列。Szabó–Wouters（2025）证明在本文设定中等变一致 Γ 性质（equivariant uniform property Γ）恰好刻画等变 `@@M@@\mathcal Z@@`-稳定性，把问题化归为构造不变的中心迹分裂——本文的全部工作正在于此。

## 主要结果

主定理（论文 Theorem 1.1）：设 `@@M@@A@@` 是简单、可分、单酉、无穷维、核、稳定有限（stably finite）的复 C*-代数且 `@@M@@A\cong A\otimes\mathcal Z@@`，`@@M@@G@@` 是可数离散顺从群（amenable group），`@@M@@\alpha:G\to\operatorname{Aut}(A)@@` 是任意作用。令 `@@M@@B=A\otimes\mathcal Z@@`、`@@M@@\beta_g=\alpha_g\otimes\operatorname{id}_{\mathcal Z}@@`。则存在单酉 *-同构 `@@M@@\Phi:A\to B@@` 与酉元族 `@@M@@u_g\in B@@`，满足 `@@M@@u_e=1@@`、`@@M@@u_{gh}=u_g\beta_g(u_h)@@`（上闭链关系），且 `@@M@@\Phi(\alpha_g(a))=u_g\beta_g(\Phi(a))u_g^*@@` 对一切 `@@M@@g@@`、`@@M@@a@@` 成立——即 `@@M@@\alpha@@` 与 `@@M@@\beta@@` 循环上同调共轭。定理对迹轨道、极值迹边界、外性均无要求；顺从性以 Følner 集形式使用。这解决了 Szabó 猜想 A 的单酉稳定有限情形（原猜想还含非酉代数，超出本文范围）。

## 证明思路

总体是"借力打力"：引用 Szabó–Wouters 的吸收定理——只要作用具有等变一致 Γ 性质，即对每个 `@@M@@k\ge2@@`，在不变中心序列代数 `@@M@@(A^\omega\cap A')^{\bar\alpha}@@` 中有两两正交、和为 `@@M@@1@@`、对一切极限迹满足 `@@M@@\tau(ap_i)=\tau(a)/k@@` 的投影——便可得到循环上同调共轭。于是全部工作化为构造这些投影，分三步。

第一步造"行"（rows）。利用张量吸收，在一致迹中心序列代数 `@@M@@A^\omega\cap A'@@` 里造出可数多个两两交换的轨道代数（orbit algebra）；关键的独立性引理表明，在它们生成的代数的任何极值迹下，不同轨道代数相互独立。这种内蕴独立性不要求所论的迹延拓到整个 `@@M@@A@@`，恰好化解"作用搬动迹"的困难。随后证明归一化和与经验协方差（empirical covariance）的联合中心极限定理（central limit theorem），且允许极值迹随行数变化。

第二步做二次高斯构造。对 Følner 集 `@@M@@F@@`，其 Gram 向量给出迹为一的正算子 `@@M@@P_F@@`；用多项式逼近 `@@M@@P_F^{1/2}@@`，得到方差一致有下界、群平移下变化微小的二次型。平方根归一化能对付任意秩、甚至高度相关的协方差矩阵；经验协方差把同一公式变成严格等变的非交换多项式；再用有限协方差空间的紧性，把标量矩极限提升为对所有迹状态一致的估计。

第三步做谱切割。用 `@@M@@A@@` 的元素给迹加权，得到相对 `@@M@@A@@` 呈 Haar 分布的中心不变酉元 `@@M@@w@@`，满足 `@@M@@\tau(af(w))=\tau(a)\int_{\mathbb T}f\,d\mu@@`；把圆环等分成 `@@M@@k@@` 段弧并对 `@@M@@w@@` 作函数演算，即得 `@@M@@k@@` 个等迹、正交、和为 `@@M@@1@@` 的不变投影——等变一致 Γ 性质成立，Szabó–Wouters 定理收尾。

## 可信度与备注

本文主结果尚无 Lean 形式化证明，请以社区核验为准。它是结果族 291 的动力学支柱：两篇姊妹篇分别从 Cuntz 比较与核维数方向确立 `@@M@@\mathcal Z@@`-稳定性，本文把这种正则性推广到顺从群作用；文中吸收步直接引用已发表的 Szabó–Wouters 定理，自建部分是中心分裂构造。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
