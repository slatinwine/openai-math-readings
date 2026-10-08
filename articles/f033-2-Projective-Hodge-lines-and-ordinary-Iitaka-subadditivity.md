---
layout: default
title: "Projective Hodge lines and ordinary Iitaka subadditivity"
family: "033"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Projective Hodge lines and ordinary Iitaka subadditivity

> 结果族 033：Iitaka subadditivity, variation, and logarithmic additivity　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

数一个代数簇能朝几个独立方向"生长"（Kodaira 维数），是双有理几何的第一课。Iitaka 半个世纪前猜想：把 `@@M@@X@@` 压到底 `@@M@@Z@@`、每点上方长一根纤维 `@@M@@F@@`，则 `@@M@@X@@` 的生长方向数至少是 `@@M@@F@@` 的加 `@@M@@Z@@` 的。这句直觉是分类纲领的顶梁柱之一，此前却只有分情形的零星进展；本文在射影范畴、特征零下把它完整证明。

**关键词卡片**

- Kodaira 维数（Kodaira dimension）：用 `@@M@@|mK|@@` 的映射像维数度量的复杂度，从 `@@M@@-\infty@@` 到空间维数。
- 几何一般纤维（geometric generic fiber）：一般位置的那根纤维。
- 典范丛公式（canonical bundle formula）：把 `@@M@@K_X@@` 拆成"基 + 边界 + 模除子"的会计工具。
- Hodge 结构变分（variation of Hodge structures）：随基点流动的影子系统，本文从中榨出正性。
- 伴随正性（adjoint positivity）：周期理论给出的"`@@M@@K_S+jL@@` 很大"型结论，证明的引擎。

**看个具体例子**

取一个曲面纤维化：底是亏格 2 曲线（`@@M@@\kappa(Z)=1@@`），纤维是亏格 3 曲线（`@@M@@\kappa(F)=1@@`）——任何这样的纤维化都适用，不必是乘积，最简单的实例是乘积 `@@M@@C_3\times C_2@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<ellipse cx="280" cy="212" rx="185" ry="42" fill="none" stroke="#333" stroke-width="1.8"/>
<text x="280" y="266" font-size="14" text-anchor="middle">底 Z：亏格 2 曲线，κ(Z) = 1</text>
<line x1="170" y1="176" x2="170" y2="196" stroke="#aaa" stroke-width="1.4"/>
<line x1="280" y1="170" x2="280" y2="188" stroke="#aaa" stroke-width="1.4"/>
<line x1="390" y1="176" x2="390" y2="196" stroke="#aaa" stroke-width="1.4"/>
<ellipse cx="170" cy="140" rx="30" ry="28" fill="none" stroke="#333" stroke-width="1.8"/>
<circle cx="161" cy="134" r="5.5" fill="none" stroke="#333" stroke-width="1.3"/>
<circle cx="176" cy="132" r="5.5" fill="none" stroke="#333" stroke-width="1.3"/>
<circle cx="169" cy="150" r="5.5" fill="none" stroke="#333" stroke-width="1.3"/>
<ellipse cx="280" cy="132" rx="32" ry="28" fill="none" stroke="#333" stroke-width="1.8"/>
<circle cx="270" cy="126" r="5.5" fill="none" stroke="#333" stroke-width="1.3"/>
<circle cx="287" cy="124" r="5.5" fill="none" stroke="#333" stroke-width="1.3"/>
<circle cx="279" cy="142" r="5.5" fill="none" stroke="#333" stroke-width="1.3"/>
<ellipse cx="390" cy="140" rx="30" ry="28" fill="none" stroke="#333" stroke-width="1.8"/>
<circle cx="381" cy="134" r="5.5" fill="none" stroke="#333" stroke-width="1.3"/>
<circle cx="396" cy="132" r="5.5" fill="none" stroke="#333" stroke-width="1.3"/>
<circle cx="389" cy="150" r="5.5" fill="none" stroke="#333" stroke-width="1.3"/>
<text x="280" y="52" font-size="14" text-anchor="middle">每根纤维 F：亏格 3 曲线（三孔），κ(F) = 1</text>
<text x="280" y="80" font-size="14" text-anchor="middle">定理：κ(X) ≥ 1 + 1 = 2；曲面至多 2 ⇒ 恰为 2</text>
</svg>

</div>

代入数字：定理给出 `@@M@@\kappa(X)\ge 1+1=2@@`；而曲面的复杂度至多是 2，所以恰好等于 2（一般型）。若底或纤维的复杂度是 `@@M@@-\infty@@`，不等式按约定 `@@M@@(-\infty)+a=-\infty@@` 读取。主定理对特征零任意代数闭域上的光滑射影纤维化一律成立。

**为什么值得关心**

这是双有理几何最核心的不等式之一，本文在射影范畴一次做满；证明还把 Hodge 理论的正性接进了经典极小模型工具箱。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文完整证明了经典 Iitaka 子可加性猜想：特征零代数闭域上任意光滑射影代数纤维空间 `@@M@@f:X\to Z@@` 都满足 `@@M@@\kappa(X)\ge\kappa(F)+\kappa(Z)@@`（`@@M@@F@@` 为几何一般纤维）。此前仅有分情形与低维进展的这一双有理几何核心不等式，由此在射影范畴内获得完整解答。

## 问题背景

Kodaira 维数（Kodaira dimension）`@@M@@\kappa(X)@@` 是完备线性系 `@@M@@|mK_X|@@` 给出的有理映射像维数的最大值，度量代数簇的双有理复杂度。Iitaka 在其除子维数理论中提出子可加性猜想 `@@M@@C_{n,m}@@`：对光滑射影簇间具连通纤维的满射态射，底与几何一般纤维的 Kodaira 维数应可加地贡献于全空间。此前只有分情形进展：Viehweg 的弱正性方法处理一般型底；Kawamata 证明曲线底以及一般纤维有好极小模型的情形；Kollár 处理一般型纤维；Kovács–Patakfalvi 建立了 log 一般型纤维的加法定理；Birkar 解决全维数至多六的情形，Chang 在 `@@M@@\kappa(X)\ge0@@` 下扩至七。一般情形长期卡在：moduli 除子携带的正性必须与边界坏除子的干扰同时控制，而经典方法只能顾及其一，Hodge 理论正是在这一缺口处进入。

## 主要结果

主定理（普通 Iitaka 子可加性）：设 `@@M@@k@@` 为特征零的代数闭域，`@@M@@f:X\to Z@@` 是光滑连通射影簇间具连通纤维的满射射影像态射，`@@M@@F@@` 为其几何一般纤维，约定 `@@M@@\kappa(\text{点})=0@@`、`@@M@@(-\infty)+a=-\infty@@`，则 `@@M@@\kappa(X)\ge\kappa(F)+\kappa(Z)@@`。

证明的引擎是一条独立的周期理论定理（射影伴随正性）：设 `@@M@@\mathbb V@@` 是光滑射影簇 `@@M@@Y@@` 的稠开集上带积分格、有理极化的纯 Hodge 结构变分（variation of Hodge structure），其最高的非零 Hodge 滤波步恰为一条线；若 `@@M@@M\in\operatorname{Pic}(Y)\otimes\Q@@` 在某个 alteration 上与该线的延拓 `@@M@@J@@` 相差正有理倍，则存在纤维化 `@@M@@p:Y\to S@@` 与 nef 有理线丛 `@@M@@L@@`，使 `@@M@@M\sim_{\Q}p^*L@@`，且对所有充分大的 `@@M@@j@@`，`@@M@@K_S+jL@@` 是大除子（big divisor）。

## 证明思路

先做相对 Iitaka 纤维化，把 `@@M@@X@@` 双有理替换为 `@@M@@\widetilde X\xrightarrow{g}Y\xrightarrow{q}Z@@`，使 `@@M@@\dim(Y/Z)=d=\kappa(F)@@` 且 `@@M@@g@@` 的几何一般纤维 Kodaira 维数为零。再对 `@@M@@g@@` 施加 Fujino–Mori 典范丛公式（canonical bundle formula）`@@M@@K_{\widetilde X}\sim_{\Q}g^*(K_Y+B+M)+R@@`：`@@M@@B@@` 是有效 klt 边界，`@@M@@M@@` 是 nef 的 moduli 除子，剩余除子 `@@M@@R@@` 的直像与例外性质保证截面比较 `@@M@@\kappa(X)\ge\kappa(Y,D)@@`（记 `@@M@@D=K_Y+B+M@@`），且 `@@M@@D@@` 在 `@@M@@q@@` 的几何一般纤维上大。把 `@@M@@M@@` 送入伴随正性定理的关键，是最小指标典范根覆盖（least-index canonical root cover）：Kodaira 维数零的纤维取这一覆盖后几何亏格为一，其唯一的典范形式恰好张成变分 `@@M@@\mathbb V=R^nh_*\Q@@` 的整条最高 Hodge 线（即使循环覆盖群的特征并非有理）；Ambro 的理论进一步保证 `@@M@@M@@` 在 alteration 上与最高线的 Schmid 延拓有理等价。伴随正性定理本身是最难的环节：周期像（period image）的代数性由 Bakker–Brunebarbe–Tsimerman 定理提供，但要得到大伴随除子，必须同时消去两类坏除子——单值对数（monodromy logarithm）非零的边界分支与有限商映射的除子分歧。做法是先取包含最高线的有理极小子变分，配合 André 的单值正规性定理与 Griffiths–Deligne–Schmid 的固定部分定理；核心的切向秩原理断言：若内部最高线映射的秩在边界极限处不降，则邻近像已包含于极限像之中。在幂零退化处，极限线必落入 `@@M@@N@@` 的核；在惯性分歧处，极限线落入单一特征空间——两种情形都会经固定部分定理迫使相关群元素固定整个周期像，与有理极小性矛盾，故秩必严格下降。此后用初等截面计数收尾：内部给出 `@@M@@L@@` 的 `@@M@@r@@` 次多项式增长，坏除子上的限制至多 `@@M@@r-1@@` 次，商上例外有效除子不改变增长阶，于是 `@@M@@M\sim_{\Q}p^*L@@` 且 `@@M@@K_S+jL@@` 大。最后回到底 `@@M@@Y@@` 收尾：Stein 因子分解与余切序列的秩估计给出 `@@M@@p@@` 的一般纤维 log Kodaira 维数非负；Fujino 的扭曲弱正性把大除子 `@@M@@K_S+jL-H@@` 转化为与 `@@M@@E_1=K_Y+B+jM-p^*H@@` 线性等价的有效除子；插值恒等式 `@@M@@D\sim_{\Q}\lambda E_1+(1-\lambda)E_2@@` 把 `@@M@@D@@` 联系到有效 klt 对的 log 典范类 `@@M@@E_2@@`，而 `@@M@@E_2@@` 在几何一般 `@@M@@q@@`-纤维上大，于是 log 一般型纤维的加法定理给出 `@@M@@\kappa(Y,E_2)\ge d+\kappa(Z)@@`，串联各不等式即得结论。复数域之外的特征零域，通过把数据下降到有限生成子域、嵌入 `@@M@@\C@@` 并利用 Kodaira 维数在纯量扩张下的不变性完成。

## 可信度与备注

主结果暂无 Lean 形式化证明，请以社区核验为准；作者亦说明论证不依赖 Tsuji、Maehara 同期预印本中的类似声明，属独立证明。本篇是结果族 033 的射影支柱：姊妹篇《The reverse logarithmic Kodaira inequality and additivity》的负纤维分支已有配套 Lean 形式化，同批的紧 Kähler b-半丰富性一文与本文共享 Bakker–Filipazzi–Mauri–Tsimerman 的 Hodge 理论工具，互为印证。按 OpenAI 官方声明，未经形式化的结果可能存在问题，宜以待核验态度阅读。

{% endraw %}
