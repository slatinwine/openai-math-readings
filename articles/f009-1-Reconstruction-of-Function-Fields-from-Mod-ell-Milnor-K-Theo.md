---
layout: default
title: "Reconstruction of Function Fields from Mod-ℓ Milnor K-Theory"
family: "009"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Reconstruction of Function Fields from Mod-ℓ Milnor K-Theory

> 结果族 009：Function-field reconstruction from Milnor K-theory and Galois data　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：特征不等于 `@@M@@\ell@@` 的代数闭常数域上、超越次数至少为 2 的函数域，可由 mod-`@@M@@\ell@@` Milnor K 群 `@@M@@K^{\mathrm M}_1/\ell@@`、`@@M@@K^{\mathrm M}_2/\ell@@` 及其双线性乘积重建出完美闭包与常数域；每个相容同构都来自域同构，歧义仅一个整体标量与 Frobenius 幂。

## 问题背景

双有理 anabelian 几何（birational anabelian geometry）追问：一个函数域能否被它的伽罗瓦型不变量恢复。Bogomolov 在 1991 年提出方案：当常数域代数闭时，不必动用整个绝对伽罗瓦群，只用交换子位于中心的小 pro-`@@M@@\ell@@` 商群即可。Bogomolov–Tschinkel 与 Pop 在 2008–2012 年对有限域代数闭包上的常数完成了重建，Pop 2018 年又处理了相对超越次数大于 2 的一般代数闭常数。有限系数（mod-`@@M@@\ell@@`）版本长期多一格缺口：Topaz 2016 年在相对超越次数至少 5 时证明了同构定理，但需要额外把"全部有理子群"作为输入一并给定。难点有二：单个 mod-`@@M@@\ell@@` 类只记录除子阶模 `@@M@@\ell@@` 的值，重数被 `@@M@@\ell@@` 整除的除子会彻底"隐身"；无穷群压缩成一个有限域上的向量空间后，全局重建失去抓手。本文把有理子域从乘积结构本身中提取出来，将重建推进到一切相对维数 `@@M@@\ge 2@@`，且不再需要任何附加输入。

## 主要结果

固定素数 `@@M@@\ell@@`，记 `@@M@@\Lambda=\mathbb F_\ell@@`。对特征异于 `@@M@@\ell@@` 的域 `@@M@@F@@`，令 `@@M@@V_F=F^\times/(F^\times)^\ell=K^{\mathrm M}_1(F)/\ell@@`，`@@M@@W_F=(V_F\otimes V_F)/R_F=K^{\mathrm M}_2(F)/\ell@@`，其中 `@@M@@R_F@@` 是 Steinberg 关系（Steinberg relation）`@@M@@[x]\otimes[1-x]@@` 张成的子空间，乘法 `@@M@@m_F@@` 即 Milnor 乘积。`@@M@@\Lambda@@`-线性同构 `@@M@@\Theta:V_K\to V_L@@` 称为相容的（compatible），若 `@@M@@(\Theta\otimes\Theta)(R_K)=R_L@@`。纯不可分扩张在 `@@M@@V@@`、`@@M@@W@@` 上诱导典范同构（`@@M@@p^r@@` 次幂映射分别乘 `@@M@@p^r@@` 与 `@@M@@p^{2r}@@`，模 `@@M@@\ell@@` 可逆），故域同构天然作用于这组数据。

**主定理**：设 `@@M@@K/k@@`、`@@M@@L/l@@` 为任意代数闭域上的有限生成扩张，`@@M@@\mathrm{char}\,k,\mathrm{char}\,l\ne\ell@@` 且相对超越次数 `@@M@@\ge 2@@`，则典范映射
`@@M@@D\mathrm{Isom}^i_{\mathrm F}(K,L)\longrightarrow \mathrm{Isom}_{\mathrm M}(V_K,V_L)/\Lambda^\times@@`
是双射。这里左边是完美闭包（perfect closure）`@@M@@K^i\to L^i@@` 之间保常数的域同构，模去 Frobenius 复合（正特征时）。通俗地说：这组数据完全确定完美闭包及其常数域；每个相容同构 `@@M@@\Theta@@` 都等于某个域同构 `@@M@@\alpha@@` 诱导的 `@@M@@\alpha_1@@` 乘上一个 `@@M@@\mathbb F_\ell^\times@@` 中的整体标量；正特征下 `@@M@@\alpha@@` 本身只剩 Frobenius 幂的自由度，而 `@@M@@\ell=2@@` 时连标量歧义也消失。相容同构的存在还强制两域特征与超越次数相等。

## 证明思路

证明按七个环环相扣的步骤展开。先对偶化：`@@M@@\Theta@@` 转到紧特征空间 `@@M@@A_F=\mathrm{Hom}(F^\times,\Lambda)@@` 上得 `@@M@@\Phi@@`。一对特征 `@@M@@f,g@@` 称交错对（alternating pair），若 `@@M@@f(x)g(1-x)=f(1-x)g(x)@@`；此条件恰好等价于行列式泛函零化 `@@M@@R_F@@`，故被 `@@M@@\Phi@@` 保持。借助 Topaz 记录的交错对赋值论，命题证明 `@@M@@A_F@@` 的最大交错子空间维数恰为 `@@M@@\mathrm{trdeg}(F/\kappa)@@`，于是 `@@M@@\Theta@@` 首先强制两域超越次数相等；进而准素除子（quasi-prime divisor）的惯性线可刻画为两个满维交错子空间的交，分解空间由与惯性的交错性唯一确定，由此逐级匹配两侧剩余域的特征空间。

再恢复曲线子域（curve subfield，即相对代数闭的一变元中间域）。mod-`@@M@@\ell@@` 类会丢失重数被 `@@M@@\ell@@` 整除的除子，对策是过渡到剩余曲线：用 Pop 的极小惯性密度定理识别常数域为有限域之代数闭包的剩余曲线及全部点序线（point-order lines）。随后是关键的支撑估计：任取有限个独立类，可造一条亏格 `@@M@@\le G_X@@` 的剩余曲线（以 Bertini 定理逐次切超平面、保持 Kummer 覆盖不可约，再把有限定义数据特殊化到有限剩余域上实现），使每个类在固定模型上的支撑度恰等于曲线上非零点阶的个数；对 `@@M@@t\in K\setminus k@@` 取五个锚参数，Riemann–Hurwitz 对相应铅笔的五条纤维给出一致界——系数 `@@M@@5(1-1/\ell)-2>0@@` 对包括 `@@M@@\ell=2@@` 的一切素数为正，这正是"五"的来由。

接着用关联簇（incidence variety）方法落地：无穷多个有界度除子装入有限型参量空间，取一条参数曲线 `@@M@@T‘@@`，关联簇 `@@M@@Z’\subset X\times T'@@` 的函数域满足合成恒等式 `@@M@@M=LP_0@@`。难点是一条参数曲线须对所有类同时有效，故不能逐类缩小开集，而在几何泛纤维分裂后经有限扩张与正规化传递；最终用 Hilbert 第 90 定理式的常数下降与"两曲线子域之交有限维"，把 `@@M@@\Theta(V_E)@@` 精确降为某曲线子域的 `@@M@@V_P@@`。合成恒等式保证精确下降——范数本会把模 `@@M@@\ell@@` 信息抹掉。

然后恢复域运算：光滑点处两个局部参数之商给出"好有理子域"，它们生成整个函数域；点序线匹配给出双射 `@@M@@B_t@@`。在光滑点爆破（blowup），例外除子可同时探测多个好函数的取值；分析加法关系 `@@M@@z=t+cs@@` 得"搬运加法"，把 `@@M@@B_t@@` 与仿射群的共轭压入 `@@M@@\mathcal H_l@@`（射影线性变换与 Frobenius 幂生成的群），而余有限单射的完美有理函数必属 `@@M@@\mathcal H_l@@`；由此对齐常数域得 `@@M@@\sigma:k\cong l@@`，并证明一切代数关系被保持，得到 `@@M@@\alpha:K^i\xrightarrow{\sim}L^i@@`。最后收尾：`@@M@@\alpha_1^{-1}\Theta@@` 固定每个好有理子域，区分真除子的引理与共享的爆破惯性线把它缝成单个整体标量；作用为标量的自同构只能是恒等或 Frobenius 幂。全程不把 mod-`@@M@@\ell@@` 同构提升为 pro-`@@M@@\ell@@` 同构。

## 可信度与备注

本文主结果暂无形式化证明，请以社区核验为准；OpenAI 官方亦声明"未经形式化的结果可能有问题"。它与族内姊妹篇互相支撑：《The Bogomolov–Pop reconstruction theorem》给出 pro-`@@M@@\ell@@` 交换子为中心版本，其有界支撑与关联方法被本文显式改编到有限系数；《Reconstruction from Milnor K-theory modulo the characteristic》则处理 `@@M@@\ell@@` 等于特征的另一侧。三者合力覆盖 Bogomolov–Pop 纲领的单素数数据点，且本文声明不引用任何 pro-`@@M@@\ell@@` 域重建定理作为前提，论证自成一体。

{% endraw %}
