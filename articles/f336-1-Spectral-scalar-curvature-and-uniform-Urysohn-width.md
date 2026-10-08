---
layout: default
title: "Spectral scalar curvature and uniform Urysohn width"
family: "336"
discipline: "Differential geometry"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Spectral scalar curvature and uniform Urysohn width

> 结果族 336：Spectral scalar curvature, Urysohn width, and macroscopic dimension　·　学科：Differential geometry　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一个处处鼓胀的空间，从很远的地方看会"矮掉两维"——就像一根粗绳子远看只是一条线。Gromov 猜想：正标量曲率的 `@@M@@n@@` 维空间一定能整体连续地压到 `@@M@@n-2@@` 维骨架上，且被压到同一点的原材料不超过固定长度。姊妹篇已在"每点曲率都正"时证明此结论；本文把它推广到宽松得多的"谱条件"——允许局部凹陷，只要能量加权的整体为正。

**关键词卡片**

- 标量曲率（scalar curvature）：每一点的平均弯曲度，正像球面外鼓
- 谱条件（spectral condition）`@@M@@-4\Delta+\mathrm{Scal}\ge1@@`：曲率与测试函数的能量加权平均后为正——局部可以取负值
- Urysohn 宽度（Urysohn width）：把空间连续压到低维骨架时，能保证的纤维直径的最小值
- 纤维（fiber）：映射送到同一处的全部点，含所有连通分支
- 宏观维度（macroscopic dimension）：空间在大尺度上"有效"的维数

**看个具体例子**

定理数字版：`@@M@@n\ge4@@` 且谱下界为 `@@M@@\lambda@@` 时，存在到 `@@M@@n-2@@` 维复形的连续映射，整根纤维直径 `@@M@@\le C_n/\sqrt\lambda@@`，按原尺度量。代入 `@@M@@n=4@@`：四维空间宏观上塌成二维骨架；若 `@@M@@\lambda=\tfrac14@@`，纤维界放大为 `@@M@@2C_n@@`。逐点条件 `@@M@@\mathrm{Scal}\ge\lambda@@` 只是特例——谱条件严格更弱。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="20" y="35" font-size="16" fill="#333">n 维空间 → n−2 维骨架</text>
<ellipse cx="150" cy="140" rx="95" ry="70" fill="none" stroke="#333" stroke-width="2"/>
<path d="M 120,74 Q 150,115 180,74" fill="none" stroke="#c33" stroke-width="4"/>
<path d="M 236,110 Q 195,140 236,170" fill="none" stroke="#c33" stroke-width="4"/>
<text x="55" y="240" font-size="14" fill="#333">n 维完备流形</text>
<text x="55" y="262" font-size="13" fill="#c33">红色凹陷：局部负曲率也允许</text>
<line x1="255" y1="140" x2="315" y2="140" stroke="#333" stroke-width="2"/>
<polygon points="327,140 315,134 315,146" fill="#333"/>
<text x="258" y="128" font-size="13" fill="#333">连续映射</text>
<line x1="370" y1="90" x2="470" y2="130" stroke="#345" stroke-width="2"/>
<line x1="370" y1="90" x2="430" y2="180" stroke="#345" stroke-width="2"/>
<line x1="470" y1="130" x2="430" y2="180" stroke="#345" stroke-width="2"/>
<line x1="470" y1="130" x2="520" y2="80" stroke="#345" stroke-width="2"/>
<line x1="430" y1="180" x2="520" y2="210" stroke="#345" stroke-width="2"/>
<circle cx="370" cy="90" r="5" fill="#345"/>
<circle cx="470" cy="130" r="5" fill="#345"/>
<circle cx="430" cy="180" r="5" fill="#345"/>
<circle cx="520" cy="80" r="5" fill="#345"/>
<circle cx="520" cy="210" r="5" fill="#345"/>
<text x="395" y="245" font-size="14" fill="#333">n−2 维骨架</text>
<text x="335" y="268" font-size="13" fill="#555">整根纤维直径 ≤ Cₙ（原尺度）</text>
</svg>

</div>

**为什么值得关心**

曲率信号从"逐点"放宽到"谱"，正曲率的空间坍缩现象仍然成立；定理不需要定向、spin、紧性或"有界几何"假设，紧与非紧流形一并适用。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对每个 `@@M@@n\ge4@@` 证明了：满足谱型标量曲率不等式 `@@M@@-4\Delta+\mathrm{Scal}\ge1@@` 的完备无边 `@@M@@n@@` 维流形都可连续映射到 `@@M@@n-2@@` 维单纯复形，且整根纤维的直径被仅依赖 `@@M@@n@@` 的常数控制——把 Gromov 的均匀 Urysohn 宽度结论从逐点曲率条件推广到了谱条件。

## 问题背景

正标量曲率（positive scalar curvature）应当迫使流形在受控尺度上坍缩掉两个维度，这是 Gromov 自 1986 年起倡导的宏观维度（macroscopic dimension）纲领的量化猜想：`@@M@@\mathrm{Scal}\ge1@@` 的完备流形应可连续映到 `@@M@@n-2@@` 维多面体，且整根纤维的直径有只依赖 `@@M@@n@@` 的上界。同族姊妹篇已在逐点假设下证明该结论。谱条件 `@@M@@-4\Delta+\mathrm{Scal}\ge1@@`（二次型意义）允许标量曲率在部分区域取负值，只要求它与测试函数的能量加权后整体为正；系数 `@@M@@4@@` 与 Perelman 的 `@@M@@\mathcal F@@`-泛函、Gromov 的环面稳定化（torus stabilization）理论天然相合，Hirsch–Kazaras–Khuri–Zhang 的谱带不等式也属此类条件。此前的宽度结论多需紧性或拓扑假设（如 Chodosh–Li–Liokumovich 在四、五维对万有覆盖的定性结果），而谱条件的新困难在于：它只提供一个正上解，对其取值与振荡没有任何控制。

## 主要结果

主定理：对每个整数 `@@M@@n\ge4@@` 存在有限常数 `@@M@@C_n@@`，使得任一满足

`@@M@@D\int_M\bigl(4|\nabla_g\phi|_g^2+\mathrm{Scal}_g\phi^2\bigr)\,\mathrm{dvol}_g\ge\int_M\phi^2\,\mathrm{dvol}_g\qquad(\phi\in C_c^\infty(M;\mathbb R))@@`

的连通完备无边光滑黎曼 `@@M@@n@@`-流形 `@@M@@(M,g)@@`，都存在到维数至多 `@@M@@n-2@@` 的单纯复形的连续映射 `@@M@@f@@`，使整根纤维（fiber，含全部连通分支）满足 `@@M@@\diam_g f^{-1}(y)\le C_n@@`，即 Urysohn `@@M@@(n-2)@@`-宽度（Urysohn width）`@@M@@\UW_{n-2}(M,g)\le C_n@@`。若谱下界为 `@@M@@\lambda>0@@`，纤维界为 `@@M@@C_n/\sqrt\lambda@@`。逐点条件 `@@M@@\mathrm{Scal}\ge\lambda@@` 蕴含谱条件，反之不然，故这是严格推广；定理不需定向、spin、有界几何假设，紧与非紧流形一并适用。

## 证明思路

整体策略是：把谱条件转化为姊妹篇分区定理（论文中作为已知结果引入）所需的输入——一个稳定化标量曲率有下界、且诸集合对充分分离的放大度量 `@@M@@h\ge g@@`，全程不对权重做任何全局控制。

先做"从谱到权"的转换：由 Allegretto–Piepenbrink 理论的穷竭列论证得到正光滑函数 `@@M@@v@@` 满足 `@@M@@-4\Delta_g v+\mathrm{Scal}_g v\ge v@@`；令 `@@M@@w=-2\log v@@`，则加权漂移表达式 `@@M@@\mathcal D(g,w)=\mathrm{Scal}+2\Delta w-|dw|^2\ge1@@`。但 `@@M@@w@@` 可以无界，而后续拉伸构造需要随漂移平方增长的"储备"。第一个新构造（二次储备命题）补上缺口：在乘积 `@@M@@(M,h)\times\mathbb R@@` 中解规定平均曲率（prescribed mean curvature）的图方程，压力取 `@@M@@p=10(u-w)@@`，即正比于图高与目标函数之差；先经图角度方程的极值原理、紧流形上的连续法，再在非紧情形用极坐标闸函数与对角序列，得到整体光滑解。标量比较引理把放大度量的曲率增益写成水平集几何量的平方和，配方后即得 `@@M@@\mathcal D(h^+,t^+)\ge\mathcal D(h,w)+(t^+)^2-C(n)@@`，其中 `@@M@@C(n)=100n+203@@` 只依赖维数——压力的平方恰好覆盖新漂移的平方。

第二个新构造是带符号的压力律 `@@M@@F(x,t)@@`：不直接造 `@@M@@F@@` 而是反解其反函数，用"磨光最大值"构造辅助函数，使 `@@M@@F_x\ge A_0N(t)@@`（其中 `@@M@@N(t)=\sqrt{t^2+T^2}@@`），并在两个区域分别满足 `@@M@@F_x\le b_0N(t)^2@@` 或 `@@M@@-FF_t\ge P_0F_x@@` 的二择一。局部拉伸引理据此在紧支撑内把集合对的距离放大 `@@M@@1.004@@` 倍，曲率损失由固定背景度量的迹（trace）下降与任意小的可和误差支付；由于储备只取正部 `@@M@@(V(t')-V(t))_+@@`，漂移变号时估计也不失效。

最后组装：取极大 `@@M@@D@@`-分离中心网，逐轮拉伸并在每轮后更换工作尺度以恢复储备，极限给出 `@@M@@\mathcal D(h,t)\ge1/2@@` 且诸分离达标；再用单位分解把 `@@M@@-t@@` 分解为局部有限的对数翘曲（log warp）并细分使梯度平方和 `@@M@@\le1/10@@`，多翘曲公式把稳定化标量曲率抬到 `@@M@@2/5@@`。于是分区定理的全部假设成立，其输出映射的整根纤维在原度量 `@@M@@g@@` 下至多 `@@M@@4D+2@@`。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准；按 OpenAI 官方声明，未经形式化的结果可能有问题。论文的拓扑坍缩部分（分区定理）整体引自同族姊妹篇《Positive scalar curvature and uniform codimension-two width》，本文的新贡献集中于两处分析构造：二次储备命题与带符号压力律的拉伸估计。另一姊妹篇以加权极小曲面方法处理 `@@M@@n=3@@`，三篇合并覆盖 `@@M@@n\ge3@@` 的完整谱宽度结论。

{% endraw %}
