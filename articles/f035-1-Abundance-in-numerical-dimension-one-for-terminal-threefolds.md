---
layout: default
title: "Abundance in numerical dimension one for terminal threefolds in positive characteristic"
family: "035"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Abundance in numerical dimension one for terminal threefolds in positive characteristic

> 结果族 035：Log-canonical threefold abundance in numerical dimension one　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

拍照片要对焦：只拍到一张全灰的照片时什么也认不出，两张不同角度的照片一对比，物体立刻立起来。这篇论文是家族的引擎篇：同样在特征 `@@M@@p>3@@` 的三维，但形状更端正（terminal 奇点）。此前的非消失定理只保证某个倍数 `@@M@@mK_X@@` 有一个截面——相当于只拍到一张灰片；论文证明一定还能拍到第二张无关的截面，两张一对比就能"对焦"，得到完整的纤维化。

**关键词卡片**

- terminal（终端奇点）：三维形状能有的最温和的奇点等级
- 非消失（nonvanishing）：某个正倍数的典范除子至少有一个非零截面
- Kodaira 维数 κ=1：截面数恰按一次方增长，像一次函数
- 循环障碍定理（cycle obstruction）：本文孤立出的核心引擎——光滑三维体上某类"连通 nef 除子"不可能存在
- jet（截断泰勒展开）：在除子附近把函数逐阶截断检查的显微镜

**看个具体例子**

定理的数字版：`@@M@@K_X@@` nef 且 `@@M@@\nu(K_X)=1@@`，则存在 `@@M@@m@@`、射影曲线 `@@M@@C@@` 及其上丰富除子 `@@M@@A@@`，使

`@@M@@mK_X\sim f^*A@@`（沿纤维严格为零）

即 `@@M@@X@@` 被整理成映射 `@@M@@f:X\to C@@`，固有曲率全部来自底曲线；同时 `@@M@@\kappa(X,K_X)=1@@`——那两个无关截面张成的正是"一次函数"式的增长。反过来，只要循环障碍不存在（引擎输出的矛盾），第二张照片就必然存在。

**为什么值得关心**

循环障碍定理被姊妹篇当黑箱引用，把结论从 terminal 推广到任意有理边界的对数典范三维对；证明全程留在特征 `@@M@@p@@`，不绕道特征零。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

特征 `@@M@@p>3@@` 的射影 `@@M@@\mathbb{Q}@@`-因子化终端（terminal）三维体 `@@M@@X@@` 若 `@@M@@K_X@@` nef 且数值维数 `@@M@@\nu(K_X)=1@@`，则 `@@M@@K_X@@` 半丰富且 `@@M@@\kappa(X,K_X)=1@@`：某个正倍数 `@@M@@mK_X@@` 至少有两个线性无关的整体截面。论文还孤立出族内核心的"循环障碍定理"——光滑三维体上某类连通 nef 除子不存在。

## 问题背景

丰富性猜想断言：奇性温和的射影簇上 nef 的典范除子半丰富。复数域上，Miyaoka 通过本原连通循环（primitive connected cycles）及其无穷小邻域证明了三维数值维数一的情形，Kawamata 用 log MMP 与形式加厚给出另一证明。正特征下，尽管三维 MMP 已在特征 `@@M@@p>5@@` 与 `@@M@@p=5@@` 建立，Xu 的系列定理仍留有一个逻辑缝隙：数值维数一的有效典范除子原则上可能 Kodaira 维数仍为零、同时 nef 维数极大（maximal nef dimension），即没有任何 `@@M@@K_X@@`-平凡曲线过 very general 点。本文的新贡献正是造出"第二个多重典范截面"以排除这一可能；而"从一个截面到半丰富"则由 Xu 的已有结果完成。

## 主要结果

主定理（原文 Theorem 1.1）：设 `@@M@@X@@` 为特征 `@@M@@p>3@@` 代数闭域上的正规射影 `@@M@@\mathbb{Q}@@`-因子化终端三维体，`@@M@@K_X@@` nef 且 `@@M@@\nu(K_X)=1@@`，则 `@@M@@K_X@@` 的某正 Cartier 倍数至少有两个无关的整体截面；特别地 `@@M@@\kappa(X,K_X)=1@@` 且 `@@M@@K_X@@` 半丰富。几何上，这给出连通纤维的态射 `@@M@@f:X\to C@@` 到某正规射影曲线以及其上的丰富除子 `@@M@@A@@`，使 `@@M@@mK_X\sim f^*A@@`。定理对第一 Betti 数、非正则数与 Albanese 纬垂均无假设。证明全在特征 `@@M@@p@@` 中完成，不提升到特征零，也不用轨道 Iitaka 定理。

## 证明思路

反证：设 nef 维数 `@@M@@n(X,K_X)=3@@`（至多二的情形 Xu 已证）。非消失给出有效除子 `@@M@@N_0\sim mK_X@@`。先做双有理准备，得到"预备循环"（prepared cycle，原文 Proposition 2.1）：光滑射影三维体 `@@M@@V@@`、可分生成有限态射 `@@M@@\rho:V\to X@@`、丰富除子 `@@M@@H@@` 与有效 Cartier 除子 `@@M@@D=\sum_\alpha m_\alpha D_\alpha@@`（重数 gcd 为一），满足：支撑连通且为简单正规交叉；`@@M@@D@@` nef 且限制在每个分量上数值平凡；`@@M@@DH^2>0@@`、`@@M@@D^2H=0@@`、没有 `@@M@@D@@`-平凡曲线过 very general 点；法线 `@@M@@\mathcal{O}_D(D)@@` 在整个非约化 Cartier 概型上为挠（torsion，设其阶为 `@@M@@r@@`）；且在 `@@M@@|D|@@` 的某邻域上 `@@M@@\omega_V^{\otimes p^b}\simeq\mathcal{O}(\sum_\alpha b_\alpha D_\alpha)@@`。构造要点是：用相对 MMP 孤立出一个约化边界分量，由曲面伴随与曲面丰富性得到其法线的挠性，再经局部上同调与 `@@M@@p@@` 幂粘合把挠性扩到非约化循环，最后用驯顺覆盖与本原化定型。

接着证斜率：对 nef 度 `@@M@@c_1(\cdot)\cdot H\cdot D@@` 证明切丛与余切丛强半稳定（strong semistability，用 Langer 的 Bogomolov 不等式）；失稳层取叶状商（foliation quotient）会产生过 very general 点的 `@@M@@D@@`-平凡曲线，故不可能。由此得到 `@@M@@c_2(V)\cdot D\geq 0@@` 与极部的一致界，作为下一步的输入。

核心是沿 `@@M@@D@@` 的 jet（截断泰勒展开）计算：在逐层 Cartier 加厚上考察截面，保留极点过滤的全部三个上同行，并在周期 `@@M@@rp^e@@` 上比较秩。标量行把完成的典范线丛等同于 `@@M@@D@@` 的支撑中某个整除子的线，并强迫 `@@M@@c_2(V)\cdot D=0@@`，还给出最后一层平凡化宽度的极限比率恰为 `@@M@@p/(p+1)@@`；这些数据同时控制了向量丛情形下各类微分的位置与长度。

由此提炼出形式邻域判据：满足 Euler 恒等式、有界极部与首阶 jet 集中条件的向量丛，其第一 Laurent 上同调消失——即每个闭的 Laurent 形式都有具界极部的原像。

最后是 Cartier 下降与终局矛盾。在 `@@M@@|D|@@` 上取 Laurent 环 `@@M@@\mathcal{R}=\widehat{\mathcal{O}}_V(*D)@@`。上述消失使每个 `@@M@@\mathcal{R}@@`-线丛带有 Cartier 固定的可积联络；局部坐标下，Katz 的 Cartier 下降（由截断泰勒算子构造的水平投影给出秩一的 `@@M@@R^p@@`-水平模）表明 `@@M@@\operatorname{Pic}(|D|,\mathcal{R})@@` 是 `@@M@@p@@`-可除群。另一面，把线丛限制到各分量 `@@M@@D_\alpha@@` 上与 `@@M@@H@@` 相交，定义整值同态 `@@M@@\overline\Phi:\operatorname{Pic}(|D|,\mathcal{R})\to\mathbb{Z}@@`；挠法线与 `@@M@@DD_\alpha H=0@@` 保证它下降到该 Picard 群上，且 `@@M@@\overline\Phi(\mathcal{O}(H))=DH^2>0@@`。但 `@@M@@p@@`-可除群的同态像被一切 `@@M@@p^n@@` 整除，只能为零——矛盾。故 nef 维数至多二，由 Xu 的定理得半丰富，再经截面空间的基底变换把结论降回原来的域。

## 可信度与备注

本文主结果暂无形式化证明。它是家族的核心篇：其循环障碍定理被十月的姊妹篇（对数典范边界一文）直接引用为黑箱，用于把结论从终端情形推广到任意有理边界的对数典范三维对；两篇互为犄角，共同完成特征 `@@M@@p>3@@` 三维数值维数一的丰富性。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
