---
layout: default
title: "Weighted dilation graphs, smooth shifted primes and totient fibers"
family: "011"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Weighted dilation graphs, smooth shifted primes and totient fibers

> 结果族 011：Prime-factor statistics of `@@M@@`p-1`@@`　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

把欧拉函数 `@@M@@\varphi(m)@@` 想成一台"缩水机"：输入整数 `@@M@@m@@`，输出 1 到 `@@M@@m@@` 中与 `@@M@@m@@` 互素的个数。这台机器远非"一机一码"——很多不同的输入会被压成同一个输出。Erdős 在 1956 年问：同一个输出的"重名名单"最长能有多长？这篇论文彻底回答：几乎能和输出值本身一样长。

**关键词卡片**

- 欧拉函数（Euler's totient function `@@M@@\varphi@@`）：数出不超过 `@@M@@m@@` 且与 `@@M@@m@@` 互素的正整数个数，如 `@@M@@\varphi(6)=2@@`。
- 纤维（fiber）：被压成同一个输出 `@@M@@n@@` 的全部输入，其个数 `@@M@@g(n)@@` 就是名单的长度。
- 平滑移位素数（smooth shifted prime）：素数 `@@M@@p@@` 的前一项 `@@M@@p-1@@`，它的所有素因子都很小。
- 最大素因子（largest prime factor `@@M@@P^+@@`）：一个数的分解中最大的那个素数。
- 筛法（sieve）：用同余条件像筛沙子一样层层剔除合数、留下素数的方法。

**看个具体例子**

以 `@@M@@n=24@@` 为例：`@@M@@\varphi(35)=\varphi(39)=\varphi(45)=\varphi(52)=\varphi(56)=\varphi(70)=\varphi(72)=\varphi(78)=\varphi(84)=\varphi(90)=24@@`，一共 10 个输入挤在同一个输出上。主定理说：对任意 `@@M@@\varepsilon>0@@`，有无穷多个 `@@M@@n@@` 的名单长到 `@@M@@g(n)>n^{1-\varepsilon}@@`，逼近理论上限。机器的关键燃料是定理二：大量素数 `@@M@@p@@` 的前身 `@@M@@p-1@@` 没有超过 `@@M@@x^\delta@@` 的素因子。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <rect x="24" y="20" width="64" height="30" rx="8" fill="#e8eef8" stroke="#345"/>
  <text x="56" y="40" font-size="15" text-anchor="middle">35</text>
  <rect x="24" y="64" width="64" height="30" rx="8" fill="#e8eef8" stroke="#345"/>
  <text x="56" y="84" font-size="15" text-anchor="middle">39</text>
  <rect x="24" y="108" width="64" height="30" rx="8" fill="#e8eef8" stroke="#345"/>
  <text x="56" y="128" font-size="15" text-anchor="middle">45</text>
  <rect x="24" y="152" width="64" height="30" rx="8" fill="#e8eef8" stroke="#345"/>
  <text x="56" y="172" font-size="15" text-anchor="middle">52</text>
  <rect x="24" y="196" width="64" height="30" rx="8" fill="#e8eef8" stroke="#345"/>
  <text x="56" y="216" font-size="15" text-anchor="middle">…</text>
  <line x1="88" y1="35" x2="238" y2="128" stroke="#99a"/>
  <line x1="88" y1="79" x2="238" y2="134" stroke="#99a"/>
  <line x1="88" y1="123" x2="238" y2="140" stroke="#99a"/>
  <line x1="88" y1="167" x2="238" y2="146" stroke="#99a"/>
  <line x1="88" y1="211" x2="238" y2="152" stroke="#99a"/>
  <rect x="238" y="112" width="124" height="56" rx="10" fill="#ffffff" stroke="#345" stroke-width="2"/>
  <text x="300" y="145" font-size="16" text-anchor="middle">φ 缩水机</text>
  <line x1="362" y1="140" x2="422" y2="140" stroke="#345" stroke-width="2"/>
  <polygon points="432,140 420,134 420,146" fill="#345"/>
  <rect x="436" y="110" width="90" height="60" rx="10" fill="#fdf6e3" stroke="#345" stroke-width="2"/>
  <text x="481" y="138" font-size="22" font-weight="bold" text-anchor="middle">24</text>
  <text x="481" y="158" font-size="12" text-anchor="middle">纤维 g(24)=10</text>
  <text x="280" y="262" font-size="14" text-anchor="middle">10 个不同输入被压成同一个输出：φ(m)=24 共有 10 个解，定理保证无穷多次更拥挤</text>
</svg>

</div>

**为什么值得关心**

它解决了悬置近七十年的 Erdős 猜想；其中的关键原料——大量"前身很平滑"的素数——也是构造 Carmichael 数等经典难题的发动机。同族两篇姊妹论文共用本文新造的筛法机器，分别证明了素数前驱的折棍极限律与因子个数的奇偶定理。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了 Erdős 关于欧拉函数（Euler's totient function）最大纤维的猜想：对任意 `@@M@@\varepsilon>0@@`，有无穷多个 `@@M@@n@@` 使 `@@M@@g(n)=\#\{m:\varphi(m)=n\}>n^{1-\varepsilon}@@`；核心输入是对每个固定 `@@M@@\delta>0@@`，存在 `@@M@@x^{1-o(1)}@@` 个素数 `@@M@@p@@` 使 `@@M@@p-1@@` 没有超过 `@@M@@x^\delta@@` 的素因子。

## 问题背景

欧拉函数 `@@M@@\varphi(m)@@` 计数不超过 `@@M@@m@@` 且与 `@@M@@m@@` 互素的正整数个数，它远非单射：同一个函数值可以有许多原像。记纤维（fiber）大小 `@@M@@g(n)=\#\{m\ge1:\varphi(m)=n\}@@`。Erdős 早在 1935 年就研究欧拉函数的重数与平滑移位素数，并在 1956 年提出猜想（Pomerance 1980 年将其表述为常数 `@@M@@C=1@@`）：`@@M@@g(n)>n^c@@` 对任意接近 `@@M@@1@@` 的指数 `@@M@@c@@` 都无穷多次成立。另一方面有初等上界 `@@M@@g(n)\ll_\eta n^{1+\eta}@@`，故指数 `@@M@@1@@` 是最优目标。这一猜想的算术核心是平滑移位素数（smooth shifted primes）：需要大量素数 `@@M@@p@@`，使其前身 `@@M@@p-1@@` 的全部素因子都小于 `@@M@@p@@` 的任意固定幂。此前最好结果都停留在固定的平滑指数上：Baker–Harman 达到 `@@M@@P^+(p-1)\le x^{0.2961}@@`（相应纤维指数 `@@M@@0.7039@@`），Lichtman 改进到 `@@M@@\beta>15/(32\sqrt e)=0.2843\ldots@@`（纤维指数 `@@M@@0.7156@@`，计数 `@@M@@x/(\log x)^C@@`）；而 Dickman 律预测每个固定指数下应占正比例。难点在于：候选序列的因子结构被严格约束，同余计数只能给出初步筛法，必须再引入双线性抵消才能剔除合成数——这正是 Friedlander–Iwaniec 型素数探测筛法的经典分工，本文把该框架推广到了权重与位移交织的新情形。

## 主要结果

论文证明两条定理。**定理一（大纤维）**：对每个实数 `@@M@@\varepsilon>0@@`，存在无穷多个正整数 `@@M@@n@@` 使 `@@M@@g(n)>n^{1-\varepsilon}@@`；结合上界 `@@M@@g(n)\ll_\eta n^{1+\eta}@@`，幂指数最优，Erdős 猜想由此完全解决。**定理二（平滑移位素数）**：对每个固定 `@@M@@0<\delta<1/4@@`（稍作变换即对任意固定 `@@M@@\delta>0@@` 成立），当 `@@M@@x\to\infty@@` 时

`@@M@@D\#\{p\ \text{素数}：2x<p\le 5x,\ P^+(p-1)\le x^\delta\}\ge x^{1-o(1)}，@@`

其中 `@@M@@P^+(m)@@` 表示最大素因子（largest prime factor），`@@M@@o(1)@@` 可依赖于 `@@M@@\delta@@`。特别地，有无穷多素数 `@@M@@p@@` 满足 `@@M@@P^+(p-1)\le p^\varepsilon@@`。`@@M@@x^{1-o(1)}@@` 无条件地给出了计数的完整幂指数，但仍弱于正比例的 Dickman 预测（后者在 Elliott–Halberstam 猜想下由 Bharadwaj–Rodgers 的框架导出）。此外，平滑前身正是 Alford–Granville–Pomerance 构造 Carmichael 数的关键原料，故这一估计在因数分解问题之外另有应用。

## 证明思路

证明分两大步。第一步是解析机制，目标是在因子受约束的序列中检出素数：候选数取 `@@M@@2u+1@@`，把 `@@M@@u@@` 的素因子布置在多个对数尺度上——一部分落在互不相交的"小群/大群"素数区间（群数约 `@@M@@\log\log x@@`，指数上界 `@@M@@d<0.47@@`），其权重标记互异的群素因子；其余因子排成几何尺度带，便于凑出接近指定大小的因子；再配一条没有小素因子的粗糙（rough）长因子。全新的核心工具是加权膨胀图（weighted dilation graph）的传递定理（transference theorem）：物理图的顶点是整数及其各群素因子列表，边为位移 `@@M@@kD@@`（`@@M@@D@@` 为两端共享素数与自由素数之积）；与之比较的理想算子（ideal operator）在独立标签上运行，标签概率正比于 `@@M@@1/p@@` 且允许重复。先证理想算子的范数小：以对数局部化、特征标核（character kernel）与两块坐标分解把共享素数乘积换成独立乘积，再用置换对称性压低均零分量、以带符号的比较项抵消其余分量；接着通过中国剩余定理平均整根，把小的理想范数转移到物理图上——重复的整除查询只付一次 `@@M@@1/p@@` 的代价，一个"记忆"结构在活跃使用之间保存同余，秩扩张恢复互异素数的"出生"，最终得到物理图的高阶矩平均，从而在移位配对中产生抵消。然后把移位相关转化为 `@@M@@mn=2u+1@@` 的 Type II 估计：概率性地拆分几何素数带，选出与 `@@M@@m@@` 同尺度的因子，经 Cauchy–Schwarz 后，非对角分解凭一个精确的行列式恒等式化为移位端点，于是余因子上的素性与粗糙性检验可换成初等粗糙代理；最后用同余估计与 Brun–Hooley 型加权筛剔除合成值，两个素因子都接近 `@@M@@x^{1/2}@@` 的平衡情形由单独的上界筛处理，得到定理二。第二步是 Erdős–Pomerance 的乘积—抽屉论证（第 7 节给出完整证明）：取 `@@M@@M>X^{1-\delta}@@` 个 `@@M@@p\le X@@` 且 `@@M@@p-1@@` 为 `@@M@@X^\delta@@`-平滑的素数，令 `@@M@@k=\lfloor X^{2\delta}\rfloor@@`，则 `@@M@@\binom Mk\ge X^{(1-3\delta)k}@@` 个互异的平方自由乘积的 `@@M@@\varphi@@` 值都是 `@@M@@X^\delta@@`-平滑、不超过 `@@M@@X^k@@` 的数，而此类数值至多 `@@M@@(1+k\log X/\log 2)^{X^\delta}=X^{o(k)}@@` 种可能；由抽屉原理，某个 `@@M@@n\le X^k@@` 的纤维必超过 `@@M@@X^{(1-3\delta-o(1))k}>n^{1-\varepsilon}@@`。

## 可信度与备注

本篇为 OpenAI 发布的数学手稿，主结果暂无 Lean 形式化证明，也未经过传统同行评审，请以社区核验为准；OpenAI 官方声明"未经形式化的结果可能有问题"。文中的膨胀图与核估计同时充当姊妹篇《The Poisson–Dirichlet law for prime predecessors》的输入，那篇证明 `@@M@@p-1@@` 素因子的规范化对数联合收敛于 Poisson–Dirichlet 律 `@@M@@\mathrm{PD}(1)@@`，解决 Ford–Konyagin–Luca 猜想；族内另一篇《Prime Predecessors with an Even Number of Prime Factors》则证明有无穷多素数 `@@M@@p@@` 使 `@@M@@\mu(p-1)=1@@`。三篇共享同一套针对 `@@M@@p-1@@` 素因子结构的分析方法，结论互相支撑。

{% endraw %}
