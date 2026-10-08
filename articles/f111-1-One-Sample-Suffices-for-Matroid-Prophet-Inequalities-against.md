---
layout: default
title: "One Sample Suffices for Matroid Prophet Inequalities against an Almighty Adversary"
family: "111"
discipline: "Theoretical computer science"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | One Sample Suffices for Matroid Prophet Inequalities against an Almighty Adversary

> 结果族 111：One-sample matroid prophet inequalities against an almighty adversary　·　学科：Theoretical computer science　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

一排礼盒依次递来，打开看到金额就必须当场决定收不收，收了不能退；更麻烦的是有些盒子互相"犯冲"，犯冲的不能同时收。"先知"是全部看完再挑的人。你不知道金额的分布规律，只允许提前对每个盒子试抽一次看个参考值；安排盒子顺序的对手甚至能看光你的参考值、每次金额，连你掷骰子的种子都一览无余。苛刻到这个地步，本文构造的规则仍保证拿到先知期望收益的固定比例。

**关键词卡片**

- 先知不等式（prophet inequality）：把"在线不可反悔的选择"与"事后全知的最优"作比较的定理。
- 拟阵（matroid）：抽象刻画"哪些组合可同时拿"的约束，如"选中的向量须线性无关"。
- 单样本（single sample）：每个元素只看一次独立试抽，以此替代未知的值分布。
- 全能对手（almighty adversary）：看完样本、在线值与算法全部随机种子后再排顺序的对手。
- 常数竞争比（constant competitive ratio）：期望收益 ≥ 2⁻³¹⁰ × 先知——数字极小，但与规模无关。

**看个具体例子**

三个盒子：样本依次为 5、2、6，在线值依次为 8、3、7，且盒 1 与盒 3 犯冲。先知全知全览，拿 8+3=11；一种直觉玩法是"只收明显高过自己样本的盒子"——本例收下盒 1、放弃其余，得 8。论文的正式规则更精细，但接口相同，保证 `@@M@@\mathbb{E}[\text{收益}]\ge 2^{-310}\cdot\mathbb{E}[\text{先知}]@@`，且收下的组合永远不犯冲。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="280" y="26" text-anchor="middle" font-size="15" fill="#333333">三个礼盒：先看样本（上），再决定收不收在线值（盒内）</text>
  <line x1="110" y1="95" x2="450" y2="95" stroke="#e0592a" stroke-width="2" stroke-dasharray="7 5"/>
  <text x="280" y="86" text-anchor="middle" font-size="13" fill="#e0592a">盒 1 与盒 3 犯冲：不能同时收</text>
  <text x="110" y="74" text-anchor="middle" font-size="13" fill="#777777">样本 5</text>
  <text x="280" y="74" text-anchor="middle" font-size="13" fill="#777777">样本 2</text>
  <text x="450" y="74" text-anchor="middle" font-size="13" fill="#777777">样本 6</text>
  <rect x="70" y="100" width="80" height="90" rx="8" fill="#eef4fb" stroke="#3b82c4" stroke-width="2"/>
  <rect x="240" y="100" width="80" height="90" rx="8" fill="#eef4fb" stroke="#3b82c4" stroke-width="2"/>
  <rect x="410" y="100" width="80" height="90" rx="8" fill="#eef4fb" stroke="#3b82c4" stroke-width="2"/>
  <text x="110" y="135" text-anchor="middle" font-size="14" fill="#333333">在线值</text>
  <text x="110" y="164" text-anchor="middle" font-size="16" font-weight="bold" fill="#333333">8</text>
  <text x="280" y="135" text-anchor="middle" font-size="14" fill="#333333">在线值</text>
  <text x="280" y="164" text-anchor="middle" font-size="16" font-weight="bold" fill="#333333">3</text>
  <text x="450" y="135" text-anchor="middle" font-size="14" fill="#333333">在线值</text>
  <text x="450" y="164" text-anchor="middle" font-size="16" font-weight="bold" fill="#333333">7</text>
  <text x="110" y="222" text-anchor="middle" font-size="13" fill="#2e8b57">✓ 收</text>
  <text x="280" y="222" text-anchor="middle" font-size="13" fill="#999999">✗ 弃</text>
  <text x="450" y="222" text-anchor="middle" font-size="13" fill="#999999">✗ 与盒1犯冲</text>
  <text x="280" y="254" text-anchor="middle" font-size="13" fill="#555555">先知拿 8+3=11；本例规则拿 8。一般保证：期望收益 ≥ 2⁻³¹⁰ × 先知期望</text>
</svg>

</div>

**为什么值得关心**

它把"零分布知识"的在线选择推到最严苛的对手模型：连算法的随机种子都被看光，一个样本仍然够用——突破在于"常数比成立"这件事本身，而不在常数大小。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

在任意有限拟阵（matroid）上，每个元素仅凭一个独立样本、完全不知道值分布，就存在在线选取规则：即使到达顺序由看得见全部样本、在线值乃至算法完整随机种子的"全能对手"（almighty adversary）决定，仍能拿到离线最优期望收益的固定常数比例（`@@M@@2^{-310}@@`）。

## 问题背景

先知不等式（prophet inequality）把"在线不可撤销选择"与"事后最优"作比较：元素带着各自未知分布的非负值依次到达，看到当前值必须立刻决定接受与否，且已接受集合须始终保持拟阵独立；基准 `@@M@@\OPT_M(v)@@` 是知道全部实现值后可取得的最优。经典地，单选择情形在已知分布时有尖锐的 `@@M@@1/2@@`（Krengel–Sucheston，因子 2 界归功于 Garling）；Kleinberg 与 Weinberg 把同样的 `@@M@@1/2@@` 推广到已知分布的任意拟阵。分布未知时，Azar–Kleinberg–Weinberg 提出用独立样本替代分布知识，Rubinstein–Wang–Weinberg 在单选择时用一个样本恢复了最优 `@@M@@1/2@@`。但对一般拟阵，已有常数比结果要么需要随规模增长的对数级样本数（Fu 等，以及 Feldman–Svensson–Zenklusen 的改进），要么只允许与样本、在线值和随机币都无关的固定顺序（Abdi 等）。在"全能对手"——看清样本、在线值与算法全部随机种子之后再排定顺序——面前，单样本的常数比保证一直空缺，本文补上了这一块。

## 主要结果

主定理断言：存在可测的在线选取规则，不依赖任何分布描述。对任意有限已知标签拟阵 `@@M@@M=(E,\mathcal I)@@` 与相互独立的非负随机对 `@@M@@(S_e,V_e)@@`（`@@M@@S_e@@` 为样本、`@@M@@V_e@@` 为在线值，二者同服从任意律 `@@M@@D_e@@`），只要 `@@M@@\Ex[\OPT_M(V)]<\infty@@`，规则先收到样本向量 `@@M@@S@@`，再用与 `@@M@@S,V@@` 独立的种子 `@@M@@R@@` 运行；则对任何可测的顺序规则 `@@M@@\pi@@`——允许它依赖 `@@M@@M@@`、诸 `@@M@@D_e@@`、`@@M@@S@@`、`@@M@@V@@` 以及完整种子 `@@M@@R@@`——规则接受集 `@@M@@A@@` 拟阵独立，且

`@@M@@D\Ex\Big[\sum_{e\in A}V_e\Big]\ge 2^{-310}\,\Ex[\OPT_M(V)].@@`

常数与拟阵的规模、秩及分布均无关；论文不主张多项式时间可实现（第 6 节实际证得更强的 `@@M@@2^{-293}@@`，定理陈述留有余量）。同一构造还给出秘书问题（secretary problem）推论：随机观察前缀被牺牲后，即使看见全部权重、有序前缀与完整种子的对手任意重排剩余元素，仍有常数比保证。

## 证明思路

证明先落到"固定向量"版本（命题 2.1）：权重 `@@M@@w@@` 是确定性的隐藏向量，规则从种子中抽取掩码 `@@M@@B_0@@`，揭示并牺牲其中标签，要证 `@@M@@\Ex_R[\min_\pi\sum_{e\in A}w_e]\ge 2^{-293}\OPT_M(w)@@`——极小值在期望之内，对手可为每个种子另选顺序，这是全能对手的严酷之处。随后作"胶水"耦合（引理 2.2）：在 `@@M@@B_0@@` 上取样本值、在其余坐标取在线值拼成的向量与 `@@M@@V@@` 同律且与整个种子独立；逐到达归纳可知两种执行接受集完全相同，故对手选任何顺序都不优于上述取极小。

主分支先把权重向下舍入为以 `@@M@@B=2^{32}@@` 为底的几何级数，再让四个独立掩码分工：`@@M@@H@@`（概率 `@@M@@1/2@@`）过滤候选，`@@M@@D@@`（`@@M@@1/4@@`）登记权重组并提供密度数据，`@@M@@C@@`、`@@M@@T@@`（各以稀疏率 `@@M@@t=2^{-140}@@`）分别提供"卫兵"与在线资格稀疏化；`@@M@@H\cup D\cup C@@` 上的标签被牺牲。对每个登记组 `@@M@@h@@`，密度扩张 `@@M@@Q_h(P)@@` 取最大化 `@@M@@|D_h\cap Z|-\kappa\rk(Z)@@`（`@@M@@\kappa=2^{100}@@`）的最大 flat（等于自身闭包的集合），自低向高迭代出名义路径 `@@M@@X_h(k)@@`，`@@M@@k@@` 是与真实到达时间无关的辅助时刻；再用卫兵提前一步扩张成守卫路径 `@@M@@F_h(k)@@`。按随机奇偶把最终路径分层，每层在基 flat `@@M@@\widehat F(b-2)@@` 上贪心接受使秩增加的标签；嵌套性保证无论何种到达顺序，并集始终拟阵独立。

分析需闯三关。其一是安全：把卫兵掩码沿辅助时间反向暴露，配合"不相交查询证书"引理（成功交易数至多 `@@M@@\log(1/\delta)@@`），可知每个非环标签大概率在条件退出概率 `@@M@@p\ge\eta@@` 的步骤离开名义路径；再用混合转移把离去卫兵的比特换成测试掩码比特，联合退出概率恰为 `@@M@@p^2@@`，一个确定性包含关系保证联合退出即"安全"。其二是样本转秩：安全样本本身已被牺牲，残差集合又依赖本组掩码，逐集合估计行不通；作者以"标记枢轴"组合引理（依靠 Schläfli 超平面区域计数）在掩码暴露前枚举出大小至多 `@@M@@\exp(1000\log\kappa\cdot n/\kappa)@@` 的残差族，一次联合界排除大残差。其三是记账：名义路径换成最终路径的扩张费，由单一生成元集合经条件秩的伸缩求和只付一次账；独立 `@@M@@T@@` 稀疏化后的秩统计量对一切排列同时下界接受数，此时才取期望并按权重层加权求和。最后与处理权重集中于单标签的最大值分支等概率混合，得常数 `@@M@@2^{-140-16-5-100-32}=2^{-293}@@`。

## 可信度与备注

本文暂无形式化证明，按 OpenAI 官方声明，未经形式化的结果可能存在问题，请以社区核验为准。本结果族目前仅此一篇手稿，结论自成一体：固定向量命题、单样本模拟与秘书推论由同一条构造链推出。常数 `@@M@@2^{-310}@@` 数值极小，其意义在"单样本＋全能对手"下首次取得与秩无关的常数比这一质的突破；与 Abdi 等固定顺序下的 `@@M@@1/2@@` 结果相比，两者对手接口不同（逐序下界对照期望内的极小值），不宜直接比较。

{% endraw %}
