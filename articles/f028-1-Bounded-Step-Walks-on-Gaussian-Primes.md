---
layout: default
title: "Bounded-Step Walks on Gaussian Primes"
family: "028"
discipline: "Number theory"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Bounded-Step Walks on Gaussian Primes

> 结果族 028：Uniformly bounded components of Gaussian-prime graphs　·　学科：Number theory　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把复数 a+bi 看成平面上的格子点，其中"素数格子"是可以落脚的石头，其余全是护城河。1962 年有人提问：能不能踩着石头、每步跨度不超过固定长度 D，永远跳下去而不落水？这篇论文证明：不能——而且不论从哪块石头出发，你能踏遍的石头总数有一个统一上限 B_D。

**关键词卡片**

- 高斯整数（Gaussian integer）：形如 a+bi 的复数，铺满一张方形格网。
- 高斯素数（Gaussian prime）：高斯整数中不可再分解的元素，即格子里能踩的石头。
- 高斯护城河猜想（Gaussian moat conjecture）：不存在步长有界的无穷素数跳跃，悬置六十余年。
- 连通分量（connected component）：图中互相能跳到的点组成的"朋友圈"。
- 一致有界（uniform bound）：上限 B_D 只依赖步长 D，与出发点无关，连坐标轴上的素数也算在内。

**看个具体例子**

此前的计算表明：从原点出发、步长不超过 6 时能走到的范围有限——但那只是一个起点的经验。新定理覆盖一切有限步长 D：每个连通分量至多含 B_D 个素数，起点任选（界存在但未给出具体数值）。数轴上 4k+3 型素数（3、7、11、19…）也是石头，同样被管住。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><circle cx="60" cy="45" r="2.5" fill="#bbb"/><circle cx="115" cy="45" r="2.5" fill="#bbb"/><circle cx="170" cy="45" r="2.5" fill="#bbb"/><circle cx="280" cy="45" r="2.5" fill="#bbb"/><circle cx="335" cy="45" r="2.5" fill="#bbb"/><circle cx="445" cy="45" r="2.5" fill="#bbb"/><circle cx="500" cy="45" r="2.5" fill="#bbb"/><circle cx="60" cy="100" r="2.5" fill="#bbb"/><circle cx="115" cy="100" r="2.5" fill="#bbb"/><circle cx="225" cy="100" r="2.5" fill="#bbb"/><circle cx="280" cy="100" r="2.5" fill="#bbb"/><circle cx="335" cy="100" r="2.5" fill="#bbb"/><circle cx="390" cy="100" r="2.5" fill="#bbb"/><circle cx="445" cy="100" r="2.5" fill="#bbb"/><circle cx="500" cy="100" r="2.5" fill="#bbb"/><circle cx="60" cy="155" r="2.5" fill="#bbb"/><circle cx="115" cy="155" r="2.5" fill="#bbb"/><circle cx="170" cy="155" r="2.5" fill="#bbb"/><circle cx="225" cy="155" r="2.5" fill="#bbb"/><circle cx="280" cy="155" r="2.5" fill="#bbb"/><circle cx="335" cy="155" r="2.5" fill="#bbb"/><circle cx="390" cy="155" r="2.5" fill="#bbb"/><circle cx="445" cy="155" r="2.5" fill="#bbb"/><circle cx="500" cy="155" r="2.5" fill="#bbb"/><circle cx="60" cy="210" r="2.5" fill="#bbb"/><circle cx="115" cy="210" r="2.5" fill="#bbb"/><circle cx="170" cy="210" r="2.5" fill="#bbb"/><circle cx="225" cy="210" r="2.5" fill="#bbb"/><circle cx="280" cy="210" r="2.5" fill="#bbb"/><circle cx="335" cy="210" r="2.5" fill="#bbb"/><circle cx="390" cy="210" r="2.5" fill="#bbb"/><circle cx="445" cy="210" r="2.5" fill="#bbb"/><circle cx="500" cy="210" r="2.5" fill="#bbb"/><ellipse cx="340" cy="140" rx="105" ry="60" fill="none" stroke="#c0392b" stroke-width="2" stroke-dasharray="8 5"/><line x1="66" y1="204" x2="106" y2="164" stroke="#1e8449" stroke-width="3"/><polygon points="115,155 104,161 109,170" fill="#1e8449"/><line x1="121" y1="149" x2="160" y2="110" stroke="#1e8449" stroke-width="3"/><polygon points="170,100 159,106 164,115" fill="#1e8449"/><circle cx="60" cy="210" r="6.5" fill="#333"/><circle cx="115" cy="155" r="6.5" fill="#333"/><circle cx="170" cy="100" r="6.5" fill="#333"/><circle cx="280" cy="45" r="6.5" fill="#333"/><circle cx="390" cy="45" r="6.5" fill="#333"/><circle cx="500" cy="45" r="6.5" fill="#333"/><circle cx="455" cy="155" r="6.5" fill="#333"/><circle cx="500" cy="210" r="6.5" fill="#333"/><circle cx="390" cy="210" r="6.5" fill="#333"/><circle cx="280" cy="210" r="6.5" fill="#333"/><text x="340" y="146" font-size="16" text-anchor="middle" fill="#c0392b">护城河</text><text x="340" y="166" font-size="12" text-anchor="middle" fill="#c0392b">（无素数区）</text><text x="60" y="232" font-size="12" text-anchor="middle" fill="#333">起点</text><text x="175" y="84" font-size="12" text-anchor="middle" fill="#c0392b">无路可走</text><text x="300" y="256" font-size="13" text-anchor="middle" fill="#333">示意：步长有界的行走迟早被"无素数区"拦住，且能走的石头总数有统一上限</text></svg>

</div>

**为什么值得关心**

六十年老问题一步关闭，而且"分量一致有界"远强于"没有无穷路径"；周期筛法加信息论计数的组合拳本身就是新方法。

> 已 Lean 形式化

## 一句话结论

证明了高斯护城河猜想（Gaussian moat conjecture）：不存在步长一致有界、经过两两不同高斯素数的无穷游走；更强的是，对每个步长上界 `@@M@@D@@`，高斯素数图的连通分支（connected component）大小有一致上界 `@@M@@B_D@@`，与起点无关——悬置六十余年的问题得到完整解决。

## 问题背景

高斯整数环 `@@M@@\mathbb{Z}[i]@@`（Gaussian integers）中的不可约元称为高斯素数（Gaussian prime），把 `@@M@@a+bi@@` 等同于格点 `@@M@@(a,b)@@`，范数 `@@M@@N(a+bi)=a^2+b^2@@`。对给定 `@@M@@D@@`，以全部高斯素数为顶点、距离 `@@M@@\le D@@` 的两点连边，得到图 `@@M@@G_D@@`；高斯护城河问题问：是否某个 `@@M@@G_D@@` 含无重复顶点的无穷路径，即能否用有界步长在素数"岛屿"间永远跳跃而不落入合数"护城河"。问题可追溯至 Basil Gordon 在 1962 年斯德哥尔摩国际数学家大会上的提问，Erdős 后来又归于 Gordon 与 Motzkin（1963 年 Pasadena 数论会议）。此前进展分两路：Gethner–Wagon–Wick 构造了任意大的无素数圆盘与任意孤立的实高斯素数（Vardi 独立证明后者），但平面上的游走可以绕开局部障碍；Tsuchimura 的计算表明步长 `@@M@@\le 6@@` 时从原点出发可达距离有限，却只针对特定起点。最接近的前身是 Gethner–Stark 的有限周期筛法（finite periodic sieving）：他们对步长 `@@M@@\sqrt2@@` 与 `@@M@@2@@` 建立了周期障碍，并提议用小高斯素数筛法处理更大步长。真正的卡点在"一致性"：一般局部有限图中"没有无穷路径"推不出"分支大小有界"，必须依靠周期结构。

## 主要结果

主定理（一致分支界，uniform component bound）：对每个有限实数 `@@M@@D@@` 存在有限数 `@@M@@B_D@@`，使 `@@M@@G_D@@` 的每个连通分支至多含 `@@M@@B_D@@` 个顶点；界与起始素数无关，坐标轴上的素数也包括在内。因此任何由不同高斯素数组成、相邻距离 `@@M@@\le D@@` 的序列至多 `@@M@@B_D@@` 项，无穷有界步长游走不存在。界是非显式的（nonexplicit）：固定 `@@M@@D@@` 后证明只保证尺度足够大；`@@M@@D<1@@` 时不同格点不能相邻，`@@M@@B_D=1@@` 即可。

核心中间结果是有限筛障碍定理（finite sieve obstruction）：对每个 `@@M@@D\ge1@@`，存在有限的有理素数集 `@@M@@\mathcal{P}_D@@`（全为 `@@M@@p\equiv1\pmod 4@@`），使得避让集 `@@M@@\mathcal{A}(\mathcal{P}_D)@@`——即模每个选定素数的两个共轭高斯因子 `@@M@@\pi_p,\overline{\pi_p}@@` 都不为零的格点——中不存在步长 `@@M@@\le D@@` 的无穷自回避（self-avoiding）序列。

## 证明思路

整体分两级：先证有限筛障碍，再用周期性归约升级为一致分支界。周期归约较短：`@@M@@\mathcal{A}(\mathcal{P})@@` 在 `@@M@@Q\mathbb{Z}^2@@`（`@@M@@Q=\prod p@@`）平移下不变；若某有限分支含相差 `@@M@@Q\mathbb{Z}^2@@` 中向量的两点，该平移把分支映到自身，与有限性矛盾，故每个分支单射入 `@@M@@(\mathbb{Z}/Q\mathbb{Z})^2@@`，至多 `@@M@@Q^2@@` 个点；被筛除的高斯素数只是所选因子的相伴元（associates），共有限多个，补一个显式修正项即可。

筛法定理是重头戏。反设存在避开全部选定零类的无穷自回避 `@@M@@D@@` 步游走——游走本身是确定的，随机性只来自采样时刻与对每个分裂素数（split prime）选取哪个共轭因子的"符号"。先做几何采样制造熵：一段 `@@M@@n@@` 步线段含很多不同差值，证明用环面度数论证（torus degree argument）——由直径端点与离直径最远点构造的连续映射在平坦环面上度为 `@@M@@-1@@` 因而满射，差值集的 `@@M@@2D@@` 圆盘覆盖面积为 `@@M@@A=RW@@` 的环面，得 `@@M@@|E-E|\ge c_DA@@`；再证随机符号乘积以高概率避开细矩形（用行列式被范数整除排除非零倍数、Hoeffding 集中控制单条直线、布尔立方体的等周不等式避免枚举直线），于是模约化在差值集上单射。从差值中均匀采样并随机取一个端点，得到熵增补（entropy enrichment）不等式：端点的剩余熵分数至少是起点熵分数与最大值的一半之和再减 `@@M@@O_D(g)@@`，迭代后熵亏指数式衰减。接着做覆盖传递（coverage transfer）：联合熵只给出平均意义下的接近均匀，需升级为"除 `@@M@@p^{1-\beta}@@` 个例外剩余外，几乎每个坐标的边缘分布质量 `@@M@@\ge\tau/p@@`"；诀窍是让 `@@M@@n@@` 次重复位移构成一个共享数据向量，其熵只在联合熵中支付一次，若覆盖失败，Fano 不等式的短列表版本会强制过大的条件信息，与联合熵预算矛盾。然后排公共调度（schedule）：把几何操作按递减尺度排成三个带（参数 `@@M@@g_0@@`、`@@M@@e^{-M^3}@@`、`@@M@@e^{-100M^{20}}@@`），并以公共终态时间律 `@@M@@t_*@@`（加均匀偏移使其在小平移下几乎不变）统一测量；从最底带极精确的单坐标熵基例出发反向归纳，得到在每个检查点、每个精确起点下的终态剩余覆盖。最后收网于信息论矛盾：既然游走避开零类，长度 `@@M@@L_T\approx T^{2/5}@@` 的短增量词就能测试候选起始剩余——词内各偏移的命中事件互不相交（两次命中意味着差被 `@@M@@\pi@@` 整除，而 `@@M@@\pi@@` 的非零倍数长度 `@@M@@\ge\sqrt p@@`，该差又 `@@M@@\le DL<\sqrt p@@`，矛盾），故每个批次每步增量至少付出 `@@M@@c_1/\log T@@` 的信息。再用嵌套剩余向量与二进分块，把各批次代价在公共时间律下望远镜求和，上界为单个有界增量的熵 `@@M@@\log K_D@@`；但批次横跨约 `@@M@@M@@` 个几何窗口，下界随 `@@M@@M@@` 发散，矛盾。此收尾与 Tao 的熵递减（entropy-decrement）论证方法相通。

## 可信度与备注

本文主结果已由作者完成 Lean 形式化证明（结果族文档附 Lean 链接），验证等级最高。本族仅此一篇手稿，内部呈"有限筛障碍 + 周期归约"两级结构，两条定理分别独立陈述、后者由前者推出，逻辑自洽。界 `@@M@@B_D@@` 非显式，具体数值不在定理范围。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，读者可对照 Lean 证明核查。

{% endraw %}
