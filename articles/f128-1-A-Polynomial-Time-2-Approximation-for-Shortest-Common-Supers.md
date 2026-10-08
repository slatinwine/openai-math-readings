---
layout: default
title: "A Polynomial-Time 2-Approximation for Shortest Common Superstring"
family: "128"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | A Polynomial-Time 2-Approximation for Shortest Common Superstring

> 结果族 128：A factor-two approximation for shortest common superstring　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

基因测序仪吐出一堆零散短串,想找一条最短的"总串"把它们都连着装下——像把几段重复的歌词并成一句最短的完整歌词,重叠部分只唱一遍。这个问题是 NP 难的;近似比从 1994 年的 3 一路缓降到 2.466、再到 2026 年的 7/3,这篇论文造出确定性多项式时间算法,首次保证长度不超过最优的 2 倍。

**关键词卡片**

- 公共超串(common superstring):把给定字符串都当作连续片段包含的字符串。
- 最短公共超串(shortest common superstring):求最短的这种总串,数据压缩与序列拼接的经典难题。
- 重叠(overlap):两串首尾相同的部分,拼接时可共享,如 100 与 001 共享"00"。
- 层级图(hierarchical graph):论文的核心舞台:顶点是全部子串,向上边加字母、向下边删首字母,一条欧拉回路写下超串。
- 近似算法(approximation algorithm):不求最优解,但保证答案不超过最优的指定倍数。

**看个具体例子**

输入 `@@M@@\{001,011,100\}@@`:最短公共超串是 10011(长度 5),三条串分别落在第 1–3、2–4、3–5 格。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="280" y="24" text-anchor="middle" font-size="16" fill="#333">输入 {001, 011, 100} → 最优公共超串 10011(长 5)</text><rect x="60" y="44" width="84" height="32" rx="8" fill="#eaf2fb" stroke="#4a90d9" stroke-width="2"/><text x="102" y="65" text-anchor="middle" font-size="15" fill="#1a5276">001</text><rect x="240" y="44" width="84" height="32" rx="8" fill="#eaf2fb" stroke="#4a90d9" stroke-width="2"/><text x="282" y="65" text-anchor="middle" font-size="15" fill="#1a5276">011</text><rect x="420" y="44" width="84" height="32" rx="8" fill="#eaf2fb" stroke="#4a90d9" stroke-width="2"/><text x="462" y="65" text-anchor="middle" font-size="15" fill="#1a5276">100</text><line x1="102" y1="80" x2="186" y2="112" stroke="#888" stroke-width="2"/><path d="M190,114 L179,115 L182,106 Z" fill="#888"/><line x1="282" y1="80" x2="279" y2="108" stroke="#888" stroke-width="2"/><path d="M277,116 L274,104 L283,105 Z" fill="#888"/><line x1="462" y1="80" x2="370" y2="110" stroke="#888" stroke-width="2"/><path d="M366,114 L374,107 L377,115 Z" fill="#888"/><rect x="168" y="118" width="44" height="44" fill="#fff" stroke="#333" stroke-width="2"/><rect x="212" y="118" width="44" height="44" fill="#fff" stroke="#333" stroke-width="2"/><rect x="256" y="118" width="44" height="44" fill="#fff" stroke="#333" stroke-width="2"/><rect x="300" y="118" width="44" height="44" fill="#fff" stroke="#333" stroke-width="2"/><rect x="344" y="118" width="44" height="44" fill="#fff" stroke="#333" stroke-width="2"/><text x="190" y="147" text-anchor="middle" font-size="22" fill="#333">1</text><text x="234" y="147" text-anchor="middle" font-size="22" fill="#333">0</text><text x="278" y="147" text-anchor="middle" font-size="22" fill="#333">0</text><text x="322" y="147" text-anchor="middle" font-size="22" fill="#333">1</text><text x="366" y="147" text-anchor="middle" font-size="22" fill="#333">1</text><path d="M168,184 L168,192 L300,192 L300,184" fill="none" stroke="#7b241c" stroke-width="2"/><text x="234" y="210" text-anchor="middle" font-size="14" fill="#7b241c">100</text><path d="M212,216 L212,224 L344,224 L344,216" fill="none" stroke="#1a5276" stroke-width="2"/><text x="356" y="223" font-size="14" fill="#1a5276">001</text><path d="M256,248 L256,256 L388,256 L388,248" fill="none" stroke="#1e8449" stroke-width="2"/><text x="400" y="255" font-size="14" fill="#1e8449">011</text><text x="200" y="226" text-anchor="middle" font-size="12" fill="#888">← 共享重叠段 →</text><text x="280" y="277" text-anchor="middle" font-size="13" fill="#666">9 个字符借重叠省下 4 格,5 格全部装下(长度 5 = 最优)</text></svg>

</div>

算法保证输出长度 `@@M@@\le 2\times\mathrm{OPT}=10@@`,这里恰好给出最优的 10011。注意:2 倍保证属于这个新算法,而不是经典的"每次合并重叠最大对"贪心——那个 1988 年的猜想至今未证,且贪心最坏情形已知至少 `@@M@@9/4@@` 倍。

**为什么值得关心**

近似比在这个问题上卡了三十多年,整数 2 这道关口首次被多项式时间算法从上方触及;而且本主结果已通过机器证明验证。

> 已 Lean 形式化

## 一句话结论
对任意显式给出的有限字符串族，本文构造出确定性多项式时间算法，输出长度至多两倍最优值的公共超串，首次跨过"多项式时间 2-近似"这道悬了三十多年的门槛。

## 问题背景
最短公共超串（shortest common superstring）问题：给定一组字符串，求把它们都当作连续子串包含的最短字符串，是数据压缩与序列拼接的经典问题。Tarhio 与 Ukkonen 在 1988 年提出猜想：每次合并重叠最大一对的贪心过程（Greedy）即可达到 2 倍近似。近似比从 Blum 等人 1994 年的 3 起，经 `@@M@@5/2@@`、`@@M@@2+11/23@@`、`@@M@@(14+\sqrt{67})/9<2.466@@` 一路缓降，2026 年 8 月刚推进到 `@@M@@7/3@@`；同期另有预印本给出贪心最坏比至少 `@@M@@9/4@@` 的反例。本文用全新算法首次给出 2-近似。

## 主要结果
主定理：存在确定性算法，运行时间关于输入的总编码长度 `@@M@@N@@`（包括符号标签的编码）多项式，对每个有限字符串族 `@@M@@\mathcal S@@` 输出公共超串 `@@M@@T@@` 满足 `@@M@@\len{T}\le 2\OPT(\mathcal S)@@`。注意两点：该保证只属于本文构造的算法，而非经典贪心；时间按编码长度计费，对超大字母表、变宽标签同样成立。

## 证明思路
证明在"层级图"（hierarchical graph）上展开：顶点是所有输入子串（含空串 `@@M@@\eps@@`），向上边追加字母、费用 1，向下边删首字母、费用 0。平衡（每点入出度相等）、连通且访问全部要求串的边多重集，其 Euler 回路写下的字母即公共超串，长度为上边总数。

先构造"强制出现次数" `@@M@@m(s)@@`：按长度递降取满足 `@@M@@m(s)\ge\sum_c m(cs)@@` 及对称式的最小整数，要求串至少计 1；再加周期规则——相对周期文本 `@@M@@A@@`，"括住词"（bracketing word）是两侧各带失配字母的匹配区间，贡献记作 `@@M@@B_A@@`，若长词 `@@M@@v@@`（比前缀 `@@M@@w@@` 长 `@@M@@k@@` 个周期）的计数超过被括住量，则强制 `@@M@@m(w)\ge B_A(w;m)+k+1@@`。任何公共超串中 `@@M@@s@@` 的出现次数不少于 `@@M@@m(s)@@`，故单字母计数之和 `@@M@@W\le\OPT@@`。这组计数给出费用恰为 `@@M@@W@@` 的平衡"基础图"，但可能不连通。

再把基础图重排为"层"（layer）：回路上追加的字母双向重复生成周期文本，同文本回路可保边重排为恰走一个最小周期 `@@M@@p@@` 的层，费用与预算各 `@@M@@p@@`，合计仍是 `@@M@@W@@`。长度控制靠两个周期性事实：一致段有界（Fine–Wilf 推论）与字典序最大旋转性质。

最后花预算连接。跨文本接触须落在同时符合两侧文本对齐的实际窗口（"记录"record）上；多数连接只花源层预算，需目标层出资的"请求"只发给周期严格更大的层，待处理该周期时一并结算。仅由源层出资的连接可能围成有向环：取环上 distinguished rotation 字典序最大者，最大旋转引理保证出现长度不超过目标周期 `@@M@@q@@` 的接触词；令目标块放弃出边、内部合并，省下的预算恰好支付它到 `@@M@@\eps@@` 的往返。附加费用至多 `@@M@@W@@`，总长 `@@M@@\le 2W\le 2\OPT@@`。

## 可信度与备注
论文正文给出完整证明，第 7 节逐项核验确定性多项式时间实现；据任务元信息，主结果已有 Lean 形式化证明。本结果族目前仅此一篇手稿，无姊妹篇互相支撑；文中对贪心猜想的讨论（Shibata 的 `@@M@@9/4@@` 反例）属旁引结论，未经形式化。OpenAI 官方声明"未经形式化的结果可能有问题"，本文主结果不在其列，但其余论述仍宜以形式化库与社区核验为准。

{% endraw %}
