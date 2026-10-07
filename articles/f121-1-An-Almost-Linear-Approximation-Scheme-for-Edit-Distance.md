---
layout: default
title: "An Almost-Linear Approximation Scheme for Edit Distance"
family: "121"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | An Almost-Linear Approximation Scheme for Edit Distance

> 结果族 121：Almost-linear approximation of edit distance　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明：对任意固定有理数 \(\varepsilon\in(0,1)\)，存在随机算法在 \(N^{1+o(1)}\) 的最坏情形期望时间内，把总长 \(N\) 的两串的编辑距离估计到 \((1+\varepsilon)\) 因子以内（成功概率 \(\ge 2/3\)），把该精度下的最好时间纪录从 \(n^2/2^{\log^{\Omega(1)}n}\) 推进到近线性。

## 问题背景

编辑距离 \(\ED(x,y)\) 是把串 \(x\) 改成 \(y\) 所需的最少插入、删除、替换次数，源于 Levenshtein（1966）对传输差错的研究，是比较字符串最基本的度量。经典动态规划（Wagner–Fischer，1974）以 \(O(N^2)\) 时间精确求解；Backurs–Indyk 进一步证明，强次二次的确定性精确算法将推翻强指数时间假设（SETH）——但这一下界并不排除近似计算。近似算法则一路演进：Bar-Yossef 等人得到准线性时间的 \(n^{3/7}\) 因子，Andoni–Krauthgamer–Onak 做到 \(n^{1+\xi}\) 时间内的多项式对数因子，2020 年前后常数因子近似落地（Andoni–Nosatzki：\(O(n^{1+\xi})\) 时间、只依赖 \(\xi\) 的因子），Mao–Rubinstein 更进一步首次实现任意 \((1+\varepsilon)\) 精度，但时间仍为 \(n^2/2^{\log^{\Omega(1)}n}\)。速度与精度能否兼得——在误差趋于零的同时把总工作量压到 \(N^{1+o(1)}\)——正是本文解决的问题。

## 主要结果

主定理：存在一个统一的（uniform）随机算法，输入总长 \(N=|x|+|y|\) 的字符串对（符号为对 \(N\) 多项式规模的整数标签）与有理数 \(\varepsilon\in(0,1)\)，输出非负整数 \(\widehat D\)，满足

\[\Pr\bigl[\ED(x,y)\le\widehat D\le(1+\varepsilon)\ED(x,y)\bigr]\ge\frac{2}{3}.\]

对每个固定的有理 \(\varepsilon\)，该算法在对数字长 RAM（logarithmic-word RAM）上的最坏情形期望运行时间为 \(N^{1+o(1)}\)；期望只对算法内部随机性取，且计入输入处理、预处理、数值计算、随机采样与数据结构操作的全部开销。相等的字符串确定性地返回零。论文有两点诚实限定：算法在依赖 \(\varepsilon\) 的长度阈值以下退回精确动态规划，故这是渐近意义下的近似方案（approximation scheme），不主张对 \(1/\varepsilon\) 的多项式依赖；输出仅为距离估计，不重构编辑脚本（edit script）。

## 证明思路

框架上，先把第一棵字符串 \(x\) 递归切成一棵 \(M\) 叉区间树（interval tree），一个"状态"由源区间 \(I\) 与目标端点对 \(q\) 组成，真值 \(c(I,q)\) 即两段子串的编辑距离。一条几何引理（connection inequality）允许子目标段之间存在缝隙或重叠，只按端点错位量收取"连接费"，于是相邻动作无需严丝合缝即可比较。

第一步先造粗种子。作者移植并加固 Andoni–Krauthgamer–Onak 的移位树（shift tree）与精度采样（precision sampling）：对每个状态和每个二进猜测 \(k\)，在 \(B\) 叉粗树上做带移位惩罚的动态规划，再用随机的非均匀加性阈值大幅剪枝。每个表项配独立随机流、惰性求值，使得以至少 \(0.99\) 的概率在整个（绝大多数永不被查询的）定义域上同时成立 \(c\le U^{(0)}\le A_{\mathrm{init}}c\)，而任一表项首次被——哪怕是自适应地——求值时，条件期望代价仅 \((1+|I|)2^{o(H)}\)。

第二步是本文的核心新意：预测对齐路径的走向。先用宽动作族传播种子得到成本代理，把"速度"定义为净移位除以预测总成本（\(\widehat v=z/Z\)），并要求对齐在每个切点处的移位满足近似不动点关系 \(p=p_0+\widehat v\,\Phi_j(p)\)，从而把候选目标位置压缩成一条窄带（band）。分析时虚构一棵"比较树"：固定最优对齐、递归圆整其子端点；代价加权的偏差求和可以伸缩（telescoping），据此控制"预测失灵"节点的总成本。带内则用熵正则化的乐观在线预测规则（Rakhlin–Sridharan 框架，以有限步 Frank–Wolfe 实现）逐时刻选动作，其累计超额由一条"固定块质量的熵不等式"界定；分析中把估计值从下方用真值截断（\(\overline d=\max(c,d)\)），杜绝单点低估抵消他处误差，并对"首次穿越"时刻单独计费。最终对每个固定查询状态得到期望正误差 \(O(D/\ell)\) 与确定性下界 \(d_S\ge D\)。

第三步是种子放大与收尾：取 \(H^2\) 个独立副本、用上中位顺序统计量把近似因子每轮从 \(A\) 降到 \(4A/F\)，重复至 \(A\le F\) 后做最后一次精化，Markov 不等式即给出 \((1+\varepsilon)\) 精度与至少 \(2/3\) 的成功率。至于 \(N^{1+o(1)}\) 的工作量：共享组采样与公共圆整网格把当前指标的递归子调用数压到略高于树的分支因子；沿依赖路径看，每次调用要么同指标在树上下降、要么使指标或轮数减小，两类计数合并便得期望总工作量界。

## 可信度与备注

按本批任务元数据，该论文主结果尚无 Lean 形式化证明（族概述中虽附 Lean 文档链接，但论文条目标记为未形式化）；OpenAI 官方声明"未经形式化的结果可能有问题"，请以社区核验为准。本结果族 121 仅含这一篇论文，没有直接姊妹篇互相印证；论文对自建的几何、概率与数值引理（第 2–10 节）均给出完整证明，其两大技术支柱——精度采样与多尺度偏差约束——分别来自已发表的 Andoni–Krauthgamer–Onak 与 Mao–Rubinstein 工作。

{% endraw %}
