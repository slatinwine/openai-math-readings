---
layout: default
title: "A surface counterexample to Shafarevich holomorphic convexity"
family: "046"
discipline: "Algebraic and complex geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A surface counterexample to Shafarevich holomorphic convexity

> 结果族 046：Shafarevich counterexamples in dimension two and with large fundamental group　·　学科：Algebraic and complex geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把一个代数曲面解开成万有覆盖后，里面挂着一串无穷长的"珍珠项链"：每颗珍珠都是一个球面，首尾相接延伸到无穷远。全纯函数在每颗珍珠上只能取一个常数，于是这条项链把"用函数区分位置"的可能性彻底锁死。本文第一次在具体曲面里造出了这串项链。

**关键词卡片**

- 全纯凸（holomorphically convex）：全纯函数能给每块有限区域画出有限"势力范围"的性质。
- Shafarevich 猜想（Shafarevich conjecture）：完备代数簇的万有覆盖是否总是全纯凸。
- 有理曲线（rational curve）：同构于球面 P¹ 的最简曲线，自身单连通。
- Nori 弦（Nori string）：覆盖中无穷延伸的有理曲线链，全纯函数的天敌。
- 节点曲线（nodal curve）：多条曲线在交点处焊接成的一体。

**看个具体例子**

反例 X 是光滑射影复曲面，含一条全由有理曲线焊接成的节点曲线 Z₀，且它在 π₁(X) 中的像无限。于是 Z₀ 的提升 W 成为闭、非紧、局部有限的项链：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <rect x="0" y="0" width="560" height="280" fill="#ffffff"/>
  <text x="30" y="32" font-size="16" fill="#222222">无穷 Nori 弦：一串首尾相接的球面</text>
  <text x="42" y="108" font-size="18" fill="#888888">…</text>
  <circle cx="92" cy="100" r="34" fill="#eef4fb" stroke="#3b6fb5" stroke-width="2.5"/>
  <circle cx="160" cy="100" r="34" fill="#eef4fb" stroke="#3b6fb5" stroke-width="2.5"/>
  <circle cx="228" cy="100" r="34" fill="#eef4fb" stroke="#3b6fb5" stroke-width="2.5"/>
  <circle cx="296" cy="100" r="34" fill="#eef4fb" stroke="#3b6fb5" stroke-width="2.5"/>
  <circle cx="364" cy="100" r="34" fill="#eef4fb" stroke="#3b6fb5" stroke-width="2.5"/>
  <text x="428" y="108" font-size="16" fill="#888888">…（无限延伸）</text>
  <text x="82" y="106" font-size="13" fill="#1d3d63">P¹</text>
  <text x="150" y="106" font-size="13" fill="#1d3d63">P¹</text>
  <text x="218" y="106" font-size="13" fill="#1d3d63">P¹</text>
  <text x="286" y="106" font-size="13" fill="#1d3d63">P¹</text>
  <text x="354" y="106" font-size="13" fill="#1d3d63">P¹</text>
  <text x="60" y="175" font-size="14" fill="#333333">每颗珠子 ≅ 球面，单连通，整颗提升到万有覆盖</text>
  <text x="60" y="203" font-size="14" fill="#333333">全纯函数在每颗珠子上由极大原理取常数，并沿焊点传递</text>
  <text x="60" y="235" font-size="14" fill="#c0392b">⇒ 整条链上恒为常数 ⇒ 无法全纯凸</text>
</svg>

</div>

推论同样锋利：由"线性 Shafarevich"定理，π₁(X) 没有任何忠实的有限维复表示，X 也不是 Campana 意义下的特殊簇。

**为什么值得关心**

无穷 Nori 弦作为障碍被讨论了近三十年，却从未落实为射影曲面；本文首次实现，从低维一侧否定了 Shafarevich 猜想。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文构造了一个光滑连通射影复曲面 `@@M@@X@@`，其中一条全由有理曲线组成的连通节点曲线 `@@M@@Z_0@@` 的基本群在 `@@M@@\pi_1(X)@@` 中的像无限；其万有覆盖因此不是全纯凸的——Shafarevich 全纯凸性猜想在复维数二被否定。

## 问题背景

Shafarevich 问：完备代数簇的万有覆盖是否全纯凸（holomorphically convex）——每个紧集的全纯包（holomorphic hull）`@@M@@\widehat K_V@@` 都紧？肯定结果集中在特殊类：Gurjar–Shastri 的椭圆曲面、Katzarkov 的几乎幂零基本群，以及 Eyssidieux、EKPR、Campana–Claudon–Eyssidieux 直到 Deng–Yamanoi、Bakker–Brunebarbe–Tsimerman 的"线性 Shafarevich"系列，全都要求基本群有某种忠实线性表示。经典障碍早已明确（Lasell–Ramachandran、Katzarkov–Ramachandran）：若一条连通曲线各分量的基本群像有限而整条曲线的像无限，其提升便是"无穷 Nori 弦"（infinite Nori string）——闭、非紧、局部有限的紧有理曲线链，全纯函数在其上必为常数，全纯凸空间容不下它。Bogomolov–Katzarkov 1998 年的候选构造依赖一条未被证明的群论无穷性断言；Eyssidieux–Funar 又对相关的均匀分歧构造证出了凸性。本文首次把这条经典障碍真正落实到射影曲面中。

## 主要结果

定理：存在光滑连通射影复曲面 `@@M@@X@@`，含连通节点曲线 `@@M@@Z_0@@`，其不可约分量皆为光滑有理曲线，且 `@@M@@\im(\pi_1(Z_0)\to\pi_1(X))@@` 无限。在单连通万有覆盖 `@@M@@\widetilde X@@` 中，`@@M@@Z_0@@` 之上的连通分量 `@@M@@W@@` 是闭、连通、非紧、局部有限的紧有理曲线之并，任一点 `@@M@@w\in W@@` 的全纯包 `@@M@@\widehat{\{w\}}_{\widetilde X}@@` 非紧；特别地 `@@M@@\widetilde X@@` 不是全纯凸的。机理在有理包引理：有理分量单连通，逐个等距提升为紧有理曲线；`@@M@@W\to Z_0@@` 是无限叶覆盖；极大原理使全纯函数在每条紧曲线上取常数并沿交点传递，故在整个 `@@M@@W@@` 上为常数。推论：由线性 Shafarevich 定理，`@@M@@\pi_1(X)@@` 无忠实有限维复表示；`@@M@@X@@` 不是 Campana 意义下的特殊（special）簇；`@@M@@\widetilde X@@` 不双全纯同构于射影簇的半代数（semialgebraic）开子集。

## 证明思路

构造从带 48 个运动穿孔的球面族开始：在带三阶自同构的椭圆曲线上作乘 4 映射，穿孔在某个参数值附近成 24 对碰撞；二次底变换加每次碰撞一个爆破，得到特异纤维——无标记的主球面挂 24 条尾巴、每条尾巴带两个标记点。难题是填满所有缺失纤维后仍保住无穷的基本群像，作者用三件互相咬合的工具。其一是加权 Golod–Shafarevich 判据：在 pro-2 群的 Magnus 展开里，用 `@@M@@(\Z/4)^2@@` 平移群的逐次差分 `@@M@@\delta_{T_1}^i\delta_{T_2}^\ell(a_{0,j})@@`（赋权 `@@M@@i+\ell+1@@`）造出加权自由基，使符号对合 `@@M@@\sigma@@` 只需 24 条度数 `@@M@@\ge w_g+1@@` 的关系就能在 48 元自由群上强加，而生成元多项式与关系多项式恰满足 `@@M@@P(t)=(1+t)G(t)@@`——对合几乎免费。其二是深层单调控制：取符号商之前，先用三个显式二重复叠证明参数群的单调（monodromy）只在更高权处改动生成元，于是深度 `@@M@@N@@` 的单调关系至多 `@@M@@4^N@@` 条、每条代价仅 `@@M@@t^{N+1}@@`，总代价可压到 `@@M@@1/100@@` 以下；紧化后剩下的有限个边界子午圈（meridian）用 `@@M@@2^e@@` 次幂杀死，再压 `@@M@@1/100@@`。在 `@@M@@t=49/200@@` 处验证 `@@M@@1-G(t)+1/50<-1/125<0@@`，加权判据说商群 `@@M@@Q@@` 无限。其三是有限局部检测与转移，顺序至关重要：先深层单调，再取有限参数覆盖并紧化，最后才加边界幂。取一个在每个局部边界余群整像上都单射的有限商，其对应覆盖经正规化与解消（SGA1 黎曼存在定理、强解消定理）延拓为光滑射影曲面 `@@M@@X@@`，且同态下降到 `@@M@@\pi_1(X)@@`。特异纤维保持有理：主球面上的分量是 1 次球面，尾巴上的分量是 `@@M@@\C^*@@` 上 `@@M@@z\mapsto z^d@@` 型覆盖的紧化 `@@M@@\PP^1@@`；提升后的交点图未必是树，van Kampen 把 `@@M@@\pi_1(Z_0)@@` 等同于对偶图的基本群——曲线虽由单连通分量组成，其节点并仍可拥有非平凡基本群。最后，穿孔光滑纤维在 `@@M@@Q@@` 中的像稠密故无限；经 Łojasiewicz 三角剖分给出的半解析形变收缩邻域与映射真性，把无穷像转移到特异纤维的一个连通分量 `@@M@@Z_0@@` 上，套用有理包引理即得定理。

## 可信度与备注

本篇主结果暂无形式化证明，构造涉及加权 pro-2 群、曲线族几何与曲面解消的大量精细计算，请以社区核验为准。它与同族 046 的姊妹篇互相支撑：本篇在维数二否定无限制的全纯凸性，姊妹篇（大基本群四维簇）在大基本群前提下否定 Stein 性，分别以"无穷 Nori 弦"与"秩三维格覆盖"为障碍，从两侧夹击同一猜想。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
