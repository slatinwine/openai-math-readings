---
layout: default
title: "Cardy's formula for critical Poisson–Voronoi percolation"
family: "224"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Cardy's formula for critical Poisson–Voronoi percolation

> 结果族 224：Critical and quenched near-critical universality for Poisson–Voronoi percolation　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

本文证明临界平面泊松–沃罗诺伊渗流的退火跨越概率在每个有界 Jordan 四边形上都收敛到 Cardy 共形不变公式，正面解决 Schramm 问题 2.12 的退火跨越部分，也是同族另两篇近临界定理的共同基石。

## 问题背景

Cardy 于 1992 年用共形场论预言：临界二维渗流的跨越概率只依赖区域的共形参数（Aizenman 最早给出共形表述）；Smirnov 于 2001 年对三角格点证明了这一公式，成为二维普适性纲领的支柱。Schramm 的遗留问题 2.12 要求对沃罗诺伊渗流证明相应的共形不变性定理。Voronoi 模型的几何完全随机、无偏好格点方向：Bollobás–Riordan 证明其临界染色参数为 \(1/2\)，Tassion 建立各尺度一致的方块跨越估计，Ahlberg 等与 Vanneuville 发展了淬火（quenched）与定量臂估计。然而这些工具只控制跨越与例外几何，要识别极限函数还需一条能穿越不规则随机镶嵌的解析恒等式——Smirnov 的变色技巧依赖正三角形几何，在此失效，正是长期卡壳之处。

## 主要结果

定理（退火 Voronoi 跨越定律）：设强度 \(\varepsilon^{-2}\) 的泊松过程的沃罗诺伊胞被独立公平染色，则对每个有界 Jordan 域 \(D\) 与四个逆时针边界标记 \(a,b,c,d\)，黑胞在 \(\overline D\) 内连接弧 \(ab\) 与 \(cd\) 的概率当 \(\varepsilon\downarrow0\) 时收敛到 \(F(x)\)，其中 \(x\in(0,1)\) 是把 \(D\) 共形映射到上半平面且 \(a,c,d\mapsto0,1,\infty\) 的映射在 \(b\) 处的值，而 \(F(x)=\frac{\int_0^x[u(1-u)]^{-2/3}\,du}{\int_0^1[u(1-u)]^{-2/3}\,du}\)，等价于 \(\frac{\Gamma(2/3)x^{1/3}}{\Gamma(1/3)\Gamma(4/3)}\,{}_2F_1(\frac13,\frac23;\frac43;x)\)。推论：对固定矩形，条件于几何的跨越概率经 Vanneuville 的方差界得到淬火 \(L^2\) 收敛。

## 证明思路

出发点是把 Smirnov 式的精确恒等式搬到随机对偶图上。取泊松点的 Delaunay 三角化与其对偶图，分离相反颜色的对偶边构成集群边界电路（circuit）；对每条电路 \(L\) 删去其全部顶点，保留余图连通分量 \(C\)，以完整标签 \((L,C)\) 记之。除孤立开边外，各分量具有取向的单色原始边界 \(P\)，称为 rim。每个三角形是参考正三角形在保向实仿射映射下的像，该映射分解出的复线性与反线性部分把边的顺时针向量拆成两项，对 rim 各边以测试函数 \(f\) 加权求和分别得 \(U_P(f)\) 与 \(Q_P(f)\)：\(Q\) 度量偏离等边几何的程度，\(V_P=U_P+Q_P\) 是加权切向位移。精确的正交性恒等式对每个 Fourier 场成立，闭 rim 上 \(V_P(1)=0\)，平稳性使 \(Q\) 的宏观闭和变小。主要任务是把闭恒等式"打开"成弧上的关系：沿公共微观子列证明 \(Q_P(f)-aV_P(f)\to0\)。为此在称为 plug 的确定性区域保留端点附近的局部染色构型，用分离的双色走廊拼成闭实验；条件重采样产生一个只依赖两端状态的函数，其在固定环路上的求和很小，并可分解为仿射位移、两个端点势与受控余项。回到真实 rim 时有两个陷阱：其一，弧已被局部几何与颜色选中，比较必须保留此条件——用臂估计在每条 rim 附近提供有限的 plug 模型菜单，以受原始定律控制的无归一次概率作比较，不除以依赖构型的拟合概率；其二，符号场的小摄动不受路径长度控制——由确定性空间加细、近返回界与正交恒等式提供抵消。最后证 \(1-2\operatorname{Re}a>0\)，故所需系数 \(1-a\ne0\)：在有限离散圆盘外补三个标记顶点，闭合于一个外部三角形，该处分量观测量的一个边界系数恰为跨越概率；正交性与传输关系给出围道抵消，极限满足 Cauchy–Riemann 方程。标量 \(a\) 本身无需识别——一旦非退化它便从方程中消失，剩余边值问题以到等边三角形的共形映射为唯一解（Carleson 表示），从而识别所有子列极限；最终经 Schoenflies 图表中的确定性比较，把多边形近似转移到任意 Jordan 域的精确闭胞跨越事件。

## 可信度与备注

主结果未形式化。本文是同族的输入源头：另两篇分别以它为假设推出淬火近临界普适性定理与 pivotal 振幅 \(\varepsilon^{-3/4}\)，形成一条完整的推理链。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
