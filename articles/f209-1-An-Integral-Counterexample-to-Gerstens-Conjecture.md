---
layout: default
title: "An integral counterexample to Gersten's conjecture"
family: "209"
discipline: "Algebra"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An integral counterexample to Gersten's conjecture

> 结果族 209：Integral counterexamples to Gersten's conjecture　·　学科：Algebra　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文显式构造混合特征 `@@M@@(0,5)@@` 的二维分歧正则局部环 `@@M@@A=(V[x,y]/(5+x^4+y^4))_{(5,x,y)}@@`，证明 `@@M@@K_5(A)\to K_5(\operatorname{Frac}A)@@` 有非零核，推翻了无限制整系数版本的 Gersten 猜想，而此前所有正面结果都恰好绕开了这类分歧环。

## 问题背景

在代数 K 理论 (algebraic K-theory) 中，Gersten 猜想断言：对正则局部环 (regular local ring) `@@M@@A@@` 及其分式域 (fraction field) `@@M@@F@@`，增广剩余复形 `@@M@@0\to K_n(A)\to K_n(F)\to\bigoplus_{\operatorname{ht}\mathfrak p=1}K_{n-1}(\kappa(\mathfrak p))\to\cdots@@` 正合，第一项断言即"限制到分式域是单射"。问题源自 Gersten 1973 年的提问，处于局部化与剩余映射研究的核心；Quillen 对一般正则局部环正式陈述并证明了域上有限型代数的情形，Panin 解决了等特征情形。混合特征 (mixed characteristic) 下，Gillet–Levine、Geisser–Levine、Skalit、Druzhinin 的正面定理都要求环非分歧（`@@M@@p\notin\mathfrak m^2@@`）或对离散赋值环 (DVR) 光滑。Feld 此前给出模 3、度 2 的有限系数核，但在他的环上整系数映射仍单射——真正的整性反例悬而未决。

## 主要结果

取 `@@M@@V@@` 为 `@@M@@\Q_5@@` 八次非分歧扩张 (unramified extension) 的整数环，令
`@@M@@DA=\bigl(V[x,y]/(5+x^4+y^4)\bigr)_{(5,x,y)}.@@`
定理断言：`@@M@@A@@` 是二维 Noetherian 正则局部整环、混合特征 `@@M@@(0,5)@@`，极大理想为 `@@M@@(x,y)@@` 且 `@@M@@5\in(x,y)^4@@`，特殊纤维在闭点处奇异（环严重分歧、不平滑），并且
`@@M@@D\ker\bigl(K_5(A)\longrightarrow K_5(\operatorname{Frac}A)\bigr)\ne0.@@`
非零整类 `@@M@@\gamma@@` 由闭除子 `@@M@@\Spec\OO\hookrightarrow\Spec A@@` 推送而来。证明检测的是这个已被泛消去的类模 5 的约化，故同一环上系数 `@@M@@\Z/5@@` 的泛单射也失效；论文不决定 `@@M@@\gamma@@` 的阶，也不触及有理系数变体。

## 证明思路

策略源于一个简单事实：从闭除子推送的类在分式域上必为零；困难在于整性地造出这样的类，再证明它非零。

先做整性构造。在分圆环 `@@M@@S=\Z[\zeta,1/5]@@` 上取 `@@M@@\beta\in K_2(S;\Z/5)@@`，其系数边界为 `@@M@@[\zeta]@@`，经特征平均化后按分圆特征 (cyclotomic character) `@@M@@\chi@@` 变换；令 `@@M@@b@@` 为乘以 `@@M@@\beta@@`，两个 Bott 因子给出 `@@M@@b^2[\zeta-1]_5\in K_5(S;\Z/5)@@`，其整提升的障碍是 `@@M@@K_4(S)[5]@@`。论文用 `@@M@@\Pic(S)=0@@`（Minkowski 界小于 2）、范数剩余定理与 Brauer 群不变量的求和、Bott 元在域上的同构以及 Quillen 的有限生成定理，证明 `@@M@@K_4(S)@@` 没有 5-准素挠，于是得 `@@M@@c\in K_5(S)@@` 满足 `@@M@@c\bmod5=b^2[\zeta-1]_5@@`，且共轭满足 `@@M@@(\delta c)\bmod5=\chi(\delta)^2b^2[\delta u]_5@@`——特征平方正是后续检测的权重。再把 `@@M@@c@@` 限制到 `@@M@@L=H_0(\zeta)@@`（`@@M@@H_0=\Frac V@@`），并用 Quillen 的有限域计算 `@@M@@K_4(k)=0@@` 把它提升到赋值环 `@@M@@\OO@@` 上得 `@@M@@\widetilde c@@`。

再做几何实现。构造满局部同态 `@@M@@A\to\OO@@`（`@@M@@x\mapsto tX_0,\ y\mapsto tY_0@@`，其中 `@@M@@t^4=-5@@` 为分圆单值化元、`@@M@@X_0^4+Y_0^4=1@@` 为 Fermat 点的提升），闭浸入 `@@M@@i@@` 给出 `@@M@@\gamma=i_*\widetilde c\in K_5(A)@@`；其支集含于真除子，故在 `@@M@@\Frac A@@` 上整性地消失。值得强调：该除子虽由正则参数生成、是主除子，但自交公式与投影公式只给出 `@@M@@i^*i_*=0@@` 与 `@@M@@i_*i^*=0@@`，均不迫使 `@@M@@i_*=0@@`，高阶 K 群上的推送可以非零。

最后是非零检测。平展基变换 `@@M@@V\to L@@` 使该除子分裂为一般 Fermat 四次曲线 `@@M@@X^4+Y^4=Z^4@@` 上四个 `@@M@@L@@`-有理点 `@@M@@p_\delta@@`，且模 5 后 `@@M@@\gamma@@` 的限制为 `@@M@@\sum_\delta(p_\delta)_*\,\chi(\delta)^2b^2[\delta u]_5@@`。反设其为零：论文的一般判据先以两次 Bott 乘法把该关系"解捻"成普通的 tame 符号 (tame symbol)，再在光滑真算术曲面 (arithmetic surface) 上用 coniveau 复形的 `@@M@@d_1^2=0@@` 把水平除子的特殊化逼成主除子 (principal divisor)，从而特殊纤维 Picard 群 (Picard group) 的一个同态足以检出矛盾。具体实现：Fermat 四次曲线经 `@@M@@s=X/Y,\ w=Z^2/Y^2@@` 二次商映射到 genus-1 曲线 `@@M@@E:w^2=s^4+1@@`，取分支点为原点后 `@@M@@w\mapsto-w@@` 恰为群运算取负；令 `@@M@@\psi:\Pic(D_k)\to E(k)/5E(k)@@`。四个 `@@M@@p_\delta@@` 特殊化为 `@@M@@g_{\chi(\delta)}P@@`，其 `@@M@@\psi@@`-像为 `@@M@@\pm Q@@`，加权和为 `@@M@@4Q\ne0@@`（`@@M@@\#E(\F_{5^4})=640@@` 保证这样的 `@@M@@Q@@` 存在）。矛盾证得 `@@M@@\gamma\ne0@@`。值得玩味的是"位置"不可丢：只看四个全为 1 的赋值，标量和 `@@M@@1+4+4+1=0\in\F_5@@`，检验便失效；保留点本身才得到 `@@M@@4Q@@`。

## 可信度与备注

本文暂无形式化证明。姊妹篇在另一分歧环上独立证明了 `@@M@@K_3@@` 版本的整性反例（Steinberg 关系加范数赋值检验），两文互不依赖，合起来表明整 Gersten 失败在度 3 与度 5 都出现，但均未确定最小失败度。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。附录指认 Mochizuki 预印本 v8 中一个引理断言的失败，与主证明无依赖关系。

{% endraw %}
