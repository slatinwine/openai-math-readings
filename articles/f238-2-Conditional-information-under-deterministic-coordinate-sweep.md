---
layout: default
title: "Conditional information under deterministic coordinate sweeps"
family: "238"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Conditional information under deterministic coordinate sweeps

> 结果族 238：Optimal logarithmic mixing of the Thorp shuffle　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 入门导读 🐣

赌场里你买通了发牌员，全程盯死一大批牌每一步的去向，想把剩下的牌也看穿——这篇论文告诉你：盯了也是白盯。它证明即使观察到任意一大批牌的完整轨迹，其余牌的条件落点依然近乎均匀；整副牌经 `@@M@@2048d@@` 次物理洗牌后彻底混匀，阶数 `@@M@@\Theta(\log n)@@` 最优。

**关键词卡片**

- 一扫（sweep）：`@@M@@d@@` 个坐标方向各更新一次，恰好消耗 `@@M@@d@@` 次物理洗牌。
- 阻挡牌（blocker）：被观察、轨迹已知的牌，它们占住的位置构成其余牌的"路障"。
- 条件律（conditional law）：在已知信息（观察到的轨迹）之下剩余牌的分布。
- 均匀单射（uniform injection）：无放回均匀放置的基准分布，条件律要与它比距离。

**看个具体例子**

取 `@@M@@n=2^{10}=1024@@` 张牌：`@@M@@256d=2560@@` 次后，任选不超过 `@@M@@7n/8=896@@` 张牌的联合位置与均匀单射的距离为 `@@M@@o(1)@@`；`@@M@@1024d@@` 次后误差缩到 `@@M@@n^{-3/2}@@`；`@@M@@2048d=20480@@` 次后整副牌均匀。条件版更强：固定一批"路障牌"的完整路径后，再洗固定个数（依赖比例）的扫，剩余牌的条件分布在期望意义下与均匀单射相差不超过 `@@M@@kn^{-4}@@`。

<div>

<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 560 280">
  <line x1="58" y1="50" x2="58" y2="225" stroke="#bbb" stroke-width="1.5"/>
  <path d="M80 200 L160 170 L240 185 L320 140 L400 155 L470 120" fill="none" stroke="#2471a3" stroke-width="2.5"/>
  <path d="M80 140 L160 120 L240 130 L320 90 L400 100 L470 70" fill="none" stroke="#2471a3" stroke-width="2.5"/>
  <path d="M80 88 L160 68 L240 76 L320 48 L400 58 L470 36" fill="none" stroke="#2471a3" stroke-width="2.5"/>
  <path d="M80 212 L160 197 L240 207 L320 177 L400 187 L470 162" fill="none" stroke="#c0392b" stroke-width="2.5" stroke-dasharray="8 5"/>
  <text x="60" y="30" font-size="13" fill="#777">洗牌时间 →</text>
  <text x="46" y="250" font-size="13" fill="#2471a3">实线：被观察牌的完整轨迹</text>
  <text x="46" y="268" font-size="13" fill="#c0392b">虚线：隐藏牌，条件落点仍近均匀</text>
</svg>

</div>

**为什么值得关心**

"暴露部分牌之后还剩多少信息"正是全牌混合的核心难点；本文首次对指定的大列表给出均匀的条件界——误差只对被观察路径取平均，不逐条断言，这是它独有且诚实的强度。

> 暂无形式化证明（AI 结果待核验）

## 一句话结论

证明了 Thorp 洗牌整副牌的混合时间具最优阶：`@@M@@n=2^d@@` 张牌经 `@@M@@2048d@@` 次物理洗牌后排列律趋于均匀；关键在于即使观察任意一大批牌的完整路径，其余牌的条件落点仍近乎均匀。

## 问题背景

Thorp 洗牌（Thorp shuffle）由 Thorp 于 1973 年研究 Faro 牌技时提出：把 `@@M@@2^d@@` 张牌对半分开，对应位置两两配对，各自独立、公平地决定是否交换。等价地，牌位置是 `@@M@@\mathbb F_2^d@@` 的顶点，一次物理洗牌沿一个坐标方向做独立公平交换并轮转坐标；`@@M@@d@@` 个方向各更新一次称为一"扫"（sweep），耗费 `@@M@@d@@` 次物理洗牌。单张牌一扫后即均匀，但所有牌共用同一批随机开关，联合秩序远未均匀。由于每次物理洗牌只消耗 `@@M@@n/2@@` 个随机比特，混合时间至少 `@@M@@2d-O(1)@@`；而上界长期停留在 Morris 的 `@@M@@O(d^{44})@@`（2008）、Montenegro–Tetali 的 `@@M@@O(d^{29})@@` 与 Morris 的 `@@M@@O(d^3)@@`（2013）。Morris 的熵方法已表明"暴露部分牌后剩余的信息"是全牌混合问题的核心，但此前无人能对指定的大列表给出均匀的条件界，这正是本文的切入点。

## 主要结果

主定理对任意确定性初始牌序、任意指定的有序标签列表成立（`@@M@@d\to\infty@@`）：
1. 在 `@@M@@256d@@` 次物理洗牌后，任意 `@@M@@k\le 7n/8@@` 张牌的像与均匀单射分布 `@@M@@\Unif(\operatorname{inj}([k],V))@@` 的总变差距离（total variation）为 `@@M@@o(1)@@`；
2. 在 `@@M@@1024d@@` 次后，任意 `@@M@@k\le 15n/16@@` 张牌的距离不超过 `@@M@@n^{-3/2}@@`；
3. 整副牌的排列律满足 `@@M@@\|q_d^{*(2048d)}-U_{S_n}\|_{\TV}\to 0@@`。

结合支撑数下界得混合时间 `@@M@@t_{\mathrm{mix}}=\Theta(\log n)@@`，阶数最优。另有条件版强化：固定基集 `@@M@@B@@` 与不相交列表（`@@M@@|B|+k-1\le pn@@`），固定个数 `@@M@@2b(p)@@` 个扫后，条件律与均匀单射的期望总变差 `@@M@@\le kn^{-4}@@`，且误差只对被观察路径取平均而非逐条断言。这种"平均意义下对指定列表"的条件信息界是本文的独有贡献。

## 证明思路

整个证明把"看牌"翻译为带噪声的线性递推。设已观察一组"阻挡牌"（blocker）的路径，`@@M@@V_t@@` 为可用位置，被追踪牌的条件误差向量 `@@M@@f_t(x)=\Pr\{\Pi_t(a)=x\mid\mathcal H_t\}-\mathbf 1_{V_t}(x)/|V_t|@@` 是 `@@M@@V_t@@` 上支撑的零和向量。其更新规则：两端都可用的位置对上取平均，仅一端可用的位置对上把质量搬运到唯一可用输出。于是 `@@M@@f_{t+1}=P_{i_t}f_t+\xi_t@@`，其中 `@@M@@P_i@@` 是坐标 `@@M@@i@@` 的成对平均算子，`@@M@@\xi_t@@` 是条件零中心的噪声。第一个关键恒等式：全部 `@@M@@d@@` 个方向的 `@@M@@P_i@@` 之积把任何零和向量压为零，故一扫之后能量 `@@M@@a_t=\E\|f_t\|_2^2@@` 完全来自上一扫内部新生的噪声，且 `@@M@@j@@` 步之前的噪声恰带几何权重 `@@M@@a_t=\sum_{j=1}^d2^{-j}w_{t-j}@@`，其中 `@@M@@w_t@@` 度量"伙伴位置被阻挡"处的能量，正是搬运噪声的源头。

再证 `@@M@@w@@` 相对 `@@M@@a@@` 压缩（half-density 引理）。考察当前坐标上一次被使用的时刻：其后两半中的阻挡数接近平衡（Hoeffding 界），而中间的 `@@M@@d-1@@` 层在两半中独立作用，故伙伴被挡的指示变量与 `@@M@@f_s(x)^2@@` 条件独立，其条件均值就是该半的阻挡比例。在好历史上求和得 `@@M@@w_s\le(1-\delta)a_s+\eta_n\|f_0\|_2^2@@`（`@@M@@\delta=\alpha/2@@`，`@@M@@\eta_n=2e^{-\alpha^2n/4}@@`），代入比较递推得指数收缩 `@@M@@a_t\le(\gamma^{t-2d}+\eta_n/\delta)\|f_0\|_2^2@@`，`@@M@@\gamma=1-\alpha/4@@`。

然后按序暴露列表：把已见牌当作阻挡，下一张牌的条件期望误差 `@@M@@\le\sqrt{na_T}/2@@`（Cauchy–Schwarz）；在真实前缀律与均匀无放回延拓的相邻律之间插值并求和，分别取 `@@M@@\alpha=1/8@@` 与 `@@M@@1/16@@` 即得两个大列表界。

最后由部分信息回到全牌：把标签分成 8 个等块，对每块之补应用 `@@M@@256d@@` 界（补集的端点像恰好是左陪集 `@@M@@gH_i@@` 的信息），删去质量超过均匀两倍的陪集得保留律 `@@M@@\nu@@`；借助伙伴篇《From partial permutation information to Fourier bounds》的等型（isotypic）转移 `@@M@@\|\widehat\nu(\lambda)\|_{\HS}^2\le 32C_2D_\lambda^{-1/2}@@`，再经 Plancherel 恒等式与卷积完备化（取 `@@M@@p=8@@` 次幂）得 `@@M@@\|\nu^{*8}-U_{S_n}\|_{\TV}\to0@@`，共 `@@M@@8\times256d=2048d@@` 次物理洗牌。后续章节给出熵、调色板、探针等不同的条件机制——它们提供的是不同的条件陈述，而非更优的混合常数。

## 可信度与备注

本篇主结果暂无形式化证明，请以社区核验为准。族内姊妹篇互相支撑：伙伴篇《Optimal-order mixing of the Thorp shuffle》独立给出 `@@M@@1600d@@` 的局部证明；《Conditional permutations in a revealed switching environment》从"揭示环境下的条件置换"角度给出另一条常倍 `@@M@@d@@` 路线；已 Lean 形式化的《Routing densities and representation contraction for Thorp sweeps》则给出绝对常数个扫的表示论收缩。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
