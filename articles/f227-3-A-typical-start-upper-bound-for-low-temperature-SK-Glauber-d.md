---
layout: default
title: "A typical-start upper bound for low-temperature SK Glauber dynamics"
family: "227"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | A typical-start upper bound for low-temperature SK Glauber dynamics

> 结果族 227：Critical SK autocorrelation processes and dynamics across the temperature transition　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论
论文证明：在零场高斯 SK 模型的低温相（固定 \(\beta>1\)），把一次 Gibbs 抽样固定为初态，其全变差距离到平衡在 \(\exp(n^{1-1/40000000})\) 时间内降至 \(1/4\) 以下，联合概率趋于 1。这说明低温下指数级慢混合主要是"病态初态"现象，典型平衡初态混合快得多。

## 问题背景
SK 模型（Sherrington–Kirkpatrick model）是自旋玻璃（spin glass）的范式：\(n\) 个 \(\pm1\) 自旋经独立高斯耦合两两作用，哈密顿量为 \(H_n^J(\sigma)=\frac1{\sqrt n}\sum_{i<j}J_{ij}\sigma_i\sigma_j\)。自然问题：单点热浴动力学（heat-bath dynamics，即 Glauber 动力学）多久达到平衡，即混合时间（mixing time）——全变差距离（total variation distance）降到 \(1/4\) 所需时间。高温相已有多项式混合（Eldan–Koehler–Zeitouni、Wang、Boban–Li–Oveis Gharan 等覆盖 \(\beta<1/2\) 邻域）；低温相则相反，Sellke（2025）证明存在"带缺口"的构型使最坏初态混合为指数级，并明确提出：若初态本身抽自 Gibbs 测度，混合能否快得多？本文在整个固定低温区 \(\beta>1\) 给出该问题的肯定上界。

## 主要结果
主定理（Theorem 1.1）：对每个固定 \(\beta>1\)，存在 \(c_\beta\in(0,1)\)（证明允许 \(c_\beta=1/40000000\)）使
\[\mathbb P_{J,\,\sigma_0\sim\pi_{n,\beta}^J}\Big\{T_{n,\beta}^J(\sigma_0)\le\exp\bigl(n^{1-c_\beta}\bigr)\Big\}\to 1,\]
概率同时对无序变量（disorder）\(J\) 与 Gibbs 抽样初态 \(\sigma_0\) 取。初态在评估距离前已固定，其随机性不进入转移律——否则平稳性会让距离恒为零。结合姊妹篇的典型初态下界 \(\exp(n^{1/10000})\)，推论 1.2 给出双侧估计：\(\exp(n^{1/10000})<T_{n,\beta}^J(\sigma_0)\le\exp(n^{1-1/40000000})\) 以联合概率趋于 1 成立，两端都是"指数为 \(n^{1\pm o(1)}\)"的拉伸指数（stretched exponential）尺度，且下界来自本结果族的障碍篇（OpenAISKBarriers2026）。

## 证明思路
骨架是构造一个与耦合矩阵相关的"提案分布"，用熵的正反两个比较把提案与 Gibbs 联合律 \(P(dG,x)=\gamma(dG)\pi_G(x)\) 联系起来。先做标量准备：组合 Lopatto 的全区间支撑定理（Parisi 极小测度支撑为整个区间）、Chen 与 Jagannath–Tobasco 的变分平稳性、Guerra 上界及 Auffinger–Chen 的 Parisi 方程正则性，得到沿整段重叠区间成立的精确标量恒等式。再构造提案（第 4 节）：坐标服从 Parisi 型扩散 \(dZ=\rho\,dB+\sqrt{1-\rho^2}\,dD\)，其中矩阵信息流 \(B\) 由逐次正交化的高斯查询生成（思路承 Bolthausen 的 TAP 迭代与 Montanari 的 AMP），\(D\) 为独立布朗运动；扩散越过 Parisi 支撑端点后继续，用权 \(\rho\) 逐渐稀释矩阵信息。精确的标量恒等式让"经矩阵信道付出的熵"与"提案获得的能量"相互抵消，导出两个关键估计：前向相对熵（relative entropy）\(\mathrm{KL}(Q_l\Vert P)\le 2n^{1-l/2}\)，以及例外事件（概率至少 \(1-\exp(-n^{1-10l})\)）外提案被 \(\exp(n^{1-l/2})P\) 支配的似然上界。仅有前向熵不足以保证提案覆盖每个大质量集合，于是反向比较（第 5 节）：把 Gibbs 联合律条件在自旋上，剩余无序律强对数凹（strongly log-concave），经强对数凹传输与高斯光滑化可逆转熵不等式，得到提案对每个 Gibbs 质量可观的集合都赋正概率下界。然后是均衡割流估计（第 6 节）：反设某割 \(S\) 两侧质量均 \(\ge n^{-d}\) 而平稳流（stationary flow）\(\le\exp(-n^{1-b/20})\)，则其按哈明距离放大的边界只有极小 Gibbs 质量；取细、粗两个视界（horizon）的提案共享同一光滑化基，在 \(\theta\) 网格上旋转高斯输入使相邻粗提案哈明距离很小——覆盖性让两个细端点以正概率落在割两侧，似然上界又迫使中间粗构形避开放大边界，而短步序列跨割必然触及边界，矛盾。最后（第 7 节）把流估计转为混合：有限链引理先删去不扩张的小质量集合，保留质量 \(>1-\varepsilon\) 的集合，用可逆 Cheeger（等周）证明在其上得 Poincaré 不等式，再用熵耗散（Diaconis–Saloff-Coste）控制固定初态全变差距离对 \(\pi\) 的平均；取 \(T=\exp(n^{1-b/40})\) 即 \(c_\beta=b/40=1/40000000\)，马氏不等式说明慢初态的 Gibbs 质量趋于零。稀有慢初态不碍事，正是因为论证只需平均意义的好性质，而不要求轨道停留在保留集中。

## 可信度与备注
主结果暂无 Lean 形式化证明，且论证依赖大量外部输入（Lopatto、Chen、Jagannath–Tobasco、Guerra 等），请以社区核验为准。它与同族姊妹篇互补：临界混合篇定出 \(\beta=1\) 的 \(n^{2/3}\) 指数，障碍篇提供典型初态下界，本篇双侧推论正是二者合成，共同拼出跨温度转移的混合图景。按 OpenAI 官方声明，未经形式化的结果可能存在问题。

{% endraw %}
