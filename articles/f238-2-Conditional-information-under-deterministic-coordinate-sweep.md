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

## 一句话结论

证明了 Thorp 洗牌整副牌的混合时间具最优阶：\(n=2^d\) 张牌经 \(2048d\) 次物理洗牌后排列律趋于均匀；关键在于即使观察任意一大批牌的完整路径，其余牌的条件落点仍近乎均匀。

## 问题背景

Thorp 洗牌（Thorp shuffle）由 Thorp 于 1973 年研究 Faro 牌技时提出：把 \(2^d\) 张牌对半分开，对应位置两两配对，各自独立、公平地决定是否交换。等价地，牌位置是 \(\mathbb F_2^d\) 的顶点，一次物理洗牌沿一个坐标方向做独立公平交换并轮转坐标；\(d\) 个方向各更新一次称为一"扫"（sweep），耗费 \(d\) 次物理洗牌。单张牌一扫后即均匀，但所有牌共用同一批随机开关，联合秩序远未均匀。由于每次物理洗牌只消耗 \(n/2\) 个随机比特，混合时间至少 \(2d-O(1)\)；而上界长期停留在 Morris 的 \(O(d^{44})\)（2008）、Montenegro–Tetali 的 \(O(d^{29})\) 与 Morris 的 \(O(d^3)\)（2013）。Morris 的熵方法已表明"暴露部分牌后剩余的信息"是全牌混合问题的核心，但此前无人能对指定的大列表给出均匀的条件界，这正是本文的切入点。

## 主要结果

主定理对任意确定性初始牌序、任意指定的有序标签列表成立（\(d\to\infty\)）：
1. 在 \(256d\) 次物理洗牌后，任意 \(k\le 7n/8\) 张牌的像与均匀单射分布 \(\Unif(\operatorname{inj}([k],V))\) 的总变差距离（total variation）为 \(o(1)\)；
2. 在 \(1024d\) 次后，任意 \(k\le 15n/16\) 张牌的距离不超过 \(n^{-3/2}\)；
3. 整副牌的排列律满足 \(\|q_d^{*(2048d)}-U_{S_n}\|_{\TV}\to 0\)。

结合支撑数下界得混合时间 \(t_{\mathrm{mix}}=\Theta(\log n)\)，阶数最优。另有条件版强化：固定基集 \(B\) 与不相交列表（\(|B|+k-1\le pn\)），固定个数 \(2b(p)\) 个扫后，条件律与均匀单射的期望总变差 \(\le kn^{-4}\)，且误差只对被观察路径取平均而非逐条断言。这种"平均意义下对指定列表"的条件信息界是本文的独有贡献。

## 证明思路

整个证明把"看牌"翻译为带噪声的线性递推。设已观察一组"阻挡牌"（blocker）的路径，\(V_t\) 为可用位置，被追踪牌的条件误差向量 \(f_t(x)=\Pr\{\Pi_t(a)=x\mid\mathcal H_t\}-\mathbf 1_{V_t}(x)/|V_t|\) 是 \(V_t\) 上支撑的零和向量。其更新规则：两端都可用的位置对上取平均，仅一端可用的位置对上把质量搬运到唯一可用输出。于是 \(f_{t+1}=P_{i_t}f_t+\xi_t\)，其中 \(P_i\) 是坐标 \(i\) 的成对平均算子，\(\xi_t\) 是条件零中心的噪声。第一个关键恒等式：全部 \(d\) 个方向的 \(P_i\) 之积把任何零和向量压为零，故一扫之后能量 \(a_t=\E\|f_t\|_2^2\) 完全来自上一扫内部新生的噪声，且 \(j\) 步之前的噪声恰带几何权重 \(a_t=\sum_{j=1}^d2^{-j}w_{t-j}\)，其中 \(w_t\) 度量"伙伴位置被阻挡"处的能量，正是搬运噪声的源头。

再证 \(w\) 相对 \(a\) 压缩（half-density 引理）。考察当前坐标上一次被使用的时刻：其后两半中的阻挡数接近平衡（Hoeffding 界），而中间的 \(d-1\) 层在两半中独立作用，故伙伴被挡的指示变量与 \(f_s(x)^2\) 条件独立，其条件均值就是该半的阻挡比例。在好历史上求和得 \(w_s\le(1-\delta)a_s+\eta_n\|f_0\|_2^2\)（\(\delta=\alpha/2\)，\(\eta_n=2e^{-\alpha^2n/4}\)），代入比较递推得指数收缩 \(a_t\le(\gamma^{t-2d}+\eta_n/\delta)\|f_0\|_2^2\)，\(\gamma=1-\alpha/4\)。

然后按序暴露列表：把已见牌当作阻挡，下一张牌的条件期望误差 \(\le\sqrt{na_T}/2\)（Cauchy–Schwarz）；在真实前缀律与均匀无放回延拓的相邻律之间插值并求和，分别取 \(\alpha=1/8\) 与 \(1/16\) 即得两个大列表界。

最后由部分信息回到全牌：把标签分成 8 个等块，对每块之补应用 \(256d\) 界（补集的端点像恰好是左陪集 \(gH_i\) 的信息），删去质量超过均匀两倍的陪集得保留律 \(\nu\)；借助伙伴篇《From partial permutation information to Fourier bounds》的等型（isotypic）转移 \(\|\widehat\nu(\lambda)\|_{\HS}^2\le 32C_2D_\lambda^{-1/2}\)，再经 Plancherel 恒等式与卷积完备化（取 \(p=8\) 次幂）得 \(\|\nu^{*8}-U_{S_n}\|_{\TV}\to0\)，共 \(8\times256d=2048d\) 次物理洗牌。后续章节给出熵、调色板、探针等不同的条件机制——它们提供的是不同的条件陈述，而非更优的混合常数。

## 可信度与备注

本篇主结果暂无形式化证明，请以社区核验为准。族内姊妹篇互相支撑：伙伴篇《Optimal-order mixing of the Thorp shuffle》独立给出 \(1600d\) 的局部证明；《Conditional permutations in a revealed switching environment》从"揭示环境下的条件置换"角度给出另一条常倍 \(d\) 路线；已 Lean 形式化的《Routing densities and representation contraction for Thorp sweeps》则给出绝对常数个扫的表示论收缩。按 OpenAI 官方声明，未经形式化的结果可能有问题。

{% endraw %}
