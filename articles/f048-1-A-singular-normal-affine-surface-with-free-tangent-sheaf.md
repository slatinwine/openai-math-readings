---
layout: default
title: "A singular normal affine surface with free tangent sheaf"
family: "048"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A singular normal affine surface with free tangent sheaf

> 结果族 048：A characteristic-zero counterexample to Lipman–Zariski　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文构造出一个带孤立奇点的正规仿射复曲面（二维），其切层 (tangent sheaf) 在整个曲面上自由、秩为 `@@M@@2@@`，而环不正则。这推翻了特征零下的 Lipman–Zariski 猜想——"切层局部自由的代数簇必光滑"。

## 问题背景

对有限生成的整 `@@M@@\mathbb C@@`-代数 `@@M@@A@@`，记 `@@M@@\Der_{\mathbb C}(A)=\Hom_A(\Omega^1_{A/\mathbb C},A)@@`，即 `@@M@@\Spec A@@` 上的代数向量场。光滑 `@@M@@d@@` 维簇的切层必局部自由、秩为 `@@M@@d@@`；Lipman–Zariski 猜想问其逆：切层局部自由的复代数簇是否必光滑。Lipman 在 1965 年证明切层自由已迫使簇正规 (normal)，于是缺口只剩"正规奇点能否出现"。正特征早有反例：曲面 `@@M@@xy-z^p=0@@` 的切层自由。特征零则有一长串正面结果——超曲面（Scheja–Storch）、局部完全交 (locally complete intersection，Källström)、klt 与 log canonical 奇点、`@@M@@p_g\le 1@@` 的曲面、对数 Kodaira 维数 `@@M@@\le 1@@` 的仿射曲面等——孤立奇点曲面成为公认的硬缺口。

## 主要结果

**定理.** 存在有限生成的正规整 `@@M@@\mathbb C@@`-代数 `@@M@@A@@`（Krull 维数 `@@M@@2@@`）及极大理想 `@@M@@\mathfrak m@@`，使得
`@@M@@D\Der_{\mathbb C}(A)\simeq A^{\oplus 2},\qquad A_{\mathfrak m}\ \text{非正则},@@`
且 `@@M@@\Spec A@@` 可取为除标记点外处处光滑。导数模自由（更是投射模）而环不正则，Lipman–Zariski 猜想在特征零不成立。奇点的解析不变量被算出：解析奇点 Gorenstein，例外曲线为亏格 `@@M@@21@@`、自交 `@@M@@-10@@` 的光滑曲线，典范差异 (discrepancy) 为 `@@M@@-5@@`，几何亏格 `@@M@@p_g\ge 33@@`，故 `@@M@@p_g-g-b\ge 12@@`，落在所有已知正面判据射程之外。附带两个推论：该曲面光滑轨迹的对数 Kodaira 维数 (log Kodaira dimension) 必为 `@@M@@2@@`；对 Barajas–Chávez-Martínez–Romano-Velázquez 的"沿导数模反复爆破能否消解奇点"问题给出否定回答——每次爆破（甚至再接正规化）都是恒等映射。

## 证明思路

整体先造解析奇点、再代数化。造奇点不走奇异锥路线（Hochster 定理已排除正分次的自由锥），而是保留法丛、改写零截面邻域的粘合映射：取光滑曲线 `@@M@@C@@` 与正线丛 `@@M@@L@@`，`@@M@@L^{\otimes4}\simeq K_C@@`、`@@M@@\deg L=10@@`，`@@M@@L^{-1}@@` 的全空间给出 `@@M@@C@@` 的邻域，其上有不变亚纯二形式 `@@M@@\sigma=t^{-5}\,dt\wedge dz@@`。目标是两个向量场 `@@M@@v_i=t(A_i\,t\partial_t+B_i\,\partial_z)@@` 使 `@@M@@\sigma(v_1,v_2)=1+O(t)@@`，即行列式恰沿 `@@M@@C@@` 消失五阶、别处不消失。难点在首项系数 `@@M@@r@@`（`@@M@@H^0(C,L)@@` 的基）有六个公共零点：既要逐点修正使行列式首项非零，修正又须满足全局留数约束才能把场粘合起来——点态与全局的相容性是全文枢纽。

先造曲线：在 `@@M@@\mathbb P^1\times\mathbb P^1@@` 上取双次数 `@@M@@(8,4)@@` 的光滑曲线（亏格 `@@M@@21@@`），使其与辅助椭圆曲线 `@@M@@\Gamma@@` 在六个标记点四阶相切。`@@M@@\Gamma@@` 上的二挠 (two-torsion) 结构给出二维二次空间中的六个向量（三个方向各用两次，`@@M@@w^2=90=9\deg L@@`），这组数值同时编码六个点态归一化与总留数；四阶相切则把截面维数与赋值映射的计算全部转移到椭圆曲线上。再用四次映射 `@@M@@f:C\to\mathbb P^1@@` 的迹配对 (trace form) 得二维商空间，经留数对偶与 `@@M@@\Gamma@@` 上的二次空间等距等同（标量与符号均显式固定），从而把六个向量搬回 `@@M@@C@@`，得到具指定单极点的亚纯对 `@@M@@P@@`，满足 `@@M@@p_j(0)\wedge R_j(0)=1@@` 与 `@@M@@\sum_j(W_j-1)=-9\deg L@@`。

再粘 jet：用有限个全纯流 `@@M@@t^k(b\,t\partial_t+h\,\partial_z)@@` 逐阶修改邻域粘合并装配场的泰勒系数。一阶由 `@@M@@P@@` 直接匹配；二阶垂直障碍分解为对称与反对称两部分——前者被 `@@M@@C@@` 上的留数定理消去（`@@M@@P_iP_j@@` 是 `@@M@@K_C@@` 的亚纯截面），后者恰被上述 `@@M@@-9\deg L@@` 恒等式抵消；三阶起先选定行列式目标系数、再解场方程，颠倒先后换来了消障碍的自由度，更高阶障碍因 `@@M@@H^1(C,L^{k+1})=0@@` 自动消失，终得模 `@@M@@\mathcal I^9\mathcal F@@` 的八阶相容 jet。

最后实现与收缩：有限过渡映射粘成 Hausdorff 邻域 `@@M@@Y@@`（`@@M@@C^2=-10@@`），Grauert 判据把 `@@M@@C@@` 收缩成正规曲面 `@@M@@X@@` 上的点 `@@M@@x@@`；分次消没 `@@M@@H^1(C,\mathcal F|_C\otimes L^n)=0@@`（`@@M@@n\ge 9@@`）配合形式函数定理把 jet 提升为真正的全纯场，绕开无穷逼近序列的收敛问题。这对场在 `@@M@@Y\setminus C\simeq X\setminus\{x\}@@` 上构成标架，二维正规性的 Hartogs 延拓把它们扩成 `@@M@@X@@` 的整体导数，得 `@@M@@\mathcal T_X\simeq\mathcal O_X^{\oplus2}@@`；而伴随公式 `@@M@@K_Y\cdot C=50@@` 排除 `@@M@@x@@` 光滑的可能。代数化一步不孤立地近似方程，而是连同关系矩阵一起近似并保持 `@@M@@gB=0@@` 精确成立，有限决定性保证完全局部环不变，忠实平坦下降把切自由性与正规性带回有限型 `@@M@@\mathbb C@@`-代数，收缩到单个仿射邻域即得定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；构造链条极长，其中二阶障碍的显式留数计算与"方程加关系矩阵"的代数化决定性引理是最值得社区复核的环节。本批任务中结果族 048 仅含此篇，族结论即本文主定理；文中还自查了反例不变量（`@@M@@p_g-g-b\ge 12@@`、差异 `@@M@@-5@@`）确实落在所有已知正面判据之外，与所引正面文献相容。按 OpenAI 官方声明："未经形式化的结果可能有问题"。

{% endraw %}
