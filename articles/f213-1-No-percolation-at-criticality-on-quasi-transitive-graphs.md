---
layout: default
title: "No percolation at criticality on quasi-transitive graphs"
family: "213"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | No percolation at criticality on quasi-transitive graphs

> 结果族 213：Critical percolation on every quasi-transitive graph　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把方格渔网换成蜂窝网、无限家谱树，或任何"从对称性看只有有限种顶点"的规则无限网络，"临界点处有没有无穷连通块"这个问题依然可以问。本文证明：只要 p_c<1，答案统一是"没有"。这正是 Benjamini 与 Schramm 在 1996 年提出的临界性猜想的键渗流版本。

**关键词卡片**

- 拟传递图（quasi-transitive graph）：图的对称性把顶点分成有限多类，方格网、蜂窝网、Cayley 图都算。
- 临界性猜想：p_c<1 的拟传递图在 p_c 处没有无穷开簇。
- Cayley 图：用群和生成元集画出的规则网络。
- 次指数增长：球体积涨得比任何指数都慢的图，是此前所有方法都够不着的最后空白。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="40" font-size="14" text-anchor="middle" fill="#222">对一大类『规则无限网络』都成立</text>
  <line x1="65" y1="95" x2="135" y2="95" stroke="#333" stroke-width="1.5"/>
  <line x1="65" y1="130" x2="135" y2="130" stroke="#333" stroke-width="1.5"/>
  <line x1="65" y1="165" x2="135" y2="165" stroke="#333" stroke-width="1.5"/>
  <line x1="65" y1="95" x2="65" y2="165" stroke="#333" stroke-width="1.5"/>
  <line x1="100" y1="95" x2="100" y2="165" stroke="#333" stroke-width="1.5"/>
  <line x1="135" y1="95" x2="135" y2="165" stroke="#333" stroke-width="1.5"/>
  <circle cx="65" cy="95" r="2.5" fill="#333"/>
  <circle cx="100" cy="95" r="2.5" fill="#333"/>
  <circle cx="135" cy="95" r="2.5" fill="#333"/>
  <circle cx="65" cy="130" r="2.5" fill="#333"/>
  <circle cx="100" cy="130" r="2.5" fill="#333"/>
  <circle cx="135" cy="130" r="2.5" fill="#333"/>
  <circle cx="65" cy="165" r="2.5" fill="#333"/>
  <circle cx="100" cy="165" r="2.5" fill="#333"/>
  <circle cx="135" cy="165" r="2.5" fill="#333"/>
  <path d="M 280 96 L 309.4 113 L 309.4 147 L 280 164 L 250.6 147 L 250.6 113 Z" fill="none" stroke="#333" stroke-width="1.8"/>
  <line x1="309.4" y1="113" x2="338" y2="113" stroke="#333" stroke-width="1.8"/>
  <line x1="250.6" y1="147" x2="222" y2="147" stroke="#333" stroke-width="1.8"/>
  <line x1="280" y1="164" x2="280" y2="193" stroke="#333" stroke-width="1.8"/>
  <circle cx="280" cy="96" r="2.5" fill="#333"/>
  <circle cx="309.4" cy="147" r="2.5" fill="#333"/>
  <circle cx="250.6" cy="147" r="2.5" fill="#333"/>
  <line x1="460" y1="175" x2="425" y2="130" stroke="#333" stroke-width="1.8"/>
  <line x1="460" y1="175" x2="495" y2="130" stroke="#333" stroke-width="1.8"/>
  <line x1="425" y1="130" x2="405" y2="90" stroke="#333" stroke-width="1.8"/>
  <line x1="425" y1="130" x2="445" y2="90" stroke="#333" stroke-width="1.8"/>
  <line x1="495" y1="130" x2="475" y2="90" stroke="#333" stroke-width="1.8"/>
  <line x1="495" y1="130" x2="515" y2="90" stroke="#333" stroke-width="1.8"/>
  <circle cx="460" cy="175" r="3" fill="#333"/>
  <text x="100" y="218" font-size="13" text-anchor="middle" fill="#333">方格网 ℤ^d</text>
  <text x="280" y="218" font-size="13" text-anchor="middle" fill="#333">蜂窝网</text>
  <text x="460" y="218" font-size="13" text-anchor="middle" fill="#333">无限树</text>
  <text x="280" y="252" font-size="13" text-anchor="middle" fill="#222">只要『拟传递』且 p_c &lt; 1，临界处都没有无穷开簇</text>
</svg>

</div>

定理一句话：`@@M@@\mathbb{P}_{p_c}(\text{存在无穷开簇})=0@@`。特别地，把图取为 `@@M@@\mathbb{Z}^d@@`（一切 `@@M@@d\ge 2@@`），就免费得到所有方格网的临界熄灭。注意条件 `@@M@@p_c<1@@` 不可省略：p=1 时整张图全开，"无穷簇"当然存在。

**为什么值得关心**

它把渗流临界理论从"逐个图攻坚"升级为"一类图通吃"：指数增长的图 2016 年已解决，此次攻下的是剩下的次指数增长、又无平面几何与花边展开可用的图类。证明按体积增长速度分成两种情形：增长快于一切幂次的走纯概率路线，多项式尺度的则借助群论加几何的"走廊"论证。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明：凡 `@@M@@p_c<1@@` 的无限连通局部有限拟传递图，其临界 Bernoulli 键渗流几乎必然没有无穷开簇——正面解决 Benjamini–Schramm 1996 年临界性猜想的键形式，特别涵盖一切 `@@M@@\mathbb{Z}^d@@`。

## 问题背景

拟传递（quasi-transitive）指图的自同构群在顶点上只有有限多个轨道，涵盖一切顶点传递图和有限生成群的 Cayley 图。Benjamini 与 Schramm 在 1996 年研究欧氏格点之外的渗流时提出猜想：`@@M@@p_c<1@@` 的拟传递图在临界参数处没有无穷簇。此前的拼图大致是：非顺从且具单模（unimodular）拟传递作用的图由 BLPS（1999）解决；指数增长的拟传递图由 Hutchcroft（2016）解决；Hermon–Hutchcroft（2021）又覆盖了满足一致伸展指数返回概率界（指数大于 `@@M@@1/2@@`）的单模图。剩下的次指数增长且不满足返回概率界的图，既无平面几何也无花边展开（lace expansion）可用，是最后的空白地带。本文按体积增长速度把这块硬骨头分成两种情形，分别用纯概率与群论加几何两条路线攻破。

## 主要结果

定理 1：设 `@@M@@G@@` 无限、连通、局部有限、拟传递，且 `@@M@@p_c(G)<1@@`，则
`@@M@@D\mathbb{P}_{p_c(G)}(\text{存在无穷开簇})=0,@@`
等价地每个顶点属于无穷簇的概率为零。条件 `@@M@@p_c<1@@` 不可去：参数为 `@@M@@1@@` 时整图全开。推论 2：对每个 `@@M@@d\ge 2@@`，`@@M@@\mathbb{Z}^d@@` 上最近邻键渗流在临界处无无穷簇（`@@M@@p_c<1@@` 由平面对偶围道计数验证）。

工具性结果是"联合粘合不等式"（joint gluing）：在可数图上，对顶点 `@@M@@o@@`、非空顶点集 `@@M@@A@@` 与任意集 `@@M@@T@@`，
`@@M@@D\mathbb{P}(o\leftrightarrow A,\ o\leftrightarrow T)\ \ge\ \mathbb{P}(o\leftrightarrow A)\inf_{a\in A}\mathbb{P}(a\leftrightarrow T),@@`
取 `@@M@@T@@` 为单点即得 Kozma–Nitzan 的乘法粘合不等式（Conjecture 1，2024）。其推论"到中继后失败"：当中继集 `@@M@@A@@` 中每点以概率 `@@M@@\ge 1-\lambda@@` 连到目标时，到达 `@@M@@A@@` 却连不到 `@@M@@T@@` 的概率 `@@M@@\le\lambda@@`，且在固定任意一批已揭示的边后仍可使用。

## 证明思路

先归化：一致指数增长率大于 `@@M@@1@@` 时整段引用 Hutchcroft 定理；剩下次指数增长，按两个穷竭性情形二分（无需中间增长分类）：(i) `@@M@@\log V_-(r)/\log r\to\infty@@`；(ii) 沿某无界半径序列 `@@M@@V_-(R_j)\le R_j^d@@`。其中 `@@M@@V_\pm(r)@@` 是半径 `@@M@@r@@` 球体积的最大、最小值。

情形 (i)（增长快于一切幂次）：设临界处有无穷簇，则各顶点有一致正下界 `@@M@@\theta@@`；经有限事件连续性，在某 `@@M@@p\in[p_c/2,p_c)@@` 处"簇大小 `@@M@@\ge L@@`"处处概率 `@@M@@\ge 3\theta/4@@`，再用带状论证找到尺寸 `@@M@@s@@`，使某顶点以概率 `@@M@@\ge(\log s)^{-2}@@` 簇落在带 `@@M@@[s,s^2)@@`，而处处尾概率 `@@M@@\ge\theta/2@@`。增长条件给出半径 `@@M@@r@@` 使 `@@M@@V_-(r)\ge s^4@@` 且 `@@M@@\log r=o(\log s)@@`；重采样带簇的关联边，可在球内找到距离 `@@M@@\le r@@`、互异且大小 `@@M@@\ge s@@` 的高概率簇对，取其最小距离 `@@M@@d@@`。一方面"双簇界"——一条固定边两侧各出现大小 `@@M@@\ge s@@` 的互异簇之概率 `@@M@@\le Cs^{-1/2}@@`（改编 Aizenman–Kesten–Newman 边界差方法与 Hutchcroft 幽场表述）——排除 `@@M@@d=1@@`；另一方面 `@@M@@d@@` 的最小性迫使距离 `@@M@@<d@@` 的点对以一致概率相连。最后沿测地线插值（interpolation）：反复二分路径，每次至多增加一个簇与一条连接边，代价由搜索的条件成功概率衰减的相对熵（relative entropy）控制，最终在某条相邻边上与双簇界矛盾。

情形 (ii)（多项式尺度）：先用 Tessera–Tointon 的单尺度结构定理，在由一个轨道构造的辅助传递图上提取有限指标子群 `@@M@@\Lambda\le\operatorname{Aut}(G)@@` 与到有限生成幂零（nilpotent）群 `@@M@@N@@` 的满同态 `@@M@@\rho@@`，其核的顶点轨道有限、顶点稳定子的像有限；商群只提供坐标，一切渗流路径与揭示的边都留在原图 `@@M@@G@@` 中。再对 `@@M@@N@@` 的循环列（cyclic series）中无穷循环因子个数 `@@M@@h@@` 归纳：`@@M@@h=0@@` 导致图有限；若交换化秩至多 `@@M@@1@@`，则水平切割中几乎必然出现无穷多闭割、一切簇被夹在有限层内，得 `@@M@@p_c=1@@`，矛盾；故存在 `@@M@@\phi:N\to\mathbb{Z}^2@@`，得等变坐标 `@@M@@\pi@@` 且相邻顶点坐标增量一致有界。归纳步排除投影有界的无穷开射线；配合临界无穷簇的唯一性，得到两个线性无关方向上的高概率近似移动（重标后位移 `@@M@@(1,1)@@` 与 `@@M@@(1,-1)@@`，边步长可任意小），并在某 `@@M@@p'<p_c@@` 保持。

最后沿斜率 `@@M@@\pm 1/4@@` 铺设走廊（corridor），走廊相交只发生在公共端区；联合粘合不等式经"新鲜领口传递"命题把连接逐段送过未揭示的走廊——入口由外部位选定，中继质量由内定位定义，二者解耦；自适应探索为每个待测点保存条件预测，单点条件失败 `@@M@@\le\varepsilon@@`。若好点集有限，其有向边界分解出的长 `@@M@@l@@` 闭迹至少指定 `@@M@@l/4@@` 个失败点，候选至多 `@@M@@4^l@@` 个，级数 `@@M@@\sum_l 4^l\varepsilon^{l/4}<1@@`，故以正概率好点无穷，在 `@@M@@p'<p_c@@` 得无穷开簇——矛盾，归纳完成。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。同族姊妹篇（`@@M@@\mathbb{Z}^3@@` 上键与点渗流的临界熄灭）主结果已 Lean 形式化，其有限联合不等式与本文的联合粘合定理在思想上同源、证法同构（簇列非负锥加交替重采样）；本文的一般定理又独立蕴含 `@@M@@\mathbb{Z}^d@@` 的键情形，两篇从特殊与一般两端互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题，阅读时宜以已形式化部分与社区核验为锚。

{% endraw %}
