---
layout: default
title: "Canonical conformal limits of subcritical FK planar maps"
family: "211"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Canonical conformal limits of subcritical FK planar maps

> 结果族 211：The geometric phase diagram, diffusion, and spectra of random planar maps　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

对每个固定的 \(0<q<4\)，本文证明：球面 FK 随机平面图按其“旗帜三角形”共形嵌入后，联合收敛到单位面积 LQG 量子球面并伴随独立的共形环系装饰；面积测度、经确定性重标的全体顶点图距离以及全部嵌套界面同时收敛。

## 问题背景

随机平面图（random planar map）是随机二维几何的离散模型，核心问题是在指定的共形坐标下识别其尺度极限，并同时保留面积、内蕴距离与统计力学装饰。Liouville 量子引力（LQG）的面积测度由高斯乘性混沌（Gaussian multiplicative chaos）理论构造。直觉预言：临界 Fortuin–Kasteleyn（FK）随机团簇模型装饰的地图，其界面收敛到共形环系（CLE），且在共形坐标下与 LQG 曲面独立。此前 Gwynne–Mao–Sun、Gwynne–Sun 等经树编码（mating of trees）识别了极限曲面；Gwynne–Miller–Sheffield 证明了 mated-CRT 图 Tutte 嵌入的收敛，Holden–Sun 证明了 \(\gamma=\sqrt{8/3}\) 多边形的 Cardy 嵌入收敛，但都针对别的模型律或嵌入输入。共形嵌入普适性猜想（HS 综述 Conjecture 3.5）在有限球面 FK 模型上悬而未决，难点有二：编码收敛不给出嵌入几何的比较，内蕴度量空间的极限本身也不说明离散顶点落在该坐标的何处。

## 主要结果

固定 \(q\in(0,4)\)，参数 \(\gamma\in(\sqrt2,2)\)、\(\kappa\in(4,8)\) 由 \(q=2+2\cos(\pi\gamma^2/2)\)、\(\kappa=16/\gamma^2\) 确定。\(n\) 边根地图对 \((M_n,A_n)\) 按权 \(q^{\ell(M,A)/2}\) 采样，其中 \(\ell=k(A)+k(A^*)-1\) 计 FK 界面数；其 \(4n\) 个等边旗帜三角形粘成共形球面 \(X_n\)，由三个独立面积采样点定出保向单值化（uniformization）\(\phi_n:X_n\to\widehat{\mathbb C}\)（依次送到 \(0,1,\infty\)），\(d_n\) 为用全部原始边的图距离。主定理：存在确定性序列 \(a_n\to0\)，使
\[\big((\phi_n)_*m_n,\;K_n(a_n),\;\Gamma_n\big)\Longrightarrow\big(\mu_h,\;\{(z,w,D_h(z,w)):z,w\in\widehat{\mathbb C}\},\;\Gamma\big),\]
其中 \(K_n(a)=\{(\phi_n(u),\phi_n(v),a\,d_n(u,v))\}\) 是嵌入距离图；三种拓扑分别是面积测度弱收敛、距离图的 Hausdorff 收敛、以及保序保重数的环匹配收敛，极限 \(\Gamma\) 为 Möbius 不变的整体嵌套 \(\mathrm{CLE}_\kappa\)，与嵌入曲面条件独立。同时最大旗帜直径依概率趋于零。距离图断言覆盖一切收敛顶点对（包括度数反常的顶点）；论文不主张 \(q=4\) 端点、收敛速率或 \(a_n\) 的显式公式。

## 证明思路

先统一舞台：由轮廓极限与连续缝合得到从旗帜曲面到参考 LQG 球面的同胚 \(H_n\)，使每个旗帜的像都足够小；这些同胚保持分离与相交关系，但尚不比较共形模与长度。为此构造“受保护的局部数据”：保留探索过程对每个紧圆盘的全部访问、周围缓冲区及原始与对偶顶点的关联，得到有限记录，从中能读出小端点集间的最小图费用或四边形极值长度（extremal length）。核心是核定理（local kernels）：给定整个连续曲面与探索，局部读出的条件律只依赖保留的局部输入，不相交保护区有乘积条件律；证明靠一个精确的字重采样恒等式——从双边无穷词换成有限条件词只改变连续输入的密度（阶梯块分解与 Doney 双变量稳定局部极限定理控制格点磨光），故同一核可转移到普通高斯场以及实际面积归一化高度的球面律上。再由逐点多半径的成功环（annuli）论证统一供给概率输入。共形一支：反证排除旗帜曲面极值长度的退化——过小的交叉模会产生低交通能量的路径流，其极限为非常值的可求长曲线；旋转协变性进一步在同一点给出两个横截方向的便宜交叉，与四边形互反性矛盾。由此得 \(\phi_n\circ H_n^{-1}\) 的拟共形（quasiconformal）极限，场芽的平凡性加上旋转协变性使它的无穷小共形结构为圆形，三个面积标记最终固定共形映射，面积与网格结论随之。界面一支：柔性顺序匹配在探索时间圆上形成不交叉的弦系统，其面恰好编码有限 FK 环及循环遍历顺序；\(\mathrm{CLE}\) 探索识别各环的初始段，双侧缠绕测试排除被略去的移动段，于是每条宏观环连同重数与嵌套层级都被匹配。度量一支：小端点集之间的图通道先与参考 LQG 度量比较，反复的环上机会与局部有限能量场改变把参考测地线带到捷径附近，加权测度变换迫使最优上下比较常数相等（改造 Gwynne–Miller 最优常数法）；通道端点是自由选取的小集合，要到达指定格点顶点则需补全——此处引用姊妹篇的 Gromov–Hausdorff 输入定标，小环绕电路与球面拓扑排除非平凡空间纤维，两个分离的正逃逸费用测试排除整体塌缩，最终全顶点度量为 \(D_h\) 的确定性倍数，倍数由内蕴直径律确定。

## 可信度与备注

本文主结果暂无 Lean 形式化证明。其度量环节直接引用同日姊妹篇《Metric-measure limits of subcritical FK and spanning-tree planar maps》（同族）定理 1.1 的 GH 推论作为内蕴输入，\(q=4\) 端点由族内另一姊妹篇独立处理；三篇合起来支撑族 211 的“曲面对树”几何相图在 \(0<q\le4\) 一侧的结论。按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。

{% endraw %}
