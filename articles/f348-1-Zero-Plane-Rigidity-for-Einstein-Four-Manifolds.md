---
layout: default
title: "Zero-Plane Rigidity for Einstein Four-Manifolds"
family: "348"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Zero-Plane Rigidity for Einstein Four-Manifolds

> 结果族 348：Nonnegative-curvature Einstein classification and an L² topological gap　·　学科：微分几何（Differential geometry）　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
证明零平面刚性定理：闭 Einstein 四维流形若具非负截面曲率且存在一个零曲率平面，其通用黎曼覆盖必等距于等半径球面乘积 `@@M@@S^2(1/\sqrt3)\times S^2(1/\sqrt3)@@`；由此补全非负截面曲率 Einstein 四维流形的完整三分类。

## 问题背景
Einstein 度量（Einstein metric）满足 `@@M@@\operatorname{Ric}=\lambda g@@`：在四维它固定了截面曲率（sectional curvature）的总和，却留下两个独立的 Weyl 曲率块（Weyl curvature blocks）自由摆动。两个等半径球面的乘积恰好展示边界现象：切于因子的平面曲率为正，横跨两因子的平面曲率为零。悬案在于：非负截面曲率下，这种乘积几何何时被强制出现？此前成果都带附加条件——Berger 的严格四分之一钳制（pinching）、Gursky–LeBrun 的非零正定交形式（intersection form）、Cheng 的 `@@M@@\chi\le3@@`、Gursky–Malchiodi 的 `@@M@@2\chi-3|\tau|\le4@@`、Liu 的 `@@M@@T^2@@`-对称性假设等。本文把假设减到最少：只在一点存在一个零曲率平面。

## 主要结果
主定理（零平面刚性）：设 `@@M@@(M^4,g)@@` 连通、闭、`@@M@@\operatorname{Ric}=3g@@` 且所有截面曲率非负。若某切二维平面 `@@M@@\sigma_0@@` 满足 `@@M@@K_g(\sigma_0)=0@@`，则通用黎曼覆盖（universal Riemannian cover）等距于 `@@M@@S^2(1/\sqrt3)\times S^2(1/\sqrt3)@@`，且覆盖的切丛是两个平行秩二子丛的正交和。推论（非负分类）：此类流形的通用覆盖只能是曲率 `@@M@@1@@` 的圆球 `@@M@@S^4@@`、Fubini–Study 度量的 `@@M@@\mathbb{CP}^2@@`（归一 `@@M@@\operatorname{Ric}=3g@@`），或上述球面乘积。全程无需定向、对称或拓扑假设；一般 `@@M@@\operatorname{Ric}=\lambda g@@`（`@@M@@\lambda>0@@`）情形两球半径均为 `@@M@@1/\sqrt\lambda@@`。

## 证明思路
先做约化：Bonnet–Myers 定理使通用覆盖紧致、单连通、可定向；曲率算子在 Hodge 星特征丛 `@@M@@\Lambda^\pm@@` 上呈 `@@M@@\operatorname{Id}+T@@`、`@@M@@\operatorname{Id}+U@@`，最小截面曲率为 `@@M@@1-(x+y)/2@@`（`@@M@@x,y@@` 是两块最小特征值的相反数），故零平面等价于走到截面曲率锥的闭边界 `@@M@@x+y=2@@`。若某块恒为零，度量半共形平坦（half-conformally flat），Hitchin 与 Obata 的经典分类给出 `@@M@@S^4@@` 或 `@@M@@\mathbb{CP}^2@@`，截面严格为正，与零平面矛盾；以下设两块均不恒为零。第一步证矩平衡：Gursky–LeBrun 的 Weyl 间隙给 `@@M@@\mathbf E v^2,\mathbf E b^2\ge1@@`；Euler 示性数与号差（signature）公式把它们和体积线性联系；上体积亏损 `@@M@@V_M\le(8\pi^2/3)(1-\tfrac{3}{40}s_0)@@`——由直径 `@@M@@\pi@@` 上界、只积分到首个共轭点之前的极坐标上界、离散 Jacobi 行列式的矩阵比较与有理多项式证书支撑——联合整数约束后仅剩 `@@M@@(\chi,|\tau|)=(5,1)@@` 一格，再用 Bochner 型加权方差不等式与一个约束矩的凸对偶引理将其排除，得 `@@M@@\tau=0@@`、`@@M@@\mathbf E v^2=\mathbf E b^2@@`。第二步构造耦合不等式：微分 Bianchi 恒等式把 `@@M@@\nabla T@@` 锁进不可约子丛，其 Hessian 分解为自由分量 `@@M@@Y@@` 与完全确定的迹分量；曲率加权算子 `@@M@@\mathcal P@@` 在 `@@M@@Y@@` 上有 `@@M@@\mathcal P\ge(4-2x-2y)\operatorname{Id}\ge0@@`——在边界退化为半正定，正是推广的难点。对两块取斜率相反的权配平方并分部积分，把二阶导数全部降为一阶，再叠加三项修正（`@@M@@\Delta\delta@@` 恒等式、平衡方差亏差、乘子 `@@M@@\kappa@@` 的范数测试），得到被积函数 `@@M@@\mathcal I@@`：均值非负，逐点却被 `@@M@@\mathcal I\le-(\Theta-cr)^2/c-c(j-r^2)@@` 压制。决定性的严格性来自"Lipschitz 函数在其水平集上梯度几乎处处为零"，它无需截面严格正性；块零点则以微扰谱 `@@M@@T_\varepsilon=\operatorname{diag}(-\varepsilon,-\varepsilon,2\varepsilon)@@`、`@@M@@U_\varepsilon=(1-\varepsilon)U@@` 保持导数数据后取极限过渡。第三步取等：积分迫使 `@@M@@dv=db=0@@`，故 `@@M@@v,b@@` 为常数，间隙加 `@@M@@v+b\le2@@` 给 `@@M@@v=b=1@@`；弱范数方程随即给 `@@M@@\nabla T=\nabla U=0@@`、谱 `@@M@@(2,-1,-1)@@`。简单特征线生成两个平行正交复结构，其乘积是迹零的平行对合，切丛分裂为两个平行秩二分布；由 de Rham 分解定理，流形是两个曲率 `@@M@@3@@` 的完备曲面之积，即半径 `@@M@@1/\sqrt3@@` 的球面乘积。

## 可信度与备注
本文与姊妹篇《Positively curved Einstein four-manifolds》共享同一套耦合 Weyl 估计：后者先证严格正截面曲率情形，本文将所有不等式推到截面曲率锥的闭边界（体积估计不越过共轭点、二次型允许退化、零点用微扰过渡），第三篇 `@@M@@L^2@@` 间隙论文又以本文推论为分类前提，三篇互相咬合成链。附录给出全部多项式符号的有理系数证书，可机械复核；但整体尚无 Lean 形式化证明。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
