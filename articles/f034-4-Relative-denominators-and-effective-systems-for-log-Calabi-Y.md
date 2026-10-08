---
layout: default
title: "Relative denominators and effective systems for log Calabi-Yau fibrations"
family: "034"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Relative denominators and effective systems for log Calabi-Yau fibrations

> 结果族 034：Log abundance for compact Kähler spaces under logarithmic Iitaka subadditivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一摞分数各有各的分母：二分之一、三分之一、七分之一……通分时总想找一个谁都能用的公分母。这篇论文研究纤维化世界里类似的"分母问题"：每族形状的"变形账本"（模性部分）系数都落在某个分母上，作者证明在不超过四维、边界系数来自固定有限集时，整类账本共用一个公分母——而且它只看维数和系数集，不看具体哪一族。

**关键词卡片**

- log Calabi–Yau 纤维化（log Calabi–Yau fibration）：一族形状 `@@M@@f:X\to Z@@`，每片纤维的固有曲率加扣除项恰好是底上数据的拉回
- 典范丛公式（canonical bundle formula）：把总曲率拆账的公式——奇纤维的"磨损"记入判别除子，纤维的变形方式记入模性部分
- 模性 b-除子（moduli b-divisor）：记录纤维如何随底移动的账本，同时活在所有高阶双有理模型上
- 一致分母（uniform denominator）：对整类纤维化通用的公分母 `@@M@@p=p(d,\Phi)@@`，只依赖维数与系数集

**看个具体例子**

定理的数字版：固定维数 `@@M@@d\le4@@` 与系数集 `@@M@@\Phi@@`（比如只许系数 `@@M@@1/2@@`），就存在整数 `@@M@@p=p(d,\Phi)@@`，使任何符合条件的纤维化在决定模型上都能把账本写成

`@@M@@M=\tfrac1p\,D_{\mathbb Z}@@`（`@@M@@D_{\mathbb Z}@@` 为整 Cartier 除子）

而且当底除子"大"（含量足够多）时，存在统一次数 `@@M@@m(d,\Phi)@@` 使每个倍数的取整伴随系非空、截面比生成底上全部有理函数；四维 klt 对收缩到有理连通底时，更有 `@@M@@r(\Phi)(K_X+B)\sim 0@@`——账被整数倍彻底清零。就像无论遇到四分之一还是六分之一，通分到 12 总够用；这里的"12"换成只依赖 `@@M@@(d,\Phi)@@` 的 `@@M@@p@@`。

**为什么值得关心**

一致分母是"有效饭高纤维化"机器里的发动机零件，没有它后面所有统一次数都无从谈起；本文正是族内的四维先行稿，被任意维数的姊妹篇直接引用推广。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
在维数至多四、边界系数取自固定有限有理集时，证明 log Calabi–Yau 纤维化的模性 b-除子有一致 Cartier 分母与一致平凡化次数；当底除子大时，一致的取整伴随系的截面比生成整个底函数域。

## 问题背景

对满足 `@@M@@K_X+B\sim_{\mathbb Q}f^*D@@` 的收缩 `@@M@@f:X\to Z@@`，典范丛公式 (canonical bundle formula) 把伴随除子分解为奇纤维的贡献——判别除子 (discriminant) `@@M@@B_Z@@`——与底上的模性部分 (moduli part) `@@M@@\mathbf M@@`。Ambro 与 Fujino–Gongyo 的定性理论保证 `@@M@@\mathbf M@@` 在某个双有理模型上是 nef 的有理 Cartier 除子，但其 Cartier 倍数可能依赖于具体纤维化；有效应用（如有效饭高纤维化、log Calabi–Yau 指数界）需要只依赖维数与边界系数的一致倍数。此前 Fujino–Mori 用循环覆盖的中间 Betti 数控制分母，Todorov–Xu 处理了相对维数二的情形，Floris 处理一般纤维为有理曲线的情形并给出例子说明随纤维 Cartier 指数变化不可能有一致界。还有一个必须绕开的障碍：换一个有理线性等价的底除子代表元，会把模性部分改变一个主除子、引入任意大的分母——因此关键是选出合适的"精确拉回表示"。

## 主要结果

**定理（一致相对分母）**：固定有限集 `@@M@@\Phi\subset[0,1]\cap\mathbb Q@@` 与 `@@M@@1\le d\le4@@`。存在正整数 `@@M@@p_0\mid p@@`（`@@M@@p_0@@` 清除 `@@M@@\Phi@@`）与只依赖 `@@M@@d,\Phi@@` 的有理 DCC 集 `@@M@@\mathcal B@@`，使得：对每个系数在 `@@M@@\Phi@@` 中的射影 log canonical 对 `@@M@@(X,B)@@` 及收缩 `@@M@@f:X\to Z@@`（`@@M@@\dim Z>0@@`，`@@M@@K_X+B\sim_{\mathbb Q}f^*D@@`，`@@M@@D@@` 有理 Cartier），存在 `@@M@@\psi\in\mathbb C(X)^*@@` 与 `@@M@@D_Z\sim_{\mathbb Q}D@@`，使实际有理除子满足精确等式
`@@M@@DK_X+B+\tfrac1{p_0}\Div(\psi)=f^*D_Z,\qquad D_Z=K_Z+B_Z+M_Z，@@`
其中 `@@M@@B_Z\ge0@@` 系数在 `@@M@@\mathcal B@@` 中，`@@M@@(Z,B_Z+M_Z)@@` 是广义 lc 对 (generalized pair)（`@@M@@(X,B)@@` 为 klt 时为广义 klt），且模性 b-除子 `@@M@@\mathbf M@@` 是 b-nef 的、`@@M@@p\mathbf M@@` 为 b-Cartier。

**配套结果**：(1) 当 `@@M@@D@@` 大时，存在 `@@M@@m(d,\Phi)@@`，使每个倍数 `@@M@@l@@` 的完备取整系 `@@M@@|\lfloor l(K_X+B)\rfloor|@@`（秩一反射除子层）非空，且截面比恰生成 `@@M@@\mathbb C(Z)\subset\mathbb C(X)@@`，其有理映射双有理等价于 `@@M@@f@@` 与饭高纤维化；(2) 有理连通底上的一致挠界：存在 `@@M@@\ell(d,I,p)@@`，使 `@@M@@K_Z+B_Z+M_Z\sim_{\mathbb Q}0@@`、带 `@@M@@p\mathbf M@@` b-Cartier 数据的广义 klt 对满足 `@@M@@\ell(K_Z+B_Z+M_Z)@@` 是整主除子。特别地，系数有限的 klt 四维对若收缩到具有有理连通光滑分解的正维数底，则 `@@M@@r(\Phi)(K_X+B)@@` 为主除子，含 `@@M@@B=0@@`。

## 证明思路

证明分四步。先固定表示：几何一般纤维是维数至多三、伴随有理线性平凡的 lc 对，用低维指数定理（经域同构化为复数对）取公共平凡化次数 `@@M@@p_0@@`，再用 Hilbert 90 把平凡化函数在不扩大次数的前提下从 Galois 扩张下降回 `@@M@@\mathbb C(Z)@@`；阈值 ACC 给出判别系数的 DCC 集，定性典范丛公式（验证秩一条件）使 `@@M@@\mathbf M@@` b-nef 且在光滑决定模型 `@@M@@W@@` 上下降。由于 `@@M@@M_W@@` 的系数与 `@@M@@\alpha+t_P@@` 只差整数（`@@M@@\alpha@@` 为 `@@M@@D_Z@@` 拉回系数、`@@M@@t_P@@` 为阈值），目标化为对每个素除子证明 `@@M@@p(\alpha+t_P)\in\mathbb Z@@`。

再化到曲线上：取横截曲线切片，用逐次 Poincaré 留数配合避开标记点的线性等价代表元保持系数 `@@M@@\alpha@@`，在切片上跑相对 dlt 极小模型程序（四维翻转终止性由 Chen–Tsakanikas 的定理保证），负性引理证明误差项消失，得到 dlt 模型上的精确恒等式 `@@M@@p_0(K_N+T+H)+\Div(\psi_C)=p_0(\alpha+t)f_N^*[c]@@`，其中约化特殊纤维 `@@M@@T@@` 连通且 `@@M@@\dim T\le3@@`。

决定性一步是整条纤维上的留数比较：`@@M@@T@@` 是 demi-normal 的 slc（semi-log canonical）对，差分 (different) 系数落在固定 DCC 集；全局 ACC 把它压缩成有限集后，Jiang–Liu 关于三维以下 slc log Calabi–Yau 对的一致指数定理给出一致的偶倍数 `@@M@@p@@` 与处处非零的 log 多重典范生成元 `@@M@@u@@`。写 `@@M@@p_0(\alpha+t)=a/m@@`（既约），取底曲线的 `@@M@@m@@` 次根覆盖 `@@M@@w^m=z@@` 并正规化，得循环覆盖 `@@M@@\pi:Y\to N@@`；形式 `@@M@@s=(\pi^*\theta)^{\otimes p_0}\pi^*\psi\,w^{-a}@@` 生成 `@@M@@Y@@` 上的 `@@M@@p_0@@` 次 log 多重典范层、带特征 `@@M@@\zeta^{-a}@@`。在每个正规化覆盖分量上，留数与拉回生成元之商的比较表明它是常数；在分支交叉的节点处，偶次张量幂使相邻的下一层留数相等，于是连通性把所有常数粘成同一个标量。这样 `@@M@@s^{p/p_0}@@` 的留数组是不变量的标量倍，其特征必须平凡，即 `@@M@@m\mid p/p_0@@`、`@@M@@p(\alpha+t)\in\mathbb Z@@`，从而 `@@M@@pM_W@@` Cartier。

最后两个应用：有效系来自精确表示给出的截面空间恒等式 `@@M@@H^0(X,\OO_X(\lfloor l(K_X+B)\rfloor))=\psi^{l/p_0}f^*H^0(Z,\OO_Z(\lfloor lD_Z\rfloor))@@`（对反射层成立、不要求 Cartier），与 Birkar–Zhang 极化有效双有理性合并，公因子在比值中自动消去。挠命题则先经提取与全局 ACC 得有限系数集和一致 `@@M@@\varepsilon@@`-lc 奇异性，Birkar 有界性定理给出余维一同构意义下的有界族，半代数平凡性使 `@@M@@H_1(U(\mathbb C),\mathbb Z)@@` 只有有限多型，Kummer 理论 `@@M@@\mathrm{Cl}(Z)[n]\simeq\mathrm{Hom}(H_1(U(\mathbb C),\mathbb Z),\mu_n)@@` 给出一致的类群挠指数，再清除系数即得整主除子。

## 可信度与备注

本文暂无 Lean 形式化证明，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。它正是族内的四维先行稿（他文引用的 [R4]）：姊妹篇《Uniform Pluricanonical Iitaka Fibrations》把这里的相对分母方法推广到任意维数，用自身归纳与 Beauville–Bogomolov 块的退化替换了 Jiang–Liu 三维 slc 指数定理，而算术 Stein 度稿与 log 丰富性稿提供其余输入。维数至多四的限制正来自特殊纤维维数至多三时才可引用的指数定理与四维 MMP 终止性。

{% endraw %}
