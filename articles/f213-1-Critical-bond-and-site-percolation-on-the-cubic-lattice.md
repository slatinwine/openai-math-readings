---
layout: default
title: "Critical bond and site percolation on the cubic lattice"
family: "213"
discipline: "Probability and statistical mechanics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Critical bond and site percolation on the cubic lattice

> 结果族 213：Critical percolation on every quasi-transitive graph　·　学科：Probability and statistical mechanics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

想象一张无限大的渔网，每条网线独立地以概率 p"接通"。p 很小时到处是孤岛，p 很大时一网连通到天边。分界点 p_c 处究竟有没有无限大的连通块？这个问题在三维方格网上卡了几十年，本文给出答案：没有——而且"随机接通边"和"随机接通顶点"两种玩法都没有。

**关键词卡片**

- 渗流（percolation）：每条边（或每个顶点）独立以概率 p 开放的随机连通模型。
- 临界参数 p_c：存在无穷连通块与不存在之间的分水岭。
- 渗流函数 θ(p)：原点连到无穷远的概率。
- 键渗流与点渗流（bond/site percolation）：开放的对象是边还是顶点，两者临界参数不同。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="70" y1="220" x2="500" y2="220" stroke="#333" stroke-width="2"/>
  <line x1="70" y1="220" x2="70" y2="50" stroke="#333" stroke-width="2"/>
  <path d="M 70 220 L 285 220 C 315 220 325 130 365 110 C 405 92 455 80 495 74" fill="none" stroke="#2c5fa8" stroke-width="3"/>
  <line x1="285" y1="220" x2="285" y2="70" stroke="#999" stroke-width="1.5" stroke-dasharray="5 4"/>
  <circle cx="285" cy="220" r="5" fill="#c0392b"/>
  <text x="285" y="242" font-size="13" text-anchor="middle" font-style="italic" fill="#333">p_c</text>
  <text x="70" y="242" font-size="12" text-anchor="middle" fill="#333">0</text>
  <text x="500" y="242" font-size="12" text-anchor="middle" fill="#333">1</text>
  <text x="52" y="58" font-size="13" font-style="italic" fill="#333">θ(p)</text>
  <text x="512" y="225" font-size="13" font-style="italic" fill="#333">p</text>
  <text x="165" y="195" font-size="12" fill="#666">p &lt; p_c：无无穷簇</text>
  <text x="400" y="140" font-size="12" fill="#2c5fa8">p &gt; p_c：有无穷簇</text>
  <text x="285" y="266" font-size="12.5" text-anchor="middle" fill="#c0392b">临界点处 θ(p_c) = 0：无无穷簇，θ 在 p_c 连续</text>
</svg>

</div>

定理的几何含义就是上图：θ(p) 在 p<p_c 时恒为 0，在 p>p_c 时变正，而在临界点本身取值也是 0——曲线"贴地"走过 p_c 后才抬头。二维靠对偶技巧早已解决，很高维（d≥11）靠花边展开也行，唯独物理上最重要的三维两边技巧同时失效，成了著名的空白。

**为什么值得关心**

它补上了悬置多年的"中间维度"缺口，证明还产出一台可复用的有限比较不等式"发动机"，对键、点两种模型统一走完。此前最好的结果是"薄板上的临界熄灭"，但薄板阈值收敛于整格点阈值并不自动给出临界点本身的结论——跨越最后这一步正是本文的关键一跃。

> 已 Lean 形式化

## 一句话结论

证明 `@@M@@\mathbb{Z}^3@@` 上最近邻 Bernoulli 键渗流与点渗流在临界参数 `@@M@@p_c@@` 处几乎必然均无无穷开簇，补上悬置多年的中间维度缺口，并得 `@@M@@\theta(p)@@` 在 `@@M@@p_c@@` 处连续。

## 问题背景

渗流模型由 Broadbent 与 Hammersley（1957）引入：每条边（键模型）或每个顶点（点模型）独立地以概率 `@@M@@p@@` 开放，问何时出现无穷开簇。临界参数 `@@M@@p_c@@` 把有无无穷簇的区域分开，而"恰在 `@@M@@p_c@@` 处是否存在无穷簇"是最基本的问题之一。二维已由 Harris（1960）、Kesten（1980）与 Russo（1981）解决；高维 `@@M@@d\ge 11@@` 由花边展开（lace expansion）覆盖（Hara–Slade，Fitzner–van der Hofstad；点模型见 Heydenreich–Matzke）。中间维度——尤其是物理上最重要的 `@@M@@d=3@@`——既没有平面自对偶几何可用，花边展开又失效，长期缺乏抓手。Benjamini 与 Schramm（1996）把问题推广为拟传递图上的临界性猜想，本结果族正冲它而去。此前 Duminil-Copin–Sidoravicius–Tassion 证明了板层（slab）上的临界熄灭，且板层阈值收敛于整格点阈值，但这并不自动给出整格点在临界处的结论——跨越这最后一步正是本文的任务。

## 主要结果

主定理（Theorem 1.2）：对 `@@M@@\mathbb{Z}^3@@` 上最近邻 Bernoulli 键渗流，键临界参数处几乎必然无无穷开簇；点渗流（site percolation）在点临界参数处同样成立。记 `@@M@@\theta(p)=\mathbb{P}_p(0\text{ 属于无穷开簇})@@`，定理蕴含 `@@M@@p\downarrow p_c@@` 时 `@@M@@\theta(p)\to 0@@`，即渗流函数在临界点连续。

论文的发动机是一条有限比较不等式——联合连接比较（joint connection comparison）：在允许各超边（hyperedge）开概率不同的独立有限超图上，对节点 `@@M@@o@@`、非空节点集 `@@M@@A@@` 与目标集 `@@M@@T@@`，
`@@M@@D\mathbb{P}(o\leftrightarrow A,\ o\leftrightarrow T)\ \ge\ \mathbb{P}(o\leftrightarrow A)\min_{a\in A}\mathbb{P}(a\leftrightarrow T),@@`
其中开超边同时连接其所有节点。取 `@@M@@T@@` 为单点并放大左端事件，即得 Kozma–Nitzan 的乘法粘合不等式（Conjecture 1，2024）。由它做减法得"失败比较"：若中继集 `@@M@@A@@` 中每点都以概率 `@@M@@\ge 1-b@@` 连到目标 `@@M@@T@@`，则 `@@M@@\mathbb{P}(o\leftrightarrow A,\ o\not\leftrightarrow T)\le b@@`；且这批结论在任意一批位被固定后依旧成立，因而可在探索过程中反复调用。点渗流经关联构造（每个顶点及其关联边合成一个超边）化为超图情形，只需额外处理"零长路径的自连接要求端点开放"这一约定差异。

## 证明思路

反证：设 `@@M@@p_c@@` 处有无穷簇。先证它几乎必然存在（改有限个位不会消灭无穷连通成分，配合 0-1 律，不用唯一性），于是大种子盒 `@@M@@\Lambda_m@@` 以趋于 1 的概率接触它；再用 Harris 正结合不等式，把"连到立方体整个边界"摊到 24 个四分之一面（quarter-face）上：在 `@@M@@p_c@@` 下每个面被连接的概率 `@@M@@>1-\gamma/2@@`。此处次序关键：所有尺度先在 `@@M@@p_c@@` 处选定；相关事件只依赖有限个位、概率是参数的多项式，故随后可一次性取某个 `@@M@@q<p_c@@`，让三个半径 `@@M@@2r,2r+1,10r@@` 上的 24 个面估计同时保持裕度——这正是绕开"板层有临界熄灭但整格点没有"这一经典障碍的办法。

有限不等式的证明：把每个簇按"第一个被列出的顶点"分解，得到条件连接向量排成的单位下三角矩阵 `@@M@@H@@`；对递增簇泛函 `@@M@@F@@` 递减归纳证明 `@@M@@v_k^F-\mu_k(F)h_k@@` 落在后面各列生成的非负锥中。归纳步靠两件事：删除残差 `@@M@@R_F@@` 的非负性与递增性，以及"交替条件簇重采样"马氏链（van den Berg–Håggström–Kahn 的技巧）：每次转移至少以概率 `@@M@@a=\prod_{e\ni s}(1-p_e)>0@@` 命中孤立点，故函数振荡以 `@@M@@(1-a)^t@@` 几何衰减，`@@M@@P^tF@@` 一致收敛于均值；闭锥取极限完成归纳，再由 `@@M@@H^{-1}=I-\Gamma@@` 的非负权重读出最后一行即得不等式。

接着是新鲜区域扩展引理：在内部位仍是独立参数 `@@M@@q@@` 的长方体 `@@M@@D@@` 内，若外部源 `@@M@@o@@` 连到内盒 `@@M@@B@@`，则以概率 `@@M@@\ge 1-\eta@@` 同时连到目标 `@@M@@T@@`。机制是壳层论证先锁定接触点足够多的确定层；外部位 `@@M@@\zeta@@` 从中选出 `@@M@@K@@` 个相距 `@@M@@>4m+2@@` 的入口并各配独立开种子盒，Chebyshev 控制成功数；中继质量 `@@M@@g_y=\mathbb{P}(v_y\leftrightarrow T\mid\xi)@@` 只用内部位 `@@M@@\xi@@` 定义，Harris 不等式保证好中继居多；最后固定 `@@M@@\xi@@`，调用失败比较收尾。

几何传送用 13 步初等移动（3 次收缩加 10 次平移，末步长 `@@M@@2r+1@@` 适配粗格间距 `@@M@@20r+1@@`）把连接从粗立方体内盒递到相邻内盒，失败 `@@M@@\le 13\eta@@`，不要求 13 个事件独立。最终在粗格 `@@M@@\mathbb{Z}^2@@` 上做自适应广度优先探索：为每个待处理立方体保存条件连接承诺 `@@M@@>1-\delta@@`，新鲜性引理保证未揭示位始终是独立参数 `@@M@@q@@` 的乘积律，故每个立方体被判"坏"的条件概率 `@@M@@<f@@`。若好集合有限，其对偶边界含长 `@@M@@n@@` 的简单圈（候选至多 `@@M@@2n3^n@@` 个），可匹配出 `@@M@@n/7@@` 条端点不交的交叉边，每条边的外侧端点必坏，概率 `@@M@@\le (2f)^{n/7}@@`；级数求和 `@@M@@<1@@`，故以正概率好集合无穷，从而在 `@@M@@q<p_c@@` 处出现无穷开簇，矛盾。全程不假设无穷簇唯一性，也不假设成功立方体相互独立；键、点两模型沿同一条主线走完。

## 可信度与备注

依据任务元数据，本文主结果已 Lean 形式化；引言亦援引 Leder 的 Lean 形式化报告（`@@M@@\mathbb{Z}^d@@` 各维键渗流的临界熄灭），其"首次接触比较 (GEN)"直接蕴含本文的有限联合不等式。同族姊妹篇对一般拟传递图证明了键渗流的临界熄灭，独立蕴含本文的键结论；本文则额外覆盖点渗流，并给出完全自足的立方格论证（含比较不等式、中继几何与探索估计的完整细节）。按 OpenAI 官方声明，未经形式化的结果可能有问题；已形式化的部分以形式化仓库为准。

{% endraw %}
