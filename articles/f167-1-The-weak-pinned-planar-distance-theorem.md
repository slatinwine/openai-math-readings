---
layout: default
title: "The weak pinned planar distance theorem"
family: "167"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The weak pinned planar distance theorem

> 结果族 167：Planar distinct distances and unit-distance bounds　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

想象操场上站着 `@@M@@n@@` 个同学，每人环顾四周，报出"我到大家的距离有多少种不同取值"。这篇论文证明：几乎每个人的答案都大得惊人——距离取值至少有 `@@M@@n^{1-\varepsilon}@@` 种，想要多接近 `@@M@@n@@` 都行；只能看到很少种距离的"宅点"，占比必然趋于零。这就是 Erdős 1957 年提出、悬置近七十年的钉点不同距离猜想的弱形式，而且结论对一切点集一致成立，不设任何分离性或一般位置假设。

**关键词卡片**

- 不同距离（distinct distances）：`@@M@@n@@` 个点两两之间能数出多少种互不相同的距离长度
- 钉点（pinned）：把所有距离固定从同一个出发点丈量，看单个点能"看到"多少种
- 例外点（exceptional points）：只看到很少种距离的点，例如圆心；定理证明其占比为 `@@M@@o(n)@@`，即随 `@@M@@n@@` 增大占比趋近于零
- 距离纤维（distance fiber）：与钉点等距的所有点构成的"同距圈"

**看个具体例子**

最天然的例外点是圆心：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="16" fill="#333">圆心是天然的"例外点"</text>
  <circle cx="280" cy="150" r="85" fill="none" stroke="#333" stroke-width="1.5"/>
  <line x1="280" y1="150" x2="365" y2="150" stroke="#aaa" stroke-width="1" stroke-dasharray="4 3"/>
  <line x1="280" y1="150" x2="340" y2="210" stroke="#aaa" stroke-width="1" stroke-dasharray="4 3"/>
  <line x1="280" y1="150" x2="280" y2="235" stroke="#aaa" stroke-width="1" stroke-dasharray="4 3"/>
  <line x1="280" y1="150" x2="220" y2="210" stroke="#aaa" stroke-width="1" stroke-dasharray="4 3"/>
  <line x1="280" y1="150" x2="195" y2="150" stroke="#aaa" stroke-width="1" stroke-dasharray="4 3"/>
  <line x1="280" y1="150" x2="220" y2="90" stroke="#aaa" stroke-width="1" stroke-dasharray="4 3"/>
  <line x1="280" y1="150" x2="280" y2="65" stroke="#aaa" stroke-width="1" stroke-dasharray="4 3"/>
  <line x1="280" y1="150" x2="340" y2="90" stroke="#aaa" stroke-width="1" stroke-dasharray="4 3"/>
  <circle cx="365" cy="150" r="4" fill="#333"/>
  <circle cx="340" cy="210" r="4" fill="#333"/>
  <circle cx="280" cy="235" r="4" fill="#333"/>
  <circle cx="220" cy="210" r="4" fill="#333"/>
  <circle cx="195" cy="150" r="4" fill="#333"/>
  <circle cx="220" cy="90" r="4" fill="#333"/>
  <circle cx="280" cy="65" r="4" fill="#333"/>
  <circle cx="340" cy="90" r="4" fill="#333"/>
  <circle cx="280" cy="150" r="6" fill="#c0392b"/>
  <text x="292" y="147" font-size="13" fill="#c0392b">圆心 O</text>
  <text x="280" y="256" text-anchor="middle" font-size="14" fill="#555">圆心到圆上每点等距：只看到 1 种距离（半径）</text>
  <text x="280" y="276" text-anchor="middle" font-size="14" fill="#555">定理：这样的例外点只占 o(n)，其余点各看到至少 n^(1−ε) 种距离</text>
</svg>

</div>

定理代入数字：`@@M@@n=10^6@@`、`@@M@@\varepsilon=0.01@@` 时，`@@M@@n^{1-\varepsilon}\approx 8.7\times10^5@@`——除占比趋零的点外，每个点都各自张出至少约 87 万种互异距离。

**为什么值得关心**

全局版不同距离问题已被 Guth–Katz 解决，而逐点的钉点版本此前最好结果只有 `@@M@@n^{0.864}@@`；本文一举推到 `@@M@@n^{1-\varepsilon}@@`；其工具箱（复坐标分解、数域乘积公式、实闭域转移）与姊妹篇单位距离上界共享，互相印证，且主结果已通过机器核验。

> 已 Lean 形式化

## 一句话结论

证明了弱钉点 Erdős 不同距离猜想：对任何固定 `@@M@@\varepsilon>0@@`，任何 `@@M@@n@@` 点平面点集中除 `@@M@@o(n)@@` 个例外点外，每个点都与其余点张出至少 `@@M@@n^{1-\varepsilon}@@` 个互异距离——Erdős 1957 年提出的这一公开问题得到肯定解决。

## 问题背景

1946 年 Erdős 开创了平面不同距离问题（distinct distances）：`@@M@@n@@` 个点的平面点集最少确定多少个互异距离？平方格点集给出约 `@@M@@n/\sqrt{\log n}@@` 个距离的构形，Guth 与 Katz 证明了 `@@M@@n/\log n@@` 的下界，全局版本基本解决。但"钉点"（pinned）版本要求这些距离共享同一个源点：对 `@@M@@x\in P@@` 记 `@@M@@D_x(P)=\{\|y-x\|_2:y\in P\setminus\{x\}\}@@`，问是否必有点使 `@@M@@|D_x(P)|@@` 很大。Erdős 1957 年明确提出了这一弱问题。此前最好结果是 Solymosi–Tóth 的 `@@M@@n^{6/7}@@`，Tardos 与 Katz–Tardos 借助熵不等式把指数推到 `@@M@@0.864137\ldots@@`，与完整猜想的目标 `@@M@@n/\sqrt{\log n}@@` 相距甚远。卡点在于：Guth–Katz 的全局估计对所有源点取并，无法锁定单个钉点；而"圆周加圆心"的构形中圆心只看到一个距离，说明例外点集天然存在，须证明它只占 `@@M@@o(n)@@`。

## 主要结果

论文核心定理控制"距离纤维"（distance fiber）的规模：对相异 `@@M@@x,y\in P@@`，令 `@@M@@k_P(x,y)@@` 为与 `@@M@@y@@` 到 `@@M@@x@@` 等距的点数（含 `@@M@@y@@` 本身），`@@M@@F_n(s)@@` 定义为在一切 `@@M@@n@@` 点集上、满足 `@@M@@k_P(x,y)\ge n^s@@` 的有序对所占比例的上确界。定理断言：对每个固定 `@@M@@s>0@@`，`@@M@@F_n(s)\to 0@@`，且对一切构形一致成立，不设分离性或一般位置假设。由它直接推出推论：对每个固定 `@@M@@\varepsilon>0@@`，满足 `@@M@@|D_x(P)|<n^{1-\varepsilon}@@` 的钉点占比趋于 `@@M@@0@@`；特别地，每个足够大的 `@@M@@n@@` 点平面集必存在一个钉点，张出至少 `@@M@@n^{1-\varepsilon}@@` 个互异非零距离。这正是弱钉点 Erdős 猜想的完整陈述。

## 证明思路

证明用反证法，分四步推进。

先做极值归约。假设 `@@M@@F_n(s)\not\to 0@@`，沿近极值序列抽出边密度趋于正数 `@@M@@\theta@@` 的有向图，边按（源点、平方距离）分成纤维（fiber），每条纤维大小 `@@M@@\ge n^{s-o(1)}@@`，并附带一条子集估计：小集合抓不住多少纤维质量。再用实闭域的转移原理（transfer for real closed fields）把坐标替换为实代数数，一切距离等式与不等式原样保留。

再搭建算术引擎。取包含全部坐标的数域 `@@M@@K@@`，令 `@@M@@Z_1=u+\mathrm{i}v@@`、`@@M@@Z_2=u-\mathrm{i}v@@`，则平方距离分解为 `@@M@@\|x-y\|_2^2=(Z_1(y)-Z_1(x))(Z_2(y)-Z_2(x))@@`，于是在一条等距纤维上第二坐标是第一坐标的分式线性函数。归一化乘积公式（product formula）`@@M@@\sum_v\sigma_v\log|z|_v=0@@` 表明两个坐标的对数深度在所有绝对值上加权平衡。为把它变成有限恒等式，在每个位上构造嵌套分割（nested partitions）：有限位由超度量不等式免费给出；复嵌入处用随机平移、随机旋转的嵌套方格网（Arora 式随机剖分），其共享深度与真实深度之误差与点对无关且指数衰减。把质量超过 `@@M@@n/2@@` 的巨胞（giant）换成补集后积分，得到加性重叠恒等式 `@@M@@L^*(x,y)=b_*+S^*(x)+S^*(y)@@`——凡总质量与两边际之和皆为零的符号测度，对 `@@M@@L^*@@` 的积分严格为零。

接着做方差估计。构造符号测度 `@@M@@P_B-2R_B+\pi@@`，它恰好零总质量、零边际和，代入上述恒等式并对胞概率展开，得到纤维质量 `@@M@@p@@` 与均匀质量 `@@M@@a@@` 之差的平方 `@@M@@(p-a)^2@@` 加上显式的有限总体修正。关键在于全程只采样相异点对：单点胞上的三项概率严格相消，无穷的单点层尾从不被积分。结论是纤维律与入边条件律都逼近均匀律到 `@@M@@o(W+1)@@`，其中 `@@M@@W@@` 为总重叠尺度。

最后按 `@@M@@W@@` 二分排除。若 `@@M@@W\to\infty@@`，保留质量与补质量都有下界的胞并组织成加权有根树；纤维方程把一棵树中源到目标的距离折算成另一棵树中只依赖目标的根到目标距离，树上传输（transport on trees）再把到达同一目标的两源替换为独立均匀点，于是两距离之差的期望可忽略，与树上距离的初等几何下界矛盾。若 `@@M@@W@@` 有界，则选取方差最小的复嵌入并归一化坐标，使均匀坐标律收敛到非原子极限 `@@M@@\beta_1,\beta_2@@`；纤维方程逼出一族 Möbius 变换把 `@@M@@\beta_1@@` 映为 `@@M@@\beta_2@@`，而第一个源坐标与整个目标对独立，令其逼近目标坐标，对数距离差在概率中塌缩，但像点的对数目标距离律即使允许加性常数也有正散布——矛盾。两种情形皆不可能，定理得证。

## 可信度与备注

本文主定理及推论已有 Lean 形式化证明，验证等级在同族中最高。姊妹篇《A power saving for planar unit distances》从单位距离上界一侧使用同一套"复坐标分解＋数域乘积公式＋实闭域转移"工具箱，两文互相印证技术路线；但该姊妹篇本身尚未形式化。按 OpenAI 官方声明，未经形式化的结果可能有问题，而本文主结果已通过机器核验。

{% endraw %}
