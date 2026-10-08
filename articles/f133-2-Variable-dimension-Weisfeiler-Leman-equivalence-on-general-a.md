---
layout: default
title: "Variable-dimension Weisfeiler–Leman equivalence on general and subcubic graphs"
family: "133"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Variable-dimension Weisfeiler–Leman equivalence on general and subcubic graphs

> 结果族 133：The computational complexity of Weisfeiler–Leman refinement　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

WL 对话的"维数 `@@M@@k@@`"以前都被当成固定的小常数；这篇论文让 `@@M@@k@@` 成为输入的一部分，用二进制写在数据里——30 个比特就能写下十亿维，而熟悉的 `@@M@@n^{O(k)}@@` 算法随之变成货真价实的指数时间。论文证明：此时判定两图是否 `@@M@@k@@`-WL 等价恰好是 EXPTIME 完全，哪怕图限制到每个点至多 3 条边，正面回答了 Berkholz 的公开问题。

**关键词卡片**

- 变维数（variable dimension）：`@@M@@k@@` 随输入给出、用二进制编码。
- 双射博弈（bijective game）：`@@M@@k@@`-WL 等价的等价刻画——Dup 必须先亮出整张双射表，Spo 再选点考验。
- EXPTIME 完全（EXPTIME-complete）：指数时间可解，且其中最难。
- 子立方图（subcubic graphs）：最大度至多 3 的图。

**看个具体例子**

归约的骨架是把一台指数时间机器的计算，压进一对多项式规模的小图：

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="30" text-anchor="middle" font-size="15" fill="#333">把指数长的计算压进多项式大的图对</text><rect x="20" y="80" width="150" height="76" rx="8" fill="#eef" stroke="#345"/><text x="95" y="112" text-anchor="middle" font-size="13" fill="#123">任意图灵机 M</text><text x="95" y="134" text-anchor="middle" font-size="13" fill="#123">输入 w，跑 2^d 步</text><line x1="174" y1="118" x2="214" y2="118" stroke="#666" stroke-width="2"/><polygon points="214,118 203,112 203,124" fill="#666"/><rect x="218" y="80" width="150" height="76" rx="8" fill="#efe" stroke="#253"/><text x="293" y="104" text-anchor="middle" font-size="13" fill="#121">图对 G, H</text><text x="293" y="124" text-anchor="middle" font-size="13" fill="#121">多项式规模</text><text x="293" y="144" text-anchor="middle" font-size="13" fill="#121">维数 k = 2d（二进制）</text><line x1="372" y1="118" x2="412" y2="118" stroke="#666" stroke-width="2"/><polygon points="412,118 401,112 401,124" fill="#666"/><rect x="416" y="80" width="130" height="76" rx="8" fill="#fdf" stroke="#534"/><text x="481" y="108" text-anchor="middle" font-size="13" fill="#312">判定 G ≡ₖ H ？</text><text x="481" y="132" text-anchor="middle" font-size="13" fill="#312">答案对应</text><text x="481" y="152" text-anchor="middle" font-size="13" fill="#312">"机器拒绝 w"？</text><text x="60" y="200" font-size="13" fill="#666">时间与带头位置各占 d 位二进制，地址长 r=2d，输出维数 k=r；</text><text x="60" y="224" font-size="13" fill="#666">一般构造图阶约 (r+1)¹²，亚三次版约 (r+2)¹⁶，多项式时间可写出。</text><text x="60" y="248" font-size="13" fill="#666">上界：k≥n 时等价即同构，换 min{k,n} 后标准细化只需 2^O(n log n)。</text></svg>

</div>

代入数字：`@@M@@d=20@@`（机器跑约一百万步）时 `@@M@@k=40@@`，图对约有 `@@M@@41^{12}\approx 2\times10^{19}@@` 个顶点。两头夹起来，判定问题恰好落在 EXPTIME 完全的位置上。

**为什么值得关心**

Luks 已证明固定最大度图的同构测试是多项式的，而本文说明"按指定维数做 WL"即使在同样的图上也指数时间完全——这是与同构测试本质不同的问题。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明当维数 `@@M@@k@@` 以二进制编码作为输入时，判定联合更新 `@@M@@k@@` 维 Weisfeiler–Leman 等价（`@@M@@G\equiv_k H@@`）是 `@@M@@\mathsf{EXPTIME}@@`-完全的，即使在连通、无色、最大度至多 3 的简单图上亦然，正面回答了 Berkholz 的公开问题。

## 问题背景

Weisfeiler–Leman 精炼源自 1968 年 Weisfeiler 与 Leman 关于图标号（graph canonization）的工作：对有序顶点元组反复染色并比较两图的直方图，固定维数 `@@M@@k@@` 时可在多项式时间完成。可一旦 `@@M@@k@@` 本身是输入的一部分（二进制给出），熟悉的 `@@M@@n^{O(k)}@@` 元组算法就不再是多项式时间的，该判定问题的复杂度长期悬而未决。经典的 Cai–Fürer–Immerman 构造只给出维数下界——区分某些非同构图需要线性多个变量——并非求解判定问题的时间下界。2024 年 Seppelt 证明了配对等价问题的 coNP-困难性，并记录下 Berkholz 提出的是否 `@@M@@\mathsf{EXPTIME}@@`-完全之问；Lichter–Raßmann–Schweitzer 随后对简单无色图独立得到 coNP-困难性。本文彻底解决此问题，并额外攻克最大度至多 3 的连通图这一受限情形——鉴于 Luks 已证明固定最大度图的同构测试属多项式时间，该限制恰恰说明"按指定维数做精炼"问的是另一回事：不同构的图仍可能等价。

## 主要结果

定义语言 `@@M@@\WL@@`：输入为两张以显式邻接矩阵给出的有限简单无色无向图 `@@M@@G,H@@` 与二进制整数 `@@M@@k\ge2@@`，判定是否 `@@M@@G\equiv_k H@@`；受限版 `@@M@@\SubWL@@` 额外要求两图连通、阶相同且最大度至多 3。主定理断言：两者在确定性多项式时间多一归约（many-one reduction）下均为 `@@M@@\mathsf{EXPTIME}@@`-完全。上界来自"维数封顶"引理——同阶两图当 `@@M@@k\ge n@@` 时 `@@M@@G\equiv_k H@@` 当且仅当二者同构，故可把 `@@M@@k@@` 替换为 `@@M@@\min\{k,n\}@@` 后运行标准精炼，耗时 `@@M@@2^{O(n\log n)}L^{O(1)}@@`。归约输出的维数 `@@M@@k=r@@` 是源输入长度的多项式，故即使改用一进制编码 `@@M@@k@@`，完全性仍成立。文中还给出显式规模：一般实现的图阶为 `@@M@@O_M((r+1)^{12})@@`、亚三次实现为 `@@M@@O_M((r+2)^{16})@@`（`@@M@@r@@` 为地址坐标数），邻接矩阵均可在 `@@M@@r@@` 的多项式时间内写出。

## 证明思路

整体策略是把一台指数时间图灵机的计算压入一对多项式规模的小图，使 Duplicator 获胜当且仅当机器拒绝该输入；对目标语言取补判定器即得所需归约极性。先证游戏刻画：`@@M@@G\equiv_k H@@` 当且仅当 Duplicator 在 `@@M@@k+1@@` 个对槽的双射博弈（bijective game）中获胜，而 Duplicator 必须在 Spoiler 选点之前宣布整个顶点集双射——这一时序是全部构造必须满足的强约束。归约链分四步。第一步把时间与带头位置各记为 `@@M@@d@@` 位二进制数，地址长 `@@M@@r=2d@@`，输出维数 `@@M@@k=r@@`；借助进位/借位表，用多项式多条连接模式（connection schema）描述指数规模的门电路，单带机在长 `@@M@@4T@@` 环上的局部更新给出无环电路，某测试门为真当且仅当机器接受。第二步把电路翻译成 `@@M@@\F_2@@` 上的标量像一致性（scalar-image consistency）：每个变量取非空的 1–2 位向量集合，每条比较只要求两端仿射形式的像集相等；私有的二坐标缓冲器 `@@M@@(z,z')@@` 实现定向传播——真信号被迫把像缩为 `@@M@@\{0\}@@`，假信号保留全集，故一致当且仅当所有测试为假。第三步把每条比较细分为长导线、将 `@@M@@r@@` 个地址坐标排成环，得到位点（site）与方块（square）两类块，其合法赋值构成 `@@M@@\F_2@@` 上的仿射纤维；核心的精确投影命题为至多 `@@M@@K=r+1@@` 个块构造相容偏移列表族且限制恰等于小族——围绕坐标环闭合的"包裹"分支至少需 `@@M@@r@@` 个块、恰为 `@@M@@r@@` 个时恢复唯一完整地址并受见证集约束，非包裹分支则靠调整角势（corner potential）吸收偏移改变。第四步实现成图：一般实现把合法赋值直接当作顶点、用私有叶子标记块；亚三次实现改用估值路径、前缀树、锚点链与共享读出上的相等匹配，再以"三角形＋连接器＋长度等于色号的私有路径"小配件消除颜色，得到连通、简单、最大度至多 3 的图对。最后读出博弈：Duplicator 对每个未激活块预先选定扩展列表，因 Spoiler 一步至多激活一个新块，各块选择无须彼此相容；反向用零查询历史，把环上 `@@M@@r@@` 个位点的解码向量求和得到被寻址变量处的值，用仅剩的空槽将环沿导线逐格搬运（先放新再弃旧），对方块方程求和使竖直读出两两抵消，双向搬运恰好凑出见证集所需的像集等式。

## 可信度与备注

本文与两篇姊妹篇同属结果族 133：固定维数篇对足够大的固定 `@@M@@k@@` 证明 `@@M@@n^{\Omega(k)}@@` 的确定性时间下界，识别维数篇证明"判定给定维数能否识别一张图"亦 `@@M@@\mathsf{EXPTIME}@@`-完全并直接复用本文的一致计算接口，三篇共享乘积地址、标量像与角势方法而互相支撑。本文主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
