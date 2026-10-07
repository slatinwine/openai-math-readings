---
layout: default
title: "The Weak Inhomogeneous Duffin–Schaeffer Conjecture"
family: "022"
discipline: "Number theory"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | The Weak Inhomogeneous Duffin–Schaeffer Conjecture

> 结果族 022：The weak inhomogeneous Duffin–Schaeffer conjecture　·　学科：Number theory　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

证明了弱非齐次 Duffin–Schaeffer 猜想：对任意固定实位移 \(\gamma\) 与取有限值的 \(\psi\)，只要 \(\sum_q\phi(q)\psi(q)/q\) 发散，则对几乎处处的 \(x\)，\(\|qx-\gamma\|<\psi(q)\) 对无穷多个 \(q\) 成立。这是齐次情形（Koukoulopoulos–Maynard，2020）解决之后，非齐次度规丢番图逼近的又一完整突破。

## 问题背景

度规丢番图逼近（metric Diophantine approximation）研究"典型"实数 \(x\) 能被容差 \(\psi(q)\) 容忍到什么程度。Khintchine 定理（1924）在 \(\psi\) 单调时给出完整判据；Szüsz（1958）把单调理论推广到固定位移的非齐次不等式 \(\|qx-\gamma\|<\psi(q)\)。去掉单调性后，许多分母的逼近区间会大量重叠，区间长度之和不复等于并集测度：Duffin 与 Schaeffer（1941）据此提出用既约分母加权 \(\sum_q\phi(q)\psi(q)/q\) 作判据，这一齐次猜想在 2020 年被 Koukoulopoulos 与 Maynard 证明。非齐次的加权版本此后仍悬置，先后被 Yu（2021）、Chow–Technau（2024）、Beresnevich–Hauke–Velani（2024）列为公开猜想，其中"弱"指分子 \(a\) 不要求与 \(q\) 互素。难点是双面的：无权重判据不够（Ramírez 2017 与 Chow–Hauke–Pollington–Ramírez 2025 给出反例），而要求互素的"强"版本一般又不成立（Hauke-Treuer–Maynard–Pollington 2026 与 He–Liao 2026 的反例覆盖所有非零有理位移）；已知的有理位移定理（BHV 2024）对无理位移则需附加块条件。

## 主要结果

**主定理（弱非齐次 Duffin–Schaeffer）**：设 \(\gamma\in\mathbb R\) 固定，\(\psi:\mathbb N\to[0,\infty)\) 只取有限多个值。若 \(\sum_{q\ge1}\frac{\phi(q)}q\psi(q)=\infty\)（\(\phi\) 为欧拉函数），则对 Lebesgue 几乎处处的 \(x\)，\(\|qx-\gamma\|<\psi(q)\)（\(\|\cdot\|\) 表示到最近整数的距离）对无穷多个正整数 \(q\) 成立。分子不受任何互素限制，位移 \(\gamma\) 无需单调性或任何丢番图（Diophantine）条件——任意无理位移、任意稀疏非单调的容差函数都被覆盖。推论借助 Beresnevich–Velani 质量转移原理（mass transference principle）给出 Hausdorff 测度版本：若尺寸函数 \(f\) 单调且 \(\sum_q\phi(q)f(\psi(q)/q)=\infty\)，则极限集 \(W_\gamma(\psi)\) 在每个有界区间上具有满的 Hausdorff \(f\)-测度。

## 证明思路

全文是"构造加二阶矩"的反证法。先做归约：记 \(r(q)=\psi(q)/q\)，一个"行"是点列 \((z+\gamma)/q\) 配半宽 \(r(q)\)。若 \(qr(q)\) 不趋于零，一个直接的平均论证已给出满测度；否则利用级数发散，把任意靠后的行切成两两不交的有限块，使每块的欧拉加权质量 \(W=\sum\phi(v)r(v)\) 落在固定小区间内。假设正测度集 \(A\) 从某项起避开一切行，目标就是在每块上构造非负加权和 \(F\)：它支在原逼近区间内、一阶质量与 \(W\) 可比、\(\|F\|_2\) 一致有界——三者的张力即是矛盾之源。

核心构造是投影表（projected table）。每行被指派一个分母的整数倍作中心（centre），中心的素因子按尺度从小到大逐级曝光；在部分素数未读出时，行先用更细的投影网格 \((z+a\gamma)/(L_i/d)\) 表示，标签携带原始行与剩余掩码（mask）信息，权重按亏值概率律 \(\pi_I(a)\) 折算。每个素数步执行"加/减列表"匹配：加号标签当且仅当其分子被 \(p\) 整除时"成功"并落到下一投影，配对的减号部分恰在失败时保留。妙处在于，在 \(1/p^\nu\) 平移轨道上取平均后一阶质量精确守恒——成功指标的均值 \(1/p\) 与掩码律的转移概率相消，全程不假设独立性，也不随机化位移。

二阶矩控制面对两个障碍。其一，两点靠近会把分子的整系数组合压进一个过短的区间，直接平均失效；小尺度抽取（small-scale extraction）命题证明，若强估计失效，两族分母的素指数必围绕一个公共支点（common pivot）集中成 \(v=NU_0a/b\) 型结构——这是 Green–Walker 简化的 Koukoulopoulos–Maynard 方法的加权移植——随后变更允许因子，或由旋转二择一引理（rotation alternative）用有理逼近压低计数，或把精确的有理模型重合线性地计入块质量。其二，大素数会使不同块的行反复对齐：文中用会计类（accounting classes）记录历史对齐，配以胞腔剖分与负载截断，剩余相关性由方差预算支付——能量增量恰好等于轨道平均下的方差。最后引入虚拟权重（virtual weights）：它控制实际最终权重，一阶质量保持在 \(c_{\rm hard}\phi(v)r(v)\) 与 \(\phi(v)r(v)\) 之间，所有丢弃损失可精确望远镜求和，且周期结构保证它在固定区间上均匀分布。用它近似 \(A\) 并配合 Cauchy–Schwarz，\(\int_U F\) 的正下界与"\(F\) 支在被 \(A\) 避开的区间内"正面相撞，矛盾完成证明。

## 可信度与备注

本文暂无形式化证明，按 OpenAI 官方声明"未经形式化的结果可能有问题"，最终可靠性有待社区逐条核验；不过论文自成体系，明确声明所有构造与转移估计均在文内证明，并把引用的方法论先例（Koukoulopoulos–Maynard、Green–Walker、Beresnevich–Hauke–Velani 等）与本文新证分开陈述。本结果族在本批任务中仅含这一篇手稿；它与 BHV 2024 的有理位移定理互补（这里去掉了所有位移与块限制），又与"强版本"反例（HMP2026、He–Liao 2026）一起划出边界：无互素要求的弱公式恰好是普遍成立的那一层。

{% endraw %}
