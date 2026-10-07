---
layout: default
title: "An explicit failure of complex affine-space cancellation"
family: "047"
discipline: "Algebraic and complex geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | An explicit failure of complex affine-space cancellation

> 结果族 047：Zariski cancellation and affine fibrations over the complex numbers　·　学科：Algebraic and complex geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文在复数域上显式构造出四维仿射簇 `@@M@@X@@`：乘一条仿射线后 `@@M@@X\times\mathbb A^1\cong\mathbb A^5@@`，但 `@@M@@X\not\cong\mathbb A^4@@`。这否定了特征 `@@M@@0@@` 下维数 `@@M@@4@@` 的 Zariski 消去问题，顺带推翻稳定坐标猜想与 Dolgachev–Weisfeiler 仿射纤维化猜想。

## 问题背景

Zariski 消去问题（Zariski cancellation problem）问：若复代数 `@@M@@A@@` 添一个变量后成为多项式环，即 `@@M@@A[w]\simeq\mathbb C[x_1,\dots,x_{n+1}]@@`，能否"消去"这个变量得到 `@@M@@A\simeq\mathbb C[x_1,\dots,x_n]@@`？维数 `@@M@@1@@` 由 Abhyankar–Heinzer–Eakin 解决，复仿射平面的情形由 Fujita、Miyanishi、Sugie 完成。正特征下 Asanuma 给出候选例子、Gupta 证明维数 `@@M@@\ge3@@` 全部有反例；但特征 `@@M@@0@@`、维数 `@@M@@\ge3@@` 长期悬而未决——2026 年 7 月的 Gaifullin–Petrov 综述仍将其列为公开。它的困难在于：圆柱的同构不必保持到仿射线的投影，因此不能直接读出 `@@M@@A@@` 的坐标。本文给出 `@@M@@n=4@@` 的否定回答。

## 主要结果

设 `@@M@@P=\mathbb C[p,s,u,F,J]@@`，令 `@@M@@x=s^2+u^3+p^2F@@`，定义
`@@M@@DH=x^2F-(1+2sx)J-p^2J^2-pu,\qquad A=P/(H).@@`

**主定理**：`@@M@@A@@` 是四维整代数，`@@M@@A[w]\simeq\mathbb C[x_1,\dots,x_5]@@`，但 `@@M@@A\not\simeq\mathbb C[x_1,\dots,x_4]@@`。故复数上的消去问题在维数 `@@M@@4@@` 有反例。

**推论一（稳定坐标猜想失败）**：`@@M@@H@@` 不是 `@@M@@P@@` 的多项式坐标（coordinate），却是 `@@M@@P[w]@@` 的坐标——猜想断言"添一个变量后成为坐标则原本就是坐标"，在环境维数 `@@M@@5@@` 被否定。

**推论二（非平凡仿射纤维化）**：由 `@@M@@p@@` 给出的 `@@M@@\pi:\Spec A\to\mathbb A^1@@` 与 `@@M@@(p,H):\mathbb A^5\to\mathbb A^2@@` 都是光滑 `@@M@@\mathbb A^3@@`-纤维化（affine fibration），每条剩余域纤维同构于 `@@M@@\mathbb A^3@@`，却都不是 Zariski 局部平凡（Zariski-locally trivial）丛，从而否定 Dolgachev–Weisfeiler 猜想在相对维数 `@@M@@3@@` 的论断。

## 证明思路

证明分两大块：先证圆柱确实是多项式环，再证 `@@M@@A@@` 本身不是。

**圆柱的显式稳定化**。先在 `@@M@@p@@` 可逆的局部化中把 `@@M@@(x,y,z,u)@@` 取为坐标，此时 `@@M@@H=p^{-2}(xy-z(z+1))-pu@@` 关于 `@@M@@u@@` 线性，故 `@@M@@H@@` 是残差坐标（residual coordinate）。再构造局部幂零导出（locally nilpotent derivation）`@@M@@\Delta=-p^2\partial/\partial u@@`，它满足 `@@M@@\Delta H=p^3@@`；指数化 `@@M@@\exp(w\Delta)@@` 把方程 `@@M@@H=0@@` 换成 `@@M@@H+p^3w=0@@`。对 `@@M@@(F,J)@@` 做行列式为 `@@M@@1@@` 的线性变换后，新方程模 `@@M@@p^2@@` 是线性的，可写出模 `@@M@@p^3@@` 的多项式根 `@@M@@L_*@@`；借助恒等式 `@@M@@p^3e_0-(L-L_*)=(p^2Q_1(L)-1)(H(L)+p^3w)@@`，第五个坐标 `@@M@@e@@` 在未局部化的环中就有多项式代表元，最终 `@@M@@A[w]\cong\mathbb C[p,s,u,M,e]@@`，五个坐标全部显式。

**排除 `@@M@@A@@` 是多项式环**则分四步。先利用 `@@M@@p=0@@` 处的离散赋值定义赋值次数 `@@M@@\deg h=-\operatorname{ord}_p(h)@@`，精确算出相伴分次代数（associated graded algebra）`@@M@@G=\operatorname{gr}A=R[\tau,I/\tau^2]@@`，其中 `@@M@@R=\mathbb C[x,y,z,u]/(xy-z(z+1))@@` 是光滑四维二次曲面，`@@M@@G@@` 是其上的仿射修正（affine modification）。若 `@@M@@A\cong\mathbb C^4@@`，则由 `@@M@@\deg F=2@@` 知某坐标 `@@M@@q_r@@` 次数为正；对另一坐标求偏导得非零局部幂零导出，滤波传递到 `@@M@@G@@` 上给出非零齐次导出及一个正次数不变量。其次，通过 `@@M@@\mathrm{SL}_2@@` 的标准环面丛（行列式环 `@@M@@\tilde R=\mathbb C[a,d,b,c,u]/(ac-bd-1)@@`）把理想 `@@M@@I@@` 主化：`@@M@@I\tilde R=(v)@@`，`@@M@@v=a^3b-a^2u^3-d^2@@`，并证明光滑仿射基上的加法作用唯一提升为线丛（line bundle）上纤维线性的作用（关键工具是 Picard 群在添变量下的不变性与无非常数多项式单位），提升保持纤维权（fiber weight）与赋值次数。正次数不变量被 `@@M@@V=v/\tau^2@@` 整除迫使 `@@M@@V@@` 不变，于是在 `@@M@@\tilde R@@` 上得到纤维移位非正、且 `@@M@@E^2(v)=0@@` 的非零导出 `@@M@@E@@`。最后是刚性障碍：引入第三个辅助分次并取最高分量 `@@M@@E'@@`，则 `@@M@@(E')^2(d^2+a^2u^3)=0@@`，即轨道多项式 `@@M@@d(q)^2+a(q)^2u(q)^3@@` 次数至多 `@@M@@1@@`；用 Mason–Stothers 多项式 `@@M@@abc@@` 不等式（polynomial `@@M@@abc@@` inequality）加上 `@@M@@-u^3@@` 在原分式域中非平方（`@@M@@u@@`-进赋值为奇数 `@@M@@3@@`），迫使 `@@M@@E'@@` 固定 `@@M@@a,d,u@@`；再由行列式关系与一维导出引理得 `@@M@@E'(b)=ah@@`、`@@M@@E'(c)=dh@@` 且 `@@M@@h\in\mathbb C[a,d,u]@@`，但 `@@M@@h@@` 的纤维权为负，与 `@@M@@\mathbb C[a,d,u]@@` 中元素纤维权非负矛盾。故 `@@M@@A\not\cong\mathbb A^4@@`。

## 可信度与备注

主定理已通过 Lean 形式化（见任务引用的 `lean/docs/047.md`），其中明确说明形式化覆盖"`@@M@@A[w]\cong\mathbb C^5@@` 且 `@@M@@A\not\cong\mathbb C^4@@`"这一核心反例，但稳定坐标推论与线丛提升等后续结论不在形式化范围内，请以社区核验为准。本族目前仅此一篇手稿，论文内部各结果环环相扣：主定理的"非多项式性"正是两个推论的引擎——纤维化非平凡性最终都归结为 `@@M@@A\not\cong\mathbb C^4@@` 或 `@@M@@H@@` 非坐标。按 OpenAI 官方声明，未经形式化的结果可能有问题，形式化部分之外的推论宜谨慎引用。

{% endraw %}
