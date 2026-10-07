---
layout: default
title: "Radial transfer estimates and polygon length laws for honeycomb walks"
family: "237"
discipline: "Probability and statistical mechanics"
formalized: false
source: null
pdfname: ""
---

{% raw %}
# 解读 | Radial transfer estimates and polygon length laws for honeycomb walks

> 结果族 237：The three-quarter exponent for honeycomb self-avoiding walk　·　学科：Probability and statistical mechanics　·　验证状态：暂无形式化证明，请以社区核验为准

## 一句话结论

在蜂窝格点上证明了临界自回避多边形（polygon）的两条直径尾律：无根质量为 \(r^{-2+o(1)}\)、长度加权质量为 \(r^{-2/3+o(1)}\)；由此长度至少 \(n\) 的多边形直径依概率为 \(n^{3/4+o(1)}\)，严格确立了 Nienhuis 预言的 3/4 尺寸指数的多边形形式。

## 问题背景

自回避多边形是自回避行走（self-avoiding walk）的闭合版本，按边数以临界权重 \(w(\gamma)=x_*^{L(\gamma)}\) 计数，其中 \(x_*=(2+\sqrt2)^{-1/2}\)。Nienhuis 1982 年借稀释 \(O(n)\) 模型预言了这一临界活性与平面标度指数族，包括尺寸指数 \(3/4\)；Duminil-Copin 与 Smirnov（2012）用仲费米观测（parafermionic observable）严格证明了 \(x_*\) 是蜂窝连通常数，但 \(3/4\) 本身始终停留在预言层面，Lawler–Schramm–Werner 只能从尚未证明的 \(\mathrm{SLE}_{8/3}\) 标度极限猜想把它恢复出来。多边形版本的难点尤为具体：一个大多边形可以远比其直径"长"，长度与直径这两个尺寸在临界权重下如何相配，此前没有任何匹配的双侧估计。本文正面解决了这个问题。

## 主要结果

记 \(\gamma\) 为按平移等价类计数的多边形，\(L(\gamma)\) 为边数、\(D(\gamma)\) 为欧氏直径。定理 1.1 证明：直径尾质量

\[A(r)=\sum_{D(\gamma)\ge r}w(\gamma)=r^{-2+o(1)},\qquad P(r)=\sum_{D(\gamma)\ge r}L(\gamma)\,w(\gamma)=r^{-2/3+o(1)},\]

并附带截断二阶矩（truncated second moment） bound \(M_2(r)=\sum_{D(\gamma)\le r}L(\gamma)^2w(\gamma)\le r^{2/3+o(1)}\)，它阻止过多临界质量被"直径小而极长"的多边形携带。推论 1.2 把尾律换成长度截断：\(\sum_{L\ge n}w=n^{-3/2+o(1)}\)、\(\sum_{L\ge n}Lw=n^{-1/2+o(1)}\)，从而在任一归一化下、条件于 \(L(\gamma)\ge n\)，有 \(D(\gamma)=n^{3/4+o(1)}\) 依概率成立——这正是 Nienhuis 指数；反向条件于 \(D\ge r\) 的长度加权定律给出 \(L=r^{4/3+o(1)}\)，无根定律的条件平均长度亦为 \(R^{4/3+o(1)}\)。文中还导出：固定近距端点的半平面行走有同样的条件平均长度；半平面拱（arch）质量 \(\asymp n^{-5/4}\)、带（strip）穿越质量 \(\asymp H^{-1/4}\) 且可限制在指定走廊内；以及收敛半径间隙 \(0\le x_{\rm strip}(W)-x_*\le W^{-4/3+o(1)}\)。

## 证明思路

先把平面多边形投影到周长 \(N|h|\) 的柱面（cylinder）上：投影后要么仍单射（可收缩柱面多边形），要么与自身平移像相撞。文章在取极限之前用有限转移矩阵（transfer matrix）比较两类质量。代数核心是两个缝捻（seam twist）\(\eta=\pm i\) 的多项式固定向量：其带标记收缩分别数出"缠绕加可收缩"与"缠绕减可收缩"，相加即分离出正的缠绕质量 \(E_N\)，并满足精确恒等式 \(E_N\tau_N=(2-\sqrt2)\tau^v_{N-1}\)；行列式计算证明 \(\tau_N\ne0\)，于是正质量被表为两个本身未必为正的有限和之比。再估计该比值：先经格点顶点算子（vertex operator）式的角向展开（双线性型不定，故先逐系数处理），后转为径向（radial）级数——插入电荷置于实轴位置并携带分段常数斜率（slope），斜率平方沿径向产生指数代价，中央标记大电荷在对数宽度区域内压制多数插入类型。最大的障碍是变换后的表达式全为复数，既非概率也非正权，形式首指数可能因系数消失而失真；作者以强制性（coercivity）不等式 \(\Re\sum_{x<y}t_xt_y\mathcal Q(x,y)\ge c\sum_I(\sum_{x\in I}t_x)^2-C\sum_x t_x^2\) 保证绝对收敛并产生紧算子（compact operator），谱信息全部来自精确迹恒等式，而第 4 节的正缠绕界防止首系数消失，最终得单标记指数 \(-2/3\)；双标记时三区贡献合成 \(k^{-9/8}(N/k)^{5/24}N^{-5/24}=k^{-4/3}\)，给出二阶矩。最后转回平面：长度加权投影损失恰为 \(E_N\)，无根损失 \(\asymp N^{-2}\)；失败投影的直径必 \(\ge|h|N\) 给下界，反向取三对称定向、\(N=\lfloor R^{1-\epsilon}\rfloor\) 并用薄柱面横距估计排除高瘦投影，即得两条直径尾。

## 可信度与备注

本文主结果暂无 Lean 形式化证明；按 OpenAI 官方声明，未经形式化的结果可能有问题，请以社区核验为准。它是结果族 237 的多边形支柱：姊妹篇《Critical honeycomb chords with prescribed boundary endpoints》证明边界弦的 \(R^{4/3}\) 长度定律、《Cylinder loop weights and planar nesting》确定环路嵌套指数，三篇从多边形尾、边界弦、嵌套配分三个侧面共同支撑族级主张"n 步行走直径为 \(n^{3/4+o(1)}\)"（族说明附有 Lean 文档，但覆盖的是族级主张而非本文逐条定理）。

{% endraw %}
