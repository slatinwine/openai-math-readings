---
layout: default
title: "Exact orders and invariant anticanonical linear systems"
family: "068"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Exact orders and invariant anticanonical linear systems

> 结果族 068：Anticanonical nonvanishing in every dimension　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了"阶的精确达到"定理：当光滑射影簇的反典范丛 `@@M@@-K_X@@` 带半正曲率的光滑度量时，沿任意中心赋值归一化阶趋于零的有效除子列，必极限为一个有理线性等价于 `@@M@@-K_X@@` 且在该赋值处阶恰为零的有效除子，为族内 `@@M@@H^0(X,-mK_X)\ne0@@` 供出关键一环。

## 问题背景

非消失（nonvanishing）问题是双有理几何的核心悬念之一：设 `@@M@@X@@` 为光滑射影复代数簇，反典范丛 `@@M@@-K_X@@` 数值有效（nef），是否存在正整数 `@@M@@m@@` 使 `@@M@@H^0(X,-mK_X)\ne0@@`？它与丰度猜想（abundance conjecture）紧密相关。此前最好成绩停留在三维：Lazić–Matsumura–Peternell–Tsakanikas–Xie（2023）证明三维的数值有效性并发展基于扭曲微分形式的非消失方法；Müller（2025）对射影 klt 三维对证明反 log 典范非消失。一般维数的卡点在于：数值有效锥中的极限只保留数值等价类，而构造截面恰恰需要有理线性等价（rational linear equivalence）的信息。本文改用"光滑半正性"假设——`@@M@@-K_X@@` 有曲率形式半正的光滑 Hermitian 度量——换来对所有维数、且在指定赋值处保阶的精确结论。

## 主要结果

**主定理（Theorem 1.1，零阶精确达到）**：设 `@@M@@X@@` 光滑连通射影、`@@M@@\dim X=n>0@@`，`@@M@@L=-K_X@@` 带代表 `@@M@@c_1(L)@@` 的半正曲率形式 `@@M@@\alpha@@`，`@@M@@\nu@@` 为 `@@M@@\alpha@@` 的最大复秩，`@@M@@G_0@@` 为丰富线丛，定义零泛函 `@@M@@\ell(D)=D\cdot L^{\nu}\cdot G_0^{\,n-\nu-1}@@`（`@@M@@\nu=n@@` 时取 `@@M@@0@@`）。它在有效除子上非负且 `@@M@@\ell(L)=0@@`。设 `@@M@@v@@` 为 `@@M@@\C(X)@@` 上在 `@@M@@X@@` 上中心（centered）的离散赋值或零赋值，`@@M@@M@@` 为任意线丛。若有效整除子 `@@M@@N_j\sim m_jL+M@@`（`@@M@@m_j\to\infty@@`）满足 `@@M@@\ell(N_j)=0@@`、`@@M@@v(N_j)/m_j\to0@@`，则存在有效有理除子 `@@M@@N\sim_{\Q}L@@` 使 `@@M@@v(N)=0@@`。结论保持有理线性等价而非仅数值类；辅助线丛 `@@M@@M@@` 任意，也无任何不规则度或欧拉特征假设。

**弧推论（Corollary 5.1）**：当 `@@M@@-M@@` 伪有效（pseudoeffective）时，沿任意泛形式弧（generic formal arc）`@@M@@\gamma:\Spec F[[t]]\to X@@` 阶为 `@@M@@o(m_j)@@` 的上述序列，给出某个 `@@M@@r>0@@` 与有效整除子 `@@M@@D\sim rL@@`，使 `@@M@@v_\gamma(D)=0@@`。

**不变截面定理（Theorem 1.2）**：再设 `@@M@@H^i(X,\OO_X)=0\ (i>0)@@`，则对任意作用于 `@@M@@X@@` 的代数环面 `@@M@@T@@`，某个正倍数 `@@M@@-mK_X@@` 有非零 `@@M@@T@@`-不变截面（取自然线性化）。结合姊妹篇的单值结构下降，最终得到族 068 的标量结论：光滑半正的 `@@M@@-K_X@@` 蕴含 `@@M@@H^0(X,-mK_X)\ne0@@`。

## 证明思路

先证纯代数的"端点引理"（Lemma 2.1）：有限生成双分次环 `@@M@@R\subset K[x,y]@@` 中，若齐次元 `@@M@@s_j=f_jx^{a_j}y^{b_j}@@` 的归一化次数逼近边界射线 `@@M@@\{(0,b)\}@@` 且 `@@M@@v(f_j)/(a_j+b_j)\to\gamma@@`，则任何齐次生成元组中必有形如 `@@M@@fx^0y^b@@` 的"射线上"生成元，其 `@@M@@v(f)/b\le\gamma@@`。理由是把 `@@M@@s_j@@` 展开为生成元的单项式，其一的系数赋值不超过 `@@M@@v(f_j)@@`；而 `@@M@@u_i>0@@` 的"离射线"生成元对次数与赋值的贡献均被 `@@M@@a_j@@` 的常数倍控制，极限中消失，故必须存在射线上生成元且其赋值比取到最小值。此处必须使用生成元的真实系数，仅知极限数值锥不够——这正是数值有效性不足以产生截面的代数根源。

再把几何装入该框架（Proposition 2.2）：取双有理—等维图 `@@M@@X\xleftarrow{p}W\xrightarrow{f}Y@@` 与基底上满足 `@@M@@p_*f^*A=0@@` 的有效修正 `@@M@@A\ge0@@`，定义极小除子 `@@M@@P(t)=\sum_Q\min_{E\mapsto Q}\coeff_E p^*D(t)/\ord_E(f^*Q)\cdot Q@@`。`@@M@@N_j@@` 有效拉回迫使 `@@M@@P(t_j)+\div_Y(h_j)\ge0@@`，故 `@@M@@h_j@@` 的幂成为双分次截面环的齐次元；端点引理在边界射线上选出赋值足够小的生成元，对应截面在 `@@M@@W@@` 上有效；先以 `@@M@@p@@` 前推消去修正 `@@M@@f^*A@@`（纯除子恒等式，与赋值无关），再比较赋值：中心性给 `@@M@@v(N)\ge0@@`，生成元选择给 `@@M@@v(N)\le0@@`，故恰为零。运算顺序的妙处是例外修正本身可以有正赋值——先消去后比较即可。

最难的几何输入是基底与有限生成。令 `@@M@@k=\{h\in\C(X)^\times:\ell((h)_\infty)=0\}@@` 为零极域（null-polar field），它是相对代数封闭的有限生成子域（`@@M@@k=\C@@` 时直接取固定支撑极限）。在模型 `@@M@@\C(Y)=k@@` 上验证两个条件：Jacobi 除子 `@@M@@K_{Z/X}@@` 的泛纤维截面空间恰为一维；在 `@@M@@\alpha@@` 的最大秩点处有 `@@M@@\ker\pi^*\alpha\subset\ker dg@@`，从而在非空开集上得到局部严格正性 `@@M@@\pi^*\alpha\ge c\,g^*\omega_H@@`。据此，姊妹篇的环体积度量定理给出有效修正 `@@M@@A_0@@` 及 `@@M@@-K_Y+A_0@@` 上开集严格正、平方范数局部可积的半正度量；另一姊妹篇的修正环定理再给出两个方向的多分次截面环有限生成（根基是 BCHM 伴随环理论）。

最后组装：用两个输入除子的有理组合解出趋于端点的参数 `@@M@@t_j@@`，把 `@@M@@N_j/m_j@@` 写成 `@@M@@D(t_j)+\div_X(h_j)@@` 且主修正 `@@M@@h_j@@` 落在 `@@M@@k@@` 中；上述命题随即产出 `@@M@@N\sim_{\Q}L@@`、`@@M@@v(N)=0@@`。通往不变截面靠阶—权恒等式（Lemma 6.1）：权为 `@@M@@w@@` 的特征截面沿单参数子群泛轨道的阶等于 `@@M@@\mu-w@@`（`@@M@@\mu@@` 为源头纤维权），故"阶恰为零"等价于"截面权达到纤维权"；再借 Białynicki-Birula 源分量、Atiyah–Bott 型不动点公式、半正硬 Lefschetz 与饱和行列式造出有界阶除子，主定理供出凸包含零的归一化截面权，通分取乘积即得不变截面。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准。两处关键输入直接引用同族姊妹篇：环体积度量定理（"Metric descent and rank-preserving contractions"）与修正环有限生成定理（"Integrable metrics and effectivity with controlled boundary"）；标量非消失结论还需 "Anticanonical nonvanishing from smooth semipositivity" 的紧单值结构定理与两步下降，本文与它们互相咬合成完整链条。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
