---
layout: default
title: "A strict inverse-first-power bound for univalent functions"
family: "072"
discipline: "Real and complex analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A strict inverse-first-power bound for univalent functions

> 结果族 072：Brennan's conjecture and the integral-means spectrum　·　学科：Real and complex analysis　·　验证状态：主结果已 Lean 形式化

## 一句话结论

证明对所有标准化单叶函数一致成立的估计 `@@M@@M_{-1}[f'](r)\le C(1-r)^{-1/4+\varepsilon}@@`，从而有界单叶类的普适积分均值谱满足 `@@M@@B_b(-1)<1/4@@`，推翻了 Kraetzer 谱猜想在 `@@M@@p=-1@@` 处的预测值。

## 问题背景

单叶（univalent，即单射全纯）函数的导数即使在图像有界时也能在边界附近剧烈集中，积分均值谱（universal integral-means spectrum）记录这种集中速率在整类映射上的最大可能指数。对图像有界的子类 `@@M@@\mathcal S_b@@`，Kraetzer 在 1996 年论文与学位论文中依据数值实验猜测 `@@M@@B_b(p)=p^2/4@@`（`@@M@@|p|\le2@@`）、`@@M@@B_b(p)=|p|-1@@`（`@@M@@|p|\ge2@@`），在 `@@M@@p=-1@@` 处给出预测值 `@@M@@1/4@@`。此前最好的严格上界来自 Hedenmalm–Shimorin 的加权 Bergman 空间方法（对无界标准盘类得 `@@M@@0.403@@`）与 Sola 的改进（`@@M@@0.388@@`），都停在 `@@M@@1/4@@` 之上；Beliaev–Smirnov 的随机共形雪花路线给出的是数值近似而非严格误差控制。该问题与 Carleson–Jones 系数问题相联系，且由 Makarov 比较定理，无界谱是有界谱与 Koebe 贡献 `@@M@@3p-1@@` 的最大值，故两谱在正指数处本质不同。本文首次把 `@@M@@p=-1@@` 处的上界严格压到 `@@M@@1/4@@` 之下。

## 主要结果

定理：存在常数 `@@M@@0<\varepsilon<1/4@@` 与 `@@M@@C<\infty@@`，使得对每个标准化单叶函数 `@@M@@f\in\mathcal S@@` 与每个 `@@M@@1/2\le r<1@@`，逆一次幂积分均值满足 `@@M@@M_{-1}[f'](r)\le C(1-r)^{-1/4+\varepsilon}@@`；常数与映射无关，连图像大小也无关，且不要求图像有界。取极限指数即得 `@@M@@B_b(-1)<1/4@@`，故 Kraetzer 猜想的谱恒等式不真。需要说明：证明只给出正间隙的存在性，不给出 `@@M@@\varepsilon@@` 的数值；结论也不解决 `@@M@@p=1@@` 处的猜测值。

## 证明思路

骨架与姊妹篇（Brennan 猜想一文）同构，但权重处处由平方改为一次幂，并新增"严格性"机制。先在上半平面紧类 `@@M@@\mathcal K@@`（`@@M@@F(i)=0@@`、`@@M@@F'(i)=1@@` 的单叶映射，由 Montel 与 Hurwitz 定理紧致）上定义正算子 `@@M@@A_z\Phi(F)=|Q_F(z)|\Phi(T_zF)@@`（`@@M@@Q_F=1/F'@@`），其增长率 `@@M@@\rho=2^\beta@@`（`@@M@@0\le\beta\le1@@`）通过二进网格比较控制全部盘均值：`@@M@@M_{-1}[f'](r)\le C_0\|L^n\|@@`，故 `@@M@@B_b(-1)\le\beta@@`。反设 `@@M@@\beta\ge1/4@@`。第一步与姊妹篇平行：由特征测度加水平平移与对数尺度平均，构造精确参数的仿射律 `@@M@@\mathbb E[|Q_F(x+iy)|\Phi(T_zF)]=y^{-\beta}\mathbb E\Phi(F)@@`，对常数测试求导得矩 `@@M@@\mathbb Ea_F(i)=-\beta@@`、`@@M@@\mathbb E|q_F(i)|^2=\beta(\beta+1)@@`（一次幂权重使矩的数值与姊妹篇不同）。第二步取 `@@M@@k=(\beta+2)/3@@` 与位势 `@@M@@V_\xi^F=y^k/|F-\xi|@@`，其临界点由临界映射 `@@M@@G_F=F-\frac{iy}{k}F'@@` 的原像给出；规范化符号 Jacobi 的期望为 `@@M@@k^2\mathbb EJ_F(i)=(4\beta-1)(\beta+2)/9@@`，当 `@@M@@\beta>1/4@@` 时严格为正，当 `@@M@@\beta=1/4@@` 时恰好为零——这个临界归零是本文独有的分岔。第三步是严格配对：好目标除要求正超水平集紧（对几乎一切映射与目标成立）与正则值（Sard 定理）外，还要求不同临界点的 `@@M@@V@@` 值互不相同；无并列这一性质由 `@@M@@F@@` 的单射性经隐函数论证排除并列临界值的零测集而得。于是按 `@@M@@V@@` 值降序的同秩配对把每个鞍点送到 `@@M@@V@@` 值严格更大的极大点。第四步是严格输运：定义比值 `@@M@@c_F(z)=(V(R_F(z))/V(z))^3>1@@`，配对在每个目标纤维上的单射性给出加权不等式，取期望得 `@@M@@\mathbb EJ_{F,+}c_F\le\mathbb EJ_{F,-}@@`，进而 `@@M@@\mathbb EJ_F(i)\le0@@`；若取等，则非负量 `@@M@@J_{F,+}(c_F-1)@@` 期望为零，迫使 `@@M@@J_F(i)=0@@` 几乎必然——不同点对之间的增益可以任意小，无需一致 Gap。与矩公式比较：`@@M@@\beta>1/4@@` 立即矛盾；只剩 `@@M@@\beta=1/4@@` 且 `@@M@@J_F\equiv0@@` 几乎必然的刚性情形。最后用调和屏障排除它：`@@M@@k=3/4@@` 时 `@@M@@J_F\equiv0@@` 等价于 `@@M@@|q_F+1/4|^2=1/4@@`，从而前 Schwarz 量满足 `@@M@@|F''/F'|\ge1/(4y)@@`，其对数 `@@M@@u@@` 调和且 `@@M@@\ge-\log4-\log y@@`；在矩形 `@@M@@[-1,1]\times[\varepsilon,1]@@` 上构造在 `@@M@@i/2@@` 处随 `@@M@@\log(1/\varepsilon)@@` 增长趋于无穷的调和下屏障，与 `@@M@@u(i/2)@@` 有限矛盾。故 `@@M@@\beta<1/4@@`，取 `@@M@@b\in(\beta,1/4)@@` 用根极限与盘比较即得一致估计。

## 可信度与备注

主结果已 Lean 形式化：族内 StrictMeans.lean 覆盖一致估计与 `@@M@@B_b(-1)<1/4@@` 的推论。本文与姊妹篇《Brennan's conjecture and sharp inverse-square integral means》共享"紧模型—二进采样—鞍点/极大点配对—输运矛盾"框架并互相印证；文中明确声明全部一次幂估计与输运输断均自证，不引用姊妹篇的逆平方端点定理。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇主结果已形式化，但 `@@M@@\varepsilon@@` 的具体数值未给出，读者应以社区核验为准。

{% endraw %}
