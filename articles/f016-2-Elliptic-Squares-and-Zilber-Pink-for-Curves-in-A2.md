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

## 一句话结论

证明了 \(\mathcal A_2\)（主极化阿贝尔曲面模空间）中任何 Hodge-通有代数曲线上，阿贝尔曲面同源于非 CM 椭圆曲线平方 \(E^2\) 的点只有有限多个；与两篇姊妹篇合并，无条件解决了 \(\mathcal A_2\) 中曲线情形的 Zilber–Pink 猜想。

## 问题背景

Zilber（2002）与 Pink（2005）提出的 Zilber–Pink 猜想是"非可能相交"（unlikely intersections）纲领的核心问题：模空间中的通有子簇不应与过多特殊子簇（special subvarieties，即 Shimura 特殊子簇）相遇。本文舞台 \(\mathcal A_2\) 是主极化阿贝尔曲面（principally polarized abelian surface）的粗模空间，维数为三。曲线情形预测：一条 Hodge-通有（Hodge-generic，即不含于任何真特殊子簇）的曲线与所有维数至多一的特殊子簇之并只交有限多个点，且不固定同源次数（isogeny degree）与自同构阶。此前 Pila–Tsimerman 证明了 \(\mathcal A_2\) 上的 André–Oort 定理，处理了特殊点情形；Daw 与 Orr 对三类特殊曲线发展了相应方法，但其无条件结果或要求曲线触及紧化边界，或要求乘法退化假设。真正的缺口在于：需要伽罗瓦轨道（Galois orbit）相对于自同构环判别式的多项式下界，且对整个椭圆平方轨迹一致成立。

## 主要结果

**定理一（椭圆平方情形）**：设 \(C\subset\mathcal A_2\) 是 \(\overline{\mathbb Q}\) 上非空不可约 Hodge-通有闭曲线，则
\[\Sigma_{E^2}(C)=\{s\in C(\overline{\mathbb Q}):\ A_s\sim E^2,\ E\ \text{为非 CM 椭圆曲线}\}\]
有限。这里 \(\sim\) 表示 \(\overline{\mathbb Q}\) 上的同源（isogeny），不要求保持主极化；条件等价于 \(\End_{\overline{\mathbb Q}}(A_s)\otimes_{\mathbb Z}\mathbb Q\simeq M_2(\mathbb Q)\)。定理对紧化边界不设任何条件，椭圆曲线、同源次数与极化均可任意变化。

**定理二（完整 Zilber–Pink）**：结合姊妹篇的 \(E\times\mathrm{CM}\) 有限性定理与四元数除法代数（indefinite quaternion division algebra）有限性定理，加上 Moonen–Zarhin 的特殊曲线分类与 André–Oort，可得 \(C(\overline{\mathbb Q})\cap\bigcup_{\dim Z\le 1}Z(\overline{\mathbb Q})\) 有限。对非通有曲线还推出 Pink 特殊闭包（special closure）形式的推论：\(C\) 与维数小于 \(\dim S_C-1\) 的特殊子簇之并的交有限。

## 证明思路

整体是 Pila–Zannier 式"算术—几何"策略。先反设 \(\Sigma_{E^2}(C)\) 无限。由 Daw–Orr 的条件蕴含定理，只要每点轨道满足 \([K(s):K]\ge c\,\Delta_s^{\delta}\)（\(\Delta_s\) 为全自同构环 \(\End_{\overline{\mathbb Q}}(A_s)\) 的正则迹判别式），有限性即得。于是核心是高度估计：固定精细水平覆盖上选取的提升 \(t\) 满足 \(h(t)\le Cd^{\kappa}\)（\(d=\max\{2,[K(t):K]\}\)）；再配 Masser–Wüstholz 自同构估计 \(\Delta_s\le C(dh(t))^v\)，合并即得轨道下界。

为此在无限轨迹中固定一个"中心"点 \(t_0\)。在一阶同调上，迹零且关于极化自伴的算子构成五维二次空间 \(\mathcal P\)，椭圆平方点的有理自同构在其中张成正平面。取中心与目标平面的标记对 \(\mathbf B,\mathbf P\)，令 \(a=x(t)\) 为中心处局部参数，\(Y(a)\) 为固定 de Rham 标架下的水平输运，考察交叉配对 \(\langle\mathbf B,Y(a)\mathbf P\rangle\)。当中心与目标纤维在某有限位有相同好约化（good reduction）时，有理的结晶比较（crystalline comparison）把这些配对等同于约化上真实自同构乘积的迹，Frobenius 又同时共轭两组数据，遂得方程 \(\langle\mathbf B,Y(a)\mathbf P\rangle=\langle\mathbf B',Y'(aR)\mathbf P'\rangle\)（\(R=a'/a\)，\(|R|_v=1\)）——剩余特征数从方程中消失，按共轭数据组分组只产生关于 \(d\) 多项式多个方程组。

两个辅助素水平 \(\ell_1,\ell_2\) 使方程可用。强逼近定理（strong approximation）允许在同一连通覆盖上独立施加两级标记；\(\ell_1\) 处要求中心与目标平面的模 \(\ell\) 约化之和退化，\(\ell_2\) 处要求非退化。后者排除中心处非潜在好约化的邻近目标：否则两平面将保持同一环面二维挠空间，与维数论证矛盾，故保留的位都适用好约化比较。前者排除恒等式：由 André 正规性定理，Hodge-通有族的单值群（monodromy group）是满特殊正交群，除非目标落在固定的有限 Hecke 对应列表上，方程不可能恒等；例外情形下固定乘子的极化同源把数据搬回，迫使公共标量为 \(\pm1\)：正号使有理数平方等于 \(p/m_*\)，\(p\)-进赋值为奇数，矛盾；负号与 \(\ell_1\) 处的退化性经 Tate 格正交分解相矛盾。

最后由插值定理把方程转化为高度控制：目标全局高度可达 \(h(t)\) 量级，但选定位置上坐标的正局部对数仅 \(Cd^C(1+\log h)^C\)，而中心除子的接近性质量达 \(h/(Cd^C)\)。图构造 \(q=F/a^m\) 把边界相交维数从 \(k-1\) 压到 \(k-2\)，使辅助多项式次数 \(L\) 与消没阶 \(n=cL\) 之比可任意大；乘积公式随即给出 \(h\le Cd^C\)，否则目标被迫落入更小的代数子簇，至多 \(N\) 步下降终止；非恒等性在每个代数分支成立是下降的前提。末节把高度估计降回粗模曲线，借极化分解 \(\psi_s=\psi_E\otimes b\) 构造 Shimura 子数据，把 \(\Delta_s\) 等同于 Daw–Orr 复杂度，应用其计数蕴含得定理一，再与三类型分类、André–Oort 及两篇姊妹篇拼装出完整定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准。它是结果族 016 的三篇姊妹工作之一：本文独立处理非 CM 椭圆平方轨迹，姊妹篇分别处理 \(E\times\mathrm{CM}\) 轨迹与四元数除法轨迹，三条有限性定理合并后才构成 \(\mathcal A_2\) 曲线情形的完整 Zilber–Pink；族内另有阿贝尔簇一般情形的工作互相支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题，读者应以同行评议与社区核验为准。

{% endraw %}
