---
layout: default
title: "Rigidity of the Turing degrees"
family: "241"
discipline: "Mathematical logic"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Rigidity of the Turing degrees

> 结果族 241：Rigidity of the Turing degrees　·　学科：Mathematical logic　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文证明图灵度（Turing degrees）偏序 \((\mathcal{D}_T,\le_T)\) 完全刚性：任何保序自同构必为恒等，正面解决刚性猜想，并连带证实 Slaman–Woodin 双解释猜想——"谁计算谁"的序关系足以唯一标记每个度。

## 问题背景

图灵归约（Turing reducibility）\(A\le_T B\) 指以 \(B\) 为谕示（oracle）的图灵机能算出 \(A\) 的特征函数；互相归约的集合视为等同，其等价类即图灵度（Turing degree），全体度构成偏序 \((\mathcal{D}_T,\le_T)\)。这一相对可计算性概念源自 Turing 1939 年的谕示机。自同构问题（automorphism problem）问：丢掉集合的具体编码、只留下抽象的序，还保有多少信息？刚性猜想断言任何满足 \(\mathbf a\le_T\mathbf b\iff\pi(\mathbf a)\le_T\pi(\mathbf b)\) 的双射 \(\pi\) 都是恒等。此前进展：Jockusch–Solovay（1977）证明保跳算子（jump operator）的自同构固定 \(\mathbf 0^{(4)}\) 以上的度；Shore–Slaman（1999）证明跳算子可由序关系定义，因而被一切自同构保持；Slaman–Woodin（2005）进一步证明所有自同构共同固定 \(\mathbf 0''\) 以上的锥（cone），且自同构群可数、每个自同构有算术表示。悬而未决的正是锥外——\(\mathbf 0''\) 以下——的度。

## 主要结果

**刚性定理（定理 1.1）**　在 ZFC 中，对任何序自同构 \(\pi\in\mathrm{Aut}(\mathcal{D}_T,\le_T)\) 与任何度 \(\mathbf a\) 均有 \(\pi(\mathbf a)=\mathbf a\)；对 \(\pi\) 不附加任何可定义性或正则性假设。

**推论 5.1（双解释）**　图灵度序与二阶算术（full second-order arithmetic）无参数双解释（biinterpretable without parameters），这由 Slaman–Woodin 所证"刚性等价于双解释"直接得到。

支撑主定理的技术核心是恢复定理（recovery，命题 4.1）：设 Borel 函数 \(F:\mathbb R\to 2^{\mathbb N}\) 具可数纤维（countable fibers）且满足加法归约 \(F(x+y)\le_T F(x)\oplus F(y)\)，则对每个无理数 \(t\in(0,1)\) 存在余贫集（comeager set）\(G_t\subseteq\mathbb R^2\)，使对每对 \((u,v)\in G_t\) 有有理数 \(\delta\in(0,1)\) 满足 \(C(t)\le_T F(u)\oplus F(u-v)\oplus F(v-u+\delta t)\oplus F(v-u+\delta(t-1))\)，其中 \(C(x)=\{i:q_i<x\}\) 是有理切割（rational cut）编码。该命题与自同构无关，独立成立。

## 证明思路

证明分三步：表示、恢复、消参。

先把自同构"落地"。本文唯一的外部输入是 Slaman–Woodin 表示定理（2005 年未刊手稿定理 6.3.1(2)）：任何自同构 \(\pi\) 都由某个算术的、因而 Borel 的函数 \(\widehat F:2^{\mathbb N}\to 2^{\mathbb N}\) 诱导，即 \(\deg_T\widehat F(A)=\pi(\deg_T A)\) 对每个集合成立。复合有理切割得 \(F:\mathbb R\to2^{\mathbb N}\)：它 Borel、纤维可数（\(\pi\) 是单射而每个度只含可数多个集合），且由 \(\pi\) 保序又保上确界（join）推出加法归约。

再证四值恢复，机制是有界递推（bounded recurrence）加平均恒等式：状态 \(s_0=0\)，每步读 \(F(u+s_n)\) 的一个固定比特位，据此选增量 \(\delta t\)（向上）或 \(\delta(t-1)\)（向下），记选择为 \(r_n\)。求和得 \(s_N=\delta(Nt-\sum_{n<N}r_n)\)；只要状态始终有界，频率 \(A_N=\frac1N\sum_{n<N}r_n\) 便以误差 \(<1/(N\delta)\) 逼近 \(t\)，而 \(t\) 无理，故可由这些逼近算出 \(C(t)\)。有界性如此保证：可数纤维使 \(F\) 在 \(u\) 两侧近处取到不同值，取差异比特 \(j\)；Borel 函数在某个余贫集上连续，于是该比特在区间两端附近各取常值，等效于"端点附近永远指向内部"，中间行为任意也不越界。递推只需四个真实谕示：辅助对 \((u,v)\) 把"从 \(u+s\) 前进 \(a\)"拆成两次加法 \((u+s)+(v-u+a)=v+s+a\)、\((v+s+a)+(u-v)=u+s+a\)；最小归约指标 \(e(x,y)\) 是 Borel 的，在其连续点附近沿可数群 \(H=\mathbb Q+\mathbb Qt\) 平移时两个程序指标保持固定，于是初始值 \(F(u)\)、返程值 \(F(u-v)\) 与两个增量处的值恰是全部谕示。

最后消参与收尾：四个自变量都是 \(t,u,v\) 的有理线性组合，度不超过 \(\mathbf b=d(t)\vee d(u)\vee d(v)\)，故 \(d(t)\le_T\pi(\mathbf b)\)；用 \(\pi^{-1}\) 作用得 \(\pi^{-1}(d(t))\le_T d(t)\vee d(u)\vee d(v)\) 在余贫集上成立。若 \(\pi^{-1}(d(t))\not\le_T d(t)\)，范畴避锥引理（category avoidance，归功于 Sacks）断言满足该式的 \((u,v)\) 只构成贫集，与 Baire 纲定理矛盾。于是 \(\pi^{-1}(\mathbf a)\le_T\mathbf a\) 对一切度成立（无理数的度穷尽非可计算度，最小度显然固定）；对 \(\pi^{-1}\) 再用一次并配合反对称性即得 \(\pi(\mathbf a)=\mathbf a\)。

## 可信度与备注

主结果已有 Lean 形式化证明（结果族 241 文档），这是目前最强的核验方式；切割编码、Borel 连续性、范畴避锥、四值恢复等关键引理在文中均有自足证明，唯一整体引用的外部输入是 Slaman–Woodin 未刊手稿中的表示定理。本结果族目前仅此一篇手稿，它直接建立在 Jockusch–Solovay、Shore–Slaman、Slaman–Woodin 的经典链条之上；与 Kjos–Hanssen 的置换自同构刚性、Lutz–Siskind 的完满集四元恢复属同族技术但假设各异。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，可靠性相应较高。

{% endraw %}
