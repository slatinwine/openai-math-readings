---
layout: default
title: "Average sensitivity of polynomial threshold functions"
family: "127"
discipline: "Theoretical computer science"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | Average sensitivity of polynomial threshold functions

> 结果族 127：Average sensitivity of polynomial threshold functions　·　学科：Theoretical computer science　·　验证状态：主结果已 Lean 形式化

## 一句话结论

本文证明：\(n\) 维布尔立方体上次数至多 \(d\) 的多项式阈值函数（polynomial threshold function），其平均灵敏度（average sensitivity）不超过 \(8d\sqrt n\)，常数绝对、\(d\) 可随 \(n\) 增长。这确立了 Gotsman–Linial 猜想的渐近形式，并首次去掉了此前最佳界中的多对数损失。

## 问题背景

多项式阈值函数先用实多项式 \(p\) 在布尔立方体 \(\{-1,1\}^n\) 上求值、再取符号 \(f(x)=\sgn(p(x))\)；次数 \(d=1\) 时就是半空间（halfspace）。平均灵敏度又称总影响（total influence），\(I(f)=\sum_{i=1}^n\Pr\{f(X)\ne f(X^{\oplus i})\}\)，度量随机输入下翻转单个坐标改变输出的期望次数，是布尔函数分析与学习理论的核心参数。Gotsman 与 Linial 在 1994 年猜想：\(n\) 元、度至多 \(d\) 的此类函数的灵敏度在某个以 \(x_1+\cdots+x_n\) 为变量的对称函数处取到最大，量级为 \(d\sqrt n\)。Chapman（2018）与 Kim–Maldonado–Wellens 各自构造反例，否定了其中"精确极值"的断言，但渐近界 \(O(d\sqrt n)\) 一直悬而未决：此前最强的是 Kane 的 \(\sqrt n(\log n)^{O(d\log d)}2^{O(d^2\log d)}\)，带有显著的多对数因子损失。本文一举消除该损失，给出对 \(d\) 线性、对 \(n\) 开方的干净界。

## 主要结果

**主定理**：设 \(n\ge1\)、\(1\le d\le n\)，\(p\) 为度至多 \(d\) 的实多重线性多项式（multilinear polynomial），\(f(x)=\sgn(p(x))\)，约定 \(\sgn(0)=1\)。则在均匀分布下 \(I(f)\le 8d\sqrt n\)。常数 8 与 \(d,n\) 均无关，\(d\) 可随 \(n\) 一起增长；\(p\) 允许在立方体上取零，不施加任何正则性条件。阶是最优的：文中给出对称例子 \(p_J(x)=\prod_{j\in J}(t(x)-j-\tfrac12)\)（\(t\) 为取 \(+1\) 的坐标个数，\(J\) 为最靠近中心的 \(d\) 个层指标），其灵敏度 \(I(\sgn p_J)\asymp d\sqrt n\)，故在 \(1\le d\le\sqrt n\) 范围内下界匹配。定理另有两个推论：其一，噪声灵敏度（noise sensitivity）满足 \(\operatorname{NS}_\eta(f)\le Cd\sqrt\eta\)（\(0<\eta\le1/2\)，\(C=8\sqrt2\) 绝对常数），与 Kane 的高斯噪声结果相对应；其二，在输入边缘均匀、标签可任意对立的分布上，PTF 类有误差达 \(\mathrm{OPT}+\alpha\) 的不可知学习（agnostic learning）算法，样本与时间关于 \((n+1)^k\)、\(1/\alpha\)、\(\log(1/\delta)\) 多项式，其中 \(k=\min\{n,\lceil Ad^2\alpha^{-2}\log(4/\alpha)\rceil\}\)。

## 证明思路

证明由一个纯概率引理与一个有限维算子构造拼接而成，两者互不知晓对方存在，最后在装配步骤会合。

先看概率部件（第 2 节）：设 \(U,V\) 同分布，有共同均值与方差 \(\sigma^2\)，且几乎必然满足**单侧**约束 \(V-U\le a\)（反方向不设限），则 \(\E(U-V)^2\le8a\sigma\)。关键在取递增函数 \(g(t)=\tfrac12(t-m)|t-m|\)（即 \(|t-m|\) 的原函数），其增量控制平方位移：\((v-u)^2/4\le g(v)-g(u)\)；而同分布性保证 \(\E g(U)=\E g(V)\)，正负增量相消，于是只需在 \(\{V>U\}\) 上用单侧界与 Cauchy–Schwarz 收尾。全程不需要独立性。

再看算子部件（第 3–4 节）：在 \(\mathbb{C}^{\Omega}\) 中以特征（character）\(\chi_S\) 为基，令 \(V_k\) 为度至多 \(k\) 的特征张成的空间；乘以 \(\sqrt w\)（\(w>0\) 为任意权函数）后逐级取正交补，得到分级空间 \(E_k\)，其维数固定为 \(\binom nk\)。令 \(M=L-\tfrac n2\Id\)（第 \(k\) 级赋特征值 \(k-n/2\)），其平方 Hilbert–Schmidt 范数恒为 \(n2^n/4\)，与权无关；且乘以单个坐标只连接相等或相邻的级。无权时 \(M\) 恰为立方体邻接阵的 \(-1/2\) 倍，每条边的矩阵元素平方为 \(1/4\)。带权时单个边元素可能缩水，作者借交换子（commutator）\(C_i=[M,Z_i]\) 并用两个酉算子 \(J,W\) 证明 \(\|C_i\|_{\op}\le1\)，从而每个边元素平方仍 \(\le1/4\)，且所有"亏损"之和被对角能量控制。由此，对乘以符号函数 \(h\) 的算子 \(H\)，反交换子（anticommutator）\(T=MH+HM\) 的范数能"数出"同号边：\(|\mathcal{E}_h|\le2\|T\|_{\HS}^2\)。

最后装配（第 5 节）：先给 \(p\) 加一个小正常数消去零点（不改变 \(f\)），取权 \(w=|p|\)，令 \(h=\chi f\)（\(\chi\) 为全奇偶性 full parity）。奇偶性逐边变号，故 \(h\) 的同号边恰是 \(f\) 的敏感边。更妙的是，乘 \(\chi\) 把 \(p\) 的 Fourier 支集抬到度至少 \(n-d\) 处，迫使块 \(\Pi_sH\Pi_r\) 在 \(r+s<n-d\) 时消失。把归一化的块范数平方视作随机指标 \((R,S)\) 的概率律，其两个边缘分布均为二项分布 \(\operatorname{Bin}(n,1/2)\)；令 \(U=S\)、\(V=n-R\)，则二者同分布且 \(V-U\le d\) 恰好是那个单侧约束。耦合引理（\(a=d\)，\(\sigma=\sqrt n/2\)）给出 \(\|T\|_{\HS}^2/N\le4d\sqrt n\)，代入边数不等式即得 \(I(f)\le8d\sqrt n\)。

## 可信度与备注

本文主定理已有 Lean 形式化证明（结果族 127 附有对应文档），是 OpenAI 此批手稿中验证等级最高的一类结果。本族仅含这一篇论文，没有姊妹篇交叉支撑，但噪声灵敏度与学习两个推论均由主定理经标准约化（随机分桶、\(L_1\) 多项式回归）直接导出，内部自洽。按 OpenAI 官方声明，未经形式化的结果可能有问题；本文主结果已形式化，推论细节仍建议以社区核验为准。

{% endraw %}
