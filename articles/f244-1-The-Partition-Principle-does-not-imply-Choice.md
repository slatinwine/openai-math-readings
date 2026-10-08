---
layout: default
title: "The Partition Principle does not imply Choice"
family: "244"
discipline: "Mathematical logic"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Partition Principle does not imply Choice

> 结果族 244：The Partition Principle does not imply Choice　·　学科：Mathematical logic　·　验证状态：主结果已 Lean 形式化

## 入门导读 🐣

把无穷多张牌全部发进若干非空的堆。"分割原理"说：只要发得完，就总能从牌里挑出一组互不相同的牌、与堆一一对应。乍看这就是"每堆各挑一张"的选择公理；本文证明它其实更弱——两者并不等价。这个 1902 年提出的问题悬置一百二十余年后，终于有了答案。

**关键词卡片**

- 分割原理（Partition Principle, PP）：若存在满射 `@@M@@X\to Y@@`，则存在单射 `@@M@@Y\to X@@`。
- 选择公理（Axiom of Choice, AC）：从任意一族非空集合里各选出一个元素总是可能的。
- 满射／单射（surjection/injection）：满射把 `@@M@@X@@`"铺满"`@@M@@Y@@`，每个目标都被打到；单射不重复地嵌入。
- 相对一致性（relative consistency）：若 ZF 无矛盾，则 ZF+PP+¬AC 也无矛盾。

**看个具体例子**

微妙之处在于：PP 保证的单射不必"从每堆里挑自家的牌"——落点完全自由（见下图红线）。定理断言：若 ZF 一致，则"分割原理＋对良序指标族的选择＋否定选择公理"也一致；换句话说，仅凭 PP 永远推不出 AC。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280"><text x="190" y="40" font-size="14" fill="#333" text-anchor="middle">X（原集合：5 个元素）</text><circle cx="80" cy="80" r="9" fill="#2c7fb8"/><circle cx="145" cy="80" r="9" fill="#2c7fb8"/><circle cx="210" cy="80" r="9" fill="#2c7fb8"/><circle cx="275" cy="80" r="9" fill="#2c7fb8"/><circle cx="340" cy="80" r="9" fill="#2c7fb8"/><rect x="50" y="200" width="90" height="44" fill="none" stroke="#2c7fb8" stroke-width="2"/><rect x="185" y="200" width="90" height="44" fill="none" stroke="#2c7fb8" stroke-width="2"/><rect x="320" y="200" width="90" height="44" fill="none" stroke="#2c7fb8" stroke-width="2"/><text x="95" y="227" font-size="13" fill="#2c7fb8" text-anchor="middle">块 B1</text><text x="230" y="227" font-size="13" fill="#2c7fb8" text-anchor="middle">块 B2</text><text x="365" y="227" font-size="13" fill="#2c7fb8" text-anchor="middle">块 B3</text><line x1="80" y1="90" x2="95" y2="190" stroke="#666" stroke-width="1.6"/><line x1="145" y1="90" x2="100" y2="190" stroke="#666" stroke-width="1.6"/><line x1="210" y1="90" x2="230" y2="190" stroke="#666" stroke-width="1.6"/><line x1="275" y1="90" x2="235" y2="190" stroke="#666" stroke-width="1.6"/><line x1="340" y1="90" x2="365" y2="190" stroke="#666" stroke-width="1.6"/><polygon points="95,200 91,190 99,190" fill="#666"/><polygon points="100,200 96,190 104,190" fill="#666"/><polygon points="230,200 226,190 234,190" fill="#666"/><polygon points="235,200 231,190 239,190" fill="#666"/><polygon points="365,200 361,190 369,190" fill="#666"/><line x1="95" y1="198" x2="212" y2="94" stroke="#c0392b" stroke-width="2" stroke-dasharray="6 4"/><line x1="230" y1="198" x2="84" y2="94" stroke="#c0392b" stroke-width="2" stroke-dasharray="6 4"/><line x1="365" y1="198" x2="150" y2="94" stroke="#c0392b" stroke-width="2" stroke-dasharray="6 4"/><polygon points="212,86 207,96 217,96" fill="#c0392b"/><polygon points="84,86 79,96 89,96" fill="#c0392b"/><polygon points="150,86 145,96 155,96" fill="#c0392b"/><text x="468" y="120" font-size="13" fill="#666" text-anchor="middle">灰线：满射 f</text><text x="468" y="145" font-size="13" fill="#c0392b" text-anchor="middle">红线：单射 j</text><text x="280" y="266" font-size="13" fill="#666" text-anchor="middle">j 不必取本块元素——这份自由正是 PP 弱于 AC 的空隙</text></svg>

</div>

**为什么值得关心**

这是无选择集合论中最著名的公开问题之一，答案出乎多数人预料；配套的传递对称模型还保持序数不变、不新增基模型元素的可数序列。更弱的两个推论——对偶 Cantor–Schröder–Bernstein 原理与弱分割原理——也随之与选择公理分离。

> 已 Lean 形式化

## 一句话结论

本文证明分割原理不蕴含选择公理：若 ZF 一致，则 `@@M@@\ZF+\PP+\ACwo+\neg\AC@@` 一致，否定了自 1902 年 Beppo Levi 提出后悬置百余年的公开问题。

## 问题背景

分割原理（Partition Principle, PP）断言：只要存在满射（surjection）`@@M@@f:X\twoheadrightarrow Y@@`，就存在反向单射（injection）`@@M@@j:Y\hookrightarrow X@@`；等价地说，任何划分（partition）的块集可嵌入原集合。选择公理（Axiom of Choice, AC）显然蕴含 PP——在每个纤维（fiber）里选一个元素即可。反向问题由 Beppo Levi 于 1902 年提出，悬置一个多世纪，是无选择集合论中最著名的公开问题之一。症结在于：PP 给出的单射不必满足 `@@M@@f\circ j=\id_Y@@`，即不必取划分块自身的元素，这份自由度使人既证不出也驳不倒蕴含；此前数个分离模型的宣称已于 2026 年被撤回。

## 主要结果

论文有两条主定理。定理一（相对一致性）：若 `@@M@@\ZF@@` 一致，则 `@@M@@\ZF+\PP+\ACwo+\neg\AC@@` 一致，其中 `@@M@@\ACwo@@` 是对序标家族（ordinal-indexed families，良序指标族）的选择公理。经典已知 `@@M@@\PP\Rightarrow\ACwo@@`（归于 Pincus），故 `@@M@@\ACwo@@` 并非额外强度。定理二（传递模型形式）：对 ZFC 的每个可数传递模型 `@@M@@V@@`，存在集合力迫 `@@M@@\mathbb Q\in V@@` 与传递的对称子模型（symmetric submodel）`@@M@@W@@`，满足 `@@M@@V\subseteq W\subseteq V[G]@@`、序数相同、`@@M@@W\models\ZF+\PP+\ACwo+\neg\AC@@`，且 `@@M@@W@@` 中每个由基模型元素组成的可数序列都已属于 `@@M@@V@@`。又因 `@@M@@\ZF@@` 中 `@@M@@\PP\Rightarrow\mathsf{CSB}^*\Rightarrow\mathsf{WPP}@@`（对偶 Cantor–Schröder–Bernstein 原理与弱分割原理），两原理也随之与 AC 分离。

## 证明思路

先搭骨架。取基模型 `@@M@@V\models\ZFC@@`，参数 `@@M@@\kappa=\omega_1^V@@`、`@@M@@\mu=((2^{\aleph_0})^+)^V@@`、`@@M@@|I|^V=\mu^+@@`。力迫为乘积 `@@M@@\mathbb Q=\mathbb R\times\mathbb P@@`：`@@M@@\mathbb R=\operatorname{Add}(\kappa,I)@@` 添加 `@@M@@|I|@@` 条 Cohen 子集；`@@M@@\mathbb P@@` 的条件是"图"（diagram），即单射 `@@M@@r:T\hookrightarrow I@@`，`@@M@@r@@` 强于 `@@M@@s@@` 当且仅当 `@@M@@s=r_n@@` 是它的平移子图。`@@M@@T@@` 是特制的左可消幺半群（monoid），由 `@@M@@\omega_1@@` 轮两类手术建成：有限合并实现指定的有限重叠模式，"探针"（probe）插入实现指定的精确交理想。对称群 `@@M@@\Sym(I)^V@@` 同时搬动两坐标，由固定群生成正规滤子，得遗传对称（hereditarily symmetric）名字类与对称模型 `@@M@@W@@`。标签集 `@@M@@A=\{A_j:j\in I\}@@` 是全体新 Cohen 子集；对称性使 `@@M@@A@@` 不可良序，进而 `@@M@@\mathcal P^W(A)\setminus\{\varnothing\}@@` 无选择函数（Hartogs 型论证），故 `@@M@@\neg\AC@@`。

再证 `@@M@@W@@` 中三条性质：(i) 借名字的轨道映射得 `@@M@@\mathrm{SVC}(A)@@`，每个非空集都是某个 `@@M@@A\times\eta@@` 的满射像；(ii) `@@M@@\ACwo@@`：`@@M@@A@@` 有一个可良序部分能遇上任何序标非空子集族的每个成员，一般家族经 (i) 归约后取最元；(iii) 全文核心：`@@M@@A@@` 的每个不可良序满射像都与 `@@M@@A@@` 双射。

(iii) 分三步。先算精确可用性纤维：对固定的不可良序商 `@@M@@A/E@@`，记录每个符号等价类与每个标签在哪些子图上可命名，得理想（ideal）；精确纤维引理用 `@@M@@\mu@@` 个独立探针副本加 Cohen 通有性证明每个理想对应的类与标签各有 `@@M@@\mu@@` 个，支撑下降（support descent）引理排除非法重合。再把纤维沿典范限制等同粘成分量（component），各带可数共尾链；幺半群下降引理把剩余对称压缩为可数群。最后做等变选择：链上"最小码"良序给出初步双射，有界 Cohen 行片段区分可数陪集并协变选定，跨分量搬运输出被 `@@M@@G_q@@` 整体固定的遗传对称图名字，赋值即 `@@M@@A@@` 与 `@@M@@A/E@@` 的双射。

最后是纯 `@@M@@\ZF@@` 归约：任给满射 `@@M@@f:X\to Y@@`，用 (i) 把 `@@M@@X@@` 切片并取互不相交的目标片；可良序片由 `@@M@@\ACwo@@` 作截面，不可良序片由 (iii) 双射拼接，再由 `@@M@@\ACwo@@` 逐片选出单射取并。元理论上先经可构成宇宙把 `@@M@@\Con(\ZF)@@` 化为 `@@M@@\Con(\ZFC+V=L)@@`，再在可数可能非良基的模型上以内部名字商结构完成推导；传递情形按通常赋值实现。

## 可信度与备注

论文主结果已配 Lean 形式化证明（族元信息链接 lean/docs/244.md），属对集合论构造目前最强的核验。本结果族仅此一篇手稿，相对一致性与传递模型两个定理共享同一构造、互为印证；文中与 Ryan-Smith 的 PP 局部化分析及 Holy–Schilhan 的对称积方法相衔接。按 OpenAI 官方声明，"未经形式化的结果可能有问题"，而本文主结果属已形式化之列；个别引理的范式重写细节技术性较强，此处从略。

{% endraw %}
