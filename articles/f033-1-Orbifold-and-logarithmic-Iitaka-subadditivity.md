---
layout: default
title: "Orbifold and logarithmic Iitaka subadditivity"
family: "033"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Orbifold and logarithmic Iitaka subadditivity

> 结果族 033：Iitaka subadditivity, variation, and logarithmic additivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

论文证明了 Campana 的轨道体（orbifold）Iitaka 次可加性猜想：对 Fujiki 类 `@@M@@\mathcal C@@` 紧复流形上系数取自 `@@M@@[0,1]\cap\mathbf Q@@` 的 SNC 边界（含系数一），`@@M@@\kappa(X,K_X+\Delta)\ge\kappa(F,K_F+\Delta_F)+\kappa(f\mid\Delta)@@`，普通与对数次可加性均为其推论。

## 问题背景

Kodaira 维数（Kodaira dimension）用多重典范形式（pluricanonical forms）的增长速度度量代数簇的"双有理体积"。对一个连通纤维的纤维化 `@@M@@f:X\to Y@@`，Iitaka 的次可加性问题问：总体维数是否至少等于一般纤维与基之和，`@@M@@\kappa(X)\ge\kappa(F)+\kappa(Y)@@`？对数版本允许沿约化边界取极点，从而覆盖开簇。此前的经典结果各从纤维化的不同部位汲取正性：Kawamata 处理曲线基与有好极小模型的纤维，Viehweg 以弱正性（weak positivity）处理一般型基上的加法，Kollár 处理一般型纤维；Birkar 处理总维数 `@@M@@\le 6@@`，Cao–Păun 与 Hacon–Popa–Schnell 处理阿贝尔基与最大 Albanese 维数基；对数方向有 Kovács–Patakfalvi、Hashizume、Maehara 等的条件性结果。而 Campana 的轨道体猜想走得更远：多重纤维的信息以"下确界重数"（inf multiplicity）记入轨道体基，猜想要求总体维数不小于纤维维数加这个轨道体基的双有理不变维数。瓶颈在于：传统正性方法要么要求纤维一般型，要么要求好极小模型，而轨道体陈述不允许任何此类假设。

## 主要结果

设 `@@M@@X@@` 为 Fujiki 类 `@@M@@\mathcal C@@`（双有理等价于紧 Kähler 空间）中的光滑紧连通复流形，`@@M@@\Delta=\sum_i\delta_i\Delta_i@@` 为系数 `@@M@@\delta_i\in\mathbf Q\cap[0,1]@@` 的有理单连通交叠（SNC）边界，`@@M@@f:X\to Y@@` 为到正规紧不可约复空间上的满全纯连通纤维映射。对源素除子 `@@M@@E@@` 记 `@@M@@m_\Delta(E)=1/(1-\Delta_E)@@`；轨道体基定义为 `@@M@@B(f,\Delta)=\sum_D(1-1/m(f,\Delta;D))D@@`，其中 `@@M@@m(f,\Delta;D)=\min_{E\mapsto D}\operatorname{ord}_E(f^*D)\,m_\Delta(E)@@`；不变量 `@@M@@\kappa(f\mid\Delta)@@` 是对所有初等模型变换取下确界的 `@@M@@\kappa(Y',K_{Y'}+B(f',\Delta'))@@`。

**定理（轨道体次可加性）**：对非常好光滑纤维 `@@M@@F@@` 与限制 `@@M@@\Delta_F=\Delta|_F@@`，有
`@@M@@D\kappa(X,K_X+\Delta)\ge\kappa(F,K_F+\Delta_F)+\kappa(f\mid\Delta).@@`
这正面解决了 Campana 猜想在有理 SNC、Fujiki 类 `@@M@@\mathcal C@@` 表述下的形式，且包括系数一的情形。由此推出：对数次可加性 `@@M@@\kappa(X,K_X+D_X)\ge\kappa(F,K_F+D_F)+\kappa(Y,K_Y+D_Y)@@`；准射影形式 `@@M@@\bar\kappa(U)\ge\bar\kappa(U_v)+\bar\kappa(V)@@`；任意特征零代数闭域上的普通次可加性 `@@M@@\kappa(X)\ge\kappa(F)+\kappa(Y)@@`。此外还得到沿 Campana 核心（core）的等式 `@@M@@\kappa(X,K_X+\Delta)=\kappa(G,K_G+\Delta_G)+\dim C@@`、"`@@M@@\kappa=0@@` 蕴含特殊（special）"、以及核心塔分解 `@@M@@c_{(X,\Delta)}=(M\circ r)^n@@`。

## 证明思路

先设右端两项非负，令 `@@M@@k=\kappa(F,K_F+\Delta_F)@@`。第一步做相对 Iitaka 约化：取相对 Iitaka 映射得 `@@M@@X\xrightarrow{g}W\xrightarrow{h}Y@@`，使 `@@M@@\dim W_y=k@@` 且非常好 `@@M@@g@@`-纤维 `@@M@@G@@` 满足 `@@M@@\kappa(G,K_G+\Delta_G)=0@@`，于是在充分可除次数下相对多重典范系统秩为一。第二步是"秩一比较"：取相对生成元 `@@M@@s@@`，作 `@@M@@m@@` 次根的正规化循环覆盖（cyclic cover）并函子式消解，其重言式顶形式张成根特征线（一维性由 `@@M@@\kappa=0@@` 强迫）；再经局部构造、相容极化与张量不变量下降，把该线的幂放入 `@@M@@W@@` 上带整格的纯 Hodge 变分（variation of Hodge structures）的最高 Hodge 步，得到有理线丛 `@@M@@M@@`（Hodge 线）与边界 `@@M@@T@@`，满足 `@@M@@B(g,\Delta)\le T\le1@@`，并在固定原模型上建立精确的截影同构 `@@M@@H^0(X,q(K_X+\Delta))\simeq H^0(W,q(K_W+T+M))@@`，它保持乘积与比值。核心计算是 Hodge 框架在基素除子上的阶 `@@M@@\beta_D=\min_{g(E)=D}(l_E+1-a_E)/a_E@@` 与原始形式阶 `@@M@@\alpha_D=\min_{g(E)=D}(l_E+\delta_E)/a_E@@` 之差 `@@M@@T_D=\alpha_D-\beta_D@@`；系数一的边界会引入混合 Hodge 结构，靠纯权数分次与抛物扩张（parabolic extension）处理。第三步引入两个正性输入。其一是伴随正性（adjoint positivity）：周期映射给出第二个纤维化 `@@M@@p:W\to S@@`（`@@M@@S@@` 光滑射影）及 nef 线丛 `@@M@@P@@`，使 `@@M@@M=p^*P@@` 且 `@@M@@K_S+aP@@` 为大（big）；其证明综合 Griffiths–Schmid–Cattani–Kaplan–Schmid 的曲率与边界理论、周期商的射影化（Villadsen 紧化、Bakker–Brunebarbe–Tsimerman 方法）、Brunebarbe–Cadorel 的 `@@M@@K_S+D@@` 大性，并用 André 单值正规性与 Bakker–Tsimerman 的 Ax–Schanuel 定理分析只保留该线时映射的纤维。其二是"一般型加法"：以 Kovács–Patakfalvi 的稳定族正性（经辅助射影族再下降回类 `@@M@@\mathcal C@@`）与 Fujino 弱正性，把纤维上已大的对数典范除子加成 `@@M@@\kappa(V,K_V+T)\ge\dim F+\kappa(Y,K_Y+C)@@`。最后是伴随加法原理的截面算术：取 `@@M@@c<1@@` 接近一，先用一般型加法得 `@@M@@\kappa(W,D+cM+\eta p^*A)\ge k+\kappa(Y,K_Y+C)@@`；再由弱正性与"大基扭转后的有效性"引理造出 `@@M@@E_-=D+aM-\lambda p^*A@@` 的一个固定非零截影 `@@M@@e@@`；令 `@@M@@\theta=(1-c)/(a-c)@@`，凸组合 `@@M@@D+M=(1-\theta)E_++\theta E_-@@` 恰好同时消去两个 ample 扰动项并给 `@@M@@M@@` 系数一；用 `@@M@@e@@` 的幂乘把 `@@M@@E_+@@` 的截影嵌入 `@@M@@D+M@@` 的系统而不改变截影比值，故线性系的像维不变，得 `@@M@@\kappa(W,K_W+T+M)\ge k+\kappa(Y,K_Y+C)@@`。最后由秩一比较把这些截影提升回原光源，结合 `@@M@@\kappa(Y,K_Y+C)\ge\kappa(f\mid\Delta)@@` 即得定理。全程是精确的截影论证，既不需要 `@@M@@P@@` 的丰度（abundance），也不需要 Kodaira 维数的任何极限式断言。

## 可信度与备注

本篇主结果暂无 Lean 形式化证明。它是结果族 033 的地基：其约化 SNC 对数次可加性与全周期伴随比较接口，直接支撑姊妹篇《Logarithmic Kodaira dimension and whole-fiber variation》证明变异性不等式；《The reverse logarithmic Kodaira inequality and additivity》则只用其下界来拼接可加性等式。按论文自己的说明，两篇姊妹篇的结论均不反过来用于本篇定理的证明。依照 OpenAI 官方声明，未经形式化的结果可能存在问题，最终请以社区核验为准。

{% endraw %}
