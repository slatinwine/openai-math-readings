---
layout: default
title: "The equivariant cohomological Hikita conjecture for arbitrary quivers"
family: "044"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The equivariant cohomological Hikita conjecture for arbitrary quivers

> 结果族 044：The equivariant cohomological Hikita conjecture　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对任意有限箭图（含环与重边）、任意维数与框架向量、任意交换 flavor 环面与正则稳定特征，本文证明等变上同调 Hikita 猜想：Nakajima 簇的等变上同调代数与 Coulomb 分支余特征不动点概形的坐标环典范同构，保留分次与幂零元。

## 问题背景

辛对偶 (symplectic duality) 理论预言：一个辛解消 (symplectic resolution) 的上同调，应由其对偶簇上环面不动点的函数给出。Hikita 于 2017 年把它提炼为精确猜想，并对平面上点的 Hilbert 概形、A 型 Spaltenstein 簇与光滑超环面情形给出证明。微妙之处在于不动点集必须带概形结构 (scheme structure)：即使不动点很少，其幂零函数也能编码高次上同调，经典原型是 de Concini–Procesi 与 Tanisaki 对 Springer 纤维的描述。在箭图规范理论中，Higgs 侧是 Nakajima 簇，Coulomb 侧是 Braverman–Finkelberg–Nakajima (BFN) 卷积代数。此前最好的结果限于有限型箭图或 Gieseker（带框架 Jordan 箭图）情形；含环与重边的一般箭图上、与系数环相容的完全版本一直悬而未决。而且在箭图设定之外 Hikita 型等同存在反例，一般性并非自动成立。

## 主要结果

设 `@@M@@Q@@` 为任意有限箭图，允许环 (loop) 与重边 (multiple arrows)。取规范群 `@@M@@G=\prod_i\GL(V_i)@@`、与之交换的 flavor 环面 `@@M@@F@@`，以及正则稳定特征 `@@M@@\nu@@`（半稳定点皆稳定且 `@@M@@G@@` 自由作用）。Higgs 侧是 Nakajima 簇 `@@M@@X=\mu^{-1}(0)^{\nu\text{-stable}}/G@@`，允许为空；Coulomb 侧是 BFN 三元组空间的 flavor 形变卷积代数 `@@M@@A_F@@`，`@@M@@Y_{\mathfrak f}=\Spec A_F@@`，特征 `@@M@@\nu@@` 给出拓扑环面 `@@M@@T_{\mathrm{top}}@@` 的余特征，不动点坐标环为 `@@M@@\C[Y_{\mathfrak f}^{\nu}]=A_F/\langle(A_F)_m:m\ne0\rangle@@`。共同系数环 `@@M@@R=H^*_{G\times F}(\mathrm{pt};\C)@@`，两侧分别有 Kirwan 映射与 Coulomb 系数映射。主定理断言：两个系数映射都满射且核相同，从而有典范分次 `@@M@@R@@`-代数同构
`@@M@@DH_F^*(X;\C)\ \cong\ \C[Y_{\mathfrak f}^{\nu}].@@`
两个分次分别是上同调次数与 BFN 同调次数；商环不做约化、幂零元完整保留，空簇对应零环。

## 证明思路

整体采用"中间会师"策略：先证 `@@M@@B_F\cong H_F^*(X)@@`，其中 `@@M@@B_F@@` 是全拓扑环面 `@@M@@T_{\mathrm{top}}@@` 的不动商；再独立地证 `@@M@@\C[Y_{\mathfrak f}^{\nu}]\cong B_F@@`。两侧系数映射的满射性由两块已知输入保证：Weekes 的 minuscule 生成定理配合 BFN 阿贝尔化的显式 Laurent 公式给出 `@@M@@R\twoheadrightarrow B_F@@`，McGerty–Nevins 的 Kirwan 满射给出 `@@M@@R\twoheadrightarrow H_F^*(X)@@`，因此核心是比较两个核。

第一步证包含 `@@M@@I_{\mathrm{top}}\subseteq I_H@@`。把 `@@M@@B_F@@` 中的系数关系展开为"中性词"——总拓扑荷为零、长度为正的 minuscule 生成元乘积；先在有限维格链对应 (correspondence) 的 Borel–Moore 同调 (Borel–Moore homology) 中实现每个词，再做稳定对 (stable pair) 检验：稳定特征给每个修改一个加性次数，中性词经重排后首个非平凡修改的次数非正，被稳定性排除，于是该关系在上同调中湮灭，得到满射 `@@M@@B_F\twoheadrightarrow H_F^*(X)@@`。

第二步算尺寸。暂时在每个正维顶点加一个环并取行列式稳定性：环权重恰好抵消 Grassmann 分母，得到多项式系数的 Laurent 模型；以多重分拆 (multipartition) 过滤 `@@M@@B_0@@`，逐层商被切割理想 (cut ideal) 的不变量商控制；再用可达性分层与 Thom 递推计算其 Hilbert 级数 (Hilbert series)，并识别为 Hausel 的常 Poincaré 多项式。上界与满射夹逼出逐阶相等，得到同构。

第三步去掉所加的环。给新环以权一的辅助环面及质量参数 `@@M@@z@@`；在规范参数零点、`@@M@@z=1@@` 附近，新的 minuscule Euler 因子取值为一而可逆，故 Coulomb 侧局部化后与原代数一致；Higgs 侧用 Brion 子群局部化把 `@@M@@H@@` 不动拉回原稳定轨迹。局部理想相等后，用齐次性论证从分次原点处的等式恢复全局理想相等。再以超凯勒 (hyperkähler) 旋转与紧支撑 Betti 数关于中心矩参数仿射族的构造不变性，把结论从行列式特征推广到一切正则特征，最后经 Borel 谱列与 Leray–Hirsch 提升到任意 flavor。

第四步识别余特征不动商，难点是正则 `@@M@@\nu@@` 可与某个维数向量正交，全环面计算不够用。在扩大箭图上添加一个秩一框架顶点，利用互补 monopole 恒等式 `@@M@@M^+_{\mathbf b}=zM^-_{\mathbf d-\mathbf b}@@`：若某非平凡 monopole 在余特征不动商中幸存，其互补者也幸存；多项式形式的 Hall 代数 (Hall algebra) 生成（基于 Jindal–Negut 与 Tsymbaliuk 的差分算子，文中还修正了乘法符号约定）把两侧荷分解为权重零的不可分解荷，其支撑由 Kac 多项式 (Kac polynomial) 给出，每个这样的荷经 Crawley–Boevey 迹零化引理与 Kempf–Ness 对应、四元数旋转实现为矩映射层块，其半稳定直和的稳定化子在去掉无效对角标量后仍是正维，与正则性中的自由性矛盾。故两个理想一致。四步合并即得定理。

## 可信度与备注

本手稿出自 OpenAI 数学研究工作流，主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。证明结构完整，外围输入（BFN 卷积代数、Weekes 生成定理、McGerty–Nevins Kirwan 满射、Hausel 公式、Hall 代数与差分算子理论）均引自已发表文献，且文中自含关键符号修正。该结果族本批仅此一篇，它把 Krylov–Shlykov 的 Gieseker 情形与 Dumanski–Krylov 的一般表述推进到任意箭图，是目前最一般的上同调版本。

{% endraw %}
