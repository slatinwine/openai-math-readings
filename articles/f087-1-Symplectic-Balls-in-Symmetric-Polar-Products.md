---
layout: default
title: "Symplectic Balls in Symmetric Polar Products"
family: "087"
discipline: "Convex and metric geometry"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Symplectic Balls in Symmetric Polar Products

> 结果族 087：The Mahler conjectures, functional inequalities and polar-product symplectic width　·　学科：Convex and metric geometry　·　验证状态：主结果已 Lean 形式化

## 一句话结论
论文证明：对每个 `@@M@@n\ge2@@` 与每个原点对称凸体 `@@M@@K@@`，相空间极积 `@@M@@\operatorname{int}K\times\operatorname{int}K^\circ@@` 的 Gromov 宽度恰为 4——每个容量 `@@M@@c<4@@` 的标准球都能光滑辛地嵌入其中且 4 不可超越；由辛嵌入保体积立刻重新推出对称 Mahler 猜想。

## 问题背景
Gromov 1985 年的非挤压定理（nonsqueezing）表明辛嵌入受体积之外的约束，容量（capacity）自此成为辛几何的核心不变量；Viterbo 进而提出凸域的体积–容量猜想。Artstein-Avidan–Karasev–Ostrover（2014）把它与对称 Mahler 猜想联系起来，证得 Hofer–Zehnder 容量 `@@M@@c_{\mathrm{HZ}}(K\times K^\circ)=4@@`，这给出 Gromov 宽度的上界，但下界需要真实构造球嵌入，此前仅在 `@@M@@\ell_p@@` 单位球（`@@M@@1<p<\infty@@`，Karasev）、立方体–交叉多胞体积（Ramos–Sepe）等特殊族上实现。Vicente 提出"无限制对称极积宽度"问题，本文给出肯定回答。另注：Haim-Kislev–Ostrover 用正五边形否定了一般 Viterbo 猜想，但五边形非中心对称，与本文无冲突。

## 主要结果
定理：对每个整数 `@@M@@n\ge2@@`、每个原点对称凸体 `@@M@@K\subset\mathbb R^n@@`，把 `@@M@@K@@` 放入位置坐标、`@@M@@K^\circ@@` 放入动量坐标，标准辛形式 `@@M@@\omega_0=\sum_j dq_j\wedge dp_j@@`，则 `@@M@@U_K=\operatorname{int}K\times\operatorname{int}K^\circ@@` 的 Gromov 宽度（Gromov width）`@@M@@c_G(U_K)=4@@`：对每个 `@@M@@0<c<4@@` 存在光滑辛嵌入 `@@M@@B^{2n}(c)\hookrightarrow U_K@@`。推论一：对称 Mahler 不等式 `@@M@@\operatorname{vol}_n(K)\operatorname{vol}_n(K^\circ)\ge 4^n/n!@@`（辛嵌入保体积而 `@@M@@\operatorname{vol}(B^{2n}(c))=c^n/n!@@`，令 `@@M@@c\uparrow4@@` 即得），立方体表明常数精确；推论二：`@@M@@n\ge3@@` 时满足严格体积和与两两容量条件的有限球组可不相交地装入 `@@M@@U_K@@`。

## 证明思路
下界来自两个解析部件的配合。第一个是"全纯消失产生球"原理：若全纯映射 `@@M@@f:\Omega\subset\mathbb C^n\to\mathbb C^m@@` 以原点为唯一公共零点、`@@M@@|f(z)|=O(|z|^k)@@` 且 `@@M@@|f|^2@@` 的次水平集在 `@@M@@\Omega@@` 中紧，则域 `@@M@@V=\{|f|^2<1\}@@` 连同辛形式 `@@M@@\omega=dd^c(|z|^2+|f|^2)@@` 包含每个容量 `@@M@@<\pi k@@` 的标准球。其证明分四步：先用光滑递增修正把 `@@M@@\log|f|^2@@` 的对数奇性削成斜率受控的仿射行为；再用正则化极大（regularized maximum，Richberg 粘合技巧）以径向位势 `@@M@@\mu\log(|z|^2+\delta)-M@@` 替换奇点而不改变边界附近的形式；然后用紧支集的 Moser 形变（Moser deformation）把光滑化的形式拉回原形式；最后在径向模型 `@@M@@R(z)=\sqrt{1+\mu/(|z|^2+\delta)}\,z@@` 下显式读出一个标准球。

第二个部件控制动量尺度：沿用透镜共形映射 `@@M@@F:\mathbb D\to D@@`（Gross 均匀分布映射的旋转，尖端在 `@@M@@\pm i@@`），其逆 `@@M@@g@@` 的高次幂的水平原函数满足一致界 `@@M@@|J_k|\le(\pi k/4)|g|^{2k}+o(k)@@`，且一致性一直保持到尖端——这一点必不可少，因为切片高度会随 `@@M@@k@@` 增大而逼近 `@@M@@\pm1@@`。组合时把条带体 `@@M@@K=\{x:|b_j\cdot x|\le1\}@@` 的实约束复线性延拓，令 `@@M@@f_j(z)=g(b_j\cdot z)^k@@`，则全纯球原理适用。相空间实现 `@@M@@\Phi_k@@` 把 `@@M@@z=u+ix@@` 的虚部送入位置 `@@M@@q=x@@`，动量取 `@@M@@p=-u-\sum_j J_k(b_j\cdot u,\,b_j\cdot x)\,b_j@@`，其中带符号切片积分修正标准动量：直接拉回计算给出 `@@M@@\Phi_k^*\omega_0=\omega@@`，偏导数 `@@M@@\partial_v J_k\ge0@@` 保证整体单射，一致界保证动量落在 `@@M@@S_k\operatorname{int}K^\circ@@` 内，且 `@@M@@S_k=(1+o(1))\pi k/4@@`。动量除以 `@@M@@S_k@@`、源球做补偿性伸缩，两尺度相除后对充分大的 `@@M@@k@@` 就凑出每个给定的容量 `@@M@@c<4@@`；整个过程对每个 `@@M@@c@@` 是一次有限构造，无需嵌入的极限。最后用极体中的有限条带体逼近把下界推广到任意对称凸体。上界则用 AAKO 的支撑柱面论证：取 `@@M@@\langle q_0,p_0\rangle=1@@` 的配对作辛线性变换，把 `@@M@@U_K@@` 嵌入 `@@M@@(-1,1)^2\times\mathbb R^{2n-2}@@`，再等面积地映入 `@@M@@B^2(4)\times\mathbb R^{2n-2}@@`，由 Gromov 非挤压定理宽度不得超过 4。

## 可信度与备注
主结果已由 Lean 形式化。本篇与对称 Mahler 姊妹篇共用透镜映射与逆映射高次幂技术，但论文明确声明其证明既不使用姊妹篇的体积积定理也不使用等号分类，是独立路线；等号情形本篇不作断言。同族一般凸体篇给出非对称常数与单纯形等号。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，球装填推论引用了同集另一篇球装填定理，以社区核验为准。

{% endraw %}
