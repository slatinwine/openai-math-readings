---
layout: default
title: "One-sided negative sectional curvature and the holomorphic Liouville property"
family: "359"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | One-sided negative sectional curvature and the holomorphic Liouville property

> 结果族 359：Negative Kähler curvature without bounded holomorphic coordinates　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在某个充分大的有限复维数 `@@M@@m@@` 下，构造出与 `@@M@@\mathbb R^{2m}@@` 微分同胚、带完备 Kähler 度量且截面曲率处处不超过 `@@M@@-1@@` 的区域，其有界全纯函数却只有常数——"一致负上界曲率必逼出非常数有界全纯函数"的单侧问题被否定。

## 问题背景

记 `@@M@@H^\infty(M)@@` 为有界全纯函数代数；`@@M@@H^\infty(M)=\mathbb C@@` 称为全纯 Liouville 性质 (holomorphic Liouville property)。源于 Yau 1982 年问题 38、经 Wu 与 Yau 记录的公开表述问：完备单连通、复维数至少为二、实截面曲率 (sectional curvature) 满足 `@@M@@\operatorname{Sec}_g\le -a^2<0@@` 的 Kähler 流形，是否必含非常数有界全纯函数？注意假设只有单侧上界而无下界。Seshadri 改造 Klembeck 的径向曲率计算，曾在 `@@M@@\C^n@@` 上造出截面曲率严格负的完备 Kähler 度量，但某些曲率趋于零，而有界整函数皆常数，结论平凡成立——一致负上界正是问题要害。Shcherbina 与 Zhang 曾用 Wermer 型集合造出具有该 Liouville 性质的 `@@M@@\C^2@@` 区域，但完全没有曲率控制；Cao–Shaw 宣布过的夹紧结果已被撤稿。曲率与有界函数刚性能否分离，此前悬而未决。

## 主要结果

主定理：存在有限整数 `@@M@@m\ge2@@` 与区域 `@@M@@\mathcal T\subset\mathbb C^m@@`，微分同胚于 `@@M@@\mathbb R^{2m}@@`，带完备 Kähler 度量 `@@M@@g@@`，满足 `@@M@@\operatorname{Sec}_g\le-1@@` 且 `@@M@@H^\infty(\mathcal T)=\mathbb C@@`；其截面曲率无下界。这否定上述单侧问题，也否定 H. Wu 1967 年更强的早期问题（对一切实二维平面的负上界自动限制全纯截面方向，而本例连一个非常好数的有界全纯函数都没有）。推论性观察：`@@M@@\mathcal T@@` 上的 Carathéodory 无穷小伪度量 (Carathéodory infinitesimal pseudometric) 恒为零，而 Bergman、Kobayashi–Royden 等内蕴度量的比较定理在此均不适用——它们都需要本例所缺的曲率下界。

## 证明思路

先做曲率转移。取管状域 (tube domain) `@@M@@\mathcal T=\{(s,y,w):\operatorname{Im}w>\ell(s,y)\}@@`（最终维数 `@@M@@m=n+2@@`：`@@M@@n@@` 个空间变量、一个纤维变量 `@@M@@y@@`、一个管变量 `@@M@@w@@`），度量为 `@@M@@\partial\bar\partial[-\log(\operatorname{Im}w-\ell)]@@`；关键引理证明：只要位势 `@@M@@\ell@@` 自身的度量完备且实截面曲率非正，管度量就完备且 `@@M@@\operatorname{Sec}\le-1@@`（与复双曲空间比较）。于是问题化为：构造这样的 `@@M@@\ell@@`，同时在管内安放巨大的全纯圆盘。

分析侧的核心是多项式采样。考察斜切圆盘 `@@M@@t\mapsto(Rv,\zeta+t,w+i\alpha bt)@@`：若它落在管内，Cauchy 估计给出 `@@M@@|f_y+i\alpha bf_w|\le L^{-1}@@`。用随机高斯齐次多项式系统 `@@M@@(H_N,p_N)@@`，其零点在射影空间 `@@M@@\mathbb P^{n-1}@@` 上均匀分布；取满足 `@@M@@p_N(v)=1@@` 的代表元，其单位根循环 `@@M@@e^{2\pi iq/N}v@@` 上的 Fourier 平均恰好分离出次数 `@@M@@\equiv h\pmod N@@` 的 Taylor 部分。维数计数是点睛之笔：固定大 `@@M@@n@@` 后，前 `@@M@@k@@` 个存活齐次次数的赋值向量只占网格值空间不到百分之二；再用随机相位与 Gram 矩阵集中不等式，可选定相位 `@@M@@b_\xi@@` 使 `@@M@@f_w@@` 的 `@@M@@h@@` 次 jet 一致远离该子空间。于是圆盘估计转化为 `@@M@@f_w@@` 各次 Taylor 系数的指数衰减；让测试高度 `@@M@@D_j\to\infty@@` 但 `@@M@@D_j/c_j\to0@@`，用 Hadamard 三线定理把高处的衰减压回整个半平面，得 `@@M@@f_w\equiv0@@`；此时 `@@M@@f@@` 沿 `@@M@@w@@` 纤维为常数，下降为 `@@M@@\mathbb C^{n+1}@@` 上的有界整函数，由 Liouville 定理为常数。

几何侧则用 Calabi–Hwang–Singer 圆不变丛框架经偏 Legendre 变换 (partial Legendre transform) 造 `@@M@@\ell@@`，曲率张量呈六个块；每个实二维平面对应秩不超过二的 Hermitian 测试矩阵，这一秩限制使所有迹损失与维数无关，陡峭的纤维剖面提供正裕度以吸收多项式井与剪切项。构造按"封顶—触发—测试—后坡—加速—换心—复位"的时钟递归推进：换心不是全纯坐标变换，需先对齐两个径向度量的 jet、临时加宽纤维剖面再移动中心，最后带常数偏移恢复；每个阶段都为所有未来井预留份额。所有几何常数先于维数选定，最后才取大 `@@M@@n@@` 使 `@@M@@\sum_{r=1}^{k-1}r^{n-1}/(n-1)!<0.01@@`；完备性由 `@@M@@g\ge c_1V@@` 与纤维逃逸估计保证；而在中心轴附近可验证曲率确实无下界。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。它与同族姊妹篇（`@@M@@\C^3@@` 中双侧夹紧却无有界全纯坐标的三维例子）证明相互独立、互不引用：本文单侧曲率、彻底无非常数有界函数，姊妹篇双侧夹紧但保留两个基坐标函数，二者合起来把这一族均匀化问题的两个版本分别否定。按 OpenAI 官方声明，未经形式化的结果可能有问题，阅读时宜保持核验态度。

{% endraw %}
