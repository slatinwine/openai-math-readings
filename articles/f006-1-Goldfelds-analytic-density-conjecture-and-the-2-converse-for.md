---
layout: default
title: "Goldfeld's analytic density conjecture and the 2-converse for elliptic curves"
family: "006"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Goldfeld's analytic density conjecture and the 2-converse for elliptic curves

> 结果族 006：Goldfeld's conjecture: densities and mean analytic rank　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

每条椭圆曲线都有一大群"表亲"：取一个无平方因子整数 `@@M@@d@@`，对曲线做二次扭曲，就得到表亲 `@@M@@E^{(d)}@@`，而每条表亲头顶挂着一个数——"秩"，粗略衡量它有多少个独立的有理点。Goldfeld 在 1979 年猜测：这群表亲的秩分布像抛硬币，秩 0 与秩 1 各占一半。本文证明了这个猜想，而且更进一步：只要一个能实际算出来的代数量（Selmer 余秩）取 0 或 1，那么"解析仪表"与"代数仪表"的读数必然一致，连著名的 BSD 猜想都不需要预先假设。

**关键词卡片**

- 椭圆曲线（elliptic curve）：形如 `@@M@@y^2=x^3+ax+b@@` 的三次曲线，有理点可定义加法构成群，是数论主角。
- 二次扭曲（quadratic twist）：以无平方因子整数 `@@M@@d@@` 为参数得到的"表亲曲线" `@@M@@E^{(d)}@@`。
- 解析秩（analytic rank）：`@@M@@L@@` 函数在 `@@M@@s=1@@` 处零点的阶数 `@@M@@a(E)@@`，像一台解析仪表的读数。
- Selmer 余秩（Selmer corank）：可用有限次 2-descent 实际计算的代数量；本文证明它为 0 或 1 时就锁死一切。
- BSD 猜想（BSD conjecture）：断言解析秩等于有理点群的秩；本文不假设它，却证得等式成立且 `@@M@@\Sha@@` 有限。

**看个具体例子**

把 `@@M@@0<|d|\le X@@` 的无平方因子整数排成一列，每个 `@@M@@d@@` 对应一条表亲曲线。定理断言（`@@M@@a@@` 为解析秩）：

`@@M@@D\frac{\#\{d:\,a(E^{(d)})=0\}}{\#\mathcal D(X)}\to\frac12,\qquad \frac{\#\{d:\,a(E^{(d)})=1\}}{\#\mathcal D(X)}\to\frac12 .@@`

画成图就是两根一样高的柱子，秩 `@@M@@\ge2@@` 的柱子高度趋零：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><line x1="70" y1="230" x2="520" y2="230" stroke="#333" stroke-width="2"/><line x1="70" y1="230" x2="70" y2="50" stroke="#333" stroke-width="2"/><rect x="120" y="80" width="110" height="150" fill="none" stroke="#2a9d4f" stroke-width="3"/><rect x="300" y="80" width="110" height="150" fill="none" stroke="#d64545" stroke-width="3"/><rect x="470" y="222" width="36" height="8" fill="#888"/><text x="175" y="255" font-size="18" text-anchor="middle" fill="#222">秩 0</text><text x="355" y="255" font-size="18" text-anchor="middle" fill="#222">秩 1</text><text x="488" y="255" font-size="15" text-anchor="middle" fill="#222">秩 ≥ 2</text><text x="175" y="70" font-size="16" text-anchor="middle" fill="#2a9d4f">密度 → 1/2</text><text x="355" y="70" font-size="16" text-anchor="middle" fill="#d64545">密度 → 1/2</text><text x="488" y="212" font-size="14" text-anchor="middle" fill="#666">→ 0</text><text x="42" y="150" font-size="15" text-anchor="middle" fill="#222" transform="rotate(-90 42 150)">占比</text><text x="295" y="30" font-size="16" text-anchor="middle" fill="#222">二次扭曲族中解析秩的占比（示意）</text></svg>

</div>

**为什么值得关心**

它把"椭圆曲线的秩统计学"从猜想变成定理，并首次在不假设 BSD 的前提下，从可计算的 Selmer 数据反推出解析结论，补上了 `@@M@@p=2@@` 一侧的长期空白。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对 `@@M@@\mathbb{Q}@@` 上任意椭圆曲线 `@@M@@E@@`，本文证明 Goldfeld 解析密度猜想：二次扭曲中解析秩 0 与 1 各占密度 `@@M@@1/2@@`；并证明低余秩 2-逆定理：`@@M@@2^\infty@@`-Selmer 余秩为 0 或 1 时它就等于解析秩与 Mordell–Weil 秩且 `@@M@@\Sha@@` 有限，全程不假设 BSD。

## 问题背景

设 `@@M@@E/\mathbb{Q}@@` 为椭圆曲线，`@@M@@a(E)=\operatorname{ord}_{s=1}L(E,s)@@` 为解析秩，`@@M@@r(E)@@` 为有理点群 `@@M@@E(\mathbb{Q})@@` 的秩。BSD 猜想断言二者相等，并预测 Tate–Shafarevich 群（Tate–Shafarevich group）`@@M@@\Sha(E/\mathbb{Q})@@` 有限。Goldfeld 在 1979 年进一步提出：在 `@@M@@E@@` 的二次扭曲（quadratic twist）族 `@@M@@\{E^{(d)}\}@@` 中，解析秩的平均应趋于 `@@M@@1/2@@`，等价说法是秩 0 与秩 1 各占一半（其原始形式按二次域判别式参数化，本文采用带符号无平方因子参数按绝对值排序的约定）。Gross–Zagier 与 Kolyvagin 的经典工作给出"正方向"：`@@M@@a(E)\le 1@@` 时秩相等、`@@M@@\Sha@@` 有限；但反方向——从 Selmer 群（Selmer group）信息推出解析非消失——此前只在好普通素数、剩余表示不可约等条件下有结果（Skinner–Urban、Skinner、Wei Zhang、Burungale–Castella–Skinner 等，且基本不覆盖 `@@M@@p=2@@`）。密度方面，James、Vatsal（`@@M@@X_0(19)@@`）、Kriz–Li（有理 3-同源曲线）等只在特殊族得到正比例，一般曲线连正比例都未知。Smith 2025 证明了对每条有理椭圆曲线 `@@M@@2^\infty@@`-Selmer 余秩 0 与 1 各占密度 `@@M@@1/2@@`，但其解析推论需要假设 BSD——本文补上的正是从 Selmer 统计到解析结论这一缺失环节。

## 主要结果

**定理 A（低余秩 2-逆定理）**：若 `@@M@@c_2(E)=\operatorname{corank}_{\mathbb{Z}_2}\Sel_{2^\infty}(E/\mathbb{Q})\in\{0,1\}@@`，则
`@@M@@Da(E)=r(E)=c_2(E),\qquad \Sha(E/\mathbb{Q})\ \text{有限}.@@`
对约化类型、复乘、有理挠点与有理同源均无任何限制。

**定理 B（Goldfeld 解析密度猜想）**：对每条 `@@M@@E/\mathbb{Q}@@` 与 `@@M@@j\in\{0,1\}@@`，
`@@M@@D\lim_{X\to\infty}\frac{\#\{d\in\mathcal{D}(X):a(E^{(d)})=j\}}{\#\mathcal{D}(X)}=\frac12,@@`
其中 `@@M@@\mathcal{D}(X)@@` 是 `@@M@@0<|d|\le X@@` 的无平方因子整数，正负参数合起来按绝对值计数。由此解析秩 `@@M@@\ge 2@@` 的扭曲密度为零；且对密度 1 的参数 `@@M@@d@@`，`@@M@@E^{(d)}@@` 的解析秩与代数秩相等、整个 `@@M@@\Sha@@` 有限。

**推论（有限判据）**：若 `@@M@@d_2(E)=\dim_{\mathbb{F}_2}\Sel_2(E/\mathbb{Q})-\dim_{\mathbb{F}_2}E(\mathbb{Q})[2]\in\{0,1\}@@`，则一次有限 2-descent 即可同时认证解析秩与整个 `@@M@@2@@`-部分 `@@M@@\Sha@@` 的消失；其证明用交错 Cassels–Tate 配对（Cassels–Tate pairing）从 `@@M@@d_2@@` 过渡到完整余秩。

## 证明思路

论文的主体是逐点逆定理（定理 A）；定理 B 由它与 Smith 的余秩分布复合而得。固定 `@@M@@E@@`，作者构造有限的"二元立方族"扭曲参数
`@@M@@Dh_x=\prod_{q\in\mathcal{Q}}(q^*)^{\lambda_q(x)},\qquad q^*=(-1/q)\,q,\qquad x\in\mathbb{F}_2^b,@@`
其中 `@@M@@\mathcal{Q}@@` 是一组互异的好奇素数，`@@M@@\lambda_q@@` 为线性型，`@@M@@x=0@@` 处参数为 `@@M@@1@@`，且所有顶点在每个固定坏位置有相同的局部扭曲类。目标是让每个非零顶点的解析阶恰为 `@@M@@c_2(E)@@`，并配一个标量"行列式坐标"：它在这些顶点处有非零的中心特殊化、且 `@@M@@2@@`-adic 赋值一致有界；最后用有界整插值把非消失传回缺失的顶点 `@@M@@0@@`，即曲线 `@@M@@E@@` 本身。

插值类按余秩分两种。`@@M@@c_2=0@@` 时用 Beilinson–Kato 类，其中心特殊化探测 `@@M@@L(E,1)@@`；工具是 `@@M@@\mathbb{Q}@@` 的实分圆 `@@M@@\mathbb{Z}_2@@`-扩张上的 Iwasawa 上同调，其中"正复形"挖去实上链但保留连通映射给出的不变线，再与 Kato 的 zeta 类合成行列式坐标。`@@M@@c_2=1@@` 时用虚二次域 `@@M@@K=\mathbb{Q}(\sqrt{k})@@` 上的 Heegner 类，其高度探测导数 `@@M@@[L(E,s)L(E^{(k)},s)]'_{s=1}@@`（依赖环类的显式 Gross–Zagier 公式）；先选定解析非消失的伴侣 `@@M@@E^{(k)}@@`，使 `@@M@@K@@` 上的 Selmer 余秩恰为 `@@M@@1@@`，并在 `@@M@@2@@` 与所有坏素数处保持整 Kummer 条件。

真正的难点在于构造这些族。偶符号系数由 Waldspurger 公式给出，奇符号由 genus Heegner 和的约化给出加权三元 theta 系数；先证一致下界，再取"最小正规赋值"完成归一化，权 `@@M@@2@@` 的 Hecke 迹把这些系数检测转化为素数有限组态上的收缩与删除规则。剩余表示 `@@M@@E[2]@@` 分两种穷举情形处理。可约时（即有有理 2-挠点），用图（graph）编码辅助素数之间规定的二次剩余符号，使两个独立的系数检测在每个非零顶点同时取单位值，奇情形先把伴侣域固定、再让维数增长。不可约时，局部 Selmer 方程给出 `@@M@@\mathbb{F}_2@@` 上的矩阵，减去由有限局部类型确定的修正项后矩阵变为对称，其零化度给出 Selmer 维数的下界；把组态分块并令块间矩阵为零，则一个非零系数检测即可界定矩阵核、从而界定奇异块的个数。取奇异块数极大的组态，经 Ramsey 型"饱和论证"在每个非零二元顶点安排出单位检测；一条交错矩阵修补引理（证明形如 `@@M@@\begin{psmallmatrix}D&N\\N&N+H\end{psmallmatrix}@@` 的分块矩阵可逆）再给出素数个数与 Selmer 长度一致有界的伴侣 `@@M@@k@@`。此外，整插值代数通过一个有界复形清除分母，使所需同余精度与新素数个数无关。最后，密度定理由逐点逆定理与 Smith 2025 的余秩分布复合，并处理从整数参数到无平方因子参数的过渡。

## 可信度与备注

本文为 OpenAI 手稿，主结果暂无形式化证明；按官方声明，未经形式化的结果可能有问题，请以社区核验为准。族内姊妹篇互相支撑：另一篇平均解析秩论文证明密度零的高秩尾巴不拖累秩加权平均，与本文合成平均解析秩 `@@M@@1/2@@`；后续的全素数 `@@M@@p@@` 推广与 `@@M@@2@@`-部分 BSD 精确公式两篇均以本文的逆定理与密度结论为输入。证明依赖大量一致 `@@M@@2@@`-adic 估计与超滤取极限的构造，技术性极强，独立核验尚需时间。

{% endraw %}
