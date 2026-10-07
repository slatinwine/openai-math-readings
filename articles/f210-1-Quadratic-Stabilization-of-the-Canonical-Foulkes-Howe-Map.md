---
layout: default
title: "Quadratic stabilization of the canonical Foulkes--Howe map"
family: "210"
discipline: "Algebra"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Quadratic stabilization of the canonical Foulkes--Howe map

> 结果族 210：Foulkes' conjecture for sixth powers and quadratic stabilization　·　学科：Algebra　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明了典范 Foulkes–Howe 乘法映射 `@@M@@\Sym^b(\Sym^a V)\to\Sym^a(\Sym^b V)@@` 在 `@@M@@a\ge 2@@`、`@@M@@b\ge a(a-1)@@` 时必满射，给出首个与 `@@M@@\dim V@@` 无关的二次稳定化界，正面回答 Landsberg 的多项式界问题，并附带 `@@M@@b\ge a(a-1)@@` 时的 Foulkes 嵌入。

## 问题背景

利用平均同构 `@@M@@\Sym^a W\simeq(W^{\otimes a})^{\mathfrak S_a}@@`，把 `@@M@@\Sym^a V@@` 的元素看成 `@@M@@a@@` 行同次张量，则在张量代数的不变子环 `@@M@@R=\bigoplus_j R_j@@` 中，分量乘法诱导典范 Foulkes–Howe 映射 `@@M@@\mu_{a,b,V}:\Sym^b(\Sym^a V)\to\Sym^a(\Sym^b V)@@`。固定 `@@M@@a@@` 后问：从哪个 `@@M@@b_0@@` 起它恒为满射（surjective）？这就是稳定化（stabilization）问题。几何上，`@@M@@R_1@@` 生成的子代数 `@@M@@A@@` 恰是可分解 `@@M@@a@@`-形式（decomposable forms）的仿射 Chow 簇（affine Chow variety）的坐标环，`@@M@@R@@` 是其正规化（normalization），满射性即坐标环与正规化何时相等。Brion 在 1993 年证明了最终满射，其后给出的有效界依赖 `@@M@@\dim V@@`；Raicu–Sam–Weyman 的正则性估计也未直接给出商 `@@M@@R/A@@` 的最高非零次。Landsberg 的教科书以 Problem 7.19 的形式求一个多项式界。与本文同源的传播现象出现在 Ikenmeyer 对 McKay 传播定理的证明里：反方向的典范映射在 `@@M@@\dim V\ge b@@` 时由一个种子处的单射性传播到一切更大的 `@@M@@b@@`；本文则是围绕槽数的归纳，直接给出一个方向的一致满射范围。

## 主要结果

定理：对每个整数 `@@M@@a\ge 2@@`、每个 `@@M@@b\ge a(a-1)@@` 与每个有限维复向量空间 `@@M@@V@@`，`@@M@@\mu_{a,b,V}@@` 满射，等价地 `@@M@@A_b=R_b@@`。界完全由 `@@M@@a@@` 决定、与 `@@M@@\dim V@@` 无关；以 Landsberg 的记号即 `@@M@@d\ge n(n-1)@@`，且包括 `@@M@@w=n@@` 的临界情形。`@@M@@a=1@@` 时映射是恒等。论文不主张该界最优，也未确定最小稳定化次数。推论：同范围内存在 `@@M@@\GL(V)@@`-等变嵌入 `@@M@@\Sym^a(\Sym^b V)\hookrightarrow\Sym^b(\Sym^a V)@@`——满射在复数域上由完全可约性分裂，取核的不变补即得；取 `@@M@@a=6@@` 给出 `@@M@@b\ge 30@@` 的第六幂比较，正是姊妹篇的大范围输入。值得强调的是该构造只断言存在性，并不把嵌入等同于任何指定的典范映射。

## 证明思路

证明分三步：化满射为消失性、一条微分单射引理、对 `@@M@@a@@` 的归纳。先证零化子判据：`@@M@@\mu_{a,b,V}@@` 满射当且仅当每个对称 `@@M@@a@@`-线性型（symmetric `@@M@@a@@`-linear form）`@@M@@T@@` 若在一切"`@@M@@b@@` 个向量之积" `@@M@@P@@` 上对角取值 `@@M@@T(P,\ldots,P)=0@@` 则必 `@@M@@T=0@@`；这里用极化恒等式说明纯幂张成 `@@M@@\Sym^b V@@`。随后设 `@@M@@r=a-1@@`，`@@M@@m=b-r\ge r^2@@`，对 `@@M@@a@@` 归纳。第一步，二元形式（binary form）`@@M@@X^r+cY^r@@` 在复数上分裂为 `@@M@@r@@` 个线性因子，故 `@@M@@(x^r+ct^r)Q@@`（`@@M@@Q@@` 是 `@@M@@m@@` 个向量之积）总是 `@@M@@b@@` 个向量之积；把条件看成 `@@M@@c@@` 的多项式并取 `@@M@@c@@` 的系数，得 `@@M@@T(x^rQ,\ldots,x^rQ,t^rQ)=0@@`。第二步，用定向导数 `@@M@@D_{Y/U}=\sum_k Y_k\partial_{U_k}@@`（降 `@@M@@U@@`-度、升 `@@M@@Y@@`-度）逐个作用于 `@@M@@H_x=T(x^rQ,\ldots,x^rQ,t^b)@@`，把 `@@M@@Q@@` 的因子一个个塞进最后一槽，终点恰是已知为零的式子；关键引理用 Fischer（apolar）内积与 `@@M@@\mathfrak{sl}_2@@` 权串（weight strings）算出 `@@M@@\|Dh\|^2-\|Eh\|^2=(p-q)\|h\|^2@@`，故只要源度超过目标度，算子单射，于是可"约掉"导数得 `@@M@@H_x=0@@`，最后一槽被解放为独立的 `@@M@@t^b@@`。第三步先对槽数归纳：固定 `@@M@@x,t@@` 后 `@@M@@S_{x,t}(Q_1,\ldots,Q_r)=T(x^rQ_1,\ldots,x^rQ_r,t^b)@@` 是 `@@M@@\Sym^m V@@` 上的对称 `@@M@@r@@`-线性型，其对角在一切 `@@M@@m@@` 个向量之积上为零，而 `@@M@@m\ge r^2\ge r(r-1)@@`，归纳假设给出它恒为零。最后去掉公共因子 `@@M@@x^r@@`：对 `@@M@@f=T(v_1^b,\ldots,v_r^b,t^b)@@` 依次施加 `@@M@@r^2@@` 个算子 `@@M@@\D{x}{v_i}^{\,r}@@`，终点是已知为零的式子；这 `@@M@@r^2@@` 个算子都在抬高同一个变量块 `@@M@@x@@` 的次数（累计至多 `@@M@@r^2-1@@`），而每个源 `@@M@@v_i@@` 的次数至少 `@@M@@m+1\ge r^2+1@@`，度的不等式在每一步成立，单射性给出 `@@M@@f=0@@`。于是 `@@M@@T@@` 在纯幂上为零，极化后 `@@M@@T=0@@`。正是"`@@M@@x@@`-度的持续累积"迫使充分界达到二次的 `@@M@@b\ge a(a-1)@@`。整套论证只用正定的 Fischer 内积、二元形式在 `@@M@@\mathbb C@@` 上的分裂以及特征零的非零标量因子；微分引理对任意有限多坐标与任意附加变量成立，度的比较又只依赖 `@@M@@a@@` 与 `@@M@@b@@`，因此同一个界在每个有限维数上同时成立，完全不需要稳定维数归约。

## 可信度与备注

本篇主结果已 Lean 形式化。它与姊妹篇互相支撑：本文提供 `@@M@@b\ge a(a-1)@@` 的一致满射，姊妹篇用它覆盖第六情形的 `@@M@@b\ge 30@@`，并以图表加极化的独立路线给出 `@@M@@b\ge a(a-1)^2@@` 的替代界，两条路线互为备份。注意典范映射在 `@@M@@(5,5)@@`、`@@M@@(6,6)@@` 处可以有非零核，这些都在 `@@M@@b\ge a(a-1)@@` 范围之外，与定理并无冲突；按 OpenAI 官方声明，未经形式化的结果可能有问题，而本文不在此列。

{% endraw %}
