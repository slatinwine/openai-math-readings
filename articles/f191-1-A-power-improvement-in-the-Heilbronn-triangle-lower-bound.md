---
layout: default
title: "A power improvement in the Heilbronn triangle lower bound"
family: "191"
discipline: "Combinatorics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A power improvement in the Heilbronn triangle lower bound

> 结果族 191：A power improvement in the Heilbronn triangle lower bound　·　学科：Combinatorics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

在一块边长为 1 的方桌布上钉 n 枚图钉，任何三枚钉子都会围出一个三角形；怎么钉，才能让"最扁的那个三角形"尽量不扁？这就是海尔布伦在 1950 年代提出的三角形问题。随手乱撒大概率撞出很扁的三角形，所以必须精心设计位置。本文给出惊人构造：能让每个三角形的面积都不小于 `@@M@@c_1 n^{-2+\eta}@@`——指数上真正前进了一步。

**关键词卡片**

- 海尔布伦三角形问题：`@@M@@n@@` 个点放入单位正方形，最大化最小三角形面积，记作 `@@M@@\Delta(n)@@`。
- 幂次改进（power improvement）：下界从 `@@M@@n^{-2}@@` 量级提高到 `@@M@@n^{-2+\eta}@@`，`@@M@@\eta>0@@` 是固定小常数。
- 对数因子：1982 年以来仅有的改进是乘一个 `@@M@@\log n@@`，增长极慢，只算"半个"进步。
- 上界与下界：答案被夹在两者之间；本文抬高下界，推翻"几乎 `@@M@@n^{-2}@@`"的上界表述。

**看个具体例子**

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
<text x="205" y="30" text-anchor="middle" font-size="14">单位正方形，撒 n 个点（示意 n=12）</text>
<rect x="90" y="45" width="230" height="190" fill="none" stroke="#222" stroke-width="2"/>
<line x1="120" y1="75" x2="165" y2="80" stroke="#b03030" stroke-width="2"/>
<line x1="165" y1="80" x2="160" y2="220" stroke="#b03030" stroke-width="2"/>
<line x1="160" y1="220" x2="120" y2="75" stroke="#b03030" stroke-width="2"/>
<circle cx="120" cy="75" r="4" fill="#b03030"/>
<circle cx="165" cy="80" r="4" fill="#b03030"/>
<circle cx="160" cy="220" r="4" fill="#b03030"/>
<circle cx="205" cy="95" r="3" fill="#222"/>
<circle cx="235" cy="175" r="3" fill="#222"/>
<circle cx="265" cy="65" r="3" fill="#222"/>
<circle cx="130" cy="150" r="3" fill="#222"/>
<circle cx="185" cy="135" r="3" fill="#222"/>
<circle cx="290" cy="205" r="3" fill="#222"/>
<circle cx="300" cy="105" r="3" fill="#222"/>
<circle cx="175" cy="60" r="3" fill="#222"/>
<circle cx="250" cy="120" r="3" fill="#222"/>
<circle cx="215" cy="160" r="3" fill="#222"/>
<text x="345" y="105" font-size="13" fill="#b03030">最扁的三角形也要</text>
<text x="345" y="123" font-size="13" fill="#b03030">面积 ≥ c₁·n^(−2+η)</text>
<text x="280" y="262" text-anchor="middle" font-size="13">旧构造：Δ(n) ≈ n^(−2)；新定理：Δ(n) ≥ c₁·n^(−2+η)</text>
</svg>

</div>

数字对比：取 `@@M@@\varepsilon=\eta/2@@`，则 `@@M@@c_1 n^{-2+\eta}\div\bigl(C_\varepsilon n^{-2+\varepsilon}\bigr)\to\infty@@`，故"对每个 `@@M@@\varepsilon@@` 都有 `@@M@@\Delta(n)\le C_\varepsilon n^{-2+\varepsilon}@@`"的表述必假。注意 `@@M@@\eta=2/(45435k+16)@@` 小到天文级，作者明言未做优化。

**为什么值得关心**

这是 1982 年对数改进之后的第一个幂次级改进，直接宣判了流行几十年的"几乎 `@@M@@n^{-2}@@`"猜想死刑。`@@M@@\eta@@` 虽小到天文级，但在数学上"指数动了一丝"就是质的飞跃：它说明 `@@M@@n^{-2}@@` 绝不是这个问题的最终答案。上界方向目前最好约为 `@@M@@n^{-7/6+\varepsilon}@@`，与下界之间仍隔着巨大鸿沟，本文让天平向下界一侧倾斜。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

论文证明存在绝对常数 `@@M@@\eta,c_1>0@@`：当 `@@M@@n@@` 充分大时，可在单位正方形内放置 `@@M@@n@@` 个点，使它们决定的任何三角形面积都不小于 `@@M@@c_1n^{-2+\eta}@@`。这一幂次（power）改进推翻了海尔布伦三角形问题的"几乎 `@@M@@n^{-2}@@`"上界猜想。

## 问题背景

海尔布伦三角形问题（Heilbronn's triangle problem）问：在单位正方形内放 `@@M@@n@@` 个点，它们决定的 `@@M@@n \choose 3@@` 个三角形中最小面积最大能到多少？记该量为 `@@M@@\Delta(n)@@`。海尔布伦在 1950 年代猜想 `@@M@@\Delta(n)=O(n^{-2})@@`（见 Roth 1951 年论文）。两个初等构造——Erdős 的有限域抛物线与"随机取样再删点"——都能达到 `@@M@@n^{-2}@@` 量级；1982 年 Komlós、Pintz 与 Szemerédi 用随机超图方法把它改进为 `@@M@@\Delta(n)\gg(\log n)/n^2@@`，从而否定了原猜想，但只多出一个对数因子。此后学界转而关注更弱的"几乎 `@@M@@n^{-2}@@`"（almost `@@M@@n^{-2}@@`）表述：对每个 `@@M@@\varepsilon>0@@` 是否都有 `@@M@@\Delta(n)\le C_\varepsilon n^{-2+\varepsilon}@@`？Zakharov 2026 年的综述讨论了这一表述。上界方面，Roth 的密度增量方法经多轮推进，目前最好结果为 Cohen–Pohoata–Zakharov 的 `@@M@@\Delta(n)\ll_\varepsilon n^{-7/6+\varepsilon}@@`。本文证伪了上述几乎 `@@M@@n^{-2}@@` 表述。

## 主要结果

定理：存在绝对常数 `@@M@@\eta,c_1>0@@` 与整数 `@@M@@n_0@@`，使对一切 `@@M@@n\ge n_0@@` 有 `@@M@@\Delta(n)\ge c_1n^{-2+\eta}@@`。指数是显式的：取固定奇数 `@@M@@d=41@@`，`@@M@@M=\binom{4d-1}{d}@@`，`@@M@@T=\binom{M}{3}@@`，`@@M@@k=T^2+1@@`，则 `@@M@@\eta=2/(45435k+16)@@`——一个天文数字级别的小正数，作者明言未做任何优化。取 `@@M@@\varepsilon=\eta/2@@`，定理下界与 `@@M@@C_\varepsilon n^{-2+\varepsilon}@@` 之比为 `@@M@@c_1n^{\eta/2}\to\infty@@`，矛盾由此而来。就论文所引文献而言，这是自 1982 年对数改进之后的第一个幂次量级改进。

## 证明思路

把面积化为行列式是核心：整数列 `@@M@@u=(u_1,u_2,u_3)^{\mathsf T}@@`（`@@M@@0\le u_1,u_2<N\le u_3<2N@@`）投影为 `@@M@@\pi(u)=(u_1/u_3,u_2/u_3)@@`，三列成阵 `@@M@@A@@` 时三角形面积恰为 `@@M@@|\det A|/(2A_{31}A_{32}A_{33})@@`，故只需让小行列式三元组（`@@M@@|\det|\le\tau@@`）稀少到可删。

第一重同余条件设在主模 `@@M@@h=B^k@@` 上。每列带独立均匀标签 `@@M@@\xi\in\mathbb F_{r^d}@@`（`@@M@@d=41@@` 固定，素数 `@@M@@r\to\infty@@`）；Erdős 有限域抛物线 `@@M@@(1,\xi,\xi^2)^{\mathsf T}@@` 标签互异时行列式非零（Vandermonde）。取域范数（field norm）降到 `@@M@@\mathbb F_r@@`，得交错多项式 `@@M@@\mathcal N@@`，分解为 `@@M@@T@@` 个单项式行列式之和，编码进列的 `@@M@@B@@` 进制指定数位，使行列式多项式的 `@@M@@Y^{k-1}@@` 系数恰为 `@@M@@\mathcal N@@` 在三标签处的值（模 `@@M@@r@@`），标签互异时非零，系数至少为 1。配合 Salem–Spencer/Behrend 大底数进位控制，行列式剩余类在 `@@M@@[-\tau,\tau]@@`（`@@M@@\tau\approx B^{k-1}/2@@`）内便无整数代表，此即"行列式障碍"。

共享随机元 `@@M@@G_h\in\operatorname{SL}_3(\mathbb Z/h\mathbb Z)@@` 混合三行而不变行列式；条件化后剩余类在特殊线性轨道（special-linear orbit）上均匀，提升的行落入指标 `@@M@@I@@` 的格（lattice），其中行列式为固定非零值的矩阵仅 `@@M@@\ll(\log X)^2X^6/I^2@@` 个（各向异性格点计数）。

行列式为零（共线）时启用第二重同余条件：在独立素数 `@@M@@q\approx h^{100}@@` 取椭圆二次曲面上无三点共线的帽集（cap），经受限随机平移与可逆线性映射均匀化并排除短整数关系；秩亏情形则按本原零向量给出的秩二行格求和。中国剩余定理（Chinese remainder theorem）合并两重条件后提升，坏三元组必须标签重复，概率 `@@M@@\le 3r^{-d}@@`。

最后是初等删除（alteration）：取 `@@M@@2n_r@@` 个样本（`@@M@@n_r=\lfloor r\sqrt{N^3/\tau}\rfloor@@`），坏事件期望为 `@@M@@o(n_r)@@`（线性性估计），不需事件独立性，也不用 KPS 超图独立引理；每坏组删一个指标后保留 `@@M@@n_r@@` 列，三角形面积均 `@@M@@\ge\tau/(16N^3)@@`。由 `@@M@@n_r\asymp r^\alpha@@`（`@@M@@\alpha=45435k+16@@`）得 `@@M@@\Delta\ge c_1n^{-2+\eta}@@`，`@@M@@\eta=2/\alpha@@`；一般大的 `@@M@@n@@` 由贝特朗公设（Bertrand's postulate）选素数 `@@M@@r@@` 使 `@@M@@n\le n_r\le C_kn@@`，弃去多点即得定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明，请以社区核验为准；论文自含全部初等证明，指数 `@@M@@\eta@@` 显式可查，便于逐步复核。值得留意的是，引言专门指出了此前声称更强下界的两份预印本（Ellmann 第 12 版、Agama 第 13 版）的具体漏洞，可见作者对同类构造的审慎态度。本结果族目前仅此一篇，暂无姊妹篇互相支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
