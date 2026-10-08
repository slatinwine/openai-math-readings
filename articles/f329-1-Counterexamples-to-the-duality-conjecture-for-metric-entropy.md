---
layout: default
title: "Counterexamples to the duality conjecture for metric entropy"
family: "329"
discipline: "Functional analysis"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Counterexamples to the duality conjecture for metric entropy

> 结果族 329：A counterexample to metric-entropy duality　·　学科：Functional analysis　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

盖住一块地砖最少要几张小纸片？这个"最少张数"叫覆盖数，是衡量图形复杂程度的计数器。1972 年 Pietsch 猜想：高维空间里一个"胖块"盖另一个的难度，与它换成对偶描述（极体）后的难度，应该只差一个与维数无关的固定倍数。本文证明这是错的：维数够高时，两种难度可以悬殊到任意倍——悬置五十多年的度量熵对偶猜想被推翻。

**关键词卡片**

- 覆盖数（covering number）：用 `@@M@@B@@` 的平移盖住 `@@M@@A@@` 所需的最少份数 `@@M@@N(A,B)@@`，集合复杂度的计数器。
- 极体（polar body）：凸体的对偶画像——改用各方向的"支撑刻度"描述同一形状。
- 对偶猜想（duality conjecture）：Pietsch 1972 年问：取极前后 `@@M@@\log N@@` 是否只差普适常数倍。
- 中心对称凸体（origin-symmetric convex body）：关于原点对称、含线段的 `@@M@@n@@` 维实心块。
- 度量熵（metric entropy）：`@@M@@\log N@@`，覆盖复杂度的对数刻度，维数越高账单越贵。

**看个具体例子**

先热身：用边长 `@@M@@\frac{1}{10}@@` 的小方片盖单位方片要 `@@M@@10^2=100@@` 片；`@@M@@n@@` 维则要 `@@M@@(1/\varepsilon)^n@@` 片——`@@M@@\log N@@` 就是"维数 × 精度"的账单。定理的数字版：任凭你把倍数 `@@M@@b@@` 定得多大（哪怕一百万），总存在足够高的维数 `@@M@@n@@` 与凸体 `@@M@@K@@`，使得用立方体 `@@M@@L=[-1,1]^n@@` 盖 `@@M@@K@@` 的账单，超过盖极体账单的 `@@M@@b@@` 倍：

`@@M@@D\log N(K,L)>b\cdot\log N(L^\circ,a^{-1}K^\circ)@@`

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="28" font-size="15" fill="#222">同一形状的两本账：盖法难度可以悬殊（示意）</text>
  <rect x="40" y="60" width="200" height="200" fill="none" stroke="#2f5fd0" stroke-width="2"/>
  <line x1="90" y1="60" x2="90" y2="260" stroke="#9db8e8" stroke-width="1"/>
  <line x1="140" y1="60" x2="140" y2="260" stroke="#9db8e8" stroke-width="1"/>
  <line x1="190" y1="60" x2="190" y2="260" stroke="#9db8e8" stroke-width="1"/>
  <line x1="40" y1="110" x2="240" y2="110" stroke="#9db8e8" stroke-width="1"/>
  <line x1="40" y1="160" x2="240" y2="160" stroke="#9db8e8" stroke-width="1"/>
  <line x1="40" y1="210" x2="240" y2="210" stroke="#9db8e8" stroke-width="1"/>
  <text x="40" y="50" font-size="13" fill="#222">盖 K：需要 16 片（示意）</text>
  <polygon points="425,90 486,125 486,195 425,230 364,195 364,125" fill="#f2f2f2" stroke="#2f5fd0" stroke-width="2"/>
  <circle cx="395" cy="160" r="52" fill="#7fc97f" fill-opacity="0.4" stroke="#2f8f4e" stroke-width="1.5"/>
  <circle cx="455" cy="160" r="52" fill="#7fc97f" fill-opacity="0.4" stroke="#2f8f4e" stroke-width="1.5"/>
  <text x="330" y="50" font-size="13" fill="#222">盖极体 K°：2 片够用（示意）</text>
  <text x="300" y="255" font-size="13" fill="#666">维数升高，悬殊程度可任意大</text>
</svg>

</div>

**为什么值得关心**

覆盖数是学习理论、压缩感知与算子理论通用的"复杂度货币"；反例说明换一种对偶描述会彻底改变标价，此后的熵估计必须绕开这个坑。

> 主结果已 Lean 形式化

## 一句话结论

本文推翻了 Pietsch 1972 年提出的度量熵对偶猜想：对任意提议的普适常数 `@@M@@a,b\ge1@@`，都能构造中心对称凸体 `@@M@@K@@` 与立方体 `@@M@@L=[-1,1]^n@@`，使 `@@M@@\log N(K,L)>b\log N(L^\circ,a^{-1}K^\circ)@@`。这一悬置五十余年的猜想由此得到否定的回答。

## 问题背景

覆盖数 (covering number) `@@M@@N(A,B)@@` 是覆盖集合 `@@M@@A@@` 所需的 `@@M@@B@@` 的平移的最少个数，其对数量化一个集合的"度量复杂度"。1972 年 Pietsch 在研究算子的熵数 (entropy numbers) 时提出对偶猜想 (duality conjecture)：是否存在绝对常数 `@@M@@a,b\ge1@@`，使一切维数、一切中心对称凸体 (origin-symmetric convex body) `@@M@@K,L@@` 都满足 `@@M@@\frac1b\log N(L^\circ,aK^\circ)\le\log N(K,L)\le b\log N(L^\circ,a^{-1}K^\circ)@@`，其中 `@@M@@K^\circ@@` 是极体 (polar body)。直观地说，它问"取极"这一对偶操作能否在普适的尺度与常数变化下保持覆盖复杂度。此前所有正面结果都限于特殊情形：一边是椭球时猜想成立（Artstein–Milman–Szarek 2004）；凸化堆积 (convexified packing) 的相应对偶成立（AMSTJ 2004）；一般对称凸体只有带对数损失的比较（E. Milman 2007）。普适常数对究竟是否存在，五十余年无人能证、也无人能否——本文给出否定答案。

## 主要结果

**定理 1（主定理）**　对任意 `@@M@@a,b\ge1@@`，存在正整数 `@@M@@n@@` 与 `@@M@@\R^n@@` 中的中心对称凸体 `@@M@@K@@`，使得取立方体 `@@M@@L=[-1,1]^n@@` 时
`@@M@@D\log N(K,L)>b\log N(L^\circ,a^{-1}K^\circ).@@`
于是猜想中的上界对每一对候选常数都失效，双边猜想整体不成立——而且反例里覆盖体已经是最简单的立方体。两点澄清：反例的维数 `@@M@@n@@` 随参数 `@@M@@a,b@@` 增长，论文不对任何固定维数下断言；`@@M@@K@@` 具有非空内部，是货真价实的凸体。论文还给出渐近版本：固定 `@@M@@a@@`、让参数 `@@M@@r@@` 增大时，两个熵的对数比 `@@M@@\log N(L_r^\circ,a^{-1}K_r^\circ)/\log N(K_r,L_r)\to0@@`，悬殊程度可任意大。文末的推论进一步把普通覆盖熵与凸化堆积熵 `@@M@@\widehat M@@` 分离：对任意 `@@M@@A,C\ge1@@` 存在 `@@M@@K@@` 使 `@@M@@\log N(K,L)>C\log\widehat M(K,L/A)@@`，说明 AMSTJ 的凸化堆积对偶定理救不回普通版本。

## 证明思路

证明是一条四步流水线：几何转换、组合压缩、有限域构造、参数选择。

先做矩阵到凸体的转换（第 2 节）。设一个实矩阵的行为 `@@M@@R_x@@`，两两在 sup 范数下距离 `@@M@@\ge1@@`，列的绝对凸包 (absolutely convex hull) 有大小为 `@@M@@M@@` 的 `@@M@@\varepsilon@@`-一致逼近表。令 `@@M@@K=3\absconv\{R_x\}+tB_\infty^Y@@`，`@@M@@L=B_\infty^Y@@`。一方面，`@@M@@L@@` 的每个平移直径为 `@@M@@2@@`，装不下相距 `@@M@@3@@` 的两点 `@@M@@3R_x@@`，故 `@@M@@N(K,L)\ge|X|@@`；另一方面，支撑函数 (support function) 恰为 `@@M@@h_K(\delta)=3\|f_\delta\|_{\infty,X}+t\|\delta\|_1@@`，把逼近表按"最先命中"分成 `@@M@@M@@` 簇并各选一个真实系数向量作代表，即得 `@@M@@N(L^\circ,(6\varepsilon+2t)K^\circ)\le M@@`。于是反例归结为：造一个行很多、列凸包的逼近表却很短的矩阵。

再证压缩定理（第 3 节），这是全文最可复用的一步。设有限集 `@@M@@X@@` 带 `@@M@@u@@` 个至多 `@@M@@q@@` 类的划分；两点若在某划分 `@@M@@i\in T@@` 中同类则相连，得图距离 `@@M@@d_T@@`；列取对数轮廓 (logarithmic profile) `@@M@@g_{(v,T)}(x)=\phi_h(d_T(x,v))@@`。断言：总质量 `@@M@@\le1@@` 的非负列组合有一致逼近表，`@@M@@\log Q\le hs\log q+C_{h,\theta,u}@@`，关键在于代价只依赖标签数 `@@M@@q@@` 而与 `@@M@@|X|@@` 无关。证明先用平均论证找到一个除 `@@M@@\theta@@` 质量外都在场的公共划分 `@@M@@i_0@@`；再在每个距离层用贪心法选至多 `@@M@@s=\lceil1/\theta\rceil@@` 个支点，捕获每个点处除 `@@M@@\theta@@` 外的全部质量；点睛之笔是把支点替换成它在 `@@M@@i_0@@` 划分中的类代表——编码只需存储标签而非原点，代价是距离从 `@@M@@j@@` 膨胀到 `@@M@@3j+2@@`，而对数轮廓恰好把该膨胀的误差压到 `@@M@@\log3/\log(h+1)\le\theta@@`；最后把权重舍入到固定粒度再计数。符号情形拆 `@@M@@\lambda=\lambda^+-\lambda^-@@`，得长 `@@M@@Q^2@@`、误差 `@@M@@6\theta@@` 的逼近表。

然后用有限域造划分并分离行（第 4 节）。取 `@@M@@X@@` 为 `@@M@@\F_p^r@@` 上全体对称 `@@M@@h@@` 线性型 (symmetric `@@M@@h@@`-linear form)，`@@M@@|X|=p^{D_h}@@`，`@@M@@D_j=\binom{r+j-1}{j}@@`；随机取方向 `@@M@@t_1,\ldots,t_u@@`，划分取收缩 (contraction) `@@M@@L_i(x)=x(t_i,\cdot,\ldots,\cdot)@@`，标签至多 `@@M@@q=p^{D_{h-1}}@@` 个，而 `@@M@@D_{h-1}/D_h=h/(r+h-1)\to0@@`。Schwartz–Zippel 多项式零点估计配合对角多项式恢复与联合界表明：以正概率，每个非零型删去 `@@M@@\theta@@` 份额的方向后，在剩余指标的任意 `@@M@@h@@` 元组（允许重复）上取值非零。假如图中存在长度 `@@M@@\le h@@` 的路径连接相异两点 `@@M@@x,y@@`，则 `@@M@@Z=y-x@@` 分解为沿路径的增量之和，每个增量都被路径上某方向杀死，由对称性 `@@M@@Z@@` 在由这些方向拼成的 `@@M@@h@@` 元组上必为零——矛盾。故 `@@M@@d_T(x,y)>h@@`，行分离恰为 `@@M@@1@@`。

最后按依赖顺序选参数（第 5 节）：先固定 `@@M@@\theta=1/(1000a)@@`、`@@M@@h@@` 与 `@@M@@r@@`（使 `@@M@@r+h-1>8bh^2s@@`），最后取足够大的素数 `@@M@@p@@` 把全部编码常数 `@@M@@C@@` 吸收掉，得 `@@M@@\log(Q^2)/\log|X|<1/(2b)@@`，与前面的估计拼起来正是 `@@M@@b\log N(L^\circ,a^{-1}K^\circ)<\log N(K,L)@@`。素数最后才选——这一依赖顺序是压垮对偶猜想的最后一击。

## 可信度与备注

本文主定理已有 Lean 形式化证明（结果族 329，见 lean/docs/329.md），属验证等级最高的一档；论证链的四个环节在文中均自足给出，不依赖外部黑箱。本结果族目前仅此一篇手稿，其结论与文献中的正面结果并不矛盾——椭球情形与凸化堆积情形的定理恰好不覆盖此处的一般对称凸体，反例正落在缝隙里。按 OpenAI 官方声明，"未经形式化的结果可能有问题"；本篇主定理已形式化，不在此列，但文中渐近形式与推论是否同在形式化范围内，请以社区核验为准。

{% endraw %}
