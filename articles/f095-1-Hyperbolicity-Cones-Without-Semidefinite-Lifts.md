---
layout: default
title: "Hyperbolicity Cones Without Semidefinite Lifts"
family: "095"
discipline: "Convex and metric geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Hyperbolicity Cones Without Semidefinite Lifts

> 结果族 095：Hyperbolicity cones without semidefinite lifts　·　学科：Convex and metric geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了存在没有任何有限半定提升的双曲锥（hyperbolicity cone）：无论引入多少辅助变量、使用什么实系数，它都不是谱面影子（spectrahedral shadow），从而同时否定 Projected Lax 猜想与广义 Lax 猜想。

## 问题背景

实齐次多项式 `@@M@@p@@` 若在某方向 `@@M@@e@@` 上使 `@@M@@t\mapsto p(te-x)@@` 对每个 `@@M@@x@@` 都只有实根，就称为双曲多项式（hyperbolic polynomial），其闭双曲锥 `@@M@@K(p,e)@@` 由"根全非负"的点组成；Gårding 在 1959 年证明它必是凸锥。对称矩阵空间上的行列式关于单位阵双曲，锥恰为半正定锥；Güler 又证明双曲锥自带对数自协和障碍（logarithmic self-concordant barrier），因而被视为超越半定规划（semidefinite programming）的天然可行域。谱面（spectrahedron）指有限仿射线性矩阵不等式 `@@M@@L(x)\succeq0@@` 的解集；谱面影子是谱面的线性投影，等价于允许辅助变量的半定提升（semidefinite lift）。广义 Lax 猜想断言每个双曲锥都是谱面；Netzer 与 Sanyal 在 2015 年提出较弱的 Projected Lax 猜想，只要求它是谱面影子。三变量情形由 Helton–Vinnikov 的行列式表示定理给出肯定答案；此后各类正面结果（初等对称族、边界光滑、Nash 光滑边界）都附加正则性假设，而 Brändén 构造的无行列式表示的多项式又不排除"换一个多项式定义同一个锥"。真正的卡点在于：如何排除允许任意多辅助变量、任意实系数的一切有限提升。

## 主要结果

主定理（Theorem 1.1）：存在实齐次双曲多项式，其闭双曲锥没有任何形如
`@@M@@DS=\Big\{x\in\R^d:\exists u\in\R^a,\ A_0+\sum_{i=1}^d x_iA_i+\sum_{j=1}^a u_jB_j\succeq0\Big\}@@`
的表示——矩阵尺寸与辅助变量个数任意有限、系数任意实数，且定义要求精确等式，不允许对投影取闭包。构造是高维存在性论证：输入空间维数 `@@M@@m=330@@`，矩阵块规模 `@@M@@r=20N-1@@`（可取 `@@M@@N>10\cdot 36^2@@`），而非对某个具体表示的尺寸下界。两个 Lax 猜想就此同告失败。

## 证明思路

先造锥。从一个处处半正定的二次矩阵映射 `@@M@@Q:\R^m\to\Sym_r@@` 出发，定义 `@@M@@p_Q(X,Z,y)=\det\big((\det X)Z-\Phi_y(\operatorname{adj}X)\big)@@`，其中 `@@M@@\Phi_y@@` 由 `@@M@@Q(y)@@` 的分块公式给出、`@@M@@\operatorname{adj}@@` 是经典伴随阵。固定 `@@M@@y@@` 做 Gram 分解 `@@M@@Q(y)=\sum_j b_jb_j^\top@@`，展开得到对称行列式恒等式 `@@M@@p_Q(te-(X,Z,y))=\det(tI-D_y(X,Z))@@`：根全是实对称矩阵的特征值，双曲性与锥的分块刻画一并到手。再取仿射截面 `@@M@@X=\diag(1,A)@@` 并投影，锥恰好映为 `@@M@@E_Q=\{(A,t,y):A\succeq0,\ \operatorname{ran}Q(y)\subseteq\operatorname{ran}A,\ t\ge\operatorname{tr}(A^\dagger Q(y))\}@@`，其中 `@@M@@A^\dagger@@` 是 Moore–Penrose 逆。仿射截面与坐标投影都保持提升的存在性，故只需证明 `@@M@@E_Q@@` 无提升。

再造障碍，难点是"`@@M@@Q@@` 处处半正定"与"`@@M@@E_Q@@` 有障碍"互相牵制，作者分两步绕开。第一步造有限性：令 `@@M@@H@@` 为八个变量的二次型空间（36 维），四次型上的线性泛函 `@@M@@y@@` 对应 Hankel 矩阵（Hankel matrix）`@@M@@Y(y)(f,g)=y(fg)@@`；借助附录里的有限域证书构造秩 20 的半正定"种子"矩阵 `@@M@@T@@`，其核满足强乘法条件。模掉平移与伸缩共八个参数后得到 185 维归一化流形，维数计数可选出子空间 `@@M@@K@@` 使归一化纤维有限，于是"压缩逆的极限方向"只剩有限多个射影类 `@@M@@\mathcal C@@`。第二步造分离：在 `@@M@@N@@` 份拷贝中用维数计数选出向量 `@@M@@w\in W^N@@` 与子空间 `@@M@@U\subset w^\perp@@`，再对任意逼近序列按"特征值发散／趋于有限非零极限／趋于零"分组做谱分析，证明 `@@M@@w@@` 不落在 Hankel 像 `@@M@@(I_N\otimes Y)u@@` 的闭包中。于是存在二次型 `@@M@@g@@` 在所有这些像上非负、而在 `@@M@@w@@` 处严格为负；定义 `@@M@@Q(y)=U^\top G(y)\,g\,G(y)U@@`，则对任意向量 `@@M@@a@@` 有 `@@M@@a^\top Q(y)a=(G(y)Ua)^\top g\,(G(y)Ua)\ge0@@`——处处半正定性免费获得，而 `@@M@@g@@` 的负方向正是预埋的障碍。

最后引爆障碍。赋值泛函给出 `@@M@@E_Q@@` 内一个次数至多四的多项式小块 `@@M@@x(s)@@`，迹不等式处处取等。再构造一个正定矩泛函（moment functional）`@@M@@\Lambda@@`——只要求其矩矩阵正定，完全不需要来自测度——作用在 `@@M@@x(c+\eps s)@@` 上：`@@M@@A@@` 坐标满足 `@@M@@A_{c,\eps}\succeq a_c\eps^4I@@`，而迹不等式被违反到 `@@M@@-\kappa_c\eps^4@@` 阶。反设存在有限提升：半代数分层与 Sard 定理提供解析的提升坐标与 Gram 因子（Gram factor）；把 `@@M@@\Lambda@@` 正延拓到 32 次，作用于 16 阶 Taylor 多项式后，pencil 值与半正定 Gram 值在 `@@M@@\eps^{16}@@` 阶内一致，再与一个最大秩可行点混合，即得距测试点仅 `@@M@@O(\eps^{16})@@` 的可行点。但 `@@M@@A\succeq\eps^4I@@` 使逆矩阵的扰动只有 `@@M@@O(\eps^8)@@`，远不足以消除 `@@M@@\eps^4@@` 阶的违反——矛盾。故 `@@M@@E_Q@@` 及整个 `@@M@@K_Q@@` 都没有有限半定提升。

## 可信度与备注

本文暂无形式化证明，按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。它与同族两篇姊妹稿互相支撑：九月底的显式反例（其主结果已 Lean 形式化）证明某个 23 变量双曲锥不是谱面，十月初的提升论文又证明该锥反而是谱面影子；只有本文的高维构造才真正切断"辅助变量"这条退路，否定 Projected Lax 猜想。技术路线上，本文与 Scheiderer 的局部平方和障碍方法一脉相承，但改用有限正矩泛函直接检验解析 Gram 恒等式，绕开了对表示测度的需求；种子矩阵的秩条件由附录中的有限域证书验证。

{% endraw %}
