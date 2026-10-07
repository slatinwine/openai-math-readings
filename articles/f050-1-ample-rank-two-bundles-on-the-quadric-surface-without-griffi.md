---
layout: default
title: "Ample rank-two bundles on the quadric surface without Griffiths-positive metrics"
family: "050"
discipline: "Algebraic and complex geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Ample rank-two bundles on the quadric surface without Griffiths-positive metrics

> 结果族 050：A counterexample to Griffiths' positivity conjecture　·　学科：Algebraic and complex geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文在二次曲面 `@@M@@\mathbb P^1\times\mathbb P^1@@` 上构造显式秩二向量丛 `@@M@@G@@`：沿坐标取幂映射拉回并扭 `@@M@@\mathcal O(1,1)@@` 得到的 `@@M@@E_m@@` 对每个 `@@M@@m@@` 都充足，却对充分大的 `@@M@@m@@` 都不容许严格 Griffiths 正的光滑度量，在秩二情形推翻 Griffiths 正性猜想。

## 问题背景

代数几何用"充足"刻画正性：全纯向量丛 (holomorphic vector bundle) `@@M@@E@@` 充足 (ample) 当且仅当射影丛 `@@M@@\mathbb P(E)@@` 上的重言商线丛 `@@M@@\mathcal O_{\mathbb P(E)}(1)@@` 充足（Hartshorne 1966）。微分几何则用曲率衡量正性：若 `@@M@@E@@` 上有光滑 Hermitian 度量，其 Chern 曲率沿任何非零切方向与非零丛方向的配对都为正，就称严格 Griffiths 正 (strictly Griffiths-positive)，这样的度量必然诱导充足性。1969 年 Griffiths 提出猜想（Problem (0.9)）：光滑射影簇上反过来也成立——充足丛必带严格 Griffiths 正度量。这一步之所以重要，是因为它把代数正性转译为丛本身的曲率条件，从而进入微分几何的消灭定理机制。

此前卡在哪里？线丛上两套语言等价（Umemura 1973）；曲线上 Hartshorne 用商丛度数刻画充足性，Umemura 与 Campana–Flenner 证明度量等价也成立，所以曲面是反例可能出现的第一维度。修改丛后有不少正面结果：Berndtsson 证明充足丛的 `@@M@@E\otimes\det E@@` Nakano 正，Liu–Sun–Yang 处理了对称幂；Demailly 的 Hermitian–Yang–Mills 方程路线及 Pingali、Murakami 的工作（2026 年完成曲线情形的解析证明）都凸显了恢复度量之难。2026 年 9 月，Du–Xie 在椭圆曲线自乘的阿贝尔曲面上给出无 Griffiths 半正度量的秩二充足丛，本文则是有理曲面上的独立反例。

## 主要结果

主定理：存在 `@@M@@\mathbb P^1\times\mathbb P^1@@` 上秩二的代数向量丛 `@@M@@G@@`（文中显式给出），使得对每个正整数 `@@M@@m@@`，取 `@@M@@f_m@@` 为把两个因子的齐次坐标各升至 `@@M@@m@@` 次幂的自映射、`@@M@@P=\mathcal O(1,1)@@`，则 `@@M@@E_m=f_m^*G\otimes P@@` 充足；同时存在整数 `@@M@@m_0@@`，使所有 `@@M@@m\ge m_0@@` 的 `@@M@@E_m@@` 都不容许 Chern 曲率严格 Griffiths 正的光滑 Hermitian 度量。充足性还带量化证书：对一切满足 `@@M@@n-1\ge 3m@@` 的偶数 `@@M@@n@@`，`@@M@@\mathcal O_{\mathbb P(E_m)}(n)@@` 非常充足 (very ample)；而 `@@M@@m_0@@` 由紧性论证得到，是无效的 (ineffective)。

## 证明思路

先造丛。取 `@@M@@\mathrm{SL}_2(\mathbb C)@@` 中的矩阵 `@@M@@A,B@@`：迹均为 1，`@@M@@A,B,A^{-1}B@@` 在 `@@M@@\mathrm{SL}_2@@` 中阶分别为 6、6、8（射影阶为 3），无公共特征线，而 `@@M@@\mathrm{tr}(AB)=1+\sqrt2>2@@` 使 `@@M@@AB@@` 双曲。三条图 `@@M@@\Gamma_I,\Gamma_A,\Gamma_B@@` 拼成双次数 `@@M@@(3,3)@@` 的除子 `@@M@@D@@`，六个横截节点、无三重点。令 `@@M@@b=24@@`，`@@M@@L_1=\mathcal O(b,0)@@`，`@@M@@L_2=\mathcal O(0,b)@@`。在每个图上，矩阵 `@@M@@M@@` 诱导重言线丛间的同构，取 `@@M@@b@@` 次张量幂给出 `@@M@@L_1^{-1}\to L_2^{-1}@@` 的同构；节点处两条分支的值因 `@@M@@\lambda^{24}=1@@` 而一致，三分支遂粘合成同构 `@@M@@\alpha@@`。`@@M@@G@@` 定义为 `@@M@@L_1\oplus L_2@@` 中在 `@@M@@D@@` 上经 `@@M@@\beta=(\alpha^\vee)^{-1}@@` 认同的截面偶，即一次沿除子的初等变换 (elementary transformation)。它自带两个商序列 `@@M@@0\to L_i(-D)\to G\to L_j\to 0@@`，其对偶给出 `@@M@@F=G^\vee@@` 中两条线子丛：在 `@@M@@S\setminus D@@` 上张成，在 `@@M@@D@@` 上按指定变换重合。

再证充足。拉回后两个核 `@@M@@K_1=\mathcal O(21m,-3m)@@`、`@@M@@K_2=\mathcal O(-3m,21m)@@` 各有一个负度，但乘积 `@@M@@K=\mathcal O(18m,18m)@@` 双向皆正。交替使用两个商序列，把 `@@M@@\mathrm{Sym}^n(f_m^*G)@@` 滤过成线因子，除一个额外的 `@@M@@-\widetilde D@@` 外系数全部非负；取偶数 `@@M@@n@@` 且 `@@M@@n-1\ge 3m@@`，扭转 `@@M@@P^{n-1}@@` 恰好抵消这最后一份亏损。借助 `@@M@@H^1@@` 消灭逐层提升截面得整体生成，再经相对 Veronese 与 Segre 嵌入完成。

然后取极限。反设无穷多个 `@@M@@E_m@@` 有正度量：对偶度量的平方范数在全空间上多重次调和 (plurisubharmonic, psh)。对每个 `@@M@@m@@`，把对偶范数在 `@@M@@f_m@@` 的原像上平均，用取局部 `@@M@@m@@` 次根的"扭转标架"吸收 `@@M@@P@@` 因子，得到 Hermitian 二次函数 `@@M@@q_m@@`；归一化后系数一致有界，弱紧性给出可测半正极限，次均值不等式保住固定质量使其非零。难点在于：点态极限可能不再是 psh——论文举出反例系数会在一点跳变，且图关系恰好躺在除子上、无法从几乎处处代表中读出。为此用径向卷积正则化：卷积随参数单调下降，极限恢复出处处定义、非零、psh 的 `@@M@@q@@`，且每根纤维上仍是 Hermitian 半正二次型。

最后是动力学障碍。把 `@@M@@q@@` 拉回两条线子丛 `@@M@@L_i^{-1}\subset F@@`：固定一个因子坐标后函数关于另一因子次调和，最大值原理使之为常数，故下降为 `@@M@@\mathcal O_{\mathbb P^1}(-b)@@` 全空间上的平方半范数 `@@M@@a_\bullet@@`，且图关系迫使它在 `@@M@@A@@`、`@@M@@B@@` 的提升下不变。写 `@@M@@a_\bullet(z,we)=u(z)|w|^2@@`，则 `@@M@@\log u@@` 次调和且局部可积，`@@M@@\mu=i\partial\bar\partial\log u@@` 是正测度，其总质量被度 `@@M@@-b@@` 钉死为 `@@M@@2\pi b>0@@`（零点以原子计入），并由不变性被 `@@M@@A@@`、`@@M@@B@@` 保持。但 `@@M@@AB@@` 共轭于 `@@M@@z\mapsto\lambda z@@`（`@@M@@|\lambda|>1@@`），等测度的环带铺满 `@@M@@\mathbb C^*@@`，有限性迫使 `@@M@@\mu@@` 集中在 `@@M@@AB@@` 的两个不动点上；`@@M@@A@@`、`@@M@@B@@` 保持这一支撑，且射影阶 3 决定了它们在至多两点的集合上只能恒等置换，于是每个支撑点都是公共不动点——与"无公共特征线"矛盾。故 `@@M@@q\equiv 0@@`，与非零性矛盾，主定理随之成立。

## 可信度与备注

主定理（每个 `@@M@@m@@` 的充足性与充分大 `@@M@@m@@` 的无度量结论）已随本项目 Lean 形式化（lean/docs/050.md），但非常充足性的量化范围（`@@M@@n-1\ge 3m@@` 的证书）不在形式化之列，且 `@@M@@m_0@@` 无有效值，这些部分仍应以社区核验为准。族内姊妹篇互相支撑：Du–Xie 给出阿贝尔曲面上的反例与一阶 jet/伴随 Levi 障碍特征化，Liu–Wan 在每个 Hirzebruch 曲面上给出更强的 Finsler 度量排除；本文的独立价值在于有理曲面、显式幂映射族、全 `@@M@@m@@` 的充足证书与对任意丛均成立的极限命题。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
