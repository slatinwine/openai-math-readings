---
layout: default
title: "The crossing number of complete graphs"
family: "165"
discipline: "Combinatorics"
formalized: true
source: null
pdfname: ""
---

{% raw %}
# 解读 | The crossing number of complete graphs

> 结果族 165：The Harary–Hill and Zarankiewicz crossing-number formulas　·　学科：Combinatorics　·　验证状态：主结果已 Lean 形式化

## 一句话结论

论文证明了悬置六十余年的哈拉里–希尔猜想（Harary–Hill conjecture）：\(n\) 顶点完全图 \(K_n\) 的普通交叉数恰为 \(\frac14\lfloor\frac n2\rfloor\lfloor\frac{n-1}2\rfloor\lfloor\frac{n-2}2\rfloor\lfloor\frac{n-3}2\rfloor\)，宣告希尔经典构图在任意连续弧画法下都无法改进。

## 问题背景

把一个图画进平面：顶点放在互异的点，边用简单连续弧表示，边内部只在有限个点发生正常交叉；交叉数（crossing number）\(\operatorname{cr}(G)\) 就是所有画法中交叉点数的最小值。完全图（complete graph）\(K_n\) 的交叉数公式由 Guy（1960）给出上界、Harary 与 Hill（1963）正式陈述为猜想。此前进展要么局部、要么渐近、要么受限：Pan–Richter 与 Aichholzer 借助计算机核实到 \(n\le 13\)；半定规划方法只证到猜想值的 \(0.83\) 倍，旗代数（flag algebras）方法推进到约 \(0.9856\) 倍；两页画法（two-page drawings）、柱面画法、\(x\)-有界画法乃至球面测地线画法等整条路线都只在受限画法类内确立下界。如何对完全不受限的画法证明下界，正是六十年来卡住所有人的难点。

## 主要结果

主定理：对每个整数 \(n\ge3\)，

\[\operatorname{cr}(K_n)=Z(n):=\frac14\left\lfloor\frac n2\right\rfloor\left\lfloor\frac{n-1}2\right\rfloor\left\lfloor\frac{n-2}2\right\rfloor\left\lfloor\frac{n-3}2\right\rfloor.\]

按奇偶可写成 \(Z(2s+1)=\binom{s}{2}^2\)、\(Z(2s)=\frac{s(s-1)^2(s-2)}4\)；\(n=1,2\) 时同一公式给出 \(0\)。论文证明两半：任何画法至少有 \(Z(n)\) 个交叉（下界），且存在恰有 \(Z(n)\) 个交叉的画法（上界），合一即哈拉里–希尔猜想成立。

## 证明思路

证明分下、上两半，下界是核心；其策略不是限制画法，而是从画法中提取代数信息。先由附录引理把极小画法归一化（normalization）：换成折线画法，并消灭相邻边（共享端点的边）之间的交叉。再构造核心代数对象：给每条边定向，令 \(I(e,f)\) 为两条边内部交叉的带号交和（signed intersection，符号由交叉处两切向的定向给出）；在公共端点 \(w\) 处用辐条（spoke）的逆时针循环序给出比较符号 \(T_w\)，定义双线性型 \(J(e,f)=I(e,f)+\frac12\sum\sigma_{we}\sigma_{wf}T_w(e,f)\)。关键的圈配对引理（cycle pairing）断言 \(J\) 在任意两条圈（cycle）上取值为零。证明时把两个圈改造成闭折线走道 \(\gamma\) 与向左、右微移的两个版本 \(\eta_\pm\)：圆盘内两条弦的带号交叉恰由端点在圆周上的交替模式决定（局部弦公式），而平面上两条闭折线的总带号交点数必为零——把第一走道的每段锥到远处一点，每个三角形与第二走道的进出交点成对相消；对两个平移版本取平均，公共辐条的比较符号恰好抵消，剩下的正是 \(J\)。

接着是插值工具。给顶点配上互异实标号 \(t_i\) 与拉格朗日权（Lagrange weights）\(w_i=1/F'(t_i)\)：权重恒等式使加权链自动成为圈，于是圈配对引理批量给出恒等式——对每变量次数 \(\le n-2\) 的多项式权 \(H\)，\(J\) 的四重加权和为零。论文再建立"偶节点序探测器"：先证双三角插值（两组三角形格点上的赋值都唯一决定双变量多项式），据此证明带序比较符号的配对 \(M\) 非退化，即与整个测试空间配对全零的多项式必为零。

最后装配下界（奇数 \(n=2s+1\)）：取每变量次数 \(\le s-2\)、在两组端点内各自对称的多项式空间 \(\mathcal S\)，其维数恰为 \(\binom{s}{2}^2=Z(2s+1)\)；把它赋值到每个带号量非零的独立边对上，得评估映射 \(E\)。先在多项式测试中插入差因子，迫使核中多项式在"两条边共享端点"的退化位置为零，于是碰撞因子 \(C=(x-y)(x-v)(u-y)(u-v)\) 整除它；除掉 \(C\) 后对称性与核资格都保持，次数可以无限下降，故 \(E\) 单射。再把圈恒等式乘上六因子差积 \(\Delta\) 用第二次，得像空间在非退化对角对称型下全迷向（totally isotropic），维数至多是坐标数之半，而每个支撑边对至少贡献一个交叉。合并得 \(c(D)\ge\binom{s}{2}^2\)；偶数情形由删点计数 \((n-4)c(D)\ge n\binom{s-1}2^2\) 导出 \(Z(n)\)。

上界则回到经典的两页画法：顶点排在一条"书脊"直线上，按 \(i+j\bmod n\) 的余数分两色，两色边分别画成上、下半平面的半圆；沿循环序数间隙做初等计数，交叉数恰为 \(Z(n)\)。

## 可信度与备注

主结果已有 Lean 形式化证明（结果族 165 的说明附有 Lean 文档链接）。姊妹篇《完全二部图的交叉数》与本文共享同一归一化附录与圈配对引理——论文明确注明该论证与姊妹篇的相应引理一致，两文在同一"带号交叉 + 插值"框架下分别解决 Harary–Hill 与 Zarankiewicz 两大猜想，互相支撑。按 OpenAI 官方声明，未经形式化的结果可能有问题；本篇主结果已形式化，属可信度最高一档，具体细节仍建议以社区核验为准。

{% endraw %}
