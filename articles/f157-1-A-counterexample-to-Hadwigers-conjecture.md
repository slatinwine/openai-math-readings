---
layout: default
title: "A counterexample to Hadwiger's conjecture"
family: "157"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A counterexample to Hadwiger's conjecture

> 结果族 157：Graph coloring, clique minors, and Colin de Verdière invariants　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

给地图染色，相邻区域不同色，最少要几种颜色？这是图的色数 χ。另一把尺子：把图里若干连通块各自"捏成一点"，能捏出的最大完全图 Kₜ 的阶数 t，叫 Hadwiger 数 h。1943 年的 Hadwiger 猜想断言 χ≤h。这篇论文造出反例：颜色比"捏合能力"多得多的图真的存在。

**关键词卡片**

- 色数 χ（chromatic number）：正常染色所需的最少颜色数。
- Hadwiger 数（clique minor 数）h：收缩连通块后能得到的最大完全图的阶数。
- 独立数 α（independence number）：两两不相邻的最大点集大小；α≤2 意味着任意三点中必有边。
- 分数色数 χ_f（fractional chromatic number）：允许按比例"混色"的染色数，不超过 χ。
- 连通匹配（connected matching）：两两接触的不相交边组的最大规模。

**看个具体例子**

"捏出 K₄"长什么样：四个连通块两两有边相连，各缩成一点就得到 K₄：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="35" text-anchor="middle" font-size="16">收缩连通块，捏出完全图</text><line x1="150" y1="90" x2="410" y2="90" stroke="#888"/><line x1="150" y1="210" x2="410" y2="210" stroke="#888"/><line x1="150" y1="90" x2="150" y2="210" stroke="#888"/><line x1="410" y1="90" x2="410" y2="210" stroke="#888"/><line x1="150" y1="90" x2="410" y2="210" stroke="#888"/><line x1="410" y1="90" x2="150" y2="210" stroke="#888"/><ellipse cx="150" cy="90" rx="48" ry="28" fill="#d6eaf8" stroke="#333"/><ellipse cx="410" cy="90" rx="48" ry="28" fill="#d6eaf8" stroke="#333"/><ellipse cx="150" cy="210" rx="48" ry="28" fill="#d6eaf8" stroke="#333"/><ellipse cx="410" cy="210" rx="48" ry="28" fill="#d6eaf8" stroke="#333"/><text x="150" y="95" text-anchor="middle" font-size="14">块 A</text><text x="410" y="95" text-anchor="middle" font-size="14">块 B</text><text x="150" y="215" text-anchor="middle" font-size="14">块 C</text><text x="410" y="215" text-anchor="middle" font-size="14">块 D</text><text x="280" y="258" text-anchor="middle" font-size="14">每块缩成一点后：四点两两相连 = K₄</text></svg>

</div>

反例的数字版：图有 m 个点、独立数至多 2，于是每个色类至多 2 点，χ(G) 至少 m/2；而连通匹配不足 m/100，推出

`@@M@@h(G)<\tfrac{26m}{75}+\tfrac23<\tfrac m2\le\chi_f(G)\le\chi(G)@@`

取 m=15000：h(G) 小于 5201，而 χ(G) 至少 7500——颜色比最大团子式多出一大截，猜想连同分数版本被一并推翻。构造分三层：先用代数条件造"洞"保证任意三点有边，再用概率方法阻止大连通匹配，最后采样出有限图。

**为什么值得关心**

一个悬置 80 多年的著名猜想被否定；但姊妹篇表明"χ≤C·h"的线性松弛依然正确——失败恰好只在系数 1。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
构造出独立数至多 2、连通匹配数却不足 `@@M@@m/100@@` 的任意大图 `@@M@@G@@`，由此 `@@M@@h(G)<26m/75+2/3<m/2\le\chi_f(G)\le\chi(G)@@`：1943 年的 Hadwiger 猜想及其分数染色弱化形式被一并推翻。

## 问题背景
Hadwiger 猜想（1943）断言每个有限非空简单图的色数 `@@M@@\chi(G)@@` 不超过其 Hadwiger 数 `@@M@@h(G)@@`，即最大团子式（clique minor）`@@M@@K_t@@` 的阶数 `@@M@@t@@`。小 `@@M@@t@@` 情形都是对的：`@@M@@t=4@@` 由 Hadwiger 与 Dirac 证明，`@@M@@t=5@@` 经 Wagner 结构定理等价于四色定理，`@@M@@t=6@@` 由 Robertson、Seymour 与 Thomas 于 1993 年解决。对一般 `@@M@@t@@`，Kostochka 与 Thomason 的密度界给出 `@@M@@O(t\sqrt{\log t})@@` 种颜色，此后不断改进，目前最好结果为 `@@M@@O(t\log\log\log t)@@`（Liu–Luo，2026），离线性仍有对数鸿沟。独立数（independence number）`@@M@@\alpha(G)\le2@@` 的情形备受关注：Plummer–Stiebitz–Toft 证明此时猜想等价于"`@@M@@m@@` 个点的图必含 `@@M@@K_{\lceil m/2\rceil}@@` 子式"。而 Duchet–Meyniel 只证得 `@@M@@h(G)\ge m/3@@`，Fox 加强到 `@@M@@m/3+c\,m^{4/5}(\log m)^{1/5}@@`，距 `@@M@@m/2@@` 一步之遥却久攻不下。本文证明：这一步其实跨不过去。

## 主要结果
定理 1.1：存在任意大的整数 `@@M@@m@@` 与 `@@M@@m@@` 点有限简单图 `@@M@@G@@`，同时满足
`@@M@@D\alpha(G)\le2,\qquad \mathrm{cm}(G)<\frac{m}{100},@@`
其中 `@@M@@\mathrm{cm}(G)@@` 是连通匹配数（connected matching），即两两接触（touching，共享端点或两端点集之间有边相连）的匹配的最大规模。作者进一步证明计数不等式
`@@M@@Dh(G)\le\frac{|V(G)|+4\,\mathrm{cm}(G)+2}{3}@@`
（大的团子式中大量分支集取单点或双边，必然导出大连通匹配）。由于每个色类至多含 `@@M@@\alpha(G)@@` 个点，对分数染色数 `@@M@@\chi_f(G)@@`（fractional chromatic number）同样有 `@@M@@\chi_f(G)\ge m/\alpha(G)@@`，于是推论 1.2 给出：任意大的图满足
`@@M@@Dh(G)<\frac{26m}{75}+\frac23<\frac m2\le\chi_f(G)\le\chi(G).@@`
因此 Hadwiger 猜想不真；Reed–Seymour 1998 年讨论的分数弱化——无 `@@M@@K_{p+1}@@` 子式的图应有分数 `@@M@@p@@` 染色（他们只证得 `@@M@@2p@@` 界）——同样被否定。历史章节还指出，Füredi–Gyárfás–Simonyi 的精确连通匹配猜想也随之失效。

## 证明思路
构造分三层。第一层用代数定义"洞"（hole，即缺失的边）。从有限概率空间采样 `@@M@@m@@` 个位置，两点相邻当且仅当它们之间没有洞。每个元素 `@@M@@i@@` 带有进入公共二元向量空间的单射线性映射 `@@M@@U_i@@` 与线性泛函 `@@M@@u_i@@`；固定泛函 `@@M@@a@@` 与对称双线性型 `@@M@@T@@`，规定 `@@M@@i,j@@` 有洞当且仅当存在 `@@M@@\lambda_i,\lambda_j@@` 满足 `@@M@@U_i\lambda_i=U_j\lambda_j@@`、`@@M@@u_jU_i=a+T(\lambda_i,\cdot)@@`、`@@M@@u_iU_j=a+T(\lambda_j,\cdot)@@`、`@@M@@a(\lambda_i)+a(\lambda_j)=1@@`。把三条泛函恒等式沿假想的洞三角形求和：左端因共享向量条件成对抵消，双线性项因 `@@M@@T@@` 的对称性成对抵消，只剩 `@@M@@1+1+1=1@@`（特征 2），矛盾。故洞关系无环、无三角形，图即使采样出现重复元素也有 `@@M@@\alpha\le2@@`、`@@M@@\chi\ge m/2@@`，分数同理。

第二层阻止大连通匹配。两条不相交边互不接触，恰当四条交叉点对全是洞，称之为冲突。原始超饱和定理断言：任何满足边际与联合密度上界（`@@M@@\sigma_1\le M\mu@@`、`@@M@@\sigma_2\le M\mu@@`、`@@M@@\sigma\le2^{DN}\mu^2@@`）的单位分布 `@@M@@\sigma@@`，两个独立单位以至少 `@@M@@2^{-100gN}@@` 的概率冲突；单位（unit）指内部无洞的点对，允许两端点强相依——这正是匹配边所需的自由度。代数部分以布尔点上单项式赋值的秩一矩 `@@M@@vv^{\top}@@` 为素材：键（key，帧映射像的元组）相等给出共享张量，针（pin）保留有界个系数方向的指定像，低秩矩分解化解交叉收缩方程，碰撞判据把"四洞"化为被接受键分布的重叠。概率部分先把条件于针像的分布分解成叶子并记录小表，相位估计在正测度上给出相容表；再用直方图与乘积比较把查询律送往公共极限，有限维对偶在极限处产生重叠的标量配方；测度极小的分支另用一致性大集估计处理。此段技术性较强，此处从略。

第三层把分布命题搬到有限图：以 Csiszár 信息投影（相对熵最小化）为势能运行 Kleitman–Winston 式指纹算法，超饱和保证每步删去足够大的冲突邻域；当不再有可行律时，用 Ford–Fulkerson 容量割把剩余单位族覆盖成小端点集加小点对集。最后采样 `@@M@@m=2^{C_0gN}@@` 个位置，以 `@@M@@1-\exp(-\Omega(m))@@` 的概率同时实现 `@@M@@\alpha\le2@@` 与 `@@M@@\mathrm{cm}<m/100@@`，定理得证。

## 可信度与备注
主结果暂无 Lean 形式化证明；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。姊妹篇用同一套帧/洞机器证明 Colin de Verdière 染色猜想 `@@M@@\chi\le\mu+1@@` 亦不成立，并给出一条独立的矩阵秩路线同样违反 Hadwiger 不等式；另一姊妹篇则证明线性列表染色界 `@@M@@\chi_{\mathrm{list}}(G)\le Ch(G)@@` 成立。三篇合观：Hadwiger 猜想的失败只在系数 1，线性松弛仍然正确。

{% endraw %}
