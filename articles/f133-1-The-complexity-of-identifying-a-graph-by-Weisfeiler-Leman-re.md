---
layout: default
title: "The complexity of identifying a graph by Weisfeiler–Leman refinement"
family: "133"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The complexity of identifying a graph by Weisfeiler–Leman refinement

> 结果族 133：The computational complexity of Weisfeiler–Leman refinement　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

`@@M@@k@@` 维 WL"对话"分不出两张图，只说明这两张像；本文问一个更强的问题：多大的 `@@M@@k@@` 才能让一张图 `@@M@@G@@` 从**所有**非同构的图里被单独认出来？论文证明：判定"认出来所需维数 `@@M@@\le k@@`"是 EXPTIME 完全的——指数时间世界里的最难一档，比 NP 难题还要再高一层。

**关键词卡片**

- WL 维数（Weisfeiler–Leman dimension, `@@M@@\mathrm{WLdim}(G)@@`）：能把 `@@M@@G@@` 与所有非同构图区分开的最小维数 `@@M@@k@@`。
- 识别问题（identification）：判定 `@@M@@\mathrm{WLdim}(G)\le k@@`，要对一切比较图 `@@M@@H@@` 全称量化。
- 联合更新（joint update）：`@@M@@k@@` 维颜色细化的一种标准约定。
- EXPTIME 完全（EXPTIME-complete）：指数时间可解，且一切指数时间问题都能归约到它。

**看个具体例子**

比如输入一张 20 个顶点的图和 `@@M@@k=5@@`，问"5-WL 认得出它吗"：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="24" text-anchor="middle" font-size="15" fill="#333">识别：多大的 k 能让 G 从所有非同构图中被单独认出？</text><line x1="280" y1="140" x2="112" y2="66" stroke="#99a" stroke-width="1.5" stroke-dasharray="5,4"/><line x1="280" y1="140" x2="468" y2="66" stroke="#99a" stroke-width="1.5" stroke-dasharray="5,4"/><line x1="280" y1="140" x2="80" y2="196" stroke="#99a" stroke-width="1.5" stroke-dasharray="5,4"/><line x1="280" y1="140" x2="480" y2="196" stroke="#99a" stroke-width="1.5" stroke-dasharray="5,4"/><line x1="280" y1="140" x2="170" y2="230" stroke="#99a" stroke-width="1.5" stroke-dasharray="5,4"/><line x1="280" y1="140" x2="390" y2="230" stroke="#99a" stroke-width="1.5" stroke-dasharray="5,4"/><polygon points="250,100 310,100 325,146 280,176 235,146" fill="none" stroke="#345" stroke-width="2"/><line x1="250" y1="100" x2="325" y2="146" stroke="#345" stroke-width="1.5"/><circle cx="250" cy="100" r="5" fill="#345"/><circle cx="310" cy="100" r="5" fill="#345"/><circle cx="325" cy="146" r="5" fill="#345"/><circle cx="280" cy="176" r="5" fill="#345"/><circle cx="235" cy="146" r="5" fill="#345"/><text x="280" y="200" text-anchor="middle" font-size="14" fill="#123">G（输入图）</text><polygon points="88,52 124,52 106,82" fill="none" stroke="#888" stroke-width="1.5"/><circle cx="88" cy="52" r="4" fill="#888"/><circle cx="124" cy="52" r="4" fill="#888"/><circle cx="106" cy="82" r="4" fill="#888"/><text x="106" y="44" text-anchor="middle" font-size="13" fill="#666">H₁</text><polygon points="444,52 480,52 462,82" fill="none" stroke="#888" stroke-width="1.5"/><circle cx="444" cy="52" r="4" fill="#888"/><circle cx="480" cy="52" r="4" fill="#888"/><circle cx="462" cy="82" r="4" fill="#888"/><text x="462" y="44" text-anchor="middle" font-size="13" fill="#666">H₂</text><polygon points="56,182 92,182 74,212" fill="none" stroke="#888" stroke-width="1.5"/><circle cx="56" cy="182" r="4" fill="#888"/><circle cx="92" cy="182" r="4" fill="#888"/><circle cx="74" cy="212" r="4" fill="#888"/><text x="74" y="236" text-anchor="middle" font-size="13" fill="#666">H₃</text><polygon points="456,182 492,182 474,212" fill="none" stroke="#888" stroke-width="1.5"/><circle cx="456" cy="182" r="4" fill="#888"/><circle cx="492" cy="182" r="4" fill="#888"/><circle cx="474" cy="212" r="4" fill="#888"/><text x="474" y="236" text-anchor="middle" font-size="13" fill="#666">H₄</text><polygon points="146,222 182,222 164,248" fill="none" stroke="#888" stroke-width="1.5"/><circle cx="146" cy="222" r="4" fill="#888"/><circle cx="182" cy="222" r="4" fill="#888"/><circle cx="164" cy="248" r="4" fill="#888"/><text x="164" y="216" text-anchor="middle" font-size="13" fill="#666">H₅</text><polygon points="366,222 402,222 384,248" fill="none" stroke="#888" stroke-width="1.5"/><circle cx="366" cy="222" r="4" fill="#888"/><circle cx="402" cy="222" r="4" fill="#888"/><circle cx="384" cy="248" r="4" fill="#888"/><text x="384" y="216" text-anchor="middle" font-size="13" fill="#666">H₆</text><text x="280" y="272" text-anchor="middle" font-size="13" fill="#666">配对等价只比指定的两张图；识别要赢下所有对手</text></svg>

</div>

上界一侧很朴素：`@@M@@k\ge n@@` 时必能识别，故枚举全部 `@@M@@2^{\binom n2}@@` 张 `@@M@@n@@` 顶点图逐一检验，耗时对 `@@M@@n@@` 指数；下界一侧把任意图灵机的指数长计算压进多项式规模的图与维数 `@@M@@r@@`。结论：即使 `@@M@@k@@` 改用一进制编码，问题仍 EXPTIME 完全——难，不靠 `@@M@@k@@` 的数字写得长。

**为什么值得关心**

它补全了 WL 框架下"识别"这一量词形态的复杂度分类（此前只知 P 艰难与 NP 艰难），说明只差一个"对所有图"的量词，问题就从多项式可解跳到指数时间完全。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论
本文证明：给定无色图 `@@M@@G@@` 的邻接矩阵和二进制编码的正整数 `@@M@@k@@`，判定"Weisfeiler–Leman 维数 `@@M@@\mathrm{WLdim}(G)\le k@@`"是 EXPTIME 完全的；即使 `@@M@@k@@` 改为一进制编码仍然完全，从而完成了输入维数下识别问题的复杂度分类。

## 问题背景
`@@M@@k@@` 维 Weisfeiler–Leman 细化是图同构检测的核心工具。与"给定一对图在细化后是否仍不可区分"不同，识别（identification）问题问：`@@M@@k@@`-WL 是否把 `@@M@@G@@` 从所有非同构图中单独区分出来，即是否 `@@M@@G\equiv_k H@@` 蕴含 `@@M@@G\cong H@@` 对每个比较图 `@@M@@H@@` 都成立；最小的这样的 `@@M@@k@@` 称为 `@@M@@G@@` 的 WL 维数（Weisfeiler–Leman dimension）。此前 Arvind–Köbler–Rattan–Verbitsky 证明维数一的识别是 P 艰难的，Lichter–Raßmann–Schweitzer 把固定维数的 P 艰难性推广到一切 `@@M@@k\ge 2@@`，并在维数作为输入时证明 NP 艰难性；变维数的配对等价已知 coNP 艰难。识别带有"对所有比较图"的全称量词，此前没有完整的复杂度刻画，本文补上最后一格：EXPTIME 完全。

## 主要结果
约定 `@@M@@k\ge 2@@` 采用联合更新（joint update）：每轮记录"同一个替换顶点 `@@M@@z@@` 在 `@@M@@k@@` 个坐标上的旧色向量"的多重集；`@@M@@k=1@@` 用普通邻居颜色细化。主定理：判定 `@@M@@\mathrm{WLdim}(G)\le k@@`——输入为非空有限简单无色图的二进制邻接矩阵与二进制正整数 `@@M@@k@@`——在确定型多项式时间多一归约下 EXPTIME 完全；推论：`@@M@@k@@` 用一进制编码仍是 EXPTIME 完全，故艰难性并不依赖 `@@M@@k@@` 的数值指数级大于其编码长度。成员性来自朴素指数算法：先比较 `@@M@@k@@` 与 `@@M@@n@@`（`@@M@@k\ge n@@` 时直接接受），否则枚举全部 `@@M@@2^{\binom n2}@@` 个 `@@M@@n@@` 顶点图，逐个检验等价与同构，耗时指数于 `@@M@@n@@` 的多项式。艰难度来自把任意指数时间机器 `@@M@@M@@` 与输入 `@@M@@w@@` 编码成图 `@@M@@G(0)@@` 和多项式有界的维数 `@@M@@r=2p(m)+4@@`。

## 证明思路
归约把 `@@M@@\mathbb F_2@@` 上的线性约束编码成"局部可重构"的图：每个变量比特对应一对顶点，每个小约束的每个合法赋值对应一个顶点并连向它指定的比特值；用互不相交的度数区间加私有悬挂叶子的办法抹去颜色，得到 `@@M@@G(\beta)@@`，其中 `@@M@@\beta@@` 是各方块约束的右端比特。关键压缩在于：地址 `@@M@@a\in\{0,1\}^r@@` 处的向量值不逐个存储，而写成相邻坐标之和 `@@M@@h(a)=\sum_{i=1}^r h_i(a_i,a_{i+1})@@`（`@@M@@a_{r+1}=a_1@@`），于是指数多的地址只需多项式大的短表即可描述。
先证配偶结构：由双射博弈（bijective game，joint 约定恰对应 `@@M@@k+1@@` 个对槽），任何满足 `@@M@@H\equiv_r G(0)@@` 的图都同构于某个 `@@M@@G(\beta)@@`——度数区间先恢复颜色类与私有叶子，再用不超过 `@@M@@K\ge 33@@` 个槽做小尺寸关联测试逐块重构同一约束模式；且 `@@M@@G(\beta)\cong G(0)@@` 当且仅当移位后的约束组有全局偏移解。其次，博弈等价给出各地址处非空的向量值集合 `@@M@@Q_{P,a}@@`，每条比较在移位下恰好等同一个标量像（像一致性），而对一类特殊移位该条件也是充分的。
计算编码采用单调电路与私有两坐标缓冲：集合 `@@M@@\{(0,0),(1,1)\}@@` 的两个坐标像都是全 `@@M@@\mathbb F@@` 而和像为 `@@M@@\{0\}@@`，因此缓冲既能保持源端的完整像，又能把和限制成单点；反之两坐标像都是单点时整个缓冲被逼成单点——这正是"真值单向传播"。若 `@@M@@M@@` 接受 `@@M@@w@@`：广播类型 `@@M@@A@@` 经翻转单坐标的自连接把单点性传遍所有 `@@M@@2^r@@` 个地址，再连到每个门的坐标；每个坐标的自连接取两份，第三次比较中两份相加抵消该坐标本身，迫使值恰具相邻坐标和的形式，于是全局偏移存在，一切等价配偶都同构，`@@M@@\mathrm{WLdim}\le r@@`。若不接受：在某条广播自连接的第三次比较上放常数 1 的特殊扭转，两条自连接分别强制 `@@M@@h_A(a)=0@@` 与 `@@M@@h_A(a)=1@@`，无全局解，但仍可对每个门按真值取 `@@M@@\{0\}@@` 或 `@@M@@\mathbb F@@` 构造满足像一致性的非空集合，得到等价而非同构的配偶，`@@M@@\mathrm{WLdim}>r@@`。图阶为 `@@M@@O_M((r+1)^{12})@@`，多项式时间可构造。

## 可信度与备注
本文未经形式化验证，请以社区核验为准。它与族 133 的姊妹结果互相支撑：变维数配对等价篇提供压缩计算构造的短表与势能延拓技术，本文的识别专用论证（全称量词下的局部到全局重构）独立完成，并不把配对艰难性当黑盒；无条件下界篇则处理固定维数的时间指数。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
