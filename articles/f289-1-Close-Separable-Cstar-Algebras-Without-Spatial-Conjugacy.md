---
layout: default
title: "Close Separable C*-Algebras Without Spatial Conjugacy"
family: "289"
discipline: "Operator algebras"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Close Separable C*-Algebras Without Spatial Conjugacy

> 结果族 289：Strong Kadison–Kastler stability and its spatial boundaries　·　学科：Operator algebras　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

两栋楼的概略图纸完全相同，外墙也贴合到任意精度，但内部承重结构不同：不存在任何刚性搬移能把一栋原样叠到另一栋上。本文据此推翻了 C*-代数层面的 Kadison–Kastler 共轭猜想。"贴合到任意精度"指两代数单位球的 Hausdorff 距离可小于任何事先给定的 `@@M@@\varepsilon@@`；"刚性搬移"指整个 Hilbert 空间的一次酉旋转。

**关键词卡片**

- C*-代数与 von Neumann 代数：范数闭包是精细图纸，弱闭包是概略图纸
- 空间共轭（spatial conjugacy）：存在酉算子 `@@M@@u@@` 使 `@@M@@uAu^*=B@@`
- 核性（nuclearity）：旧有正结果的关键假设，本文构造不带它
- 张量范数恒等式（tensor norm identity）：本文发明的"辨楼术"，共轭必保它
- von Neumann 闭包 `@@M@@A''=B''@@`：本文反例中两代数的弱闭包相同

**看个具体例子**

数字版定理：一侧 `@@M@@\bigl\|\sum_i p_iz_i\bigr\|\ge mt@@`，另一侧 `@@M@@\bigl\|\sum_i p_i\otimes z_i\bigr\|\le 2\sqrt m@@`。取 `@@M@@t=0.1,\ m=500@@`：一侧至少 `@@M@@50@@`，另一侧至多 `@@M@@2\sqrt{500}\approx 44.7@@`——恒等式破裂，两代数不可能空间共轭；而与此同时，它们的 Kadison–Kastler 距离却可以压到任意小。这件"辨楼术"检查的是：把同一串元素分别放在原空间与张量空间中求和，范数是否恒相等——共轭必保持它，一旦破裂便无共轭。

**为什么值得关心**

它表明"任意接近"在 C* 世界并不保证共轭，除非补上核性；与姊妹篇合看，"接近即共轭"只在 von Neumann 双边世界成立，边界由此被精确画出。旧例中 Johnson 的构造仍可共轭、Choi–Christensen 的反例依赖不可分性，本文首次在可分且无核性假设下给出致命一击。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

推翻可分 `@@M@@C^*@@`-代数形式的 Kadison–Kastler 空间共轭猜想：对任意 `@@M@@\varepsilon>0@@`，构造出共单位元、范数可分、`@@M@@d_{\mathrm{KK}}(A,B)<\varepsilon@@` 且 von Neumann 闭包相同的 `@@M@@C^*@@`-代数对 `@@M@@A,B@@`，但不存在任何酉算子使 `@@M@@uAu^*=B@@`。

## 问题背景

Kadison–Kastler 问题的 `@@M@@C^*@@`-版本问：范数足够接近的 `@@M@@C^*@@`-代数是否必被某酉算子（unitary）共轭（此处不要求 `@@M@@u@@` 接近恒等算子）？已知图景分三块：Johnson 在 1982 年构造了任意接近的可分核代数，其实现酉元无法接近恒等算子，但共轭仍然存在；Choi 与 Christensen 在 1983 年给出任意接近却不同构的代数对，但范数不可分性是那些例子的本质成分；Christensen–Sinclair–Smith–White–Winter 于 2010 年证明：可分 Hilbert 空间上充分接近的可分核（nuclear）`@@M@@C^*@@`-代数必空间同构。悬而未决的是：去掉核性假设，仅凭"范数可分 + 任意接近"是否仍保证空间共轭？本文对此给出否定回答。

## 主要结果

**定理**：对每个 `@@M@@\varepsilon>0@@`，存在可分复 Hilbert 空间 `@@M@@H@@` 与共单位元 `@@M@@I_H@@` 的幺正、范数可分 `@@M@@C^*@@`-代数 `@@M@@A,B\subseteq\mathcal B(H)@@`，使得 `@@M@@d_{\mathrm{KK}}(A,B)<\varepsilon@@`（Kadison–Kastler 距离，即单位球间的 Hausdorff 距离）、`@@M@@A''=B''@@`（von Neumann 闭包相同），但没有任何酉算子 `@@M@@u\in\mathcal B(H)@@` 满足 `@@M@@uAu^*=B@@`。适用范围的边界同样重要：定理不设核性假设；它不主张两代数抽象不同构——构造中的子代数 `@@M@@P_0,P_t@@` 本身可用接近恒等的酉元互相共轭，障碍仅在于它们在坐标代数 `@@M@@D@@` 内的位置；它也不构成 von Neumann 代数层面的反例，故与本族第一篇的正定理相容。

## 证明思路

证明组合两个机制：收敛序列归约与相对张量范数检验。归约：设 `@@M@@D\subseteq\mathcal B(L)@@` 是中心为标量、范数可分的幺正代数，`@@M@@P\subseteq D@@` 是共单位元的 `@@M@@C^*@@`-子代数，令 `@@M@@\mathcal E_D(P)=\{(x_n):x_n\in D,\ x_n\to p\in P\ \text{依范数}\}@@` 在 `@@M@@\bigoplus_{n\ge1}L@@` 上对角作用。此构造保持 Kadison–Kastler 距离，且坐标投影恰为其极小中心投影，因此任何共轭酉算子必置换坐标、并在每个坐标处正规化（normalize）`@@M@@D@@`，从而把 `@@M@@Q@@` 中的常值序列拉回为"`@@M@@P@@` 经 `@@M@@D@@` 的正规化子共轭"的极限。检验：称 `@@M@@P\subseteq D@@` 满足空间张量范数恒等式，若 `@@M@@\|\sum_ip_iz_i\|_{\mathcal B(L)}=\|\sum_ip_i\otimes z_i\|_{\mathcal B(L\otimes L)}@@` 对一切 `@@M@@p_i\in P@@`、`@@M@@z_i\in D'@@`（交换子代数）成立；该性质在 `@@M@@D@@` 的正规化子共轭下不变，且通过有限族的同步范数极限传递——因此它能区分 `@@M@@\mathcal E_D(P)@@` 与 `@@M@@\mathcal E_D(Q)@@`：一个满足、一个不满足，则二者不可能空间共轭，哪怕距离任意小。具体代数来自自由群：与姊妹篇同源的树形 Pytlik–Szwarc 形变给出表示 `@@M@@\pi_t@@`，满足 `@@M@@\langle\pi_t(s_i)\delta_e,\delta_e\rangle=t@@` 且 `@@M@@\sup_{g}\|\pi_t(g)-\lambda(g)\|\le c(t)\to 0@@`（与正则表示之差集中在一条测地路上）。在 `@@M@@L=K\otimes K@@` 上取 `@@M@@P_a=C^*(\lambda(g)\otimes\pi_a(g))@@`，坐标代数 `@@M@@D@@` 由 `@@M@@\lambda(g)\otimes I@@`、`@@M@@I\otimes\pi_0(g)@@`、`@@M@@I\otimes\pi_t(g)@@` 及全部矩阵单元 `@@M@@I\otimes E_{xy}@@` 生成（其中心为标量，靠自由群共轭类皆无穷的初等事实）。吸收公式 `@@M@@W_\sigma(\lambda(g)\otimes I)W_\sigma^*=\lambda(g)\otimes\sigma(g)@@` 给出 `@@M@@\|W-I\|\le c(t)@@` 的酉元使 `@@M@@WP_0W^*=P_t@@`，故两代数确实接近——甚至可共轭，但 `@@M@@W@@` 不正规化 `@@M@@D@@`。`@@M@@P_0@@` 满足恒等式：一个重排酉元把 `@@M@@P_0@@` 变成 `@@M@@I\otimes C^*(\lambda(G))@@`，四重张量因子的置换把两侧化归为同一范数。`@@M@@P_t@@` 破坏恒等式：取 `@@M@@p_i=\lambda(s_i)\otimes\pi_t(s_i)@@`、`@@M@@z_i=\rho(s_i)\otimes I\in D'@@`，乘积范数 `@@M@@\ge mt@@`（系数 `@@M@@t@@` 在 `@@M@@\delta_e\otimes\delta_e@@` 处显现），而张量范数经吸收化归为 `@@M@@\|\sum_i\lambda(s_i)\|\le 2\sqrt m@@`（Haagerup 型估计：以"以 `@@M@@s_i^{-1}@@` 开头的词"上的两两正交投影分组）；选 `@@M@@m>4/t^2@@` 即得严格不等式 `@@M@@mt>2\sqrt m@@`。最终取 `@@M@@A=\mathcal E_D(P_0)@@`、`@@M@@B=\mathcal E_D(P_t)@@`：公共理想 `@@M@@c_0(\mathbb N,D)@@` 保证 von Neumann 闭包相同，而范数极限条件保留了两包含的区别，排除了任何酉共轭。

## 可信度与备注

本反例与族内第一篇不矛盾：那里是 von Neumann 代数加双边距离，这里降为 `@@M@@C^*@@`-层面；与第二篇合看，说明"接近即共轭"只在 von Neumann 双边世界成立。Johnson 与 Choi–Christensen 的旧例都无法替代它：前者仍空间共轭，后者依赖范数不可分性。主结果暂无 Lean 形式化证明；OpenAI 官方声明未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
