---
layout: default
title: "The free energy of the Ising random perceptron"
family: "222"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The free energy of the Ising random perceptron

> 结果族 222：Perceptron free energies and microscopic jamming exponents　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

想象一个极简裁判：它有 N 个只能拨到 +1 或 −1 的旋钮。每来一张随机噪点图，旋钮组合就给出一个投影打分，规则奖优罚劣。考卷越来越多时，这堆旋钮还剩多少"自由度"？这篇论文第一次对任意数量的考卷、任意正温度，算出了这个量（自由能）的精确极限。

**关键词卡片**

- 感知机（perceptron）：最简神经网络——一个神经元，带 N 个 ±1 的权重旋钮。
- 模式（patterns）：随机生成的高斯样本向量，相当于喂给裁判的一张张"考卷"。
- 密度 α（density）：考卷数除以旋钮数，比值越大系统越"拥挤"。
- 自由能（free energy）：对数配分函数除以 N，衡量剩余自由度的"成绩单"。
- 交叠（overlap）：两套旋钮配置的相似度，极限公式里唯一的主角。

**看个具体例子**

设 α=0.5：1000 个旋钮要应付 500 张随机考卷。定理断言自由能收敛到 `@@M@@\inf_q\{\alpha V(q)+S(q)\}@@`——左边 `@@M@@V(q)@@` 是考卷项沿交叠路径 `@@M@@q@@` 的逐层高斯递归，右边 `@@M@@S(q)@@` 是旋钮剩下的熵；在所有非降路径里挑最优折中，得到的正是真值。而且不管打分规则 `@@M@@f@@` 是什么样的有界函数，公式都成立。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <text x="20" y="26" font-size="15" fill="#333">Ising 感知机：旋钮 x=±1，考卷 g，打分 f</text>
  <circle cx="90" cy="80" r="17" fill="#fff" stroke="#333" stroke-width="2"/>
  <text x="78" y="86" font-size="14" fill="#333">g₁</text>
  <circle cx="90" cy="150" r="17" fill="#fff" stroke="#333" stroke-width="2"/>
  <text x="78" y="156" font-size="14" fill="#333">g₂</text>
  <circle cx="90" cy="220" r="17" fill="#fff" stroke="#333" stroke-width="2"/>
  <text x="70" y="226" font-size="14" fill="#333">g₃…</text>
  <line x1="107" y1="85" x2="233" y2="130" stroke="#888" stroke-width="2"/>
  <line x1="107" y1="150" x2="233" y2="150" stroke="#888" stroke-width="2"/>
  <line x1="107" y1="215" x2="233" y2="170" stroke="#888" stroke-width="2"/>
  <circle cx="255" cy="150" r="26" fill="#eef" stroke="#333" stroke-width="2"/>
  <text x="247" y="156" font-size="15" fill="#333">Σ·x</text>
  <line x1="281" y1="150" x2="352" y2="150" stroke="#888" stroke-width="2"/>
  <polygon points="356,150 346,145 346,155" fill="#888"/>
  <text x="288" y="136" font-size="13" fill="#555">投影 gᵃ·x/√N</text>
  <rect x="358" y="122" width="60" height="56" rx="8" fill="#fff" stroke="#c33" stroke-width="2"/>
  <text x="376" y="146" font-size="14" fill="#c33">奖惩</text>
  <text x="368" y="166" font-size="13" fill="#c33">f(·)</text>
  <text x="20" y="262" font-size="14" fill="#333">考卷数 M=αN；自由能极限＝一切交叠路径上的最优折中</text>
</svg>

</div>

**为什么值得关心**

此前的严格结果只在小密度下成立，本文取消了全部限制，把统计物理的 replica 直觉完整扶正为数学定理。

> 暂无形式化证明（AI 结果待核验）

# 过渡 | The free energy of the Ising random perceptron

## 由浅入深：从类比走向定理

**第一级台阶**

导读里的"极简裁判"可以这样重说：对象是一组只能取正负一的权重，以及一批独立随机生成的"考卷"向量；操作是每张考卷与权重做投影后经一个有界的奖惩函数打分，再把所有考卷的分数乘进每种权重组合的权重里。要问的是：权重个数趋于无穷、考卷数按固定比例增长时，加权后的配置空间的对数规模平均每个权重收敛到什么值。

**第二级台阶**

用标准记号：配置空间是 {−1,1}^N 上的均匀测度，模式是独立高斯向量 g^a，共 M=⌊αN⌋ 个，压强定义为 p_N(f)=(1/N)log E exp{Σf(g^a·x/√N)}，其中 f 是有界 Borel 函数。从 Gibbs 测度独立抽两个样本，其交叠 q=(1/N)Σx_i¹x_i² 的分布取代单一典型值，成为描述这个系统的核心量。

**第三级台阶**

主定理的语境是：模式之和不是自旋上的高斯过程，混合 p 自旋的 Parisi 公式不能直接套用，因此公式必须自己保留整个交叠分布。假设方面，f 有界挡住了硬约束（f 取 −∞）带来的极限次序问题，α 固定为正则排除了此前小密度结果的边界。结论说：期望与依概率都有 p_N(f) 收敛到变分值 inf_q{αV_f(q)+S_I(q)}，其中 q 取遍非降交叠路径，V_f 是逐层高斯递归，S_I 是 log cosh 单自旋熵的对偶——任意正温度、任意正密度下的精确公式。

## 一句话结论

本文对独立高斯模式的 Ising 感知机证明了：在任意正温度、任意正模式密度下，自由能极限由一个显式变分公式（Parisi 型高斯递归加 Ising 熵对偶）给出，且依期望与依概率收敛，彻底取消了既往工作必需的小密度限制。

## 问题背景

感知机（perceptron）是神经网络的极简模型：自旋 `@@M@@x\in\{-1,1\}^N@@`（Ising 权重）通过独立高斯模式 `@@M@@g^a@@` 的投影 `@@M@@g^a\cdot x/\sqrt N@@` 获得非线性奖惩。Gardner（1988）、Gardner–Derrida（1988）与 Krauth–Mézard（1989）用 replica 方法研究其存储容量；严格数学此前长期停留在小密度：Talagrand 证明了小 `@@M@@\alpha@@` 时的交叠集中，Bolthausen–Nakajima–Sun–Xu（2022）用近似消息传递条件下的矩方法重新证明了 Gardner 公式。卡壳的根源在于：各模式的对数势之和不是自旋上的高斯过程，混合 `@@M@@p@@`-自旋玻璃的 Parisi 公式无法直接套用；一般密度下的公式必须保留 Gibbs 样本两两交叠（overlap）的整个分布。本文在一切固定 `@@M@@\alpha>0@@`、一切有界 Borel 对数势 `@@M@@f@@` 下补齐了这块空白。

## 主要结果

记 `@@M@@M_N=\lfloor\alpha N\rfloor@@`，压强为归一化对数配分函数
`@@M@@Dp_N(f)=\frac1N\log\int_{\{-1,1\}^N}\exp\Big\{\sum_{a=1}^{M_N}f\big(g^a\cdot x/\sqrt N\big)\Big\}\,\nu_N(dx).@@`
定理（main.tex 引用的 thm:main）：对每个 `@@M@@\alpha>0@@` 与每个有界 Borel `@@M@@f:\mathbb R\to\mathbb R@@`，
`@@M@@D\lim_{N\to\infty}\mathbb E\,p_N(f)=\mathcal P_f(\alpha):=\inf_{q\in\mathcal Q}\{\alpha V_f(q)+S_{\mathrm I}(q)\},@@`
且 `@@M@@p_N(f)@@` 依概率收敛到同一值。变分变量是非降交叠路径 `@@M@@q:(0,1)\to[0,1]@@`；模式项 `@@M@@V_f(q)@@` 是沿 `@@M@@q@@` 的逐层高斯递归（对数矩变换 `@@M@@\mathcal T_{s,d}@@`），熵项 `@@M@@S_{\mathrm I}(q)=\sup_h\{\ell(h)+\frac12\int_0^1 h(u)q(u)\,du\}@@` 是 `@@M@@\log\cosh@@` 单自旋递归的对偶。写 `@@M@@f=\beta\phi@@` 即覆盖任意正逆温度与有界激活 `@@M@@\phi@@`，不要求对称性、凹性或小性条件。

## 证明思路

全文先对光滑紧支撑的 `@@M@@f@@` 证明，再用逼近去掉光滑性。上界用"富化仿射比较"：先把 Ruelle 概率级联（Ruelle probability cascades）的标签作为额外 Gibbs 坐标，配上分层高斯场（hierarchical Gaussian fields）作探针，再把模式数 Poisson 化，使密度成为可微的插值参数。若变分上界不真，一个仿射比较泛函在紧参数区域内取到负的最小值；对扰动参数加二次罚项后，在这个确定性最小点处涨落可控，从而强制成立联合 Ghirlanda–Guerra 恒等式（Ghirlanda–Guerra identities），把自旋交叠与级联标签交叠一并排序。最后沿场参数做变分得到尾部不等式，与"密度每提高一点就多加一个非线性模式"的导数在最小点处矛盾——这正是 Mourrat 超解接触点方法（supersolution contact-point strategy）在非线性模式哈密顿量上的实现。

下界沿 Aizenman–Sims–Starr 空腔（cavity）路线分两步。第一步恢复协方差：先挖掉两个模式并强制交叠恒等式，再把它们作为独立高斯标记放回；带标记的级联计算给出经验梯度协方差的一、二阶矩，证明它收敛为极限自旋交叠的非降确定函数——作用在将来空腔坐标上的高斯场由此从体模型内部被识别出来。第二步空腔增量：加入固定 `@@M@@L@@` 个 Ising 坐标，Taylor 展开与归一化测度估计把增量化归为该高斯空腔场加有限个新模式；坐标可交换性（coordinate exchangeability）识别出熵的次梯度，而场泛函的凹性（Chen–Issa–Mourrat 与 Ho 的中心化 Ising 路径凸性定理）把这一恒等式转化为熵上确界的可达性。对每个增量取匹配的变分下界（模式数取整的误差可控），平均扰动参数并望远镜求和，即完成下界。

最后，删去单个模式给出对维数一致的高斯 `@@M@@L^1@@` 逼近，倾斜递归给出对交叠路径一致的匹配界，二者合力把光滑情形推广到有界 Borel `@@M@@f@@`，并附带可积无界激活与随机符号模式的 universality 结论。

## 可信度与备注

按任务标注，本文主结果 formalized=false，暂无 Lean 形式化证明；族 222 描述中链接的 Lean 文档属族级材料，不应视为本定理已被机器验证，请以社区核验为准。文中自述与族内球面感知机自由能论文为姊妹篇，共享级联富化与空腔机架并互相印证方法。OpenAI 官方声明"未经形式化的结果可能有问题"，阅读细节时宜保持此警觉。

---

# 深挖 | The free energy of the Ising random perceptron

## 深入探讨：像审稿人一样追问 🔍

**问 1：上界证明里最关键、最脆弱的一步是什么？**

（答：是 Mourrat 式"接触点超解"策略（upper 一节）：若变分上界不真，富化后的仿射比较泛函在紧参数域内取到负的最小值；对扰动参数加二次罚项在该确定性最小点处换取涨落控制，强制联合 Ghirlanda–Guerra 恒等式，再用场变分导出尾部不等式，与"密度每加一点就多一个非线性模式"的导数矛盾。命门在同步化（synchronization）把自旋交叠与级联标签交叠一并排序这一步。）

**问 2：下界与标准 Aizenman–Sims–Starr 方案相比，真正的难点在哪？**

（答：标准方案里空腔场协方差由模型直接给出，这里的高斯空腔协方差必须从体模型内部识别：先挖掉两个模式并强制交叠恒等式，再把它们作为独立高斯标记放回，用带标记级联算出经验梯度协方差的一、二阶矩，证其收敛为极限自旋交叠的非降确定函数（bulk 一节）。这是本文模型特有的新环节。）

**问 3：为什么只做有界 Borel 对数势，不覆盖硬约束存储容量？**

（答：论文在引言明确区分：硬约束对应 f 取 −∞，此类零一权重需要额外控制极限的次序（零温与热力学极限交换），本文定理只处理有限 f；Ding–Sun、Huang、Shmalo 等的容量结果是另一套理论，二者不能直接互推。）

**问 4：与 Talagrand、Bolthausen–Nakajima–Sun–Xu 相比，新意是否只是"去掉小密度"？**

（答：不止。前人只得到 replica 对称公式或交叠集中，本文给出全密度、非对称非凹激活下的完整 Parisi 型变分公式；级联标签富化、分层高斯场探针与 Poisson 化密度插值在非线性哈密顿量上首次组合，Ising 熵对偶可达性还自证了 Chen–Issa–Mourrat/Ho 凸性定理的重复场水平情形。）

**问 5：作为 AI 生成证明，最可能出错的模式是什么？**

（答：典型风险在数组/级联的测度变换簿记：论文特意保留"每次副本访问（含同一级联叶的两次访问）上的独立残差高斯噪声"，这类多重富化构造里一个协方差归一化或符号约定（文中凸性定理需"反号并改协方差归一化"）出错，上下界就可能只是看似匹配。该结果未形式化，恰是最需要独立复核的环节。）

**问 6：依期望收敛和依概率收敛，哪个才是使用者需要的？**

（答：后者。依概率（即 quenched）陈述保证对几乎每个实现，单次实验的自由能都逼近公式值；期望版只是中间站。论文两者都证。）

**问 7：谁会用到这个结果？**

（答：存储容量与学习理论社区：f=βφ 覆盖任意正温有界激活，随机符号模式的 universality 在高斯零测不连续条件下也附带给出；族 222 的姊妹篇（球面感知机、微观阻塞指数）与之共享机架，是 jamming 指数严格化的基础。）

**总评**

本文把感知机自由能从"小密度孤岛"推到全密度范围，方法机架与姊妹篇互相印证；最大风险在于富化级联与测度变换的簿记未被机器验证，一处符号或归一化错误即可同时损毁两个界。

{% endraw %}
