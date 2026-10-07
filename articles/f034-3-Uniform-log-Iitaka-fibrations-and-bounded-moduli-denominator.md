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

## 一句话结论

对固定维数 \(d\geq5\)、边界系数取自固定有限有理集的射影 log canonical 对，证明存在只依赖维数与系数集的次数 \(m\)，使第 \(m\) 个完整舍入多重典范系已生成全部 Iitaka 域；并一致界定典范丛公式中模除子的 Cartier 分母。

## 问题背景

Iitaka 纤维化由所有多重典范系的渐近像定义，而有效（effective）问题问：是否存在一个只依赖维数与容许系数集的统一次数？一般型情形即 Hacon–McKernan、Takayama、Tsuji 的一致双有理性定理，Hacon–McKernan–Xu 推广到 DCC 系数的大 log 典范伴随。当 Kodaira 维数小于维数时，一般纤维上诱导出 Kodaira 维数为零的 log 结构，典范丛公式（canonical bundle formula）把伴随除子转移到基底，纤维的变差贡献模除子（moduli divisor）；要把截面从纤维搬到基底，必须控制模除子的 Cartier 分母，而曲线半稳定覆盖的分歧度一般无界，这正是难点所在。Fujino–Mori、Viehweg–Zhang、Birkar–Zhang 逐步推进了有效 Iitaka 纤维化；Chen–Han–Liu 对 lc 对提出该问题并在三维以下解决。本文处理带有水平边界（horizontal boundary）的任意纤维维数情形。

## 主要结果

**定理（一致 log Iitaka 次数）**：对每个整数 \(d\geq5\) 与有限集 \(\Phi\subset[0,1]\cap\mathbb Q\)，存在 \(m=m(d,\Phi)>0\)：任何特征零代数闭域上、边界系数落在 \(\Phi\) 内、\(D=K_X+B\) 为有理 Cartier 且 \(\kappa(X,D)\geq0\) 的正规积分射影 lc \(d\) 折对，都有 \(V_m(D)=H^0(X,\mathcal O_X(\lfloor mD\rfloor))\neq0\)，且由第 \(m\) 次系统截面比生成的域 \(F_m(D)\) 等于所有次数截面比生成的 Iitaka 域 \(K(D)\)。舍入（round-down）系统使叙述在 \(\ell D\) 非 Cartier 时也有意义。

**定理（模除子一致分母）**：对本文规范化的典范丛公式，存在 \(p=p(d,\Phi)\)：在每个光滑射影判定模型 \(W\) 上，\(pM_W\) 是 nef Cartier 除子——分母一致有界且不依赖 \(W\) 的复杂程度。

## 证明思路

先在 \(\mathbb C\) 上证明。由族内姊妹篇的好模型定理取终止 MMP 与半丰富收缩，问题化为 log Calabi–Yau 纤维化 \(f\colon X\to Z\) 上 \(K_X+B\sim_{\mathbb Q}f^*L\) 的情形。第一步用正常 lc 指标定理（姊妹篇）固定主平移的规模 \(p_0\)，得精确表述 \(K_X+B+\frac1{p_0}\operatorname{Div}(\psi)=f^*D_Z\)——固定 \(p_0\) 至关重要，任意的有理主平移会引入新分母；判别式 \(B_Z\) 的系数由 log canonical 阈值的 ACC 定理落在固定 DCC 集内。第二步用横截曲线切片把 \(M_Z\) 的一个系数实现为曲线权：在基底上取一般完全交曲线过 \(P\) 的横截点 \(c\)，经消解、相伴与留数构造出几何积分的 lc 对 \((V,B_V)\) 及 \(m\)-典范形式 \(\phi\)，满足 \(\operatorname{Div}(\phi)+mB_V=0\) 且权 \(w_z(\phi)=\alpha-1+t_P\) 恰为模系数加整数修正。

第三步是可复用的中间定理——曲线权定理：权可被只依赖纤维维数 \(s\) 与次数 \(a\) 的整数清分。其证明分两条线。dlt 模型有水平系数一分支时，取有理多重留数降低纤维维数做归纳，其 Stein 因子化对曲线域的改变由算术 Stein 度定理（另一姊妹篇）控制。klt 情形用 Matsumura–Wang 乘积定理得有理连通因子（承载边界）加阿贝尔与非阿贝尔 Beauville–Bogomolov 因子；但乘积覆盖未必承载惯性作用，需过渡到 Galois 比较覆盖，用保持边界切向量场的切丛自同态代数证明某个有界幂分别作用在各因子的有限覆盖上，而有限不变体积测度消灭有理连通因子上切边整体向量场。半稳定化后各因子形式可规范化为零权，其乘积亦零权；原形式与之只差曲线覆盖上的底函数 \(v\)，惯性恒等式 \(e\,w_z(\phi)=\operatorname{ord}_{c'}(v)/a\) 便强迫分歧指数 \(e\) 整除 \(\operatorname{ord}_{c'}(v)\) 的有界倍数，从而抵消无控制的分歧。阿贝尔因子的特征作用在有限秩整上同调群上；其余因子改用好模型上的 dlt 特殊纤维，Du Bois 基变换与凝聚 Lefschetz 给出作用有界幂的不动点，再取有界幂保持某正规分支，其上留数是原次数的 log 平凡化，different 系数落在固定有限集内，最后对该分支的循环商引用正常 lc 指标定理界定特征——只需在单个正规分支上工作，正是回避可约特殊纤维指标定理之处。

第四步回到线性系统：分母界定后，Birkar–Zhang 极化对的有效双有理性定理在底上给出双有理系统；再由两条"舍入截面比较"引理——拉回比较与双有理比较——把楼上与楼下的完整舍入截面空间在公共函数域内精确等同，连同样比升次技巧，证得 \(K(D)=f^*\mathbb C(Z)\)。基底为点时由指标定理得 \(K(D)=\mathbb C\)。最后用比值域下降引理（先下降到可嵌入 \(\mathbb C\) 的代数闭子域再扩张回去）把结论搬到任意特征零代数闭域。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；依 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。证明把三个姊妹篇定理（好模型定理、正常 log canonical 指标定理、算术 Stein 度定理）当作黑箱输入，本文自有的贡献是水平边界下的一致分母传递与舍入截面域的精确比较，其中 Galois 比较覆盖上惯性作用的分因子控制是技术最重、最值得独立核验的环节。它与族内各篇共同构成族 34"有效性/一致性"一侧的支柱。

{% endraw %}
