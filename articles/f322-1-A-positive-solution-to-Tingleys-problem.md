---
layout: default
title: "A positive solution to Tingley's problem"
family: "322"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A positive solution to Tingley's problem

> 结果族 322：Tingley's sphere-isometry problem　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文肯定地解决了 Tingley 问题：实 Banach 空间单位球面之间的满等距映射必可唯一扩张为全空间上的满实线性等距算子，且对维数、可分性、光滑性均无限制——单位球面的度量几何在线性等距意义下完全决定整个空间。

## 问题背景

对实赋范空间 `@@M@@X@@`，记单位球面（unit sphere）`@@M@@S_X=\{x:\norm{x}=1\}@@`，距离继承自 `@@M@@X@@`。1987 年 Tingley 提出：球面间的满等距映射（surjective isometry）`@@M@@f:S_X\to S_Y@@` 是否总能扩张（extension）为全空间之间的线性等距？经典工具在此失灵：Mazur–Ulam 定理（1932）只处理整个空间之间的满等距，Mankiewicz（1972）的推广要求凸集具有非空内部，而球面在所在空间中没有内部。Tingley 原文仅在有限维证明了对径点（antipodal points）被保持，即 `@@M@@f(-x)=-f(x)@@`。此后三十余年，`@@M@@\ell^p@@`、`@@M@@L^p@@` 等序列与函数空间，`@@M@@C^*@@`-代数、von Neumann 代数，以及二维空间等具体空间类相继获得肯定答案，但完全不设限制的一般情形始终悬而未决。

## 主要结果

主定理（main.tex，定理 1.1）：设 `@@M@@X,Y@@` 为非零实 Banach 空间，`@@M@@f:S_X\to S_Y@@` 是满等距映射，则径向映射
`@@M@@DT(0)=0,\qquad T(x)=\norm{x}\,f\Bigl(\frac{x}{\norm{x}}\Bigr)\quad(x\ne0)@@`
是 `@@M@@X@@` 到 `@@M@@Y@@` 的满实线性等距算子，且是 `@@M@@f@@` 唯一的线性扩张。候选映射 `@@M@@T@@` 天然保范、保同一半径上的距离，全部困难在于从单个球面的度量恢复不同半径的点之间的距离。空间可以是任意维数，不必可分、自反、光滑或严格凸；复 Banach 空间视为实空间时结论是实线性，不断言复线性。

## 证明思路

全文围绕亏损（defect）`@@M@@D_q(x,y)=\norm{f(x)-qf(y)}-\norm{x-qy}@@`（`@@M@@x,y\in S_X@@`，`@@M@@0\le q\le1@@`）及其上确界 `@@M@@M@@` 展开。因 `@@M@@f@@` 保范保距，`@@M@@D_0=D_1=0@@`，故 `@@M@@M\le1@@`；只要证明 `@@M@@M=0@@`，径向映射便保持全部距离、满且固定原点，再由 Mazur–Ulam 定理得仿射性、进而实线性。以下反设 `@@M@@M>0@@`。

先取到极大：以自由超滤子（free ultrafilter）构造 Banach 空间超幂（ultrapower），将 `@@M@@f@@` 逐项作用，得到一对可能放大的空间上仍以 `@@M@@M@@` 为亏损上界的球面满等距，且亏损在某处精确取等：存在 `@@M@@x_0,y\in S_X@@` 与 `@@M@@0<t<1@@` 使 `@@M@@\norm{f(x_0)-tf(y)}-\norm{x_0-ty}=M@@`。于是只需排除这个"极大已取到"的构型。

再对齐弦（chord）：固定 `@@M@@y,t@@`，记 `@@M@@b=f(y)@@`。从内点 `@@M@@ty@@` 沿方向 `@@M@@v@@` 交 `@@M@@S_X@@` 于 `@@M@@x=ty+pv@@`，其像记 `@@M@@f(x)=tb+sw@@`；再从 `@@M@@tb@@` 沿 `@@M@@-w@@` 交 `@@M@@S_Y@@` 于 `@@M@@f(z)=tb-uw@@`，把 `@@M@@z@@` 拉回并反向得返回映射 `@@M@@g(v)@@`。`@@M@@g@@` 的不动点恰好给出两条沿各自方向对齐的弦，满足 `@@M@@s-p=r-u=M@@`。为找不动点，令极值方向集 `@@M@@E=\{v\in S_X:s(v)-p(v)=M\}@@`，其核心传播规则是：凡与 `@@M@@g(v)@@` 共有支撑泛函（common support）的单位方向都落入 `@@M@@E@@`——支撑泛函由"范数等于权重之和"时的 Hahn–Banach 论证给出。据此归纳构造闭凸集 `@@M@@C=\clco\{v_0,v_1,\dots\}\subset E\subset S_X@@` 且 `@@M@@g(C)\subset C@@`，并证明 `@@M@@g@@` 严格压缩 Kuratowski 非紧性测度（measure of noncompactness）：`@@M@@\chi(g(H))\le\gamma\chi(H)@@`，`@@M@@\gamma=(1-M/(1+t))^2<1@@`；Darbo 不动点定理（Darbo's fixed-point theorem，附录中自 Sperner 引理完整证明）便给出不动方向。

最后弦矛盾：记 `@@M@@d=\norm{x-z}=p+r=s+u\le2@@`，`@@M@@A=p/d@@`，`@@M@@B=u/d@@`，`@@M@@\epsilon=1-t@@`，则 `@@M@@A+B=1-M/d<1@@`。割线（secant）估计把支撑泛函在 `@@M@@v@@` 处的值夹逼于 `@@M@@\epsilon/p@@` 与 `@@M@@1-B@@`（或 `@@M@@B@@`）之间。若 `@@M@@A>\epsilon@@` 或 `@@M@@B>\epsilon@@`，借助逆映射构型的对称性 `@@M@@(p',s',r',u')=(u,r,s,p)@@` 可推出：`@@M@@v@@` 处的支撑在 `@@M@@y@@` 上恒取负值、`@@M@@w@@` 处的支撑在 `@@M@@b@@` 上恒取正值，于是小径向扰动使 `@@M@@\norm{sw+\eta b}>s@@` 而 `@@M@@\norm{pv+\eta y}<p@@`，与亏损界 `@@M@@\le M=s-p@@` 矛盾。故只能 `@@M@@A,B\le\epsilon@@`，对原构型与逆构型分别用割线估计得 `@@M@@\epsilon\le dA(1-B)@@`、`@@M@@\epsilon\le dB(1-A)@@`；两乘积中较小者 `@@M@@<1/4@@`，迫使 `@@M@@\epsilon<1/2@@`。最后比较凸函数 `@@M@@F(\lambda)=\norm{y+\lambda v}@@` 与 `@@M@@G(\lambda)=\norm{b+\lambda w}@@` 的割线斜率：得 `@@M@@F(r/\epsilon)>1/t@@` 而 `@@M@@G(u/\epsilon)\le1/t@@`，但球面保距要求 `@@M@@\epsilon F(r/\epsilon)=\norm{y-z}=\norm{b-f(z)}=\epsilon G(u/\epsilon)@@`，矛盾。故 `@@M@@M=0@@`，中点反射论证（Mazur–Ulam 的简证形式）最终完成实线性与唯一性。

## 可信度与备注

据任务元信息，本篇主结果已有 Lean 形式化证明，族内附有对应文档（lean/docs/322.md）；从支撑泛函、超幂构造到 Darbo 不动点定理的完整证明链均写入正文与附录，可经机器核验。本篇是该结果族的核心：它不限定空间类别，此前 `@@M@@\ell^p@@`、`@@M@@L^p@@`、`@@M@@C^*@@`-代数、二维空间等肯定结论皆为其特例。仍请留意 OpenAI 官方声明：未经形式化的结果可能存在问题，核验请以形式化版本与社区审查为准。

{% endraw %}
