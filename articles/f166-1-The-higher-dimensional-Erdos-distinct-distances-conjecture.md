---
layout: default
title: "The higher-dimensional Erdős distinct-distances conjecture"
family: "166"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The higher-dimensional Erdős distinct-distances conjecture

> 结果族 166：The higher-dimensional Erdős distinct-distances conjecture　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

在天上撒一把星星，量出每两颗之间的距离——这些距离里能有多少种不同的数值？撒得聪明的话，很多距离会重复。Erdős 在 1946 年问：n 个点最少能给出多少种不同距离？平面情形至今还差着对数因子没合拢，而这篇论文把三维及以上的版本彻底解决：不管你怎么撒，至少 `@@M@@c_d n^{2/d}@@` 种，而且幂次无法再改进。

**关键词卡片**

- 不同距离集（distinct distances）：所有点对距离去重后的个数，记 `@@M@@|\Delta(P)|@@`。
- 格点构造（integer lattice）：整点网格 `@@M@@\{1,\dots,t\}^d@@`，已知最"省距离"的撒法。
- 幂次 `@@M@@2/d@@`（exponent）：距离种数随点数增长的指数，定理证明它不能更低。
- 刚体运动（rigid motion）：整体旋转加平移；证明中用它给"等距点对"建立联系。

**看个具体例子**

拿最熟悉的格点：正方体的 8 个顶点。28 对点对的距离只有 3 种——棱、面对角线、体对角线。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="150" y1="100" x2="310" y2="100" stroke="#8899aa" stroke-width="2"/>
  <line x1="310" y1="100" x2="310" y2="240" stroke="#8899aa" stroke-width="2"/>
  <line x1="310" y1="240" x2="150" y2="240" stroke="#8899aa" stroke-width="2"/>
  <line x1="150" y1="240" x2="150" y2="100" stroke="#8899aa" stroke-width="2"/>
  <line x1="230" y1="58" x2="390" y2="58" stroke="#8899aa" stroke-width="2"/>
  <line x1="390" y1="58" x2="390" y2="198" stroke="#8899aa" stroke-width="2"/>
  <line x1="390" y1="198" x2="230" y2="198" stroke="#8899aa" stroke-width="2"/>
  <line x1="230" y1="198" x2="230" y2="58" stroke="#8899aa" stroke-width="2"/>
  <line x1="150" y1="100" x2="230" y2="58" stroke="#8899aa" stroke-width="2"/>
  <line x1="310" y1="100" x2="390" y2="58" stroke="#8899aa" stroke-width="2"/>
  <line x1="310" y1="240" x2="390" y2="198" stroke="#8899aa" stroke-width="2"/>
  <line x1="150" y1="240" x2="230" y2="198" stroke="#8899aa" stroke-width="2"/>
  <line x1="310" y1="100" x2="150" y2="240" stroke="#e0a000" stroke-width="2" stroke-dasharray="7 5"/>
  <line x1="150" y1="240" x2="390" y2="58" stroke="#8a4fbf" stroke-width="2" stroke-dasharray="7 5"/>
  <circle cx="150" cy="100" r="6" fill="#45607a"/>
  <circle cx="310" cy="100" r="6" fill="#45607a"/>
  <circle cx="310" cy="240" r="6" fill="#45607a"/>
  <circle cx="150" cy="240" r="6" fill="#45607a"/>
  <circle cx="230" cy="58" r="6" fill="#45607a"/>
  <circle cx="390" cy="58" r="6" fill="#45607a"/>
  <circle cx="390" cy="198" r="6" fill="#45607a"/>
  <circle cx="230" cy="198" r="6" fill="#45607a"/>
  <text x="100" y="86" font-size="13" fill="#777777">棱 = 1</text>
  <text x="280" y="252" font-size="14" text-anchor="middle" fill="#333333">正方体 8 个顶点：28 对点对的距离只有 3 种</text>
  <text x="280" y="271" font-size="13" text-anchor="middle" fill="#555555">实线棱 1；橙虚线面对角线 √2；紫虚线体对角线 √3</text>
</svg>

</div>

推向三维格 `@@M@@\{1,\dots,t\}^3@@`：`@@M@@t^3@@` 个点，平方距离是 1 到 `@@M@@3(t-1)^2@@` 的整数，至多 `@@M@@O(t^2)=O(n^{2/3})@@` 种——指数 `@@M@@\tfrac23=2/d@@` 正是构造与定理的会师点。定理（数字版）：`@@M@@\mathbb{R}^3@@` 中任意 n 个点至少 `@@M@@c_3 n^{2/3}@@` 种距离；如 `@@M@@n=10^6@@` 时至少约 `@@M@@c_3\cdot 10^4@@` 种，且 `@@M@@c_3@@` 是不随点集变化的绝对常数。这最后一句并不显然：三维此前最好的 `@@M@@n^{2/3-o(1)}@@` 型界带着会慢慢衰减的尾巴，推不出常数因子，本文必须一次性排除所有潜在的反例序列。

**为什么值得关心**

高维 Erdős 不同距离猜想获正面解决；此前偏低的指数（如四维的 `@@M@@8/17@@`）全部被推平到 `@@M@@2/d@@`。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

对每个固定维数 `@@M@@d\ge3@@`，`@@M@@\mathbb R^d@@` 中任意 `@@M@@n\ge2@@` 个不同点至少决定 `@@M@@c_d n^{2/d}@@` 个不同距离，`@@M@@c_d>0@@` 只依赖 `@@M@@d@@`。幂次与整数格例子一致而达最优，由此正面解决高维 Erdős 不同距离猜想。

## 问题背景

不同距离问题（distinct-distances problem）由 Erdős 于 1946 年提出：`@@M@@n@@` 个点两两距离的总数最少能有多少？平面方格构造只给出 `@@M@@O(n/\sqrt{\log n})@@` 个距离，Guth–Katz 证明了阶匹配的 `@@M@@\Omega(n/\log n)@@` 下界；而 `@@M@@d\ge3@@` 时的猜想是常数倍的 `@@M@@n^{2/d}@@`。此前最好的结果沿两条线：Solymosi–Vu 的递推不等式，以及 Tidor–Yu–Zakharov（2026）的三维界 `@@M@@n^{2/3-o(1)}@@`——代入递推得四维 `@@M@@n^{8/17-o(1)}@@`、五维 `@@M@@n^{3/8-o(1)}@@`，指数全都低于 `@@M@@2/d@@`。更本质的困难是：`@@M@@n^{2/d-o(1)}@@` 型下界推不出常数因子，因为比值可能以任意慢的速度衰减，证明必须一次性排除所有反例序列。历史上 Aksoy Yazici 曾宣布解决该猜想，后因证明有误自行撤稿，可见此问题极易出错。

## 主要结果

记 `@@M@@\Delta(P)=\{|p-q|:p,q\in P,\ p\ne q\}@@`。主定理（introduction.tex 第 19–26 行）：对每个整数 `@@M@@d\ge3@@` 存在 `@@M@@c_d>0@@`，使任意 `@@M@@n\ge2@@` 个不同点的有限集 `@@M@@P\subset\mathbb R^d@@` 满足 `@@M@@|\Delta(P)|\ge c_d n^{2/d}@@`，对点的位置、间距与集中程度不作任何假设。指数 `@@M@@2/d@@` 最优：整数格 `@@M@@\{1,\ldots,t\}^d@@` 有 `@@M@@t^d@@` 个点，其平方距离是 `@@M@@1@@` 到 `@@M@@d(t-1)^2@@` 之间的整数，故仅 `@@M@@O(t^2)=O(n^{2/d})@@` 个距离。平面情形因方格给出 `@@M@@O(n/\sqrt{\log n})@@`，猜想阶与此不同，不属本文范围。

## 证明思路

全文用反证法：取定理失效的最小维数 `@@M@@d\ge3@@`，则有序列 `@@M@@N=|P|\to\infty@@` 使 `@@M@@M=1+|\Delta(P)|=o(A)@@`，其中 `@@M@@B=N^{1/d}@@`、`@@M@@A=B^2@@`；由低维归纳与附录自给的平面 Guth–Katz 型界，先封顶每个真仿射平坦上的点数。

第一步做对称的方向选取：在每个中心 `@@M@@p@@` 处，让次数 `@@M@@\lfloor A\rfloor@@` 的齐次多项式能在选中的位移方向 `@@M@@\pi_p(q)=[q-p]@@` 上任意指定取值（等价于赋值向量线性无关）。唯一实质障碍是"稀疏锥"（sparse cones）：给每点配一族总次数 `@@M@@o(N/A)@@` 的投影曲线，覆盖几乎全体点对。论文用多尺度"尺度剖面"（scale profile）将其排除——在 `@@M@@[Be^{-s},Be^s]@@` 的多个对数宽度窗口内记录 `@@M@@d@@` 次真超曲面切割的切割时刻，得到平衡剖面（`@@M@@\sum_i b_i=0@@`，`@@M@@b_1<0<b_d@@` 等），再用 Chardin–Philippon 型 Hilbert 函数（Hilbert function）下界给出每个正密度子集的多项式限制秩下界，与锥覆盖迫使的秩上界冲突；割线几何（secant geometry）与终端曲线的先期删除控制径向投影合并造成的损失，两个端点情形则用直接的投影像比较处理。

第二步把等距化为平坦相交：取 `@@M@@P@@` 的通用旋转副本 `@@M@@Q@@`，当 `@@M@@|p-p'|=|q-q'|@@` 且两端点对均被选中时连边，Cauchy–Schwarz 给出 `@@M@@\Omega(N^4/M)@@` 条边。每个点对对应斜形式空间中一个 `@@M@@s_0=d(d-1)/2@@` 维仿射平坦 `@@M@@F_{p,q}@@`，插值性保证邻居平坦两两不同且有 `@@M@@O(A)@@` 次分离子（separator）。`@@M@@d=3@@` 时还需"富运动定理"（`@@M@@\sum_g k_g^2\le K N^4/A@@`，两种定向都计入）删除单个刚性运动（rigid motion）匹配过多的边，其证明综合了 Szemerédi–Trotter、Beck 二分法与六维空间中关于分裂二次型的多项式降次论证。

最后一步只做一次随机采样：全局集中性加 Hilbert 下界给出全体保留平坦在次数 `@@M@@\lfloor A\rfloor@@` 的总秩至少 `@@M@@c_4 mA^{s_0}@@`，而以小固定概率采样的子族秩严格更小，同时每个顶点仍保有 `@@M@@\gg A^{d-1}@@` 个采样邻居。于是存在次数 `@@M@@\le A@@` 的多项式，在所有采样平坦上为零、却在某个保留平坦 `@@M@@F@@` 上不恒为零；其限制零化超过 `@@M@@C A^{d-1}@@` 个两两不同的邻居平坦，与局部集中性（次数 `@@M@@\le A@@` 的多项式至多含 `@@M@@O(A^{d-1})@@` 个邻居平坦）矛盾。所有常数沿序列一致，这正是常数因子的来源。

## 可信度与备注

本文暂无形式化证明，请以社区核验为准。结果族 166 目前仅此一篇手稿，无姊妹篇互证；其依赖的平面基例与集中性、经典关联工具均在附录内自给并逐处标明与 Szemerédi–Trotter、Beck、Elekes–Sharir、Guth–Katz 及 Tidor–Yu–Zakharov 工作的关系，作者还如实记录了前人撤稿的教训。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
