---
layout: default
title: "Nuclear dimension and Jiang–Su stability without elementary subquotients"
family: "291"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Nuclear dimension and Jiang–Su stability without elementary subquotients

> 结果族 291：Cuntz comparison, nuclear dimension, and equivariant Jiang–Su stability　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明可分核 C*-代数只要没有非零初等理想子商，"有限核维数""Jiang–Su 稳定""核维数 `@@M@@\le1@@`"三者等价，解决 Robert–Tikuisis 猜想 (C1) 及非单 Toms–Winter 正则性问题的核维数等价，并对一切可分核 `@@M@@A_0@@` 给出最优界 `@@M@@\dim_{\mathrm{nuc}}(A_0\otimes\mathcal Z)\le1@@`。

## 问题背景

核维数（nuclear dimension）由 Winter–Zacharias 引入，计数有限维完全正逼近所需的零阶序（order-zero）颜色数，是非交换的覆盖维数；Jiang–Su 稳定性（`@@M@@A\cong A\otimes\mathcal Z@@`）是分类纲领的中心正则性。单代数情形两者等价已由 Winter、CETWW、Castillejos–Evington 等完成，非单情形悬置多年，原因有二。其一，矩阵代数核维数为零却不吸收 `@@M@@\mathcal Z@@`，说明排除条件必须贯穿整个理想结构——这引出"无处散射"（nowhere scattered）假设：没有任何理想商 `@@M@@I/J@@` 是初等代数 `@@M@@\mathcal K(H)@@`。其二，非单代数中迹可在一个理想上有界、在另一处无穷，稳定有限与纯无限的理想商可以共存，须用 Elliott–Robert–Santiago 的下半连续扩迹（extended traces）锥。Robert–Tikuisis（2017）把吸收问题化归为中心序列代数中两个满（full）正交正元素的存在性，即其猜想 (C1)；Winter–Zacharias 的有限覆盖数界又排除该代数的特征标（character）。剩下的缺口正是 Kirchberg–Rørdam 问题 6.2 所问的张量分裂。

## 主要结果

主定理（论文 Theorem 1.1）：设 `@@M@@A@@` 是可分核复 C*-代数且无非零初等理想子商，则 `@@M@@\dim_{\mathrm{nuc}}(A)<\infty@@`、`@@M@@A\cong A\otimes\mathcal Z@@` 与 `@@M@@\dim_{\mathrm{nuc}}(A)\le1@@` 三条等价。这证明 Robert–Tikuisis 猜想 (C1)，并确立非单 Toms–Winter 正则性问题中的核维数等价；配套推论 1.2 把两条 Cuntz 半群判据（典范映射 `@@M@@\Cu(\iota_A)@@` 是同构、或 `@@M@@\Cu(A)\cong\Cu(A\otimes\mathcal Z)@@` 抽象同构）并入等价列表。第二定理给出一致最优界：对每个可分核 `@@M@@A_0@@`，`@@M@@\dim_{\mathrm{nuc}}(A_0\otimes\mathcal Z)\le1@@`；因核维数为零的可分代数必为 AF 而 `@@M@@\mathcal Z@@` 无非常值投影，`@@M@@\dim_{\mathrm{nuc}}(\mathcal Z)=1@@`，故此界不可再降。第三定理独立成立：每个无非零特征标的单酉复 C*-代数 `@@M@@D@@`，存在有限 `@@M@@n@@` 使极大张量幂（maximal tensor power）`@@M@@D^{\otimes_{\max}n}@@` 含两个满的正交正元素，不假设可分与核——把 Kirchberg–Rørdam 问题 6.2 的无穷张量幂版本一并肯定回答。

## 证明思路

两个方向独立推进，最后合流。维数界方向：先把模型安放进 `@@M@@A\otimes\mathcal Z_1\otimes\mathcal Z_2\otimes\mathcal Z_3@@`，第一因子承载模型；拟中心理想切割给出有限多族两两正交的遗传碎片。关键在次序——先固定碎片与比较界、后选内逼近误差，使范数误差全部化为相对谱切割支撑秩（support rank）的界，对所有使该秩有限的扩迹一致；秩无穷时改用理想包含论证逼出比较目标的无穷秩。再把 Hirshberg–Kirchberg–White 与 Brown–Carrión–White 的凸零阶序逼近局部化到遗传角，凸权取整成单个矩阵值零阶序返回映射；在超幂的支撑相对交换子中，用 Gabe 的零阶序版 Kirchberg–Rørdam 锥判据得到有限压缩和并打包成比较，复以 BBSTWW 的酉等价判据化为两次加权共轭；第三个 `@@M@@\mathcal Z@@` 因子提供满谱正压缩 `@@M@@k@@`，对 `@@M@@k@@` 与 `@@M@@1-k@@` 的共轭恰好给出两种颜色；稳定化、遗传持久性与单理化收尾。

吸收方向始于高斯符号引理：以 Gilbert 的 Hamming 填充选出指数多个两两汉明距离 `@@M@@\ge n/4@@` 的字，相应的高斯评估因协方差近对角而弱相关，失效概率按 `@@M@@q^N@@` 衰减，联合界加紧空间网格论证便产生一个实张量 `@@M@@G@@`，它在所有充分分离的二元组（各因子内积绝对值 `@@M@@\le r@@`）配置上一致取到 `@@M@@>1/2@@` 与 `@@M@@<-1/2@@` 两个值。再用一个有限交换子见证把"`@@M@@D@@` 无特征标"转化为纯态期望向量的一致分离，并以 Akemann–Anderson–Pedersen 纯态切除（pure-state excision）把张量评估转移到极大张量积的每个不可约表示，所得自伴元的正、负部分因此皆满。最后看中心序列代数 `@@M@@F(A)@@`：有限覆盖界排除特征标，取含单位的可分无特征标子代数套用分裂定理，得有限张量幂中的满正交对；交换重指标给出到 `@@M@@F(A)@@` 的单酉同态且满性存活，Robert–Tikuisis 判据随即给出吸收。

## 可信度与备注

本文主结果尚无 Lean 形式化证明，请以社区核验为准。它是结果族 291 的维数支柱：姊妹篇 Cuntz 比较论文提供 Cuntz 半群判据（本文推论 1.2 即援引之），等变稳定性论文再把正则性推向顺从群作用。高斯符号引理与纯态切除等组件在文内自含证明（后者附基于 Kadison 传递定理的短证明）。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
