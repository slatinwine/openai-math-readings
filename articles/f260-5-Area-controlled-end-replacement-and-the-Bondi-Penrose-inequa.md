---
layout: default
title: "Area-controlled end replacement and the Bondi Penrose inequality in the CKS class"
family: "260"
discipline: "Mathematical physics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Area-controlled end replacement and the Bondi Penrose inequality in the CKS class

> 结果族 260：Spacetime Penrose inequalities: enclosing area, charge, rotation, and anti-de Sitter extensions　·　学科：Mathematical physics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文把三维 Cha–Khuri–Sakovich（CKS）双曲端初值数据整体替换为渐平端：保持主能量条件、不动紧内部、最小包围面积几乎不损失，且新数据的 ADM 质量收敛于原数据的 Bondi 质量 `@@M@@m_B@@`，据此在该类数据上证得尖锐的 Bondi 型 Penrose 不等式。

## 问题背景

Penrose 于上世纪 70 年代由引力坍缩与黑洞面积定理提出：表观视界（apparent horizon）的面积应给初值数据的总质量立一个下界。时间对称情形已由 Huisken–Ilmanen 的弱逆平均曲率流（weak inverse mean curvature flow）与 Bray 的共形流（conformal flow）解决，但带一般第二基本形式（second fundamental form）的时空版本是公开难题。Cha–Khuri–Sakovich 转而考虑端点渐近双曲的数据（CKS 类），其无穷远守恒荷是类 Bondi 的 `@@M@@(E_B,P_B)@@` 而非 ADM 荷；他们把 sharp 不等式约化为广义 Jang 方程与弱逆平均曲率流的耦合系统，却只证明了 Jang 方程单独可解。本文绕开耦合系统：直接把双曲端"换掉"，转用渐平情形的姊妹篇定理。

## 主要结果

设 `@@M@@(\Omega,g,K)@@` 为三维完备外部区域，紧光滑边界 `@@M@@S@@` 非空、单端，端上两张量满足 CKS 渐近展式（如 `@@M@@a_{AB}=r^{-1}m^g_{AB}+O_3(r^{-2})@@`）、主能量条件（dominant energy condition）`@@M@@\mu\ge|J|_g@@` 与 `@@M@@E_B>|P_B|@@`；`@@M@@(E_B,P_B)@@` 是纯初值层面的显式泛函，无需时空发展。面积取**最小包围面积** `@@M@@A_{\min,g}(S)=\inf_\Gamma\operatorname{Area}(\Gamma)@@`：下确界跑遍所有包围割线（enclosing cut，即包含整个远端的连通区域的边界，可不连通、可与 `@@M@@S@@` 重合）；Ben-Dov 的反例表明不能改用视界自身的面积。

**定理（面积受控的端替换）**：存在 `@@M@@P_B=0@@` 的平衡坐标图，使对每个充分大的 `@@M@@R@@`，同流形上有光滑数据 `@@M@@(G_R,k_R)@@`：(i) `@@M@@r\le R@@` 处与原数据重合且满足 DEC；(ii) 全空间 `@@M@@G_R\ge(1-\varepsilon_R)g@@`，`@@M@@\varepsilon_R\to0@@`，特别地 `@@M@@A_{\min,G_R}(S)\ge(1-\varepsilon_R)A_{\min,g}(S)@@`；(iii) 端渐近平坦，远处 `@@M@@k_R=0@@`，且 `@@M@@P_R=0@@`、`@@M@@E_R=m_B+\eta_R@@`，`@@M@@0\le\eta_R\le 2R^{-1/2}@@`。

**推论（CKS 类的尖锐 Bondi 不等式）**：若边界还弱未来囚陷（`@@M@@\theta_+(S)\le0@@`，可不连通）且 `@@M@@A_{\min,g}(S)>0@@`，则
`@@M@@D\sqrt{E_B^2-|P_B|^2}\ \ge\ \sqrt{\frac{A_{\min,g}(S)}{16\pi}}.@@`
视界正则的 Schwarzschild 双曲外域对每个 `@@M@@m>0@@` 取等：`@@M@@A_{\min}=16\pi m^2@@`、`@@M@@m_B=m@@`。

## 证明思路

证明始于径向真空模型 `@@M@@G=u^{-2}dr^2+r^2\sigma@@`，`@@M@@u^2=1+v^2-2m/r@@`，`@@M@@k(N,N)=v'@@`，`@@M@@k_T=(v/r)r^2\sigma@@`：对**任意** `@@M@@v@@` 它都是真空数据，`@@M@@v=r@@` 给出双曲标度、`@@M@@v=0@@` 给出空间 Schwarzschild，故把切向张量迹 `@@M@@2v/r@@` 从 `@@M@@2@@` 降到 `@@M@@0@@` 不花任何质量。一般 CKS 数据的"质量"是角函数 `@@M@@F(r,\omega)@@`，其角导数在两个约束里各生出一项多余量：能量中的 `@@M@@\Delta_\sigma F@@` 与角动量中的 `@@M@@\mathrm d_\sigma F@@`。前者用球面热流消去（取 `@@M@@F=f(t(r),\omega)+c_R(r)@@`，`@@M@@\partial_tf=\Delta_\sigma f@@`），后者用无迹球面张量 `@@M@@\mathcal T@@`（`@@M@@\diver_\sigma\mathcal T=\mathrm d_\sigma f@@`）消去；这一除法恰有"一次谐波障碍"——`@@M@@f@@` 的一阶球谐必须为零，这正是开局先做洛伦兹平衡（boost 到 `@@M@@P_B=0@@`）的原因。

具体分三段。先在领圈 `@@M@@R\le r\le3R@@` 上把非球面叶磨圆：原 DEC 可能饱和，"改动小"不足以保 DEC，作者让约束向量 `@@M@@(C,Q,Z)@@` 的增量自身落入未来光锥——先激活缓增的质量垫层 `@@M@@c_R@@`（总量 `@@M@@\le2R^{-1/2}@@`），使两个零方向余量之积恰好压制角动量增量的平方。再在 `@@M@@r\ge3R@@` 上弯曲：热流在 `@@M@@v/r@@` 尚未变动时先开启，随后分两个径向尺度把 `@@M@@v@@` 从 `@@M@@r@@` 降到 `@@M@@0@@`，最终截断推迟到 `@@M@@r\sim R^2@@`，彼时 `@@M@@v@@` 已很小，避免对 `@@M@@1/v@@` 的奇异估计；精确系数使 `@@M@@\Delta_\sigma F@@` 与梯度项到领先阶相消，残余误差被垫层正余量 `@@M@@2r^{-7/2}@@` 吸收，DEC 全程成立。最后做转移：热流保均值给出 `@@M@@E_R=m_B+c_R(\infty)@@`，尾端 `@@M@@k_R=0@@` 给出 `@@M@@P_R=0@@`；逐点度量比较控制每个包围割的面积元，故 `@@M@@A_{\min}@@` 几乎不变。对每个固定的 `@@M@@R@@`，把姊妹篇的三维渐平时空 Penrose 定理用于替换后的数据，得 `@@M@@m_B+c_R(\infty)\ge\sqrt{(1-\varepsilon_R)A_{\min,g}(S)/16\pi}@@`；先令 `@@M@@r\to\infty@@` 取 ADM 极限、再令 `@@M@@R\to\infty@@`，两个余量同时消失。

取等例子在 `@@M@@\Omega=[2m,\infty)\times\mathbb S^2@@` 上：`@@M@@v@@` 近边界取 `@@M@@-1@@`、远端取 `@@M@@r@@`，数据是 Schwarzschild 时空的图形超曲面，光滑延伸到未来视界，`@@M@@\theta_+(S)=0@@`；坐标球障面 `@@M@@H=2u/r>|\tr k|@@` 排除内部任何取向的表观视界；径向投影不长增，故每个包围割面积 `@@M@@\ge16\pi m^2@@`。

## 可信度与备注

本文暂无 Lean 形式化证明，且 Bondi 不等式的最后一步显式依赖同族姊妹篇——三维渐平类时空 Penrose 定理——作为唯一数值输入；端替换的几何构造本身自足：本文把双曲端化归为渐平端，姊妹篇提供渐平端的不等式。按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。

{% endraw %}
