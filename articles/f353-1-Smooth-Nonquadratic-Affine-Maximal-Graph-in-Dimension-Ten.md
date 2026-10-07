---
layout: default
title: "A Smooth Nonquadratic Entire Affine Maximal Graph in Dimension Ten"
family: "353"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Smooth Nonquadratic Entire Affine Maximal Graph in Dimension Ten

> 结果族 353：Affine Bernstein rigidity through dimension nine and a smooth dimension-ten counterexample　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
论文在十维构造了一个光滑、整定义于 `@@M@@\R^{10}@@`、Hessian 逐点正定且满足经典仿射极值方程 (affine maximal equation) 的非二次函数，推翻"整图仿射 Bernstein 断言"在十维的成立，与姊妹篇一起把刚性成立的范围精确卡在三至九维。

## 问题背景
仿射极值方程是仿射面积泛函 `@@M@@\int(\det D^2u)^{1/(n+2)}@@` 的欧拉—拉格朗日方程，刻画"仿射极大小体积"的凸图。Chern 于 1979 年提出二维整图问题：整定义、局部一致凸 (locally uniformly convex) 的仿射极值图是否必为椭圆抛物面 (elliptic paraboloid)？Trudinger 与 Wang 证明了二维刚性，并在同一篇 2000 年工作中给出十维奇异反例 `@@M@@u_0=\sqrt{|x|^9+t^2}@@`——但它在原点不光滑、Hessian 也不处处正定，只是弱解。光滑反例是否存在一直悬而未决：姊妹篇证明三至九维刚性成立，本篇则补上十维的光滑否定，使这条界线分毫不差。

## 主要结果
主定理：存在非二次函数 `@@M@@u\in C^\infty(\R^{10})@@`，`@@M@@D^2u@@` 在每一点都正定，且在整个 `@@M@@\R^{10}@@` 上满足
`@@M@@D\sum_{i,j=1}^{10}U^{ij}\partial_{ij}(\det D^2u)^{-11/12}=0,\qquad U=\det(D^2u)(D^2u)^{-1}.@@`
需要强调：这里的正定是逐点意义，不含一致下界；论文也不断言 Berwald–Blaschke 度量 (affine metric) 的完备性。因此它否定的是无完备性假设的"整图断言"，与姊妹篇的欧氏完备定理并不冲突，也不违背 Trudinger–Wang 原文中带全局截面凸性假设的结论。

## 证明思路
构造沿用奇异反例的代数关系 `@@M@@u^2-t^2=F(x)^2@@`，但把非光滑的 `@@M@@F=|x|^{9/2}@@` 换成待定的光滑严格凸径向函数，取 `@@M@@F(0)=1@@`。先做维数无关的归约（命题 2.1）：若正的光滑函数 `@@M@@F,P@@` 满足 `@@M@@\det D_x^2F=FP^{-\gamma}@@` 与 `@@M@@\tr((D_x^2F)^{-1}D_x^2P)+kP/F=0@@`（`@@M@@m=9@@` 时 `@@M@@\gamma=12/11@@`、`@@M@@k=11@@`），则 `@@M@@u=\sqrt{F^2+t^2}@@` 在 `@@M@@\R^{10}@@` 上自动有正定 Hessian 并解方程。四阶方程由此降为两个一元函数的二阶方程，再径向化成四个一阶常微分方程；其中第二条写成散度形式 `@@M@@(y^{m-1}P')'=-kr^{m-1}P^{1-\gamma}@@`，正是这一形式让解得以从奇异点 `@@M@@r=0@@` 启动。其次处理原点奇性：径向方程含除以 `@@M@@y=F'@@`，在 `@@M@@r=0@@` 退化；作者改用 `@@M@@s=r^2/2@@` 的积分形式，在连续函数对的闭集上验证一致 Lipschitz 与压缩性，由压缩映射定理 (contraction mapping principle) 得到原点附近的光滑解，`@@M@@D_x^2F(0)=I@@`、`@@M@@D_x^2P(0)=-\frac{11}{9}I@@`，且因剖面是 `@@M@@|x|^2/2@@` 的函数，关于 `@@M@@x@@` 自动光滑；不动点还顺带给出近端 `@@M@@y,y'>0@@`、`@@M@@P'<0@@`，凸性与单调性从原点起即成立。最大的障碍是整体存在性：辅助函数 `@@M@@P@@` 原则上可能在有限半径处归零。作者不分别估计 `@@M@@F,P@@`，而控制对数导数 (logarithmic derivatives) `@@M@@A=ry/F@@`、`@@M@@B=ry'/y@@`、`@@M@@D=C/B@@`（`@@M@@C=-rP'/P@@`），它们满足以 `@@M@@\log r@@` 为时间的三维自治系统。奇异解的常数 `@@M@@(9/2,\,7/2,\,33/7)@@` 张出一个长方体；关键的一步是改用这组导数变量后，向量场在盒内成为合作系统 (cooperative system)——每个分量对另外两个变量单调不减——而盒子角点恰为驻点 (stationary point)，于是所有上界面被这一个角点统一压制，配合 Gronwall 论证得到盒子前向不变 (forward invariant)。由此 `@@M@@F,P,y,y'@@` 被夹在幂函数界之间：若解的最大存在半径 `@@M@@R<\infty@@`，则状态 `@@M@@(r,F,P,y,P')@@` 停留在正则域 `@@M@@r,F,P,y>0@@` 的一个紧子集内，右端有界、极限存在，局部存在唯一性便把解越过 `@@M@@R@@` 延拓，矛盾，故解延拓到任意 `@@M@@r>0@@`。最后 `@@M@@u(x,t)=\sqrt{F(|x|)^2+t^2}@@` 光滑、Hessian 处处正定、解方程，而 `@@M@@u(0,t)=\sqrt{1+t^2}@@` 保证它不是二次多项式。

## 可信度与备注
本篇未形式化，请以社区核验为准。它与姊妹篇互为印证：三至九维刚性证明中强制性二次型的行列式为 `@@M@@(n-2)(10-n)/16@@`，恰在 `@@M@@n=10@@` 退化为零——方法失效之处正是反例所在，说明"三至九"这一范围在当前技术下已无法改进。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
