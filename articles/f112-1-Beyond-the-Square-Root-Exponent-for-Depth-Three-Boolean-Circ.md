---
layout: default
title: "Beyond the Square-Root Exponent for Depth-Three Boolean Circuits"
family: "112"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Beyond the Square-Root Exponent for Depth-Three Boolean Circuits

> 结果族 112：Beyond the square-root exponent for depth-three circuits　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论

构造出一个确定性多项式时间语言：其 \(n\) 位成员函数在无界扇入 OR–AND–OR 电路中所需总门数，在一切充分长的长度上超过 \(2^{A\sqrt n}\)（\(A\) 为任意常数），即达到 \(2^{\omega(\sqrt n)}\)，首次突破显式深度三电路下界的平方根指数壁垒。

## 问题背景

深度三电路（depth-three circuit）即无界扇入的 OR–AND–OR 电路——若干合取范式（CNF）的或——是显式电路下界的经典试验场。Håstad 的随机限制（random restriction）与切换引理（switching lemma）证明奇偶函数（parity）需 \(2^{\Omega(\sqrt n)}\) 门；Håstad–Jukna–Pudlák 的自顶向下方法改进常数，Paturi–Pudlák–Zane 的可满足性编码引理（satisfiability coding lemma）得到最优的 \(\Omega(n^{1/4}2^{\sqrt n})\)——奇偶函数本身就此"到顶"。此后显式下界的指数都停在"常数乘 \(\sqrt n\)"量级。能否让一个多项式时间语言对每个常数 \(A>0\) 都需要多于 \(2^{A\sqrt n}\) 个门，且在每个充分大长度同时成立？"一个"很关键：语言及判定算法须在 \(A\) 之前固定，此问题至今列为公开（GPPST24 第 1.1 节等）。限制底层扇入（bottom fan-in）的模型已有 \(2^{n-o(n)}\) 级结果，但任意扇入下任何函数都是单个 CNF，只有总门数才有意义。

## 主要结果

**主定理（定理 1.1）。** 存在语言 \(L\subseteq\{0,1\}^*\) 与一台确定性图灵机以 \(C(n+1)^a\) 时间判定它，使成员函数 \(f_n\) 满足
\[\lim_{n\to\infty}\frac{\log_2 S_3(f_n)}{\sqrt n}=\infty,\]
等价地：对任意 \(A>0\) 存在 \(N_A\)，使一切 \(n\ge N_A\) 都有 \(S_3(f_n)>2^{A\sqrt n}\)。\(S_3(f)\) 是计算 \(f\) 的 OR–AND–OR 电路中 AND、OR 门总数（底层门与输出门都计入，输入取反免费），不施加一致性（uniformity）或底层扇入限制。

**语言构造（定义 5.1）。** 输入长 \(n\) 时取 \(d=\lfloor n/5\rfloor\)、\(r=\lceil d^{2/3}\rceil\)、\(t\) 为 \(t^6\le d\) 的最大偶数，输入切成四块：\(d\) 个数据位 \(x\)；\(d+r-1\) 个哈希位 \(u\)；\(r\) 位编码首一多项式 \(P\in\mathbb{F}_2[Z]\)；\(t\) 个 \(r\) 位块编码商环 \(R_P=\mathbb{F}_2[Z]/(P)\) 中元素 \(\beta_0,\dots,\beta_{t-1}\)。用 Toeplitz 型矩阵把 \(x\) 线性哈希为 \(h(x)\in R_P\)，当 \(\lambda\bigl(\sum_j\beta_j h(x)^j\bigr)=0\)（\(\lambda\) 取常数项系数）时接受。判定只需 \(O(rd+tr^2)\) 位运算，从不检验 \(P\) 是否不可约。

## 证明思路

整体走相关性（correlation）路线：设 \(g\) 为目标函数的符号。中间层 CNF \(H\) 若喂给恰好表示该函数的顶层 OR，就只接受正例，故 \(gH=H\)；只要 \(g\) 与一切 CNF 相关性都小，至多 \(S\) 个中间门的接受概率之和就盖不住切片的常数接受密度。难点在子句数无界，而切换引理会换范式。证明分三步绕过。

第一步证与子句数无关的限制引理（引理 3.1）：以 \(p\le 1/2\)（\(pk\) 有界）做随机限制，把限制后的宽 \(k\) CNF 展开成带符号的宽 \(b\) CNF 组合，期望总绝对系数质量至多 \(1/(1-\theta)\le 2\)，与子句个数无关。展开沿"连续同时违反子句"的路径做，再逆向计数：每步用违反子句数的倒数抵消子句个数，权重几何衰减。测试始终仍是 CNF，这是与切换引理的本质区别。

第二步证稀疏分解引理（引理 4.1）：用向日葵（sunflower）稀疏化加不相交加细，把 \(m\) 变量上任意宽 \(b\) CNF 分成至多 \(2^{\eta m}\) 个两两不交、至多 \(Mm\) 条子句的片段，使稀疏测试种数不超过 \(2^{Mm(1+b\log_2(2m+1))}\)，联合界即可一次控制。

第三步构造硬切片（slice）：固定非数据位即得数据位上的符号 \(g\)。取不可约 \(P\) 使 \(R_P\) 成域；随机 Toeplitz 哈希把每个非零差均匀散布，联合界给出限制立方上单射概率 \(\ge 1-2^{m-r}\)；单射时多项式插值（interpolation）给出 \(t\)-wise 独立无偏符号；偶数 \(t\) 阶矩加 Markov 不等式给出所有稀疏测试相关性 \(\le 2^{-m/4}\)，再经稀疏分解推到一切宽 \(b\) CNF（\(2^{-m/8}\)）。平均论证即可固定一组输入位——判定器从不搜索硬切片（承袭 PSZ00 输入索引思想）。

最后组合：固定 \(A\)，取 \(s=3A\)、\(B=64(s+1)\)、\(k=\lceil 3(s+1)\sqrt d\rceil\)、\(p=B/\sqrt d\)，选仅依赖 \(A\) 的 \(b\) 使 \(\theta\le 1/2\)。两条估计不需独立性：好限制用系数质量期望，坏限制相关性至多 1，故 \(|\E gH|\le 6\cdot 2^{-m_0/16}\) 对一切宽 \(k\) CNF 成立；常真测试推出切片接受密度 \(\ge 1/4\)。反设电路共 \(S\le 2^{A\sqrt n}\) 门：中间门至多 \(S\) 个、每个至多 \(S\) 条子句，删宽超 \(k\) 的子句后单门误差 \(\le S2^{-k}\)，求和得接受概率 \(\le 6S2^{-m_0/16}+S^22^{-k}\to 0\)，与 \(\ge 1/4\) 矛盾。\(A\) 任意而语言不变，定理得证。

## 可信度与备注

验证状态：主结果已 Lean 形式化（族文档 lean/docs/112.md），这是目前最强的核验手段。本结果族仅此一篇手稿，无姊妹篇交叉印证，可靠性来自文内闭环与上述形式化。按 OpenAI 官方声明，"未经形式化的结果可能有问题"；本文主结果已跨过这道门槛，文献史转述仍以被引原文为准。

{% endraw %}
