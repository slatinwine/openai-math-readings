---
layout: default
title: "Elliptic squares and Zilber–Pink for curves in A2"
family: "016"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Elliptic squares and Zilber–Pink for curves in A2

> 结果族 016：Zilber–Pink in abelian varieties and the Siegel threefold　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

`@@M@@\mathcal A_2@@` 曲线情形的 Zilber–Pink 像一幅三块拼图：`@@M@@E\times@@`CM 分量、四元数分量，加上本文补上的第三块——"椭圆平方"点，即曲面恰是同一个普通椭圆曲线自乘 `@@M@@E^2@@` 的地方。本文独立攻克第三块，再把三块与处理特殊点的 André–Oort 定理拼装起来，让整个猜想在这个舞台上无条件收官。

**关键词卡片**

- 椭圆曲线平方 (`@@M@@E^2@@`)：同一椭圆曲线自乘得到的曲面；非 CM 指其因子没有超常自同态
- Hodge 一般 (Hodge generic)：不落在任何真特殊子簇里的曲线
- 正则迹判别式 (discriminant `@@M@@\Delta_s@@`)：自同构环复杂度的计量
- Galois 轨道下界 (Galois orbit lower bound)：`@@M@@[K(s):K]\ge c\,\Delta_s^{\delta}@@` 型不等式，有限性的发动机
- André–Oort 定理：模空间中特殊点稀疏性的定理，负责第四类例外

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 305">
  <text x="280" y="24" font-size="15" text-anchor="middle" fill="#333">三块拼图＋特殊点＝A₂ 曲线情形的完整 Zilber–Pink</text>
  <path d="M30 150 Q170 60 300 140 Q430 220 530 90" fill="none" stroke="#d33" stroke-width="2.5"/>
  <path d="M40 60 Q160 200 280 70" fill="none" stroke="#26b" stroke-width="2"/>
  <circle cx="105" cy="112" r="5" fill="#f0a"/>
  <path d="M330 200 Q400 150 470 175" fill="none" stroke="#2a7" stroke-width="2"/>
  <circle cx="400" cy="169" r="5" fill="#f0a"/>
  <path d="M430 90 Q470 170 535 130" fill="none" stroke="#e83" stroke-width="2"/>
  <circle cx="477" cy="141" r="5" fill="#f0a"/>
  <polygon points="221,100 227,107 221,114 215,107" fill="#85a"/>
  <polygon points="510,108 516,115 510,122 504,115" fill="#85a"/>
  <text x="280" y="262" font-size="12" text-anchor="middle" fill="#555">红＝一般曲线 C；蓝＝E×CM；绿＝QM；橙＝E²；紫菱形＝特殊点</text>
  <text x="280" y="286" font-size="13" text-anchor="middle" fill="#333">四类例外都有限 ⇒ C 与特殊点、特殊曲线之并只交有限点</text>
</svg>

</div>

判定代入数字：`@@M@@s@@` 属于 `@@M@@\Sigma_{E^2}(C)@@` 当且仅当 `@@M@@A_s@@` 同源于某个 `@@M@@E^2@@`（`@@M@@E@@` 无 CM），等价于 `@@M@@\mathrm{End}^0(A_s)\simeq M_2(\mathbb Q)@@`；同源不必保持极化，次数、阶、椭圆曲线本身都可任意变化，定理一概照收。拼装后的定理二断言：`@@M@@C(\overline{\mathbb Q})\cap\bigcup_{\dim Z\le 1}Z(\overline{\mathbb Q})@@` 是有限集——一条一般曲线与全部特殊点、特殊曲线的并，只交有限个点。

**为什么值得关心**

"不可能交点"纲领在经典舞台 `@@M@@\mathcal A_2@@` 的曲线情形就此完整落地：三篇姊妹工作互相咬合，不需要任何边界、退化或约化假设。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了 `@@M@@\mathcal A_2@@`（主极化阿贝尔曲面模空间）中任何 Hodge-通有代数曲线上，阿贝尔曲面同源于非 CM 椭圆曲线平方 `@@M@@E^2@@` 的点只有有限多个；与两篇姊妹篇合并，无条件解决了 `@@M@@\mathcal A_2@@` 中曲线情形的 Zilber–Pink 猜想。

## 问题背景

Zilber（2002）与 Pink（2005）提出的 Zilber–Pink 猜想是"非可能相交"（unlikely intersections）纲领的核心问题：模空间中的通有子簇不应与过多特殊子簇（special subvarieties，即 Shimura 特殊子簇）相遇。本文舞台 `@@M@@\mathcal A_2@@` 是主极化阿贝尔曲面（principally polarized abelian surface）的粗模空间，维数为三。曲线情形预测：一条 Hodge-通有（Hodge-generic，即不含于任何真特殊子簇）的曲线与所有维数至多一的特殊子簇之并只交有限多个点，且不固定同源次数（isogeny degree）与自同构阶。此前 Pila–Tsimerman 证明了 `@@M@@\mathcal A_2@@` 上的 André–Oort 定理，处理了特殊点情形；Daw 与 Orr 对三类特殊曲线发展了相应方法，但其无条件结果或要求曲线触及紧化边界，或要求乘法退化假设。真正的缺口在于：需要伽罗瓦轨道（Galois orbit）相对于自同构环判别式的多项式下界，且对整个椭圆平方轨迹一致成立。

## 主要结果

**定理一（椭圆平方情形）**：设 `@@M@@C\subset\mathcal A_2@@` 是 `@@M@@\overline{\mathbb Q}@@` 上非空不可约 Hodge-通有闭曲线，则
`@@M@@D\Sigma_{E^2}(C)=\{s\in C(\overline{\mathbb Q}):\ A_s\sim E^2,\ E\ \text{为非 CM 椭圆曲线}\}@@`
有限。这里 `@@M@@\sim@@` 表示 `@@M@@\overline{\mathbb Q}@@` 上的同源（isogeny），不要求保持主极化；条件等价于 `@@M@@\End_{\overline{\mathbb Q}}(A_s)\otimes_{\mathbb Z}\mathbb Q\simeq M_2(\mathbb Q)@@`。定理对紧化边界不设任何条件，椭圆曲线、同源次数与极化均可任意变化。

**定理二（完整 Zilber–Pink）**：结合姊妹篇的 `@@M@@E\times\mathrm{CM}@@` 有限性定理与四元数除法代数（indefinite quaternion division algebra）有限性定理，加上 Moonen–Zarhin 的特殊曲线分类与 André–Oort，可得 `@@M@@C(\overline{\mathbb Q})\cap\bigcup_{\dim Z\le 1}Z(\overline{\mathbb Q})@@` 有限。对非通有曲线还推出 Pink 特殊闭包（special closure）形式的推论：`@@M@@C@@` 与维数小于 `@@M@@\dim S_C-1@@` 的特殊子簇之并的交有限。

## 证明思路

整体是 Pila–Zannier 式"算术—几何"策略。先反设 `@@M@@\Sigma_{E^2}(C)@@` 无限。由 Daw–Orr 的条件蕴含定理，只要每点轨道满足 `@@M@@[K(s):K]\ge c\,\Delta_s^{\delta}@@`（`@@M@@\Delta_s@@` 为全自同构环 `@@M@@\End_{\overline{\mathbb Q}}(A_s)@@` 的正则迹判别式），有限性即得。于是核心是高度估计：固定精细水平覆盖上选取的提升 `@@M@@t@@` 满足 `@@M@@h(t)\le Cd^{\kappa}@@`（`@@M@@d=\max\{2,[K(t):K]\}@@`）；再配 Masser–Wüstholz 自同构估计 `@@M@@\Delta_s\le C(dh(t))^v@@`，合并即得轨道下界。

为此在无限轨迹中固定一个"中心"点 `@@M@@t_0@@`。在一阶同调上，迹零且关于极化自伴的算子构成五维二次空间 `@@M@@\mathcal P@@`，椭圆平方点的有理自同构在其中张成正平面。取中心与目标平面的标记对 `@@M@@\mathbf B,\mathbf P@@`，令 `@@M@@a=x(t)@@` 为中心处局部参数，`@@M@@Y(a)@@` 为固定 de Rham 标架下的水平输运，考察交叉配对 `@@M@@\langle\mathbf B,Y(a)\mathbf P\rangle@@`。当中心与目标纤维在某有限位有相同好约化（good reduction）时，有理的结晶比较（crystalline comparison）把这些配对等同于约化上真实自同构乘积的迹，Frobenius 又同时共轭两组数据，遂得方程 `@@M@@\langle\mathbf B,Y(a)\mathbf P\rangle=\langle\mathbf B',Y'(aR)\mathbf P'\rangle@@`（`@@M@@R=a'/a@@`，`@@M@@|R|_v=1@@`）——剩余特征数从方程中消失，按共轭数据组分组只产生关于 `@@M@@d@@` 多项式多个方程组。

两个辅助素水平 `@@M@@\ell_1,\ell_2@@` 使方程可用。强逼近定理（strong approximation）允许在同一连通覆盖上独立施加两级标记；`@@M@@\ell_1@@` 处要求中心与目标平面的模 `@@M@@\ell@@` 约化之和退化，`@@M@@\ell_2@@` 处要求非退化。后者排除中心处非潜在好约化的邻近目标：否则两平面将保持同一环面二维挠空间，与维数论证矛盾，故保留的位都适用好约化比较。前者排除恒等式：由 André 正规性定理，Hodge-通有族的单值群（monodromy group）是满特殊正交群，除非目标落在固定的有限 Hecke 对应列表上，方程不可能恒等；例外情形下固定乘子的极化同源把数据搬回，迫使公共标量为 `@@M@@\pm1@@`：正号使有理数平方等于 `@@M@@p/m_*@@`，`@@M@@p@@`-进赋值为奇数，矛盾；负号与 `@@M@@\ell_1@@` 处的退化性经 Tate 格正交分解相矛盾。

最后由插值定理把方程转化为高度控制：目标全局高度可达 `@@M@@h(t)@@` 量级，但选定位置上坐标的正局部对数仅 `@@M@@Cd^C(1+\log h)^C@@`，而中心除子的接近性质量达 `@@M@@h/(Cd^C)@@`。图构造 `@@M@@q=F/a^m@@` 把边界相交维数从 `@@M@@k-1@@` 压到 `@@M@@k-2@@`，使辅助多项式次数 `@@M@@L@@` 与消没阶 `@@M@@n=cL@@` 之比可任意大；乘积公式随即给出 `@@M@@h\le Cd^C@@`，否则目标被迫落入更小的代数子簇，至多 `@@M@@N@@` 步下降终止；非恒等性在每个代数分支成立是下降的前提。末节把高度估计降回粗模曲线，借极化分解 `@@M@@\psi_s=\psi_E\otimes b@@` 构造 Shimura 子数据，把 `@@M@@\Delta_s@@` 等同于 Daw–Orr 复杂度，应用其计数蕴含得定理一，再与三类型分类、André–Oort 及两篇姊妹篇拼装出完整定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准。它是结果族 016 的三篇姊妹工作之一：本文独立处理非 CM 椭圆平方轨迹，姊妹篇分别处理 `@@M@@E\times\mathrm{CM}@@` 轨迹与四元数除法轨迹，三条有限性定理合并后才构成 `@@M@@\mathcal A_2@@` 曲线情形的完整 Zilber–Pink；族内另有阿贝尔簇一般情形的工作互相支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题，读者应以同行评议与社区核验为准。

{% endraw %}
