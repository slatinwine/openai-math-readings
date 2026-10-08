---
layout: default
title: "Beyond the Square-Root Exponent for Depth-Three Boolean Circuits"
family: "112"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Beyond the Square-Root Exponent for Depth-Three Boolean Circuits

> 结果族 112：Beyond the square-root exponent for depth-three circuits　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把"判断一串 0/1 输入是否合格"的机器想成一条三层流水线：最底层一群"或门"扫局部特征，中层"与门"把特征拼成一张张清单，顶层一个"或门"只要任何清单点头就放行。这样的三层流水线（OR–AND–OR 电路）判同一个问题，最多能省多少零件？本文造出一个具体问题：用普通计算机多项式时间就能判定，但任何这种流水线无论怎么搭，零件总数都会超过 2^(A√n)——A 取多大的常数都拦不住。

**关键词卡片**

- 深度三电路（depth-three circuit）：无界扇入的 OR–AND–OR 三层电路，等价于若干 CNF 之或。
- 显式语言（explicit language）：被证明存在多项式时间判定算法的具体问题，不是抽象存在性构造。
- 电路下界（circuit lower bound）：证明某函数用某类电路"至少需要多少个门"。
- 门数（gate count / S₃(f)）：AND、OR 门总数，底层门与输出门都计入。
- 平方根壁垒（square-root barrier）：此前所有显式下界都停在"常数×√n"的指数量级。

**看个具体例子**

n=10000 位输入时 √n=100。旧纪录形如"超过 `@@M@@2^{3\sqrt n}=2^{300}@@` 个门"，常数被技巧钉死；新语言的判定函数满足：任给 A=5，只要 n 足够大，门数 `@@M@@>2^{5\sqrt n}@@`，且同一个语言对付所有常数 A——写成数字版定理就是 `@@M@@\lim_{n\to\infty}\frac{\log_2 S_3(f_n)}{\sqrt n}=\infty@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="24" text-anchor="middle" font-size="15" fill="#333333">深度三电路（OR–AND–OR）：要数的是全部门的总数</text>
  <rect x="20" y="205" width="44" height="24" fill="#f4f4f4" stroke="#999999"/>
  <text x="42" y="222" text-anchor="middle" font-size="13" fill="#555555">x₁</text>
  <rect x="120" y="205" width="44" height="24" fill="#f4f4f4" stroke="#999999"/>
  <text x="142" y="222" text-anchor="middle" font-size="13" fill="#555555">x₂</text>
  <rect x="220" y="205" width="44" height="24" fill="#f4f4f4" stroke="#999999"/>
  <text x="242" y="222" text-anchor="middle" font-size="13" fill="#555555">x₃</text>
  <rect x="320" y="205" width="44" height="24" fill="#f4f4f4" stroke="#999999"/>
  <text x="342" y="222" text-anchor="middle" font-size="13" fill="#555555">x₄</text>
  <rect x="420" y="205" width="44" height="24" fill="#f4f4f4" stroke="#999999"/>
  <text x="442" y="222" text-anchor="middle" font-size="13" fill="#555555">x₅</text>
  <line x1="42" y1="205" x2="75" y2="132" stroke="#aaaaaa"/>
  <line x1="142" y1="205" x2="105" y2="132" stroke="#aaaaaa"/>
  <line x1="242" y1="205" x2="185" y2="132" stroke="#aaaaaa"/>
  <line x1="342" y1="205" x2="315" y2="132" stroke="#aaaaaa"/>
  <line x1="442" y1="205" x2="455" y2="132" stroke="#aaaaaa"/>
  <rect x="60" y="132" width="60" height="28" rx="6" fill="#eef4fb" stroke="#3b82c4" stroke-width="2"/>
  <text x="90" y="151" text-anchor="middle" font-size="14" fill="#3b82c4">或门</text>
  <rect x="170" y="132" width="60" height="28" rx="6" fill="#eef4fb" stroke="#3b82c4" stroke-width="2"/>
  <text x="200" y="151" text-anchor="middle" font-size="14" fill="#3b82c4">或门</text>
  <rect x="300" y="132" width="60" height="28" rx="6" fill="#eef4fb" stroke="#3b82c4" stroke-width="2"/>
  <text x="330" y="151" text-anchor="middle" font-size="14" fill="#3b82c4">或门</text>
  <rect x="430" y="132" width="60" height="28" rx="6" fill="#eef4fb" stroke="#3b82c4" stroke-width="2"/>
  <text x="460" y="151" text-anchor="middle" font-size="14" fill="#3b82c4">或门</text>
  <line x1="90" y1="132" x2="170" y2="96" stroke="#aaaaaa"/>
  <line x1="200" y1="132" x2="192" y2="96" stroke="#aaaaaa"/>
  <line x1="330" y1="132" x2="352" y2="96" stroke="#aaaaaa"/>
  <line x1="460" y1="132" x2="372" y2="96" stroke="#aaaaaa"/>
  <rect x="150" y="68" width="64" height="28" rx="6" fill="#fdeee6" stroke="#e0592a" stroke-width="2"/>
  <text x="182" y="87" text-anchor="middle" font-size="14" fill="#e0592a">与门</text>
  <rect x="340" y="68" width="64" height="28" rx="6" fill="#fdeee6" stroke="#e0592a" stroke-width="2"/>
  <text x="372" y="87" text-anchor="middle" font-size="14" fill="#e0592a">与门</text>
  <line x1="182" y1="68" x2="268" y2="62" stroke="#aaaaaa"/>
  <line x1="372" y1="68" x2="292" y2="62" stroke="#aaaaaa"/>
  <rect x="248" y="34" width="64" height="28" rx="6" fill="#eef4fb" stroke="#3b82c4" stroke-width="2"/>
  <text x="280" y="53" text-anchor="middle" font-size="14" fill="#3b82c4">或门</text>
  <text x="325" y="53" font-size="13" fill="#555555">→ 输出</text>
  <text x="280" y="258" text-anchor="middle" font-size="13" fill="#555555">扇入不限；存在多项式可判定的问题，任何此类电路的门数 &gt; 2^(A·√n)</text>
</svg>

</div>

**为什么值得关心**

显式电路下界是理论计算机科学最难的方向之一；本文首次让一个"好算"的函数把平方根指数远远甩开，且结论在每个充分大的输入长度上同时成立。

> 已 Lean 形式化

## 一句话结论

构造出一个确定性多项式时间语言：其 `@@M@@n@@` 位成员函数在无界扇入 OR–AND–OR 电路中所需总门数，在一切充分长的长度上超过 `@@M@@2^{A\sqrt n}@@`（`@@M@@A@@` 为任意常数），即达到 `@@M@@2^{\omega(\sqrt n)}@@`，首次突破显式深度三电路下界的平方根指数壁垒。

## 问题背景

深度三电路（depth-three circuit）即无界扇入的 OR–AND–OR 电路——若干合取范式（CNF）的或——是显式电路下界的经典试验场。Håstad 的随机限制（random restriction）与切换引理（switching lemma）证明奇偶函数（parity）需 `@@M@@2^{\Omega(\sqrt n)}@@` 门；Håstad–Jukna–Pudlák 的自顶向下方法改进常数，Paturi–Pudlák–Zane 的可满足性编码引理（satisfiability coding lemma）得到最优的 `@@M@@\Omega(n^{1/4}2^{\sqrt n})@@`——奇偶函数本身就此"到顶"。此后显式下界的指数都停在"常数乘 `@@M@@\sqrt n@@`"量级。能否让一个多项式时间语言对每个常数 `@@M@@A>0@@` 都需要多于 `@@M@@2^{A\sqrt n}@@` 个门，且在每个充分大长度同时成立？"一个"很关键：语言及判定算法须在 `@@M@@A@@` 之前固定，此问题至今列为公开（GPPST24 第 1.1 节等）。限制底层扇入（bottom fan-in）的模型已有 `@@M@@2^{n-o(n)}@@` 级结果，但任意扇入下任何函数都是单个 CNF，只有总门数才有意义。

## 主要结果

**主定理（定理 1.1）。** 存在语言 `@@M@@L\subseteq\{0,1\}^*@@` 与一台确定性图灵机以 `@@M@@C(n+1)^a@@` 时间判定它，使成员函数 `@@M@@f_n@@` 满足
`@@M@@D\lim_{n\to\infty}\frac{\log_2 S_3(f_n)}{\sqrt n}=\infty,@@`
等价地：对任意 `@@M@@A>0@@` 存在 `@@M@@N_A@@`，使一切 `@@M@@n\ge N_A@@` 都有 `@@M@@S_3(f_n)>2^{A\sqrt n}@@`。`@@M@@S_3(f)@@` 是计算 `@@M@@f@@` 的 OR–AND–OR 电路中 AND、OR 门总数（底层门与输出门都计入，输入取反免费），不施加一致性（uniformity）或底层扇入限制。

**语言构造（定义 5.1）。** 输入长 `@@M@@n@@` 时取 `@@M@@d=\lfloor n/5\rfloor@@`、`@@M@@r=\lceil d^{2/3}\rceil@@`、`@@M@@t@@` 为 `@@M@@t^6\le d@@` 的最大偶数，输入切成四块：`@@M@@d@@` 个数据位 `@@M@@x@@`；`@@M@@d+r-1@@` 个哈希位 `@@M@@u@@`；`@@M@@r@@` 位编码首一多项式 `@@M@@P\in\mathbb{F}_2[Z]@@`；`@@M@@t@@` 个 `@@M@@r@@` 位块编码商环 `@@M@@R_P=\mathbb{F}_2[Z]/(P)@@` 中元素 `@@M@@\beta_0,\dots,\beta_{t-1}@@`。用 Toeplitz 型矩阵把 `@@M@@x@@` 线性哈希为 `@@M@@h(x)\in R_P@@`，当 `@@M@@\lambda\bigl(\sum_j\beta_j h(x)^j\bigr)=0@@`（`@@M@@\lambda@@` 取常数项系数）时接受。判定只需 `@@M@@O(rd+tr^2)@@` 位运算，从不检验 `@@M@@P@@` 是否不可约。

## 证明思路

整体走相关性（correlation）路线：设 `@@M@@g@@` 为目标函数的符号。中间层 CNF `@@M@@H@@` 若喂给恰好表示该函数的顶层 OR，就只接受正例，故 `@@M@@gH=H@@`；只要 `@@M@@g@@` 与一切 CNF 相关性都小，至多 `@@M@@S@@` 个中间门的接受概率之和就盖不住切片的常数接受密度。难点在子句数无界，而切换引理会换范式。证明分三步绕过。

第一步证与子句数无关的限制引理（引理 3.1）：以 `@@M@@p\le 1/2@@`（`@@M@@pk@@` 有界）做随机限制，把限制后的宽 `@@M@@k@@` CNF 展开成带符号的宽 `@@M@@b@@` CNF 组合，期望总绝对系数质量至多 `@@M@@1/(1-\theta)\le 2@@`，与子句个数无关。展开沿"连续同时违反子句"的路径做，再逆向计数：每步用违反子句数的倒数抵消子句个数，权重几何衰减。测试始终仍是 CNF，这是与切换引理的本质区别。

第二步证稀疏分解引理（引理 4.1）：用向日葵（sunflower）稀疏化加不相交加细，把 `@@M@@m@@` 变量上任意宽 `@@M@@b@@` CNF 分成至多 `@@M@@2^{\eta m}@@` 个两两不交、至多 `@@M@@Mm@@` 条子句的片段，使稀疏测试种数不超过 `@@M@@2^{Mm(1+b\log_2(2m+1))}@@`，联合界即可一次控制。

第三步构造硬切片（slice）：固定非数据位即得数据位上的符号 `@@M@@g@@`。取不可约 `@@M@@P@@` 使 `@@M@@R_P@@` 成域；随机 Toeplitz 哈希把每个非零差均匀散布，联合界给出限制立方上单射概率 `@@M@@\ge 1-2^{m-r}@@`；单射时多项式插值（interpolation）给出 `@@M@@t@@`-wise 独立无偏符号；偶数 `@@M@@t@@` 阶矩加 Markov 不等式给出所有稀疏测试相关性 `@@M@@\le 2^{-m/4}@@`，再经稀疏分解推到一切宽 `@@M@@b@@` CNF（`@@M@@2^{-m/8}@@`）。平均论证即可固定一组输入位——判定器从不搜索硬切片（承袭 PSZ00 输入索引思想）。

最后组合：固定 `@@M@@A@@`，取 `@@M@@s=3A@@`、`@@M@@B=64(s+1)@@`、`@@M@@k=\lceil 3(s+1)\sqrt d\rceil@@`、`@@M@@p=B/\sqrt d@@`，选仅依赖 `@@M@@A@@` 的 `@@M@@b@@` 使 `@@M@@\theta\le 1/2@@`。两条估计不需独立性：好限制用系数质量期望，坏限制相关性至多 1，故 `@@M@@|\E gH|\le 6\cdot 2^{-m_0/16}@@` 对一切宽 `@@M@@k@@` CNF 成立；常真测试推出切片接受密度 `@@M@@\ge 1/4@@`。反设电路共 `@@M@@S\le 2^{A\sqrt n}@@` 门：中间门至多 `@@M@@S@@` 个、每个至多 `@@M@@S@@` 条子句，删宽超 `@@M@@k@@` 的子句后单门误差 `@@M@@\le S2^{-k}@@`，求和得接受概率 `@@M@@\le 6S2^{-m_0/16}+S^22^{-k}\to 0@@`，与 `@@M@@\ge 1/4@@` 矛盾。`@@M@@A@@` 任意而语言不变，定理得证。

## 可信度与备注

验证状态：主结果已 Lean 形式化（族文档 lean/docs/112.md），这是目前最强的核验手段。本结果族仅此一篇手稿，无姊妹篇交叉印证，可靠性来自文内闭环与上述形式化。按 OpenAI 官方声明，"未经形式化的结果可能有问题"；本文主结果已跨过这道门槛，文献史转述仍以被引原文为准。

{% endraw %}
