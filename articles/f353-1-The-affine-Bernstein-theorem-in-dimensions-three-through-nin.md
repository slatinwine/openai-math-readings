---
layout: default
title: "The affine Bernstein theorem in dimensions three through nine"
family: "353"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The affine Bernstein theorem in dimensions three through nine

> 结果族 353：Affine Bernstein rigidity through dimension nine and a smooth dimension-ten counterexample　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象家里有一口无限大的炒锅，碗面永远是 `@@M@@y=x^2@@` 那种抛物形。这篇论文证明了一件很"霸道"的事：在 3 到 9 维空间里，凡是满足某个特殊"最优化方程"、又能无限延伸下去的光滑凸曲面（凸函数的图像），最后只能是这种锅——换花样的可能性为零。

**关键词卡片**

- 仿射极值方程（affine maximal equation）：刻画"在仿射几何意义下最均衡"的偏微分方程，是本文曲面的"身份证"。
- 椭圆抛物面（elliptic paraboloid）：`@@M@@u=\tfrac12 x^{\mathsf T}Ax@@`（`@@M@@A@@` 正定）的图像，即那口无限大的碗。
- 欧氏完备（Euclidean complete）：用曲面自身诱导的距离去量，能一直走下去而不碰边缘。
- 局部一致凸（locally uniformly convex）：每个局部都严格向外鼓，不许有平坦片段。
- 维数 3–9：结论成立的范围；证明里一个行列式 `@@M@@\tfrac{(n-2)(10-n)}{16}@@` 恰在此范围为正，第 10 维归零——姊妹篇恰在十维造出反例。

**看个具体例子**

定理代入最简单情形：若 `@@M@@u@@` 的 Hessian 正定、解仿射极值方程，且诱导度量 `@@M@@g_{ij}=\delta_{ij}+u_i u_j@@` 完备，则必为 `@@M@@u=\tfrac12 x^{\mathsf T}Ax+b\cdot x+c@@`。画出来：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<line x1="100" y1="240" x2="520" y2="240" stroke="#555" stroke-width="2"/>
<line x1="100" y1="40" x2="100" y2="252" stroke="#555" stroke-width="2"/>
<text x="524" y="254" font-size="16">x</text>
<text x="76" y="46" font-size="16">u</text>
<polyline points="140,90 160,130 180,164 200,186 220,212 240,228 260,237 280,240 300,237 320,228 340,212 360,186 380,164 400,130 420,90" fill="none" stroke="#1a6" stroke-width="3"/>
<polyline points="150,235 190,234 230,231 270,224 310,212 350,192 390,160 418,116" fill="none" stroke="#e33" stroke-width="2" stroke-dasharray="7 5"/>
<text x="240" y="70" font-size="15" fill="#1a6">碗 u=½xᵀAx：定理的唯一幸存者</text>
<text x="150" y="150" font-size="15" fill="#e33">别的凸解</text>
<text x="424" y="112" font-size="19" fill="#e33">×</text>
</svg>

</div>

红色虚线那样的其他凸曲面，只要同时占住"解方程 + 度量完备"两条，就被判定不可能存在。

**为什么值得关心**

它把 Trudinger–Wang 的二维定理一路推广到 3 至 9 维，补齐高维仿射 Bernstein 问题的最后拼图；而证明恰好失效的第 10 维正是反例所在——可行与不可行严丝合缝。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
论文证明当 `@@M@@3\le n\le9@@` 时，诱导欧氏度量完备的光滑局部一致凸仿射极值图必为椭圆抛物面——定义域必是全空间、函数必是正定二次多项式；仿射完备 (affine-complete) 的经典仿射极大浸入超曲面亦得同样结论。配合姊妹篇的十维反例，范围恰好封闭。

## 问题背景
仿射 Bernstein 问题问：完备的局部一致凸 (locally uniformly convex) 仿射极大超曲面是否必为椭圆抛物面 (elliptic paraboloid)？"完备"在此有两种不等价的含义——图从欧氏空间诱导的度量完备，与仿射 Berwald–Blaschke 度量完备；Trudinger 与 Wang 证明仿射完备蕴含欧氏完备，反之不然。Chern 1979 年提出二维整图问题，Calabi 1982 年在双完备假设下证明二维刚性，Trudinger–Wang 2000 年去掉仿射完备性证得欧氏完备的二维定理。他们的高维路线（内估计加截面重标度）本对任意维数有效，唯独缺一块拼图：图与切平面分离的一致严格凸性模 (modulus of strict convexity) 在归一化下保持一致——二维靠凸极限与接触集的细致分析获得，高维一直无人补齐。本篇在不加任何增长或积分条件下补上这一环。

## 主要结果
主定理：设 `@@M@@3\le n\le9@@`，`@@M@@\Omega\subset\R^n@@` 非空凸开，`@@M@@u\in C^\infty(\Omega)@@` 的 Hessian 正定且解仿射极值方程 `@@M@@U^{ij}w_{ij}=0@@`（`@@M@@U^{ij}=\det(D^2u)(D^2u)^{-1}_{ij}@@`，`@@M@@w=(\det D^2u)^{-(n+1)/(n+2)}@@`）。若图关于诱导欧氏度量 `@@M@@g_{ij}=\delta_{ij}+u_iu_j@@` 完备，则 `@@M@@\Omega=\R^n@@` 且 `@@M@@u(x)=\tfrac12x^{\mathsf T}Ax+b\cdot x+c@@`，`@@M@@A@@` 正定，即标准椭圆抛物面的可逆仿射像。论文明确指出这涵盖整图断言，且不设增长条件、不断言仿射度量完备。推论：`@@M@@3\le n\le9@@` 时，连通、开（非紧无边界）、仿射完备、经典仿射极大的局部一致凸浸入超曲面也是椭圆抛物面的可逆仿射像。

## 证明思路
证明分三段。先做纯几何：欧氏完备迫使 `@@M@@u@@` 在有限边界点处趋于 `@@M@@+\infty@@`，上境图 (epigraph) 的每个"帽子"（切平面以下的截体）都紧。对上境图全体可逆仿射像取局部极限，定义具 `@@M@@k@@` 个非负方向 `@@M@@s_i\ge0@@` 的"`@@M@@k@@`-模型"，其横截纤维 `@@M@@K_s@@` 紧；取方向数 `@@M@@k@@` 达最大的模型。若纤维无一致居中 `@@M@@-K_s\subset C_*K_s@@`，则用 John 椭球 (John's ellipsoid) 归一化一列愈发不对称的纤维，其极限纤维以原点为边界点，再经一次"薄切片"仿射重标度即可造出 `@@M@@(k+1)@@`-模型，与最大性矛盾——故居中必一致。再排除 `@@M@@k\ge2@@`，此处才真正用到方程：在纤维的支撑函数 (support function) 坐标下，平稳性化为对数坐标中的加权积分恒等式；将两个恒等式按参数 `@@M@@\lambda@@` 组合后，剩余二次型的 `@@M@@2\times2@@` 矩阵行列式在 `@@M@@\lambda=1@@` 时等于 `@@M@@(n-2)(10-n)/16@@`，恰在 `@@M@@3\le n\le9@@` 上为正（固定 `@@M@@\lambda=15/16@@` 可行）——这是维度限制唯一进入的地方。强制性给出对数测度 `@@M@@\sigma@@` 的指数增长不等式；另一面，`@@M@@(\det D^2g)^{n/(n+2)}@@` 的凹性配合平稳性经局部凸扰动比较给出帽子面积的一致正下界，帽子恒等式 (cap identity) 控制逆 Hessian 加权积分，Hessian 子式估计加 Hölder 插值给出每个对数胞腔的一致质量上界，合计只允许多项式增长 `@@M@@\sigma(Q_L)\le C(L+1)^k@@`。指数与多项式矛盾，故最大方向数 `@@M@@k=1@@`。最后刚性收尾：`@@M@@k=1@@` 等价于所有切截面 (tangent section) 有统一平衡 `@@M@@-\rho K_a(t)\subset K_a(t)@@`，对一切基点与高度一致；沿射线迭代得倍增估计 `@@M@@g(\beta r)\le Ag(r)@@`，迫使每条射线可无限延伸，故 `@@M@@\Omega=\R^n@@`。归一化后的截面族共享一个严格凸性模，套用 Trudinger–Wang 对维数不变的内估计 (interior estimates) 得 `@@M@@|D^3v_t(0)|\le C_0@@`，换回原坐标得 `@@M@@|D^3u(0)|\le Ct^{-1/2}\to0@@`；基点任意，故 `@@M@@D^3u\equiv0@@`，`@@M@@u@@` 是正定二次多项式。

## 可信度与备注
主结果未形式化，请以社区核验为准。强制性行列式 `@@M@@(n-2)(10-n)/16@@` 在 `@@M@@n=10@@` 恰好归零，与姊妹篇在该维构造的光滑非二次整图精确互补：方法失效的临界点正是反例所在，故"三至九维"在当前框架下不可再加强。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
