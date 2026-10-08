---
layout: default
title: "Elementary positivity of chromatic quasisymmetric functions"
family: "169"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Elementary positivity of chromatic quasisymmetric functions

> 结果族 169：Shareshian–Wachs elementary positivity　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

给图的顶点涂色，相邻顶点不许同色——就像给地图涂色。把所有合法涂色方案打包成一个大函数，再拆成一排"标准零件"，问每张零件前的账单是否都不为负。这类"正性"问题看似只是记账，实则关系到系数能否有组合或几何上的良好解释；本文对一大家族图给出了肯定答案。

**关键词卡片**

- 色对称函数（chromatic symmetric function）：把图的所有合法染色打包成的一个对称函数
- 初等对称函数（elementary symmetric function）：`@@M@@e_k@@`=取 `@@M@@k@@` 个不同变量相乘再全部求和，一套"标准零件"
- 初等正性（elementary positivity）：拆成标准零件后，每张账单都是系数非负的整系数多项式
- 单位区间图（unit interval graph）：顶点对应区间、区间重叠才连边的图
- 图逆序（graph inversion）：置换中两端成边的逆序对，给账单提供 `@@M@@q@@` 的幂次

**看个具体例子**

把最简单的三点路径 `@@M@@P_3@@`（顶点连成 1—2—3）代入，公式卡为：

`@@M@@\chi_{P_3}(X;q)=q\,e_{(2,1)}(X)+(1+q+q^2)\,e_{(3)}(X)@@`

两张账单 `@@M@@q@@` 与 `@@M@@1+q+q^2@@` 的每个系数都是非负整数。主定理证明对任何自然单位区间图 `@@M@@G@@` 都有 `@@M@@\chi_G(X;q)=\sum_{\sigma}q^{\operatorname{ginv}(\sigma)}e_{\theta(\sigma)}(X)@@`，其中 `@@M@@\sigma@@` 取遍一个显式的有限置换集——每张账单都是"数得出来"的计数多项式，非负性自动成立。

**为什么值得关心**

这解决了 Shareshian–Wachs 猜想的初等正性部分；取 `@@M@@q=1@@` 退化为经典的 Stanley–Stembridge 正性，还连带给出 Hessenberg 簇上同调的直和分解。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

本文证明：任一自然单位区间图（natural unit interval graph）的色拟对称函数在初等对称函数基下的系数全属于 `@@M@@\mathbb N[q]@@`，从而解决了 Shareshian–Wachs 猜想的初等正性部分，并给出把这些系数显式实现为带图逆序权重的置换计数之组合见证。

## 问题背景

Stanley 于 1995 年引入色对称函数（chromatic symmetric function），把图的色多项式提升为对称函数；Stanley–Stembridge 猜想断言，`@@M@@(3+1)@@`-free 偏序的不可比图（incomparability graph）的色对称函数是初等正的（elementary-positive）。经 Guay-Paquet 归约，问题化归到自然标号的单位区间图：顶点为 `@@M@@[n]@@`，边为满足 `@@M@@i<j\le h(i)@@` 的点对 `@@M@@\{i,j\}@@`，其中 `@@M@@h@@` 弱增。Shareshian–Wachs 进一步引入按真染色（proper coloring）的上升边数加权的 `@@M@@q@@`-细化 `@@M@@\chi_G(X;q)@@`，证明了它的对称性与 Schur 正性，并猜想其初等基系数属于 `@@M@@\mathbb N[q]@@`（连同单峰性）。卡点在于：染色定义在单项式基下天然非负，换到初等基必然出现减法；Hikita 在 2024 年给出的概率公式只对正实数 `@@M@@q@@` 证明数值非负，得不到系数式非负，更没有逐分拆的置换解释。

## 主要结果

主定理：存在确定性的可终止过程，对自然单位区间图 `@@M@@G@@` 与任一"下降步必落在边上的置换" `@@M@@\sigma\in D_G^0@@`，输出一个分拆（partition）`@@M@@\theta_G(\sigma)\vdash n@@`，使得
`@@M@@D\chi_G(X;q)=\sum_{\sigma\in D_G^0}q^{\ginv_G(\sigma)}\,e_{\theta_G(\sigma)}(X),@@`
其中 `@@M@@\ginv_G(\sigma)@@` 统计两端成边的逆序对（graph inversion）。于是每个初等系数恰是某个显式有限置换集的生成多项式，自动属于 `@@M@@\mathbb N[q]@@`，且次数不超过边数 `@@M@@|E(G)|@@`。例如三点路径图的展开为 `@@M@@q\,e_{(2,1)}+(1+q+q^2)e_{(3)}@@`。取 `@@M@@q=1@@` 重新给出经典的 Stanley–Stembridge 正性；结合 Brosnan–Chow 与 Guay-Paquet 的表示论等式，还得到 Hessenberg 簇（Hessenberg variety）上同调在 Tymoczko 点作用下按 Young 置换模（Young permutation module）的直和分解。定理不涉及初等单峰性。

## 证明思路

证明分"归约—正性—取见证"三大阶段。第一步把染色计数换成代数系数：令 `@@M@@q=v^2@@`，进入以顶点重数向量为指标的中心量子环面（quantum torus），乘法按由有序边决定的交错型 `@@M@@\Omega@@` 扭曲；把 `@@M@@G@@` 嵌入一个更大的辅助单位区间图，令 `@@M@@E_k@@` 为全部独立集（independent set）`@@M@@k@@` 点对应的单项式之和，用双色交换对合证明诸 `@@M@@E_k@@` 两两交换，于是可令 `@@M@@e_k(Y)=E_k@@` 做"图字母表"赋值。染色核恒等式 `@@M@@[e_\lambda(X)]\chi_G(X;v^2)=v^M[X_u]m_\lambda(Y)@@` 把正性问题化为单项式对称函数 `@@M@@m_\lambda(Y)@@` 的系数非负，这里 `@@M@@u@@` 是原顶点指数和、`@@M@@M=|E(G)|@@`。第二步把每个 `@@M@@m_\lambda(Y)@@` 认定为散射图（scattering diagram）中单个正 `@@M@@\theta@@`-截面（theta section）在全负腔的取值：墙是超平面片段，携带量子环面级数的共轭作用，截面由入射系数按根度递归唯一确定；关键引理"正量子因子反序后仍正"把新重数实现为显式分次向量空间的维数，从而保证各截面系数逐项非负。第三步构造三角图：设 `@@M@@D@@` 个彼此独立的锚点 `@@M@@d_1,\ldots,d_D@@` 及按位相排序的桥顶点，任何 `@@M@@G@@` 都能作为某 `@@M@@D@@` 个桥上的有序诱导子图嵌入；反复做区间旋转（本质是根变换 `@@M@@p\mapsto -p@@`），并借助 `@@M@@E_1@@` 正幂的支撑论证排除只含桥不含锚的指数，最终证明 `@@M@@m_\lambda(Y)=\Theta_{\lambda_1d_1+\cdots+\lambda_Dd_D}@@`——至此系数式正性已经证完。第四步从截面中提取个体见证：先把输入置换反转进入容许词域，把词切成递增独立集"包"；局部包交换把跨墙输运化为带装饰跳跃（decorated jump）的能量保持双射，沿事先固定的公共母线回溯得到有限跳跃史，其生成级数恰为 `@@M@@[X_u]\Theta_x^{H_-}@@`；再用 Garsia–Milne 对合原理式的有限交错路消元，把"必需掩码"双射细化为"精确掩码"双射，终点的弱减锚词之重数读出输出分拆。能量界 `@@M@@-M\le E\le M@@` 与奇偶性 `@@M@@E\equiv M\pmod 2@@` 保证 `@@M@@q=v^2@@` 的转换合法；最后由互反律 `@@M@@c_\lambda(q)=q^Mc_\lambda(q^{-1})@@` 换回 `@@M@@D_G^0@@` 的约定，完成主定理。

## 可信度与备注

按任务标注，本文主结果尚无 Lean 形式化证明，也未经过完整同行评议，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。作为结果族 169 的主篇，它与 Hikita 的概率式证明以及 Griffin–Mellit–Romero–Weigl–Wen 的 Macdonald 展开路线同族互证，并把此前"正实数 `@@M@@q@@` 处数值非负"强化为系数式 `@@M@@\mathbb N[q]@@` 正性与显式置换见证；算法可终止但无多项式时间界。另需注意，定理未触及猜想中初等单峰性的那一半。

{% endraw %}
