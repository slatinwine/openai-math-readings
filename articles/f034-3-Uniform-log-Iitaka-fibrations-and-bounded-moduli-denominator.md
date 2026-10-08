---
layout: default
title: "Uniform log Iitaka fibrations and bounded moduli denominators"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Uniform log Iitaka fibrations and bounded moduli denominators

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

问一个空间"有多复杂"，标准办法是不断调高观察倍数（多重典范系），看信息何时饱和。一般来说，不同空间需要不同倍数；这篇论文证明：只要维数和允许的系数固定，就存在一个统一的放大倍数，到了那里所有空间的信息一律饱和——并且顺带把"模除子"的分母也一致框住。

**关键词卡片**

- Iitaka 纤维化（Iitaka fibration）：由全部多重典范截面共同定义的、到"复杂度模型"的映射。
- 多重典范系（pluricanonical system）：`@@M@@|mD|@@` 的截面组成的观察系统。
- 一致次数（uniform degree）：对整类空间同时够用的放大倍数 `@@M@@m(d,\Phi)@@`。
- 典范丛公式（canonical bundle formula）：把纤维化全空间的弯曲拆到底空间的公式。
- 模除子（moduli divisor）：公式里记录纤维形状变化的部分，其"分母"需一致控制。

**看个具体例子**

经典类比来自曲线：任何亏格 `@@M@@\ge 2@@` 的光滑曲线上，`@@M@@|3K|@@` 一律给出嵌入——倍数 `@@M@@3@@` 对所有曲线同时够用。论文的高维版本（数字版）：固定 `@@M@@d\ge 5@@` 与系数集 `@@M@@\Phi@@` 后，存在 `@@M@@m=m(d,\Phi)@@`，使任何 `@@M@@\kappa\ge 0@@` 的 lc 配对上，`@@M@@\lfloor mD\rfloor@@` 的截面比已经生成整个 Iitaka 域 `@@M@@K(D)@@`；同时模除子有只依赖 `@@M@@d,\Phi@@` 的 Cartier 分母 `@@M@@p@@`。

**为什么值得关心**

"有效 Iitaka 纤维化"与一致分母是模空间有界化与高维丰度传递的定量基石：有了统一刻度，整类空间的复杂度才能放进有限张"对照表"里比较。本文处理了带水平边界、任意纤维维数的困难情形。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对固定维数 `@@M@@d\geq5@@`、边界系数取自固定有限有理集的射影 log canonical 对，证明存在只依赖维数与系数集的次数 `@@M@@m@@`，使第 `@@M@@m@@` 个完整舍入多重典范系已生成全部 Iitaka 域；并一致界定典范丛公式中模除子的 Cartier 分母。

## 问题背景

Iitaka 纤维化由所有多重典范系的渐近像定义，而有效（effective）问题问：是否存在一个只依赖维数与容许系数集的统一次数？一般型情形即 Hacon–McKernan、Takayama、Tsuji 的一致双有理性定理，Hacon–McKernan–Xu 推广到 DCC 系数的大 log 典范伴随。当 Kodaira 维数小于维数时，一般纤维上诱导出 Kodaira 维数为零的 log 结构，典范丛公式（canonical bundle formula）把伴随除子转移到基底，纤维的变差贡献模除子（moduli divisor）；要把截面从纤维搬到基底，必须控制模除子的 Cartier 分母，而曲线半稳定覆盖的分歧度一般无界，这正是难点所在。Fujino–Mori、Viehweg–Zhang、Birkar–Zhang 逐步推进了有效 Iitaka 纤维化；Chen–Han–Liu 对 lc 对提出该问题并在三维以下解决。本文处理带有水平边界（horizontal boundary）的任意纤维维数情形。

## 主要结果

**定理（一致 log Iitaka 次数）**：对每个整数 `@@M@@d\geq5@@` 与有限集 `@@M@@\Phi\subset[0,1]\cap\mathbb Q@@`，存在 `@@M@@m=m(d,\Phi)>0@@`：任何特征零代数闭域上、边界系数落在 `@@M@@\Phi@@` 内、`@@M@@D=K_X+B@@` 为有理 Cartier 且 `@@M@@\kappa(X,D)\geq0@@` 的正规积分射影 lc `@@M@@d@@` 折对，都有 `@@M@@V_m(D)=H^0(X,\mathcal O_X(\lfloor mD\rfloor))\neq0@@`，且由第 `@@M@@m@@` 次系统截面比生成的域 `@@M@@F_m(D)@@` 等于所有次数截面比生成的 Iitaka 域 `@@M@@K(D)@@`。舍入（round-down）系统使叙述在 `@@M@@\ell D@@` 非 Cartier 时也有意义。

**定理（模除子一致分母）**：对本文规范化的典范丛公式，存在 `@@M@@p=p(d,\Phi)@@`：在每个光滑射影判定模型 `@@M@@W@@` 上，`@@M@@pM_W@@` 是 nef Cartier 除子——分母一致有界且不依赖 `@@M@@W@@` 的复杂程度。

## 证明思路

先在 `@@M@@\mathbb C@@` 上证明。由族内姊妹篇的好模型定理取终止 MMP 与半丰富收缩，问题化为 log Calabi–Yau 纤维化 `@@M@@f\colon X\to Z@@` 上 `@@M@@K_X+B\sim_{\mathbb Q}f^*L@@` 的情形。第一步用正常 lc 指标定理（姊妹篇）固定主平移的规模 `@@M@@p_0@@`，得精确表述 `@@M@@K_X+B+\frac1{p_0}\operatorname{Div}(\psi)=f^*D_Z@@`——固定 `@@M@@p_0@@` 至关重要，任意的有理主平移会引入新分母；判别式 `@@M@@B_Z@@` 的系数由 log canonical 阈值的 ACC 定理落在固定 DCC 集内。第二步用横截曲线切片把 `@@M@@M_Z@@` 的一个系数实现为曲线权：在基底上取一般完全交曲线过 `@@M@@P@@` 的横截点 `@@M@@c@@`，经消解、相伴与留数构造出几何积分的 lc 对 `@@M@@(V,B_V)@@` 及 `@@M@@m@@`-典范形式 `@@M@@\phi@@`，满足 `@@M@@\operatorname{Div}(\phi)+mB_V=0@@` 且权 `@@M@@w_z(\phi)=\alpha-1+t_P@@` 恰为模系数加整数修正。

第三步是可复用的中间定理——曲线权定理：权可被只依赖纤维维数 `@@M@@s@@` 与次数 `@@M@@a@@` 的整数清分。其证明分两条线。dlt 模型有水平系数一分支时，取有理多重留数降低纤维维数做归纳，其 Stein 因子化对曲线域的改变由算术 Stein 度定理（另一姊妹篇）控制。klt 情形用 Matsumura–Wang 乘积定理得有理连通因子（承载边界）加阿贝尔与非阿贝尔 Beauville–Bogomolov 因子；但乘积覆盖未必承载惯性作用，需过渡到 Galois 比较覆盖，用保持边界切向量场的切丛自同态代数证明某个有界幂分别作用在各因子的有限覆盖上，而有限不变体积测度消灭有理连通因子上切边整体向量场。半稳定化后各因子形式可规范化为零权，其乘积亦零权；原形式与之只差曲线覆盖上的底函数 `@@M@@v@@`，惯性恒等式 `@@M@@e\,w_z(\phi)=\operatorname{ord}_{c'}(v)/a@@` 便强迫分歧指数 `@@M@@e@@` 整除 `@@M@@\operatorname{ord}_{c'}(v)@@` 的有界倍数，从而抵消无控制的分歧。阿贝尔因子的特征作用在有限秩整上同调群上；其余因子改用好模型上的 dlt 特殊纤维，Du Bois 基变换与凝聚 Lefschetz 给出作用有界幂的不动点，再取有界幂保持某正规分支，其上留数是原次数的 log 平凡化，different 系数落在固定有限集内，最后对该分支的循环商引用正常 lc 指标定理界定特征——只需在单个正规分支上工作，正是回避可约特殊纤维指标定理之处。

第四步回到线性系统：分母界定后，Birkar–Zhang 极化对的有效双有理性定理在底上给出双有理系统；再由两条"舍入截面比较"引理——拉回比较与双有理比较——把楼上与楼下的完整舍入截面空间在公共函数域内精确等同，连同样比升次技巧，证得 `@@M@@K(D)=f^*\mathbb C(Z)@@`。基底为点时由指标定理得 `@@M@@K(D)=\mathbb C@@`。最后用比值域下降引理（先下降到可嵌入 `@@M@@\mathbb C@@` 的代数闭子域再扩张回去）把结论搬到任意特征零代数闭域。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；依 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。证明把三个姊妹篇定理（好模型定理、正常 log canonical 指标定理、算术 Stein 度定理）当作黑箱输入，本文自有的贡献是水平边界下的一致分母传递与舍入截面域的精确比较，其中 Galois 比较覆盖上惯性作用的分因子控制是技术最重、最值得独立核验的环节。它与族内各篇共同构成族 34"有效性/一致性"一侧的支柱。

{% endraw %}
