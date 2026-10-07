---
layout: default
title: "Cylinder amplitudes and logarithmic bridge-length windows on the honeycomb lattice"
family: "237"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Cylinder amplitudes and logarithmic bridge-length windows on the honeycomb lattice

> 结果族 237：The three-quarter exponent for honeycomb self-avoiding walk　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明临界蜂窝桥的长度有一个对数窗口：高度不超过 \(2h(\log h)^{1/64}\)、长度介于 \(h^{4/3}(\log h)^{-1/8}\) 与 \(2h^{4/3}(\log h)^{1/2}\) 之间的桥，其总质量至少 \(c\,h^{3/4}(\log h)^{-C}\)——首次把"桥长应约 \(h^{4/3}\)"从一阶矩的暗示落实为真实的质量集中。

## 问题背景

高度 \(h\) 的带条上，临界自避行走（critical self-avoiding walk）的预期长度约为 \(h^{4/3}\)，对应指数 \(1/\nu=4/3\)。但总质量与一阶长度矩的比较只能"暗示"这个尺度：极少几条超长路径就可能背负整个一阶矩，质量究竟集中在哪段长度上，此前无从知晓。理论坐标早已有：Nienhuis（1982）预言 \(\nu=3/4\)；Lawler–Schramm–Werner 提出 \(\mathrm{SLE}_{8/3}\) 纲领并预言边界幂 \(5/8\)；Duminil-Copin–Smirnov（2012）在讨论共形不变性时记录了 \(B_H\asymp H^{-1/4}\) 与拱两点函数 \(g^{-5/4}\) 的预测。后续工作（Beaton 等、Glazman–Manolescu、Krachun–Panagiotis）逐步逼近桥质量衰减，但都没有触及长度窗口。本文的拦路虎是"精确归一化"：形式渐近指数不够用，首项系数可能恰好为零。

## 主要结果

桥（bridge）从一条格点线上的固定端口出发、终止于高度 \(H\) 的线上、途中严格介于两线之间；\(\mu(\omega)=X^{|\omega|}\)，\(X=(2+\sqrt2)^{-1/2}\)。主定理（对数桥长窗口）：记 \(R_h=h(\log h)^{1/64}\)，\(\ell_-(h)=h^{4/3}(\log h)^{-1/8}\)，\(\ell_+(h)=h^{4/3}(\log h)^{1/2}\)，则对一切充分大的 \(h\)，
\[\sum_{1\le H\le 2R_h}\ \sum_{\substack{\omega\in\mathcal B_H\\ \ell_-(h)\le|\omega|\le 2\ell_+(h)}}\mu(\omega)\ \ge\ c\,h^{3/4}(\log h)^{-C}.\]
高度求和是结论的一部分；定理不指定具体高度、横向端点或精确长度。若干有限估计有独立价值，构成第二定理：带条桥质量 \(B_H\asymp H^{-1/4}\)；半平面同界拱（arch）两点质量 \(A_g\asymp g^{-5/4}\)；横向位移限制在 \(TH\) 内的桥质量至少 \(c_TH^{-1/4}\)、长度加权质量至多 \(C_TH^{13/12}\)；直径超过 \(r\ge CH\) 的路径质量尾部 \(\le CH^{-1/4}e^{-cr/H}\)；模平移、直径落在 \([R,2R)\) 的多边形满足 \(\sum\mu(P)|P|^2\le CR^{2/3}(1+\log\log R)\)；以及 \(n\) 列正圆柱上缠绕多边形质量 \(J_n\sim\sqrt3/(6n)\)。

## 证明思路

分析部分从有限周长圆柱上的圈图出发：水平切口处的配对态给出有限转移矩阵，图示滑动通过多项式插值确定真空向量；两个标量多项式——Pfaffian 型的 \(Q\) 与行列式型的 \(R\)——编码全部归一化。为排除首系数为零，作者把振子迹（oscillator trace）在两个高斯通道中求值，短程交互的强制性（coercivity）保证换展开合法；长圆论证给出可控余项；正的 Fourier 测度把合流 \(Q,R\) 表为多项式范数，迫使首系数非零，由此得到 \(J_n\sim\sqrt3/(6n)\) 并进一步强化为长方向的指数尾；\(B_H\) 则由独立的开带（open strip）几何单独计算。随后是向平面路径的转移：圈逸度 \(2\) 的包围圈气体经局部通量反转为"访问给定顶点的边界弦"的质量；双端口恒等式数同一条多边形上的两点，其斜渐近在两标记区间尺度悬殊时仍一致，这一致性允许在较小物理尺度校准，得到多边形二阶矩估计。最后的正质量组合论证：带条穿越质量提供受限路径与指定间隙处的帽；包围气体给出一阶长度矩下界；多边形二阶矩控制剪去长路径的损耗；圆柱压强尾排除纵横比过大的路径；幸存者要么已是桥，要么是可外接两条不交连结器（connector）的拱，双割数界控制"回收"倍数；对所述高度范围求和即得窗口定理。

## 可信度与备注

本文主结果暂无 Lean 形式化证明。它是结果族 237 的另一解析支柱：其 \(B_H\asymp H^{-1/4}\)、受限桥的 \(13/12\) 长度加权质量、多边形二阶矩与圆柱压强尾，正是几何主干篇引用的那类精确输入；其边界与多边形估计又与"标记多边形"篇互相印证。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
