---
layout: default
title: "A counterexample to Kaplansky's quasitrace conjecture and failure of tensor-product stable finiteness"
family: "294"
discipline: "Operator algebras"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to Kaplansky's quasitrace conjecture and failure of tensor-product stable finiteness

> 结果族 294：Kaplansky's quasitrace conjecture and failure of tensor-product stable finiteness　·　学科：Operator algebras　·　验证状态：主结果已 Lean 形式化

## 一句话结论

构造出一个可分单位复 `@@M@@C^*@@`-代数：它拥有正规化 2-拟迹（2-quasitrace）却没有任何迹态，且所有拟迹在一对固定正元上非可加，从而推翻 Kaplansky 拟迹猜想；进而两个单的稳定有限代数之最小张量积可以真无限，一个因子可取 `@@M@@C_r^*(\mathbb F_2)@@`。

## 问题背景

1951 年，Kaplansky 引入 AW*-代数（AW*-algebra），希望脱离 Hilbert 空间表示、仅凭内在代数条件刻画 von Neumann 代数。已知类型 I 的 AW*-因子必为 `@@M@@W^*@@`-代数、类型 III 存在反例，唯独有限的 `@@M@@\mathrm{II}_1@@` 情形悬置七十余年。这个问题等价于拟迹问题（quasitrace problem）：单位 `@@M@@C^*@@`-代数上每个正规化 2-拟迹是否都是迹态（tracial state）？拟迹只要求在交换子代数上线性并满足 `@@M@@\tau(x^*x)=\tau(xx^*)@@`，2-拟迹还需延拓到 `@@M@@M_2@@`，这条矩阵延拓条件正是症结。Haagerup 证明精确（exact）代数上 2-拟迹必为迹，故反例只能是非精确代数，极难构造。Milhøj–Rørdam 进而证明：两个单位单稳定有限（stably finite）`@@M@@C^*@@`-代数的最小张量积是否仍稳定有限，与拟迹问题等价。

## 主要结果

**主定理**：存在可分单位复 `@@M@@C^*@@`-代数 `@@M@@A@@`，它拥有正规化 2-拟迹，且存在正压缩元（positive contraction）`@@M@@a,b\in A@@`，使 `@@M@@A@@` 上每个正规化 2-拟迹 `@@M@@\tau@@` 都满足 `@@M@@\tau(a+b)-\tau(a)-\tau(b)\ge\frac{1}{144}@@`。迹态必须可加，故此不等式否定"凡 2-拟迹皆迹"的猜想，并给 Kaplansky 的 `@@M@@\mathrm{II}_1@@` AW*-因子问题以否定回答；由 Haagerup 定理，`@@M@@A@@` 必然非精确。

**推论**（均为最小张量积）：(i) 两个单位单的稳定有限 `@@M@@C^*@@`-代数之最小张量积可以真无限（properly infinite），一个因子可取二生成自由群的既约群代数 `@@M@@C_r^*(\mathbb F_2)@@`；(ii) 存在拥有正规化 2-拟迹的可分单位代数 `@@M@@B@@`，使 `@@M@@B\otimes_{\min}C_r^*(\mathbb F_2)@@` 真无限且不再有 2-拟迹；(iii) 存在可分、单位、稳定有限却没有迹态的 `@@M@@C^*@@`-代数。矩阵延拓条件不可去：Kirchberg 2006 年有 1-拟迹非迹的未发表例子，但缺少所需的 `@@M@@M_2@@` 延拓。

## 证明思路

一切围绕 `@@M@@B=C^*(1,x_1,\ldots,x_{24})@@` 展开，生成元满足 `@@M@@\sum_{i=1}^{24}x_i^*x_i=1@@`、`@@M@@\sum_{i=1}^{24}x_ix_i^*\le\tfrac23\cdot1@@`。迹态作用两式会得 `@@M@@1\le 2/3@@`，故 `@@M@@B@@` 无迹态；另一面要证每个 `@@M@@M_m(B)@@` 都不含值域正交的等距对，即不真无限，Cuntz–Blackadar–Handelman 存在性定理随即给出 2-拟迹。

生成元是向量丛之间的移位。先对每对参数 `@@M@@(m,R)@@` 搭建一个有限"拓扑测试"：紧基是若干复射影空间之积，丛 `@@M@@E_j@@` 由超平面线丛（hyperplane line bundle）直和而成，重数经设计使被测丛 `@@M@@G=(\bigoplus_{j=0}^{R}E_j)^{\oplus m}@@` 的最高陈类（Chern class）`@@M@@\prod_i z_i^{K_i}\ne0@@`，从而 `@@M@@G@@` 容不下秩 `@@M@@2md_0@@` 的平凡子丛。相邻层之间的 24 个映射分两组：16 个进入旧线丛的缩减副本，负责维数 `@@M@@\le m@@` 的小子空间；8 个通用映射进入新区块，负责大子空间；存在性靠 Sard 型维数计数引理，保证每个源子空间的联合像维数至少翻倍。再由"连续规范化"引理逐纤维最小化行列式势 `@@M@@g_y(P)=\log\det(I+D_y(P))-\tfrac32\log\det P@@`：沿正定测地线用 Gram 行列式展开证严格凸，得唯一极小点；唯一性保证它随基点连续、可在非平凡丛上粘合，由极小条件解出 `@@M@@X_i@@`，使列和为 `@@M@@I@@`、行和 `@@M@@\le 2/3@@`（与 Gurvits 算子尺度化 operator scaling 同源）。由于映射个数与范数界关于 `@@M@@(m,R)@@` 一致，可把所有测试的移位放进同一个有界直积一次性定义 `@@M@@x_i@@`；有理系数多项式使 `@@M@@B@@` 可分。

排除真无限时，设 `@@M@@M_m(B)@@` 有等距 `@@M@@s_1,s_2@@`，拼成 `@@M@@W=[s_1\ s_2]@@`，`@@M@@W^*W=I_{2m}@@`；用多项式矩阵 `@@M@@P@@` 逼近使 `@@M@@P^*P\ge\tfrac12 I@@`。取 `@@M@@R@@` 不小于 `@@M@@P@@` 中词长，则 `@@M@@P@@` 限制在零层得丛映射 `@@M@@E_0^{\oplus 2m}\to G@@`，规范化后是纤维等距，其像是秩 `@@M@@2md_0@@` 的平凡子丛，与陈类障碍矛盾。最后令 `@@M@@A=M_{48}(B)@@`：用部分和构造对角正元对 `@@M@@a,b@@`，仅凭交换线性和角点等式 `@@M@@\tau(t^*t)=\tau(tt^*)@@` 做望远镜求和，得非可加量 `@@M@@\ge\frac{1-c}{2N}=\frac1{144}@@`；此步对一切 1-拟迹成立，无需拟迹的显式公式。

## 可信度与备注

任务元信息标明主结果已获 Lean 形式化证明，可信度较高。构造融合 Haagerup 迹障碍、Villadsen–Rørdam 式陈类障碍与逐纤维尺度化，各引理自成闭环；作为结果族 294 的核心篇，它直接产出族概述强调的张量积推论。依 OpenAI 官方声明，未经形式化的结果可能存在问题，未入形式化范围的细节仍请以社区核验为准。

{% endraw %}
