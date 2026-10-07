---
layout: default
title: "Constant-factor hardness of directed feedback vertex set"
family: "102"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Constant-factor hardness of directed feedback vertex set

> 结果族 102：The Unique Games Conjecture and optimal approximation thresholds　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对任意固定常数 \(A\ge1\)，在无权有向图上把最小反馈顶点集近似到 \(A\) 因子是 NP-hard 的。此前这一结论依赖唯一游戏猜想，本文把它变成不附带复杂性假设的普通 NP-hardness。

## 问题背景

有向图的最小反馈顶点集（directed feedback vertex set, DFVS）是删去后使余图无环的最小顶点集，等价于命中每条有向圈，可用拓扑序（topological order）在多项式时间内验证。算法方面，Seymour 1995 年关于有向圈分数装填（fractional packing）的工作给出一般的 \(O(\log n\log\log n)\) 近似，Even–Naor–Schieber–Sudan 1998 年给出覆盖加权情形的构造性算法，至今没有实质改进。硬度方面，把无向图每条边换成一对反向弧，顶点覆盖（Vertex Cover）的任何硬度都直接迁移到 DFVS：Dinur–Safra 的 \(10\sqrt5-21\)、以及 two-to-one 游戏路线完成的 \(\sqrt2\) 以下因子相继传入。但"每个常数因子都难"这一更强命题，此前只在 UGC 之下成立：Guruswami–Manokaran–Raghavendra（2008 年，后与 Håstad、Charikar 出期刊版）经最大无环子图与反馈弧集建立，Svensson 2013 年与 Guruswami–Lee 2016 年又给出 YES 结构更强的构造。换言之，常数因子门槛之上始终横亘着一道复杂性假设，本文将其移除。

## 主要结果

主定理：对每个固定实数 \(A\ge1\)，存在从 NP-hard 承诺问题（promise problem）出发的确定性多项式时间归约，产出实例 \((G,k)\) 满足 YES: \(\DFVS(G)\le k\)、NO: \(\DFVS(G)>Ak\)。因此，多项式时间常数近似算法存在当且仅当 \(\mathrm P=\mathrm{NP}\)。两个附带结论：同样的常数因子硬度对最小反馈弧集（directed feedback arc set）在无权、无重弧、无双向弧的有向图上成立；DFVS 版本也可要求图中不出现反向弧。

## 证明思路

出发点是"不完美完备性"的 2-to-1 游戏定理（由 Dinur–Khot–Kindler–Minzer–Safra、Khot–Minzer–Safra、Barak–Kothari–Steurer 等人的工作合成）：区分游戏值至少 \(1-\theta\) 与至多 \(\theta\) 的 2-to-1 游戏是 NP-hard 的，且投影纤维恰好两个——论证完全不消费唯一游戏硬度定理。构造沿用 Svensson 独裁测试（dictatorship test）中受保护顶点与可删测试顶点的分工：受保护的是"秩顶点"，可删的是"测试顶点"。

先建加权图。对每个短的游戏顶点元组 \(\mathbf d\) 与取值于 \([N]\) 的秩函数 \(x\)，建一个代价 \(D+1=10A+1\) 的顶点；当 \(x\) 逐点小于 \(y\) 时加弧，并按前缀投影把相应顶点等同起来。核心不变量：任何全局标号 \(\ell\) 通过 \(x(\ell(\mathbf d))\) 给出评估值，使每条秩弧严格递增，故秩图本身无环。测试顶点分三族：全前缀测试（总质量 \(H\)）、大侧与小侧各一族的单标签测试（质量 \(|X|\) 与 \(|Y|\)）、比较测试（质量 \(K\)），每族都按"逐结果建点、概率计入代价"确定性枚举。YES 情形删去评估元组落入星集的通配测试与所涉边不被满足的比较测试，指数型 Markov 界逐族付账，总代价至多 \(4\)；幸存弧按评估值严格递增，因此无环。

NO 情形反设存在代价至多 \(D\) 的反馈顶点集：秩顶点全部幸存，其拓扑序在秩顶点间诱导出一致的比较位，论文分四步读出矛盾。其一，秩比较：用有限 Ramsey 定理加有限 minimax 造出秩嵌入的分布，使任意三个位置的像分布几乎相同，于是有序比较以高概率一致，得到关于标号元组子集的单调布尔函数。其二，共享前缀的条件化：随机子集把元组按词典序分成胞腔，单调性选出唯一转移胞，全前缀测试保证它在每个二进偏差（bias）下的一步不至于太少，从而条件化后大侧函数的接受概率在每个尺度都不低于偏差的固定常数倍。其三，与字母表无关的关键性（pivotality）预算：单标签测试对"星标在随机排列某个前缀处成为关键"收费，所得量 \(B(f)\) 同时控制总影响力与接受概率除以偏差，其期望不超过 \(D+1\)；于是 Friedgut 的 junta 定理（固定二进偏差版本）给出有界坐标列表，其大小在游戏字母表确定之前就已固定。其四，跨尺度的公共尾变量：用保持投影的耦合比较大侧偏差 \(p_i\) 与小侧偏差 \(2p_i\)，游戏 soundness 使两侧 junta 列表典型地落在不相交的投影纤维里，从而耦合下输出独立；于是每个二进偏差都被迫给小侧预算的尾和贡献一个固定正常数。所有估计针对同一分布下的同一随机变量，把全部 \(M\) 个尺度的贡献相加即超出预算，得出矛盾。

最后去权：把每个顶点代价上取整为 \(\lceil Sw_v\rceil\) 并克隆成相应大小的独立集，弧改为全连接。舍入使任何删除集至多多付一个单位，于是 YES: \(\DFVS\le5S\)、NO: \(\DFVS>DS=10AS\)，取 \(k=5S\) 即得 \(A\) 倍鸿沟。若要禁止反向弧，先把每条弧用私有顶点细分；反馈弧集版本则把每个顶点拆成 \(v^-,v^+\) 并配 \(n+1\) 条私有二长路，最优值与近似解同时保持。

## 可信度与备注

本篇同属该结果族的直接归约支线：硬性起点是已发表的 2-to-1 游戏定理，既不假设 UGC，也与族内中心篇对 UGC 本身的证明相互独立，却共同刻画出同一批问题的最优近似阈值图景，与 Max-Cut、Vertex Cover、Min-UnCut 等姊妹篇互相支撑。按 OpenAI 官方声明，未经形式化的结果可能存在问题；本篇主结果尚无 Lean 形式化证明，请以社区核验为准。

{% endraw %}
