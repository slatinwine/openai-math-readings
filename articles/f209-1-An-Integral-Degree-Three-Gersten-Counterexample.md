---
layout: default
title: "An integral degree-three Gersten counterexample"
family: "209"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An integral degree-three Gersten counterexample

> 结果族 209：Integral counterexamples to Gersten's conjecture　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文在混合特征 `@@M@@(0,5)@@` 的二维分歧正则局部环——分圆五次平面模型 `@@M@@(X-Z)^5-XY^4+Y^5+\zeta Z^5=0@@` 特殊点处的局部环——上构造整类 `@@M@@c\in K_3(A)@@`，它在分式域上变为零但自身非零，从而在度 3 否定无限制整系数 Gersten 猜想。

## 问题背景

Gersten 猜想断言正则局部环 (regular local ring) `@@M@@B@@` 的增广剩余复形 `@@M@@0\to K_n(B)\to K_n(F_B)\to\cdots@@` 正合，首当其冲是到分式域 (fraction field) 的单射性；Gersten 最初的提问之一是剩余域到离散赋值环的转移映射是否为零，局部化理论把转移的像与这个核等同起来。Quillen 证明了域上有限型代数的情形，Sherman 处理等特征 DVR，Panin 完成等特征情形；混合特征 (mixed characteristic) 下 Geisser–Levine、Druzhinin 要求对离散赋值环 (DVR) 光滑，Skalit 要求非分歧。难点在整性：Feld 的模 3 度 2 反例只有有限系数核，整系数映射在那儿仍单射——系数核可能有非零边界而无法整提升，即使提升，泛像也可能被系数素整除。本文的环满足 `@@M@@5\in\mathfrak m_A^2@@` 且特殊纤维奇异，落在所有已知正面定理的射程之外。

## 主要结果

固定本原五次单位根 `@@M@@\zeta@@`，令 `@@M@@L=\Q_5(\zeta)@@`、`@@M@@V=\OO_L@@`、`@@M@@\pi=1-\zeta@@`。设 `@@M@@\mathcal X\subset\mathbb P^2_V@@` 为五次超曲面 `@@M@@(X-Z)^5-XY^4+Y^5+\zeta Z^5=0@@`，取特殊纤维上的点 `@@M@@m=[0:0:1]@@`，令 `@@M@@A=\OO_{\mathcal X,m}@@`。定理断言：`@@M@@A@@` 是混合特征 `@@M@@(0,5)@@` 的二维 Noetherian 正则局部整环，且 `@@M@@\pi\in\mathfrak m_A^2@@`（分歧、不平滑）；存在整类 `@@M@@c\in K_3(A)@@` 使得
`@@M@@Dc|_{\Frac A}=0,\qquad c|_{A[1/\pi]}\bmod5\ne0\ \ \text{于}\ G_3(A[1/\pi];\Z/5),@@`
特别地 `@@M@@K_3(A)\to K_3(\Frac A)@@` 不单。第二式立得 `@@M@@c\notin5K_3(A)@@`；论文不决定 `@@M@@c@@` 的阶及其有理化像。与 Feld 的做法不同，这里的整提升被直接安排在除子上：支集先保证泛消去，非零性留待范数检验。

## 证明思路

先建立模型与算术输入。特殊纤维多项式 `@@M@@X^5-XY^4+Y^5@@` 借 `@@M@@s^5-s+1@@` 在 `@@M@@\F_5@@` 上的不可约性（其根的 Frobenius 轨道长度恰为 5）保证一般曲线 `@@M@@C=\mathcal X_L@@` 积分；定义方程模 `@@M@@\mathfrak m^2@@` 余 `@@M@@-\pi@@`，故 `@@M@@A@@` 正则且 `@@M@@\pi\in\mathfrak m_A^2@@`。关键除子取 `@@M@@y=0@@`：其商 `@@M@@S=A/yA\cong V[t]/((t-1)^5+\zeta)@@` 是 Eisenstein 多项式 (Eisenstein polynomial) 定义的离散赋值环，单值化元 `@@M@@t@@` 的分式域 `@@M@@D@@` 在 `@@M@@L@@` 上全分歧五次，范数 (norm) 满足 `@@M@@N_{D/L}(t)=\pi@@`，且 `@@M@@(1-t)^5=\zeta@@`；对应闭点 `@@M@@q_0@@` 的剩余域 (residue field) 为 `@@M@@D@@` 而剩余次数 (residue degree) 为 1；这一"全分歧但剩余次数为一"的落差正是非平凡检验的来源。模型的核心算术事实是：凡不在 `@@M@@m@@` 特殊化的闭点，剩余次数必被 5 整除。

再构造整类。取 `@@M@@\beta\in K_2(L;\Z/5)@@` 边界为 `@@M@@[\zeta]@@`，令 `@@M@@a_D=\beta_D\cdot[t]\in K_3(D;\Z/5)@@`。其系数边界 `@@M@@=\pm5\{\eta,1-\eta\}=0@@`——这里正是 Steinberg 关系 (Steinberg relation) 出场：`@@M@@\zeta=\eta^5@@` 与 `@@M@@t=1-\eta@@` 把 `@@M@@[\zeta]\cdot[t]@@` 变成五倍的 Steinberg 符号。有个细节值得留意：`@@M@@\beta_D@@` 自身的边界 `@@M@@[\zeta]@@` 在整群 `@@M@@K_1(D)=D^\times@@` 中并非零，`@@M@@\zeta@@` 成为五次幂只使它在 `@@M@@D^\times/D^{\times5}@@` 中消失；真正杀死乘积 `@@M@@a_D@@` 之边界的是 Steinberg 关系。故 `@@M@@a_D@@` 可整提升到 `@@M@@K_3(D)@@`；又因 Quillen 算得 `@@M@@K_2(\F_5)=0@@`，经局部化再提升到 `@@M@@K_3(S)@@`；沿除子闭浸入推送得 `@@M@@c\in K_3(A)@@`，支集性质保证 `@@M@@c|_{\Frac A}=0@@`，且 `@@M@@c|_T\bmod5=i_*a_D@@`（`@@M@@T=\Spec A[1/\pi]@@`）。

最后用范数赋值检验非零。域论引理（Friedlander–Suslin 动机到 K 理论谱序列、Suslin 的乘法比较、范数剩余定理，配合局部域的 `@@M@@5@@`-上同调维数为 2）给出同构 `@@M@@\theta_E:E^\times/E^{\times5}\cong K_3(E;\Z/5)@@`；投影公式使域转移对应范数，于是赋值泛函 `@@M@@\lambda_L=(v_L\bmod5)\circ\theta_L^{-1}@@` 杀掉一切来自剩余次数被 5 整除的域的转移类，而 `@@M@@a_D@@` 的转移赋值为 `@@M@@v_L(\pi)=1@@`。检测时注意 `@@M@@T@@` 是 `@@M@@C@@` 的仿射开集 `@@M@@U_h@@` 的平展逆极限而非开子集：Quillen 连续性定理把 `@@M@@c|_T\bmod5@@` 的消失降到某个有限阶段 `@@M@@U_h@@`；局部化序列把 `@@M@@w=(q_0)_*\theta_D(t)@@` 写成被省略点上支撑的类之和，这些点的剩余次数都被 5 整除，故逐项被 `@@M@@\lambda_L@@` 杀死，得 `@@M@@\lambda_L(p_*w)=0@@`；但直接计算给出 `@@M@@\lambda_L(p_*w)=v_L(N_{D/L}t)=1@@`，矛盾。整个论证在可能奇异的 `@@M@@C@@` 上以凝聚 G-理论 (coherent K-theory) 进行，避免任何光滑性假设。

## 可信度与备注

本文暂无形式化证明。姊妹篇在 `@@M@@5+x^4+y^4@@` 模型上独立给出度 5 的整性反例（分圆整提升加 Picard 特殊化检验），两文互不依赖、互不引用，合观之无限制整系数 Gersten 猜想在度 3 与度 5 均告失败，但均未确定最小失败度。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
